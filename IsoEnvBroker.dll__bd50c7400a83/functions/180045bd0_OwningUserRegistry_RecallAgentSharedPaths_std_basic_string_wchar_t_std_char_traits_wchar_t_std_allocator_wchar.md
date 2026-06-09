# OwningUserRegistry::RecallAgentSharedPaths(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180045bd0`
- end: `0x180045ebe`
- name: `?RecallAgentSharedPaths@OwningUserRegistry@@QEAA?AV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@@Z`
- size: `750`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180040d30`
- `0x1800414dc`
- `0x180049750`

## callees

- `0x180002520`
- `0x18000e50c`
- `0x18001045c`
- `0x180011e18`
- `0x18001eb90`
- `0x18001f998`
- `0x18003dce4`
- `0x18003e7b0`
- `0x180045bd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045c81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045cb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045cfc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045c81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045cb3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180045cfc`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180045df4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180045e4e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180045df4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180045e4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045dc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045e0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045e1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045e8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045dc8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045e0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045e1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180045e8e`

## string_xrefs

- `0x180045ca7`: `RegisteredPaths`
- `0x180045d63`: `Recalled shared path for %s: %s`
- `0x180045e72`: `No shared paths found for %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall OwningUserRegistry::RecallAgentSharedPaths(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v3; // rbx
  int v5; // r14d
  int v6; // r15d
  DWORD i; // edx
  int v8; // esi
  DWORD j; // edx
  _QWORD *v10; // r9
  _QWORD *v11; // r8
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v14; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v15; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v17; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  HKEY v19; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v20[4]; // [rsp+78h] [rbp-88h] BYREF
  char v21; // [rsp+98h] [rbp-68h]
  _QWORD *v22; // [rsp+A0h] [rbp-60h]
  WCHAR Name[256]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SubKey[256]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v3 = a3;
  v22 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  wil::reg::create_unique_key(&hKey, *a1, a3);
  v5 = 3;
  v14 = 256;
  v6 = 1;
  for ( i = 0; !RegEnumKeyExW(hKey, i, SubKey, &v14, 0, 0, 0, 0); i = v6++ )
  {
    v14 = 256;
    phkResult = 0;
    if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &phkResult) )
    {
      v15 = 0;
      if ( !RegOpenKeyExW(phkResult, L"RegisteredPaths", 0, 0x20019u, &v15) )
      {
        cchName = 256;
        v8 = 1;
        for ( j = 0; !RegEnumKeyExW(v15, j, Name, &cchName, 0, 0, 0, 0); j = v8++ )
        {
          cchName = 256;
          v17 = 0;
          if ( !RegOpenKeyExW(v15, Name, 0, 0x20019u, &v17) )
          {
            v19 = v17;
            wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(
              &v19,
              v20,
              0,
              &stru_1800A0760,
              268435462);
            v5 |= 4u;
            if ( v21 )
            {
              v10 = v20;
              if ( v20[3] > 7u )
                v10 = (_QWORD *)v20[0];
              if ( v3[3] <= 7u )
                v11 = v3;
              else
                v11 = (_QWORD *)*v3;
              Log(4u, L"Recalled shared path for %s: %s", v11, v10);
              if ( !v21 )
                std::_Throw_bad_optional_access();
              if ( a2[1] == a2[2] )
              {
                std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a2, a2[1], v20);
              }
              else
              {
                std::wstring::wstring(a2[1], v20);
                a2[1] += 32LL;
              }
            }
            if ( v21 )
              std::wstring::~wstring(v20);
          }
          if ( v17 )
            RegCloseKey(v17);
        }
      }
      if ( v15 )
        RegCloseKey(v15);
    }
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  if ( *a2 == a2[1] )
  {
    if ( v3[3] > 7u )
      v3 = (_QWORD *)*v3;
    Log(4u, L"No shared paths found for %s", v3);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return a2;
}

```

## disassembly

```asm
0x180045bd0  push    rbp
0x180045bd2  push    rbx
0x180045bd3  push    rsi
0x180045bd4  push    rdi
0x180045bd5  push    r12
0x180045bd7  push    r14
0x180045bd9  push    r15
0x180045bdb  lea     rbp, [rsp-3C0h]
0x180045be3  sub     rsp, 4C0h
0x180045bea  mov     rax, cs:__security_cookie
0x180045bf1  xor     rax, rsp
0x180045bf4  mov     [rbp+3F0h+var_40], rax
0x180045bfb  mov     rbx, r8
0x180045bfe  mov     rdi, rdx
0x180045c01  mov     [rbp+3F0h+var_450], rdx
0x180045c05  xor     r12d, r12d
0x180045c08  mov     [rsp+4F0h+var_4B0], r12d
0x180045c0d  mov     [rdx], r12
0x180045c10  mov     [rdx+8], r12
0x180045c14  mov     [rdx+10h], r12
0x180045c18  mov     [rsp+4F0h+var_4B0], 1
0x180045c20  cmp     qword ptr [r8+18h], 7
0x180045c25  jbe     short loc_180045C2A
0x180045c27  mov     r8, [r8]
0x180045c2a  mov     rdx, [rcx]
0x180045c2d  lea     rcx, [rsp+4F0h+hKey]
0x180045c32  call    ?create_unique_key@reg@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@PEAUHKEY__@@PEB_WW4key_access@12@@Z; wil::reg::create_unique_key(HKEY__ *,wchar_t const *,wil::reg::key_access)
0x180045c37  mov     r14d, 3
0x180045c3d  mov     [rsp+4F0h+var_4B0], r14d
0x180045c42  mov     [rsp+4F0h+var_4A8], 100h
0x180045c4a  lea     r15d, [r14-2]
0x180045c4e  xor     edx, edx
0x180045c50  jmp     loc_180045E29
0x180045c55  mov     [rsp+4F0h+var_4A8], 100h
0x180045c5d  mov     [rsp+4F0h+var_498], r12
0x180045c62  lea     rax, [rsp+4F0h+var_498]
0x180045c67  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180045c6c  mov     r9d, 20019h; samDesired
0x180045c72  xor     r8d, r8d; ulOptions
0x180045c75  lea     rdx, [rbp+3F0h+SubKey]; lpSubKey
0x180045c7c  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180045c81  call    cs:__imp_RegOpenKeyExW
0x180045c87  test    eax, eax
0x180045c89  jnz     loc_180045E13
0x180045c8f  mov     [rsp+4F0h+var_4A0], r12
0x180045c94  lea     rax, [rsp+4F0h+var_4A0]
0x180045c99  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180045c9e  mov     r9d, 20019h; samDesired
0x180045ca4  xor     r8d, r8d; ulOptions
0x180045ca7  lea     rdx, aRegisteredpath; "RegisteredPaths"
0x180045cae  mov     rcx, [rsp+4F0h+var_498]; hKey
0x180045cb3  call    cs:__imp_RegOpenKeyExW
0x180045cb9  test    eax, eax
0x180045cbb  jnz     loc_180045E02
0x180045cc1  mov     [rsp+4F0h+cchName], 100h
0x180045cc9  lea     esi, [rax+1]
0x180045ccc  xor     edx, edx
0x180045cce  jmp     loc_180045DD2
0x180045cd3  mov     [rsp+4F0h+cchName], 100h
0x180045cdb  mov     [rsp+4F0h+var_490], r12
0x180045ce0  lea     rax, [rsp+4F0h+var_490]
0x180045ce5  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180045cea  mov     r9d, 20019h; samDesired
0x180045cf0  xor     r8d, r8d; ulOptions
0x180045cf3  lea     rdx, [rbp+3F0h+Name]; lpSubKey
0x180045cf7  mov     rcx, [rsp+4F0h+var_4A0]; hKey
0x180045cfc  call    cs:__imp_RegOpenKeyExW
0x180045d02  test    eax, eax
0x180045d04  jnz     loc_180045DBE
0x180045d0a  mov     rax, [rsp+4F0h+var_490]
0x180045d0f  mov     [rsp+4F0h+var_480], rax
0x180045d14  mov     dword ptr [rsp+4F0h+phkResult], 10000006h
0x180045d1c  lea     r9, stru_1800A0760
0x180045d23  xor     r8d, r8d
0x180045d26  lea     rdx, [rsp+4F0h+var_478]
0x180045d2b  lea     rcx, [rsp+4F0h+var_480]
0x180045d30  call    ??$try_get_value@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEB_W0K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<std::wstring>(wchar_t const *,wchar_t const *,ulong)
0x180045d35  or      r14d, 4
0x180045d39  mov     [rsp+4F0h+var_4B0], r14d
0x180045d3e  cmp     [rbp+3F0h+var_458], r12b
0x180045d42  jz      short loc_180045DAD
0x180045d44  lea     r9, [rsp+4F0h+var_478]
0x180045d49  cmp     [rbp+3F0h+var_460], 7
0x180045d4e  cmova   r9, [rsp+4F0h+var_478]
0x180045d54  cmp     qword ptr [rbx+18h], 7
0x180045d59  jbe     short loc_180045D60
0x180045d5b  mov     r8, [rbx]
0x180045d5e  jmp     short loc_180045D63
0x180045d60  mov     r8, rbx
0x180045d63  lea     rdx, aRecalledShared; "Recalled shared path for %s: %s"
0x180045d6a  mov     ecx, 4; unsigned __int8
0x180045d6f  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180045d74  cmp     [rbp+3F0h+var_458], r12b
0x180045d78  jz      loc_180045EB8
0x180045d7e  mov     rax, [rdi+8]
0x180045d82  cmp     rax, [rdi+10h]
0x180045d86  jz      short loc_180045D9C
0x180045d88  lea     rdx, [rsp+4F0h+var_478]
0x180045d8d  mov     rcx, rax
0x180045d90  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180045d95  add     qword ptr [rdi+8], 20h ; ' '
0x180045d9a  jmp     short loc_180045DAD
0x180045d9c  lea     r8, [rsp+4F0h+var_478]
0x180045da1  mov     rdx, rax
0x180045da4  mov     rcx, rdi
0x180045da7  call    ??$_Emplace_reallocate@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180045dac  nop
0x180045dad  cmp     [rbp+3F0h+var_458], r12b
0x180045db1  jz      short loc_180045DBE
0x180045db3  lea     rcx, [rsp+4F0h+var_478]
0x180045db8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180045dbd  nop
0x180045dbe  mov     rcx, [rsp+4F0h+var_490]; hKey
0x180045dc3  test    rcx, rcx
0x180045dc6  jz      short loc_180045DCE
0x180045dc8  call    cs:__imp_RegCloseKey
0x180045dce  mov     edx, esi; dwIndex
0x180045dd0  inc     esi
0x180045dd2  mov     [rsp+4F0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180045dd7  mov     [rsp+4F0h+lpcchClass], r12; lpcchClass
0x180045ddc  mov     [rsp+4F0h+lpClass], r12; lpClass
0x180045de1  mov     [rsp+4F0h+phkResult], r12; lpReserved
0x180045de6  lea     r9, [rsp+4F0h+cchName]; lpcchName
0x180045deb  lea     r8, [rbp+3F0h+Name]; lpName
0x180045def  mov     rcx, [rsp+4F0h+var_4A0]; hKey
0x180045df4  call    cs:__imp_RegEnumKeyExW
0x180045dfa  test    eax, eax
0x180045dfc  jz      loc_180045CD3
0x180045e02  mov     rcx, [rsp+4F0h+var_4A0]; hKey
0x180045e07  test    rcx, rcx
0x180045e0a  jz      short loc_180045E13
0x180045e0c  call    cs:__imp_RegCloseKey
0x180045e12  nop
0x180045e13  mov     rcx, [rsp+4F0h+var_498]; hKey
0x180045e18  test    rcx, rcx
0x180045e1b  jz      short loc_180045E23
0x180045e1d  call    cs:__imp_RegCloseKey
0x180045e23  mov     edx, r15d; dwIndex
0x180045e26  inc     r15d
0x180045e29  mov     [rsp+4F0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180045e2e  mov     [rsp+4F0h+lpcchClass], r12; lpcchClass
0x180045e33  mov     [rsp+4F0h+lpClass], r12; lpClass
0x180045e38  mov     [rsp+4F0h+phkResult], r12; lpReserved
0x180045e3d  lea     r9, [rsp+4F0h+var_4A8]; lpcchName
0x180045e42  lea     r8, [rbp+3F0h+SubKey]; lpName
0x180045e49  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180045e4e  call    cs:__imp_RegEnumKeyExW
0x180045e54  test    eax, eax
0x180045e56  jz      loc_180045C55
0x180045e5c  mov     rax, [rdi+8]
0x180045e60  cmp     [rdi], rax
0x180045e63  jnz     short loc_180045E84
0x180045e65  cmp     qword ptr [rbx+18h], 7
0x180045e6a  jbe     short loc_180045E6F
0x180045e6c  mov     rbx, [rbx]
0x180045e6f  mov     r8, rbx
0x180045e72  lea     rdx, aNoSharedPathsF; "No shared paths found for %s"
0x180045e79  mov     ecx, 4; unsigned __int8
0x180045e7e  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180045e83  nop
0x180045e84  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180045e89  test    rcx, rcx
0x180045e8c  jz      short loc_180045E94
0x180045e8e  call    cs:__imp_RegCloseKey
0x180045e94  mov     rax, rdi
0x180045e97  mov     rcx, [rbp+3F0h+var_40]
0x180045e9e  xor     rcx, rsp; StackCookie
0x180045ea1  call    __security_check_cookie
0x180045ea6  add     rsp, 4C0h
0x180045ead  pop     r15
0x180045eaf  pop     r14
0x180045eb1  pop     r12
0x180045eb3  pop     rdi
0x180045eb4  pop     rsi
0x180045eb5  pop     rbx
0x180045eb6  pop     rbp
0x180045eb7  retn
0x180045eb8  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
```
