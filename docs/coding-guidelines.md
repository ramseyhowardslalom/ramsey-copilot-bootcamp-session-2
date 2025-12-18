# Coding Guidelines

## Overview
This document outlines the coding style and quality principles for the TODO application to ensure consistent, maintainable, and high-quality code across the project.

## Language and Type Safety

### TypeScript
The application is built using TypeScript to provide:
- Static type checking at compile time
- Enhanced IDE support with intelligent code completion
- Better code documentation through type definitions
- Reduced runtime errors through early detection of type-related issues
- Improved code maintainability and refactoring capabilities

All new code must be written in TypeScript with proper type annotations. Avoid using `any` type unless absolutely necessary, and document the reason when it is used.

## Code Quality Tools

### ESLint
ESLint is used to enforce code quality and consistency standards:
- Catches potential bugs and code smells
- Enforces consistent coding patterns
- Helps maintain code readability
- Configured with TypeScript-specific rules

### Prettier
Prettier is used for automatic code formatting:
- Ensures consistent code style across the entire codebase
- Removes debates about formatting preferences
- Automatically formats code on save or commit
- Works seamlessly with ESLint

### Quality Checks
Run `npm run check` to verify code quality before committing:
- Runs ESLint to check for code quality issues
- Runs TypeScript compiler to check for type errors
- Runs Prettier to verify code formatting
- All checks must pass before code can be merged

## Code Organization

### Module Imports
Use absolute imports instead of relative imports to improve code readability and maintainability:

**Preferred (Absolute Imports)**:
```typescript
import { TaskService } from '@/services/task-service';
import { Button } from '@/components/button';
```

**Avoid (Relative Imports)**:
```typescript
import { TaskService } from '../../../services/task-service';
import { Button } from '../../components/button';
```

Benefits of absolute imports:
- Easier to read and understand module dependencies
- No need to count directory levels
- Files can be moved without updating import paths
- More maintainable as the project grows

## Naming Conventions

### Kebab Case for Files and Folders
Use kebab-case (lowercase with hyphens) for all file and folder names:

**Correct**:
- `task-service.ts`
- `user-profile.tsx`
- `api-client.ts`
- `components/task-list/`

**Incorrect**:
- `TaskService.ts` (PascalCase)
- `user_profile.tsx` (snake_case)
- `apiClient.ts` (camelCase)

### Other Naming Conventions
- **Variables and Functions**: camelCase (e.g., `getUserName`, `taskList`)
- **Classes and Interfaces**: PascalCase (e.g., `TaskService`, `UserProfile`)
- **Constants**: UPPER_SNAKE_CASE (e.g., `MAX_RETRY_COUNT`, `API_BASE_URL`)
- **Type Aliases**: PascalCase (e.g., `TaskStatus`, `FilterOptions`)

## Code Style Principles

### Readability
- Write self-documenting code with clear, descriptive names
- Keep functions small and focused on a single responsibility
- Use comments to explain "why" rather than "what"
- Maintain consistent indentation and spacing (handled by Prettier)

### Maintainability
- Follow DRY (Don't Repeat Yourself) principle
- Extract reusable logic into utility functions or services
- Keep components and modules loosely coupled
- Write code that is easy to test

### Best Practices
- Use meaningful variable and function names
- Avoid deeply nested code structures
- Handle errors gracefully with proper error messages
- Use async/await for asynchronous operations
- Leverage TypeScript's type system to catch errors early

## Development Workflow

### Before Committing
1. Run `npm run check` to verify code quality
2. Ensure all tests pass
3. Review your changes for potential issues
4. Verify that TypeScript compilation succeeds
5. Ensure Prettier has formatted all files

### Code Review Standards
- All code must pass automated quality checks
- Code should follow the principles outlined in this document
- Reviewers should verify adherence to TypeScript best practices
- Focus on code clarity, maintainability, and correctness
