# File::GetFilesFromCache(TelCacheProvider *)

- ea: `0x180038c50`
- end: `0x18003915b`
- name: `?GetFilesFromCache@File@@SA?AV?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@PEAVTelCacheProvider@@@Z`
- size: `1291`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180039164`
- `0x18003a0b0`

## callees

- `0x180004ea0`
- `0x18000527c`
- `0x180006cec`
- `0x180006eac`
- `0x180006f14`
- `0x18000fc14`
- `0x18001338c`
- `0x18001b554`
- `0x18001bb7c`
- `0x18001d840`
- `0x180033250`
- `0x1800342b0`
- `0x180035178`
- `0x180035b98`
- `0x180036834`
- `0x180038c50`
- `0x180044344`
- `0x180044364`
- `0x180044694`
- `0x18004c020`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180038d06`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180038d06`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038d5d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038f18`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038d5d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038f18`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038ed6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039098`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180038ed6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180039098`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038d46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038d54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038d46`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180038d54`

## string_xrefs

- `0x1800390d7`: `onecore\internal\base\inc\appcompat\inventory\file.cpp`
- `0x18003911f`: `onecore\internal\base\inc\appcompat\inventory\file.cpp`
- `0x180039134`: `onecore\internal\base\inc\appcompat\inventory\file.cpp`
- `0x180039149`: `onecore\internal\base\inc\appcompat\inventory\file.cpp`
- `0x180038da7`: `Cache file count changed - refreshing file list.`
- `0x180038f62`: `Cache file count changed - refreshing file list.`
- `0x180038db4`: `File::GetFilesFromCache`
- `0x180038f6f`: `File::GetFilesFromCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall File::GetFilesFromCache(__int64 a1, TelCacheProvider *a2, __int64 a3, const char *a4)
{
  int ItemCount; // eax
  int v7; // eax
  _QWORD *v8; // rax
  struct File *v9; // rsi
  File *v10; // r12
  int i; // eax
  int v12; // eax
  _QWORD *v13; // rax
  struct File *v14; // rsi
  File *v15; // r12
  int j; // eax
  unsigned int v18[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD *v19; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v20; // [rsp+30h] [rbp-D0h]
  RTL_SRWLOCK *v21; // [rsp+38h] [rbp-C8h]
  _BYTE v22[8]; // [rsp+48h] [rbp-B8h] BYREF
  char v23; // [rsp+50h] [rbp-B0h]
  _BYTE v24[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v25[48]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v26[760]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v27[8]; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v28[48]; // [rsp+398h] [rbp+298h] BYREF
  _BYTE v29[760]; // [rsp+3C8h] [rbp+2C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6F8h] [rbp+5F8h]

  v18[1] = HIDWORD(a1);
  v18[0] = 0;
  if ( dword_18011C118 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18011C118);
    if ( dword_18011C118 == -1 )
    {
      atexit(File::GetFilesFromCache_::_2_::_dynamic_atexit_destructor_for__cacheFiles__);
      Init_thread_footer(&dword_18011C118);
    }
  }
  if ( !a2 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x632,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\file.cpp",
      a4);
  ItemCount = TelCacheProvider::GetItemCount(a2, v18);
  if ( ItemCount < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x634,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\file.cpp",
      (const char *)(unsigned int)ItemCount,
      v18[0]);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV>::GetImpl'::`2'::impl) )
  {
    AcquireSRWLockShared(&stru_18011BF08);
    v21 = &stru_18011BF08;
    if ( v18[0] == 0xFAFAFAFAFAFAFAFBuLL * ((qword_18011C128 - qword_18011C120) >> 4) )
    {
      std::vector<File>::vector<File>(a1);
      ReleaseSRWLockShared(&stru_18011BF08);
    }
    else
    {
      ReleaseSRWLockShared(&stru_18011BF08);
      AcquireSRWLockExclusive(&stru_18011BF08);
      v21 = &stru_18011BF08;
      v7 = TelCacheProvider::GetItemCount(a2, v18);
      if ( v7 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x649,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\file.cpp",
          (const char *)(unsigned int)v7,
          v18[0]);
      if ( v18[0] != 0xFAFAFAFAFAFAFAFBuLL * ((qword_18011C128 - qword_18011C120) >> 4) )
      {
        AslLogCallPrintf(3, "File::GetFilesFromCache", 1613, "Cache file count changed - refreshing file list.");
        v19 = 0;
        v20 = 0;
        v8 = operator new(0x40u);
        *v8 = v8;
        v8[1] = v8;
        v8[2] = v8;
        *((_WORD *)v8 + 12) = 257;
        v19 = v8;
        File::File((File *)v24);
        v9 = qword_18011C120;
        v10 = qword_18011C128;
        if ( qword_18011C120 != qword_18011C128 )
        {
          do
          {
            (**(void (__fastcall ***)(struct File *, _QWORD))v9)(v9, 0);
            v9 = (struct File *)((char *)v9 + 816);
          }
          while ( v9 != v10 );
          qword_18011C128 = qword_18011C120;
        }
        for ( i = TelCacheProvider::GetFirstItem(a2, (struct IAmiInventoryItem *)v25);
              i >= 0;
              i = TelCacheProvider::GetNextItem(a2, (struct IAmiInventoryItem *)v25) )
        {
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring const &>(
            &v19,
            v22,
            v26);
          if ( v23 )
          {
            if ( qword_18011C128 == (File *)qword_18011C130 )
            {
              std::vector<File>::_Emplace_reallocate<File>(&qword_18011C120, qword_18011C128, v24);
            }
            else
            {
              File::File(qword_18011C128, (const struct File *)v24);
              qword_18011C128 = (File *)((char *)qword_18011C128 + 816);
            }
          }
        }
        File::~File((File *)v24);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v19);
      }
      std::vector<File>::vector<File>(a1);
      ReleaseSRWLockExclusive(&stru_18011BF08);
    }
  }
  else
  {
    if ( v18[0] != 0xFAFAFAFAFAFAFAFBuLL * ((qword_18011C128 - qword_18011C120) >> 4) )
    {
      AcquireSRWLockExclusive(&stru_18011BF08);
      v21 = &stru_18011BF08;
      v12 = TelCacheProvider::GetItemCount(a2, v18);
      if ( v12 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x66D,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\file.cpp",
          (const char *)(unsigned int)v12,
          v18[0]);
      if ( v18[0] != 0xFAFAFAFAFAFAFAFBuLL * ((qword_18011C128 - qword_18011C120) >> 4) )
      {
        AslLogCallPrintf(3, "File::GetFilesFromCache", 1649, "Cache file count changed - refreshing file list.");
        v19 = 0;
        v20 = 0;
        v13 = operator new(0x40u);
        *v13 = v13;
        v13[1] = v13;
        v13[2] = v13;
        *((_WORD *)v13 + 12) = 257;
        v19 = v13;
        File::File((File *)v27);
        v14 = qword_18011C120;
        v15 = qword_18011C128;
        if ( qword_18011C120 != qword_18011C128 )
        {
          do
          {
            (**(void (__fastcall ***)(struct File *, _QWORD))v14)(v14, 0);
            v14 = (struct File *)((char *)v14 + 816);
          }
          while ( v14 != v15 );
          qword_18011C128 = qword_18011C120;
        }
        for ( j = TelCacheProvider::GetFirstItem(a2, (struct IAmiInventoryItem *)v28);
              j >= 0;
              j = TelCacheProvider::GetNextItem(a2, (struct IAmiInventoryItem *)v28) )
        {
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring const &>(
            &v19,
            v22,
            v29);
          if ( v23 )
          {
            if ( qword_18011C128 == (File *)qword_18011C130 )
            {
              std::vector<File>::_Emplace_reallocate<File>(&qword_18011C120, qword_18011C128, v27);
            }
            else
            {
              File::File(qword_18011C128, (const struct File *)v27);
              qword_18011C128 = (File *)((char *)qword_18011C128 + 816);
            }
          }
        }
        File::~File((File *)v27);
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(&v19);
      }
      ReleaseSRWLockExclusive(&stru_18011BF08);
    }
    std::vector<File>::vector<File>(a1);
  }
  return a1;
}

```

## disassembly

```asm
0x180038c50  mov     [rsp-8+arg_10], rbx
0x180038c55  mov     [rsp-8+arg_18], rsi
0x180038c5a  push    rbp
0x180038c5b  push    rdi
0x180038c5c  push    r12
0x180038c5e  push    r14
0x180038c60  push    r15
0x180038c62  lea     rbp, [rsp-5D0h]
0x180038c6a  sub     rsp, 6D0h
0x180038c71  mov     rax, cs:__security_cookie
0x180038c78  xor     rax, rsp
0x180038c7b  mov     [rbp+5F0h+var_30], rax
0x180038c82  mov     r14, rdx
0x180038c85  mov     rdi, rcx
0x180038c88  mov     qword ptr [rsp+6F0h+var_6D0], rcx
0x180038c8d  mov     [rsp+6F0h+var_6D0], 0; int
0x180038c95  mov     ecx, cs:_tls_index
0x180038c9b  mov     rax, gs:58h
0x180038ca4  mov     edx, 4
0x180038ca9  mov     rax, [rax+rcx*8]
0x180038cad  mov     ecx, [rdx+rax]
0x180038cb0  cmp     cs:dword_18011C118, ecx
0x180038cb6  jg      loc_1800390E9
0x180038cbc  mov     rcx, [rbp+5F8h]; this
0x180038cc3  test    r14, r14
0x180038cc6  jz      loc_18003911F
0x180038ccc  lea     rdx, [rsp+6F0h+var_6D0]; unsigned int *
0x180038cd1  mov     rcx, r14; this
0x180038cd4  call    ?GetItemCount@TelCacheProvider@@QEAAJAEAK@Z; TelCacheProvider::GetItemCount(ulong &)
0x180038cd9  mov     rcx, [rbp+5F8h]; this
0x180038ce0  test    eax, eax
0x180038ce2  js      loc_180039131
0x180038ce8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV> `wil::Feature<__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV>::GetImpl(void)'::`2'::impl
0x180038cef  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppInv_GetFilesFromCache_AV>::__private_IsEnabled(void)
0x180038cf4  test    al, al
0x180038cf6  jz      loc_180038EE1
0x180038cfc  lea     rbx, stru_18011BF08
0x180038d03  mov     rcx, rbx; SRWLock
0x180038d06  call    cs:__imp_AcquireSRWLockShared
0x180038d0c  mov     [rsp+6F0h+var_6B8], rbx
0x180038d11  mov     r8, cs:qword_18011C128
0x180038d18  sub     r8, cs:qword_18011C120
0x180038d1f  sar     r8, 4
0x180038d23  mov     rsi, 0FAFAFAFAFAFAFAFBh
0x180038d2d  imul    r8, rsi
0x180038d31  mov     edx, [rsp+6F0h+var_6D0]
0x180038d35  cmp     rdx, r8
0x180038d38  jnz     short loc_180038D51
0x180038d3a  mov     rcx, rdi
0x180038d3d  call    ??0?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<File>::vector<File>(std::vector<File> const &)
0x180038d42  nop
0x180038d43  mov     rcx, rbx; SRWLock
0x180038d46  call    cs:__imp_ReleaseSRWLockShared
0x180038d4c  jmp     loc_1800390A6
0x180038d51  mov     rcx, rbx; SRWLock
0x180038d54  call    cs:__imp_ReleaseSRWLockShared
0x180038d5a  mov     rcx, rbx; SRWLock
0x180038d5d  call    cs:__imp_AcquireSRWLockExclusive
0x180038d63  mov     [rsp+6F0h+var_6B8], rbx
0x180038d68  lea     rdx, [rsp+6F0h+var_6D0]; unsigned int *
0x180038d6d  mov     rcx, r14; this
0x180038d70  call    ?GetItemCount@TelCacheProvider@@QEAAJAEAK@Z; TelCacheProvider::GetItemCount(ulong &)
0x180038d75  mov     rcx, [rbp+5F8h]; this
0x180038d7c  test    eax, eax
0x180038d7e  js      loc_180039146
0x180038d84  mov     rcx, cs:qword_18011C128
0x180038d8b  sub     rcx, cs:qword_18011C120
0x180038d92  sar     rcx, 4
0x180038d96  imul    rcx, rsi
0x180038d9a  mov     eax, [rsp+6F0h+var_6D0]
0x180038d9e  cmp     rax, rcx
0x180038da1  jz      loc_180038ECA
0x180038da7  lea     r9, aCacheFileCount; "Cache file count changed - refreshing f"...
0x180038dae  mov     r8d, 64Dh
0x180038db4  lea     rdx, aFileGetfilesfr; "File::GetFilesFromCache"
0x180038dbb  mov     ecx, 3
0x180038dc0  call    AslLogCallPrintf
0x180038dc5  mov     [rsp+6F0h+var_6C8], 0
0x180038dce  mov     [rsp+6F0h+var_6C0], 0
0x180038dd7  mov     ecx, 40h ; '@'; Size
0x180038ddc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038de1  mov     [rax], rax
0x180038de4  mov     [rax+8], rax
0x180038de8  mov     [rax+10h], rax
0x180038dec  mov     word ptr [rax+18h], 101h
0x180038df2  mov     [rsp+6F0h+var_6C8], rax
0x180038df7  lea     rcx, [rsp+6F0h+var_690]; this
0x180038dfc  call    ??0File@@QEAA@XZ; File::File(void)
0x180038e01  nop
0x180038e02  mov     rsi, cs:qword_18011C120
0x180038e09  mov     r15d, 330h
0x180038e0f  mov     r12, cs:qword_18011C128
0x180038e16  cmp     rsi, r12
0x180038e19  jz      short loc_180038E41
0x180038e1b  mov     rax, [rsi]
0x180038e1e  xor     edx, edx
0x180038e20  mov     rcx, rsi
0x180038e23  mov     rax, [rax]
0x180038e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e2b  add     rsi, r15
0x180038e2e  cmp     rsi, r12
0x180038e31  jnz     short loc_180038E1B
0x180038e33  mov     rsi, cs:qword_18011C120
0x180038e3a  mov     cs:qword_18011C128, rsi
0x180038e41  lea     rdx, [rsp+6F0h+var_688]; struct IAmiInventoryItem *
0x180038e46  mov     rcx, r14; this
0x180038e49  call    ?GetFirstItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetFirstItem(IAmiInventoryItem *)
0x180038e4e  jmp     short loc_180038EB1
0x180038e50  lea     r8, [rbp+5F0h+var_658]
0x180038e54  lea     rdx, [rsp+6F0h+var_6A8]
0x180038e59  lea     rcx, [rsp+6F0h+var_6C8]
0x180038e5e  call    ??$_Emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring const &>(std::wstring const &)
0x180038e63  cmp     [rsp+6F0h+var_6A0], 0
0x180038e68  jz      short loc_180038EA4
0x180038e6a  mov     rax, cs:qword_18011C128
0x180038e71  cmp     rax, cs:qword_18011C130
0x180038e78  jz      short loc_180038E90
0x180038e7a  lea     rdx, [rsp+6F0h+var_690]; struct File *
0x180038e7f  mov     rcx, rax; this
0x180038e82  call    ??0File@@QEAA@AEBV0@@Z; File::File(File const &)
0x180038e87  add     cs:qword_18011C128, r15
0x180038e8e  jmp     short loc_180038EA4
0x180038e90  lea     r8, [rsp+6F0h+var_690]
0x180038e95  mov     rdx, rax
0x180038e98  lea     rcx, qword_18011C120
0x180038e9f  call    ??$_Emplace_reallocate@VFile@@@?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@AEAAPEAVFile@@QEAV2@$$QEAV2@@Z; std::vector<File>::_Emplace_reallocate<File>(File * const,File &&)
0x180038ea4  lea     rdx, [rsp+6F0h+var_688]; struct IAmiInventoryItem *
0x180038ea9  mov     rcx, r14; this
0x180038eac  call    ?GetNextItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetNextItem(IAmiInventoryItem *)
0x180038eb1  test    eax, eax
0x180038eb3  jns     short loc_180038E50
0x180038eb5  lea     rcx, [rsp+6F0h+var_690]; this
0x180038eba  call    ??1File@@UEAA@XZ; File::~File(void)
0x180038ebf  nop
0x180038ec0  lea     rcx, [rsp+6F0h+var_6C8]
0x180038ec5  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180038eca  mov     rcx, rdi
0x180038ecd  call    ??0?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<File>::vector<File>(std::vector<File> const &)
0x180038ed2  nop
0x180038ed3  mov     rcx, rbx; SRWLock
0x180038ed6  call    cs:__imp_ReleaseSRWLockExclusive
0x180038edc  jmp     loc_1800390A6
0x180038ee1  mov     rcx, cs:qword_18011C128
0x180038ee8  sub     rcx, cs:qword_18011C120
0x180038eef  sar     rcx, 4
0x180038ef3  mov     rsi, 0FAFAFAFAFAFAFAFBh
0x180038efd  imul    rcx, rsi
0x180038f01  mov     eax, [rsp+6F0h+var_6D0]
0x180038f05  cmp     rax, rcx
0x180038f08  jz      loc_18003909E
0x180038f0e  lea     rbx, stru_18011BF08
0x180038f15  mov     rcx, rbx; SRWLock
0x180038f18  call    cs:__imp_AcquireSRWLockExclusive
0x180038f1e  mov     [rsp+6F0h+var_6B8], rbx
0x180038f23  lea     rdx, [rsp+6F0h+var_6D0]; unsigned int *
0x180038f28  mov     rcx, r14; this
0x180038f2b  call    ?GetItemCount@TelCacheProvider@@QEAAJAEAK@Z; TelCacheProvider::GetItemCount(ulong &)
0x180038f30  mov     rcx, [rbp+5F8h]; this
0x180038f37  test    eax, eax
0x180038f39  js      loc_1800390D4
0x180038f3f  mov     rcx, cs:qword_18011C128
0x180038f46  sub     rcx, cs:qword_18011C120
0x180038f4d  sar     rcx, 4
0x180038f51  imul    rcx, rsi
0x180038f55  mov     eax, [rsp+6F0h+var_6D0]
0x180038f59  cmp     rax, rcx
0x180038f5c  jz      loc_180039095
0x180038f62  lea     r9, aCacheFileCount; "Cache file count changed - refreshing f"...
0x180038f69  mov     r8d, 671h
0x180038f6f  lea     rdx, aFileGetfilesfr; "File::GetFilesFromCache"
0x180038f76  mov     ecx, 3
0x180038f7b  call    AslLogCallPrintf
0x180038f80  mov     [rsp+6F0h+var_6C8], 0
0x180038f89  mov     [rsp+6F0h+var_6C0], 0
0x180038f92  mov     ecx, 40h ; '@'; Size
0x180038f97  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180038f9c  mov     [rax], rax
0x180038f9f  mov     [rax+8], rax
0x180038fa3  mov     [rax+10h], rax
0x180038fa7  mov     word ptr [rax+18h], 101h
0x180038fad  mov     [rsp+6F0h+var_6C8], rax
0x180038fb2  lea     rcx, [rbp+5F0h+var_360]; this
0x180038fb9  call    ??0File@@QEAA@XZ; File::File(void)
0x180038fbe  nop
0x180038fbf  mov     rsi, cs:qword_18011C120
0x180038fc6  mov     r15d, 330h
0x180038fcc  mov     r12, cs:qword_18011C128
0x180038fd3  cmp     rsi, r12
0x180038fd6  jz      short loc_180038FFE
0x180038fd8  mov     rax, [rsi]
0x180038fdb  xor     edx, edx
0x180038fdd  mov     rcx, rsi
0x180038fe0  mov     rax, [rax]
0x180038fe3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fe8  add     rsi, r15
0x180038feb  cmp     rsi, r12
0x180038fee  jnz     short loc_180038FD8
0x180038ff0  mov     rsi, cs:qword_18011C120
0x180038ff7  mov     cs:qword_18011C128, rsi
0x180038ffe  lea     rdx, [rbp+5F0h+var_358]; struct IAmiInventoryItem *
0x180039005  mov     rcx, r14; this
0x180039008  call    ?GetFirstItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetFirstItem(IAmiInventoryItem *)
0x18003900d  jmp     short loc_180039079
0x18003900f  lea     r8, [rbp+5F0h+var_328]
0x180039016  lea     rdx, [rsp+6F0h+var_6A8]
0x18003901b  lea     rcx, [rsp+6F0h+var_6C8]
0x180039020  call    ??$_Emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring const &>(std::wstring const &)
0x180039025  cmp     [rsp+6F0h+var_6A0], 0
0x18003902a  jz      short loc_18003906A
0x18003902c  mov     rax, cs:qword_18011C128
0x180039033  cmp     rax, cs:qword_18011C130
0x18003903a  jz      short loc_180039054
0x18003903c  lea     rdx, [rbp+5F0h+var_360]; struct File *
0x180039043  mov     rcx, rax; this
0x180039046  call    ??0File@@QEAA@AEBV0@@Z; File::File(File const &)
0x18003904b  add     cs:qword_18011C128, r15
0x180039052  jmp     short loc_18003906A
0x180039054  lea     r8, [rbp+5F0h+var_360]
0x18003905b  mov     rdx, rax
0x18003905e  lea     rcx, qword_18011C120
0x180039065  call    ??$_Emplace_reallocate@VFile@@@?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@AEAAPEAVFile@@QEAV2@$$QEAV2@@Z; std::vector<File>::_Emplace_reallocate<File>(File * const,File &&)
0x18003906a  lea     rdx, [rbp+5F0h+var_358]; struct IAmiInventoryItem *
0x180039071  mov     rcx, r14; this
0x180039074  call    ?GetNextItem@TelCacheProvider@@QEAAJPEAVIAmiInventoryItem@@@Z; TelCacheProvider::GetNextItem(IAmiInventoryItem *)
0x180039079  test    eax, eax
0x18003907b  jns     short loc_18003900F
0x18003907d  lea     rcx, [rbp+5F0h+var_360]; this
0x180039084  call    ??1File@@UEAA@XZ; File::~File(void)
0x180039089  nop
0x18003908a  lea     rcx, [rsp+6F0h+var_6C8]
0x18003908f  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180039094  nop
0x180039095  mov     rcx, rbx; SRWLock
0x180039098  call    cs:__imp_ReleaseSRWLockExclusive
0x18003909e  mov     rcx, rdi
0x1800390a1  call    ??0?$vector@VFile@@V?$allocator@VFile@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<File>::vector<File>(std::vector<File> const &)
0x1800390a6  mov     rax, rdi
0x1800390a9  mov     rcx, [rbp+5F0h+var_30]
0x1800390b0  xor     rcx, rsp; StackCookie
0x1800390b3  call    __security_check_cookie
0x1800390b8  lea     r11, [rsp+6F0h+var_20]
0x1800390c0  mov     rbx, [r11+40h]
0x1800390c4  mov     rsi, [r11+48h]
0x1800390c8  mov     rsp, r11
0x1800390cb  pop     r15
0x1800390cd  pop     r14
0x1800390cf  pop     r12
0x1800390d1  pop     rdi
0x1800390d2  pop     rbp
0x1800390d3  retn
0x1800390d4  mov     r9d, eax; char *
0x1800390d7  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x1800390de  mov     edx, 66Dh; void *
0x1800390e3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800390e9  lea     rcx, dword_18011C118
0x1800390f0  call    _Init_thread_header
0x1800390f5  cmp     cs:dword_18011C118, 0FFFFFFFFh
0x1800390fc  jnz     loc_180038CBC
0x180039102  lea     rcx, _File__GetFilesFromCache____2____dynamic_atexit_destructor_for__cacheFiles__; void (__cdecl *)()
0x180039109  call    atexit
0x18003910e  lea     rcx, dword_18011C118
0x180039115  call    _Init_thread_footer
0x18003911a  jmp     loc_180038CBC
0x18003911f  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x180039126  mov     edx, 632h; void *
0x18003912b  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180039131  mov     r9d, eax; char *
0x180039134  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x18003913b  mov     edx, 634h; void *
0x180039140  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180039146  mov     r9d, eax; char *
0x180039149  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x180039150  mov     edx, 649h; void *
0x180039155  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
