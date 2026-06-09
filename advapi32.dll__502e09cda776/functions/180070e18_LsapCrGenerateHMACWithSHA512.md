# LsapCrGenerateHMACWithSHA512

- ea: `0x180070e18`
- end: `0x180071043`
- name: `LsapCrGenerateHMACWithSHA512`
- size: `555`
- prototype: `__int64 __usercall@<rax>(BCRYPT_ALG_HANDLE hAlgorithm@<rcx>, ULONG cbInput, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180071118`
- `0x1800714f0`

## callees

- `0x180070e18`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180070eb7`
- `KERNELBASE!LocalAlloc` at `0x180070f1e`
- `KERNELBASE!LocalAlloc` at `0x180070eb7`
- `KERNELBASE!LocalAlloc` at `0x180070f1e`
- `KERNEL32!LocalFree` at `0x180070ff1`
- `KERNEL32!LocalFree` at `0x18007101c`
- `KERNEL32!LocalFree` at `0x180070ff1`
- `KERNEL32!LocalFree` at `0x18007101c`
- `bcrypt!BCryptDestroyHash` at `0x180070fc6`
- `bcrypt!BCryptDestroyHash` at `0x180070fc6`
- `bcrypt!BCryptHashData` at `0x180070f77`
- `bcrypt!BCryptHashData` at `0x180070f77`
- `bcrypt!BCryptCreateHash` at `0x180070f56`
- `bcrypt!BCryptCreateHash` at `0x180070f56`
- `bcrypt!BCryptFinishHash` at `0x180070f97`
- `bcrypt!BCryptFinishHash` at `0x180070f97`
- `bcrypt!BCryptGetProperty` at `0x180070e91`
- `bcrypt!BCryptGetProperty` at `0x180070ef6`
- `bcrypt!BCryptGetProperty` at `0x180070e91`
- `bcrypt!BCryptGetProperty` at `0x180070ef6`

## pseudocode

```c

```
