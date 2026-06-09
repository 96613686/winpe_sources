# Utility::GetAllUserSids(bool)

- ea: `0x1800caa40`
- end: `0x1800cacbd`
- name: `?GetAllUserSids@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_N@Z`
- size: `637`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800cce68`
- `0x1800cd894`
- `0x1800dc88c`

## callees

- `0x180005890`
- `0x180005d10`
- `0x180005ec0`
- `0x180005f28`
- `0x180008570`
- `0x18001c5f0`
- `0x1800c31cc`
- `0x1800c97f0`
- `0x1800c993c`
- `0x1800ca464`
- `0x1800caa40`
- `0x1800d00c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cac3b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cac3b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800caae4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800caae4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cab2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cab2f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800cabf9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800cabf9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800cab7f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800cab7f`

## string_xrefs

- `0x1800cab9c`: `onecore\base\appcompat\inventory\software\inv\lib\utility.cpp`
- `0x1800cacab`: `onecore\base\appcompat\inventory\software\inv\lib\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *Utility::GetAllUserSids()
{
  char v0; // al
  const WCHAR *v1; // rdx
  int v2; // eax
  DWORD i; // edi
  WCHAR *v4; // r8
  LSTATUS v5; // eax
  __int64 *j; // rbx
  LPWSTR *v7; // rcx
  int phkResult; // [rsp+20h] [rbp-59h]
  int phkResulta; // [rsp+20h] [rbp-59h]
  DWORD cSubKeys; // [rsp+60h] [rbp-19h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-15h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-11h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-9h] BYREF
  RTL_SRWLOCK *v15; // [rsp+78h] [rbp-1h] BYREF
  LPWSTR lpName[3]; // [rsp+80h] [rbp+7h] BYREF
  unsigned __int64 v17; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( dword_180122DE0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180122DE0);
    if ( dword_180122DE0 == -1 )
    {
      atexit(Utility::GetAllUserSids_::_2_::_dynamic_atexit_destructor_for__allUserSids__);
      Init_thread_footer(&dword_180122DE0);
    }
  }
  if ( byte_180122B98 )
  {
    v0 = 0;
    byte_180122B88 = 0;
    byte_180122B98 = 0;
  }
  else
  {
    v0 = byte_180122B88;
  }
  if ( !v0 )
  {
    AcquireSRWLockExclusive(&stru_180122B90);
    v15 = &stru_180122B90;
    if ( !byte_180122B88 )
    {
      hKey = 0;
      v1 = (const WCHAR *)&Utility::ProfileListSubKeyPath;
      if ( (unsigned __int64)qword_180121C48 > 7 )
        v1 = Utility::ProfileListSubKeyPath;
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0x20019u, &hKey) )
      {
        cSubKeys = 0;
        cbMaxSubKeyLen = 0;
        v2 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
        if ( v2 > 0 )
          v2 = (unsigned __int16)v2 | 0x80070000;
        if ( v2 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x267,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\utility.cpp",
            (const char *)(unsigned int)v2,
            phkResult);
        for ( i = 0; i < cSubKeys; ++i )
        {
          cchName = cbMaxSubKeyLen + 1;
          std::wstring::wstring(lpName, cbMaxSubKeyLen + 1);
          v4 = (WCHAR *)lpName;
          if ( v17 > 7 )
            v4 = lpName[0];
          v5 = RegEnumKeyExW(hKey, i, v4, &cchName, 0, 0, 0, 0);
          if ( v5 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x275,
              (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\utility.cpp",
              (const char *)(unsigned int)v5,
              phkResulta);
          std::wstring::resize(lpName, cchName);
          for ( j = (__int64 *)off_1800EFDC0; j != &qword_1800EFDD8; ++j )
          {
            v7 = lpName;
            if ( v17 > 7 )
              v7 = (LPWSTR *)lpName[0];
            if ( !(unsigned int)_o__wcsicmp(v7, *j) )
              goto LABEL_27;
          }
          std::vector<std::wstring>::push_back(qword_180122DE8, lpName);
LABEL_27:
          std::wstring::_Tidy_deallocate(lpName);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
    byte_180122B88 = 1;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  }
  return qword_180122DE8;
}

```

## disassembly

```asm
0x1800caa40  push    rbp
0x1800caa42  push    rbx
0x1800caa43  push    rsi
0x1800caa44  push    rdi
0x1800caa45  lea     rbp, [rsp-3Fh]
0x1800caa4a  sub     rsp, 0B8h
0x1800caa51  mov     rax, cs:__security_cookie
0x1800caa58  xor     rax, rsp
0x1800caa5b  mov     [rbp+57h+var_30], rax
0x1800caa5f  mov     ecx, cs:_tls_index
0x1800caa65  mov     rax, gs:58h
0x1800caa6e  mov     edx, 4
0x1800caa73  mov     rax, [rax+rcx*8]
0x1800caa77  mov     eax, [rdx+rax]
0x1800caa7a  cmp     cs:dword_180122DE0, eax
0x1800caa80  jle     short loc_1800CAAAF
0x1800caa82  lea     rcx, dword_180122DE0
0x1800caa89  call    _Init_thread_header
0x1800caa8e  cmp     cs:dword_180122DE0, 0FFFFFFFFh
0x1800caa95  jnz     short loc_1800CAAAF
0x1800caa97  lea     rcx, _Utility__GetAllUserSids____2____dynamic_atexit_destructor_for__allUserSids__; void (__cdecl *)()
0x1800caa9e  call    atexit
0x1800caaa3  lea     rcx, dword_180122DE0
0x1800caaaa  call    _Init_thread_footer
0x1800caaaf  xor     esi, esi
0x1800caab1  cmp     cs:byte_180122B98, sil
0x1800caab8  jz      short loc_1800CAACC
0x1800caaba  mov     al, sil
0x1800caabd  mov     cs:byte_180122B88, al
0x1800caac3  mov     cs:byte_180122B98, sil
0x1800caaca  jmp     short loc_1800CAAD2
0x1800caacc  mov     al, cs:byte_180122B88
0x1800caad2  test    al, al
0x1800caad4  jnz     loc_1800CAC89
0x1800caada  lea     rbx, stru_180122B90
0x1800caae1  mov     rcx, rbx; SRWLock
0x1800caae4  call    cs:__imp_AcquireSRWLockExclusive
0x1800caaea  mov     [rbp+57h+var_58], rbx
0x1800caaee  cmp     cs:byte_180122B88, sil
0x1800caaf5  jnz     loc_1800CAC79
0x1800caafb  mov     [rbp+57h+hKey], rsi
0x1800caaff  lea     rdx, ?ProfileListSubKeyPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::ProfileListSubKeyPath
0x1800cab06  cmp     cs:qword_180121C48, 7
0x1800cab0e  cmova   rdx, cs:?ProfileListSubKeyPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; lpSubKey
0x1800cab16  lea     rax, [rbp+57h+hKey]
0x1800cab1a  mov     [rsp+0D0h+phkResult], rax; phkResult
0x1800cab1f  mov     r9d, 20019h; samDesired
0x1800cab25  xor     r8d, r8d; ulOptions
0x1800cab28  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800cab2f  call    cs:__imp_RegOpenKeyExW
0x1800cab35  test    eax, eax
0x1800cab37  jnz     loc_1800CAC70
0x1800cab3d  mov     [rbp+57h+cSubKeys], esi
0x1800cab40  mov     [rbp+57h+cbMaxSubKeyLen], esi
0x1800cab43  mov     [rsp+0D0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x1800cab48  mov     [rsp+0D0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x1800cab4d  mov     [rsp+0D0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x1800cab52  mov     [rsp+0D0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x1800cab57  mov     [rsp+0D0h+lpcValues], rsi; lpcValues
0x1800cab5c  mov     [rsp+0D0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x1800cab61  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1800cab65  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800cab6a  lea     rax, [rbp+57h+cSubKeys]
0x1800cab6e  mov     [rsp+0D0h+phkResult], rax; int
0x1800cab73  xor     r9d, r9d; lpReserved
0x1800cab76  xor     r8d, r8d; lpcchClass
0x1800cab79  xor     edx, edx; lpClass
0x1800cab7b  mov     rcx, [rbp+57h+hKey]; hKey
0x1800cab7f  call    cs:__imp_RegQueryInfoKeyW
0x1800cab85  test    eax, eax
0x1800cab87  jle     short loc_1800CAB91
0x1800cab89  movzx   eax, ax
0x1800cab8c  or      eax, 80070000h
0x1800cab91  mov     rcx, [rbp+5Fh]; this
0x1800cab95  test    eax, eax
0x1800cab97  jns     short loc_1800CABAE
0x1800cab99  mov     r9d, eax; char *
0x1800cab9c  lea     r8, aOnecoreBaseApp; "onecore\\base\\appcompat\\inventory\\so"...
0x1800caba3  mov     edx, 267h; void *
0x1800caba8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800cabae  mov     edi, esi
0x1800cabb0  cmp     [rbp+57h+cSubKeys], esi
0x1800cabb3  jbe     loc_1800CAC70
0x1800cabb9  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1800cabbc  inc     eax
0x1800cabbe  mov     [rbp+57h+cchName], eax
0x1800cabc1  mov     edx, eax
0x1800cabc3  lea     rcx, [rbp+57h+lpName]
0x1800cabc7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1800cabcc  nop
0x1800cabcd  lea     r8, [rbp+57h+lpName]
0x1800cabd1  cmp     [rbp+57h+var_38], 7
0x1800cabd6  cmova   r8, [rbp+57h+lpName]; lpName
0x1800cabdb  mov     [rsp+0D0h+lpcValues], rsi; lpftLastWriteTime
0x1800cabe0  mov     [rsp+0D0h+lpcbMaxClassLen], rsi; lpcchClass
0x1800cabe5  mov     [rsp+0D0h+lpcbMaxSubKeyLen], rsi; lpClass
0x1800cabea  mov     [rsp+0D0h+phkResult], rsi; int
0x1800cabef  lea     r9, [rbp+57h+cchName]; lpcchName
0x1800cabf3  mov     edx, edi; dwIndex
0x1800cabf5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800cabf9  call    cs:__imp_RegEnumKeyExW
0x1800cabff  mov     rcx, [rbp+5Fh]; this
0x1800cac03  test    eax, eax
0x1800cac05  js      loc_1800CACA8
0x1800cac0b  mov     edx, [rbp+57h+cchName]
0x1800cac0e  lea     rcx, [rbp+57h+lpName]
0x1800cac12  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800cac17  lea     rbx, off_1800EFDC0; "s-1-5-18"
0x1800cac1e  lea     rax, qword_1800EFDD8
0x1800cac25  cmp     rbx, rax
0x1800cac28  jz      short loc_1800CAC4B
0x1800cac2a  lea     rcx, [rbp+57h+lpName]
0x1800cac2e  cmp     [rbp+57h+var_38], 7
0x1800cac33  cmova   rcx, [rbp+57h+lpName]
0x1800cac38  mov     rdx, [rbx]
0x1800cac3b  call    cs:__imp__o__wcsicmp
0x1800cac41  test    eax, eax
0x1800cac43  jz      short loc_1800CAC5C
0x1800cac45  add     rbx, 8
0x1800cac49  jmp     short loc_1800CAC1E
0x1800cac4b  lea     rdx, [rbp+57h+lpName]
0x1800cac4f  lea     rcx, qword_180122DE8
0x1800cac56  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cac5b  nop
0x1800cac5c  lea     rcx, [rbp+57h+lpName]
0x1800cac60  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cac65  inc     edi
0x1800cac67  cmp     edi, [rbp+57h+cSubKeys]
0x1800cac6a  jb      loc_1800CABB9
0x1800cac70  lea     rcx, [rbp+57h+hKey]
0x1800cac74  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cac79  mov     cs:byte_180122B88, 1
0x1800cac80  lea     rcx, [rbp+57h+var_58]
0x1800cac84  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800cac89  lea     rax, qword_180122DE8
0x1800cac90  mov     rcx, [rbp+57h+var_30]
0x1800cac94  xor     rcx, rsp; StackCookie
0x1800cac97  call    __security_check_cookie
0x1800cac9c  add     rsp, 0B8h
0x1800caca3  pop     rdi
0x1800caca4  pop     rsi
0x1800caca5  pop     rbx
0x1800caca6  pop     rbp
0x1800caca7  retn
0x1800caca8  mov     r9d, eax; char *
0x1800cacab  lea     r8, aOnecoreBaseApp; "onecore\\base\\appcompat\\inventory\\so"...
0x1800cacb2  mov     edx, 275h; void *
0x1800cacb7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
