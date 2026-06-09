# File::GetFilesFromCache(TelCacheProvider *)

- ea: `0x180012ba0`
- end: `0x180013015`
- name: `?GetFilesFromCache@File@@SA?AV?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@PEAVTelCacheProvider@@@Z`
- size: `1141`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001282c`
- `0x18003a050`
- `0x180052fc8`
- `0x1800fbd50`

## callees

- `0x18000ecac`
- `0x18000f700`
- `0x18000f8ec`
- `0x180012ba0`
- `0x1800188f4`
- `0x1800197d4`
- `0x1800218c0`
- `0x18002ff68`
- `0x18003fb20`
- `0x180040254`
- `0x180043598`
- `0x18004869c`
- `0x1800531ac`
- `0x1800568f8`
- `0x180059920`
- `0x180059cd0`
- `0x180059f2c`
- `0x180059f94`
- `0x1800679f8`
- `0x1800f863c`
- `0x1800f8b94`
- `0x1801003f4`
- `0x180100630`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x180012c5b`
- `KERNEL32!AcquireSRWLockShared` at `0x180012c5b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180012cbb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180012e26`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180012cbb`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180012e26`

## string_xrefs

- `0x180012f91`: `onecore\internal\base\inc\appcompat\inventory\file.cpp`
- `0x180012fd9`: `onecore\internal\base\inc\appcompat\inventory\file.cpp`
- `0x180012fee`: `onecore\internal\base\inc\appcompat\inventory\file.cpp`
- `0x180013003`: `onecore\internal\base\inc\appcompat\inventory\file.cpp`
- `0x180012d12`: `File::GetFilesFromCache`
- `0x180012e7d`: `File::GetFilesFromCache`
- `0x180012d05`: `Cache file count changed - refreshing file list.`
- `0x180012e70`: `Cache file count changed - refreshing file list.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
RTL_SRWLOCK *__fastcall File::GetFilesFromCache(RTL_SRWLOCK *a1, TelCacheProvider *a2, __int64 a3, const char *a4)
{
  int ItemCount; // eax
  int v7; // eax
  int i; // eax
  int v9; // eax
  int j; // eax
  unsigned int v12[2]; // [rsp+28h] [rbp-E0h] BYREF
  RTL_SRWLOCK *v13; // [rsp+30h] [rbp-D8h] BYREF
  _BYTE v14[24]; // [rsp+38h] [rbp-D0h] BYREF
  char v15[8]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+58h] [rbp-B0h]
  __int64 v17; // [rsp+60h] [rbp-A8h]
  char v18[8]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v19[48]; // [rsp+70h] [rbp-98h] BYREF
  char v20[760]; // [rsp+A0h] [rbp-68h] BYREF
  char v21[8]; // [rsp+398h] [rbp+290h] BYREF
  _BYTE v22[48]; // [rsp+3A0h] [rbp+298h] BYREF
  char v23[760]; // [rsp+3D0h] [rbp+2C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6F0h] [rbp+5E8h]

  v17 = -2;
  v13 = a1;
  v12[0] = 0;
  if ( dword_1801840E0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1801840E0);
    if ( dword_1801840E0 == -1 )
    {
      atexit(File::GetFilesFromCache_::_2_::_dynamic_atexit_destructor_for__cacheFiles__);
      Init_thread_footer(&dword_1801840E0);
    }
  }
  if ( !a2 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x632,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\file.cpp",
      a4);
  ItemCount = TelCacheProvider::GetItemCount(a2, v12);
  if ( ItemCount < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x634,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\file.cpp",
      (const char *)(unsigned int)ItemCount,
      v12[0]);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV>::GetImpl'::`2'::impl) )
  {
    AcquireSRWLockShared(&SRWLock);
    v13 = &SRWLock;
    if ( v12[0] == 0xFAFAFAFAFAFAFAFBuLL * (((__int64)qword_1801840F0 - qword_1801840E8) >> 4) )
    {
      std::vector<File>::vector<File>(a1, &qword_1801840E8);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
      AcquireSRWLockExclusive(&SRWLock);
      v13 = &SRWLock;
      v7 = TelCacheProvider::GetItemCount(a2, v12);
      if ( v7 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x649,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\file.cpp",
          (const char *)(unsigned int)v7,
          v12[0]);
      if ( v12[0] != 0xFAFAFAFAFAFAFAFBuLL * (((__int64)qword_1801840F0 - qword_1801840E8) >> 4) )
      {
        AslLogCallPrintf(
          3,
          (unsigned int)"File::GetFilesFromCache",
          1613,
          (unsigned int)"Cache file count changed - refreshing file list.");
        std::set<std::wstring>::set<std::wstring>(v14);
        File::File((File *)v18);
        std::vector<File>::clear();
        for ( i = TelCacheProvider::GetFirstItem(a2, (struct IAmiInventoryItem *)v19);
              i >= 0;
              i = TelCacheProvider::GetNextItem(a2, (struct IAmiInventoryItem *)v19) )
        {
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
            v14,
            v15,
            v20);
          if ( (_BYTE)v16 )
          {
            if ( qword_1801840F0 == (File *)qword_1801840F8 )
            {
              std::vector<File>::_Emplace_reallocate<File const &>(&qword_1801840E8, qword_1801840F0, v18);
            }
            else
            {
              File::File(qword_1801840F0, (const struct File *)v18);
              qword_1801840F0 = (File *)((char *)qword_1801840F0 + 816);
            }
          }
        }
        File::~File((File *)v18);
        std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
          v14,
          v14);
      }
      std::vector<File>::vector<File>(a1, &qword_1801840E8);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
    }
  }
  else
  {
    if ( v12[0] != 0xFAFAFAFAFAFAFAFBuLL * (((__int64)qword_1801840F0 - qword_1801840E8) >> 4) )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v13 = &SRWLock;
      v9 = TelCacheProvider::GetItemCount(a2, v12);
      if ( v9 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x66D,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\file.cpp",
          (const char *)(unsigned int)v9,
          v12[0]);
      if ( v12[0] != 0xFAFAFAFAFAFAFAFBuLL * (((__int64)qword_1801840F0 - qword_1801840E8) >> 4) )
      {
        AslLogCallPrintf(
          3,
          (unsigned int)"File::GetFilesFromCache",
          1649,
          (unsigned int)"Cache file count changed - refreshing file list.");
        std::set<std::wstring>::set<std::wstring>(v14);
        File::File((File *)v21);
        std::vector<File>::clear();
        for ( j = TelCacheProvider::GetFirstItem(a2, (struct IAmiInventoryItem *)v22);
              j >= 0;
              j = TelCacheProvider::GetNextItem(a2, (struct IAmiInventoryItem *)v22) )
        {
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
            v14,
            v15,
            v23);
          if ( (_BYTE)v16 )
          {
            if ( qword_1801840F0 == (File *)qword_1801840F8 )
            {
              std::vector<File>::_Emplace_reallocate<File const &>(&qword_1801840E8, qword_1801840F0, v21);
            }
            else
            {
              File::File(qword_1801840F0, (const struct File *)v21);
              qword_1801840F0 = (File *)((char *)qword_1801840F0 + 816);
            }
          }
        }
        File::~File((File *)v21);
        std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
          v14,
          v14);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
    }
    std::vector<File>::vector<File>(a1, &qword_1801840E8);
  }
  return a1;
}

```

## disassembly

```asm
0x180012ba0  mov     rax, rsp
0x180012ba3  push    rbp
0x180012ba4  push    rdi
0x180012ba5  push    r14
0x180012ba7  lea     rbp, [rax-5E8h]
0x180012bae  sub     rsp, 6D0h
0x180012bb5  mov     [rsp+6E0h+var_688], 0FFFFFFFFFFFFFFFEh
0x180012bbe  mov     [rax+18h], rbx
0x180012bc2  mov     [rax+20h], rsi
0x180012bc6  mov     rax, cs:__security_cookie
0x180012bcd  xor     rax, rsp
0x180012bd0  mov     [rbp+5E0h+var_20], rax
0x180012bd7  mov     rsi, rdx
0x180012bda  mov     rbx, rcx
0x180012bdd  mov     [rsp+6E0h+var_6B8], rcx
0x180012be2  mov     [rsp+6E0h+var_6C0], 0; int
0x180012bea  mov     ecx, cs:_tls_index
0x180012bf0  mov     rax, gs:58h
0x180012bf9  mov     edx, 4
0x180012bfe  mov     rax, [rax+rcx*8]
0x180012c02  mov     ecx, [rdx+rax]
0x180012c05  cmp     cs:dword_1801840E0, ecx
0x180012c0b  jg      loc_180012FA3
0x180012c11  mov     rcx, [rbp+5E8h]; this
0x180012c18  test    rsi, rsi
0x180012c1b  jz      loc_180012FD9
0x180012c21  lea     rdx, [rsp+6E0h+var_6C0]; unsigned int *
0x180012c26  mov     rcx, rsi; this
0x180012c29  call    ?GetItemCount@TelCacheProvider@@QEAAJAEAK@Z; TelCacheProvider::GetItemCount(ulong &)
0x180012c2e  mov     rcx, [rbp+5E8h]; this
0x180012c35  test    eax, eax
0x180012c37  js      loc_180012FEB
0x180012c3d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV> `wil::Feature<__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV>::GetImpl(void)'::`2'::impl
0x180012c44  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV>::__private_IsEnabled(void)
0x180012c49  test    al, al
0x180012c4b  jz      loc_180012DEF
0x180012c51  lea     rdi, SRWLock
0x180012c58  mov     rcx, rdi; SRWLock
0x180012c5b  call    cs:__imp_AcquireSRWLockShared
0x180012c61  mov     [rsp+6E0h+var_6B8], rdi
0x180012c66  mov     rdx, cs:qword_1801840F0
0x180012c6d  sub     rdx, cs:qword_1801840E8
0x180012c74  sar     rdx, 4
0x180012c78  mov     r14, 0FAFAFAFAFAFAFAFBh
0x180012c82  imul    rdx, r14
0x180012c86  mov     ecx, [rsp+6E0h+var_6C0]
0x180012c8a  cmp     rcx, rdx
0x180012c8d  jnz     short loc_180012CAE
0x180012c8f  lea     rdx, qword_1801840E8
0x180012c96  mov     rcx, rbx
0x180012c99  call    ??0?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<File>::vector<File>(std::vector<File> const &)
0x180012c9e  nop
0x180012c9f  lea     rcx, [rsp+6E0h+var_6B8]
0x180012ca4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012ca9  jmp     loc_180012F64
0x180012cae  lea     rcx, [rsp+6E0h+var_6B8]
0x180012cb3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012cb8  mov     rcx, rdi; SRWLock
0x180012cbb  call    cs:__imp_AcquireSRWLockExclusive
0x180012cc1  mov     [rsp+6E0h+var_6B8], rdi
0x180012cc6  lea     rdx, [rsp+6E0h+var_6C0]; unsigned int *
0x180012ccb  mov     rcx, rsi; this
0x180012cce  call    ?GetItemCount@TelCacheProvider@@QEAAJAEAK@Z; TelCacheProvider::GetItemCount(ulong &)
0x180012cd3  mov     rcx, [rbp+5E8h]; this
0x180012cda  test    eax, eax
0x180012cdc  js      loc_180013000
0x180012ce2  mov     rcx, cs:qword_1801840F0
0x180012ce9  sub     rcx, cs:qword_1801840E8
0x180012cf0  sar     rcx, 4
0x180012cf4  imul    rcx, r14
0x180012cf8  mov     eax, [rsp+6E0h+var_6C0]
0x180012cfc  cmp     rax, rcx
0x180012cff  jz      loc_180012DD0
0x180012d05  lea     r9, aCacheFileCount; "Cache file count changed - refreshing f"...
0x180012d0c  mov     r8d, 64Dh
0x180012d12  lea     rdx, aFileGetfilesfr; "File::GetFilesFromCache"
0x180012d19  mov     ecx, 3
0x180012d1e  call    AslLogCallPrintf
0x180012d23  lea     rcx, [rsp+6E0h+var_6B0]
0x180012d28  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180012d2d  nop
0x180012d2e  lea     rcx, [rsp+6E0h+var_680]; this
0x180012d33  call    ??0File@@QEAA@XZ; File::File(void)
0x180012d38  nop
0x180012d39  call    ?clear@?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAAXXZ; std::vector<File>::clear(void)
0x180012d3e  lea     rdx, [rsp+6E0h+var_678]; struct IAmiInventoryItem *
0x180012d43  mov     rcx, rsi; this
0x180012d46  call    ?GetFirstItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetFirstItem(IAmiInventoryItem *)
0x180012d4b  jmp     short loc_180012DB2
0x180012d4d  lea     r8, [rbp+5E0h+var_648]
0x180012d51  lea     rdx, [rsp+6E0h+var_698]
0x180012d56  lea     rcx, [rsp+6E0h+var_6B0]
0x180012d5b  call    ??$emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(std::wstring const &)
0x180012d60  cmp     byte ptr [rsp+6E0h+var_690], 0
0x180012d65  jz      short loc_180012DA5
0x180012d67  mov     rax, cs:qword_1801840F0
0x180012d6e  cmp     rax, cs:qword_1801840F8
0x180012d75  jz      short loc_180012D91
0x180012d77  lea     rdx, [rsp+6E0h+var_680]; struct File *
0x180012d7c  mov     rcx, rax; this
0x180012d7f  call    ??0File@@QEAA@AEBV0@@Z; File::File(File const &)
0x180012d84  add     cs:qword_1801840F0, 330h
0x180012d8f  jmp     short loc_180012DA5
0x180012d91  lea     r8, [rsp+6E0h+var_680]
0x180012d96  mov     rdx, rax
0x180012d99  lea     rcx, qword_1801840E8
0x180012da0  call    ??$_Emplace_reallocate@AEBVFile@@@?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@AEAAPEAVFile@@QEAV2@AEBV2@@Z; std::vector<File>::_Emplace_reallocate<File const &>(File * const,File const &)
0x180012da5  lea     rdx, [rsp+6E0h+var_678]; struct IAmiInventoryItem *
0x180012daa  mov     rcx, rsi; this
0x180012dad  call    ?GetNextItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetNextItem(IAmiInventoryItem *)
0x180012db2  test    eax, eax
0x180012db4  jns     short loc_180012D4D
0x180012db6  lea     rcx, [rsp+6E0h+var_680]; this
0x180012dbb  call    ??1File@@UEAA@XZ; File::~File(void)
0x180012dc0  nop
0x180012dc1  lea     rdx, [rsp+6E0h+var_6B0]
0x180012dc6  lea     rcx, [rsp+6E0h+var_6B0]
0x180012dcb  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &)
0x180012dd0  lea     rdx, qword_1801840E8
0x180012dd7  mov     rcx, rbx
0x180012dda  call    ??0?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<File>::vector<File>(std::vector<File> const &)
0x180012ddf  nop
0x180012de0  lea     rcx, [rsp+6E0h+var_6B8]
0x180012de5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012dea  jmp     loc_180012F64
0x180012def  mov     rcx, cs:qword_1801840F0
0x180012df6  sub     rcx, cs:qword_1801840E8
0x180012dfd  sar     rcx, 4
0x180012e01  mov     r14, 0FAFAFAFAFAFAFAFBh
0x180012e0b  imul    rcx, r14
0x180012e0f  mov     eax, [rsp+6E0h+var_6C0]
0x180012e13  cmp     rax, rcx
0x180012e16  jz      loc_180012F55
0x180012e1c  lea     rdi, SRWLock
0x180012e23  mov     rcx, rdi; SRWLock
0x180012e26  call    cs:__imp_AcquireSRWLockExclusive
0x180012e2c  mov     [rsp+6E0h+var_6B8], rdi
0x180012e31  lea     rdx, [rsp+6E0h+var_6C0]; unsigned int *
0x180012e36  mov     rcx, rsi; this
0x180012e39  call    ?GetItemCount@TelCacheProvider@@QEAAJAEAK@Z; TelCacheProvider::GetItemCount(ulong &)
0x180012e3e  mov     rcx, [rbp+5E8h]; this
0x180012e45  test    eax, eax
0x180012e47  js      loc_180012F8E
0x180012e4d  mov     rcx, cs:qword_1801840F0
0x180012e54  sub     rcx, cs:qword_1801840E8
0x180012e5b  sar     rcx, 4
0x180012e5f  imul    rcx, r14
0x180012e63  mov     eax, [rsp+6E0h+var_6C0]
0x180012e67  cmp     rax, rcx
0x180012e6a  jz      loc_180012F4B
0x180012e70  lea     r9, aCacheFileCount; "Cache file count changed - refreshing f"...
0x180012e77  mov     r8d, 671h
0x180012e7d  lea     rdx, aFileGetfilesfr; "File::GetFilesFromCache"
0x180012e84  mov     ecx, 3
0x180012e89  call    AslLogCallPrintf
0x180012e8e  lea     rcx, [rsp+6E0h+var_6B0]
0x180012e93  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180012e98  nop
0x180012e99  lea     rcx, [rbp+5E0h+var_350]; this
0x180012ea0  call    ??0File@@QEAA@XZ; File::File(void)
0x180012ea5  nop
0x180012ea6  call    ?clear@?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAAXXZ; std::vector<File>::clear(void)
0x180012eab  lea     rdx, [rbp+5E0h+var_348]; struct IAmiInventoryItem *
0x180012eb2  mov     rcx, rsi; this
0x180012eb5  call    ?GetFirstItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetFirstItem(IAmiInventoryItem *)
0x180012eba  jmp     short loc_180012F2A
0x180012ebc  lea     r8, [rbp+5E0h+var_318]
0x180012ec3  lea     rdx, [rsp+6E0h+var_698]
0x180012ec8  lea     rcx, [rsp+6E0h+var_6B0]
0x180012ecd  call    ??$emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(std::wstring const &)
0x180012ed2  cmp     byte ptr [rsp+6E0h+var_690], 0
0x180012ed7  jz      short loc_180012F1B
0x180012ed9  mov     rax, cs:qword_1801840F0
0x180012ee0  cmp     rax, cs:qword_1801840F8
0x180012ee7  jz      short loc_180012F05
0x180012ee9  lea     rdx, [rbp+5E0h+var_350]; struct File *
0x180012ef0  mov     rcx, rax; this
0x180012ef3  call    ??0File@@QEAA@AEBV0@@Z; File::File(File const &)
0x180012ef8  add     cs:qword_1801840F0, 330h
0x180012f03  jmp     short loc_180012F1B
0x180012f05  lea     r8, [rbp+5E0h+var_350]
0x180012f0c  mov     rdx, rax
0x180012f0f  lea     rcx, qword_1801840E8
0x180012f16  call    ??$_Emplace_reallocate@AEBVFile@@@?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@AEAAPEAVFile@@QEAV2@AEBV2@@Z; std::vector<File>::_Emplace_reallocate<File const &>(File * const,File const &)
0x180012f1b  lea     rdx, [rbp+5E0h+var_348]; struct IAmiInventoryItem *
0x180012f22  mov     rcx, rsi; this
0x180012f25  call    ?GetNextItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetNextItem(IAmiInventoryItem *)
0x180012f2a  test    eax, eax
0x180012f2c  jns     short loc_180012EBC
0x180012f2e  lea     rcx, [rbp+5E0h+var_350]; this
0x180012f35  call    ??1File@@UEAA@XZ; File::~File(void)
0x180012f3a  nop
0x180012f3b  lea     rdx, [rsp+6E0h+var_6B0]
0x180012f40  lea     rcx, [rsp+6E0h+var_6B0]
0x180012f45  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &)
0x180012f4a  nop
0x180012f4b  lea     rcx, [rsp+6E0h+var_6B8]
0x180012f50  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012f55  lea     rdx, qword_1801840E8
0x180012f5c  mov     rcx, rbx
0x180012f5f  call    ??0?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<File>::vector<File>(std::vector<File> const &)
0x180012f64  mov     rax, rbx
0x180012f67  mov     rcx, [rbp+5E0h+var_20]
0x180012f6e  xor     rcx, rsp; StackCookie
0x180012f71  call    __security_check_cookie
0x180012f76  lea     r11, [rsp+6E0h+var_10]
0x180012f7e  mov     rbx, [r11+30h]
0x180012f82  mov     rsi, [r11+38h]
0x180012f86  mov     rsp, r11
0x180012f89  pop     r14
0x180012f8b  pop     rdi
0x180012f8c  pop     rbp
0x180012f8d  retn
0x180012f8e  mov     r9d, eax; char *
0x180012f91  lea     r8, aOnecoreInterna_9; "onecore\\internal\\base\\inc\\appcompat"...
0x180012f98  mov     edx, 66Dh; void *
0x180012f9d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180012fa3  lea     rcx, dword_1801840E0
0x180012faa  call    _Init_thread_header
0x180012faf  cmp     cs:dword_1801840E0, 0FFFFFFFFh
0x180012fb6  jnz     loc_180012C11
0x180012fbc  lea     rcx, _File__GetFilesFromCache____2____dynamic_atexit_destructor_for__cacheFiles__; void (__cdecl *)()
0x180012fc3  call    atexit
0x180012fc8  lea     rcx, dword_1801840E0
0x180012fcf  call    _Init_thread_footer
0x180012fd4  jmp     loc_180012C11
0x180012fd9  lea     r8, aOnecoreInterna_9; "onecore\\internal\\base\\inc\\appcompat"...
0x180012fe0  mov     edx, 632h; void *
0x180012fe5  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180012feb  mov     r9d, eax; char *
0x180012fee  lea     r8, aOnecoreInterna_9; "onecore\\internal\\base\\inc\\appcompat"...
0x180012ff5  mov     edx, 634h; void *
0x180012ffa  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180013000  mov     r9d, eax; char *
0x180013003  lea     r8, aOnecoreInterna_9; "onecore\\internal\\base\\inc\\appcompat"...
0x18001300a  mov     edx, 649h; void *
0x18001300f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
