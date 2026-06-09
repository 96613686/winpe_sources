# PolicyModel::CFilePublisherCondition::Deserialize(Sharp::Util::Xml::CNode const &)

- ea: `0x14000cba0`
- end: `0x14000cd70`
- name: `?Deserialize@CFilePublisherCondition@PolicyModel@@MEAAXAEBVCNode@Xml@Util@Sharp@@@Z`
- size: `464`
- prototype: `void __fastcall(PolicyModel::CFilePublisherCondition *__hidden this, const struct Sharp::Util::Xml::CNode *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x140008368`
- `0x1400099b4`
- `0x14000a0d4`
- `0x14000cba0`
- `0x140012138`
- `0x140012b94`
- `0x140012f20`
- `0x1400130ec`
- `0x140013b10`
- `0x140016010`

## pseudocode

```c
void __fastcall PolicyModel::CFilePublisherCondition::Deserialize(
        PolicyModel::CFilePublisherCondition *this,
        const struct Sharp::Util::Xml::CNode *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  char HasSpecificChild; // bl
  _QWORD v8[4]; // [rsp+20h] [rbp-50h] BYREF
  _QWORD v9[4]; // [rsp+40h] [rbp-30h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_f3cd61ca77c6343f41027d72af25da0d_Traceguids);
  std::wstring::wstring((__int64)v8);
  v4 = Sharp::Util::Xml::CNode::ParseStringAttribute(a2, v9, v8);
  std::wstring::operator=((__int64)this + 8, v4);
  std::wstring::_Tidy(v9, 1, 0);
  std::wstring::_Tidy(v8, 1, 0);
  std::wstring::wstring((__int64)v8);
  v5 = Sharp::Util::Xml::CNode::ParseStringAttribute(a2, v9, v8);
  std::wstring::operator=((__int64)this + 40, v5);
  std::wstring::_Tidy(v9, 1, 0);
  std::wstring::_Tidy(v8, 1, 0);
  std::wstring::wstring((__int64)v8);
  v6 = Sharp::Util::Xml::CNode::ParseStringAttribute(a2, v9, v8);
  std::wstring::operator=((__int64)this + 72, v6);
  std::wstring::_Tidy(v9, 1, 0);
  std::wstring::_Tidy(v8, 1, 0);
  std::wstring::wstring((__int64)v8);
  HasSpecificChild = Sharp::Util::Xml::CNode::HasSpecificChild(a2, v8);
  std::wstring::_Tidy(v8, 1, 0);
  if ( HasSpecificChild )
  {
    std::wstring::wstring((__int64)v9);
    Sharp::Util::Xml::CNode::GetSpecificChild(a2, v8, v9);
    std::wstring::_Tidy(v9, 1, 0);
    (*(void (__fastcall **)(char *, _QWORD *))(*((_QWORD *)this + 14) + 16LL))((char *)this + 112, v8);
    Sharp::Util::Xml::CNode::~CNode((Sharp::Util::Xml::CNode *)v8);
  }
}

```

## disassembly

```asm
0x14000cba0  mov     [rsp-18h+arg_10], rbx
0x14000cba5  push    rbp
0x14000cba6  push    rsi
0x14000cba7  push    rdi
0x14000cba8  mov     rbp, rsp
0x14000cbab  sub     rsp, 70h
0x14000cbaf  mov     rax, cs:__security_cookie
0x14000cbb6  xor     rax, rsp
0x14000cbb9  mov     [rbp+var_10], rax
0x14000cbbd  mov     rdi, rdx
0x14000cbc0  mov     rsi, rcx
0x14000cbc3  lea     rax, WPP_GLOBAL_Control
0x14000cbca  mov     rcx, cs:WPP_GLOBAL_Control
0x14000cbd1  cmp     rcx, rax
0x14000cbd4  jz      short loc_14000CBF1
0x14000cbd6  test    byte ptr [rcx+1Ch], 8
0x14000cbda  jz      short loc_14000CBF1
0x14000cbdc  mov     edx, 0Dh
0x14000cbe1  lea     r8, WPP_f3cd61ca77c6343f41027d72af25da0d_Traceguids
0x14000cbe8  mov     rcx, [rcx+10h]
0x14000cbec  call    WPP_SF_
0x14000cbf1  lea     rdx, aPublishername; "PublisherName"
0x14000cbf8  lea     rcx, [rbp+var_50]
0x14000cbfc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000cc01  nop
0x14000cc02  lea     r8, [rbp+var_50]
0x14000cc06  lea     rdx, [rbp+var_30]
0x14000cc0a  mov     rcx, rdi
0x14000cc0d  call    ?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Sharp::Util::Xml::CNode::ParseStringAttribute(std::wstring const &)
0x14000cc12  nop
0x14000cc13  lea     rcx, [rsi+8]
0x14000cc17  mov     rdx, rax
0x14000cc1a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14000cc1f  nop
0x14000cc20  xor     r8d, r8d
0x14000cc23  mov     dl, 1
0x14000cc25  lea     rcx, [rbp+var_30]
0x14000cc29  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000cc2e  nop
0x14000cc2f  xor     r8d, r8d
0x14000cc32  mov     dl, 1
0x14000cc34  lea     rcx, [rbp+var_50]
0x14000cc38  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000cc3d  lea     rdx, aProductname; "ProductName"
0x14000cc44  lea     rcx, [rbp+var_50]
0x14000cc48  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000cc4d  nop
0x14000cc4e  lea     r8, [rbp+var_50]
0x14000cc52  lea     rdx, [rbp+var_30]
0x14000cc56  mov     rcx, rdi
0x14000cc59  call    ?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Sharp::Util::Xml::CNode::ParseStringAttribute(std::wstring const &)
0x14000cc5e  nop
0x14000cc5f  lea     rcx, [rsi+28h]
0x14000cc63  mov     rdx, rax
0x14000cc66  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14000cc6b  nop
0x14000cc6c  xor     r8d, r8d
0x14000cc6f  mov     dl, 1
0x14000cc71  lea     rcx, [rbp+var_30]
0x14000cc75  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000cc7a  nop
0x14000cc7b  xor     r8d, r8d
0x14000cc7e  mov     dl, 1
0x14000cc80  lea     rcx, [rbp+var_50]
0x14000cc84  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000cc89  lea     rdx, aBinaryname; "BinaryName"
0x14000cc90  lea     rcx, [rbp+var_50]
0x14000cc94  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000cc99  nop
0x14000cc9a  lea     r8, [rbp+var_50]
0x14000cc9e  lea     rdx, [rbp+var_30]
0x14000cca2  mov     rcx, rdi
0x14000cca5  call    ?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Sharp::Util::Xml::CNode::ParseStringAttribute(std::wstring const &)
0x14000ccaa  nop
0x14000ccab  lea     rcx, [rsi+48h]
0x14000ccaf  mov     rdx, rax
0x14000ccb2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14000ccb7  nop
0x14000ccb8  xor     r8d, r8d
0x14000ccbb  mov     dl, 1
0x14000ccbd  lea     rcx, [rbp+var_30]
0x14000ccc1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000ccc6  nop
0x14000ccc7  xor     r8d, r8d
0x14000ccca  mov     dl, 1
0x14000cccc  lea     rcx, [rbp+var_50]
0x14000ccd0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000ccd5  lea     rdx, aBinaryversionr; "BinaryVersionRange"
0x14000ccdc  lea     rcx, [rbp+var_50]
0x14000cce0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000cce5  nop
0x14000cce6  lea     rdx, [rbp+var_50]
0x14000ccea  mov     rcx, rdi
0x14000cced  call    ?HasSpecificChild@CNode@Xml@Util@Sharp@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::HasSpecificChild(std::wstring const &)
0x14000ccf2  mov     bl, al
0x14000ccf4  xor     r8d, r8d
0x14000ccf7  mov     dl, 1
0x14000ccf9  lea     rcx, [rbp+var_50]
0x14000ccfd  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000cd02  test    bl, bl
0x14000cd04  jz      short loc_14000CD54
0x14000cd06  lea     rdx, aBinaryversionr; "BinaryVersionRange"
0x14000cd0d  lea     rcx, [rbp+var_30]
0x14000cd11  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000cd16  nop
0x14000cd17  lea     r8, [rbp+var_30]
0x14000cd1b  lea     rdx, [rbp+var_50]
0x14000cd1f  mov     rcx, rdi
0x14000cd22  call    ?GetSpecificChild@CNode@Xml@Util@Sharp@@QEBA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::GetSpecificChild(std::wstring const &)
0x14000cd27  nop
0x14000cd28  xor     r8d, r8d
0x14000cd2b  mov     dl, 1
0x14000cd2d  lea     rcx, [rbp+var_30]
0x14000cd31  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000cd36  lea     rcx, [rsi+70h]
0x14000cd3a  mov     rax, [rcx]
0x14000cd3d  lea     rdx, [rbp+var_50]
0x14000cd41  mov     rax, [rax+10h]
0x14000cd45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cd4a  nop
0x14000cd4b  lea     rcx, [rbp+var_50]; this
0x14000cd4f  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x14000cd54  mov     rcx, [rbp+var_10]
0x14000cd58  xor     rcx, rsp; StackCookie
0x14000cd5b  call    __security_check_cookie
0x14000cd60  mov     rbx, [rsp+70h+arg_10]
0x14000cd68  add     rsp, 70h
0x14000cd6c  pop     rdi
0x14000cd6d  pop     rsi
0x14000cd6e  pop     rbp
0x14000cd6f  retn
```
