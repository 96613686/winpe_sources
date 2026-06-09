# AppXDeleteFileWithDeleteOnClose(ushort const *)

- ea: `0x180184b8c`
- end: `0x180184c79`
- name: `?AppXDeleteFileWithDeleteOnClose@@YAJPEBG@Z`
- size: `237`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18006d5dc`

## callees

- `0x18000669c`
- `0x1800529ec`
- `0x180184b8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180184bb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180184bb8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180184bf8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180184bf8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180184ba4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180184ba4`
- `KERNEL32!SetFileInformationByHandle` at `0x180184c30`
- `KERNEL32!SetFileInformationByHandle` at `0x180184c30`

## string_xrefs

- `0x180184c4a`: `onecore\admin\appmodel\common\appxdeletefile.cpp`

## pseudocode

```c
__int64 __fastcall AppXDeleteFileWithDeleteOnClose(LPCWSTR lpFileName)
{
  HANDLE FileW; // rax
  const char *v4; // r9
  __int64 v5; // rdx
  unsigned int LastError; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int FileInformation; // [rsp+50h] [rbp+8h] BYREF
  HANDLE v9; // [rsp+58h] [rbp+10h] BYREF

  if ( !lpFileName )
    return 2147942487LL;
  if ( !DeleteFileW(lpFileName) && GetLastError() - 2 > 1 )
  {
    FileW = CreateFileW(lpFileName, 0x10000u, 7u, 0, 3u, 0x2200080u, 0);
    v9 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v5 = 139;
LABEL_9:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v5,
                    (unsigned int)"onecore\\admin\\appmodel\\common\\appxdeletefile.cpp",
                    v4);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
      return LastError;
    }
    FileInformation = 1;
    if ( !SetFileInformationByHandle(FileW, FileRenameInfoEx|FileDispositionInfo, &FileInformation, 4u) )
    {
      v5 = 144;
      goto LABEL_9;
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v9);
  }
  return 0;
}

```

## disassembly

```asm
0x180184b8c  push    rbx
0x180184b8e  sub     rsp, 40h
0x180184b92  mov     rbx, rcx
0x180184b95  test    rcx, rcx
0x180184b98  jnz     short loc_180184BA4
0x180184b9a  mov     eax, 80070057h
0x180184b9f  jmp     loc_180184C72
0x180184ba4  call    cs:__imp_DeleteFileW
0x180184bab  nop     dword ptr [rax+rax+00h]
0x180184bb0  test    eax, eax
0x180184bb2  jnz     loc_180184C70
0x180184bb8  call    cs:__imp_GetLastError
0x180184bbf  nop     dword ptr [rax+rax+00h]
0x180184bc4  add     eax, 0FFFFFFFEh
0x180184bc7  cmp     eax, 1
0x180184bca  jbe     loc_180184C70
0x180184bd0  xor     r9d, r9d; lpSecurityAttributes
0x180184bd3  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180184bdc  mov     [rsp+48h+dwFlagsAndAttributes], 2200080h; dwFlagsAndAttributes
0x180184be4  mov     edx, 10000h; dwDesiredAccess
0x180184be9  mov     rcx, rbx; lpFileName
0x180184bec  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x180184bf4  lea     r8d, [r9+7]; dwShareMode
0x180184bf8  call    cs:__imp_CreateFileW
0x180184bff  nop     dword ptr [rax+rax+00h]
0x180184c04  mov     [rsp+48h+arg_8], rax
0x180184c09  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180184c0d  jnz     short loc_180184C16
0x180184c0f  mov     edx, 8Bh
0x180184c14  jmp     short loc_180184C45
0x180184c16  mov     r9d, 4; dwBufferSize
0x180184c1c  mov     [rsp+48h+FileInformation], 1
0x180184c24  lea     r8, [rsp+48h+FileInformation]; lpFileInformation
0x180184c29  mov     rcx, rax; hFile
0x180184c2c  lea     edx, [r9+11h]; FileInformationClass
0x180184c30  call    cs:__imp_SetFileInformationByHandle
0x180184c37  nop     dword ptr [rax+rax+00h]
0x180184c3c  test    eax, eax
0x180184c3e  jnz     short loc_180184C66
0x180184c40  mov     edx, 90h; void *
0x180184c45  mov     rcx, [rsp+48h]; this
0x180184c4a  lea     r8, aOnecoreAdminAp_60; "onecore\\admin\\appmodel\\common\\appxd"...
0x180184c51  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180184c56  lea     rcx, [rsp+48h+arg_8]
0x180184c5b  mov     ebx, eax
0x180184c5d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180184c62  mov     eax, ebx
0x180184c64  jmp     short loc_180184C72
0x180184c66  lea     rcx, [rsp+48h+arg_8]
0x180184c6b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180184c70  xor     eax, eax
0x180184c72  add     rsp, 40h
0x180184c76  pop     rbx
0x180184c77  retn
```
