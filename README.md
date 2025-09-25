# HoareWhileVerifier

A **Program Verifier** for a simple **While language** using **Hoare Logic**, implemented in **C#**. This tool takes programs with their formal specifications (preconditions and postconditions) and verifies their correctness using automated theorem proving with Z3 SMT solver.
Link to descriptions: [Week 1 project](https://github.com/yasaminashoori/CS_ReadingClub/blob/master/week1/README.md)
## 🎯 Overview

This project implements a complete verification pipeline for imperative programs written in a simple While language. The verifier uses Hoare Logic to generate verification conditions and leverages the Z3 SMT solver to automatically prove program correctness.

## ✨ Features
These features are in progress....
- **Parser**: Reads While programs and their specifications
- **Hoare Logic Engine**: Generates verification conditions using formal rules
- **Z3 Integration**: Automatically proves or disproves verification conditions
- **Error Reporting**: Detailed feedback when verification fails
- **Extensible Architecture**: Easy to add new language constructs

## 🏗️ Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   While Program │───▶│     Parser      │───▶│   AST & Specs   │
└─────────────────┘    └─────────────────┘    └─────────────────┘
                                                        │
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│  Z3 SMT Solver  │◀───│ Hoare Logic VCG │◀───│  Verification   │
└─────────────────┘    └─────────────────┘    │   Condition     │
          │                                   │   Generator     │
          ▼                                   └─────────────────┘
┌─────────────────┐
│ Verification    │
│ Result          │
└─────────────────┘
```

## 🚀 Getting Started

### Prerequisites

- **.NET 6.0** or later
- **Z3 Solver** (automatically installed via NuGet package)

### Installation

```bash
git clone https://github.com/yasaminashoori/HoareWhileVerifier.git
cd HoareWhileVerifier
dotnet restore
dotnet build
```

### Quick Start

1. **Create a While program** (example.while):
```
// Specification
requires: x >= 0
ensures: result = x * x

// Program
y := 0;
i := 0;
while (i < x) do
    y := y + x;
    i := i + 1
od;
result := y
```

2. **Run the verifier**:
```bash
dotnet run example.while
```


## 🧮 Implementation Steps

### Phase 1: Core Infrastructure
- [ ] Define AST nodes for expressions and statements
- [ ] Implement lexer for tokenization
- [ ] Build recursive descent parser
- [ ] Add basic error handling

### Phase 2: Hoare Logic Engine  
- [ ] Implement verification condition generation
- [ ] Add support for assignment rule
- [ ] Handle sequential composition
- [ ] Implement conditional statement verification

### Phase 3: Loop Verification
- [ ] Add while loop invariant checking
- [ ] Implement loop invariant inference (advanced)
- [ ] Handle nested loops

### Phase 4: SMT Integration
- [ ] Integrate Z3 .NET API
- [ ] Convert verification conditions to Z3 format
- [ ] Parse and report Z3 results

### Phase 5: Testing & Examples
- [ ] Create comprehensive test suite
- [ ] Add example programs
- [ ] Performance op
