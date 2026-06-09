# Windows::Registry::GetSubKeyList(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x18003c8dc`
- end: `0x18003cb55`
- name: `?GetSubKeyList@Registry@Windows@@QEAA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAUHKEY__@@V?$basic_zstring_view@_W@wil@@1@Z`
- size: `633`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x18000cde8`
- `0x180034570`

## callees

- `0x180009380`
- `0x1800338a4`
- `0x18003679c`
- `0x18003c020`
- `0x18003c8dc`
- `0x18003d328`
- `0x18003d47c`
- `0x18003dbf4`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003caf3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003caf3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c981`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c981`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003ca48`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003ca48`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003c9d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003c9d1`

## string_xrefs

- `0x18003cb2e`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`
- `0x18003cb43`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Registry::GetSubKeyList(__int64 a1, __int64 a2, __int64 a3, _OWORD *a4, _OWORD *a5)
{
  const WCHAR *v6; // rdx
  unsigned int v7; // eax
  DWORD v8; // edi
  __m128i si128; // xmm6
  unsigned int v10; // eax
  __int64 v11; // r8
  _OWORD *v12; // rdx
  unsigned int phkResult; // [rsp+28h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+28h] [rbp-E0h]
  _QWORD v16[3]; // [rsp+70h] [rbp-98h] BYREF
  __m128i v17; // [rsp+88h] [rbp-80h]
  __int64 v18; // [rsp+98h] [rbp-70h]
  DWORD cbMaxSubKeyLen; // [rsp+A0h] [rbp-68h] BYREF
  DWORD cSubKeys; // [rsp+A4h] [rbp-64h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp-60h] BYREF
  DWORD cchName; // [rsp+B0h] [rbp-58h] BYREF
  LPWSTR lpName[2]; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v24; // [rsp+C8h] [rbp-40h]
  LPCWSTR lpSubKey[4]; // [rsp+D8h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+130h] [rbp+28h]

  v18 = a2;
  *(_OWORD *)a2 = 0;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  *(_OWORD *)&v16[1] = *a5;
  *(_OWORD *)lpName = *a4;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, lpName, &v16[1]);
  hKey = 0;
  v6 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v6 = lpSubKey[0];
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x20019u, &hKey) )
  {
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v7 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1CC,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
        (const char *)v7,
        phkResult);
    if ( cSubKeys )
    {
      ++cbMaxSubKeyLen;
      *(_OWORD *)lpName = 0;
      v24 = 0;
      std::vector<wchar_t>::vector<wchar_t>(lpName, cbMaxSubKeyLen);
      v8 = 0;
      if ( cSubKeys )
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        do
        {
          cchName = cbMaxSubKeyLen;
          v10 = RegEnumKeyExW(hKey, v8, lpName[0], &cchName, 0, 0, 0, 0);
          if ( v10 == 259 )
            break;
          if ( v10 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x1DD,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
              (const char *)v10,
              phkResulta);
          *(_OWORD *)&v16[1] = 0;
          v17 = 0;
          v11 = -1;
          do
            ++v11;
          while ( lpName[0][v11] );
          std::wstring::_Construct<1,wchar_t const *>(&v16[1]);
          v12 = *(_OWORD **)(a2 + 8);
          if ( v12 == *(_OWORD **)(a2 + 16) )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a2, v12, &v16[1]);
          }
          else
          {
            *v12 = *(_OWORD *)&v16[1];
            v12[1] = v17;
            v17 = si128;
            LOWORD(v16[1]) = 0;
            *(_QWORD *)(a2 + 8) += 32LL;
          }
          std::wstring::~wstring(&v16[1]);
          ++v8;
        }
        while ( v8 < cSubKeys );
      }
      std::vector<wchar_t>::~vector<wchar_t>(lpName);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(lpSubKey);
  return a2;
}

```

## disassembly

```asm
0x18003c8dc  mov     rax, rsp
0x18003c8df  mov     [rax+8], rbx
0x18003c8e3  push    rbp
0x18003c8e4  push    rsi
0x18003c8e5  push    rdi
0x18003c8e6  lea     rbp, [rax-28h]
0x18003c8ea  sub     rsp, 110h
0x18003c8f1  movaps  xmmword ptr [rax-28h], xmm6
0x18003c8f5  mov     rax, cs:__security_cookie
0x18003c8fc  xor     rax, rsp
0x18003c8ff  mov     [rbp+20h+var_30], rax
0x18003c903  mov     rbx, rdx
0x18003c906  mov     [rbp+20h+var_90], rdx
0x18003c90a  mov     rax, [rbp+20h+arg_20]
0x18003c90e  mov     [rsp+120h+var_C0], 1
0x18003c916  xorps   xmm0, xmm0
0x18003c919  movups  xmmword ptr [rdx], xmm0
0x18003c91c  xor     esi, esi
0x18003c91e  mov     [rdx], rsi
0x18003c921  mov     [rdx+8], rsi
0x18003c925  mov     [rdx+10h], rsi
0x18003c929  mov     [rsp+120h+var_C0], 1
0x18003c931  movaps  xmm0, xmmword ptr [rax]
0x18003c934  movdqa  xmmword ptr [rsp+120h+var_B8+8], xmm0
0x18003c93a  movaps  xmm1, xmmword ptr [r9]
0x18003c93e  movdqa  xmmword ptr [rbp+20h+lpName], xmm1
0x18003c943  lea     r9, [rsp+120h+var_B8+8]
0x18003c948  lea     r8, [rbp+20h+lpName]
0x18003c94c  lea     rdx, [rbp+20h+lpSubKey]
0x18003c950  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18003c955  nop
0x18003c956  mov     [rbp+20h+hKey], rsi
0x18003c95a  lea     rdx, [rbp+20h+lpSubKey]
0x18003c95e  cmp     [rbp+20h+var_38], 7
0x18003c963  cmova   rdx, [rbp+20h+lpSubKey]; lpSubKey
0x18003c968  lea     rax, [rbp+20h+hKey]
0x18003c96c  mov     [rsp+120h+phkResult], rax; phkResult
0x18003c971  mov     r9d, 20019h; samDesired
0x18003c977  xor     r8d, r8d; ulOptions
0x18003c97a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c981  call    cs:__imp_RegOpenKeyExW
0x18003c987  test    eax, eax
0x18003c989  jnz     loc_18003CAEA
0x18003c98f  mov     [rbp+20h+cSubKeys], esi
0x18003c992  mov     [rbp+20h+cbMaxSubKeyLen], esi
0x18003c995  mov     [rsp+120h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18003c99a  mov     [rsp+120h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18003c99f  mov     [rsp+120h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18003c9a4  mov     [rsp+120h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18003c9a9  mov     [rsp+120h+lpcValues], rsi; lpcValues
0x18003c9ae  mov     [rsp+120h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18003c9b3  lea     rax, [rbp+20h+cbMaxSubKeyLen]
0x18003c9b7  mov     [rsp+120h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18003c9bc  lea     rax, [rbp+20h+cSubKeys]
0x18003c9c0  mov     [rsp+120h+phkResult], rax; unsigned int
0x18003c9c5  xor     r9d, r9d; lpReserved
0x18003c9c8  xor     r8d, r8d; lpcchClass
0x18003c9cb  xor     edx, edx; lpClass
0x18003c9cd  mov     rcx, [rbp+20h+hKey]; hKey
0x18003c9d1  call    cs:__imp_RegQueryInfoKeyW
0x18003c9d7  mov     rcx, [rbp+28h]; this
0x18003c9db  test    eax, eax
0x18003c9dd  jnz     loc_18003CB2B
0x18003c9e3  cmp     [rbp+20h+cSubKeys], esi
0x18003c9e6  jbe     loc_18003CAEA
0x18003c9ec  mov     eax, [rbp+20h+cbMaxSubKeyLen]
0x18003c9ef  inc     eax
0x18003c9f1  mov     [rbp+20h+cbMaxSubKeyLen], eax
0x18003c9f4  mov     edx, eax
0x18003c9f6  xorps   xmm0, xmm0
0x18003c9f9  xor     eax, eax
0x18003c9fb  movups  xmmword ptr [rbp+20h+lpName], xmm0
0x18003c9ff  mov     [rbp+20h+var_60], rax
0x18003ca03  lea     rcx, [rbp+20h+lpName]
0x18003ca07  call    ??0?$vector@_WV?$allocator@_W@std@@@std@@QEAA@_KAEBV?$allocator@_W@1@@Z; std::vector<wchar_t>::vector<wchar_t>(unsigned __int64,std::allocator<wchar_t> const &)
0x18003ca0c  nop
0x18003ca0d  mov     edi, esi
0x18003ca0f  cmp     [rbp+20h+cSubKeys], esi
0x18003ca12  jbe     loc_18003CAE0
0x18003ca18  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18003ca20  mov     eax, [rbp+20h+cbMaxSubKeyLen]
0x18003ca23  mov     [rbp+20h+cchName], eax
0x18003ca26  mov     [rsp+120h+lpcValues], rsi; lpftLastWriteTime
0x18003ca2b  mov     [rsp+120h+lpcbMaxClassLen], rsi; lpcchClass
0x18003ca30  mov     [rsp+120h+lpcbMaxSubKeyLen], rsi; lpClass
0x18003ca35  mov     [rsp+120h+phkResult], rsi; unsigned int
0x18003ca3a  lea     r9, [rbp+20h+cchName]; lpcchName
0x18003ca3e  mov     r8, [rbp+20h+lpName]; lpName
0x18003ca42  mov     edx, edi; dwIndex
0x18003ca44  mov     rcx, [rbp+20h+hKey]; hKey
0x18003ca48  call    cs:__imp_RegEnumKeyExW
0x18003ca4e  cmp     eax, 103h
0x18003ca53  jz      loc_18003CAE0
0x18003ca59  mov     rcx, [rbp+28h]; this
0x18003ca5d  test    eax, eax
0x18003ca5f  jnz     loc_18003CB40
0x18003ca65  xorps   xmm0, xmm0
0x18003ca68  movups  xmmword ptr [rsp+120h+var_B8+8], xmm0
0x18003ca6d  xorps   xmm1, xmm1
0x18003ca70  movdqu  [rbp+20h+var_A0], xmm1
0x18003ca75  mov     rdx, [rbp+20h+lpName]
0x18003ca79  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003ca7d  inc     r8
0x18003ca80  cmp     [rdx+r8*2], si
0x18003ca85  jnz     short loc_18003CA7D
0x18003ca87  lea     rcx, [rsp+120h+var_B8+8]
0x18003ca8c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003ca91  nop
0x18003ca92  mov     rdx, [rbx+8]
0x18003ca96  cmp     rdx, [rbx+10h]
0x18003ca9a  jz      short loc_18003CABD
0x18003ca9c  movups  xmm0, xmmword ptr [rsp+120h+var_B8+8]
0x18003caa1  movups  xmmword ptr [rdx], xmm0
0x18003caa4  movups  xmm1, [rbp+20h+var_A0]
0x18003caa8  movups  xmmword ptr [rdx+10h], xmm1
0x18003caac  movdqu  [rbp+20h+var_A0], xmm6
0x18003cab1  mov     word ptr [rsp+120h+var_B8+8], si
0x18003cab6  add     qword ptr [rbx+8], 20h ; ' '
0x18003cabb  jmp     short loc_18003CACB
0x18003cabd  lea     r8, [rsp+120h+var_B8+8]
0x18003cac2  mov     rcx, rbx
0x18003cac5  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18003caca  nop
0x18003cacb  lea     rcx, [rsp+120h+var_B8+8]; void *
0x18003cad0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cad5  inc     edi
0x18003cad7  cmp     edi, [rbp+20h+cSubKeys]
0x18003cada  jb      loc_18003CA20
0x18003cae0  lea     rcx, [rbp+20h+lpName]
0x18003cae4  call    ??1?$vector@_WV?$allocator@_W@std@@@std@@QEAA@XZ; std::vector<wchar_t>::~vector<wchar_t>(void)
0x18003cae9  nop
0x18003caea  mov     rcx, [rbp+20h+hKey]; hKey
0x18003caee  test    rcx, rcx
0x18003caf1  jz      short loc_18003CAFA
0x18003caf3  call    cs:__imp_RegCloseKey
0x18003caf9  nop
0x18003cafa  lea     rcx, [rbp+20h+lpSubKey]; void *
0x18003cafe  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cb03  nop
0x18003cb04  mov     rax, rbx
0x18003cb07  mov     rcx, [rbp+20h+var_30]
0x18003cb0b  xor     rcx, rsp; StackCookie
0x18003cb0e  call    __security_check_cookie
0x18003cb13  lea     r11, [rsp+120h+var_10]
0x18003cb1b  mov     rbx, [r11+20h]
0x18003cb1f  movaps  xmm6, xmmword ptr [r11-10h]
0x18003cb24  mov     rsp, r11
0x18003cb27  pop     rdi
0x18003cb28  pop     rsi
0x18003cb29  pop     rbp
0x18003cb2a  retn
0x18003cb2b  mov     r9d, eax; char *
0x18003cb2e  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003cb35  mov     edx, 1CCh; void *
0x18003cb3a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003cb40  mov     r9d, eax; char *
0x18003cb43  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003cb4a  mov     edx, 1DDh; void *
0x18003cb4f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
