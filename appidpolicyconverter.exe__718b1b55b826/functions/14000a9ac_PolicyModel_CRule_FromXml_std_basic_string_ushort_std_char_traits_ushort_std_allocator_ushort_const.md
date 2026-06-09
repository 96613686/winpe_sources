# PolicyModel::CRule::FromXml(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14000a9ac`
- end: `0x14000abed`
- name: `?FromXml@CRule@PolicyModel@@SA?AV?$CSharedPtr@VCRule@PolicyModel@@@Util@Sharp@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `577`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x140007edc`

## callees

- `0x140001d1c`
- `0x1400070e4`
- `0x140008368`
- `0x1400091c0`
- `0x1400091f4`
- `0x1400092a8`
- `0x14000935c`
- `0x140009804`
- `0x140009c34`
- `0x14000a9ac`
- `0x14000abf4`
- `0x1400118bc`
- `0x140011aa8`
- `0x140011c40`
- `0x140011d68`
- `0x140012138`
- `0x140012a74`
- `0x140013b10`

## string_xrefs

- `0x14000aaa2`: `FilePathRule`

## pseudocode

```c
__int64 __fastcall PolicyModel::CRule::FromXml(__int64 a1, __int64 a2)
{
  __int64 RootNode; // rax
  PolicyModel::CRule *v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  _BYTE v9[16]; // [rsp+20h] [rbp-79h] BYREF
  int v10; // [rsp+30h] [rbp-69h]
  _BYTE v11[16]; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v12[16]; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v13[16]; // [rsp+58h] [rbp-41h] BYREF
  __int64 v14; // [rsp+68h] [rbp-31h]
  _QWORD v15[4]; // [rsp+70h] [rbp-29h] BYREF
  _QWORD pExceptionObject[8]; // [rsp+90h] [rbp-9h] BYREF

  v14 = a1;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_d304a645fd6338ffd40dd01c834cc669_Traceguids);
  Sharp::Util::Xml::CDocument::CDocument((Sharp::Util::Xml::CDocument *)v12);
  Sharp::Util::Xml::CDocument::LoadXml(v12, a2);
  Sharp::Util::Xml::CDocument::GetRootNode(v12, v13);
  Sharp::Util::Xml::CNode::GetName(v13, v15);
  Sharp::Util::CSharedPtr<PolicyModel::CRule>::CSharedPtr<PolicyModel::CRule>(a1, 0);
  v10 = 1;
  if ( (unsigned __int8)std::operator==<unsigned short>(v15, L"FilePublisherRule") )
  {
    Sharp::Util::Xml::CDocument::CDocument((Sharp::Util::Xml::CDocument *)v9);
    Sharp::Util::Xml::CDocument::LoadXml(v9, a2);
    RootNode = Sharp::Util::Xml::CDocument::GetRootNode(v9, v11);
    v5 = PolicyModel::CXmlSerializer::Deserialize<PolicyModel::CFilePublisherRule>(RootNode);
    Sharp::Util::Xml::CNode::~CNode((Sharp::Util::Xml::CNode *)v11);
  }
  else if ( (unsigned __int8)std::operator==<unsigned short>(v15, L"FilePathRule") )
  {
    Sharp::Util::Xml::CDocument::CDocument((Sharp::Util::Xml::CDocument *)v9);
    Sharp::Util::Xml::CDocument::LoadXml(v9, a2);
    v6 = Sharp::Util::Xml::CDocument::GetRootNode(v9, v11);
    v5 = PolicyModel::CXmlSerializer::Deserialize<PolicyModel::CFilePathRule>(v6);
    Sharp::Util::Xml::CNode::~CNode((Sharp::Util::Xml::CNode *)v11);
  }
  else
  {
    if ( !(unsigned __int8)std::operator==<unsigned short>(v15, L"FileHashRule") )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_d304a645fd6338ffd40dd01c834cc669_Traceguids);
      policy_model_exception::policy_model_exception((policy_model_exception *)pExceptionObject, -2147418113);
      pExceptionObject[0] = &unsupported_policy_element_exception::`vftable';
      throw (unsupported_policy_element_exception *)pExceptionObject;
    }
    Sharp::Util::Xml::CDocument::CDocument((Sharp::Util::Xml::CDocument *)v9);
    Sharp::Util::Xml::CDocument::LoadXml(v9, a2);
    v7 = Sharp::Util::Xml::CDocument::GetRootNode(v9, v11);
    v5 = PolicyModel::CXmlSerializer::Deserialize<PolicyModel::CFileHashRule>(v7);
    Sharp::Util::Xml::CNode::~CNode((Sharp::Util::Xml::CNode *)v11);
  }
  Sharp::Util::Xml::CDocument::~CDocument((Sharp::Util::Xml::CDocument *)v9);
  Sharp::Util::CSharedPtr<PolicyModel::CRule>::Reset(a1, v5);
  std::wstring::_Tidy(v15, 1, 0);
  Sharp::Util::Xml::CNode::~CNode((Sharp::Util::Xml::CNode *)v13);
  Sharp::Util::Xml::CDocument::~CDocument((Sharp::Util::Xml::CDocument *)v12);
  return a1;
}

```

## disassembly

```asm
0x14000a9ac  mov     [rsp-8+arg_10], rbx
0x14000a9b1  push    rbp
0x14000a9b2  push    rsi
0x14000a9b3  push    rdi
0x14000a9b4  lea     rbp, [rsp-47h]
0x14000a9b9  sub     rsp, 0E0h
0x14000a9c0  mov     rax, cs:__security_cookie
0x14000a9c7  xor     rax, rsp
0x14000a9ca  mov     [rbp+57h+var_20], rax
0x14000a9ce  mov     rbx, rdx
0x14000a9d1  mov     rdi, rcx
0x14000a9d4  mov     [rbp+57h+var_88], rcx
0x14000a9d8  mov     [rbp+57h+var_C0], 0
0x14000a9df  lea     rsi, WPP_GLOBAL_Control
0x14000a9e6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a9ed  cmp     rcx, rsi
0x14000a9f0  jz      short loc_14000AA0D
0x14000a9f2  test    byte ptr [rcx+1Ch], 8
0x14000a9f6  jz      short loc_14000AA0D
0x14000a9f8  mov     edx, 12h
0x14000a9fd  lea     r8, WPP_d304a645fd6338ffd40dd01c834cc669_Traceguids
0x14000aa04  mov     rcx, [rcx+10h]
0x14000aa08  call    WPP_SF_
0x14000aa0d  lea     rcx, [rbp+57h+var_A8]; this
0x14000aa11  call    ??0CDocument@Xml@Util@Sharp@@QEAA@XZ; Sharp::Util::Xml::CDocument::CDocument(void)
0x14000aa16  nop
0x14000aa17  mov     rdx, rbx
0x14000aa1a  lea     rcx, [rbp+57h+var_A8]
0x14000aa1e  call    ?LoadXml@CDocument@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CDocument::LoadXml(std::wstring const &)
0x14000aa23  lea     rdx, [rbp+57h+var_98]
0x14000aa27  lea     rcx, [rbp+57h+var_A8]
0x14000aa2b  call    ?GetRootNode@CDocument@Xml@Util@Sharp@@QEBA?AVCNode@234@XZ; Sharp::Util::Xml::CDocument::GetRootNode(void)
0x14000aa30  nop
0x14000aa31  lea     rdx, [rbp+57h+var_80]
0x14000aa35  lea     rcx, [rbp+57h+var_98]
0x14000aa39  call    ?GetName@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Sharp::Util::Xml::CNode::GetName(void)
0x14000aa3e  nop
0x14000aa3f  xor     edx, edx
0x14000aa41  mov     rcx, rdi
0x14000aa44  call    ??0?$CSharedPtr@VCRule@PolicyModel@@@Util@Sharp@@QEAA@PEAVCRule@PolicyModel@@@Z; Sharp::Util::CSharedPtr<PolicyModel::CRule>::CSharedPtr<PolicyModel::CRule>(PolicyModel::CRule *)
0x14000aa49  mov     [rbp+57h+var_C0], 1
0x14000aa50  lea     rdx, aFilepublisherr; "FilePublisherRule"
0x14000aa57  lea     rcx, [rbp+57h+var_80]
0x14000aa5b  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x14000aa60  test    al, al
0x14000aa62  jz      short loc_14000AAA2
0x14000aa64  lea     rcx, [rbp+57h+var_D0]; this
0x14000aa68  call    ??0CDocument@Xml@Util@Sharp@@QEAA@XZ; Sharp::Util::Xml::CDocument::CDocument(void)
0x14000aa6d  nop
0x14000aa6e  mov     rdx, rbx
0x14000aa71  lea     rcx, [rbp+57h+var_D0]
0x14000aa75  call    ?LoadXml@CDocument@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CDocument::LoadXml(std::wstring const &)
0x14000aa7a  lea     rdx, [rbp+57h+var_B8]
0x14000aa7e  lea     rcx, [rbp+57h+var_D0]
0x14000aa82  call    ?GetRootNode@CDocument@Xml@Util@Sharp@@QEBA?AVCNode@234@XZ; Sharp::Util::Xml::CDocument::GetRootNode(void)
0x14000aa87  nop
0x14000aa88  mov     rcx, rax
0x14000aa8b  call    ??$Deserialize@VCFilePublisherRule@PolicyModel@@@CXmlSerializer@PolicyModel@@KAPEAVCFilePublisherRule@1@AEBVCNode@Xml@Util@Sharp@@@Z; PolicyModel::CXmlSerializer::Deserialize<PolicyModel::CFilePublisherRule>(Sharp::Util::Xml::CNode const &)
0x14000aa90  mov     rbx, rax
0x14000aa93  lea     rcx, [rbp+57h+var_B8]; this
0x14000aa97  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x14000aa9c  nop
0x14000aa9d  jmp     loc_14000AB42
0x14000aaa2  lea     rdx, aFilepathrule; "FilePathRule"
0x14000aaa9  lea     rcx, [rbp+57h+var_80]
0x14000aaad  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x14000aab2  test    al, al
0x14000aab4  jz      short loc_14000AAF1
0x14000aab6  lea     rcx, [rbp+57h+var_D0]; this
0x14000aaba  call    ??0CDocument@Xml@Util@Sharp@@QEAA@XZ; Sharp::Util::Xml::CDocument::CDocument(void)
0x14000aabf  nop
0x14000aac0  mov     rdx, rbx
0x14000aac3  lea     rcx, [rbp+57h+var_D0]
0x14000aac7  call    ?LoadXml@CDocument@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CDocument::LoadXml(std::wstring const &)
0x14000aacc  lea     rdx, [rbp+57h+var_B8]
0x14000aad0  lea     rcx, [rbp+57h+var_D0]
0x14000aad4  call    ?GetRootNode@CDocument@Xml@Util@Sharp@@QEBA?AVCNode@234@XZ; Sharp::Util::Xml::CDocument::GetRootNode(void)
0x14000aad9  nop
0x14000aada  mov     rcx, rax
0x14000aadd  call    ??$Deserialize@VCFilePathRule@PolicyModel@@@CXmlSerializer@PolicyModel@@KAPEAVCFilePathRule@1@AEBVCNode@Xml@Util@Sharp@@@Z; PolicyModel::CXmlSerializer::Deserialize<PolicyModel::CFilePathRule>(Sharp::Util::Xml::CNode const &)
0x14000aae2  mov     rbx, rax
0x14000aae5  lea     rcx, [rbp+57h+var_B8]; this
0x14000aae9  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x14000aaee  nop
0x14000aaef  jmp     short loc_14000AB42
0x14000aaf1  lea     rdx, aFilehashrule; "FileHashRule"
0x14000aaf8  lea     rcx, [rbp+57h+var_80]
0x14000aafc  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x14000ab01  test    al, al
0x14000ab03  jz      loc_14000AB9B
0x14000ab09  lea     rcx, [rbp+57h+var_D0]; this
0x14000ab0d  call    ??0CDocument@Xml@Util@Sharp@@QEAA@XZ; Sharp::Util::Xml::CDocument::CDocument(void)
0x14000ab12  nop
0x14000ab13  mov     rdx, rbx
0x14000ab16  lea     rcx, [rbp+57h+var_D0]
0x14000ab1a  call    ?LoadXml@CDocument@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CDocument::LoadXml(std::wstring const &)
0x14000ab1f  lea     rdx, [rbp+57h+var_B8]
0x14000ab23  lea     rcx, [rbp+57h+var_D0]
0x14000ab27  call    ?GetRootNode@CDocument@Xml@Util@Sharp@@QEBA?AVCNode@234@XZ; Sharp::Util::Xml::CDocument::GetRootNode(void)
0x14000ab2c  nop
0x14000ab2d  mov     rcx, rax
0x14000ab30  call    ??$Deserialize@VCFileHashRule@PolicyModel@@@CXmlSerializer@PolicyModel@@KAPEAVCFileHashRule@1@AEBVCNode@Xml@Util@Sharp@@@Z; PolicyModel::CXmlSerializer::Deserialize<PolicyModel::CFileHashRule>(Sharp::Util::Xml::CNode const &)
0x14000ab35  mov     rbx, rax
0x14000ab38  lea     rcx, [rbp+57h+var_B8]; this
0x14000ab3c  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x14000ab41  nop
0x14000ab42  lea     rcx, [rbp+57h+var_D0]; this
0x14000ab46  call    ??1CDocument@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CDocument::~CDocument(void)
0x14000ab4b  mov     rdx, rbx
0x14000ab4e  mov     rcx, rdi
0x14000ab51  call    ?Reset@?$CSharedPtr@VCRule@PolicyModel@@@Util@Sharp@@QEAAXPEAVCRule@PolicyModel@@@Z; Sharp::Util::CSharedPtr<PolicyModel::CRule>::Reset(PolicyModel::CRule *)
0x14000ab56  nop
0x14000ab57  xor     r8d, r8d
0x14000ab5a  mov     dl, 1
0x14000ab5c  lea     rcx, [rbp+57h+var_80]
0x14000ab60  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000ab65  nop
0x14000ab66  lea     rcx, [rbp+57h+var_98]; this
0x14000ab6a  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x14000ab6f  nop
0x14000ab70  lea     rcx, [rbp+57h+var_A8]; this
0x14000ab74  call    ??1CDocument@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CDocument::~CDocument(void)
0x14000ab79  mov     rax, rdi
0x14000ab7c  mov     rcx, [rbp+57h+var_20]
0x14000ab80  xor     rcx, rsp; StackCookie
0x14000ab83  call    __security_check_cookie
0x14000ab88  mov     rbx, [rsp+0F0h+arg_10]
0x14000ab90  add     rsp, 0E0h
0x14000ab97  pop     rdi
0x14000ab98  pop     rsi
0x14000ab99  pop     rbp
0x14000ab9a  retn
0x14000ab9b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aba2  cmp     rcx, rsi
0x14000aba5  jz      short loc_14000ABC2
0x14000aba7  test    byte ptr [rcx+1Ch], 1
0x14000abab  jz      short loc_14000ABC2
0x14000abad  mov     edx, 13h
0x14000abb2  lea     r8, WPP_d304a645fd6338ffd40dd01c834cc669_Traceguids
0x14000abb9  mov     rcx, [rcx+10h]
0x14000abbd  call    WPP_SF_
0x14000abc2  mov     edx, 8000FFFFh; int
0x14000abc7  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000abcb  call    ??0policy_model_exception@@QEAA@J@Z; policy_model_exception::policy_model_exception(long)
0x14000abd0  nop
0x14000abd1  lea     rax, ??_7unsupported_policy_element_exception@@6B@; const unsupported_policy_element_exception::`vftable'
0x14000abd8  mov     [rbp+57h+pExceptionObject], rax
0x14000abdc  lea     rdx, _TI4?AVunsupported_policy_element_exception@@; pThrowInfo
0x14000abe3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000abe7  call    _CxxThrowException_0
```
