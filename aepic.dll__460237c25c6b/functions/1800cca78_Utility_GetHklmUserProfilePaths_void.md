# Utility::GetHklmUserProfilePaths(void)

- ea: `0x1800cca78`
- end: `0x1800cce5f`
- name: `?GetHklmUserProfilePaths@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `999`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800cd720`
- `0x1800ce2c0`

## callees

- `0x180005890`
- `0x180005d10`
- `0x180005ec0`
- `0x180005f28`
- `0x180008570`
- `0x18000faf0`
- `0x1800108a8`
- `0x18001c5f0`
- `0x1800c31cc`
- `0x1800c97f0`
- `0x1800c993c`
- `0x1800ca464`
- `0x1800cca78`
- `0x1800cd470`
- `0x1800cea08`
- `0x1800d00c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800ccd20`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x1800ccd20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ccb3e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ccb3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ccb8c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ccb8c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ccc60`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ccc60`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ccbe1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ccbe1`

## string_xrefs

- `0x1800ccbfe`: `onecore\base\appcompat\inventory\software\inv\lib\utility.cpp`
- `0x1800cce4d`: `onecore\base\appcompat\inventory\software\inv\lib\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 *Utility::GetHklmUserProfilePaths()
{
  __int64 v0; // rbx
  const WCHAR *v1; // rdx
  int v2; // eax
  DWORD i; // ebx
  WCHAR *v4; // r8
  LSTATUS v5; // eax
  __int64 *v6; // rdx
  LPWSTR *v7; // rdx
  __int64 v8; // rax
  unsigned __int16 *v9; // rcx
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  RTL_SRWLOCK *v25; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v26[3]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v27; // [rsp+98h] [rbp-68h]
  LPWSTR lpName[3]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v29; // [rsp+B8h] [rbp-48h]
  _BYTE v30[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v31[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v32[32]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_180122E80 > *(_DWORD *)(v0 + 4) )
  {
    Init_thread_header(&dword_180122E80);
    if ( dword_180122E80 == -1 )
    {
      atexit(Utility::GetHklmUserProfilePaths_::_2_::_dynamic_atexit_destructor_for__userProfilePaths__);
      Init_thread_footer(&dword_180122E80);
    }
  }
  if ( dword_180122EA0 > *(_DWORD *)(v0 + 4) )
  {
    Init_thread_header(&dword_180122EA0);
    if ( dword_180122EA0 == -1 )
    {
      atexit(Utility::GetHklmUserProfilePaths_::_2_::_dynamic_atexit_destructor_for__programDataPath__);
      Init_thread_footer(&dword_180122EA0);
    }
  }
  if ( byte_180120D99 )
  {
    AcquireSRWLockExclusive(&stru_180122B58);
    v25 = &stru_180122B58;
    if ( byte_180120D99 )
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
            (void *)0x58E,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\utility.cpp",
            (const char *)(unsigned int)v2,
            phkResult);
        for ( i = 0; i < cSubKeys; ++i )
        {
          cchName = cbMaxSubKeyLen + 1;
          std::wstring::wstring(lpName, cbMaxSubKeyLen + 1);
          v4 = (WCHAR *)lpName;
          if ( v29 > 7 )
            v4 = lpName[0];
          v5 = RegEnumKeyExW(hKey, i, v4, &cchName, 0, 0, 0, 0);
          if ( v5 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x59C,
              (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\utility.cpp",
              (const char *)(unsigned int)v5,
              phkResulta);
          std::wstring::resize(lpName, cchName);
          v6 = &Utility::ProfileImagePath;
          if ( (unsigned __int64)qword_180121C68 > 7 )
            v6 = (__int64 *)Utility::ProfileImagePath;
          std::wstring::wstring(v31, v6);
          v7 = lpName;
          if ( v29 > 7 )
            v7 = (LPWSTR *)lpName[0];
          std::wstring::wstring(v30, v7);
          Utility::GetRegValueString(v26, hKey, v30, v31);
          std::wstring::_Tidy_deallocate(v30);
          std::wstring::_Tidy_deallocate(v31);
          v8 = Utility::ToLower(v32, v26);
          std::wstring::operator=(v26, v8);
          std::wstring::_Tidy_deallocate(v32);
          if ( v26[2] >= 9u )
          {
            v9 = (unsigned __int16 *)v26;
            if ( v27 > 7 )
              v9 = (unsigned __int16 *)v26[0];
            if ( (unsigned int)_o_iswalpha(*v9) )
            {
              v10 = v26;
              if ( v27 > 7 )
                v10 = (_QWORD *)v26[0];
              if ( *((_WORD *)v10 + 1) == 58 )
              {
                v11 = v26;
                if ( v27 > 7 )
                  v11 = (_QWORD *)v26[0];
                if ( *((_WORD *)v11 + 2) == 92 )
                {
                  v12 = v26;
                  if ( v27 > 7 )
                    v12 = (_QWORD *)v26[0];
                  if ( *((_WORD *)v12 + 3) == 117 )
                  {
                    v13 = v26;
                    if ( v27 > 7 )
                      v13 = (_QWORD *)v26[0];
                    if ( *((_WORD *)v13 + 4) == 115 )
                    {
                      v14 = v26;
                      if ( v27 > 7 )
                        v14 = (_QWORD *)v26[0];
                      if ( *((_WORD *)v14 + 5) == 101 )
                      {
                        v15 = v26;
                        if ( v27 > 7 )
                          v15 = (_QWORD *)v26[0];
                        if ( *((_WORD *)v15 + 6) == 114 )
                        {
                          v16 = v26;
                          if ( v27 > 7 )
                            v16 = (_QWORD *)v26[0];
                          if ( *((_WORD *)v16 + 7) == 115 )
                          {
                            v17 = v26;
                            if ( v27 > 7 )
                              v17 = (_QWORD *)v26[0];
                            if ( *((_WORD *)v17 + 8) == 92 )
                              std::vector<std::wstring>::push_back(qword_180122E88, v26);
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          std::wstring::_Tidy_deallocate(v26);
          std::wstring::_Tidy_deallocate(lpName);
        }
      }
      byte_180120D99 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v25);
  }
  return qword_180122E88;
}

```

## disassembly

```asm
0x1800cca78  mov     [rsp-8+arg_0], rbx
0x1800cca7d  mov     [rsp-8+arg_8], rdi
0x1800cca82  push    rbp
0x1800cca83  lea     rbp, [rsp-30h]
0x1800cca88  sub     rsp, 130h
0x1800cca8f  mov     rax, cs:__security_cookie
0x1800cca96  xor     rax, rsp
0x1800cca99  mov     [rbp+30h+var_10], rax
0x1800cca9d  mov     ecx, cs:_tls_index
0x1800ccaa3  mov     rax, gs:58h
0x1800ccaac  mov     edi, 4
0x1800ccab1  mov     rbx, [rax+rcx*8]
0x1800ccab5  mov     eax, [rbx+rdi]
0x1800ccab8  cmp     cs:dword_180122E80, eax
0x1800ccabe  jle     short loc_1800CCAED
0x1800ccac0  lea     rcx, dword_180122E80
0x1800ccac7  call    _Init_thread_header
0x1800ccacc  cmp     cs:dword_180122E80, 0FFFFFFFFh
0x1800ccad3  jnz     short loc_1800CCAED
0x1800ccad5  lea     rcx, _Utility__GetHklmUserProfilePaths____2____dynamic_atexit_destructor_for__userProfilePaths__; void (__cdecl *)()
0x1800ccadc  call    atexit
0x1800ccae1  lea     rcx, dword_180122E80
0x1800ccae8  call    _Init_thread_footer
0x1800ccaed  mov     eax, [rbx+rdi]
0x1800ccaf0  cmp     cs:dword_180122EA0, eax
0x1800ccaf6  jle     short loc_1800CCB25
0x1800ccaf8  lea     rcx, dword_180122EA0
0x1800ccaff  call    _Init_thread_header
0x1800ccb04  cmp     cs:dword_180122EA0, 0FFFFFFFFh
0x1800ccb0b  jnz     short loc_1800CCB25
0x1800ccb0d  lea     rcx, _Utility__GetHklmUserProfilePaths____2____dynamic_atexit_destructor_for__programDataPath__; void (__cdecl *)()
0x1800ccb14  call    atexit
0x1800ccb19  lea     rcx, dword_180122EA0
0x1800ccb20  call    _Init_thread_footer
0x1800ccb25  xor     edi, edi
0x1800ccb27  cmp     cs:byte_180120D99, dil
0x1800ccb2e  jz      loc_1800CCE22
0x1800ccb34  lea     rbx, stru_180122B58
0x1800ccb3b  mov     rcx, rbx; SRWLock
0x1800ccb3e  call    cs:__imp_AcquireSRWLockExclusive
0x1800ccb44  mov     [rsp+130h+var_B8], rbx
0x1800ccb49  cmp     cs:byte_180120D99, dil
0x1800ccb50  jz      loc_1800CCE18
0x1800ccb56  mov     [rsp+130h+hKey], rdi
0x1800ccb5b  lea     rdx, ?ProfileListSubKeyPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::ProfileListSubKeyPath
0x1800ccb62  cmp     cs:qword_180121C48, 7
0x1800ccb6a  cmova   rdx, cs:?ProfileListSubKeyPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; lpSubKey
0x1800ccb72  lea     rax, [rsp+130h+hKey]
0x1800ccb77  mov     [rsp+130h+phkResult], rax; phkResult
0x1800ccb7c  mov     r9d, 20019h; samDesired
0x1800ccb82  xor     r8d, r8d; ulOptions
0x1800ccb85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ccb8c  call    cs:__imp_RegOpenKeyExW
0x1800ccb92  test    eax, eax
0x1800ccb94  jnz     loc_1800CCE06
0x1800ccb9a  mov     [rsp+130h+cSubKeys], edi
0x1800ccb9e  mov     [rsp+130h+cbMaxSubKeyLen], edi
0x1800ccba2  mov     [rsp+130h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800ccba7  mov     [rsp+130h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x1800ccbac  mov     [rsp+130h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x1800ccbb1  mov     [rsp+130h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x1800ccbb6  mov     [rsp+130h+lpcValues], rdi; lpcValues
0x1800ccbbb  mov     [rsp+130h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x1800ccbc0  lea     rax, [rsp+130h+cbMaxSubKeyLen]
0x1800ccbc5  mov     [rsp+130h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800ccbca  lea     rax, [rsp+130h+cSubKeys]
0x1800ccbcf  mov     [rsp+130h+phkResult], rax; int
0x1800ccbd4  xor     r9d, r9d; lpReserved
0x1800ccbd7  xor     r8d, r8d; lpcchClass
0x1800ccbda  xor     edx, edx; lpClass
0x1800ccbdc  mov     rcx, [rsp+130h+hKey]; hKey
0x1800ccbe1  call    cs:__imp_RegQueryInfoKeyW
0x1800ccbe7  test    eax, eax
0x1800ccbe9  jle     short loc_1800CCBF3
0x1800ccbeb  movzx   eax, ax
0x1800ccbee  or      eax, 80070000h
0x1800ccbf3  mov     rcx, [rbp+38h]; this
0x1800ccbf7  test    eax, eax
0x1800ccbf9  jns     short loc_1800CCC10
0x1800ccbfb  mov     r9d, eax; char *
0x1800ccbfe  lea     r8, aOnecoreBaseApp; "onecore\\base\\appcompat\\inventory\\so"...
0x1800ccc05  mov     edx, 58Eh; void *
0x1800ccc0a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800ccc10  mov     ebx, edi
0x1800ccc12  cmp     [rsp+130h+cSubKeys], edi
0x1800ccc16  jbe     loc_1800CCE06
0x1800ccc1c  mov     eax, [rsp+130h+cbMaxSubKeyLen]
0x1800ccc20  inc     eax
0x1800ccc22  mov     [rsp+130h+cchName], eax
0x1800ccc26  mov     edx, eax
0x1800ccc28  lea     rcx, [rbp+30h+lpName]
0x1800ccc2c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1800ccc31  nop
0x1800ccc32  lea     r8, [rbp+30h+lpName]
0x1800ccc36  cmp     [rbp+30h+var_78], 7
0x1800ccc3b  cmova   r8, [rbp+30h+lpName]; lpName
0x1800ccc40  mov     [rsp+130h+lpcValues], rdi; lpftLastWriteTime
0x1800ccc45  mov     [rsp+130h+lpcbMaxClassLen], rdi; lpcchClass
0x1800ccc4a  mov     [rsp+130h+lpcbMaxSubKeyLen], rdi; lpClass
0x1800ccc4f  mov     [rsp+130h+phkResult], rdi; int
0x1800ccc54  lea     r9, [rsp+130h+cchName]; lpcchName
0x1800ccc59  mov     edx, ebx; dwIndex
0x1800ccc5b  mov     rcx, [rsp+130h+hKey]; hKey
0x1800ccc60  call    cs:__imp_RegEnumKeyExW
0x1800ccc66  mov     rcx, [rbp+38h]; this
0x1800ccc6a  test    eax, eax
0x1800ccc6c  js      loc_1800CCE4A
0x1800ccc72  mov     edx, [rsp+130h+cchName]
0x1800ccc76  lea     rcx, [rbp+30h+lpName]
0x1800ccc7a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800ccc7f  lea     rdx, ?ProfileImagePath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::ProfileImagePath
0x1800ccc86  cmp     cs:qword_180121C68, 7
0x1800ccc8e  cmova   rdx, cs:?ProfileImagePath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::ProfileImagePath
0x1800ccc96  lea     rcx, [rbp+30h+var_50]
0x1800ccc9a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ccc9f  nop
0x1800ccca0  lea     rdx, [rbp+30h+lpName]
0x1800ccca4  cmp     [rbp+30h+var_78], 7
0x1800ccca9  cmova   rdx, [rbp+30h+lpName]
0x1800cccae  lea     rcx, [rbp+30h+var_70]
0x1800cccb2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cccb7  nop
0x1800cccb8  lea     r9, [rbp+30h+var_50]
0x1800cccbc  lea     r8, [rbp+30h+var_70]
0x1800cccc0  mov     rdx, [rsp+130h+hKey]
0x1800cccc5  lea     rcx, [rbp+30h+var_B0]
0x1800cccc9  call    ?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z; Utility::GetRegValueString(HKEY__ * const,std::wstring const &,std::wstring const &,bool)
0x1800cccce  nop
0x1800ccccf  lea     rcx, [rbp+30h+var_70]
0x1800cccd3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cccd8  nop
0x1800cccd9  lea     rcx, [rbp+30h+var_50]
0x1800cccdd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ccce2  lea     rdx, [rbp+30h+var_B0]
0x1800ccce6  lea     rcx, [rbp+30h+var_30]
0x1800cccea  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cccef  mov     rdx, rax
0x1800cccf2  lea     rcx, [rbp+30h+var_B0]
0x1800cccf6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800cccfb  lea     rcx, [rbp+30h+var_30]
0x1800cccff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ccd04  cmp     [rbp+30h+var_A0], 9
0x1800ccd09  jb      loc_1800CCDE7
0x1800ccd0f  lea     rcx, [rbp+30h+var_B0]
0x1800ccd13  cmp     [rbp+30h+var_98], 7
0x1800ccd18  cmova   rcx, [rbp+30h+var_B0]
0x1800ccd1d  movzx   ecx, word ptr [rcx]
0x1800ccd20  call    cs:__imp__o_iswalpha
0x1800ccd26  test    eax, eax
0x1800ccd28  jz      loc_1800CCDE7
0x1800ccd2e  mov     rcx, [rbp+30h+var_98]
0x1800ccd32  lea     rax, [rbp+30h+var_B0]
0x1800ccd36  mov     rdx, [rbp+30h+var_B0]
0x1800ccd3a  cmp     rcx, 7
0x1800ccd3e  cmova   rax, rdx
0x1800ccd42  cmp     word ptr [rax+2], 3Ah ; ':'
0x1800ccd47  jnz     loc_1800CCDE7
0x1800ccd4d  lea     rax, [rbp+30h+var_B0]
0x1800ccd51  cmp     rcx, 7
0x1800ccd55  cmova   rax, rdx
0x1800ccd59  cmp     word ptr [rax+4], 5Ch ; '\'
0x1800ccd5e  jnz     loc_1800CCDE7
0x1800ccd64  lea     rax, [rbp+30h+var_B0]
0x1800ccd68  cmp     rcx, 7
0x1800ccd6c  cmova   rax, rdx
0x1800ccd70  cmp     word ptr [rax+6], 75h ; 'u'
0x1800ccd75  jnz     short loc_1800CCDE7
0x1800ccd77  lea     rax, [rbp+30h+var_B0]
0x1800ccd7b  cmp     rcx, 7
0x1800ccd7f  cmova   rax, rdx
0x1800ccd83  cmp     word ptr [rax+8], 73h ; 's'
0x1800ccd88  jnz     short loc_1800CCDE7
0x1800ccd8a  lea     rax, [rbp+30h+var_B0]
0x1800ccd8e  cmp     rcx, 7
0x1800ccd92  cmova   rax, rdx
0x1800ccd96  cmp     word ptr [rax+0Ah], 65h ; 'e'
0x1800ccd9b  jnz     short loc_1800CCDE7
0x1800ccd9d  lea     rax, [rbp+30h+var_B0]
0x1800ccda1  cmp     rcx, 7
0x1800ccda5  cmova   rax, rdx
0x1800ccda9  cmp     word ptr [rax+0Ch], 72h ; 'r'
0x1800ccdae  jnz     short loc_1800CCDE7
0x1800ccdb0  lea     rax, [rbp+30h+var_B0]
0x1800ccdb4  cmp     rcx, 7
0x1800ccdb8  cmova   rax, rdx
0x1800ccdbc  cmp     word ptr [rax+0Eh], 73h ; 's'
0x1800ccdc1  jnz     short loc_1800CCDE7
0x1800ccdc3  lea     rax, [rbp+30h+var_B0]
0x1800ccdc7  cmp     rcx, 7
0x1800ccdcb  cmova   rax, rdx
0x1800ccdcf  cmp     word ptr [rax+10h], 5Ch ; '\'
0x1800ccdd4  jnz     short loc_1800CCDE7
0x1800ccdd6  lea     rdx, [rbp+30h+var_B0]
0x1800ccdda  lea     rcx, qword_180122E88
0x1800ccde1  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800ccde6  nop
0x1800ccde7  lea     rcx, [rbp+30h+var_B0]
0x1800ccdeb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ccdf0  nop
0x1800ccdf1  lea     rcx, [rbp+30h+lpName]
0x1800ccdf5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ccdfa  inc     ebx
0x1800ccdfc  cmp     ebx, [rsp+130h+cSubKeys]
0x1800cce00  jb      loc_1800CCC1C
0x1800cce06  mov     cs:byte_180120D99, dil
0x1800cce0d  lea     rcx, [rsp+130h+hKey]
0x1800cce12  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cce17  nop
0x1800cce18  lea     rcx, [rsp+130h+var_B8]
0x1800cce1d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800cce22  lea     rax, qword_180122E88
0x1800cce29  mov     rcx, [rbp+30h+var_10]
0x1800cce2d  xor     rcx, rsp; StackCookie
0x1800cce30  call    __security_check_cookie
0x1800cce35  lea     r11, [rsp+130h+var_s0]
0x1800cce3d  mov     rbx, [r11+10h]
0x1800cce41  mov     rdi, [r11+18h]
0x1800cce45  mov     rsp, r11
0x1800cce48  pop     rbp
0x1800cce49  retn
0x1800cce4a  mov     r9d, eax; char *
0x1800cce4d  lea     r8, aOnecoreBaseApp; "onecore\\base\\appcompat\\inventory\\so"...
0x1800cce54  mov     edx, 59Ch; void *
0x1800cce59  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
