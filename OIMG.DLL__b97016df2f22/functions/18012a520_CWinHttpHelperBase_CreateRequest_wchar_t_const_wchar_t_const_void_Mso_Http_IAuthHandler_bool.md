# CWinHttpHelperBase::CreateRequest(wchar_t const *,wchar_t const *,void * *,Mso::Http::IAuthHandler *,bool)

- ea: `0x18012a520`
- end: `0x18012a7bb`
- name: `?CreateRequest@CWinHttpHelperBase@@QEAAKPEB_W0PEAPEAXPEAVIAuthHandler@Http@Mso@@_N@Z`
- size: `667`
- prototype: `unsigned int __usercall@<eax>(CWinHttpHelperBase *__hidden this@<rcx>, const wchar_t *@<rdx>, const wchar_t *@<r8>, void **@<r9>, struct Mso::Http::IAuthHandler *, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180122900`

## callees

- `0x1800a17ec`
- `0x180129fb8`
- `0x18012a520`
- `0x18056bd00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18012a594`
- `KERNEL32!GetLastError` at `0x18012a65f`
- `KERNEL32!GetLastError` at `0x18012a6a1`
- `KERNEL32!GetLastError` at `0x18012a594`
- `KERNEL32!GetLastError` at `0x18012a65f`
- `KERNEL32!GetLastError` at `0x18012a6a1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012a654`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012a75a`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012a654`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18012a75a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012a64d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012a753`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012a64d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18012a753`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18012a691`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18012a691`
- `WINHTTP!WinHttpSetOption` at `0x18012a779`
- `WINHTTP!WinHttpSetOption` at `0x18012a779`
- `WINHTTP!WinHttpOpenRequest` at `0x18012a58b`
- `WINHTTP!WinHttpOpenRequest` at `0x18012a58b`

## string_xrefs

- `0x18012a6e2`: `Error: CreateRequest failed in WinHttpSetStatusCallback`
- `0x18012a5cc`: `Error: CreateRequest failed in WinHttpOpenRequest`

## pseudocode

```c

```
