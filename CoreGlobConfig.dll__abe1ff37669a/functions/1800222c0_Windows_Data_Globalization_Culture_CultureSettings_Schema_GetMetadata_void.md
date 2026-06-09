# Windows::Data::Globalization::Culture::CultureSettings::Schema::GetMetadata(void)

- ea: `0x1800222c0`
- end: `0x180022432`
- name: `?GetMetadata@Schema@CultureSettings@Culture@Globalization@Data@Windows@@SA?AUMetadata@bond@@XZ`
- size: `370`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001eb0`

## callees

- `0x180002380`
- `0x1800027bc`
- `0x18000d174`
- `0x18000f5dc`
- `0x18000f67c`
- `0x1800221d0`
- `0x180022438`

## string_xrefs

- `0x180022316`: `LastWriterWins`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 *Windows::Data::Globalization::Culture::CultureSettings::Schema::GetMetadata()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  _BYTE v4[16]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v5[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v6[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v7[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v8[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v9[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v10[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v11[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v12[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v13[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v14[32]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v15; // [rsp+190h] [rbp+90h] BYREF

  std::string::string(v5, "CloudData.ConflictPolicy");
  std::string::string(v6, "LastWriterWins");
  std::string::string(v7, "CloudData.Scope");
  std::string::string(v8, "PerUser");
  std::string::string(v9, "CloudData.SyncGroup");
  std::string::string(v10, "Microsoft.Language.CultureSettings");
  std::string::string(v11, "CloudData.UploadPolicy");
  std::string::string(v12, "Opportunistic");
  std::string::string(v13, "CloudData.WindowsClient.CloudDataAvailableWnf");
  std::string::string(v14, "0xa3bc1875, 0x0389022a");
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(v4);
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::_Insert_range_unchecked<std::pair<std::string const,std::string> const *,std::pair<std::string const,std::string> const *>(
    v4,
    v5,
    &v15);
  bond::reflection::MetadataInit(v1, v0, v2, v4);
  std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::string>,void *>>>(
    v4,
    v4);
  `eh vector destructor iterator'(
    v5,
    0x40u,
    5u,
    std::pair<std::string const,std::string>::~pair<std::string const,std::string>);
  return Windows::Data::Globalization::Culture::CultureSettings::Schema::metadata;
}

```

## disassembly

```asm
0x1800222c0  mov     [rsp-8+arg_0], rbx
0x1800222c5  push    rbp
0x1800222c6  lea     rbp, [rsp-0A0h]
0x1800222ce  sub     rsp, 1A0h
0x1800222d5  mov     rax, cs:__security_cookie
0x1800222dc  xor     rax, rsp
0x1800222df  mov     [rbp+0A0h+var_10], rax
0x1800222e6  mov     rax, [rsp+1A0h+var_170]
0x1800222eb  mov     [rsp+1A0h+var_170], rax
0x1800222f0  mov     [rsp+1A0h+var_180], 0
0x1800222f8  lea     rbx, ?metadata@Schema@CultureSettings@Culture@Globalization@Data@Windows@@2UMetadata@bond@@B; bond::Metadata const Windows::Data::Globalization::Culture::CultureSettings::Schema::metadata
0x1800222ff  mov     [rsp+1A0h+var_170], rbx
0x180022304  lea     rdx, aClouddataConfl; "CloudData.ConflictPolicy"
0x18002230b  lea     rcx, [rsp+1A0h+var_150]
0x180022310  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180022315  nop
0x180022316  lea     rdx, aLastwriterwins; "LastWriterWins"
0x18002231d  lea     rcx, [rsp+1A0h+var_130]
0x180022322  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180022327  nop
0x180022328  lea     rdx, aClouddataScope; "CloudData.Scope"
0x18002232f  lea     rcx, [rbp+0A0h+var_110]
0x180022333  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180022338  nop
0x180022339  lea     rdx, aPeruser; "PerUser"
0x180022340  lea     rcx, [rbp+0A0h+var_F0]
0x180022344  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180022349  nop
0x18002234a  lea     rdx, aClouddataSyncg; "CloudData.SyncGroup"
0x180022351  lea     rcx, [rbp+0A0h+var_D0]
0x180022355  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002235a  nop
0x18002235b  lea     rdx, aMicrosoftLangu; "Microsoft.Language.CultureSettings"
0x180022362  lea     rcx, [rbp+0A0h+var_B0]
0x180022366  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002236b  nop
0x18002236c  lea     rdx, aClouddataUploa; "CloudData.UploadPolicy"
0x180022373  lea     rcx, [rbp+0A0h+var_90]
0x180022377  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002237c  nop
0x18002237d  lea     rdx, aOpportunistic; "Opportunistic"
0x180022384  lea     rcx, [rbp+0A0h+var_70]
0x180022388  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002238d  nop
0x18002238e  lea     rdx, aClouddataWindo; "CloudData.WindowsClient.CloudDataAvaila"...
0x180022395  lea     rcx, [rbp+0A0h+var_50]
0x180022399  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002239e  nop
0x18002239f  lea     rdx, a0xa3bc18750x03; "0xa3bc1875, 0x0389022a"
0x1800223a6  lea     rcx, [rbp+0A0h+var_30]
0x1800223aa  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800223af  nop
0x1800223b0  lea     rcx, [rsp+1A0h+var_160]
0x1800223b5  call    ??0?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@AEBU?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(std::less<std::string> const &)
0x1800223ba  nop
0x1800223bb  lea     r8, [rbp+0A0h+var_10]
0x1800223c2  lea     rdx, [rsp+1A0h+var_150]
0x1800223c7  lea     rcx, [rsp+1A0h+var_160]
0x1800223cc  call    ??$_Insert_range_unchecked@PEBU?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEBU12@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXPEBU?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@1@QEBU21@@Z; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::_Insert_range_unchecked<std::pair<std::string const,std::string> const *,std::pair<std::string const,std::string> const *>(std::pair<std::string const,std::string> const *,std::pair<std::string const,std::string> const * const)
0x1800223d1  nop
0x1800223d2  lea     r9, [rsp+1A0h+var_160]
0x1800223d7  call    ?MetadataInit@reflection@bond@@YA?AUMetadata@2@PEBD0AEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@@Z; bond::reflection::MetadataInit(char const *,char const *,std::map<std::string,std::string> const &)
0x1800223dc  mov     [rsp+1A0h+var_180], 1
0x1800223e4  lea     rdx, [rsp+1A0h+var_160]
0x1800223e9  lea     rcx, [rsp+1A0h+var_160]
0x1800223ee  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::string>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::string>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::string>,void *>> &)
0x1800223f3  nop
0x1800223f4  lea     r9, ??1?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@QEAA@XZ; void (*)(void *)
0x1800223fb  mov     edx, 40h ; '@'; unsigned __int64
0x180022400  lea     r8d, [rdx-3Bh]; unsigned __int64
0x180022404  lea     rcx, [rsp+1A0h+var_150]; void *
0x180022409  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002240e  mov     rax, rbx
0x180022411  mov     rcx, [rbp+0A0h+var_10]
0x180022418  xor     rcx, rsp; StackCookie
0x18002241b  call    __security_check_cookie
0x180022420  mov     rbx, [rsp+1A0h+arg_0]
0x180022428  add     rsp, 1A0h
0x18002242f  pop     rbp
0x180022430  retn
```
