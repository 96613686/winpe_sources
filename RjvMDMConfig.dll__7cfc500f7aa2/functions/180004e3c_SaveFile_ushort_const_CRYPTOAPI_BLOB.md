# SaveFile(ushort const *,_CRYPTOAPI_BLOB *)

- ea: `0x180004e3c`
- end: `0x180004efb`
- name: `?SaveFile@@YAJPEBGPEAU_CRYPTOAPI_BLOB@@@Z`
- size: `191`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _CRYPTOAPI_BLOB *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1800039fc`

## callees

- `0x1800038c0`
- `0x180004e3c`
- `0x1800055f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ec8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004ec8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004eb8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004eb8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004e7b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004e7b`

## pseudocode

```c
__int64 __fastcall SaveFile(const unsigned __int16 *a1, struct _CRYPTOAPI_BLOB *a2)
{
  HANDLE FileW; // rax
  unsigned int v4; // ebx
  signed int LastError; // eax
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp+18h] BYREF
  HANDLE hFile; // [rsp+68h] [rbp+20h] BYREF

  NumberOfBytesWritten = 0;
  hFile = (HANDLE)-1LL;
  FileW = CreateFileW(a1, 0x40000000u, 0, 0, 2u, 0x80u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hFile,
    FileW);
  if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0
    || (v4 = 0, !WriteFile(hFile, a2->pbData, a2->cbData, &NumberOfBytesWritten, 0)) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
  return v4;
}

```

## disassembly

```asm
0x180004e3c  mov     rax, rsp
0x180004e3f  mov     [rax+8], rbx
0x180004e43  push    rdi
0x180004e44  sub     rsp, 40h
0x180004e48  mov     qword ptr [rax-18h], 0
0x180004e50  mov     rdi, rdx
0x180004e53  mov     dword ptr [rax-20h], 80h
0x180004e5a  mov     edx, 40000000h; dwDesiredAccess
0x180004e5f  xor     r9d, r9d; lpSecurityAttributes
0x180004e62  mov     dword ptr [rax-28h], 2
0x180004e69  xor     r8d, r8d; dwShareMode
0x180004e6c  mov     dword ptr [rax+18h], 0
0x180004e73  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x180004e7b  call    cs:__imp_CreateFileW
0x180004e82  nop     dword ptr [rax+rax+00h]
0x180004e87  mov     rdx, rax
0x180004e8a  lea     rcx, [rsp+48h+hFile]
0x180004e8f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180004e94  mov     rcx, [rsp+48h+hFile]; hFile
0x180004e99  lea     rax, [rcx+1]
0x180004e9d  test    rax, 0FFFFFFFFFFFFFFFEh
0x180004ea3  jz      short loc_180004EC8
0x180004ea5  mov     r8d, [rdi]; nNumberOfBytesToWrite
0x180004ea8  lea     r9, [rsp+48h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180004ead  mov     rdx, [rdi+8]; lpBuffer
0x180004eb1  xor     ebx, ebx
0x180004eb3  mov     [rsp+48h+lpOverlapped], rbx; lpOverlapped
0x180004eb8  call    cs:__imp_WriteFile
0x180004ebf  nop     dword ptr [rax+rax+00h]
0x180004ec4  test    eax, eax
0x180004ec6  jnz     short loc_180004EE3
0x180004ec8  call    cs:__imp_GetLastError
0x180004ecf  nop     dword ptr [rax+rax+00h]
0x180004ed4  mov     ebx, eax
0x180004ed6  test    eax, eax
0x180004ed8  jle     short loc_180004EE3
0x180004eda  movzx   ebx, ax
0x180004edd  or      ebx, 80070000h
0x180004ee3  lea     rcx, [rsp+48h+hFile]
0x180004ee8  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180004eed  mov     eax, ebx
0x180004eef  mov     rbx, [rsp+48h+arg_0]
0x180004ef4  add     rsp, 40h
0x180004ef8  pop     rdi
0x180004ef9  retn
```
