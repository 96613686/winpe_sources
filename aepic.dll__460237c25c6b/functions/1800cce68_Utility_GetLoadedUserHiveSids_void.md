# Utility::GetLoadedUserHiveSids(void)

- ea: `0x1800cce68`
- end: `0x1800cd0ef`
- name: `?GetLoadedUserHiveSids@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `647`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001f378`

## callees

- `0x180005890`
- `0x180005d10`
- `0x180005ec0`
- `0x180005f28`
- `0x180008570`
- `0x18000faac`
- `0x18001c5f0`
- `0x18001de0c`
- `0x18001df50`
- `0x18002248c`
- `0x1800c31cc`
- `0x1800c97f0`
- `0x1800c993c`
- `0x1800ca464`
- `0x1800caa40`
- `0x1800cce68`
- `0x1800d00c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ccf05`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800ccf05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ccf2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ccf2e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ccffc`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ccffc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ccf80`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800ccf80`

## string_xrefs

- `0x1800ccf9d`: `onecore\base\appcompat\inventory\software\inv\lib\utility.cpp`
- `0x1800cd0dd`: `onecore\base\appcompat\inventory\software\inv\lib\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 *Utility::GetLoadedUserHiveSids()
{
  __int64 v0; // rcx
  __int64 AllUserSids; // rax
  int v2; // eax
  DWORD i; // edi
  WCHAR *v4; // r8
  LSTATUS v5; // eax
  __int64 v6; // rbx
  __int64 v7; // rsi
  _QWORD *v8; // r8
  LPWSTR *v9; // rcx
  int phkResult; // [rsp+20h] [rbp-89h]
  int phkResulta; // [rsp+20h] [rbp-89h]
  DWORD cSubKeys; // [rsp+60h] [rbp-49h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+64h] [rbp-45h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-39h] BYREF
  RTL_SRWLOCK *v17; // [rsp+78h] [rbp-31h] BYREF
  _QWORD v18[3]; // [rsp+80h] [rbp-29h] BYREF
  LPWSTR lpName[3]; // [rsp+98h] [rbp-11h] BYREF
  unsigned __int64 v20; // [rsp+B0h] [rbp+7h]
  _QWORD v21[4]; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v0 = (unsigned int)tls_index;
  if ( dword_180122E00 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180122E00);
    if ( dword_180122E00 == -1 )
    {
      atexit(Utility::GetLoadedUserHiveSids_::_2_::_dynamic_atexit_destructor_for__loadedUserHiveSids__);
      Init_thread_footer(&dword_180122E00);
    }
  }
  if ( !byte_180122B78 )
  {
    AllUserSids = Utility::GetAllUserSids(v0);
    std::vector<std::wstring>::vector<std::wstring>(v18, AllUserSids);
    AcquireSRWLockExclusive(&stru_180122B80);
    v17 = &stru_180122B80;
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_USERS, 0, 0, 0x20019u, &hKey) )
    {
      cSubKeys = 0;
      cbMaxSubKeyLen = 0;
      v2 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
      if ( v2 > 0 )
        v2 = (unsigned __int16)v2 | 0x80070000;
      if ( v2 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x2CC,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\utility.cpp",
          (const char *)(unsigned int)v2,
          phkResult);
      for ( i = 0; i < cSubKeys; ++i )
      {
        cchName = cbMaxSubKeyLen + 1;
        std::wstring::wstring(lpName, cbMaxSubKeyLen + 1);
        v4 = (WCHAR *)lpName;
        if ( v20 > 7 )
          v4 = lpName[0];
        v5 = RegEnumKeyExW(hKey, i, v4, &cchName, 0, 0, 0, 0);
        if ( v5 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x2DA,
            (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\utility.cpp",
            (const char *)(unsigned int)v5,
            phkResulta);
        std::wstring::resize(lpName, cchName);
        v6 = v18[0];
        v7 = v18[1];
        while ( v6 != v7 )
        {
          std::wstring::wstring(v21, v6);
          v8 = v21;
          if ( v21[3] > 7u )
            v8 = (_QWORD *)v21[0];
          v9 = lpName;
          if ( v20 > 7 )
            v9 = (LPWSTR *)lpName[0];
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v9, lpName[2], v8, v21[2]) )
            std::vector<std::wstring>::push_back(qword_180122E08, lpName);
          std::wstring::_Tidy_deallocate(v21);
          v6 += 32;
        }
        std::wstring::_Tidy_deallocate(lpName);
      }
    }
    byte_180122B78 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
    std::vector<std::wstring>::_Tidy(v18);
  }
  return qword_180122E08;
}

```

## disassembly

```asm
0x1800cce68  push    rbp
0x1800cce6a  push    rbx
0x1800cce6b  push    rsi
0x1800cce6c  push    rdi
0x1800cce6d  push    r14
0x1800cce6f  lea     rbp, [rsp-37h]
0x1800cce74  sub     rsp, 0E0h
0x1800cce7b  mov     rax, cs:__security_cookie
0x1800cce82  xor     rax, rsp
0x1800cce85  mov     [rbp+57h+var_28], rax
0x1800cce89  mov     ecx, cs:_tls_index
0x1800cce8f  mov     rax, gs:58h
0x1800cce98  mov     edx, 4
0x1800cce9d  mov     rax, [rax+rcx*8]
0x1800ccea1  mov     eax, [rdx+rax]
0x1800ccea4  cmp     cs:dword_180122E00, eax
0x1800cceaa  jle     short loc_1800CCED9
0x1800cceac  lea     rcx, dword_180122E00
0x1800cceb3  call    _Init_thread_header
0x1800cceb8  cmp     cs:dword_180122E00, 0FFFFFFFFh
0x1800ccebf  jnz     short loc_1800CCED9
0x1800ccec1  lea     rcx, _Utility__GetLoadedUserHiveSids____2____dynamic_atexit_destructor_for__loadedUserHiveSids__; void (__cdecl *)()
0x1800ccec8  call    atexit
0x1800ccecd  lea     rcx, dword_180122E00
0x1800cced4  call    _Init_thread_footer
0x1800cced9  xor     r14d, r14d
0x1800ccedc  cmp     cs:byte_180122B78, r14b
0x1800ccee3  jnz     loc_1800CD0B9
0x1800ccee9  call    ?GetAllUserSids@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_N@Z; Utility::GetAllUserSids(bool)
0x1800cceee  mov     rdx, rax
0x1800ccef1  lea     rcx, [rbp+57h+var_80]
0x1800ccef5  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x1800ccefa  nop
0x1800ccefb  lea     rbx, stru_180122B80
0x1800ccf02  mov     rcx, rbx; SRWLock
0x1800ccf05  call    cs:__imp_AcquireSRWLockExclusive
0x1800ccf0b  mov     [rbp+57h+var_88], rbx
0x1800ccf0f  mov     [rbp+57h+hKey], r14
0x1800ccf13  lea     rax, [rbp+57h+hKey]
0x1800ccf17  mov     [rsp+100h+phkResult], rax; phkResult
0x1800ccf1c  mov     r9d, 20019h; samDesired
0x1800ccf22  xor     r8d, r8d; ulOptions
0x1800ccf25  xor     edx, edx; lpSubKey
0x1800ccf27  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800ccf2e  call    cs:__imp_RegOpenKeyExW
0x1800ccf34  test    eax, eax
0x1800ccf36  jnz     loc_1800CD095
0x1800ccf3c  mov     [rbp+57h+cSubKeys], r14d
0x1800ccf40  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x1800ccf44  mov     [rsp+100h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800ccf49  mov     [rsp+100h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800ccf4e  mov     [rsp+100h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800ccf53  mov     [rsp+100h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800ccf58  mov     [rsp+100h+lpcValues], r14; lpcValues
0x1800ccf5d  mov     [rsp+100h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800ccf62  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1800ccf66  mov     [rsp+100h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800ccf6b  lea     rax, [rbp+57h+cSubKeys]
0x1800ccf6f  mov     [rsp+100h+phkResult], rax; int
0x1800ccf74  xor     r9d, r9d; lpReserved
0x1800ccf77  xor     r8d, r8d; lpcchClass
0x1800ccf7a  xor     edx, edx; lpClass
0x1800ccf7c  mov     rcx, [rbp+57h+hKey]; hKey
0x1800ccf80  call    cs:__imp_RegQueryInfoKeyW
0x1800ccf86  test    eax, eax
0x1800ccf88  jle     short loc_1800CCF92
0x1800ccf8a  movzx   eax, ax
0x1800ccf8d  or      eax, 80070000h
0x1800ccf92  mov     rcx, [rbp+5Fh]; this
0x1800ccf96  test    eax, eax
0x1800ccf98  jns     short loc_1800CCFAF
0x1800ccf9a  mov     r9d, eax; char *
0x1800ccf9d  lea     r8, aOnecoreBaseApp; "onecore\\base\\appcompat\\inventory\\so"...
0x1800ccfa4  mov     edx, 2CCh; void *
0x1800ccfa9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800ccfaf  mov     edi, r14d
0x1800ccfb2  cmp     [rbp+57h+cSubKeys], r14d
0x1800ccfb6  jbe     loc_1800CD095
0x1800ccfbc  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1800ccfbf  inc     eax
0x1800ccfc1  mov     [rbp+57h+cchName], eax
0x1800ccfc4  mov     edx, eax
0x1800ccfc6  lea     rcx, [rbp+57h+lpName]
0x1800ccfca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1800ccfcf  nop
0x1800ccfd0  lea     r8, [rbp+57h+lpName]
0x1800ccfd4  cmp     [rbp+57h+var_50], 7
0x1800ccfd9  cmova   r8, [rbp+57h+lpName]; lpName
0x1800ccfde  mov     [rsp+100h+lpcValues], r14; lpftLastWriteTime
0x1800ccfe3  mov     [rsp+100h+lpcbMaxClassLen], r14; lpcchClass
0x1800ccfe8  mov     [rsp+100h+lpcbMaxSubKeyLen], r14; lpClass
0x1800ccfed  mov     [rsp+100h+phkResult], r14; int
0x1800ccff2  lea     r9, [rbp+57h+cchName]; lpcchName
0x1800ccff6  mov     edx, edi; dwIndex
0x1800ccff8  mov     rcx, [rbp+57h+hKey]; hKey
0x1800ccffc  call    cs:__imp_RegEnumKeyExW
0x1800cd002  mov     rcx, [rbp+5Fh]; this
0x1800cd006  test    eax, eax
0x1800cd008  js      loc_1800CD0DA
0x1800cd00e  mov     edx, [rbp+57h+cchName]
0x1800cd011  lea     rcx, [rbp+57h+lpName]
0x1800cd015  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800cd01a  mov     rbx, [rbp+57h+var_80]
0x1800cd01e  mov     rsi, [rbp+57h+var_78]
0x1800cd022  jmp     short loc_1800CD07C
0x1800cd024  mov     rdx, rbx
0x1800cd027  lea     rcx, [rbp+57h+var_48]
0x1800cd02b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800cd030  nop
0x1800cd031  lea     r8, [rbp+57h+var_48]
0x1800cd035  cmp     [rbp+57h+var_30], 7
0x1800cd03a  cmova   r8, [rbp+57h+var_48]
0x1800cd03f  lea     rcx, [rbp+57h+lpName]
0x1800cd043  cmp     [rbp+57h+var_50], 7
0x1800cd048  cmova   rcx, [rbp+57h+lpName]
0x1800cd04d  mov     r9, [rbp+57h+var_38]
0x1800cd051  mov     rdx, [rbp+57h+var_58]
0x1800cd055  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800cd05a  test    al, al
0x1800cd05c  jz      short loc_1800CD06F
0x1800cd05e  lea     rdx, [rbp+57h+lpName]
0x1800cd062  lea     rcx, qword_180122E08
0x1800cd069  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cd06e  nop
0x1800cd06f  lea     rcx, [rbp+57h+var_48]
0x1800cd073  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd078  add     rbx, 20h ; ' '
0x1800cd07c  cmp     rbx, rsi
0x1800cd07f  jnz     short loc_1800CD024
0x1800cd081  lea     rcx, [rbp+57h+lpName]
0x1800cd085  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd08a  inc     edi
0x1800cd08c  cmp     edi, [rbp+57h+cSubKeys]
0x1800cd08f  jb      loc_1800CCFBC
0x1800cd095  mov     cs:byte_180122B78, r14b
0x1800cd09c  lea     rcx, [rbp+57h+hKey]
0x1800cd0a0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cd0a5  nop
0x1800cd0a6  lea     rcx, [rbp+57h+var_88]
0x1800cd0aa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800cd0af  nop
0x1800cd0b0  lea     rcx, [rbp+57h+var_80]
0x1800cd0b4  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800cd0b9  lea     rax, qword_180122E08
0x1800cd0c0  mov     rcx, [rbp+57h+var_28]
0x1800cd0c4  xor     rcx, rsp; StackCookie
0x1800cd0c7  call    __security_check_cookie
0x1800cd0cc  add     rsp, 0E0h
0x1800cd0d3  pop     r14
0x1800cd0d5  pop     rdi
0x1800cd0d6  pop     rsi
0x1800cd0d7  pop     rbx
0x1800cd0d8  pop     rbp
0x1800cd0d9  retn
0x1800cd0da  mov     r9d, eax; char *
0x1800cd0dd  lea     r8, aOnecoreBaseApp; "onecore\\base\\appcompat\\inventory\\so"...
0x1800cd0e4  mov     edx, 2DAh; void *
0x1800cd0e9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
