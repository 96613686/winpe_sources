# NDXGI::ResolveFinalPath

- ea: `0x18011c30c`
- end: `0x18011c483`
- name: `NDXGI::ResolveFinalPath`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, registry_config`

## callers

- `0x18011b6d0`

## callees

- `0x180085cc0`
- `0x1800cbc58`
- `0x1800ea6b8`
- `0x18011952c`
- `0x180119774`
- `0x18011c30c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c3a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c372`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011c3a7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18011c39b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18011c3e3`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18011c39b`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x18011c3e3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011c35e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18011c35e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NDXGI::ResolveFinalPath(const WCHAR *a1, __int64 a2)
{
  HANDLE FileW; // rax
  void *v5; // rbx
  signed int LastError; // eax
  unsigned int v7; // ebx
  DWORD FinalPathNameByHandleW; // eax
  DWORD v9; // esi
  signed int v10; // eax
  WCHAR *v11; // rdx
  __int64 v12; // rax
  int v13; // r9d
  __int64 v14; // rax
  const wchar_t *v15; // [rsp+40h] [rbp-18h] BYREF
  __int64 v16; // [rsp+48h] [rbp-10h]
  HANDLE v17; // [rsp+60h] [rbp+8h] BYREF

  if ( !*((_QWORD *)a1 + 2) )
    return 2147942487LL;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x2000080u, 0);
  v5 = FileW;
  v17 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, 0, 0, 0);
    v9 = FinalPathNameByHandleW;
    if ( FinalPathNameByHandleW
      && ((std::wstring::resize(a2, FinalPathNameByHandleW - 1), *(_QWORD *)(a2 + 24) <= 7u)
        ? (v11 = (WCHAR *)a2)
        : (v11 = *(WCHAR **)a2),
          GetFinalPathNameByHandleW(v5, v11, v9, 0)) )
    {
      v15 = L"\\\\?\\UNC";
      v16 = 7;
      v12 = std::wstring::find<std::basic_string_view<unsigned short>,0>(a2, &v15);
      if ( v12 == -1 )
      {
        v15 = L"\\\\?\\";
        v16 = 4;
        v14 = std::wstring::find<std::basic_string_view<unsigned short>,0>(a2, &v15);
        if ( v14 != -1 )
          std::wstring::erase(a2, v14, 4);
      }
      else
      {
        std::wstring::_Replace<unsigned short>(a2, v12, 7, v13, 1);
      }
      v7 = 0;
    }
    else
    {
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      v7 = v10;
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
  return v7;
}

```

## disassembly

```asm
0x18011c30c  mov     [rsp+arg_8], rbx
0x18011c311  mov     [rsp+arg_10], rsi
0x18011c316  push    rdi
0x18011c317  sub     rsp, 50h
0x18011c31b  mov     rdi, rdx
0x18011c31e  cmp     qword ptr [rcx+10h], 0
0x18011c323  jnz     short loc_18011C32F
0x18011c325  mov     eax, 80070057h
0x18011c32a  jmp     loc_18011C473
0x18011c32f  cmp     qword ptr [rcx+18h], 7
0x18011c334  jbe     short loc_18011C339
0x18011c336  mov     rcx, [rcx]; lpFileName
0x18011c339  mov     [rsp+58h+hTemplateFile], 0; hTemplateFile
0x18011c342  mov     [rsp+58h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18011c34a  mov     [rsp+58h+dwCreationDisposition], 3; dwCreationDisposition
0x18011c352  xor     r9d, r9d; lpSecurityAttributes
0x18011c355  mov     edx, 80000000h; dwDesiredAccess
0x18011c35a  lea     r8d, [r9+1]; dwShareMode
0x18011c35e  call    cs:__imp_CreateFileW
0x18011c364  mov     rbx, rax
0x18011c367  mov     [rsp+58h+arg_0], rax
0x18011c36c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18011c370  jnz     short loc_18011C390
0x18011c372  call    cs:__imp_GetLastError
0x18011c378  mov     ebx, eax
0x18011c37a  test    eax, eax
0x18011c37c  jle     loc_18011C467
0x18011c382  movzx   ebx, ax
0x18011c385  or      ebx, 80070000h
0x18011c38b  jmp     loc_18011C467
0x18011c390  xor     r9d, r9d; dwFlags
0x18011c393  xor     r8d, r8d; cchFilePath
0x18011c396  xor     edx, edx; lpszFilePath
0x18011c398  mov     rcx, rbx; hFile
0x18011c39b  call    cs:__imp_GetFinalPathNameByHandleW
0x18011c3a1  mov     esi, eax
0x18011c3a3  test    eax, eax
0x18011c3a5  jnz     short loc_18011C3C0
0x18011c3a7  call    cs:__imp_GetLastError
0x18011c3ad  test    eax, eax
0x18011c3af  jle     short loc_18011C3B9
0x18011c3b1  movzx   eax, ax
0x18011c3b4  or      eax, 80070000h
0x18011c3b9  mov     ebx, eax
0x18011c3bb  jmp     loc_18011C467
0x18011c3c0  lea     edx, [rax-1]
0x18011c3c3  mov     rcx, rdi
0x18011c3c6  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18011c3cb  cmp     qword ptr [rdi+18h], 7
0x18011c3d0  jbe     short loc_18011C3D7
0x18011c3d2  mov     rdx, [rdi]
0x18011c3d5  jmp     short loc_18011C3DA
0x18011c3d7  mov     rdx, rdi; lpszFilePath
0x18011c3da  xor     r9d, r9d; dwFlags
0x18011c3dd  mov     r8d, esi; cchFilePath
0x18011c3e0  mov     rcx, rbx; hFile
0x18011c3e3  call    cs:__imp_GetFinalPathNameByHandleW
0x18011c3e9  test    eax, eax
0x18011c3eb  jz      short loc_18011C3A7
0x18011c3ed  lea     rax, aUnc; "\\\\?\\UNC"
0x18011c3f4  mov     [rsp+58h+var_18], rax
0x18011c3f9  mov     [rsp+58h+var_10], 7
0x18011c402  lea     rdx, [rsp+58h+var_18]
0x18011c407  mov     rcx, rdi
0x18011c40a  call    ??$find@V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV?$basic_string_view@GU?$char_traits@G@std@@@1@_K@Z; std::wstring::find<std::basic_string_view<ushort>,0>(std::basic_string_view<ushort> const &,unsigned __int64)
0x18011c40f  mov     rcx, rdi
0x18011c412  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18011c416  jz      short loc_18011C431
0x18011c418  mov     qword ptr [rsp+58h+dwCreationDisposition], 1
0x18011c421  mov     r8d, 7
0x18011c427  mov     rdx, rax
0x18011c42a  call    ??$_Replace@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_K_KQEBG0@Z; std::wstring::_Replace<ushort>(unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18011c42f  jmp     short loc_18011C465
0x18011c431  lea     rax, asc_1802A70C8; "\\\\?\\"
0x18011c438  mov     [rsp+58h+var_18], rax
0x18011c43d  mov     ebx, 4
0x18011c442  mov     [rsp+58h+var_10], rbx
0x18011c447  lea     rdx, [rsp+58h+var_18]
0x18011c44c  call    ??$find@V?$basic_string_view@GU?$char_traits@G@std@@@std@@$0A@@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KAEBV?$basic_string_view@GU?$char_traits@G@std@@@1@_K@Z; std::wstring::find<std::basic_string_view<ushort>,0>(std::basic_string_view<ushort> const &,unsigned __int64)
0x18011c451  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18011c455  jz      short loc_18011C465
0x18011c457  mov     r8d, ebx
0x18011c45a  mov     rdx, rax
0x18011c45d  mov     rcx, rdi
0x18011c460  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x18011c465  xor     ebx, ebx
0x18011c467  lea     rcx, [rsp+58h+arg_0]
0x18011c46c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18011c471  mov     eax, ebx
0x18011c473  mov     rbx, [rsp+58h+arg_8]
0x18011c478  mov     rsi, [rsp+58h+arg_10]
0x18011c47d  add     rsp, 50h
0x18011c481  pop     rdi
0x18011c482  retn
```
