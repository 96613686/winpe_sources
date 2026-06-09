# LsapCrGenerateHMACWithSHA512

- ea: `0x180063f38`
- end: `0x180064126`
- name: `LsapCrGenerateHMACWithSHA512`
- size: `494`
- prototype: `__int64 __usercall@<rax>(BCRYPT_ALG_HANDLE hAlgorithm@<rcx>, ULONG cbInput, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800641ec`
- `0x180064594`

## callees

- `0x180063f38`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180063fd1`
- `KERNELBASE!LocalAlloc` at `0x18006402c`
- `KERNELBASE!LocalAlloc` at `0x180063fd1`
- `KERNELBASE!LocalAlloc` at `0x18006402c`
- `KERNEL32!LocalFree` at `0x1800640e1`
- `KERNEL32!LocalFree` at `0x180064106`
- `KERNEL32!LocalFree` at `0x1800640e1`
- `KERNEL32!LocalFree` at `0x180064106`
- `bcrypt!BCryptDestroyHash` at `0x1800640bc`
- `bcrypt!BCryptDestroyHash` at `0x1800640bc`
- `bcrypt!BCryptHashData` at `0x180064079`
- `bcrypt!BCryptHashData` at `0x180064079`
- `bcrypt!BCryptCreateHash` at `0x18006405e`
- `bcrypt!BCryptCreateHash` at `0x18006405e`
- `bcrypt!BCryptFinishHash` at `0x180064093`
- `bcrypt!BCryptFinishHash` at `0x180064093`
- `bcrypt!BCryptGetProperty` at `0x180063fb1`
- `bcrypt!BCryptGetProperty` at `0x18006400a`
- `bcrypt!BCryptGetProperty` at `0x180063fb1`
- `bcrypt!BCryptGetProperty` at `0x18006400a`

## pseudocode

```c

```
