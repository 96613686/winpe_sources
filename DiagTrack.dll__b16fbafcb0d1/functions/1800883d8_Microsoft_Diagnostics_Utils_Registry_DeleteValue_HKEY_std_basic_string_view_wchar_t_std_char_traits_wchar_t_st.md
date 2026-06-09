# Microsoft::Diagnostics::Utils::Registry::DeleteValue(HKEY__ *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1800883d8`
- end: `0x180088559`
- name: `?DeleteValue@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1@Z`
- size: `385`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037118`
- `0x180087e20`
- `0x18008815c`
- `0x180088560`
- `0x1800886d8`
- `0x1801418d8`
- `0x18014dc8c`
- `0x18016211c`
- `0x1801b4dc4`
- `0x1801d6278`
- `0x1801e53e8`
- `0x1801e5c40`
- `0x180240be0`
- `0x1802549f8`
- `0x18027a99c`
- `0x1802d2e70`

## callees

- `0x180020db8`
- `0x18002be90`
- `0x18002df00`
- `0x1800883d8`
- `0x18008abf4`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180088443`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180088443`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180088489`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180088489`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800884cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008851f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008853e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800884cb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008851f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008853e`

## string_xrefs

- `0x1800884ae`: `onecore\base\telemetry\utc\include\RegistryUtils.h`
- `0x180088502`: `onecore\base\telemetry\utc\include\RegistryUtils.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::Utils::Registry::DeleteValue(__int64 a1, _OWORD *a2, _QWORD *a3)
{
  const WCHAR *v4; // rdx
  unsigned int v5; // eax
  const WCHAR *v6; // rdx
  unsigned int v7; // ebx
  unsigned int v8; // ebx
  unsigned int phkResult; // [rsp+20h] [rbp-78h]
  HKEY hKey; // [rsp+30h] [rbp-68h] BYREF
  LPCWSTR lpValueName[2]; // [rsp+40h] [rbp-58h] BYREF
  __int128 v13; // [rsp+50h] [rbp-48h]
  LPCWSTR lpSubKey[4]; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  *(_OWORD *)lpValueName = *a2;
  Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName((LPCWSTR)lpSubKey);
  hKey = 0;
  v4 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v4 = lpSubKey[0];
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 2u, &hKey);
  if ( v5 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x674,
           (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
           (const char *)v5,
           phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_9;
  }
  *(_OWORD *)lpValueName = 0;
  v13 = 0;
  std::wstring::_Construct<1,wchar_t *>(lpValueName, *a3, a3[1]);
  v6 = (const WCHAR *)lpValueName;
  if ( *((_QWORD *)&v13 + 1) > 7u )
    v6 = lpValueName[0];
  v7 = RegDeleteValueW(hKey, v6);
  std::wstring::_Tidy_deallocate(lpValueName);
  if ( v7 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x676,
           (unsigned int)"onecore\\base\\telemetry\\utc\\include\\RegistryUtils.h",
           (const char *)v7,
           phkResult);
    if ( hKey )
      RegCloseKey(hKey);
LABEL_9:
    std::wstring::_Tidy_deallocate(lpSubKey);
    return v8;
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::_Tidy_deallocate(lpSubKey);
  return 0;
}

```

## disassembly

```asm
0x1800883d8  push    rbx
0x1800883da  sub     rsp, 90h
0x1800883e1  mov     rax, cs:__security_cookie
0x1800883e8  xor     rax, rsp
0x1800883eb  mov     [rsp+98h+var_18], rax
0x1800883f3  mov     rbx, r8
0x1800883f6  movaps  xmm0, xmmword ptr [rdx]
0x1800883f9  movdqa  xmmword ptr [rsp+98h+lpValueName], xmm0
0x1800883ff  lea     rdx, [rsp+98h+lpValueName]
0x180088404  lea     rcx, [rsp+98h+lpSubKey]
0x180088409  call    ?TryExpandKeyName@Registry@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::Utils::Registry::TryExpandKeyName(std::wstring_view)
0x18008840e  nop
0x18008840f  mov     [rsp+98h+hKey], 0
0x180088418  lea     rdx, [rsp+98h+lpSubKey]
0x18008841d  cmp     [rsp+98h+var_20], 7
0x180088423  cmova   rdx, [rsp+98h+lpSubKey]; lpSubKey
0x180088429  lea     rax, [rsp+98h+hKey]
0x18008842e  mov     qword ptr [rsp+98h+phkResult], rax; unsigned int
0x180088433  mov     r9d, 2; samDesired
0x180088439  xor     r8d, r8d; ulOptions
0x18008843c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180088443  call    cs:__imp_RegOpenKeyExW
0x180088449  test    eax, eax
0x18008844b  jnz     loc_1800884F7
0x180088451  xorps   xmm0, xmm0
0x180088454  movups  xmmword ptr [rsp+98h+lpValueName], xmm0
0x180088459  xorps   xmm1, xmm1
0x18008845c  movdqu  [rsp+98h+var_48], xmm1
0x180088462  mov     r8, [rbx+8]
0x180088466  mov     rdx, [rbx]
0x180088469  lea     rcx, [rsp+98h+lpValueName]
0x18008846e  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180088473  lea     rdx, [rsp+98h+lpValueName]
0x180088478  cmp     qword ptr [rsp+98h+var_48+8], 7
0x18008847e  cmova   rdx, [rsp+98h+lpValueName]; lpValueName
0x180088484  mov     rcx, [rsp+98h+hKey]; hKey
0x180088489  call    cs:__imp_RegDeleteValueW
0x18008848f  mov     ebx, eax
0x180088491  lea     rcx, [rsp+98h+lpValueName]
0x180088496  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008849b  test    ebx, ebx
0x18008849d  jz      loc_180088534
0x1800884a3  mov     rcx, [rsp+98h]; this
0x1800884ab  mov     r9d, ebx; char *
0x1800884ae  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x1800884b5  mov     edx, 676h; void *
0x1800884ba  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800884bf  mov     ebx, eax
0x1800884c1  mov     rcx, [rsp+98h+hKey]; hKey
0x1800884c6  test    rcx, rcx
0x1800884c9  jz      short loc_1800884D2
0x1800884cb  call    cs:__imp_RegCloseKey
0x1800884d1  nop
0x1800884d2  lea     rcx, [rsp+98h+lpSubKey]
0x1800884d7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800884dc  mov     eax, ebx
0x1800884de  mov     rcx, [rsp+98h+var_18]
0x1800884e6  xor     rcx, rsp; StackCookie
0x1800884e9  call    __security_check_cookie
0x1800884ee  add     rsp, 90h
0x1800884f5  pop     rbx
0x1800884f6  retn
0x1800884f7  mov     rcx, [rsp+98h]; this
0x1800884ff  mov     r9d, eax; char *
0x180088502  lea     r8, aOnecoreBaseTel_198; "onecore\\base\\telemetry\\utc\\include"...
0x180088509  mov     edx, 674h; void *
0x18008850e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180088513  mov     ebx, eax
0x180088515  mov     rcx, [rsp+98h+hKey]; hKey
0x18008851a  test    rcx, rcx
0x18008851d  jz      short loc_180088526
0x18008851f  call    cs:__imp_RegCloseKey
0x180088525  nop
0x180088526  lea     rcx, [rsp+98h+lpSubKey]
0x18008852b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180088530  mov     eax, ebx
0x180088532  jmp     short loc_1800884DE
0x180088534  mov     rcx, [rsp+98h+hKey]; hKey
0x180088539  test    rcx, rcx
0x18008853c  jz      short loc_180088545
0x18008853e  call    cs:__imp_RegCloseKey
0x180088544  nop
0x180088545  lea     rcx, [rsp+98h+lpSubKey]
0x18008854a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008854f  xor     eax, eax
0x180088551  jmp     short loc_1800884DE
0x180088553  mov     eax, dword ptr [rsp+98h+hKey]
0x180088557  jmp     short loc_1800884DE
```
