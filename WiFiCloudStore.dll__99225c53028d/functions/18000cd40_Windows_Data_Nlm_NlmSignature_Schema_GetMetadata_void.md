# Windows::Data::Nlm::NlmSignature::Schema::GetMetadata(void)

- ea: `0x18000cd40`
- end: `0x18000cf3d`
- name: `?GetMetadata@Schema@NlmSignature@Nlm@Data@Windows@@SA?AUMetadata@bond@@XZ`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update`

## callers

- `0x1800023d0`

## callees

- `0x18000ae1c`
- `0x18000b308`
- `0x18000b8e8`
- `0x18000bbd8`
- `0x18000bd14`
- `0x18000c404`
- `0x18000c4b4`
- `0x18000c544`
- `0x18000caa8`
- `0x18000cad8`
- `0x18000cb74`
- `0x18000cd40`
- `0x180025308`
- `0x180026bc8`
- `0x18002a030`
- `0x18002f14c`

## string_xrefs

- `0x18000ce9a`: `Windows.Data.Nlm.NlmSignature`
- `0x18000ce85`: `NlmSignature`

## pseudocode

```c
__int64 *Windows::Data::Nlm::NlmSignature::Schema::GetMetadata()
{
  __int64 v0; // rax
  __int64 v1; // rax
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // rsi
  __int64 v6; // r14
  __int64 *v7; // rbx
  __int64 *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // rax
  __int128 v12; // [rsp+28h] [rbp-91h] BYREF
  __int64 *v13; // [rsp+40h] [rbp-79h]
  _QWORD v14[2]; // [rsp+50h] [rbp-69h] BYREF
  _QWORD v15[2]; // [rsp+60h] [rbp-59h] BYREF
  _BYTE v16[40]; // [rsp+70h] [rbp-49h] BYREF
  __int128 v17; // [rsp+98h] [rbp-21h] BYREF
  __int128 v18; // [rsp+A8h] [rbp-11h]
  __int128 v19; // [rsp+B8h] [rbp-1h] BYREF
  __int128 v20; // [rsp+C8h] [rbp+Fh]

  v13 = Windows::Data::Nlm::NlmSignature::Schema::metadata;
  v19 = 0;
  v20 = 0;
  std::string::_Construct<1,char const *>(&v19, "0xa3bc0875, 0x12820d3a", 0x16u);
  v17 = 0;
  v18 = 0;
  std::string::_Construct<1,char const *>(&v17, "CloudData.WindowsClient.CloudDataAvailableWnf", 0x2Du);
  v0 = boost::assign::map_list_of<std::string,std::string>(v16, &v17, &v19);
  v1 = boost::assign_detail::generic_list<std::pair<std::string,std::string>>::operator()<char [16],char [8]>(v0);
  v2 = boost::assign_detail::generic_list<std::pair<std::string,std::string>>::operator()<char [28],char [5]>(v1);
  v3 = boost::assign_detail::generic_list<std::pair<std::string,std::string>>::operator()<char [25],char [15]>(v2);
  v4 = boost::assign_detail::generic_list<std::pair<std::string,std::string>>::operator()<char [20],char [27]>(v3);
  v5 = *(_QWORD *)(v4 + 24);
  v6 = v5 + *(_QWORD *)(v4 + 32);
  if ( v4 )
  {
    v7 = *(__int64 **)v4;
    v8 = *(__int64 **)v4;
  }
  else
  {
    v7 = 0;
    v8 = 0;
  }
  v12 = 0;
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::_Alloc_sentinel_and_proxy(&v12);
  if ( v8 )
    v9 = *v8;
  else
    v9 = 0;
  if ( v7 )
    v10 = *v7;
  else
    v10 = 0;
  v14[0] = v9;
  v14[1] = v6;
  v15[0] = v10;
  v15[1] = v5;
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::_Insert_range_unchecked<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<std::pair<std::string,std::string>>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<std::pair<std::string,std::string>>>>>(
    &v12,
    v15,
    v14);
  bond::Metadata::Metadata((bond::Metadata *)Windows::Data::Nlm::NlmSignature::Schema::metadata);
  std::string::_Assign<char>(Windows::Data::Nlm::NlmSignature::Schema::metadata, "NlmSignature", 12);
  std::string::_Assign<char>(&qword_180052AA0, "Windows.Data.Nlm.NlmSignature", 29);
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::operator=(
    qword_180052AC0,
    &v12);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::string const,std::string>,void *>>>(
    (__int64)&v12,
    (__int64)&v12,
    *(char **)(v12 + 8));
  std::_Deallocate<16>((void *)v12, 0x60u);
  std::deque<std::pair<std::string,std::string>>::~deque<std::pair<std::string,std::string>>(v16);
  if ( *((_QWORD *)&v18 + 1) > 0xFu )
    std::_Deallocate<16>((void *)v17, *((_QWORD *)&v18 + 1) + 1LL);
  if ( *((_QWORD *)&v20 + 1) > 0xFu )
    std::_Deallocate<16>((void *)v19, *((_QWORD *)&v20 + 1) + 1LL);
  return Windows::Data::Nlm::NlmSignature::Schema::metadata;
}

```

## disassembly

```asm
0x18000cd40  push    rbp
0x18000cd42  push    rbx
0x18000cd43  push    rsi
0x18000cd44  push    rdi
0x18000cd45  push    r14
0x18000cd47  push    r15
0x18000cd49  lea     rbp, [rsp-2Fh]
0x18000cd4e  sub     rsp, 0E8h
0x18000cd55  mov     rax, cs:__security_cookie
0x18000cd5c  xor     rax, rsp
0x18000cd5f  mov     [rbp+57h+var_38], rax
0x18000cd63  mov     rax, [rbp+57h+var_D0]
0x18000cd67  mov     [rbp+57h+var_D0], rax
0x18000cd6b  mov     [rsp+110h+var_F0], 0
0x18000cd73  lea     r15, ?metadata@Schema@NlmSignature@Nlm@Data@Windows@@2UMetadata@bond@@B; bond::Metadata const Windows::Data::Nlm::NlmSignature::Schema::metadata
0x18000cd7a  mov     [rbp+57h+var_D0], r15
0x18000cd7e  xorps   xmm0, xmm0
0x18000cd81  movups  [rbp+57h+var_58], xmm0
0x18000cd85  xorps   xmm1, xmm1
0x18000cd88  movdqu  [rbp+57h+var_48], xmm1
0x18000cd8d  mov     r8d, 16h
0x18000cd93  lea     rdx, a0xa3bc08750x12; "0xa3bc0875, 0x12820d3a"
0x18000cd9a  lea     rcx, [rbp+57h+var_58]
0x18000cd9e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000cda3  nop
0x18000cda4  xorps   xmm0, xmm0
0x18000cda7  movups  [rbp+57h+var_78], xmm0
0x18000cdab  xorps   xmm1, xmm1
0x18000cdae  movdqu  [rbp+57h+var_68], xmm1
0x18000cdb3  mov     r8d, 2Dh ; '-'
0x18000cdb9  lea     rdx, aClouddataWindo; "CloudData.WindowsClient.CloudDataAvaila"...
0x18000cdc0  lea     rcx, [rbp+57h+var_78]
0x18000cdc4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18000cdc9  nop
0x18000cdca  lea     r8, [rbp+57h+var_58]
0x18000cdce  lea     rdx, [rbp+57h+var_78]
0x18000cdd2  lea     rcx, [rbp+57h+var_A0]
0x18000cdd6  call    ??$map_list_of@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@assign@boost@@YA?AV?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; boost::assign::map_list_of<std::string,std::string>(std::string const &,std::string const &)
0x18000cddb  nop
0x18000cddc  mov     rcx, rax
0x18000cddf  call    ??$?R$$BY0BA@D$$BY07D@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@boost@@QEAAAEAV012@AEAY0BA@$$CBDAEAY07$$CBD@Z; boost::assign_detail::generic_list<std::pair<std::string,std::string>>::operator()<char [16],char [8]>(char const (&)[16],char const (&)[8])
0x18000cde4  mov     rcx, rax
0x18000cde7  call    ??$?R$$BY0BM@D$$BY04D@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@boost@@QEAAAEAV012@AEAY0BM@$$CBDAEAY04$$CBD@Z; boost::assign_detail::generic_list<std::pair<std::string,std::string>>::operator()<char [28],char [5]>(char const (&)[28],char const (&)[5])
0x18000cdec  mov     rcx, rax
0x18000cdef  call    ??$?R$$BY0BJ@D$$BY0P@D@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@boost@@QEAAAEAV012@AEAY0BJ@$$CBDAEAY0P@$$CBD@Z; boost::assign_detail::generic_list<std::pair<std::string,std::string>>::operator()<char [25],char [15]>(char const (&)[25],char const (&)[15])
0x18000cdf4  mov     rcx, rax
0x18000cdf7  call    ??$?R$$BY0BE@D$$BY0BL@D@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@boost@@QEAAAEAV012@AEAY0BE@$$CBDAEAY0BL@$$CBD@Z; boost::assign_detail::generic_list<std::pair<std::string,std::string>>::operator()<char [20],char [27]>(char const (&)[20],char const (&)[27])
0x18000cdfc  mov     rsi, [rax+18h]
0x18000ce00  mov     r14, [rax+20h]
0x18000ce04  add     r14, rsi
0x18000ce07  test    rax, rax
0x18000ce0a  jz      short loc_18000CE14
0x18000ce0c  mov     rbx, [rax]
0x18000ce0f  mov     rdi, rbx
0x18000ce12  jmp     short loc_18000CE18
0x18000ce14  xor     ebx, ebx
0x18000ce16  xor     edi, edi
0x18000ce18  xorps   xmm0, xmm0
0x18000ce1b  movdqu  [rsp+110h+var_E8], xmm0
0x18000ce21  lea     rcx, [rsp+110h+var_E8]
0x18000ce26  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18000ce2b  nop
0x18000ce2c  test    rdi, rdi
0x18000ce2f  jz      short loc_18000CE36
0x18000ce31  mov     rcx, [rdi]
0x18000ce34  jmp     short loc_18000CE38
0x18000ce36  xor     ecx, ecx
0x18000ce38  test    rbx, rbx
0x18000ce3b  jz      short loc_18000CE42
0x18000ce3d  mov     rax, [rbx]
0x18000ce40  jmp     short loc_18000CE44
0x18000ce42  xor     eax, eax
0x18000ce44  mov     [rbp+57h+var_C0], rcx
0x18000ce48  mov     [rbp+57h+var_B8], r14
0x18000ce4c  mov     [rbp+57h+var_B0], rax
0x18000ce50  mov     [rbp+57h+var_A8], rsi
0x18000ce54  lea     r8, [rbp+57h+var_C0]
0x18000ce58  lea     rdx, [rbp+57h+var_B0]
0x18000ce5c  lea     rcx, [rsp+110h+var_E8]
0x18000ce61  call    ??$_Insert_range_unchecked@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@@std@@V12@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::_Insert_range_unchecked<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<std::pair<std::string,std::string>>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<std::pair<std::string,std::string>>>>>(std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<std::pair<std::string,std::string>>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<std::pair<std::string,std::string>>>>)
0x18000ce66  nop
0x18000ce67  mov     [rsp+110h+var_F0], 1Ch
0x18000ce6f  mov     rcx, r15; this
0x18000ce72  call    ??0Metadata@bond@@QEAA@XZ; bond::Metadata::Metadata(void)
0x18000ce77  mov     [rsp+110h+var_F0], 3Ch ; '<'
0x18000ce7f  mov     r8d, 0Ch
0x18000ce85  lea     rdx, aNlmsignature; "NlmSignature"
0x18000ce8c  mov     rcx, r15
0x18000ce8f  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x18000ce94  mov     r8d, 1Dh
0x18000ce9a  lea     rdx, aWindowsDataNlm; "Windows.Data.Nlm.NlmSignature"
0x18000cea1  lea     rcx, qword_180052AA0
0x18000cea8  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x18000cead  lea     rdx, [rsp+110h+var_E8]
0x18000ceb2  lea     rcx, qword_180052AC0
0x18000ceb9  call    ??4?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::operator=(std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>> const &)
0x18000cebe  nop
0x18000cebf  mov     r8, qword ptr [rsp+110h+var_E8]
0x18000cec4  mov     r8, [r8+8]
0x18000cec8  lea     rdx, [rsp+110h+var_E8]
0x18000cecd  lea     rcx, [rsp+110h+var_E8]
0x18000ced2  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::string const,std::string>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::string>,void *>> &,std::_Tree_node<std::pair<std::string const,std::string>,void *> *)
0x18000ced7  mov     edx, 60h ; '`'
0x18000cedc  mov     rcx, qword ptr [rsp+110h+var_E8]
0x18000cee1  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000cee6  nop
0x18000cee7  lea     rcx, [rbp+57h+var_A0]
0x18000ceeb  call    ??1?$deque@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::deque<std::pair<std::string,std::string>>::~deque<std::pair<std::string,std::string>>(void)
0x18000cef0  nop
0x18000cef1  mov     rdx, qword ptr [rbp+57h+var_68+8]
0x18000cef5  cmp     rdx, 0Fh
0x18000cef9  jbe     short loc_18000CF08
0x18000cefb  inc     rdx
0x18000cefe  mov     rcx, qword ptr [rbp+57h+var_78]
0x18000cf02  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000cf07  nop
0x18000cf08  mov     rdx, qword ptr [rbp+57h+var_48+8]
0x18000cf0c  cmp     rdx, 0Fh
0x18000cf10  jbe     short loc_18000CF1E
0x18000cf12  inc     rdx
0x18000cf15  mov     rcx, qword ptr [rbp+57h+var_58]
0x18000cf19  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000cf1e  mov     rax, r15
0x18000cf21  mov     rcx, [rbp+57h+var_38]
0x18000cf25  xor     rcx, rsp; StackCookie
0x18000cf28  call    __security_check_cookie
0x18000cf2d  add     rsp, 0E8h
0x18000cf34  pop     r15
0x18000cf36  pop     r14
0x18000cf38  pop     rdi
0x18000cf39  pop     rsi
0x18000cf3a  pop     rbx
0x18000cf3b  pop     rbp
0x18000cf3c  retn
```
