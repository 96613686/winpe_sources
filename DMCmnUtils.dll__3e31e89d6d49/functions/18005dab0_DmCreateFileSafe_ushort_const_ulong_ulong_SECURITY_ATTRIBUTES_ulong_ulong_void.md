# DmCreateFileSafe(ushort const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)

- ea: `0x18005dab0`
- end: `0x18005dc67`
- name: `?DmCreateFileSafe@@YAPEAXPEBGKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z`
- size: `439`
- prototype: `__int64 __fastcall(const unsigned __int16 *, DWORD dwDesiredAccess, DWORD dwShareMode, LPSECURITY_ATTRIBUTES lpSecurityAttributes, DWORD dwCreationDisposition, DWORD dwFlagsAndAttributes, void *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180007270`
- `0x180007840`
- `0x18005d7f8`
- `0x18005dab0`
- `0x18005dcf8`
- `0x18005ded4`
- `0x18005e13c`
- `0x18005e19c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18005db36`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x18005db36`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005db5f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18005db5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005dc0f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005dc0f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005dc1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005dc1e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005dbe9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005dbe9`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall DmCreateFileSafe(
        const unsigned __int16 *a1,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        LPSECURITY_ATTRIBUTES lpSecurityAttributes,
        DWORD dwCreationDisposition,
        DWORD dwFlagsAndAttributes,
        void *a7)
{
  __int64 v11; // rbx
  size_t v12; // rax
  unsigned __int64 v13; // rcx
  void *v14; // rax
  HANDLE FileW; // rax
  void *v16; // rdi
  __int64 v18; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hTemplateFile; // [rsp+58h] [rbp-A8h]
  wchar_t Drive[264]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Dir[264]; // [rsp+270h] [rbp+170h] BYREF

  hTemplateFile = a7;
  v18 = 0;
  v11 = -1;
  if ( !_wsplitpath_s(a1, Drive, 0x104u, Dir, 0x104u, 0, 0, 0, 0) && !(unsigned int)_o_wcscat_s(Drive, 260, Dir) )
  {
    v12 = wcsnlen_s(Drive, 0x104u);
    if ( v12 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v13 = 2 * v12 - 2;
      if ( v13 >= 0x208 )
        _report_rangecheckfailure();
      *(wchar_t *)((char *)Drive + v13) = 0;
      v14 = DmVerifyFolderPath(Drive);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &v18,
        v14);
      if ( v18 != -1 )
      {
        FileW = CreateFileW(
                  a1,
                  dwDesiredAccess,
                  dwShareMode,
                  lpSecurityAttributes,
                  dwCreationDisposition,
                  dwFlagsAndAttributes,
                  hTemplateFile);
        v16 = FileW;
        if ( FileW != (HANDLE)-1LL )
        {
          if ( (int)DmVerifyFilePath(a1, FileW) >= 0 )
          {
            v11 = (__int64)v16;
          }
          else
          {
            SetLastError(5u);
            CloseHandle(v16);
          }
        }
      }
    }
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
  return v11;
}

```

## disassembly

```asm
0x18005dab0  push    rbp
0x18005dab2  push    rbx
0x18005dab3  push    rsi
0x18005dab4  push    rdi
0x18005dab5  push    r12
0x18005dab7  push    r13
0x18005dab9  push    r14
0x18005dabb  push    r15
0x18005dabd  lea     rbp, [rsp-398h]
0x18005dac5  sub     rsp, 498h
0x18005dacc  mov     rax, cs:__security_cookie
0x18005dad3  xor     rax, rsp
0x18005dad6  mov     [rbp+3D0h+var_50], rax
0x18005dadd  mov     r15, r9
0x18005dae0  mov     r14d, r8d
0x18005dae3  mov     edi, edx
0x18005dae5  mov     rsi, rcx
0x18005dae8  mov     r12d, [rbp+3D0h+dwCreationDisposition]
0x18005daef  mov     r13d, [rbp+3D0h+dwFlagsAndAttributes]
0x18005daf6  mov     rax, [rbp+3D0h+arg_30]
0x18005dafd  mov     [rsp+4D0h+hTemplateFile], rax
0x18005db02  xor     eax, eax
0x18005db04  mov     [rsp+4D0h+var_480], rax
0x18005db09  mov     [rsp+4D0h+ExtCount], rax; ExtCount
0x18005db0e  mov     [rsp+4D0h+Ext], rax; Ext
0x18005db13  mov     [rsp+4D0h+FilenameCount], rax; FilenameCount
0x18005db18  mov     [rsp+4D0h+Filename], rax; Filename
0x18005db1d  mov     eax, 104h
0x18005db22  mov     [rsp+4D0h+DirCount], rax; DirCount
0x18005db27  lea     r9, [rbp+3D0h+Dir]; Dir
0x18005db2e  mov     r8d, eax; DriveCount
0x18005db31  lea     rdx, [rsp+4D0h+Drive]; Drive
0x18005db36  call    cs:__imp__wsplitpath_s
0x18005db3d  nop     dword ptr [rax+rax+00h]
0x18005db42  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18005db46  test    eax, eax
0x18005db48  jnz     loc_18005DC2B
0x18005db4e  lea     r8, [rbp+3D0h+Dir]
0x18005db55  mov     edx, 104h
0x18005db5a  lea     rcx, [rsp+4D0h+Drive]
0x18005db5f  call    cs:__imp__o_wcscat_s
0x18005db66  nop     dword ptr [rax+rax+00h]
0x18005db6b  test    eax, eax
0x18005db6d  jnz     loc_18005DC2B
0x18005db73  mov     edx, 104h; MaxCount
0x18005db78  lea     rcx, [rsp+4D0h+Drive]; Source
0x18005db7d  call    wcsnlen_s
0x18005db82  lea     rcx, [rax-1]
0x18005db86  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18005db8a  ja      loc_18005DC2B
0x18005db90  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18005db98  cmp     rcx, 208h
0x18005db9f  jnb     loc_18005DC61
0x18005dba5  xor     eax, eax
0x18005dba7  mov     [rsp+rcx+4D0h+Drive], ax
0x18005dbac  lea     rcx, [rsp+4D0h+Drive]; unsigned __int16 *
0x18005dbb1  call    ?DmVerifyFolderPath@@YAPEAXPEBG@Z; DmVerifyFolderPath(ushort const *)
0x18005dbb6  mov     rdx, rax
0x18005dbb9  lea     rcx, [rsp+4D0h+var_480]
0x18005dbbe  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18005dbc3  cmp     [rsp+4D0h+var_480], rbx
0x18005dbc8  jz      short loc_18005DC2B
0x18005dbca  mov     rax, [rsp+4D0h+hTemplateFile]
0x18005dbcf  mov     [rsp+4D0h+FilenameCount], rax; hTemplateFile
0x18005dbd4  mov     dword ptr [rsp+4D0h+Filename], r13d; dwFlagsAndAttributes
0x18005dbd9  mov     dword ptr [rsp+4D0h+DirCount], r12d; dwCreationDisposition
0x18005dbde  mov     r9, r15; lpSecurityAttributes
0x18005dbe1  mov     r8d, r14d; dwShareMode
0x18005dbe4  mov     edx, edi; dwDesiredAccess
0x18005dbe6  mov     rcx, rsi; lpFileName
0x18005dbe9  call    cs:__imp_CreateFileW
0x18005dbf0  nop     dword ptr [rax+rax+00h]
0x18005dbf5  mov     rdi, rax
0x18005dbf8  cmp     rax, rbx
0x18005dbfb  jz      short loc_18005DC2B
0x18005dbfd  mov     rdx, rax; hFile
0x18005dc00  mov     rcx, rsi; unsigned __int16 *
0x18005dc03  call    ?DmVerifyFilePath@@YAJPEBGPEAX@Z; DmVerifyFilePath(ushort const *,void *)
0x18005dc08  test    eax, eax
0x18005dc0a  jns     short loc_18005DC5C
0x18005dc0c  lea     ecx, [rbx+6]; dwErrCode
0x18005dc0f  call    cs:__imp_SetLastError
0x18005dc16  nop     dword ptr [rax+rax+00h]
0x18005dc1b  mov     rcx, rdi; hObject
0x18005dc1e  call    cs:__imp_CloseHandle
0x18005dc25  nop     dword ptr [rax+rax+00h]
0x18005dc2a  nop
0x18005dc2b  lea     rcx, [rsp+4D0h+var_480]
0x18005dc30  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005dc35  mov     rax, rbx
0x18005dc38  mov     rcx, [rbp+3D0h+var_50]
0x18005dc3f  xor     rcx, rsp; StackCookie
0x18005dc42  call    __security_check_cookie
0x18005dc47  add     rsp, 498h
0x18005dc4e  pop     r15
0x18005dc50  pop     r14
0x18005dc52  pop     r13
0x18005dc54  pop     r12
0x18005dc56  pop     rdi
0x18005dc57  pop     rsi
0x18005dc58  pop     rbx
0x18005dc59  pop     rbp
0x18005dc5a  retn
0x18005dc5c  mov     rbx, rdi
0x18005dc5f  jmp     short loc_18005DC2B
0x18005dc61  call    __report_rangecheckfailure
```
