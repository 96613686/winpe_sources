# PolicyModel::CRule::Deserialize(Sharp::Util::Xml::CNode const &)

- ea: `0x14000a560`
- end: `0x14000a9a3`
- name: `?Deserialize@CRule@PolicyModel@@MEAAXAEBVCNode@Xml@Util@Sharp@@@Z`
- size: `1091`
- prototype: `void __fastcall(PolicyModel::CRule *__hidden this, const struct Sharp::Util::Xml::CNode *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, registry_config`

## callees

- `0x1400070e4`
- `0x140008368`
- `0x14000918c`
- `0x140009410`
- `0x140009520`
- `0x1400096c4`
- `0x1400099b4`
- `0x14000a0d4`
- `0x14000a560`
- `0x14000ba60`
- `0x14000bbc8`
- `0x140012138`
- `0x140012b94`
- `0x140012f20`
- `0x140012fa0`
- `0x1400130ec`
- `0x140013b10`

## string_xrefs

- `0x14000a6b2`: `UserOrGroupSid`
- `0x14000a7fd`: `FilePathCondition`
- `0x14000a905`: `FilePathCondition`

## pseudocode

```c
void __fastcall PolicyModel::CRule::Deserialize(PolicyModel::CRule *this, const struct Sharp::Util::Xml::CNode *a2)
{
  char *v3; // rdi
  __int128 *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  int v9; // ebx
  char HasSpecificChild; // bl
  _BYTE v11[16]; // [rsp+20h] [rbp-39h] BYREF
  _QWORD v12[4]; // [rsp+30h] [rbp-29h] BYREF
  void **v13; // [rsp+50h] [rbp-9h] BYREF
  __int128 v14; // [rsp+58h] [rbp-1h]
  _QWORD v15[4]; // [rsp+70h] [rbp+17h] BYREF

  v3 = (char *)this - 8;
  std::wstring::wstring((__int64)v12);
  v4 = (__int128 *)Sharp::Util::Xml::CNode::ParseGuidAttribute(a2, v11, v12);
  PolicyModel::CPolicyElement::CPolicyElement((PolicyModel::CPolicyElement *)&v13);
  v13 = &PolicyModel::CId::`vftable';
  v14 = *v4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_58eb30b6f4dc383367536c56e7c2c555_Traceguids);
  *(_OWORD *)(v3 + 24) = v14;
  PolicyModel::CId::~CId((PolicyModel::CId *)&v13);
  std::wstring::_Tidy(v12, 1, 0);
  std::wstring::wstring((__int64)v12);
  v5 = Sharp::Util::Xml::CNode::ParseStringAttribute(a2, &v13, v12);
  std::wstring::operator=((__int64)(v3 + 40), v5);
  std::wstring::_Tidy(&v13, 1, 0);
  std::wstring::_Tidy(v12, 1, 0);
  std::wstring::wstring((__int64)v12);
  v6 = Sharp::Util::Xml::CNode::ParseStringAttribute(a2, &v13, v12);
  std::wstring::operator=((__int64)(v3 + 72), v6);
  std::wstring::_Tidy(&v13, 1, 0);
  std::wstring::_Tidy(v12, 1, 0);
  std::wstring::wstring((__int64)v12);
  v7 = Sharp::Util::Xml::CNode::ParseStringAttribute(a2, &v13, v12);
  std::wstring::operator=((__int64)(v3 + 104), v7);
  std::wstring::_Tidy(&v13, 1, 0);
  std::wstring::_Tidy(v12, 1, 0);
  std::wstring::wstring((__int64)v12);
  Sharp::Util::Xml::CNode::ParseStringAttribute(a2, v15, v12);
  std::wstring::_Tidy(v12, 1, 0);
  v8 = std::wstring::wstring((__int64)v12);
  v9 = (unsigned __int8)std::operator==<unsigned short>(v15, v8);
  std::wstring::_Tidy(v12, 1, 0);
  *((_DWORD *)v3 + 34) = v9 ^ 1;
  std::wstring::wstring((__int64)v12);
  LOBYTE(v9) = Sharp::Util::Xml::CNode::HasSpecificChild(a2, v12);
  std::wstring::_Tidy(v12, 1, 0);
  if ( (_BYTE)v9 )
  {
    std::wstring::wstring((__int64)v12);
    Sharp::Util::Xml::CNode::GetSpecificChild(a2, v11, v12);
    std::wstring::_Tidy(v12, 1, 0);
    std::wstring::wstring((__int64)v12);
    PolicyModel::CRule::DeserializeConditions<PolicyModel::CFilePublisherCondition>(
      (__int64)v3,
      (__int64)v11,
      (__int64)v12,
      1);
    std::wstring::_Tidy(v12, 1, 0);
    std::wstring::wstring((__int64)v12);
    PolicyModel::CRule::DeserializeConditions<PolicyModel::CFilePathCondition>(
      (__int64)v3,
      (__int64)v11,
      (__int64)v12,
      1);
    std::wstring::_Tidy(v12, 1, 0);
    std::wstring::wstring((__int64)v12);
    PolicyModel::CRule::DeserializeConditions<PolicyModel::CFileHashCondition>(
      (__int64)v3,
      (__int64)v11,
      (__int64)v12,
      1);
    std::wstring::_Tidy(v12, 1, 0);
    Sharp::Util::Xml::CNode::~CNode((Sharp::Util::Xml::CNode *)v11);
  }
  std::wstring::wstring((__int64)v12);
  HasSpecificChild = Sharp::Util::Xml::CNode::HasSpecificChild(a2, v12);
  std::wstring::_Tidy(v12, 1, 0);
  if ( HasSpecificChild )
  {
    std::wstring::wstring((__int64)v12);
    Sharp::Util::Xml::CNode::GetSpecificChild(a2, v11, v12);
    std::wstring::_Tidy(v12, 1, 0);
    std::wstring::wstring((__int64)v12);
    PolicyModel::CRule::DeserializeConditions<PolicyModel::CFilePublisherCondition>(
      (__int64)v3,
      (__int64)v11,
      (__int64)v12,
      0);
    std::wstring::_Tidy(v12, 1, 0);
    std::wstring::wstring((__int64)v12);
    PolicyModel::CRule::DeserializeConditions<PolicyModel::CFilePathCondition>(
      (__int64)v3,
      (__int64)v11,
      (__int64)v12,
      0);
    std::wstring::_Tidy(v12, 1, 0);
    std::wstring::wstring((__int64)v12);
    PolicyModel::CRule::DeserializeConditions<PolicyModel::CFileHashCondition>(
      (__int64)v3,
      (__int64)v11,
      (__int64)v12,
      0);
    std::wstring::_Tidy(v12, 1, 0);
    Sharp::Util::Xml::CNode::~CNode((Sharp::Util::Xml::CNode *)v11);
  }
  std::wstring::_Tidy(v15, 1, 0);
}

```

## disassembly

```asm
0x14000a560  mov     [rsp-8+arg_10], rbx
0x14000a565  push    rbp
0x14000a566  push    rsi
0x14000a567  push    rdi
0x14000a568  lea     rbp, [rsp-47h]
0x14000a56d  sub     rsp, 0A0h
0x14000a574  mov     rax, cs:__security_cookie
0x14000a57b  xor     rax, rsp
0x14000a57e  mov     [rbp+57h+var_20], rax
0x14000a582  mov     rsi, rdx
0x14000a585  lea     rdi, [rcx-8]
0x14000a589  lea     rdx, aId; "Id"
0x14000a590  lea     rcx, [rbp+57h+var_80]
0x14000a594  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a599  nop
0x14000a59a  lea     r8, [rbp+57h+var_80]
0x14000a59e  lea     rdx, [rbp+57h+var_90]
0x14000a5a2  mov     rcx, rsi
0x14000a5a5  call    ?ParseGuidAttribute@CNode@Xml@Util@Sharp@@QEBA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::ParseGuidAttribute(std::wstring const &)
0x14000a5aa  mov     rbx, rax
0x14000a5ad  lea     rcx, [rbp+57h+var_60]; this
0x14000a5b1  call    ??0CPolicyElement@PolicyModel@@IEAA@XZ; PolicyModel::CPolicyElement::CPolicyElement(void)
0x14000a5b6  nop
0x14000a5b7  lea     rax, ??_7CId@PolicyModel@@6B@; const PolicyModel::CId::`vftable'
0x14000a5be  mov     [rbp+57h+var_60], rax
0x14000a5c2  movups  xmm0, xmmword ptr [rbx]
0x14000a5c5  movdqu  [rbp+57h+var_58], xmm0
0x14000a5ca  lea     rax, WPP_GLOBAL_Control
0x14000a5d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a5d8  cmp     rcx, rax
0x14000a5db  jz      short loc_14000A5F9
0x14000a5dd  test    byte ptr [rcx+1Ch], 8
0x14000a5e1  jz      short loc_14000A5F9
0x14000a5e3  mov     edx, 0Bh
0x14000a5e8  lea     r8, WPP_58eb30b6f4dc383367536c56e7c2c555_Traceguids
0x14000a5ef  mov     rcx, [rcx+10h]
0x14000a5f3  call    WPP_SF_
0x14000a5f8  nop
0x14000a5f9  movups  xmm0, [rbp+57h+var_58]
0x14000a5fd  movdqu  xmmword ptr [rdi+18h], xmm0
0x14000a602  lea     rcx, [rbp+57h+var_60]; this
0x14000a606  call    ??1CId@PolicyModel@@UEAA@XZ; PolicyModel::CId::~CId(void)
0x14000a60b  nop
0x14000a60c  xor     r8d, r8d
0x14000a60f  mov     dl, 1
0x14000a611  lea     rcx, [rbp+57h+var_80]
0x14000a615  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a61a  lea     rdx, aName; "Name"
0x14000a621  lea     rcx, [rbp+57h+var_80]
0x14000a625  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a62a  nop
0x14000a62b  lea     r8, [rbp+57h+var_80]
0x14000a62f  lea     rdx, [rbp+57h+var_60]
0x14000a633  mov     rcx, rsi
0x14000a636  call    ?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Sharp::Util::Xml::CNode::ParseStringAttribute(std::wstring const &)
0x14000a63b  nop
0x14000a63c  lea     rcx, [rdi+28h]
0x14000a640  mov     rdx, rax
0x14000a643  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14000a648  nop
0x14000a649  xor     r8d, r8d
0x14000a64c  mov     dl, 1
0x14000a64e  lea     rcx, [rbp+57h+var_60]
0x14000a652  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a657  nop
0x14000a658  xor     r8d, r8d
0x14000a65b  mov     dl, 1
0x14000a65d  lea     rcx, [rbp+57h+var_80]
0x14000a661  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a666  lea     rdx, aDescription; "Description"
0x14000a66d  lea     rcx, [rbp+57h+var_80]
0x14000a671  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a676  nop
0x14000a677  lea     r8, [rbp+57h+var_80]
0x14000a67b  lea     rdx, [rbp+57h+var_60]
0x14000a67f  mov     rcx, rsi
0x14000a682  call    ?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Sharp::Util::Xml::CNode::ParseStringAttribute(std::wstring const &)
0x14000a687  nop
0x14000a688  lea     rcx, [rdi+48h]
0x14000a68c  mov     rdx, rax
0x14000a68f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14000a694  nop
0x14000a695  xor     r8d, r8d
0x14000a698  mov     dl, 1
0x14000a69a  lea     rcx, [rbp+57h+var_60]
0x14000a69e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a6a3  nop
0x14000a6a4  xor     r8d, r8d
0x14000a6a7  mov     dl, 1
0x14000a6a9  lea     rcx, [rbp+57h+var_80]
0x14000a6ad  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a6b2  lea     rdx, aUserorgroupsid; "UserOrGroupSid"
0x14000a6b9  lea     rcx, [rbp+57h+var_80]
0x14000a6bd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a6c2  nop
0x14000a6c3  lea     r8, [rbp+57h+var_80]
0x14000a6c7  lea     rdx, [rbp+57h+var_60]
0x14000a6cb  mov     rcx, rsi
0x14000a6ce  call    ?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Sharp::Util::Xml::CNode::ParseStringAttribute(std::wstring const &)
0x14000a6d3  nop
0x14000a6d4  lea     rcx, [rdi+68h]
0x14000a6d8  mov     rdx, rax
0x14000a6db  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14000a6e0  nop
0x14000a6e1  xor     r8d, r8d
0x14000a6e4  mov     dl, 1
0x14000a6e6  lea     rcx, [rbp+57h+var_60]
0x14000a6ea  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a6ef  nop
0x14000a6f0  xor     r8d, r8d
0x14000a6f3  mov     dl, 1
0x14000a6f5  lea     rcx, [rbp+57h+var_80]
0x14000a6f9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a6fe  lea     rdx, aAction; "Action"
0x14000a705  lea     rcx, [rbp+57h+var_80]
0x14000a709  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a70e  nop
0x14000a70f  lea     r8, [rbp+57h+var_80]
0x14000a713  lea     rdx, [rbp+57h+var_40]
0x14000a717  mov     rcx, rsi
0x14000a71a  call    ?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Sharp::Util::Xml::CNode::ParseStringAttribute(std::wstring const &)
0x14000a71f  nop
0x14000a720  xor     r8d, r8d
0x14000a723  mov     dl, 1
0x14000a725  lea     rcx, [rbp+57h+var_80]
0x14000a729  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a72e  lea     rdx, aAllow; "Allow"
0x14000a735  lea     rcx, [rbp+57h+var_80]
0x14000a739  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a73e  nop
0x14000a73f  mov     rdx, rax
0x14000a742  lea     rcx, [rbp+57h+var_40]
0x14000a746  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator==<ushort>(std::wstring const &,std::wstring const &)
0x14000a74b  movzx   ebx, al
0x14000a74e  xor     r8d, r8d
0x14000a751  mov     dl, 1
0x14000a753  lea     rcx, [rbp+57h+var_80]
0x14000a757  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a75c  xor     ebx, 1
0x14000a75f  mov     [rdi+88h], ebx
0x14000a765  lea     rdx, aConditions; "Conditions"
0x14000a76c  lea     rcx, [rbp+57h+var_80]
0x14000a770  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a775  nop
0x14000a776  lea     rdx, [rbp+57h+var_80]
0x14000a77a  mov     rcx, rsi
0x14000a77d  call    ?HasSpecificChild@CNode@Xml@Util@Sharp@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::HasSpecificChild(std::wstring const &)
0x14000a782  mov     bl, al
0x14000a784  xor     r8d, r8d
0x14000a787  mov     dl, 1
0x14000a789  lea     rcx, [rbp+57h+var_80]
0x14000a78d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a792  test    bl, bl
0x14000a794  jz      loc_14000A86D
0x14000a79a  lea     rdx, aConditions; "Conditions"
0x14000a7a1  lea     rcx, [rbp+57h+var_80]
0x14000a7a5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a7aa  nop
0x14000a7ab  lea     r8, [rbp+57h+var_80]
0x14000a7af  lea     rdx, [rbp+57h+var_90]
0x14000a7b3  mov     rcx, rsi
0x14000a7b6  call    ?GetSpecificChild@CNode@Xml@Util@Sharp@@QEBA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::GetSpecificChild(std::wstring const &)
0x14000a7bb  nop
0x14000a7bc  xor     r8d, r8d
0x14000a7bf  mov     dl, 1
0x14000a7c1  lea     rcx, [rbp+57h+var_80]
0x14000a7c5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a7ca  lea     rdx, aFilepublisherc; "FilePublisherCondition"
0x14000a7d1  lea     rcx, [rbp+57h+var_80]
0x14000a7d5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a7da  nop
0x14000a7db  mov     r9b, 1
0x14000a7de  lea     r8, [rbp+57h+var_80]
0x14000a7e2  lea     rdx, [rbp+57h+var_90]
0x14000a7e6  mov     rcx, rdi
0x14000a7e9  call    ??$DeserializeConditions@VCFilePublisherCondition@PolicyModel@@@CRule@PolicyModel@@AEAAXAEBVCNode@Xml@Util@Sharp@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; PolicyModel::CRule::DeserializeConditions<PolicyModel::CFilePublisherCondition>(Sharp::Util::Xml::CNode const &,std::wstring const &,bool)
0x14000a7ee  nop
0x14000a7ef  xor     r8d, r8d
0x14000a7f2  mov     dl, 1
0x14000a7f4  lea     rcx, [rbp+57h+var_80]
0x14000a7f8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a7fd  lea     rdx, aFilepathcondit; "FilePathCondition"
0x14000a804  lea     rcx, [rbp+57h+var_80]
0x14000a808  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a80d  nop
0x14000a80e  mov     r9b, 1
0x14000a811  lea     r8, [rbp+57h+var_80]
0x14000a815  lea     rdx, [rbp+57h+var_90]
0x14000a819  mov     rcx, rdi
0x14000a81c  call    ??$DeserializeConditions@VCFilePathCondition@PolicyModel@@@CRule@PolicyModel@@AEAAXAEBVCNode@Xml@Util@Sharp@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; PolicyModel::CRule::DeserializeConditions<PolicyModel::CFilePathCondition>(Sharp::Util::Xml::CNode const &,std::wstring const &,bool)
0x14000a821  nop
0x14000a822  xor     r8d, r8d
0x14000a825  mov     dl, 1
0x14000a827  lea     rcx, [rbp+57h+var_80]
0x14000a82b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a830  lea     rdx, aFilehashcondit; "FileHashCondition"
0x14000a837  lea     rcx, [rbp+57h+var_80]
0x14000a83b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a840  nop
0x14000a841  mov     r9b, 1
0x14000a844  lea     r8, [rbp+57h+var_80]
0x14000a848  lea     rdx, [rbp+57h+var_90]
0x14000a84c  mov     rcx, rdi
0x14000a84f  call    ??$DeserializeConditions@VCFileHashCondition@PolicyModel@@@CRule@PolicyModel@@AEAAXAEBVCNode@Xml@Util@Sharp@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; PolicyModel::CRule::DeserializeConditions<PolicyModel::CFileHashCondition>(Sharp::Util::Xml::CNode const &,std::wstring const &,bool)
0x14000a854  nop
0x14000a855  xor     r8d, r8d
0x14000a858  mov     dl, 1
0x14000a85a  lea     rcx, [rbp+57h+var_80]
0x14000a85e  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a863  nop
0x14000a864  lea     rcx, [rbp+57h+var_90]; this
0x14000a868  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x14000a86d  lea     rdx, aExceptions; "Exceptions"
0x14000a874  lea     rcx, [rbp+57h+var_80]
0x14000a878  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a87d  nop
0x14000a87e  lea     rdx, [rbp+57h+var_80]
0x14000a882  mov     rcx, rsi
0x14000a885  call    ?HasSpecificChild@CNode@Xml@Util@Sharp@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::HasSpecificChild(std::wstring const &)
0x14000a88a  mov     bl, al
0x14000a88c  xor     r8d, r8d
0x14000a88f  mov     dl, 1
0x14000a891  lea     rcx, [rbp+57h+var_80]
0x14000a895  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a89a  test    bl, bl
0x14000a89c  jz      loc_14000A976
0x14000a8a2  lea     rdx, aExceptions; "Exceptions"
0x14000a8a9  lea     rcx, [rbp+57h+var_80]
0x14000a8ad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a8b2  nop
0x14000a8b3  lea     r8, [rbp+57h+var_80]
0x14000a8b7  lea     rdx, [rbp+57h+var_90]
0x14000a8bb  mov     rcx, rsi
0x14000a8be  call    ?GetSpecificChild@CNode@Xml@Util@Sharp@@QEBA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::GetSpecificChild(std::wstring const &)
0x14000a8c3  nop
0x14000a8c4  xor     r8d, r8d
0x14000a8c7  mov     dl, 1
0x14000a8c9  lea     rcx, [rbp+57h+var_80]
0x14000a8cd  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a8d2  lea     rdx, aFilepublisherc; "FilePublisherCondition"
0x14000a8d9  lea     rcx, [rbp+57h+var_80]
0x14000a8dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a8e2  nop
0x14000a8e3  xor     r9d, r9d
0x14000a8e6  lea     r8, [rbp+57h+var_80]
0x14000a8ea  lea     rdx, [rbp+57h+var_90]
0x14000a8ee  mov     rcx, rdi
0x14000a8f1  call    ??$DeserializeConditions@VCFilePublisherCondition@PolicyModel@@@CRule@PolicyModel@@AEAAXAEBVCNode@Xml@Util@Sharp@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; PolicyModel::CRule::DeserializeConditions<PolicyModel::CFilePublisherCondition>(Sharp::Util::Xml::CNode const &,std::wstring const &,bool)
0x14000a8f6  nop
0x14000a8f7  xor     r8d, r8d
0x14000a8fa  mov     dl, 1
0x14000a8fc  lea     rcx, [rbp+57h+var_80]
0x14000a900  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a905  lea     rdx, aFilepathcondit; "FilePathCondition"
0x14000a90c  lea     rcx, [rbp+57h+var_80]
0x14000a910  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a915  nop
0x14000a916  xor     r9d, r9d
0x14000a919  lea     r8, [rbp+57h+var_80]
0x14000a91d  lea     rdx, [rbp+57h+var_90]
0x14000a921  mov     rcx, rdi
0x14000a924  call    ??$DeserializeConditions@VCFilePathCondition@PolicyModel@@@CRule@PolicyModel@@AEAAXAEBVCNode@Xml@Util@Sharp@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; PolicyModel::CRule::DeserializeConditions<PolicyModel::CFilePathCondition>(Sharp::Util::Xml::CNode const &,std::wstring const &,bool)
0x14000a929  nop
0x14000a92a  xor     r8d, r8d
0x14000a92d  mov     dl, 1
0x14000a92f  lea     rcx, [rbp+57h+var_80]
0x14000a933  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a938  lea     rdx, aFilehashcondit; "FileHashCondition"
0x14000a93f  lea     rcx, [rbp+57h+var_80]
0x14000a943  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000a948  nop
0x14000a949  xor     r9d, r9d
0x14000a94c  lea     r8, [rbp+57h+var_80]
0x14000a950  lea     rdx, [rbp+57h+var_90]
0x14000a954  mov     rcx, rdi
0x14000a957  call    ??$DeserializeConditions@VCFileHashCondition@PolicyModel@@@CRule@PolicyModel@@AEAAXAEBVCNode@Xml@Util@Sharp@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; PolicyModel::CRule::DeserializeConditions<PolicyModel::CFileHashCondition>(Sharp::Util::Xml::CNode const &,std::wstring const &,bool)
0x14000a95c  nop
0x14000a95d  xor     r8d, r8d
0x14000a960  mov     dl, 1
0x14000a962  lea     rcx, [rbp+57h+var_80]
0x14000a966  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a96b  nop
0x14000a96c  lea     rcx, [rbp+57h+var_90]; this
0x14000a970  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x14000a975  nop
0x14000a976  xor     r8d, r8d
0x14000a979  mov     dl, 1
0x14000a97b  lea     rcx, [rbp+57h+var_40]
0x14000a97f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000a984  mov     rcx, [rbp+57h+var_20]
0x14000a988  xor     rcx, rsp; StackCookie
0x14000a98b  call    __security_check_cookie
0x14000a990  mov     rbx, [rsp+0B0h+arg_10]
0x14000a998  add     rsp, 0A0h
0x14000a99f  pop     rdi
0x14000a9a0  pop     rsi
0x14000a9a1  pop     rbp
0x14000a9a2  retn
```
