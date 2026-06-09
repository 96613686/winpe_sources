# DSUtils::SetFileAttributesToNormal(ushort const *)

- ea: `0x18001a93c`
- end: `0x18001a9e1`
- name: `?SetFileAttributesToNormal@DSUtils@@YAJPEBG@Z`
- size: `165`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000ca4c`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18001a93c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a954`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a995`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001a98b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18001a98b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001a949`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001a949`

## string_xrefs

- `0x18001a9c0`: `DSUtils::SetFileAttributesToNormal`
- `0x18001a9af`: `Failed to SetFileAttributes (%s). hr=0x%x`

## pseudocode

```c
__int64 __fastcall DSUtils::SetFileAttributesToNormal(LPCWSTR lpFileName, const unsigned __int16 *a2)
{
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  unsigned int v5; // ebx
  DSLogger *v6; // rax
  const unsigned __int16 *v7; // r9
  unsigned int v8; // r8d
  signed int v9; // eax
  unsigned int v11; // [rsp+28h] [rbp-10h]

  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    v6 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    v7 = L"Failed to GetFileAttributes (%s). hr=0x%x";
    v8 = 287;
LABEL_10:
    v11 = v5;
    DSLogger::LogError(v6, L"DSUtils::SetFileAttributesToNormal", v8, v7, lpFileName, v11);
    return v5;
  }
  v5 = 0;
  if ( FileAttributesW != 128 && !SetFileAttributesW(lpFileName, 0x80u) )
  {
    v9 = GetLastError();
    v5 = v9;
    if ( v9 > 0 )
      v5 = (unsigned __int16)v9 | 0x80070000;
    v6 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get();
    v7 = L"Failed to SetFileAttributes (%s). hr=0x%x";
    v8 = 298;
    goto LABEL_10;
  }
  return v5;
}

```

## disassembly

```asm
0x18001a93c  mov     [rsp+arg_0], rbx
0x18001a941  push    rdi
0x18001a942  sub     rsp, 30h
0x18001a946  mov     rdi, rcx
0x18001a949  call    cs:__imp_GetFileAttributesW
0x18001a94f  cmp     eax, 0FFFFFFFFh
0x18001a952  jnz     short loc_18001A97D
0x18001a954  call    cs:__imp_GetLastError
0x18001a95a  mov     ebx, eax
0x18001a95c  test    eax, eax
0x18001a95e  jle     short loc_18001A969
0x18001a960  movzx   ebx, ax
0x18001a963  or      ebx, 80070000h
0x18001a969  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001a96e  lea     r9, aFailedToGetfil; "Failed to GetFileAttributes (%s). hr=0x"...
0x18001a975  mov     r8d, 11Fh
0x18001a97b  jmp     short loc_18001A9BC
0x18001a97d  xor     ebx, ebx
0x18001a97f  mov     edx, 80h; dwFileAttributes
0x18001a984  cmp     eax, edx
0x18001a986  jz      short loc_18001A9D4
0x18001a988  mov     rcx, rdi; lpFileName
0x18001a98b  call    cs:__imp_SetFileAttributesW
0x18001a991  test    eax, eax
0x18001a993  jnz     short loc_18001A9D4
0x18001a995  call    cs:__imp_GetLastError
0x18001a99b  mov     ebx, eax
0x18001a99d  test    eax, eax
0x18001a99f  jle     short loc_18001A9AA
0x18001a9a1  movzx   ebx, ax
0x18001a9a4  or      ebx, 80070000h
0x18001a9aa  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001a9af  lea     r9, aFailedToSetfil; "Failed to SetFileAttributes (%s). hr=0x"...
0x18001a9b6  mov     r8d, 12Ah; unsigned int
0x18001a9bc  mov     [rsp+38h+var_10], ebx
0x18001a9c0  lea     rdx, aDsutilsSetfile; "DSUtils::SetFileAttributesToNormal"
0x18001a9c7  mov     rcx, rax; this
0x18001a9ca  mov     [rsp+38h+var_18], rdi
0x18001a9cf  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18001a9d4  mov     eax, ebx
0x18001a9d6  mov     rbx, [rsp+38h+arg_0]
0x18001a9db  add     rsp, 30h
0x18001a9df  pop     rdi
0x18001a9e0  retn
```
