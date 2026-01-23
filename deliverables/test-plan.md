# Test Plan for ATM Simulation System - SENG 637 Assignment 1

## 1. Introduction

This test plan outlines the testing strategy for the provided ATM Machine Simulation System (versions 1.0 and 1.1). The plan covers exploratory testing, manual scripted testing, and regression testing phases to ensure comprehensive coverage of the system's functionality and proper defect tracking.

## 2. Test Types

### 2.1 Exploratory Testing (Manual Non-Scripted)
- **Purpose**: To explore the functionalities of the system and uncover defects through ad-hoc testing without predefined test cases
- **Duration**: Approximately 30 minutes per pair
- **Approach**: Testers will explore the system freely based on their understanding of requirements
- **Documentation**: Defects discovered will be logged immediately in the bug tracking system

### 2.2 Manual Scripted Testing
- **Purpose**: Systematically verify system functionality against predefined test cases
- **Test Suite**: 40 test cases provided in Appendix C of the assignment
- **Coverage**: 
  - System Startup and Shutdown
  - Session Management
  - Transaction Processing
  - Withdrawal Operations
- **Documentation**: Defects will be prefixed with "MFT:" in the summary field

### 2.3 Regression Testing
- **Purpose**: Verify bug fixes and identify new defects introduced in version 1.1
- **Scope**: Retest all defects found in version 1.0 and execute the scripted test suite again
- **Documentation**: Update defect status (Resolved/Fixed or In-Progress) and report new defects specific to version 1.1

## 3. Scope of Testing

### 3.1 In-Scope Functionalities

#### System Operations
- System startup with initial cash amount entry
- System shutdown when not servicing customers
- Connection establishment with the bank

#### Session Management
- ATM card reading and validation
- PIN entry and validation (including invalid PIN handling)
- Multi-transaction sessions
- Session termination and card ejection

#### Transaction Types
- **Withdrawal**: Account selection, amount selection, cash dispensing, receipt printing
- **Deposit**: Account selection, amount entry, envelope insertion
- **Transfer**: Source and destination account selection, amount entry
- **Balance Inquiry**: Account selection, balance display

#### Security Features
- Invalid PIN handling (3 attempts maximum)
- Card retention after failed authentication
- Transaction logging (excluding PINs)

#### Error Handling
- Insufficient cash in ATM
- Insufficient balance in account
- Unreadable card rejection
- Transaction cancellation

### 3.2 Out-of-Scope
- Bank-side validation logic (external system)
- Physical hardware components
- Network communication protocols
- Database integrity
- Performance and load testing
- Security penetration testing

### 3.3 Test Environment
- **System Under Test**: ATM System JAR files (v1.0 and v1.1)
- **Platform**: Java Runtime Environment
- **Test Data**:
  - Card Number: 1
  - PIN: 42
  - Initial Balances: Checking $100, Savings $1,000, Money Market $5,000
- **Defect Tracking**: Atlassian Jira or Azure DevOps

## 4. Test Logistics

### 4.1 Team Structure
Testing will be conducted using pair testing methodology with groups of 2-4 members divided into pairs.

### 4.2 Role Assignment

#### Exploratory Testing Phase
- **Pair 1**: 
  - **Tester**: Operates the system and executes test scenarios
  - **Recorder**: Documents defects, observations, and test coverage
  - **Focus Areas**: System startup/shutdown, session management, withdrawal operations

- **Pair 2**:
  - **Tester**: Operates the system and executes test scenarios
  - **Recorder**: Documents defects, observations, and test coverage
  - **Focus Areas**: Deposit operations, transfer operations, balance inquiry, error scenarios

#### Manual Scripted Testing Phase
- **Combined Group Activity**: All team members work together
- **Driver**: One student operates the ATM system and executes test cases
- **Navigator**: Other students track test execution, verify results, and report defects
- **Test Case Distribution**: Execute all 17 test cases sequentially
  - Test Cases 1-4: System Startup and Shutdown
  - Test Cases 5-11: Session Management
  - Test Cases 12-17: Withdrawal Transactions

#### Regression Testing Phase
- **Defect Verification**: Divided among all group members
- Each member retests assigned defects from version 1.0 in version 1.1
- **New Defect Discovery**: Combined group activity re-executing the scripted test suite
- **Status Updates**: Each member updates status of their assigned defects

### 4.3 Test Execution Schedule

| Phase | Duration | Responsible Party |
|-------|----------|-------------------|
| Familiarization with SUT | 15 minutes | All team members |
| Exploratory Testing - Pair 1 | 30 minutes | Pair 1 |
| Exploratory Testing - Pair 2 | 30 minutes | Pair 2 |
| Defect Review & Consolidation | 20 minutes | All team members |
| Manual Scripted Testing | 45 minutes | Combined group |
| Regression Testing - Defect Retesting | 30 minutes | Individual members |
| Regression Testing - New Defects | 30 minutes | Combined group |
| Final Review & Report Preparation | 40 minutes | All team members |

### 4.4 Defect Reporting Guidelines

**All defect reports must include:**
1. Function being tested
2. Initial state of the system
3. Detailed steps to reproduce
4. Expected outcome
5. Actual outcome
6. Priority/Severity (Low, Medium, High, Critical)
7. Version of SUT (1.0 or 1.1)
8. Phase identifier (exploratory or "MFT:" prefix for manual scripted testing)

### 4.5 Communication and Coordination
- Regular sync-ups between pairs after exploratory testing
- Peer review of defect reports before final submission
- Collaborative discussion for ambiguous defects or edge cases
- Shared documentation repository for test notes and observations

## 5. Entry and Exit Criteria

### 5.1 Entry Criteria
- ATM system JAR files (v1.0 and v1.1) downloaded and executable
- Requirements documentation (Appendix B) reviewed by all team members
- Defect tracking system (Jira/Azure DevOps) set up and accessible
- Test environment configured with Java runtime
- Team members trained on pair testing methodology

### 5.2 Exit Criteria
- All 17 scripted test cases executed at least once in both versions
- 30 minutes of exploratory testing completed by each pair
- All discovered defects documented with complete information
- Regression testing completed for all version 1.0 defects
- Defect reports peer-reviewed and consolidated
- Lab report completed with required sections

## 6. Risk Assessment

| Risk | Impact | Mitigation |
|------|--------|------------|
| Incomplete understanding of requirements | High | Thorough review of Appendix B before testing |
| Missed defects during exploratory testing | Medium | Two pairs testing independently increases coverage |
| Inconsistent defect reporting | Medium | Use standardized template and peer review |
| Time constraints | Medium | Prioritize critical functionality and high-severity defects |
| Version confusion | Low | Clear labeling and separate tracking for v1.0 and v1.1 |

## 7. Deliverables

1. Consolidated defect report (Markdown format)
2. Lab report in markdown format containing:
   - This test plan
   - Comparison of exploratory vs. manual testing
   - Peer review notes
   - Reflection and lessons learned
   - Feedback on the assignment
