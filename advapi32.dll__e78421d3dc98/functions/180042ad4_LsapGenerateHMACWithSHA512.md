# LsapGenerateHMACWithSHA512

- ea: `0x180042ad4`
- end: `0x180042c8b`
- name: `LsapGenerateHMACWithSHA512`
- size: `439`
- prototype: `__int64 __usercall@<rax>(BCRYPT_ALG_HANDLE hAlgorithm@<rcx>, ULONG cbInput, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180042604`

## callees

- `0x180042ad4`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180042b6e`
- `KERNELBASE!LocalAlloc` at `0x180042bc9`
- `KERNELBASE!LocalAlloc` at `0x180042b6e`
- `KERNELBASE!LocalAlloc` at `0x180042bc9`
- `KERNEL32!LocalFree` at `0x180042c62`
- `KERNEL32!LocalFree` at `0x180042c6b`
- `KERNEL32!LocalFree` at `0x180042c62`
- `KERNEL32!LocalFree` at `0x180042c6b`
- `bcrypt!BCryptDestroyHash` at `0x180042c59`
- `bcrypt!BCryptDestroyHash` at `0x180042c59`
- `bcrypt!BCryptHashData` at `0x180042c16`
- `bcrypt!BCryptHashData` at `0x180042c16`
- `bcrypt!BCryptCreateHash` at `0x180042bfb`
- `bcrypt!BCryptCreateHash` at `0x180042bfb`
- `bcrypt!BCryptFinishHash` at `0x180042c30`
- `bcrypt!BCryptFinishHash` at `0x180042c30`
- `bcrypt!BCryptGetProperty` at `0x180042b4e`
- `bcrypt!BCryptGetProperty` at `0x180042ba7`
- `bcrypt!BCryptGetProperty` at `0x180042b4e`
- `bcrypt!BCryptGetProperty` at `0x180042ba7`

## pseudocode

```c

```
