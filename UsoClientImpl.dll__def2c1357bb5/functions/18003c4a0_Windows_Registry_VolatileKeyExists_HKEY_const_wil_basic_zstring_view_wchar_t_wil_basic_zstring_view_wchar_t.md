# Windows::Registry::VolatileKeyExists(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x18003c4a0`
- end: `0x18003c6a9`
- name: `?VolatileKeyExists@Registry@Windows@@QEAA?AV?$optional@_N@std@@QEAUHKEY__@@V?$basic_zstring_view@_W@wil@@1@Z`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800236f0`

## callees

- `0x180009380`
- `0x1800181d4`
- `0x18001932c`
- `0x18003c020`
- `0x18003c4a0`
- `0x18003dcf4`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c554`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c554`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c567`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003c567`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c55f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c667`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c677`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c55f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c667`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c677`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c523`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c523`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c5b1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c5b1`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18003c62f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18003c62f`

## string_xrefs

- `0x18003c5a6`: `ToBeDeleted`
- `0x18003c5f6`: `{}\ToBeDeleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Registry::VolatileKeyExists(__int64 a1, __int64 a2, __int64 a3, __int128 *a4, __int128 *a5)
{
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  unsigned int v8; // r8d
  HKEY v9; // rsi
  DWORD LastError; // ebx
  unsigned int v11; // eax
  unsigned int v12; // r8d
  __int64 v13; // rax
  const WCHAR *v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // r8d
  unsigned int phkResult; // [rsp+20h] [rbp-81h]
  unsigned int phkResulta; // [rsp+20h] [rbp-81h]
  __int128 v20; // [rsp+50h] [rbp-51h] BYREF
  __int128 v21; // [rsp+60h] [rbp-41h] BYREF
  LPCWSTR Src[4]; // [rsp+70h] [rbp-31h] BYREF
  _BYTE v23[24]; // [rsp+90h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+7h] BYREF
  HKEY v25; // [rsp+B0h] [rbp+Fh] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+B8h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v21 = *a5;
  v20 = *a4;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, &v20, &v21);
  hKey = 0;
  v25 = 0;
  v6 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v6 = lpSubKey[0];
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20006u, &v25);
  if ( v7 - 2 <= 1 )
  {
    *(_BYTE *)(a2 + 1) = 0;
  }
  else
  {
    if ( v7 )
      wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x125, v8, (const char *)v7, phkResult);
    v9 = hKey;
    if ( hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v9);
      SetLastError(LastError);
    }
    hKey = 0;
    v11 = RegCreateKeyExW(v25, L"ToBeDeleted", 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( v11 == 1021 )
    {
      *(_WORD *)a2 = 257;
    }
    else
    {
      if ( v11 )
        wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x138, v12, (const char *)v11, phkResulta);
      v13 = std::make_wformat_args<std::wstring>(v23, lpSubKey);
      *(_QWORD *)&v20 = 1;
      *((_QWORD *)&v20 + 1) = v13;
      *(_QWORD *)&v21 = L"{}\\ToBeDeleted";
      *((_QWORD *)&v21 + 1) = 14;
      std::vformat<0>(Src);
      v14 = (const WCHAR *)Src;
      if ( Src[3] > (LPCWSTR)7 )
        v14 = Src[0];
      v15 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, v14);
      if ( v15 )
        wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x13B, v16, (const char *)v15, phkResulta);
      std::wstring::~wstring(Src);
      *(_WORD *)a2 = 256;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v25 )
    RegCloseKey(v25);
  std::wstring::~wstring(lpSubKey);
  return a2;
}

```

## disassembly

```asm
0x18003c4a0  mov     [rsp-8+arg_0], rbx
0x18003c4a5  push    rbp
0x18003c4a6  push    rsi
0x18003c4a7  push    rdi
0x18003c4a8  lea     rbp, [rsp-3Fh]
0x18003c4ad  sub     rsp, 0E0h
0x18003c4b4  mov     rax, cs:__security_cookie
0x18003c4bb  xor     rax, rsp
0x18003c4be  mov     [rbp+4Fh+var_18], rax
0x18003c4c2  mov     rdi, rdx
0x18003c4c5  mov     rax, [rbp+4Fh+arg_20]
0x18003c4c9  movaps  xmm0, xmmword ptr [rax]
0x18003c4cc  movdqa  [rbp+4Fh+var_90], xmm0
0x18003c4d1  movaps  xmm1, xmmword ptr [r9]
0x18003c4d5  movdqa  [rbp+4Fh+var_A0], xmm1
0x18003c4da  lea     r9, [rbp+4Fh+var_90]
0x18003c4de  lea     r8, [rbp+4Fh+var_A0]
0x18003c4e2  lea     rdx, [rbp+4Fh+lpSubKey]
0x18003c4e6  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18003c4eb  nop
0x18003c4ec  mov     [rbp+4Fh+hKey], 0
0x18003c4f4  mov     [rbp+4Fh+var_40], 0
0x18003c4fc  lea     rdx, [rbp+4Fh+lpSubKey]
0x18003c500  cmp     [rbp+4Fh+var_20], 7
0x18003c505  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x18003c50a  lea     rax, [rbp+4Fh+var_40]
0x18003c50e  mov     [rsp+0F0h+phkResult], rax; unsigned int
0x18003c513  mov     r9d, 20006h; samDesired
0x18003c519  xor     r8d, r8d; ulOptions
0x18003c51c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c523  call    cs:__imp_RegOpenKeyExW
0x18003c529  mov     r9d, eax; char *
0x18003c52c  add     eax, 0FFFFFFFEh
0x18003c52f  cmp     eax, 1
0x18003c532  jbe     loc_18003C65A
0x18003c538  mov     rcx, [rbp+57h]; this
0x18003c53c  test    r9d, r9d
0x18003c53f  jz      short loc_18003C54B
0x18003c541  mov     edx, 125h; void *
0x18003c546  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18003c54b  mov     rsi, [rbp+4Fh+hKey]
0x18003c54f  test    rsi, rsi
0x18003c552  jz      short loc_18003C56D
0x18003c554  call    cs:__imp_GetLastError
0x18003c55a  mov     ebx, eax
0x18003c55c  mov     rcx, rsi; hKey
0x18003c55f  call    cs:__imp_RegCloseKey
0x18003c565  mov     ecx, ebx; dwErrCode
0x18003c567  call    cs:__imp_SetLastError
0x18003c56d  mov     [rbp+4Fh+hKey], 0
0x18003c575  mov     [rsp+0F0h+lpdwDisposition], 0; lpdwDisposition
0x18003c57e  lea     rax, [rbp+4Fh+hKey]
0x18003c582  mov     [rsp+0F0h+var_B8], rax; phkResult
0x18003c587  mov     [rsp+0F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003c590  mov     [rsp+0F0h+samDesired], 20006h; samDesired
0x18003c598  mov     dword ptr [rsp+0F0h+phkResult], 0; unsigned int
0x18003c5a0  xor     r9d, r9d; lpClass
0x18003c5a3  xor     r8d, r8d; Reserved
0x18003c5a6  lea     rdx, aTobedeleted; "ToBeDeleted"
0x18003c5ad  mov     rcx, [rbp+4Fh+var_40]; hKey
0x18003c5b1  call    cs:__imp_RegCreateKeyExW
0x18003c5b7  cmp     eax, 3FDh
0x18003c5bc  jnz     short loc_18003C5C8
0x18003c5be  mov     word ptr [rdi], 101h
0x18003c5c3  jmp     loc_18003C65E
0x18003c5c8  mov     rcx, [rbp+57h]; this
0x18003c5cc  test    eax, eax
0x18003c5ce  jz      short loc_18003C5DD
0x18003c5d0  mov     r9d, eax; char *
0x18003c5d3  mov     edx, 138h; void *
0x18003c5d8  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18003c5dd  lea     rdx, [rbp+4Fh+lpSubKey]
0x18003c5e1  lea     rcx, [rbp+4Fh+var_60]
0x18003c5e5  call    ??$make_wformat_args@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@YA?A_PAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z
0x18003c5ea  mov     qword ptr [rbp+4Fh+var_A0], 1
0x18003c5f2  mov     qword ptr [rbp+4Fh+var_A0+8], rax
0x18003c5f6  lea     rax, aTobedeleted_0; "{}\\ToBeDeleted"
0x18003c5fd  mov     qword ptr [rbp+4Fh+var_90], rax
0x18003c601  mov     qword ptr [rbp+4Fh+var_90+8], 0Eh
0x18003c609  lea     r8, [rbp+4Fh+var_A0]
0x18003c60d  lea     rdx, [rbp+4Fh+var_90]
0x18003c611  lea     rcx, [rbp+4Fh+Src]; Src
0x18003c615  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x18003c61a  lea     rdx, [rbp+4Fh+Src]
0x18003c61e  cmp     [rbp+4Fh+var_68], 7
0x18003c623  cmova   rdx, [rbp+4Fh+Src]; lpSubKey
0x18003c628  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c62f  call    cs:__imp_RegDeleteKeyW
0x18003c635  mov     rcx, [rbp+57h]; this
0x18003c639  test    eax, eax
0x18003c63b  jz      short loc_18003C64A
0x18003c63d  mov     r9d, eax; char *
0x18003c640  mov     edx, 13Bh; void *
0x18003c645  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18003c64a  lea     rcx, [rbp+4Fh+Src]; void *
0x18003c64e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c653  mov     word ptr [rdi], 100h
0x18003c658  jmp     short loc_18003C65E
0x18003c65a  mov     byte ptr [rdi+1], 0
0x18003c65e  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18003c662  test    rcx, rcx
0x18003c665  jz      short loc_18003C66E
0x18003c667  call    cs:__imp_RegCloseKey
0x18003c66d  nop
0x18003c66e  mov     rcx, [rbp+4Fh+var_40]; hKey
0x18003c672  test    rcx, rcx
0x18003c675  jz      short loc_18003C67E
0x18003c677  call    cs:__imp_RegCloseKey
0x18003c67d  nop
0x18003c67e  lea     rcx, [rbp+4Fh+lpSubKey]; void *
0x18003c682  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c687  mov     rax, rdi
0x18003c68a  mov     rcx, [rbp+4Fh+var_18]
0x18003c68e  xor     rcx, rsp; StackCookie
0x18003c691  call    __security_check_cookie
0x18003c696  mov     rbx, [rsp+0F0h+arg_0]
0x18003c69e  add     rsp, 0E0h
0x18003c6a5  pop     rdi
0x18003c6a6  pop     rsi
0x18003c6a7  pop     rbp
0x18003c6a8  retn
```
