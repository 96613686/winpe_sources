# Utility::GetLoadedUserHiveSids(void)

- ea: `0x180052178`
- end: `0x180052415`
- name: `?GetLoadedUserHiveSids@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `669`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180031a40`

## callees

- `0x18000e458`
- `0x180018a60`
- `0x18001e0d0`
- `0x18001ea80`
- `0x18002a36c`
- `0x180046510`
- `0x18004869c`
- `0x1800493b8`
- `0x18004f820`
- `0x180050030`
- `0x180052178`
- `0x180052bfc`
- `0x180052f28`
- `0x180059920`
- `0x180059cd0`
- `0x180059f2c`
- `0x180059f94`
- `0x1800679f8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180052254`
- `ADVAPI32!RegOpenKeyExW` at `0x180052254`
- `ADVAPI32!RegEnumKeyExW` at `0x180052322`
- `ADVAPI32!RegEnumKeyExW` at `0x180052322`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800522a6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800522a6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18005222b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18005222b`

## string_xrefs

- `0x1800522c3`: `onecore\internal\base\inc\appcompat\inventory\utility.cpp`
- `0x180052403`: `onecore\internal\base\inc\appcompat\inventory\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 *Utility::GetLoadedUserHiveSids()
{
  __int64 *AllUserSids; // rax
  int v1; // eax
  DWORD i; // edi
  WCHAR *v3; // r8
  LSTATUS v4; // eax
  __int64 v5; // rbx
  __int64 v6; // rsi
  _QWORD *v7; // r8
  LPWSTR *v8; // rcx
  int phkResult; // [rsp+20h] [rbp-99h]
  int phkResulta; // [rsp+20h] [rbp-99h]
  DWORD cSubKeys; // [rsp+60h] [rbp-59h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-55h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-51h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-49h] BYREF
  RTL_SRWLOCK *v16; // [rsp+78h] [rbp-41h] BYREF
  _QWORD v17[4]; // [rsp+80h] [rbp-39h] BYREF
  LPWSTR lpName[3]; // [rsp+A0h] [rbp-19h] BYREF
  unsigned __int64 v19; // [rsp+B8h] [rbp-1h]
  _QWORD v20[4]; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v17[3] = -2;
  if ( dword_180184160 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180184160);
    if ( dword_180184160 == -1 )
    {
      std::vector<enum tagMSIINSTALLCONTEXT>::vector<enum tagMSIINSTALLCONTEXT>(qword_180184168);
      atexit(Utility::GetLoadedUserHiveSids_::_2_::_dynamic_atexit_destructor_for__loadedUserHiveSids__);
      Init_thread_footer(&dword_180184160);
    }
  }
  if ( !byte_180183E80 )
  {
    AllUserSids = Utility::GetAllUserSids(0);
    std::vector<std::wstring>::vector<std::wstring>(v17, AllUserSids);
    AcquireSRWLockExclusive(&stru_180183E78);
    v16 = &stru_180183E78;
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_USERS, 0, 0, 0x20019u, &hKey) )
    {
      cSubKeys = 0;
      cbMaxSubKeyLen = 0;
      v1 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      if ( v1 > 0 )
        v1 = (unsigned __int16)v1 | 0x80070000;
      if ( v1 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x2CC,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\utility.cpp",
          (const char *)(unsigned int)v1,
          phkResult);
      for ( i = 0; i < cSubKeys; ++i )
      {
        cchName = cbMaxSubKeyLen + 1;
        std::wstring::wstring(lpName, cbMaxSubKeyLen + 1);
        v3 = (WCHAR *)lpName;
        if ( v19 > 7 )
          v3 = lpName[0];
        v4 = RegEnumKeyExW(hKey, i, v3, &cchName, 0, 0, 0, 0);
        if ( v4 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x2DA,
            (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\utility.cpp",
            (const char *)(unsigned int)v4,
            phkResulta);
        std::wstring::resize(lpName, cchName);
        v5 = v17[0];
        v6 = v17[1];
        while ( v5 != v6 )
        {
          std::wstring::wstring(v20, v5);
          v7 = v20;
          if ( v20[3] > 7u )
            v7 = (_QWORD *)v20[0];
          v8 = lpName;
          if ( v19 > 7 )
            v8 = (LPWSTR *)lpName[0];
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                  v8,
                                  lpName[2],
                                  v7,
                                  v20[2],
                                  phkResulta) )
            std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184168, lpName);
          std::wstring::~wstring(v20);
          v5 += 32;
        }
        std::wstring::~wstring(lpName);
      }
    }
    byte_180183E80 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    std::vector<std::wstring>::_Tidy(v17);
  }
  return qword_180184168;
}

```

## disassembly

```asm
0x180052178  push    rbp
0x18005217a  push    rbx
0x18005217b  push    rsi
0x18005217c  push    rdi
0x18005217d  push    r14
0x18005217f  lea     rbp, [rsp-37h]
0x180052184  sub     rsp, 0F0h
0x18005218b  mov     [rbp+57h+var_78], 0FFFFFFFFFFFFFFFEh
0x180052193  mov     rax, cs:__security_cookie
0x18005219a  xor     rax, rsp
0x18005219d  mov     [rbp+57h+var_30], rax
0x1800521a1  mov     ecx, cs:_tls_index
0x1800521a7  mov     rax, gs:58h
0x1800521b0  mov     edx, 4
0x1800521b5  mov     rax, [rax+rcx*8]
0x1800521b9  mov     eax, [rdx+rax]
0x1800521bc  cmp     cs:dword_180184160, eax
0x1800521c2  jle     short loc_1800521FD
0x1800521c4  lea     rcx, dword_180184160
0x1800521cb  call    _Init_thread_header
0x1800521d0  cmp     cs:dword_180184160, 0FFFFFFFFh
0x1800521d7  jnz     short loc_1800521FD
0x1800521d9  lea     rcx, qword_180184168
0x1800521e0  call    ??0?$vector@W4tagMSIINSTALLCONTEXT@@V?$allocator@W4tagMSIINSTALLCONTEXT@@@std@@@std@@QEAA@XZ; std::vector<tagMSIINSTALLCONTEXT>::vector<tagMSIINSTALLCONTEXT>(void)
0x1800521e5  lea     rcx, _Utility__GetLoadedUserHiveSids____2____dynamic_atexit_destructor_for__loadedUserHiveSids__; void (__cdecl *)()
0x1800521ec  call    atexit
0x1800521f1  lea     rcx, dword_180184160
0x1800521f8  call    _Init_thread_footer
0x1800521fd  xor     r14d, r14d
0x180052200  cmp     cs:byte_180183E80, r14b
0x180052207  jnz     loc_1800523DF
0x18005220d  xor     ecx, ecx
0x18005220f  call    ?GetAllUserSids@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_N@Z; Utility::GetAllUserSids(bool)
0x180052214  mov     rdx, rax
0x180052217  lea     rcx, [rbp+57h+var_90]
0x18005221b  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180052220  nop
0x180052221  lea     rbx, stru_180183E78
0x180052228  mov     rcx, rbx; SRWLock
0x18005222b  call    cs:__imp_AcquireSRWLockExclusive
0x180052231  mov     [rbp+57h+var_98], rbx
0x180052235  mov     [rbp+57h+hKey], r14
0x180052239  lea     rax, [rbp+57h+hKey]
0x18005223d  mov     [rsp+110h+phkResult], rax; phkResult
0x180052242  mov     r9d, 20019h; samDesired
0x180052248  xor     r8d, r8d; ulOptions
0x18005224b  xor     edx, edx; lpSubKey
0x18005224d  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180052254  call    cs:__imp_RegOpenKeyExW
0x18005225a  test    eax, eax
0x18005225c  jnz     loc_1800523BB
0x180052262  mov     [rbp+57h+cSubKeys], r14d
0x180052266  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x18005226a  mov     [rsp+110h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18005226f  mov     [rsp+110h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x180052274  mov     [rsp+110h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x180052279  mov     [rsp+110h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18005227e  mov     [rsp+110h+lpcValues], r14; lpcValues
0x180052283  mov     [rsp+110h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x180052288  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18005228c  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180052291  lea     rax, [rbp+57h+cSubKeys]
0x180052295  mov     [rsp+110h+phkResult], rax; int
0x18005229a  xor     r9d, r9d; lpReserved
0x18005229d  xor     r8d, r8d; lpcchClass
0x1800522a0  xor     edx, edx; lpClass
0x1800522a2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800522a6  call    cs:__imp_RegQueryInfoKeyW
0x1800522ac  test    eax, eax
0x1800522ae  jle     short loc_1800522B8
0x1800522b0  movzx   eax, ax
0x1800522b3  or      eax, 80070000h
0x1800522b8  mov     rcx, [rbp+5Fh]; this
0x1800522bc  test    eax, eax
0x1800522be  jns     short loc_1800522D5
0x1800522c0  mov     r9d, eax; char *
0x1800522c3  lea     r8, aOnecoreInterna_2; "onecore\\internal\\base\\inc\\appcompat"...
0x1800522ca  mov     edx, 2CCh; void *
0x1800522cf  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800522d5  mov     edi, r14d
0x1800522d8  cmp     [rbp+57h+cSubKeys], r14d
0x1800522dc  jbe     loc_1800523BB
0x1800522e2  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1800522e5  inc     eax
0x1800522e7  mov     [rbp+57h+cchName], eax
0x1800522ea  mov     edx, eax
0x1800522ec  lea     rcx, [rbp+57h+lpName]
0x1800522f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1800522f5  nop
0x1800522f6  lea     r8, [rbp+57h+lpName]
0x1800522fa  cmp     [rbp+57h+var_58], 7
0x1800522ff  cmova   r8, [rbp+57h+lpName]; lpName
0x180052304  mov     [rsp+110h+lpcValues], r14; lpftLastWriteTime
0x180052309  mov     [rsp+110h+lpcbMaxClassLen], r14; lpcchClass
0x18005230e  mov     [rsp+110h+lpcbMaxSubKeyLen], r14; lpClass
0x180052313  mov     [rsp+110h+phkResult], r14; int
0x180052318  lea     r9, [rbp+57h+cchName]; lpcchName
0x18005231c  mov     edx, edi; dwIndex
0x18005231e  mov     rcx, [rbp+57h+hKey]; hKey
0x180052322  call    cs:__imp_RegEnumKeyExW
0x180052328  mov     rcx, [rbp+5Fh]; this
0x18005232c  test    eax, eax
0x18005232e  js      loc_180052400
0x180052334  mov     edx, [rbp+57h+cchName]
0x180052337  lea     rcx, [rbp+57h+lpName]
0x18005233b  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180052340  mov     rbx, [rbp+57h+var_90]
0x180052344  mov     rsi, [rbp+57h+var_88]
0x180052348  jmp     short loc_1800523A2
0x18005234a  mov     rdx, rbx
0x18005234d  lea     rcx, [rbp+57h+var_50]
0x180052351  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180052356  nop
0x180052357  lea     r8, [rbp+57h+var_50]
0x18005235b  cmp     [rbp+57h+var_38], 7
0x180052360  cmova   r8, [rbp+57h+var_50]
0x180052365  lea     rcx, [rbp+57h+lpName]
0x180052369  cmp     [rbp+57h+var_58], 7
0x18005236e  cmova   rcx, [rbp+57h+lpName]
0x180052373  mov     r9, [rbp+57h+var_40]
0x180052377  mov     rdx, [rbp+57h+var_60]
0x18005237b  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180052380  test    al, al
0x180052382  jz      short loc_180052395
0x180052384  lea     rdx, [rbp+57h+lpName]
0x180052388  lea     rcx, qword_180184168
0x18005238f  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x180052394  nop
0x180052395  lea     rcx, [rbp+57h+var_50]
0x180052399  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005239e  add     rbx, 20h ; ' '
0x1800523a2  cmp     rbx, rsi
0x1800523a5  jnz     short loc_18005234A
0x1800523a7  lea     rcx, [rbp+57h+lpName]
0x1800523ab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800523b0  inc     edi
0x1800523b2  cmp     edi, [rbp+57h+cSubKeys]
0x1800523b5  jb      loc_1800522E2
0x1800523bb  mov     cs:byte_180183E80, r14b
0x1800523c2  lea     rcx, [rbp+57h+hKey]
0x1800523c6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800523cb  nop
0x1800523cc  lea     rcx, [rbp+57h+var_98]
0x1800523d0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800523d5  nop
0x1800523d6  lea     rcx, [rbp+57h+var_90]
0x1800523da  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800523df  lea     rax, qword_180184168
0x1800523e6  mov     rcx, [rbp+57h+var_30]
0x1800523ea  xor     rcx, rsp; StackCookie
0x1800523ed  call    __security_check_cookie
0x1800523f2  add     rsp, 0F0h
0x1800523f9  pop     r14
0x1800523fb  pop     rdi
0x1800523fc  pop     rsi
0x1800523fd  pop     rbx
0x1800523fe  pop     rbp
0x1800523ff  retn
0x180052400  mov     r9d, eax; char *
0x180052403  lea     r8, aOnecoreInterna_2; "onecore\\internal\\base\\inc\\appcompat"...
0x18005240a  mov     edx, 2DAh; void *
0x18005240f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
