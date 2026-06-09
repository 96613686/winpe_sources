# OneDriveUtils::IsFileIdentical(ushort const *,ushort const *)

- ea: `0x1800ad734`
- end: `0x1800ad95b`
- name: `?IsFileIdentical@OneDriveUtils@@YA_NPEBG0@Z`
- size: `551`
- prototype: `char __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x1800a96f0`
- `0x1800aa010`
- `0x1800aca2c`
- `0x1800bca00`

## callees

- `0x18000c6e0`
- `0x18001c180`
- `0x18001d0a8`
- `0x1800a442c`
- `0x1800a8718`
- `0x1800ad734`
- `0x1800b0f54`
- `0x18011d1c0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1800ad7fb`
- `KERNEL32!CreateFileW` at `0x1800ad845`
- `KERNEL32!CreateFileW` at `0x1800ad7fb`
- `KERNEL32!CreateFileW` at `0x1800ad845`
- `KERNEL32!ReadFile` at `0x1800ad8a5`
- `KERNEL32!ReadFile` at `0x1800ad8d5`
- `KERNEL32!ReadFile` at `0x1800ad8a5`
- `KERNEL32!ReadFile` at `0x1800ad8d5`

## pseudocode

```c
char __fastcall OneDriveUtils::IsFileIdentical(
        const WCHAR *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v5; // r8
  const struct std::filesystem::path *v6; // rdx
  unsigned __int64 v7; // rdi
  const struct std::filesystem::path *v8; // rdx
  unsigned __int64 v9; // rbx
  unsigned __int16 *FileW; // rbx
  const char *v12; // r9
  WCHAR *v13; // rdi
  const char *v14; // r9
  DWORD v15; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-BCh] BYREF
  const WCHAR *v17; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v18; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v20[40]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v21[4096]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE Buffer[4096]; // [rsp+10A0h] [rbp+FA0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+20C8h] [rbp+1FC8h]

  v17 = this;
  v18 = a2;
  std::filesystem::path::path(v20, &v18, a3);
  std::filesystem::path::path(v19, &v17, v5);
  v7 = std::filesystem::file_size((std::filesystem *)v19, v6);
  v9 = std::filesystem::file_size((std::filesystem *)v20, v8);
  std::wstring::_Tidy_deallocate(v19);
  std::wstring::_Tidy_deallocate(v20);
  if ( v7 == v9 )
  {
    FileW = (unsigned __int16 *)CreateFileW(this, 0x80000000, 0, 0, 3u, 0x80u, 0);
    v18 = FileW;
    if ( (unsigned __int64)FileW - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xE3,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\OneDriveUtils.h",
        v12);
    v13 = (WCHAR *)CreateFileW(a2, 0x80000000, 0, 0, 3u, 0x80u, 0);
    v17 = v13;
    if ( (unsigned __int64)v13 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xE5,
        (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\cloudbackuprestore\\OneDriveUtils.h",
        v14);
    v15 = 0;
    NumberOfBytesRead = 0;
    do
    {
      if ( !ReadFile(FileW, v21, 0x1000u, &v15, 0)
        || !v15
        || !ReadFile(v13, Buffer, 0x1000u, &NumberOfBytesRead, 0)
        || !NumberOfBytesRead )
      {
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
        return 1;
      }
    }
    while ( v15 == NumberOfBytesRead );
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v18);
  }
  return 0;
}

```

## disassembly

```asm
0x1800ad734  mov     [rsp-8+arg_10], rbx
0x1800ad739  mov     [rsp-8+arg_18], rsi
0x1800ad73e  push    rbp
0x1800ad73f  push    rdi
0x1800ad740  push    r14
0x1800ad742  lea     rbp, [rsp-1FB0h]
0x1800ad74a  mov     eax, 20B0h
0x1800ad74f  call    _alloca_probe
0x1800ad754  sub     rsp, rax
0x1800ad757  mov     rax, cs:__security_cookie
0x1800ad75e  xor     rax, rsp
0x1800ad761  mov     [rbp+1FC0h+var_20], rax
0x1800ad768  mov     r14, rdx
0x1800ad76b  mov     rsi, rcx
0x1800ad76e  mov     [rsp+20C0h+var_2078], rcx
0x1800ad773  mov     [rsp+20C0h+var_2070], rdx
0x1800ad778  lea     rdx, [rsp+20C0h+var_2070]
0x1800ad77d  lea     rcx, [rsp+20C0h+var_2048]
0x1800ad782  call    ??$?0PEBG$0A@@path@filesystem@std@@QEAA@AEBQEBGW4format@012@@Z; std::filesystem::path::path(ushort const * const &,std::filesystem::path::format)
0x1800ad787  nop
0x1800ad788  lea     rdx, [rsp+20C0h+var_2078]
0x1800ad78d  lea     rcx, [rsp+20C0h+var_2068]
0x1800ad792  call    ??$?0PEBG$0A@@path@filesystem@std@@QEAA@AEBQEBGW4format@012@@Z; std::filesystem::path::path(ushort const * const &,std::filesystem::path::format)
0x1800ad797  nop
0x1800ad798  lea     rcx, [rsp+20C0h+var_2068]; this
0x1800ad79d  call    ?file_size@filesystem@std@@YA_KAEBVpath@12@@Z; std::filesystem::file_size(std::filesystem::path const &)
0x1800ad7a2  mov     rdi, rax
0x1800ad7a5  lea     rcx, [rsp+20C0h+var_2048]; this
0x1800ad7aa  call    ?file_size@filesystem@std@@YA_KAEBVpath@12@@Z; std::filesystem::file_size(std::filesystem::path const &)
0x1800ad7af  mov     rbx, rax
0x1800ad7b2  lea     rcx, [rsp+20C0h+var_2068]
0x1800ad7b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ad7bc  nop
0x1800ad7bd  lea     rcx, [rsp+20C0h+var_2048]
0x1800ad7c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ad7c7  cmp     rdi, rbx
0x1800ad7ca  jz      short loc_1800AD7D3
0x1800ad7cc  xor     al, al
0x1800ad7ce  jmp     loc_1800AD8F6
0x1800ad7d3  mov     [rsp+20C0h+hTemplateFile], 0; hTemplateFile
0x1800ad7dc  mov     edi, 80h
0x1800ad7e1  mov     [rsp+20C0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x1800ad7e5  mov     [rsp+20C0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800ad7ed  xor     r9d, r9d; lpSecurityAttributes
0x1800ad7f0  xor     r8d, r8d; dwShareMode
0x1800ad7f3  mov     edx, 80000000h; dwDesiredAccess
0x1800ad7f8  mov     rcx, rsi; lpFileName
0x1800ad7fb  call    cs:__imp_CreateFileW
0x1800ad801  mov     rbx, rax
0x1800ad804  mov     [rsp+20C0h+var_2070], rax
0x1800ad809  dec     rax
0x1800ad80c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800ad810  setnbe  al
0x1800ad813  mov     rcx, [rbp+1FC8h]; this
0x1800ad81a  test    al, al
0x1800ad81c  jnz     loc_1800AD949
0x1800ad822  mov     [rsp+20C0h+hTemplateFile], 0; hTemplateFile
0x1800ad82b  mov     [rsp+20C0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x1800ad82f  mov     [rsp+20C0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800ad837  xor     r9d, r9d; lpSecurityAttributes
0x1800ad83a  xor     r8d, r8d; dwShareMode
0x1800ad83d  mov     edx, 80000000h; dwDesiredAccess
0x1800ad842  mov     rcx, r14; lpFileName
0x1800ad845  call    cs:__imp_CreateFileW
0x1800ad84b  mov     rdi, rax
0x1800ad84e  mov     [rsp+20C0h+var_2078], rax
0x1800ad853  dec     rax
0x1800ad856  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800ad85a  setnbe  al
0x1800ad85d  mov     rcx, [rbp+1FC8h]; this
0x1800ad864  test    al, al
0x1800ad866  jnz     loc_1800AD937
0x1800ad86c  mov     [rsp+20C0h+var_2080], 0
0x1800ad874  mov     [rsp+20C0h+NumberOfBytesRead], 0
0x1800ad87c  mov     esi, 1000h
0x1800ad881  jmp     short loc_1800AD8BD
0x1800ad883  cmp     [rsp+20C0h+var_2080], 0
0x1800ad888  jz      short loc_1800AD8DF
0x1800ad88a  mov     qword ptr [rsp+20C0h+dwCreationDisposition], 0; lpOverlapped
0x1800ad893  lea     r9, [rsp+20C0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800ad898  mov     r8d, esi; nNumberOfBytesToRead
0x1800ad89b  lea     rdx, [rbp+1FC0h+Buffer]; lpBuffer
0x1800ad8a2  mov     rcx, rdi; hFile
0x1800ad8a5  call    cs:__imp_ReadFile
0x1800ad8ab  test    eax, eax
0x1800ad8ad  jz      short loc_1800AD8DF
0x1800ad8af  mov     eax, [rsp+20C0h+NumberOfBytesRead]
0x1800ad8b3  test    eax, eax
0x1800ad8b5  jz      short loc_1800AD8DF
0x1800ad8b7  cmp     [rsp+20C0h+var_2080], eax
0x1800ad8bb  jnz     short loc_1800AD91D
0x1800ad8bd  mov     qword ptr [rsp+20C0h+dwCreationDisposition], 0; lpOverlapped
0x1800ad8c6  lea     r9, [rsp+20C0h+var_2080]; lpNumberOfBytesRead
0x1800ad8cb  mov     r8d, esi; nNumberOfBytesToRead
0x1800ad8ce  lea     rdx, [rbp+1FC0h+var_2020]; lpBuffer
0x1800ad8d2  mov     rcx, rbx; hFile
0x1800ad8d5  call    cs:__imp_ReadFile
0x1800ad8db  test    eax, eax
0x1800ad8dd  jnz     short loc_1800AD883
0x1800ad8df  lea     rcx, [rsp+20C0h+var_2078]
0x1800ad8e4  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ad8e9  nop
0x1800ad8ea  lea     rcx, [rsp+20C0h+var_2070]
0x1800ad8ef  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ad8f4  mov     al, 1
0x1800ad8f6  mov     rcx, [rbp+1FC0h+var_20]
0x1800ad8fd  xor     rcx, rsp; StackCookie
0x1800ad900  call    __security_check_cookie
0x1800ad905  lea     r11, [rsp+20C0h+var_10]
0x1800ad90d  mov     rbx, [r11+30h]
0x1800ad911  mov     rsi, [r11+38h]
0x1800ad915  mov     rsp, r11
0x1800ad918  pop     r14
0x1800ad91a  pop     rdi
0x1800ad91b  pop     rbp
0x1800ad91c  retn
0x1800ad91d  lea     rcx, [rsp+20C0h+var_2078]
0x1800ad922  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ad927  nop
0x1800ad928  lea     rcx, [rsp+20C0h+var_2070]
0x1800ad92d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800ad932  jmp     loc_1800AD7CC
0x1800ad937  lea     r8, aPcshellShellCl_36; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800ad93e  mov     edx, 0E5h; void *
0x1800ad943  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800ad949  lea     r8, aPcshellShellCl_36; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x1800ad950  mov     edx, 0E3h; void *
0x1800ad955  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
