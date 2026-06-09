# LsapGenerateHMACWithSHA512

- ea: `0x180047ef0`
- end: `0x1800480e4`
- name: `LsapGenerateHMACWithSHA512`
- size: `500`
- prototype: `__int64 __usercall@<rax>(BCRYPT_ALG_HANDLE hAlgorithm@<rcx>, ULONG cbInput, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800479c0`

## callees

- `0x180047ef0`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180047f90`
- `KERNELBASE!LocalAlloc` at `0x180047ff7`
- `KERNELBASE!LocalAlloc` at `0x180047f90`
- `KERNELBASE!LocalAlloc` at `0x180047ff7`
- `KERNEL32!LocalFree` at `0x1800480ae`
- `KERNEL32!LocalFree` at `0x1800480bd`
- `KERNEL32!LocalFree` at `0x1800480ae`
- `KERNEL32!LocalFree` at `0x1800480bd`
- `bcrypt!BCryptDestroyHash` at `0x18004809f`
- `bcrypt!BCryptDestroyHash` at `0x18004809f`
- `bcrypt!BCryptHashData` at `0x180048050`
- `bcrypt!BCryptHashData` at `0x180048050`
- `bcrypt!BCryptCreateHash` at `0x18004802f`
- `bcrypt!BCryptCreateHash` at `0x18004802f`
- `bcrypt!BCryptFinishHash` at `0x180048070`
- `bcrypt!BCryptFinishHash` at `0x180048070`
- `bcrypt!BCryptGetProperty` at `0x180047f6a`
- `bcrypt!BCryptGetProperty` at `0x180047fcf`
- `bcrypt!BCryptGetProperty` at `0x180047f6a`
- `bcrypt!BCryptGetProperty` at `0x180047fcf`

## pseudocode

```c

```
