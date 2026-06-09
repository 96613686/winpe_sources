# PolicyModel::CFileVersionRange::Deserialize(Sharp::Util::Xml::CNode const &)

- ea: `0x14000f200`
- end: `0x14000f33c`
- name: `?Deserialize@CFileVersionRange@PolicyModel@@MEAAXAEBVCNode@Xml@Util@Sharp@@@Z`
- size: `316`
- prototype: `void __fastcall(PolicyModel::CFileVersionRange *__hidden this, const struct Sharp::Util::Xml::CNode *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x140008368`
- `0x1400099b4`
- `0x14000f200`
- `0x14000f44c`
- `0x14000f740`
- `0x14000f7a8`
- `0x1400130ec`
- `0x140013b10`

## pseudocode

```c
void __fastcall PolicyModel::CFileVersionRange::Deserialize(
        PolicyModel::CFileVersionRange *this,
        const struct Sharp::Util::Xml::CNode *a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  _BYTE v6[8]; // [rsp+20h] [rbp-29h] BYREF
  _BYTE *v7; // [rsp+28h] [rbp-21h]
  _BYTE *v8; // [rsp+30h] [rbp-19h]
  _QWORD v9[4]; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v10[4]; // [rsp+58h] [rbp+Fh] BYREF
  _QWORD v11[4]; // [rsp+78h] [rbp+2Fh] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_e2dc33e2e1ab38bca8052973938c015d_Traceguids);
  std::wstring::wstring((__int64)v9);
  Sharp::Util::Xml::CNode::ParseStringAttribute(a2, v11, v9);
  std::wstring::_Tidy(v9, 1, 0);
  v7 = v6;
  v4 = PolicyModel::CFileVersionRange::RangeSectionFromString(v6, v11);
  PolicyModel::CFileVersionRange::SetLowSection((char *)this - 8, v4);
  std::wstring::wstring((__int64)v9);
  Sharp::Util::Xml::CNode::ParseStringAttribute(a2, v10, v9);
  std::wstring::_Tidy(v9, 1, 0);
  v8 = v6;
  v5 = PolicyModel::CFileVersionRange::RangeSectionFromString(v6, v10);
  PolicyModel::CFileVersionRange::SetHighSection((char *)this - 8, v5);
  std::wstring::_Tidy(v10, 1, 0);
  std::wstring::_Tidy(v11, 1, 0);
}

```

## disassembly

```asm
0x14000f200  mov     [rsp-8+arg_10], rbx
0x14000f205  mov     [rsp-8+arg_18], rdi
0x14000f20a  push    rbp
0x14000f20b  lea     rbp, [rsp-57h]
0x14000f210  sub     rsp, 0A0h
0x14000f217  mov     rax, cs:__security_cookie
0x14000f21e  xor     rax, rsp
0x14000f221  mov     [rbp+57h+var_8], rax
0x14000f225  mov     rdi, rdx
0x14000f228  mov     rbx, rcx
0x14000f22b  lea     rax, WPP_GLOBAL_Control
0x14000f232  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f239  cmp     rcx, rax
0x14000f23c  jz      short loc_14000F259
0x14000f23e  test    byte ptr [rcx+1Ch], 8
0x14000f242  jz      short loc_14000F259
0x14000f244  mov     edx, 14h
0x14000f249  lea     r8, WPP_e2dc33e2e1ab38bca8052973938c015d_Traceguids
0x14000f250  mov     rcx, [rcx+10h]
0x14000f254  call    WPP_SF_
0x14000f259  lea     rdx, aLowsection; "LowSection"
0x14000f260  lea     rcx, [rbp+57h+var_68]
0x14000f264  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000f269  nop
0x14000f26a  lea     r8, [rbp+57h+var_68]
0x14000f26e  lea     rdx, [rbp+57h+var_28]
0x14000f272  mov     rcx, rdi
0x14000f275  call    ?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Sharp::Util::Xml::CNode::ParseStringAttribute(std::wstring const &)
0x14000f27a  nop
0x14000f27b  xor     r8d, r8d
0x14000f27e  mov     dl, 1
0x14000f280  lea     rcx, [rbp+57h+var_68]
0x14000f284  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000f289  lea     rax, [rbp+57h+var_80]
0x14000f28d  mov     [rbp+57h+var_78], rax
0x14000f291  lea     rdx, [rbp+57h+var_28]
0x14000f295  lea     rcx, [rbp+57h+var_80]
0x14000f299  call    ?RangeSectionFromString@CFileVersionRange@PolicyModel@@CA?AV?$CSharedPtr@VCFileVersion@PolicyModel@@@Util@Sharp@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyModel::CFileVersionRange::RangeSectionFromString(std::wstring const &)
0x14000f29e  nop
0x14000f29f  mov     rdx, rax
0x14000f2a2  lea     rcx, [rbx-8]
0x14000f2a6  call    ?SetLowSection@CFileVersionRange@PolicyModel@@QEAAXV?$CSharedPtr@VCFileVersion@PolicyModel@@@Util@Sharp@@@Z; PolicyModel::CFileVersionRange::SetLowSection(Sharp::Util::CSharedPtr<PolicyModel::CFileVersion>)
0x14000f2ab  lea     rdx, aHighsection; "HighSection"
0x14000f2b2  lea     rcx, [rbp+57h+var_68]
0x14000f2b6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000f2bb  nop
0x14000f2bc  lea     r8, [rbp+57h+var_68]
0x14000f2c0  lea     rdx, [rbp+57h+var_48]
0x14000f2c4  mov     rcx, rdi
0x14000f2c7  call    ?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Sharp::Util::Xml::CNode::ParseStringAttribute(std::wstring const &)
0x14000f2cc  nop
0x14000f2cd  xor     r8d, r8d
0x14000f2d0  mov     dl, 1
0x14000f2d2  lea     rcx, [rbp+57h+var_68]
0x14000f2d6  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000f2db  lea     rax, [rbp+57h+var_80]
0x14000f2df  mov     [rbp+57h+var_70], rax
0x14000f2e3  lea     rdx, [rbp+57h+var_48]
0x14000f2e7  lea     rcx, [rbp+57h+var_80]
0x14000f2eb  call    ?RangeSectionFromString@CFileVersionRange@PolicyModel@@CA?AV?$CSharedPtr@VCFileVersion@PolicyModel@@@Util@Sharp@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyModel::CFileVersionRange::RangeSectionFromString(std::wstring const &)
0x14000f2f0  nop
0x14000f2f1  mov     rdx, rax
0x14000f2f4  lea     rcx, [rbx-8]
0x14000f2f8  call    ?SetHighSection@CFileVersionRange@PolicyModel@@QEAAXV?$CSharedPtr@VCFileVersion@PolicyModel@@@Util@Sharp@@@Z; PolicyModel::CFileVersionRange::SetHighSection(Sharp::Util::CSharedPtr<PolicyModel::CFileVersion>)
0x14000f2fd  nop
0x14000f2fe  xor     r8d, r8d
0x14000f301  mov     dl, 1
0x14000f303  lea     rcx, [rbp+57h+var_48]
0x14000f307  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000f30c  nop
0x14000f30d  xor     r8d, r8d
0x14000f310  mov     dl, 1
0x14000f312  lea     rcx, [rbp+57h+var_28]
0x14000f316  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000f31b  mov     rcx, [rbp+57h+var_8]
0x14000f31f  xor     rcx, rsp; StackCookie
0x14000f322  call    __security_check_cookie
0x14000f327  lea     r11, [rsp+0A0h+var_s0]
0x14000f32f  mov     rbx, [r11+20h]
0x14000f333  mov     rdi, [r11+28h]
0x14000f337  mov     rsp, r11
0x14000f33a  pop     rbp
0x14000f33b  retn
```
