# std::map<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<ushort>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<ushort>>>>>::_Try_emplace<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<ushort>>>(Microsoft::WRL::Wrappers::HString &&,WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<ushort>> &&)

- ea: `0x1800554d4`
- end: `0x180055607`
- name: `??$_Try_emplace@VHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@?$map@VHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@PEAX@std@@_N@1@$$QEAVHString@Wrappers@WRL@Microsoft@@$$QEAV?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@Z`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180033af0`

## callees

- `0x180028060`
- `0x180054b38`
- `0x180055364`
- `0x1800554d4`
- `0x180056988`
- `0x180059a50`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180055574`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180055574`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180055546`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180055546`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005551a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005552b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005551a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005552b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::map<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<unsigned short>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<unsigned short>>>>>::_Try_emplace<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<unsigned short>>>(
        __int64 *a1,
        __int64 a2,
        HSTRING *a3,
        __int64 a4)
{
  __int64 v8; // rdi
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rdi
  UINT32 v14[2]; // [rsp+30h] [rbp-40h] BYREF
  UINT32 length[2]; // [rsp+38h] [rbp-38h] BYREF
  __int128 v16; // [rsp+40h] [rbp-30h] BYREF
  __int128 v17; // [rsp+50h] [rbp-20h] BYREF
  __int64 v18; // [rsp+60h] [rbp-10h]

  std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<unsigned short>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<unsigned short>>>>,0>>::_Find_lower_bound<Microsoft::WRL::Wrappers::HString>(
    a1,
    &v17);
  v8 = v18;
  if ( *(_BYTE *)(v18 + 25)
    || (length[0] = 0,
        v14[0] = 0,
        StringRawBuffer = WindowsGetStringRawBuffer(*a3, length),
        v10 = WindowsGetStringRawBuffer(*(HSTRING *)(v8 + 32), v14),
        CompareStringOrdinal(StringRawBuffer, length[0], v10, v14[0], 1) == 1) )
  {
    if ( a1[1] == 0x2AAAAAAAAAAAAAALL )
      std::_Xlength_error("map/set too long");
    v11 = *a1;
    v16 = (unsigned __int64)a1;
    v12 = std::_Allocate<16,std::_Default_allocate_traits>(96);
    *((_QWORD *)&v16 + 1) = v12;
    *(_QWORD *)length = a4;
    *(_QWORD *)v14 = a3;
    ____0V__tuple___QEAVHString_Wrappers_WRL_Microsoft___std__V__tuple___QEAV__NamespaceMap_V__shared_ptr___CBUPerFolderRootInfo___std__U__nt_path_segment_tokenizer_G___Utilities_WindowsStorage___1__0A___Z_0A____pair___CBVHString_Wrappers_WRL_Microsoft__V__NamespaceMap_V__shared_ptr___CBUPerFolderRootInfo___std__U__nt_path_segment_tokenizer_G___Utilities_WindowsStorage___std__AEAA_AEAV__tuple___QEAVHString_Wrappers_WRL_Microsoft___1_AEAV__tuple___QEAV__NamespaceMap_V__shared_ptr___CBUPerFolderRootInfo___std__U__nt_path_segment_tokenizer_G___Utilities_WindowsStorage___1_U__integer_sequence__K_0A__1_2_Z(
      v12 + 32,
      v14,
      length);
    *(_QWORD *)v12 = v11;
    *(_QWORD *)(v12 + 8) = v11;
    *(_QWORD *)(v12 + 16) = v11;
    *(_WORD *)(v12 + 24) = 0;
    *((_QWORD *)&v16 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<unsigned short>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<unsigned short>>>,void *>>>(&v16);
    v16 = v17;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,KeyFoundInLocationEntry>>>::_Insert_node(
                      a1,
                      &v16,
                      v12);
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
0x1800554d4  push    rbp
0x1800554d6  push    rbx
0x1800554d7  push    rsi
0x1800554d8  push    rdi
0x1800554d9  push    r12
0x1800554db  push    r14
0x1800554dd  push    r15
0x1800554df  mov     rbp, rsp
0x1800554e2  sub     rsp, 70h
0x1800554e6  mov     r12, r9
0x1800554e9  mov     r15, r8
0x1800554ec  mov     rsi, rdx
0x1800554ef  mov     r14, rcx
0x1800554f2  lea     rdx, [rbp+var_20]
0x1800554f6  call    ??$_Find_lower_bound@VHString@Wrappers@WRL@Microsoft@@@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@PEAX@std@@@1@AEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<ushort>>,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<ushort>>>>,0>>::_Find_lower_bound<Microsoft::WRL::Wrappers::HString>(Microsoft::WRL::Wrappers::HString const &)
0x1800554fb  mov     rdi, [rbp+var_10]
0x1800554ff  cmp     byte ptr [rdi+19h], 0
0x180055503  jnz     short loc_18005555D
0x180055505  mov     [rbp+length], 0
0x18005550c  mov     [rbp+var_40], 0
0x180055513  lea     rdx, [rbp+length]; length
0x180055517  mov     rcx, [r15]; string
0x18005551a  call    cs:__imp_WindowsGetStringRawBuffer
0x180055520  mov     rbx, rax
0x180055523  lea     rdx, [rbp+var_40]; length
0x180055527  mov     rcx, [rdi+20h]; string
0x18005552b  call    cs:__imp_WindowsGetStringRawBuffer
0x180055531  mov     [rsp+70h+bIgnoreCase], 1; bIgnoreCase
0x180055539  mov     r9d, [rbp+var_40]; cchCount2
0x18005553d  mov     r8, rax; lpString2
0x180055540  mov     edx, [rbp+length]; cchCount1
0x180055543  mov     rcx, rbx; lpString1
0x180055546  call    cs:__imp_CompareStringOrdinal
0x18005554c  cmp     eax, 1
0x18005554f  jz      short loc_18005555D
0x180055551  mov     [rsi], rdi
0x180055554  mov     byte ptr [rsi+8], 0
0x180055558  jmp     loc_1800555F5
0x18005555d  mov     rax, 2AAAAAAAAAAAAAAh
0x180055567  cmp     [r14+8], rax
0x18005556b  jnz     short loc_18005557B
0x18005556d  lea     rcx, aMapSetTooLong; "map/set too long"
0x180055574  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18005557b  mov     rbx, [r14]
0x18005557e  mov     qword ptr [rbp+var_30], r14
0x180055582  mov     qword ptr [rbp+var_30+8], 0
0x18005558a  mov     ecx, 60h ; '`'
0x18005558f  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180055594  mov     rdi, rax
0x180055597  mov     qword ptr [rbp+var_30+8], rax
0x18005559b  mov     qword ptr [rbp+length], r12
0x18005559f  mov     qword ptr [rbp+var_40], r15
0x1800555a3  lea     rcx, [rax+20h]
0x1800555a7  lea     r8, [rbp+length]
0x1800555ab  lea     rdx, [rbp+var_40]
0x1800555af  call    ??$?0V?$tuple@$$QEAVHString@Wrappers@WRL@Microsoft@@@std@@V?$tuple@$$QEAV?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@1@$0A@$$Z$0A@@?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@AEAA@AEAV?$tuple@$$QEAVHString@Wrappers@WRL@Microsoft@@@1@AEAV?$tuple@$$QEAV?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@1@U?$integer_sequence@_K$0A@@1@2@Z
0x1800555b4  mov     [rdi], rbx
0x1800555b7  mov     [rdi+8], rbx
0x1800555bb  mov     [rdi+10h], rbx
0x1800555bf  mov     word ptr [rdi+18h], 0
0x1800555c5  mov     qword ptr [rbp+var_30+8], 0
0x1800555cd  lea     rcx, [rbp+var_30]
0x1800555d1  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V?$NamespaceMap@V?$shared_ptr@$$CBUPerFolderRootInfo@@@std@@U?$nt_path_segment_tokenizer@G@@@Utilities@WindowsStorage@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<ushort>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Microsoft::WRL::Wrappers::HString const,WindowsStorage::Utilities::NamespaceMap<std::shared_ptr<PerFolderRootInfo const>,nt_path_segment_tokenizer<ushort>>>,void *>>>(void)
0x1800555d6  movups  xmm0, [rbp+var_20]
0x1800555da  movdqu  [rbp+var_30], xmm0
0x1800555df  mov     r8, rdi
0x1800555e2  lea     rdx, [rbp+var_30]
0x1800555e6  mov     rcx, r14
0x1800555e9  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyFoundInLocationEntry@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyFoundInLocationEntry@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UKeyFoundInLocationEntry@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,KeyFoundInLocationEntry>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,KeyFoundInLocationEntry>,void *> *>,std::_Tree_node<std::pair<std::wstring const,KeyFoundInLocationEntry>,void *> * const)
0x1800555ee  mov     [rsi], rax
0x1800555f1  mov     byte ptr [rsi+8], 1
0x1800555f5  mov     rax, rsi
0x1800555f8  add     rsp, 70h
0x1800555fc  pop     r15
0x1800555fe  pop     r14
0x180055600  pop     r12
0x180055602  pop     rdi
0x180055603  pop     rsi
0x180055604  pop     rbx
0x180055605  pop     rbp
0x180055606  retn
```
