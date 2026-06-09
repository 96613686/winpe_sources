# Utility::GetHklmUserProfilePaths(void)

- ea: `0x180051d68`
- end: `0x18005216f`
- name: `?GetHklmUserProfilePaths@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `1031`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180043640`
- `0x1800439d0`
- `0x180043ebc`

## callees

- `0x18000e458`
- `0x1800150ac`
- `0x180017724`
- `0x180018300`
- `0x180018450`
- `0x180018a60`
- `0x18001ea80`
- `0x1800404c4`
- `0x18004869c`
- `0x1800493b8`
- `0x180050030`
- `0x180051d68`
- `0x180052bfc`
- `0x180059920`
- `0x180059cd0`
- `0x180059f2c`
- `0x180059f94`
- `0x1800679f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180052030`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x180052030`
- `ADVAPI32!RegOpenKeyExW` at `0x180051e9c`
- `ADVAPI32!RegOpenKeyExW` at `0x180051e9c`
- `ADVAPI32!RegEnumKeyExW` at `0x180051f70`
- `ADVAPI32!RegEnumKeyExW` at `0x180051f70`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180051ef1`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180051ef1`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180051e4e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180051e4e`

## string_xrefs

- `0x180051f0e`: `onecore\internal\base\inc\appcompat\inventory\utility.cpp`
- `0x18005215d`: `onecore\internal\base\inc\appcompat\inventory\utility.cpp`

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
  __int64 *v9; // rcx
  __int64 *v10; // rax
  __int64 *v11; // rax
  __int64 *v12; // rax
  __int64 *v13; // rax
  __int64 *v14; // rax
  __int64 *v15; // rax
  __int64 *v16; // rax
  __int64 *v17; // rax
  int phkResult; // [rsp+28h] [rbp-E0h]
  int phkResulta; // [rsp+28h] [rbp-E0h]
  DWORD cSubKeys; // [rsp+68h] [rbp-A0h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+6Ch] [rbp-9Ch] BYREF
  DWORD cchName[2]; // [rsp+70h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v25[2]; // [rsp+80h] [rbp-88h] BYREF
  __int64 v26[3]; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v27; // [rsp+A8h] [rbp-60h]
  LPWSTR lpName[3]; // [rsp+B0h] [rbp-58h] BYREF
  unsigned __int64 v29; // [rsp+C8h] [rbp-40h]
  WCHAR v30[16]; // [rsp+D0h] [rbp-38h] BYREF
  WCHAR v31[16]; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v32[32]; // [rsp+110h] [rbp+8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+38h]

  v25[1] = -2;
  v0 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_180184208 > *(_DWORD *)(v0 + 4) )
  {
    Init_thread_header(&dword_180184208);
    if ( dword_180184208 == -1 )
    {
      std::vector<enum tagMSIINSTALLCONTEXT>::vector<enum tagMSIINSTALLCONTEXT>(qword_180184210);
      atexit(Utility::GetHklmUserProfilePaths_::_2_::_dynamic_atexit_destructor_for__userProfilePaths__);
      Init_thread_footer(&dword_180184208);
    }
  }
  if ( dword_180184228 > *(_DWORD *)(v0 + 4) )
  {
    Init_thread_header(&dword_180184228);
    if ( dword_180184228 == -1 )
    {
      std::wstring::wstring(qword_180184230);
      atexit(Utility::GetHklmUserProfilePaths_::_2_::_dynamic_atexit_destructor_for__programDataPath__);
      Init_thread_footer(&dword_180184228);
    }
  }
  if ( byte_1801817E5 )
  {
    AcquireSRWLockExclusive(&stru_180183E50);
    v25[0] = &stru_180183E50;
    if ( byte_1801817E5 )
    {
      hKey = 0;
      v1 = (const WCHAR *)&Utility::ProfileListSubKeyPath;
      if ( (unsigned __int64)qword_1801831D8 > 7 )
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
            (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\utility.cpp",
            (const char *)(unsigned int)v2,
            phkResult);
        for ( i = 0; i < cSubKeys; ++i )
        {
          cchName[0] = cbMaxSubKeyLen + 1;
          std::wstring::wstring(lpName, cbMaxSubKeyLen + 1);
          v4 = (WCHAR *)lpName;
          if ( v29 > 7 )
            v4 = lpName[0];
          v5 = RegEnumKeyExW(hKey, i, v4, cchName, 0, 0, 0, 0);
          if ( v5 < 0 )
            wil::details::in1diag3::_Throw_Hr(
              retaddr,
              (void *)0x59C,
              (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\utility.cpp",
              (const char *)(unsigned int)v5,
              phkResulta);
          std::wstring::resize(lpName, cchName[0]);
          v6 = &Utility::ProfileImagePath;
          if ( (unsigned __int64)qword_1801831F8 > 7 )
            v6 = (__int64 *)Utility::ProfileImagePath;
          std::wstring::wstring(v31, v6);
          v7 = lpName;
          if ( v29 > 7 )
            v7 = (LPWSTR *)lpName[0];
          std::wstring::wstring(v30, v7);
          Utility::GetRegValueString((__int64)v26, hKey, v30, v31);
          std::wstring::~wstring(v30);
          std::wstring::~wstring(v31);
          v8 = Utility::ToLower((__int64)v32, v26);
          std::wstring::operator=(v26, v8);
          std::wstring::~wstring(v32);
          if ( v26[2] >= 9uLL )
          {
            v9 = v26;
            if ( v27 > 7 )
              v9 = (__int64 *)v26[0];
            if ( (unsigned int)_o_iswalpha(*(unsigned __int16 *)v9) )
            {
              v10 = v26;
              if ( v27 > 7 )
                v10 = (__int64 *)v26[0];
              if ( *((_WORD *)v10 + 1) == 58 )
              {
                v11 = v26;
                if ( v27 > 7 )
                  v11 = (__int64 *)v26[0];
                if ( *((_WORD *)v11 + 2) == 92 )
                {
                  v12 = v26;
                  if ( v27 > 7 )
                    v12 = (__int64 *)v26[0];
                  if ( *((_WORD *)v12 + 3) == 117 )
                  {
                    v13 = v26;
                    if ( v27 > 7 )
                      v13 = (__int64 *)v26[0];
                    if ( *((_WORD *)v13 + 4) == 115 )
                    {
                      v14 = v26;
                      if ( v27 > 7 )
                        v14 = (__int64 *)v26[0];
                      if ( *((_WORD *)v14 + 5) == 101 )
                      {
                        v15 = v26;
                        if ( v27 > 7 )
                          v15 = (__int64 *)v26[0];
                        if ( *((_WORD *)v15 + 6) == 114 )
                        {
                          v16 = v26;
                          if ( v27 > 7 )
                            v16 = (__int64 *)v26[0];
                          if ( *((_WORD *)v16 + 7) == 115 )
                          {
                            v17 = v26;
                            if ( v27 > 7 )
                              v17 = (__int64 *)v26[0];
                            if ( *((_WORD *)v17 + 8) == 92 )
                              std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_180184210, v26);
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          std::wstring::~wstring(v26);
          std::wstring::~wstring(lpName);
        }
      }
      byte_1801817E5 = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v25);
  }
  return qword_180184210;
}

```

## disassembly

```asm
0x180051d68  mov     rax, rsp
0x180051d6b  push    rbp
0x180051d6c  lea     rbp, [rax-38h]
0x180051d70  sub     rsp, 130h
0x180051d77  mov     [rbp+30h+var_B0], 0FFFFFFFFFFFFFFFEh
0x180051d7f  mov     [rax+8], rbx
0x180051d83  mov     [rax+10h], rdi
0x180051d87  mov     rax, cs:__security_cookie
0x180051d8e  xor     rax, rsp
0x180051d91  mov     [rbp+30h+var_8], rax
0x180051d95  mov     ecx, cs:_tls_index
0x180051d9b  mov     rax, gs:58h
0x180051da4  mov     edi, 4
0x180051da9  mov     rbx, [rax+rcx*8]
0x180051dad  mov     eax, [rbx+rdi]
0x180051db0  cmp     cs:dword_180184208, eax
0x180051db6  jle     short loc_180051DF1
0x180051db8  lea     rcx, dword_180184208
0x180051dbf  call    _Init_thread_header
0x180051dc4  cmp     cs:dword_180184208, 0FFFFFFFFh
0x180051dcb  jnz     short loc_180051DF1
0x180051dcd  lea     rcx, qword_180184210
0x180051dd4  call    ??0?$vector@W4tagMSIINSTALLCONTEXT@@V?$allocator@W4tagMSIINSTALLCONTEXT@@@std@@@std@@QEAA@XZ; std::vector<tagMSIINSTALLCONTEXT>::vector<tagMSIINSTALLCONTEXT>(void)
0x180051dd9  lea     rcx, _Utility__GetHklmUserProfilePaths____2____dynamic_atexit_destructor_for__userProfilePaths__; void (__cdecl *)()
0x180051de0  call    atexit
0x180051de5  lea     rcx, dword_180184208
0x180051dec  call    _Init_thread_footer
0x180051df1  mov     eax, [rbx+rdi]
0x180051df4  cmp     cs:dword_180184228, eax
0x180051dfa  jle     short loc_180051E35
0x180051dfc  lea     rcx, dword_180184228
0x180051e03  call    _Init_thread_header
0x180051e08  cmp     cs:dword_180184228, 0FFFFFFFFh
0x180051e0f  jnz     short loc_180051E35
0x180051e11  lea     rcx, qword_180184230
0x180051e18  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180051e1d  lea     rcx, _Utility__GetHklmUserProfilePaths____2____dynamic_atexit_destructor_for__programDataPath__; void (__cdecl *)()
0x180051e24  call    atexit
0x180051e29  lea     rcx, dword_180184228
0x180051e30  call    _Init_thread_footer
0x180051e35  xor     edi, edi
0x180051e37  cmp     cs:byte_1801817E5, dil
0x180051e3e  jz      loc_180052132
0x180051e44  lea     rbx, stru_180183E50
0x180051e4b  mov     rcx, rbx; SRWLock
0x180051e4e  call    cs:__imp_AcquireSRWLockExclusive
0x180051e54  mov     [rsp+130h+var_B8], rbx
0x180051e59  cmp     cs:byte_1801817E5, dil
0x180051e60  jz      loc_180052128
0x180051e66  mov     [rsp+130h+hKey], rdi
0x180051e6b  lea     rdx, ?ProfileListSubKeyPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::ProfileListSubKeyPath
0x180051e72  cmp     cs:qword_1801831D8, 7
0x180051e7a  cmova   rdx, cs:?ProfileListSubKeyPath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; lpSubKey
0x180051e82  lea     rax, [rsp+130h+hKey]
0x180051e87  mov     [rsp+130h+phkResult], rax; phkResult
0x180051e8c  mov     r9d, 20019h; samDesired
0x180051e92  xor     r8d, r8d; ulOptions
0x180051e95  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180051e9c  call    cs:__imp_RegOpenKeyExW
0x180051ea2  test    eax, eax
0x180051ea4  jnz     loc_180052116
0x180051eaa  mov     [rsp+130h+cSubKeys], edi
0x180051eae  mov     [rsp+130h+cbMaxSubKeyLen], edi
0x180051eb2  mov     [rsp+130h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180051eb7  mov     [rsp+130h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180051ebc  mov     [rsp+130h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x180051ec1  mov     [rsp+130h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x180051ec6  mov     [rsp+130h+lpcValues], rdi; lpcValues
0x180051ecb  mov     [rsp+130h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x180051ed0  lea     rax, [rsp+130h+cbMaxSubKeyLen]
0x180051ed5  mov     [rsp+130h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180051eda  lea     rax, [rsp+130h+cSubKeys]
0x180051edf  mov     [rsp+130h+phkResult], rax; int
0x180051ee4  xor     r9d, r9d; lpReserved
0x180051ee7  xor     r8d, r8d; lpcchClass
0x180051eea  xor     edx, edx; lpClass
0x180051eec  mov     rcx, [rsp+130h+hKey]; hKey
0x180051ef1  call    cs:__imp_RegQueryInfoKeyW
0x180051ef7  test    eax, eax
0x180051ef9  jle     short loc_180051F03
0x180051efb  movzx   eax, ax
0x180051efe  or      eax, 80070000h
0x180051f03  mov     rcx, [rbp+38h]; this
0x180051f07  test    eax, eax
0x180051f09  jns     short loc_180051F20
0x180051f0b  mov     r9d, eax; char *
0x180051f0e  lea     r8, aOnecoreInterna_2; "onecore\\internal\\base\\inc\\appcompat"...
0x180051f15  mov     edx, 58Eh; void *
0x180051f1a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180051f20  mov     ebx, edi
0x180051f22  cmp     [rsp+130h+cSubKeys], edi
0x180051f26  jbe     loc_180052116
0x180051f2c  mov     eax, [rsp+130h+cbMaxSubKeyLen]
0x180051f30  inc     eax
0x180051f32  mov     [rsp+130h+cchName], eax
0x180051f36  mov     edx, eax
0x180051f38  lea     rcx, [rbp+30h+lpName]
0x180051f3c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x180051f41  nop
0x180051f42  lea     r8, [rbp+30h+lpName]
0x180051f46  cmp     [rbp+30h+var_70], 7
0x180051f4b  cmova   r8, [rbp+30h+lpName]; lpName
0x180051f50  mov     [rsp+130h+lpcValues], rdi; lpftLastWriteTime
0x180051f55  mov     [rsp+130h+lpcbMaxClassLen], rdi; lpcchClass
0x180051f5a  mov     [rsp+130h+lpcbMaxSubKeyLen], rdi; lpClass
0x180051f5f  mov     [rsp+130h+phkResult], rdi; int
0x180051f64  lea     r9, [rsp+130h+cchName]; lpcchName
0x180051f69  mov     edx, ebx; dwIndex
0x180051f6b  mov     rcx, [rsp+130h+hKey]; hKey
0x180051f70  call    cs:__imp_RegEnumKeyExW
0x180051f76  mov     rcx, [rbp+38h]; this
0x180051f7a  test    eax, eax
0x180051f7c  js      loc_18005215A
0x180051f82  mov     edx, [rsp+130h+cchName]
0x180051f86  lea     rcx, [rbp+30h+lpName]
0x180051f8a  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180051f8f  lea     rdx, ?ProfileImagePath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::ProfileImagePath
0x180051f96  cmp     cs:qword_1801831F8, 7
0x180051f9e  cmova   rdx, cs:?ProfileImagePath@Utility@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@A; std::wstring Utility::ProfileImagePath
0x180051fa6  lea     rcx, [rbp+30h+var_48]
0x180051faa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180051faf  nop
0x180051fb0  lea     rdx, [rbp+30h+lpName]
0x180051fb4  cmp     [rbp+30h+var_70], 7
0x180051fb9  cmova   rdx, [rbp+30h+lpName]
0x180051fbe  lea     rcx, [rbp+30h+var_68]
0x180051fc2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180051fc7  nop
0x180051fc8  lea     r9, [rbp+30h+var_48]
0x180051fcc  lea     r8, [rbp+30h+var_68]
0x180051fd0  mov     rdx, [rsp+130h+hKey]
0x180051fd5  lea     rcx, [rbp+30h+var_A8]
0x180051fd9  call    ?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z; Utility::GetRegValueString(HKEY__ * const,std::wstring const &,std::wstring const &,bool)
0x180051fde  nop
0x180051fdf  lea     rcx, [rbp+30h+var_68]
0x180051fe3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051fe8  nop
0x180051fe9  lea     rcx, [rbp+30h+var_48]
0x180051fed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180051ff2  lea     rdx, [rbp+30h+var_A8]
0x180051ff6  lea     rcx, [rbp+30h+var_28]
0x180051ffa  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x180051fff  mov     rdx, rax
0x180052002  lea     rcx, [rbp+30h+var_A8]
0x180052006  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005200b  lea     rcx, [rbp+30h+var_28]
0x18005200f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052014  cmp     [rbp+30h+var_98], 9
0x180052019  jb      loc_1800520F7
0x18005201f  lea     rcx, [rbp+30h+var_A8]
0x180052023  cmp     [rbp+30h+var_90], 7
0x180052028  cmova   rcx, [rbp+30h+var_A8]
0x18005202d  movzx   ecx, word ptr [rcx]
0x180052030  call    cs:__imp__o_iswalpha
0x180052036  test    eax, eax
0x180052038  jz      loc_1800520F7
0x18005203e  mov     rcx, [rbp+30h+var_90]
0x180052042  lea     rax, [rbp+30h+var_A8]
0x180052046  mov     rdx, [rbp+30h+var_A8]
0x18005204a  cmp     rcx, 7
0x18005204e  cmova   rax, rdx
0x180052052  cmp     word ptr [rax+2], 3Ah ; ':'
0x180052057  jnz     loc_1800520F7
0x18005205d  lea     rax, [rbp+30h+var_A8]
0x180052061  cmp     rcx, 7
0x180052065  cmova   rax, rdx
0x180052069  cmp     word ptr [rax+4], 5Ch ; '\'
0x18005206e  jnz     loc_1800520F7
0x180052074  lea     rax, [rbp+30h+var_A8]
0x180052078  cmp     rcx, 7
0x18005207c  cmova   rax, rdx
0x180052080  cmp     word ptr [rax+6], 75h ; 'u'
0x180052085  jnz     short loc_1800520F7
0x180052087  lea     rax, [rbp+30h+var_A8]
0x18005208b  cmp     rcx, 7
0x18005208f  cmova   rax, rdx
0x180052093  cmp     word ptr [rax+8], 73h ; 's'
0x180052098  jnz     short loc_1800520F7
0x18005209a  lea     rax, [rbp+30h+var_A8]
0x18005209e  cmp     rcx, 7
0x1800520a2  cmova   rax, rdx
0x1800520a6  cmp     word ptr [rax+0Ah], 65h ; 'e'
0x1800520ab  jnz     short loc_1800520F7
0x1800520ad  lea     rax, [rbp+30h+var_A8]
0x1800520b1  cmp     rcx, 7
0x1800520b5  cmova   rax, rdx
0x1800520b9  cmp     word ptr [rax+0Ch], 72h ; 'r'
0x1800520be  jnz     short loc_1800520F7
0x1800520c0  lea     rax, [rbp+30h+var_A8]
0x1800520c4  cmp     rcx, 7
0x1800520c8  cmova   rax, rdx
0x1800520cc  cmp     word ptr [rax+0Eh], 73h ; 's'
0x1800520d1  jnz     short loc_1800520F7
0x1800520d3  lea     rax, [rbp+30h+var_A8]
0x1800520d7  cmp     rcx, 7
0x1800520db  cmova   rax, rdx
0x1800520df  cmp     word ptr [rax+10h], 5Ch ; '\'
0x1800520e4  jnz     short loc_1800520F7
0x1800520e6  lea     rdx, [rbp+30h+var_A8]
0x1800520ea  lea     rcx, qword_180184210
0x1800520f1  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x1800520f6  nop
0x1800520f7  lea     rcx, [rbp+30h+var_A8]
0x1800520fb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052100  nop
0x180052101  lea     rcx, [rbp+30h+lpName]
0x180052105  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005210a  inc     ebx
0x18005210c  cmp     ebx, [rsp+130h+cSubKeys]
0x180052110  jb      loc_180051F2C
0x180052116  mov     cs:byte_1801817E5, dil
0x18005211d  lea     rcx, [rsp+130h+hKey]
0x180052122  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180052127  nop
0x180052128  lea     rcx, [rsp+130h+var_B8]
0x18005212d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180052132  lea     rax, qword_180184210
0x180052139  mov     rcx, [rbp+30h+var_8]
0x18005213d  xor     rcx, rsp; StackCookie
0x180052140  call    __security_check_cookie
0x180052145  lea     r11, [rsp+130h+var_s0]
0x18005214d  mov     rbx, [r11+10h]
0x180052151  mov     rdi, [r11+18h]
0x180052155  mov     rsp, r11
0x180052158  pop     rbp
0x180052159  retn
0x18005215a  mov     r9d, eax; char *
0x18005215d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\base\\inc\\appcompat"...
0x180052164  mov     edx, 59Ch; void *
0x180052169  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
