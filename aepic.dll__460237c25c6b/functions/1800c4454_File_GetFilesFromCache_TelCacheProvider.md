# File::GetFilesFromCache(TelCacheProvider *)

- ea: `0x1800c4454`
- end: `0x1800c48ab`
- name: `?GetFilesFromCache@File@@SA?AV?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@PEAVTelCacheProvider@@@Z`
- size: `1111`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c43c0`
- `0x1800c48b4`

## callees

- `0x180005890`
- `0x180005d10`
- `0x180005ec0`
- `0x180005f28`
- `0x180008570`
- `0x180008590`
- `0x18001daec`
- `0x18001deb4`
- `0x18001df20`
- `0x1800211ec`
- `0x18002135c`
- `0x1800213c0`
- `0x1800295dc`
- `0x1800c1da0`
- `0x1800c23b0`
- `0x1800c2404`
- `0x1800c2d74`
- `0x1800c3280`
- `0x1800c4454`
- `0x1800c97f0`
- `0x1800c9810`
- `0x1800c9834`
- `0x1800c98ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c455f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c46c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c455f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800c46c3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c4506`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c4506`

## string_xrefs

- `0x1800c4827`: `onecore\base\appcompat\inventory\software\inv\lib\file.cpp`
- `0x1800c486f`: `onecore\base\appcompat\inventory\software\inv\lib\file.cpp`
- `0x1800c4884`: `onecore\base\appcompat\inventory\software\inv\lib\file.cpp`
- `0x1800c4899`: `onecore\base\appcompat\inventory\software\inv\lib\file.cpp`
- `0x1800c45b6`: `File::GetFilesFromCache`
- `0x1800c471a`: `File::GetFilesFromCache`
- `0x1800c45a9`: `Cache file count changed - refreshing file list.`
- `0x1800c470d`: `Cache file count changed - refreshing file list.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
RTL_SRWLOCK *__fastcall File::GetFilesFromCache(RTL_SRWLOCK *a1, TelCacheProvider *a2, __int64 a3, const char *a4)
{
  int ItemCount; // eax
  int v7; // eax
  int i; // eax
  int v9; // eax
  int j; // eax
  unsigned int v12; // [rsp+20h] [rbp-E0h] BYREF
  RTL_SRWLOCK *v13; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v14[24]; // [rsp+30h] [rbp-D0h] BYREF
  char v15[8]; // [rsp+48h] [rbp-B8h] BYREF
  char v16; // [rsp+50h] [rbp-B0h]
  char v17[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[48]; // [rsp+68h] [rbp-98h] BYREF
  char v19[760]; // [rsp+98h] [rbp-68h] BYREF
  char v20[8]; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v21[48]; // [rsp+398h] [rbp+298h] BYREF
  char v22[760]; // [rsp+3C8h] [rbp+2C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6E8h] [rbp+5E8h]

  v13 = a1;
  v12 = 0;
  if ( dword_180122DB0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180122DB0);
    if ( dword_180122DB0 == -1 )
    {
      atexit(File::GetFilesFromCache_::_2_::_dynamic_atexit_destructor_for__cacheFiles__);
      Init_thread_footer(&dword_180122DB0);
    }
  }
  if ( !a2 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x632,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\file.cpp",
      a4);
  ItemCount = TelCacheProvider::GetItemCount(a2, &v12);
  if ( ItemCount < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x634,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\file.cpp",
      (const char *)(unsigned int)ItemCount,
      v12);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV>::GetImpl'::`2'::impl) )
  {
    AcquireSRWLockShared(&stru_180122A58);
    v13 = &stru_180122A58;
    if ( v12 == 0xFAFAFAFAFAFAFAFBuLL * (((__int64)qword_180122DC0 - qword_180122DB8) >> 4) )
    {
      std::vector<File>::vector<File>(a1);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
    }
    else
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
      AcquireSRWLockExclusive(&stru_180122A58);
      v13 = &stru_180122A58;
      v7 = TelCacheProvider::GetItemCount(a2, &v12);
      if ( v7 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x649,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\file.cpp",
          (const char *)(unsigned int)v7,
          v12);
      if ( v12 != 0xFAFAFAFAFAFAFAFBuLL * (((__int64)qword_180122DC0 - qword_180122DB8) >> 4) )
      {
        AslLogCallPrintf(3, "File::GetFilesFromCache", 1613, "Cache file count changed - refreshing file list.");
        std::set<std::wstring>::set<std::wstring>(v14);
        File::File((File *)v17);
        std::vector<File>::clear();
        for ( i = TelCacheProvider::GetFirstItem(a2, (struct IAmiInventoryItem *)v18);
              i >= 0;
              i = TelCacheProvider::GetNextItem(a2, (struct IAmiInventoryItem *)v18) )
        {
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
            v14,
            v15,
            v19);
          if ( v16 )
          {
            if ( qword_180122DC0 == (File *)qword_180122DC8 )
            {
              std::vector<File>::_Emplace_reallocate<File const &>(&qword_180122DB8, qword_180122DC0, v17);
            }
            else
            {
              File::File(qword_180122DC0, (const struct File *)v17);
              qword_180122DC0 = (File *)((char *)qword_180122DC0 + 816);
            }
          }
        }
        File::~File((File *)v17);
        std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
          v14,
          v14);
      }
      std::vector<File>::vector<File>(a1);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
    }
  }
  else
  {
    if ( v12 != 0xFAFAFAFAFAFAFAFBuLL * (((__int64)qword_180122DC0 - qword_180122DB8) >> 4) )
    {
      AcquireSRWLockExclusive(&stru_180122A58);
      v13 = &stru_180122A58;
      v9 = TelCacheProvider::GetItemCount(a2, &v12);
      if ( v9 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x66D,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\file.cpp",
          (const char *)(unsigned int)v9,
          v12);
      if ( v12 != 0xFAFAFAFAFAFAFAFBuLL * (((__int64)qword_180122DC0 - qword_180122DB8) >> 4) )
      {
        AslLogCallPrintf(3, "File::GetFilesFromCache", 1649, "Cache file count changed - refreshing file list.");
        std::set<std::wstring>::set<std::wstring>(v14);
        File::File((File *)v20);
        std::vector<File>::clear();
        for ( j = TelCacheProvider::GetFirstItem(a2, (struct IAmiInventoryItem *)v21);
              j >= 0;
              j = TelCacheProvider::GetNextItem(a2, (struct IAmiInventoryItem *)v21) )
        {
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
            v14,
            v15,
            v22);
          if ( v16 )
          {
            if ( qword_180122DC0 == (File *)qword_180122DC8 )
            {
              std::vector<File>::_Emplace_reallocate<File const &>(&qword_180122DB8, qword_180122DC0, v20);
            }
            else
            {
              File::File(qword_180122DC0, (const struct File *)v20);
              qword_180122DC0 = (File *)((char *)qword_180122DC0 + 816);
            }
          }
        }
        File::~File((File *)v20);
        std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
          v14,
          v14);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
    }
    std::vector<File>::vector<File>(a1);
  }
  return a1;
}

```

## disassembly

```asm
0x1800c4454  mov     [rsp-8+arg_10], rbx
0x1800c4459  mov     [rsp-8+arg_18], rsi
0x1800c445e  push    rbp
0x1800c445f  push    rdi
0x1800c4460  push    r14
0x1800c4462  lea     rbp, [rsp-5D0h]
0x1800c446a  sub     rsp, 6D0h
0x1800c4471  mov     rax, cs:__security_cookie
0x1800c4478  xor     rax, rsp
0x1800c447b  mov     [rbp+5E0h+var_20], rax
0x1800c4482  mov     rsi, rdx
0x1800c4485  mov     rbx, rcx
0x1800c4488  mov     [rsp+6E0h+var_6B8], rcx
0x1800c448d  mov     [rsp+6E0h+var_6C0], 0; int
0x1800c4495  mov     ecx, cs:_tls_index
0x1800c449b  mov     rax, gs:58h
0x1800c44a4  mov     edx, 4
0x1800c44a9  mov     rax, [rax+rcx*8]
0x1800c44ad  mov     ecx, [rdx+rax]
0x1800c44b0  cmp     cs:dword_180122DB0, ecx
0x1800c44b6  jg      loc_1800C4839
0x1800c44bc  mov     rcx, [rbp+5E8h]; this
0x1800c44c3  test    rsi, rsi
0x1800c44c6  jz      loc_1800C486F
0x1800c44cc  lea     rdx, [rsp+6E0h+var_6C0]; unsigned int *
0x1800c44d1  mov     rcx, rsi; this
0x1800c44d4  call    ?GetItemCount@TelCacheProvider@@QEAAJAEAK@Z; TelCacheProvider::GetItemCount(ulong &)
0x1800c44d9  mov     rcx, [rbp+5E8h]; this
0x1800c44e0  test    eax, eax
0x1800c44e2  js      loc_1800C4881
0x1800c44e8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV> `wil::Feature<__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV>::GetImpl(void)'::`2'::impl
0x1800c44ef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV>::__private_IsEnabled(void)
0x1800c44f4  test    al, al
0x1800c44f6  jz      loc_1800C468C
0x1800c44fc  lea     rdi, stru_180122A58
0x1800c4503  mov     rcx, rdi; SRWLock
0x1800c4506  call    cs:__imp_AcquireSRWLockShared
0x1800c450c  mov     [rsp+6E0h+var_6B8], rdi
0x1800c4511  mov     rdx, cs:qword_180122DC0
0x1800c4518  sub     rdx, cs:qword_180122DB8
0x1800c451f  sar     rdx, 4
0x1800c4523  mov     r14, 0FAFAFAFAFAFAFAFBh
0x1800c452d  imul    rdx, r14
0x1800c4531  mov     ecx, [rsp+6E0h+var_6C0]
0x1800c4535  cmp     rcx, rdx
0x1800c4538  jnz     short loc_1800C4552
0x1800c453a  mov     rcx, rbx
0x1800c453d  call    ??0?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<File>::vector<File>(std::vector<File> const &)
0x1800c4542  nop
0x1800c4543  lea     rcx, [rsp+6E0h+var_6B8]
0x1800c4548  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800c454d  jmp     loc_1800C47FA
0x1800c4552  lea     rcx, [rsp+6E0h+var_6B8]
0x1800c4557  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800c455c  mov     rcx, rdi; SRWLock
0x1800c455f  call    cs:__imp_AcquireSRWLockExclusive
0x1800c4565  mov     [rsp+6E0h+var_6B8], rdi
0x1800c456a  lea     rdx, [rsp+6E0h+var_6C0]; unsigned int *
0x1800c456f  mov     rcx, rsi; this
0x1800c4572  call    ?GetItemCount@TelCacheProvider@@QEAAJAEAK@Z; TelCacheProvider::GetItemCount(ulong &)
0x1800c4577  mov     rcx, [rbp+5E8h]; this
0x1800c457e  test    eax, eax
0x1800c4580  js      loc_1800C4896
0x1800c4586  mov     rcx, cs:qword_180122DC0
0x1800c458d  sub     rcx, cs:qword_180122DB8
0x1800c4594  sar     rcx, 4
0x1800c4598  imul    rcx, r14
0x1800c459c  mov     eax, [rsp+6E0h+var_6C0]
0x1800c45a0  cmp     rax, rcx
0x1800c45a3  jz      loc_1800C4674
0x1800c45a9  lea     r9, aCacheFileCount; "Cache file count changed - refreshing f"...
0x1800c45b0  mov     r8d, 64Dh
0x1800c45b6  lea     rdx, aFileGetfilesfr; "File::GetFilesFromCache"
0x1800c45bd  mov     ecx, 3
0x1800c45c2  call    AslLogCallPrintf
0x1800c45c7  lea     rcx, [rsp+6E0h+var_6B0]
0x1800c45cc  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x1800c45d1  nop
0x1800c45d2  lea     rcx, [rsp+6E0h+var_680]; this
0x1800c45d7  call    ??0File@@QEAA@XZ; File::File(void)
0x1800c45dc  nop
0x1800c45dd  call    ?clear@?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAAXXZ; std::vector<File>::clear(void)
0x1800c45e2  lea     rdx, [rsp+6E0h+var_678]; struct IAmiInventoryItem *
0x1800c45e7  mov     rcx, rsi; this
0x1800c45ea  call    ?GetFirstItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetFirstItem(IAmiInventoryItem *)
0x1800c45ef  jmp     short loc_1800C4656
0x1800c45f1  lea     r8, [rbp+5E0h+var_648]
0x1800c45f5  lea     rdx, [rsp+6E0h+var_698]
0x1800c45fa  lea     rcx, [rsp+6E0h+var_6B0]
0x1800c45ff  call    ??$emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(std::wstring const &)
0x1800c4604  cmp     [rsp+6E0h+var_690], 0
0x1800c4609  jz      short loc_1800C4649
0x1800c460b  mov     rax, cs:qword_180122DC0
0x1800c4612  cmp     rax, cs:qword_180122DC8
0x1800c4619  jz      short loc_1800C4635
0x1800c461b  lea     rdx, [rsp+6E0h+var_680]; struct File *
0x1800c4620  mov     rcx, rax; this
0x1800c4623  call    ??0File@@QEAA@AEBV0@@Z; File::File(File const &)
0x1800c4628  add     cs:qword_180122DC0, 330h
0x1800c4633  jmp     short loc_1800C4649
0x1800c4635  lea     r8, [rsp+6E0h+var_680]
0x1800c463a  mov     rdx, rax
0x1800c463d  lea     rcx, qword_180122DB8
0x1800c4644  call    ??$_Emplace_reallocate@AEBVFile@@@?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@AEAAPEAVFile@@QEAV2@AEBV2@@Z; std::vector<File>::_Emplace_reallocate<File const &>(File * const,File const &)
0x1800c4649  lea     rdx, [rsp+6E0h+var_678]; struct IAmiInventoryItem *
0x1800c464e  mov     rcx, rsi; this
0x1800c4651  call    ?GetNextItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetNextItem(IAmiInventoryItem *)
0x1800c4656  test    eax, eax
0x1800c4658  jns     short loc_1800C45F1
0x1800c465a  lea     rcx, [rsp+6E0h+var_680]; this
0x1800c465f  call    ??1File@@UEAA@XZ; File::~File(void)
0x1800c4664  nop
0x1800c4665  lea     rdx, [rsp+6E0h+var_6B0]
0x1800c466a  lea     rcx, [rsp+6E0h+var_6B0]
0x1800c466f  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &)
0x1800c4674  mov     rcx, rbx
0x1800c4677  call    ??0?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<File>::vector<File>(std::vector<File> const &)
0x1800c467c  nop
0x1800c467d  lea     rcx, [rsp+6E0h+var_6B8]
0x1800c4682  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800c4687  jmp     loc_1800C47FA
0x1800c468c  mov     rcx, cs:qword_180122DC0
0x1800c4693  sub     rcx, cs:qword_180122DB8
0x1800c469a  sar     rcx, 4
0x1800c469e  mov     r14, 0FAFAFAFAFAFAFAFBh
0x1800c46a8  imul    rcx, r14
0x1800c46ac  mov     eax, [rsp+6E0h+var_6C0]
0x1800c46b0  cmp     rax, rcx
0x1800c46b3  jz      loc_1800C47F2
0x1800c46b9  lea     rdi, stru_180122A58
0x1800c46c0  mov     rcx, rdi; SRWLock
0x1800c46c3  call    cs:__imp_AcquireSRWLockExclusive
0x1800c46c9  mov     [rsp+6E0h+var_6B8], rdi
0x1800c46ce  lea     rdx, [rsp+6E0h+var_6C0]; unsigned int *
0x1800c46d3  mov     rcx, rsi; this
0x1800c46d6  call    ?GetItemCount@TelCacheProvider@@QEAAJAEAK@Z; TelCacheProvider::GetItemCount(ulong &)
0x1800c46db  mov     rcx, [rbp+5E8h]; this
0x1800c46e2  test    eax, eax
0x1800c46e4  js      loc_1800C4824
0x1800c46ea  mov     rcx, cs:qword_180122DC0
0x1800c46f1  sub     rcx, cs:qword_180122DB8
0x1800c46f8  sar     rcx, 4
0x1800c46fc  imul    rcx, r14
0x1800c4700  mov     eax, [rsp+6E0h+var_6C0]
0x1800c4704  cmp     rax, rcx
0x1800c4707  jz      loc_1800C47E8
0x1800c470d  lea     r9, aCacheFileCount; "Cache file count changed - refreshing f"...
0x1800c4714  mov     r8d, 671h
0x1800c471a  lea     rdx, aFileGetfilesfr; "File::GetFilesFromCache"
0x1800c4721  mov     ecx, 3
0x1800c4726  call    AslLogCallPrintf
0x1800c472b  lea     rcx, [rsp+6E0h+var_6B0]
0x1800c4730  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x1800c4735  nop
0x1800c4736  lea     rcx, [rbp+5E0h+var_350]; this
0x1800c473d  call    ??0File@@QEAA@XZ; File::File(void)
0x1800c4742  nop
0x1800c4743  call    ?clear@?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAAXXZ; std::vector<File>::clear(void)
0x1800c4748  lea     rdx, [rbp+5E0h+var_348]; struct IAmiInventoryItem *
0x1800c474f  mov     rcx, rsi; this
0x1800c4752  call    ?GetFirstItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetFirstItem(IAmiInventoryItem *)
0x1800c4757  jmp     short loc_1800C47C7
0x1800c4759  lea     r8, [rbp+5E0h+var_318]
0x1800c4760  lea     rdx, [rsp+6E0h+var_698]
0x1800c4765  lea     rcx, [rsp+6E0h+var_6B0]
0x1800c476a  call    ??$emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(std::wstring const &)
0x1800c476f  cmp     [rsp+6E0h+var_690], 0
0x1800c4774  jz      short loc_1800C47B8
0x1800c4776  mov     rax, cs:qword_180122DC0
0x1800c477d  cmp     rax, cs:qword_180122DC8
0x1800c4784  jz      short loc_1800C47A2
0x1800c4786  lea     rdx, [rbp+5E0h+var_350]; struct File *
0x1800c478d  mov     rcx, rax; this
0x1800c4790  call    ??0File@@QEAA@AEBV0@@Z; File::File(File const &)
0x1800c4795  add     cs:qword_180122DC0, 330h
0x1800c47a0  jmp     short loc_1800C47B8
0x1800c47a2  lea     r8, [rbp+5E0h+var_350]
0x1800c47a9  mov     rdx, rax
0x1800c47ac  lea     rcx, qword_180122DB8
0x1800c47b3  call    ??$_Emplace_reallocate@AEBVFile@@@?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@AEAAPEAVFile@@QEAV2@AEBV2@@Z; std::vector<File>::_Emplace_reallocate<File const &>(File * const,File const &)
0x1800c47b8  lea     rdx, [rbp+5E0h+var_348]; struct IAmiInventoryItem *
0x1800c47bf  mov     rcx, rsi; this
0x1800c47c2  call    ?GetNextItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetNextItem(IAmiInventoryItem *)
0x1800c47c7  test    eax, eax
0x1800c47c9  jns     short loc_1800C4759
0x1800c47cb  lea     rcx, [rbp+5E0h+var_350]; this
0x1800c47d2  call    ??1File@@UEAA@XZ; File::~File(void)
0x1800c47d7  nop
0x1800c47d8  lea     rdx, [rsp+6E0h+var_6B0]
0x1800c47dd  lea     rcx, [rsp+6E0h+var_6B0]
0x1800c47e2  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &)
0x1800c47e7  nop
0x1800c47e8  lea     rcx, [rsp+6E0h+var_6B8]
0x1800c47ed  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800c47f2  mov     rcx, rbx
0x1800c47f5  call    ??0?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<File>::vector<File>(std::vector<File> const &)
0x1800c47fa  mov     rax, rbx
0x1800c47fd  mov     rcx, [rbp+5E0h+var_20]
0x1800c4804  xor     rcx, rsp; StackCookie
0x1800c4807  call    __security_check_cookie
0x1800c480c  lea     r11, [rsp+6E0h+var_10]
0x1800c4814  mov     rbx, [r11+30h]
0x1800c4818  mov     rsi, [r11+38h]
0x1800c481c  mov     rsp, r11
0x1800c481f  pop     r14
0x1800c4821  pop     rdi
0x1800c4822  pop     rbp
0x1800c4823  retn
0x1800c4824  mov     r9d, eax; char *
0x1800c4827  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\inventory\\so"...
0x1800c482e  mov     edx, 66Dh; void *
0x1800c4833  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800c4839  lea     rcx, dword_180122DB0
0x1800c4840  call    _Init_thread_header
0x1800c4845  cmp     cs:dword_180122DB0, 0FFFFFFFFh
0x1800c484c  jnz     loc_1800C44BC
0x1800c4852  lea     rcx, _File__GetFilesFromCache____2____dynamic_atexit_destructor_for__cacheFiles__; void (__cdecl *)()
0x1800c4859  call    atexit
0x1800c485e  lea     rcx, dword_180122DB0
0x1800c4865  call    _Init_thread_footer
0x1800c486a  jmp     loc_1800C44BC
0x1800c486f  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\inventory\\so"...
0x1800c4876  mov     edx, 632h; void *
0x1800c487b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800c4881  mov     r9d, eax; char *
0x1800c4884  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\inventory\\so"...
0x1800c488b  mov     edx, 634h; void *
0x1800c4890  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800c4896  mov     r9d, eax; char *
0x1800c4899  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appcompat\\inventory\\so"...
0x1800c48a0  mov     edx, 649h; void *
0x1800c48a5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
