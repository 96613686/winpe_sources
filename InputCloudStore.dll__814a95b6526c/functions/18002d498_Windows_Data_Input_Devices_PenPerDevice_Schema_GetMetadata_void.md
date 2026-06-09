# Windows::Data::Input::Devices::PenPerDevice::Schema::GetMetadata(void)

- ea: `0x18002d498`
- end: `0x18002d63c`
- name: `?GetMetadata@Schema@PenPerDevice@Devices@Input@Data@Windows@@SA?AUMetadata@bond@@XZ`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001b50`

## callees

- `0x180003560`
- `0x18001213c`
- `0x180019bd8`
- `0x18002b7a0`
- `0x18002ca60`
- `0x18002cf28`
- `0x18002d060`
- `0x18002d498`
- `0x18002db1c`
- `0x18002e374`

## string_xrefs

- `0x18002d514`: `LastWriterWins`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 *Windows::Data::Input::Devices::PenPerDevice::Schema::GetMetadata()
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

  std::string::string((__int64)v8, (__int64)"PerDevice");
  std::string::string((__int64)v6, (__int64)"CloudData.Scope");
  v0 = boost::assign::map_list_of<std::string,std::string>(v5, v6, v8);
  std::string::string((__int64)v3, (__int64)"CloudData.ConflictPolicy");
  std::string::string((__int64)v4, (__int64)"LastWriterWins");
  boost::assign_detail::generic_list<std::pair<std::string,std::string>>::push_back(v0, v3);
  std::string::string((__int64)v3, (__int64)"CloudData.UploadPolicy");
  std::string::string((__int64)v4, (__int64)"Opportunistic");
  boost::assign_detail::generic_list<std::pair<std::string,std::string>>::push_back(v0, v3);
  std::string::string((__int64)v3, (__int64)"CloudData.SyncGroup");
  std::string::string((__int64)v4, (__int64)"MicrosoftDevice.Default.PenPerDevice");
  boost::assign_detail::generic_list<std::pair<std::string,std::string>>::push_back(v0, v3);
  boost::assign_detail::generic_list<std::pair<std::string,std::string>>::operator<std::map<std::string,std::string>> std::map<std::string,std::string>(
    v0,
    v2);
  bond::reflection::MetadataInit(
    Windows::Data::Input::Devices::PenPerDevice::Schema::metadata,
    "PenPerDevice",
    "Windows.Data.Input.Devices.PenPerDevice",
    v2);
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(v2);
  std::deque<std::pair<std::string,std::string>>::~deque<std::pair<std::string,std::string>>(v5);
  if ( si128.m128i_i64[1] > 0xFuLL )
    std::_Deallocate<16>(v6[0], si128.m128i_i64[1] + 1);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v6[0]) = 0;
  if ( v9 > 0xF )
    std::_Deallocate<16>(v8[0], v9 + 1);
  return Windows::Data::Input::Devices::PenPerDevice::Schema::metadata;
}

```

## disassembly

```asm
0x18002d498  mov     [rsp-8+arg_0], rbx
0x18002d49d  mov     [rsp-8+arg_8], rdi
0x18002d4a2  push    rbp
0x18002d4a3  lea     rbp, [rsp-57h]
0x18002d4a8  sub     rsp, 100h
0x18002d4af  mov     rax, cs:__security_cookie
0x18002d4b6  xor     rax, rsp
0x18002d4b9  mov     [rbp+57h+var_10], rax
0x18002d4bd  lea     rdi, ?metadata@Schema@PenPerDevice@Devices@Input@Data@Windows@@2UMetadata@bond@@B; bond::Metadata const Windows::Data::Input::Devices::PenPerDevice::Schema::metadata
0x18002d4c4  lea     rdx, aPerdevice; "PerDevice"
0x18002d4cb  lea     rcx, [rbp+57h+var_30]
0x18002d4cf  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002d4d4  nop
0x18002d4d5  lea     rdx, aClouddataScope; "CloudData.Scope"
0x18002d4dc  lea     rcx, [rbp+57h+var_50]
0x18002d4e0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002d4e5  nop
0x18002d4e6  lea     r8, [rbp+57h+var_30]
0x18002d4ea  lea     rdx, [rbp+57h+var_50]
0x18002d4ee  lea     rcx, [rbp+57h+var_78]
0x18002d4f2  call    ??$map_list_of@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@assign@boost@@YA?AV?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; boost::assign::map_list_of<std::string,std::string>(std::string const &,std::string const &)
0x18002d4f7  mov     rbx, rax
0x18002d4fa  lea     rax, [rbp+57h+var_B8]
0x18002d4fe  mov     [rsp+100h+var_E0], rax
0x18002d503  lea     rdx, aClouddataConfl; "CloudData.ConflictPolicy"
0x18002d50a  lea     rcx, [rbp+57h+var_B8]
0x18002d50e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002d513  nop
0x18002d514  lea     rdx, aLastwriterwins; "LastWriterWins"
0x18002d51b  lea     rcx, [rbp+57h+var_98]
0x18002d51f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002d524  nop
0x18002d525  lea     rdx, [rbp+57h+var_B8]
0x18002d529  mov     rcx, rbx
0x18002d52c  call    ?push_back@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@boost@@AEAAXU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@Z; boost::assign_detail::generic_list<std::pair<std::string,std::string>>::push_back(std::pair<std::string,std::string>)
0x18002d531  lea     rax, [rbp+57h+var_B8]
0x18002d535  mov     [rsp+100h+var_E0], rax
0x18002d53a  lea     rdx, aClouddataUploa; "CloudData.UploadPolicy"
0x18002d541  lea     rcx, [rbp+57h+var_B8]
0x18002d545  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002d54a  nop
0x18002d54b  lea     rdx, aOpportunistic; "Opportunistic"
0x18002d552  lea     rcx, [rbp+57h+var_98]
0x18002d556  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002d55b  nop
0x18002d55c  lea     rdx, [rbp+57h+var_B8]
0x18002d560  mov     rcx, rbx
0x18002d563  call    ?push_back@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@boost@@AEAAXU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@Z; boost::assign_detail::generic_list<std::pair<std::string,std::string>>::push_back(std::pair<std::string,std::string>)
0x18002d568  lea     rax, [rbp+57h+var_B8]
0x18002d56c  mov     [rsp+100h+var_E0], rax
0x18002d571  lea     rdx, aClouddataSyncg; "CloudData.SyncGroup"
0x18002d578  lea     rcx, [rbp+57h+var_B8]
0x18002d57c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002d581  nop
0x18002d582  lea     rdx, aMicrosoftdevic_0; "MicrosoftDevice.Default.PenPerDevice"
0x18002d589  lea     rcx, [rbp+57h+var_98]
0x18002d58d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002d592  nop
0x18002d593  lea     rdx, [rbp+57h+var_B8]
0x18002d597  mov     rcx, rbx
0x18002d59a  call    ?push_back@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@boost@@AEAAXU?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@Z; boost::assign_detail::generic_list<std::pair<std::string,std::string>>::push_back(std::pair<std::string,std::string>)
0x18002d59f  lea     rdx, [rbp+57h+var_C8]
0x18002d5a3  mov     rcx, rbx
0x18002d5a6  call    ??$?BV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@@?$generic_list@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@assign_detail@boost@@QEBA?AV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@XZ; boost::assign_detail::generic_list<std::pair<std::string,std::string>>::operator<std::map<std::string,std::string>> std::map<std::string,std::string>(void)
0x18002d5ab  nop
0x18002d5ac  lea     r9, [rbp+57h+var_C8]
0x18002d5b0  lea     r8, aWindowsDataInp_2; "Windows.Data.Input.Devices.PenPerDevice"
0x18002d5b7  lea     rdx, aPenperdevice; "PenPerDevice"
0x18002d5be  mov     rcx, rdi
0x18002d5c1  call    ?MetadataInit@reflection@bond@@YA?AUMetadata@2@PEBD0AEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@@Z; bond::reflection::MetadataInit(char const *,char const *,std::map<std::string,std::string> const &)
0x18002d5c6  nop
0x18002d5c7  lea     rcx, [rbp+57h+var_C8]
0x18002d5cb  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(void)
0x18002d5d0  nop
0x18002d5d1  lea     rcx, [rbp+57h+var_78]
0x18002d5d5  call    ??1?$deque@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::deque<std::pair<std::string,std::string>>::~deque<std::pair<std::string,std::string>>(void)
0x18002d5da  nop
0x18002d5db  mov     rdx, [rbp+57h+var_38]
0x18002d5df  cmp     rdx, 0Fh
0x18002d5e3  jbe     short loc_18002D5F1
0x18002d5e5  inc     rdx
0x18002d5e8  mov     rcx, [rbp+57h+var_50]
0x18002d5ec  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002d5f1  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18002d5f9  movdqu  xmmword ptr [rbp+17h], xmm0
0x18002d5fe  mov     byte ptr [rbp+57h+var_50], 0
0x18002d602  mov     rdx, [rbp+57h+var_18]
0x18002d606  cmp     rdx, 0Fh
0x18002d60a  jbe     short loc_18002D618
0x18002d60c  inc     rdx
0x18002d60f  mov     rcx, [rbp+57h+var_30]
0x18002d613  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002d618  mov     rax, rdi
0x18002d61b  mov     rcx, [rbp+57h+var_10]
0x18002d61f  xor     rcx, rsp; StackCookie
0x18002d622  call    __security_check_cookie
0x18002d627  lea     r11, [rsp+100h+var_s0]
0x18002d62f  mov     rbx, [r11+10h]
0x18002d633  mov     rdi, [r11+18h]
0x18002d637  mov     rsp, r11
0x18002d63a  pop     rbp
0x18002d63b  retn
```
