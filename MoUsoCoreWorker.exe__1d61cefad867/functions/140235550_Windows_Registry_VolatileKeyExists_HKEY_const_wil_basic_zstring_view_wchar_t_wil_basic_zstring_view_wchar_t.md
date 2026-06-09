# Windows::Registry::VolatileKeyExists(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x140235550`
- end: `0x14023573c`
- name: `?VolatileKeyExists@Registry@Windows@@QEAA?AV?$optional@_N@std@@QEAUHKEY__@@V?$basic_zstring_view@_W@wil@@1@Z`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14012cfd0`

## callees

- `0x140045404`
- `0x1400a3eac`
- `0x1402350d0`
- `0x140235550`
- `0x1402367c4`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140235617`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140235617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140235604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140235604`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1402355d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1402355d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14023560f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1402356fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14023570a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14023560f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1402356fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14023570a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140235661`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140235661`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1402356c2`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x1402356c2`

## string_xrefs

- `0x14023568a`: `{}\ToBeDeleted`
- `0x140235656`: `ToBeDeleted`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Registry::VolatileKeyExists(__int64 a1, __int64 a2, __int64 a3, _OWORD *a4, __int128 *a5)
{
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // r8d
  HKEY v10; // rsi
  DWORD LastError; // ebx
  unsigned int v12; // eax
  unsigned int v13; // r8d
  __int64 v14; // rax
  unsigned int v15; // eax
  __int64 v16; // rdx
  unsigned int v17; // r8d
  unsigned int phkResult; // [rsp+20h] [rbp-61h]
  unsigned int phkResulta; // [rsp+20h] [rbp-61h]
  __int128 v21; // [rsp+50h] [rbp-31h] BYREF
  _OWORD Src[2]; // [rsp+60h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-1h] BYREF
  HKEY v24; // [rsp+88h] [rbp+7h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+90h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v21 = *a5;
  Src[0] = *a4;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, Src, &v21);
  hKey = 0;
  v24 = 0;
  v6 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v6 = lpSubKey[0];
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20006u, &v24);
  if ( v7 - 2 <= 1 )
  {
    *(_BYTE *)(a2 + 1) = 0;
  }
  else
  {
    if ( v7 )
      wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x125, v9, (const char *)v7, phkResult);
    v10 = hKey;
    if ( hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v10);
      SetLastError(LastError);
    }
    hKey = 0;
    v12 = RegCreateKeyExW(v24, L"ToBeDeleted", 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( v12 == 1021 )
    {
      *(_WORD *)a2 = 257;
    }
    else
    {
      if ( v12 )
        wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x138, v13, (const char *)v12, phkResulta);
      *(_QWORD *)&v21 = L"{}\\ToBeDeleted";
      *((_QWORD *)&v21 + 1) = 14;
      v14 = std::format<std::wstring const &>(Src);
      if ( *(_QWORD *)(v14 + 24) > 7u )
        v14 = *(_QWORD *)v14;
      v15 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, (LPCWSTR)v14);
      if ( v15 )
        wil::details::in1diag3::_Log_Win32(retaddr, (void *)0x13B, v17, (const char *)v15, phkResulta);
      std::wstring::~wstring(Src, v16);
      *(_WORD *)a2 = 256;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( v24 )
    RegCloseKey(v24);
  std::wstring::~wstring(lpSubKey, v8);
  return a2;
}

```

## disassembly

```asm
0x140235550  mov     [rsp-8+arg_0], rbx
0x140235555  push    rbp
0x140235556  push    rsi
0x140235557  push    rdi
0x140235558  lea     rbp, [rsp-3Fh]
0x14023555d  sub     rsp, 0C0h
0x140235564  mov     rax, cs:__security_cookie
0x14023556b  xor     rax, rsp
0x14023556e  mov     [rbp+4Fh+var_20], rax
0x140235572  mov     rdi, rdx
0x140235575  mov     rax, [rbp+4Fh+arg_20]
0x140235579  movaps  xmm0, xmmword ptr [rax]
0x14023557c  movdqa  [rbp+4Fh+var_80], xmm0
0x140235581  movaps  xmm1, xmmword ptr [r9]
0x140235585  movdqa  [rbp+4Fh+Src], xmm1
0x14023558a  lea     r9, [rbp+4Fh+var_80]
0x14023558e  lea     r8, [rbp+4Fh+Src]
0x140235592  lea     rdx, [rbp+4Fh+lpSubKey]
0x140235596  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x14023559b  nop
0x14023559c  mov     [rbp+4Fh+hKey], 0
0x1402355a4  mov     [rbp+4Fh+var_48], 0
0x1402355ac  lea     rdx, [rbp+4Fh+lpSubKey]
0x1402355b0  cmp     [rbp+4Fh+var_28], 7
0x1402355b5  cmova   rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x1402355ba  lea     rax, [rbp+4Fh+var_48]
0x1402355be  mov     [rsp+0D0h+phkResult], rax; unsigned int
0x1402355c3  mov     r9d, 20006h; samDesired
0x1402355c9  xor     r8d, r8d; ulOptions
0x1402355cc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1402355d3  call    cs:__imp_RegOpenKeyExW
0x1402355d9  mov     r9d, eax; char *
0x1402355dc  add     eax, 0FFFFFFFEh
0x1402355df  cmp     eax, 1
0x1402355e2  jbe     loc_1402356ED
0x1402355e8  mov     rcx, [rbp+57h]; this
0x1402355ec  test    r9d, r9d
0x1402355ef  jz      short loc_1402355FB
0x1402355f1  mov     edx, 125h; void *
0x1402355f6  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1402355fb  mov     rsi, [rbp+4Fh+hKey]
0x1402355ff  test    rsi, rsi
0x140235602  jz      short loc_14023561D
0x140235604  call    cs:__imp_GetLastError
0x14023560a  mov     ebx, eax
0x14023560c  mov     rcx, rsi; hKey
0x14023560f  call    cs:__imp_RegCloseKey
0x140235615  mov     ecx, ebx; dwErrCode
0x140235617  call    cs:__imp_SetLastError
0x14023561d  mov     [rbp+4Fh+hKey], 0
0x140235625  mov     [rsp+0D0h+lpdwDisposition], 0; lpdwDisposition
0x14023562e  lea     rax, [rbp+4Fh+hKey]
0x140235632  mov     [rsp+0D0h+var_98], rax; phkResult
0x140235637  mov     [rsp+0D0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140235640  mov     [rsp+0D0h+samDesired], 20006h; samDesired
0x140235648  mov     dword ptr [rsp+0D0h+phkResult], 0; unsigned int
0x140235650  xor     r9d, r9d; lpClass
0x140235653  xor     r8d, r8d; Reserved
0x140235656  lea     rdx, aTobedeleted; "ToBeDeleted"
0x14023565d  mov     rcx, [rbp+4Fh+var_48]; hKey
0x140235661  call    cs:__imp_RegCreateKeyExW
0x140235667  cmp     eax, 3FDh
0x14023566c  jnz     short loc_140235675
0x14023566e  mov     word ptr [rdi], 101h
0x140235673  jmp     short loc_1402356F1
0x140235675  mov     rcx, [rbp+57h]; this
0x140235679  test    eax, eax
0x14023567b  jz      short loc_14023568A
0x14023567d  mov     r9d, eax; char *
0x140235680  mov     edx, 138h; void *
0x140235685  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x14023568a  lea     rax, aTobedeleted_0; "{}\\ToBeDeleted"
0x140235691  mov     qword ptr [rbp+4Fh+var_80], rax
0x140235695  mov     qword ptr [rbp+4Fh+var_80+8], 0Eh
0x14023569d  lea     r8, [rbp+4Fh+lpSubKey]
0x1402356a1  lea     rdx, [rbp+4Fh+var_80]
0x1402356a5  lea     rcx, [rbp+4Fh+Src]; Src
0x1402356a9  call    ??$format@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@U?$basic_format_string@_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@AEBV10@@Z; std::format<std::wstring const &>(std::basic_format_string<wchar_t,std::wstring const &>,std::wstring const &)
0x1402356ae  cmp     qword ptr [rax+18h], 7
0x1402356b3  jbe     short loc_1402356B8
0x1402356b5  mov     rax, [rax]
0x1402356b8  mov     rdx, rax; lpSubKey
0x1402356bb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1402356c2  call    cs:__imp_RegDeleteKeyW
0x1402356c8  mov     rcx, [rbp+57h]; this
0x1402356cc  test    eax, eax
0x1402356ce  jz      short loc_1402356DD
0x1402356d0  mov     r9d, eax; char *
0x1402356d3  mov     edx, 13Bh; void *
0x1402356d8  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1402356dd  lea     rcx, [rbp+4Fh+Src]
0x1402356e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1402356e6  mov     word ptr [rdi], 100h
0x1402356eb  jmp     short loc_1402356F1
0x1402356ed  mov     byte ptr [rdi+1], 0
0x1402356f1  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1402356f5  test    rcx, rcx
0x1402356f8  jz      short loc_140235701
0x1402356fa  call    cs:__imp_RegCloseKey
0x140235700  nop
0x140235701  mov     rcx, [rbp+4Fh+var_48]; hKey
0x140235705  test    rcx, rcx
0x140235708  jz      short loc_140235711
0x14023570a  call    cs:__imp_RegCloseKey
0x140235710  nop
0x140235711  lea     rcx, [rbp+4Fh+lpSubKey]
0x140235715  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14023571a  mov     rax, rdi
0x14023571d  mov     rcx, [rbp+4Fh+var_20]
0x140235721  xor     rcx, rsp; StackCookie
0x140235724  call    __security_check_cookie
0x140235729  mov     rbx, [rsp+0D0h+arg_0]
0x140235731  add     rsp, 0C0h
0x140235738  pop     rdi
0x140235739  pop     rsi
0x14023573a  pop     rbp
0x14023573b  retn
```
