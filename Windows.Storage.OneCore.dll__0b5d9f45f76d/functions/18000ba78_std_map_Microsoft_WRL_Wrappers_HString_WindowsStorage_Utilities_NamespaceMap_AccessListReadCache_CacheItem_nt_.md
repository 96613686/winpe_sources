# std::map<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>>>::_Try_emplace<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>(Microsoft::WRL::Wrappers::HString &&,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>> &&)

- ea: `0x18000ba78`
- end: `0x18000bbd5`
- name: `??$_Try_emplace@VHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@?$map@VHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@PEAX@std@@_N@1@$$QEAVHString@Wrappers@WRL@Microsoft@@$$QEAV?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@Z`
- size: `349`
- prototype: `__int64 __fastcall(_QWORD *, __int64, HSTRING *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000e01c`

## callees

- `0x18000adb4`
- `0x18000ae14`
- `0x18000b7f4`
- `0x18000ba78`
- `0x18000bc34`
- `0x18000d258`
- `0x1800103dc`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000bb1b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000bb1b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000baed`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000baed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bac1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bad2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bac1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bad2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall std::map<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>>>::_Try_emplace<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>(
        _QWORD *a1,
        __int64 a2,
        HSTRING *a3,
        __int64 a4)
{
  __int64 v8; // rsi
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v10; // rax
  __int64 v11; // rbx
  int v12; // ecx
  int v13; // r8d
  UINT32 v15[2]; // [rsp+30h] [rbp-50h] BYREF
  UINT32 length[2]; // [rsp+38h] [rbp-48h] BYREF
  HSTRING *v17; // [rsp+40h] [rbp-40h] BYREF
  __int128 v18; // [rsp+50h] [rbp-30h] BYREF
  __int128 v19; // [rsp+60h] [rbp-20h] BYREF
  __int64 v20; // [rsp+70h] [rbp-10h]

  std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>>,0>>::_Find_lower_bound<Microsoft::WRL::Wrappers::HString>(
    (__int64)a1,
    &v19,
    a3);
  v8 = v20;
  if ( *(_BYTE *)(v20 + 25)
    || (length[0] = 0,
        v15[0] = 0,
        StringRawBuffer = WindowsGetStringRawBuffer(*a3, length),
        v10 = WindowsGetStringRawBuffer(*(HSTRING *)(v8 + 32), v15),
        CompareStringOrdinal(StringRawBuffer, length[0], v10, v15[0], 1) == 1) )
  {
    if ( a1[1] == 0x333333333333333LL )
      std::_Xlength_error("map/set too long");
    *(_QWORD *)v15 = a4;
    v17 = a3;
    *(_QWORD *)length = *a1;
    v18 = (unsigned __int64)a1;
    v11 = std::_Allocate<16,std::_Default_allocate_traits>(80);
    *((_QWORD *)&v18 + 1) = v11;
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>,void *>>>::construct<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>,std::piecewise_construct_t const &,std::tuple<Microsoft::WRL::Wrappers::HString &&>,std::tuple<WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>> &&>>(
      v12,
      v11 + 32,
      v13,
      (unsigned int)&v17,
      (__int64)v15);
    std::_Construct_in_place<std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> *,std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> * &>(
      (__int64 *)v11,
      (__int64 *)length);
    std::_Construct_in_place<std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> *,std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> * &>(
      (__int64 *)(v11 + 8),
      (__int64 *)length);
    std::_Construct_in_place<std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> *,std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> * &>(
      (__int64 *)(v11 + 16),
      (__int64 *)length);
    *(_WORD *)(v11 + 24) = 0;
    *((_QWORD *)&v18 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>,void *>>>(&v18);
    v18 = v19;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<unsigned short>>>>>::_Insert_node(
                      a1,
                      &v18,
                      v11);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v8;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18000ba78  push    rbp
0x18000ba7a  push    rbx
0x18000ba7b  push    rsi
0x18000ba7c  push    rdi
0x18000ba7d  push    r12
0x18000ba7f  push    r14
0x18000ba81  push    r15
0x18000ba83  mov     rbp, rsp
0x18000ba86  sub     rsp, 80h
0x18000ba8d  mov     r12, r9
0x18000ba90  mov     r15, r8
0x18000ba93  mov     rdi, rdx
0x18000ba96  mov     r14, rcx
0x18000ba99  lea     rdx, [rbp+var_20]
0x18000ba9d  call    ??$_Find_lower_bound@VHString@Wrappers@WRL@Microsoft@@@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@PEAX@std@@@1@AEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>>,0>>::_Find_lower_bound<Microsoft::WRL::Wrappers::HString>(Microsoft::WRL::Wrappers::HString const &)
0x18000baa2  mov     rsi, [rbp+var_10]
0x18000baa6  cmp     byte ptr [rsi+19h], 0
0x18000baaa  jnz     short loc_18000BB04
0x18000baac  mov     [rbp+length], 0
0x18000bab3  mov     [rbp+var_50], 0
0x18000baba  lea     rdx, [rbp+length]; length
0x18000babe  mov     rcx, [r15]; string
0x18000bac1  call    cs:__imp_WindowsGetStringRawBuffer
0x18000bac7  mov     rbx, rax
0x18000baca  lea     rdx, [rbp+var_50]; length
0x18000bace  mov     rcx, [rsi+20h]; string
0x18000bad2  call    cs:__imp_WindowsGetStringRawBuffer
0x18000bad8  mov     [rsp+80h+bIgnoreCase], 1; bIgnoreCase
0x18000bae0  mov     r9d, [rbp+var_50]; cchCount2
0x18000bae4  mov     r8, rax; lpString2
0x18000bae7  mov     edx, [rbp+length]; cchCount1
0x18000baea  mov     rcx, rbx; lpString1
0x18000baed  call    cs:__imp_CompareStringOrdinal
0x18000baf3  cmp     eax, 1
0x18000baf6  jz      short loc_18000BB04
0x18000baf8  mov     [rdi], rsi
0x18000bafb  mov     byte ptr [rdi+8], 0
0x18000baff  jmp     loc_18000BBC0
0x18000bb04  mov     rax, 333333333333333h
0x18000bb0e  cmp     [r14+8], rax
0x18000bb12  jnz     short loc_18000BB22
0x18000bb14  lea     rcx, aMapSetTooLong; "map/set too long"
0x18000bb1b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000bb22  mov     qword ptr [rbp+var_50], r12
0x18000bb26  mov     [rbp+var_40], r15
0x18000bb2a  mov     rax, [r14]
0x18000bb2d  mov     qword ptr [rbp+length], rax
0x18000bb31  mov     qword ptr [rbp+var_30], r14
0x18000bb35  mov     qword ptr [rbp+var_30+8], 0
0x18000bb3d  mov     ecx, 50h ; 'P'
0x18000bb42  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000bb47  mov     rbx, rax
0x18000bb4a  mov     qword ptr [rbp+var_30+8], rax
0x18000bb4e  lea     rdx, [rax+20h]
0x18000bb52  lea     rax, [rbp+var_50]
0x18000bb56  mov     qword ptr [rsp+80h+bIgnoreCase], rax
0x18000bb5b  lea     r9, [rbp+var_40]
0x18000bb5f  call    ??$construct@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@AEBUpiecewise_construct_t@2@V?$tuple@$$QEAVHString@Wrappers@WRL@Microsoft@@@2@V?$tuple@$$QEAV?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@$$QEAVHString@Wrappers@WRL@Microsoft@@@1@$$QEAV?$tuple@$$QEAV?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>,void *>>>::construct<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>,std::piecewise_construct_t const &,std::tuple<Microsoft::WRL::Wrappers::HString &&>,std::tuple<WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>> &&>>(std::allocator<std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>,void *>> &,std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>> * const,std::piecewise_construct_t const &,std::tuple<Microsoft::WRL::Wrappers::HString &&> &&,std::tuple<WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>> &&> &&)
0x18000bb64  lea     rdx, [rbp+length]
0x18000bb68  mov     rcx, rbx
0x18000bb6b  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VPackageInfoCache@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VPackageInfoCache@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> *,std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> * &>(std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> * &,std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> * &)
0x18000bb70  lea     rcx, [rbx+8]
0x18000bb74  lea     rdx, [rbp+length]
0x18000bb78  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VPackageInfoCache@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VPackageInfoCache@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> *,std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> * &>(std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> * &,std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> * &)
0x18000bb7d  lea     rcx, [rbx+10h]
0x18000bb81  lea     rdx, [rbp+length]
0x18000bb85  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VPackageInfoCache@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VPackageInfoCache@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> *,std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> * &>(std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> * &,std::_Tree_node<std::pair<std::wstring const,PackageInfoCache>,void *> * &)
0x18000bb8a  mov     word ptr [rbx+18h], 0
0x18000bb90  mov     qword ptr [rbp+var_30+8], 0
0x18000bb98  lea     rcx, [rbp+var_30]
0x18000bb9c  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>,void *>>>(void)
0x18000bba1  movups  xmm0, [rbp+var_20]
0x18000bba5  movdqu  [rbp+var_30], xmm0
0x18000bbaa  mov     r8, rbx
0x18000bbad  lea     rdx, [rbp+var_30]
0x18000bbb1  mov     rcx, r14
0x18000bbb4  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@PEAUCacheItem@AccessListReadCache@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>,void *> *>,std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<AccessListReadCache::CacheItem *,nt_path_segment_tokenizer<ushort>>>,void *> * const)
0x18000bbb9  mov     [rdi], rax
0x18000bbbc  mov     byte ptr [rdi+8], 1
0x18000bbc0  mov     rax, rdi
0x18000bbc3  add     rsp, 80h
0x18000bbca  pop     r15
0x18000bbcc  pop     r14
0x18000bbce  pop     r12
0x18000bbd0  pop     rdi
0x18000bbd1  pop     rsi
0x18000bbd2  pop     rbx
0x18000bbd3  pop     rbp
0x18000bbd4  retn
```
