# Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::GetMetadata(void)

- ea: `0x18002e474`
- end: `0x18002e5e1`
- name: `?GetMetadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@SA?AUMetadata@bond@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002d30`

## callees

- `0x180003560`
- `0x18001213c`
- `0x180019bd8`
- `0x18002b7a0`
- `0x18002ca60`
- `0x18002cf28`
- `0x18002d060`
- `0x18002db1c`
- `0x18002e374`
- `0x18002e474`

## string_xrefs

- `0x18002e4a0`: `CopyRestoreData`
- `0x18002e555`: `Windows.Data.Accessibility.EyeControl.SyncedSettings`
- `0x18002e527`: `Microsoft.Accessibility.EyeControl`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 *Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::GetMetadata()
{
  __int64 v0; // rbx
  _BYTE v2[16]; // [rsp+38h] [rbp-71h] BYREF
  _BYTE v3[32]; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v4[32]; // [rsp+68h] [rbp-41h] BYREF
  _BYTE v5[40]; // [rsp+88h] [rbp-21h] BYREF
  _QWORD *v6[2]; // [rsp+B0h] [rbp+7h] BYREF
  __m128i si128; // [rsp+C0h] [rbp+17h]
  _QWORD *v8[3]; // [rsp+D0h] [rbp+27h] BYREF
  unsigned __int64 v9; // [rsp+E8h] [rbp+3Fh]

  std::string::string((__int64)v8, (__int64)"CopyRestoreData");
  std::string::string((__int64)v6, (__int64)"CloudData.BackupRestorePolicy");
  v0 = boost::assign::map_list_of<std::string,std::string>(v5, v6, v8);
  std::string::string((__int64)v3, (__int64)"CloudData.Scope");
  std::string::string((__int64)v4, (__int64)"PerDevice");
  boost::assign_detail::generic_list<std::pair<std::string,std::string>>::push_back(v0, v3);
  std::string::string((__int64)v3, (__int64)"CloudData.SyncGroup");
  std::string::string((__int64)v4, (__int64)"Microsoft.Accessibility.EyeControl");
  boost::assign_detail::generic_list<std::pair<std::string,std::string>>::push_back(v0, v3);
  boost::assign_detail::generic_list<std::pair<std::string,std::string>>::operator<std::map<std::string,std::string>> std::map<std::string,std::string>(
    v0,
    v2);
  bond::reflection::MetadataInit(
    Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::metadata,
    "SyncedSettings",
    "Windows.Data.Accessibility.EyeControl.SyncedSettings",
    v2);
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(v2);
  std::deque<std::pair<std::string,std::string>>::~deque<std::pair<std::string,std::string>>(v5);
  if ( si128.m128i_i64[1] > 0xFuLL )
    std::_Deallocate<16>(v6[0], si128.m128i_i64[1] + 1);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v6[0]) = 0;
  if ( v9 > 0xF )
    std::_Deallocate<16>(v8[0], v9 + 1);
  return Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::metadata;
}

```

## disassembly

```asm
0x18002e474  mov     [rsp-8+arg_0], rbx
0x18002e479  mov     [rsp-8+arg_8], rdi
0x18002e47e  push    rbp
0x18002e47f  lea     rbp, [rsp-57h]
0x18002e484  sub     rsp, 100h
0x18002e48b  mov     rax, cs:__security_cookie
0x18002e492  xor     rax, rsp
0x18002e495  mov     [rbp+57h+var_10], rax
0x18002e499  lea     rdi, ?metadata@Schema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@2UMetadata@bond@@B; bond::Metadata const Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema::metadata
0x18002e4a0  lea     rdx, aCopyrestoredat; "CopyRestoreData"
0x18002e4a7  lea     rcx, [rbp+57h+var_30]
0x18002e4ab  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002e4b0  nop
0x18002e4b1  lea     rdx, aClouddataBacku; "CloudData.BackupRestorePolicy"
0x18002e4b8  lea     rcx, [rbp+57h+var_50]
0x18002e4bc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002e4c1  nop
0x18002e4c2  lea     r8, [rbp+57h+var_30]
0x18002e4c6  lea     rdx, [rbp+57h+var_50]
0x18002e4ca  lea     rcx, [rbp+57h+var_78]
0x18002e4ce  call    ??$map_list_of@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@assign@boost@@YA?AV?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; boost::assign::map_list_of<std::string,std::string>(std::string const &,std::string const &)
0x18002e4d3  mov     rbx, rax
0x18002e4d6  lea     rax, [rbp+57h+var_B8]
0x18002e4da  mov     [rsp+100h+var_E0], rax
0x18002e4df  lea     rdx, aClouddataScope; "CloudData.Scope"
0x18002e4e6  lea     rcx, [rbp+57h+var_B8]
0x18002e4ea  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002e4ef  nop
0x18002e4f0  lea     rdx, aPerdevice; "PerDevice"
0x18002e4f7  lea     rcx, [rbp+57h+var_98]
0x18002e4fb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002e500  nop
0x18002e501  lea     rdx, [rbp+57h+var_B8]
0x18002e505  mov     rcx, rbx
0x18002e508  call    ?push_back@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@boost@@AEAAXU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@Z; boost::assign_detail::generic_list<std::pair<std::string,std::string>>::push_back(std::pair<std::string,std::string>)
0x18002e50d  lea     rax, [rbp+57h+var_B8]
0x18002e511  mov     [rsp+100h+var_E0], rax
0x18002e516  lea     rdx, aClouddataSyncg; "CloudData.SyncGroup"
0x18002e51d  lea     rcx, [rbp+57h+var_B8]
0x18002e521  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002e526  nop
0x18002e527  lea     rdx, aMicrosoftAcces; "Microsoft.Accessibility.EyeControl"
0x18002e52e  lea     rcx, [rbp+57h+var_98]
0x18002e532  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002e537  nop
0x18002e538  lea     rdx, [rbp+57h+var_B8]
0x18002e53c  mov     rcx, rbx
0x18002e53f  call    ?push_back@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@boost@@AEAAXU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@Z; boost::assign_detail::generic_list<std::pair<std::string,std::string>>::push_back(std::pair<std::string,std::string>)
0x18002e544  lea     rdx, [rbp+57h+var_C8]
0x18002e548  mov     rcx, rbx
0x18002e54b  call    ??$?BV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@boost@@QEBA?AV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@XZ; boost::assign_detail::generic_list<std::pair<std::string,std::string>>::operator<std::map<std::string,std::string>> std::map<std::string,std::string>(void)
0x18002e550  nop
0x18002e551  lea     r9, [rbp+57h+var_C8]
0x18002e555  lea     r8, aWindowsDataAcc; "Windows.Data.Accessibility.EyeControl.S"...
0x18002e55c  lea     rdx, aSyncedsettings; "SyncedSettings"
0x18002e563  mov     rcx, rdi
0x18002e566  call    ?MetadataInit@reflection@bond@@YA?AUMetadata@2@PEBD0AEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@@Z; bond::reflection::MetadataInit(char const *,char const *,std::map<std::string,std::string> const &)
0x18002e56b  nop
0x18002e56c  lea     rcx, [rbp+57h+var_C8]
0x18002e570  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(void)
0x18002e575  nop
0x18002e576  lea     rcx, [rbp+57h+var_78]
0x18002e57a  call    ??1?$deque@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::deque<std::pair<std::string,std::string>>::~deque<std::pair<std::string,std::string>>(void)
0x18002e57f  nop
0x18002e580  mov     rdx, [rbp+57h+var_38]
0x18002e584  cmp     rdx, 0Fh
0x18002e588  jbe     short loc_18002E596
0x18002e58a  inc     rdx
0x18002e58d  mov     rcx, [rbp+57h+var_50]
0x18002e591  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002e596  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18002e59e  movdqu  xmmword ptr [rbp+17h], xmm0
0x18002e5a3  mov     byte ptr [rbp+57h+var_50], 0
0x18002e5a7  mov     rdx, [rbp+57h+var_18]
0x18002e5ab  cmp     rdx, 0Fh
0x18002e5af  jbe     short loc_18002E5BD
0x18002e5b1  inc     rdx
0x18002e5b4  mov     rcx, [rbp+57h+var_30]
0x18002e5b8  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002e5bd  mov     rax, rdi
0x18002e5c0  mov     rcx, [rbp+57h+var_10]
0x18002e5c4  xor     rcx, rsp; StackCookie
0x18002e5c7  call    __security_check_cookie
0x18002e5cc  lea     r11, [rsp+100h+var_s0]
0x18002e5d4  mov     rbx, [r11+10h]
0x18002e5d8  mov     rdi, [r11+18h]
0x18002e5dc  mov     rsp, r11
0x18002e5df  pop     rbp
0x18002e5e0  retn
```
