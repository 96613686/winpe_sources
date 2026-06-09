# PolicyModel::CFileVersionRange::Serialize(Sharp::Util::Xml::CNode &)

- ea: `0x14000f610`
- end: `0x14000f737`
- name: `?Serialize@CFileVersionRange@PolicyModel@@MEBAXAEAVCNode@Xml@Util@Sharp@@@Z`
- size: `295`
- prototype: `void __fastcall(PolicyModel::CFileVersionRange *__hidden this, struct Sharp::Util::Xml::CNode *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x140008368`
- `0x1400099b4`
- `0x14000f344`
- `0x14000f390`
- `0x14000f514`
- `0x14000f610`
- `0x140012604`
- `0x140013b10`

## pseudocode

```c
void __fastcall PolicyModel::CFileVersionRange::Serialize(
        PolicyModel::CFileVersionRange *this,
        struct Sharp::Util::Xml::CNode *a2)
{
  const struct PolicyModel::CFileVersion *LowSection; // rax
  const OLECHAR *v5; // rbx
  const struct PolicyModel::CFileVersion *HighSection; // rax
  const OLECHAR *v7; // rbx
  unsigned __int16 v8[16]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v9[4]; // [rsp+40h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_e2dc33e2e1ab38bca8052973938c015d_Traceguids);
  LowSection = PolicyModel::CFileVersionRange::GetLowSection((PolicyModel::CFileVersionRange *)((char *)this - 8));
  v5 = (const OLECHAR *)PolicyModel::CFileVersionRange::RangeSectionToString(v9, LowSection);
  std::wstring::wstring((__int64)v8);
  Sharp::Util::Xml::CNode::CreateAttribute((__int64)a2, v8, v5);
  std::wstring::_Tidy(v8, 1, 0);
  std::wstring::_Tidy(v9, 1, 0);
  HighSection = PolicyModel::CFileVersionRange::GetHighSection((PolicyModel::CFileVersionRange *)((char *)this - 8));
  v7 = (const OLECHAR *)PolicyModel::CFileVersionRange::RangeSectionToString(v9, HighSection);
  std::wstring::wstring((__int64)v8);
  Sharp::Util::Xml::CNode::CreateAttribute((__int64)a2, v8, v7);
  std::wstring::_Tidy(v8, 1, 0);
  std::wstring::_Tidy(v9, 1, 0);
}

```

## disassembly

```asm
0x14000f610  mov     [rsp+arg_10], rbx
0x14000f615  mov     [rsp+arg_18], rsi
0x14000f61a  push    rdi
0x14000f61b  sub     rsp, 70h
0x14000f61f  mov     rax, cs:__security_cookie
0x14000f626  xor     rax, rsp
0x14000f629  mov     [rsp+78h+var_18], rax
0x14000f62e  mov     rsi, rdx
0x14000f631  mov     rdi, rcx
0x14000f634  lea     rax, WPP_GLOBAL_Control
0x14000f63b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f642  cmp     rcx, rax
0x14000f645  jz      short loc_14000F662
0x14000f647  test    byte ptr [rcx+1Ch], 8
0x14000f64b  jz      short loc_14000F662
0x14000f64d  mov     edx, 13h
0x14000f652  lea     r8, WPP_e2dc33e2e1ab38bca8052973938c015d_Traceguids
0x14000f659  mov     rcx, [rcx+10h]
0x14000f65d  call    WPP_SF_
0x14000f662  lea     rcx, [rdi-8]; this
0x14000f666  call    ?GetLowSection@CFileVersionRange@PolicyModel@@QEBAPEBVCFileVersion@2@XZ; PolicyModel::CFileVersionRange::GetLowSection(void)
0x14000f66b  mov     rdx, rax
0x14000f66e  lea     rcx, [rsp+78h+var_38]
0x14000f673  call    ?RangeSectionToString@CFileVersionRange@PolicyModel@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVCFileVersion@2@@Z; PolicyModel::CFileVersionRange::RangeSectionToString(PolicyModel::CFileVersion const *)
0x14000f678  mov     rbx, rax
0x14000f67b  lea     rdx, aLowsection; "LowSection"
0x14000f682  lea     rcx, [rsp+78h+var_58]
0x14000f687  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000f68c  nop
0x14000f68d  mov     r8, rbx
0x14000f690  lea     rdx, [rsp+78h+var_58]
0x14000f695  mov     rcx, rsi
0x14000f698  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,std::wstring const &)
0x14000f69d  nop
0x14000f69e  xor     r8d, r8d
0x14000f6a1  mov     dl, 1
0x14000f6a3  lea     rcx, [rsp+78h+var_58]
0x14000f6a8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000f6ad  nop
0x14000f6ae  xor     r8d, r8d
0x14000f6b1  mov     dl, 1
0x14000f6b3  lea     rcx, [rsp+78h+var_38]
0x14000f6b8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000f6bd  lea     rcx, [rdi-8]; this
0x14000f6c1  call    ?GetHighSection@CFileVersionRange@PolicyModel@@QEBAPEBVCFileVersion@2@XZ; PolicyModel::CFileVersionRange::GetHighSection(void)
0x14000f6c6  mov     rdx, rax
0x14000f6c9  lea     rcx, [rsp+78h+var_38]
0x14000f6ce  call    ?RangeSectionToString@CFileVersionRange@PolicyModel@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVCFileVersion@2@@Z; PolicyModel::CFileVersionRange::RangeSectionToString(PolicyModel::CFileVersion const *)
0x14000f6d3  mov     rbx, rax
0x14000f6d6  lea     rdx, aHighsection; "HighSection"
0x14000f6dd  lea     rcx, [rsp+78h+var_58]
0x14000f6e2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000f6e7  nop
0x14000f6e8  mov     r8, rbx
0x14000f6eb  lea     rdx, [rsp+78h+var_58]
0x14000f6f0  mov     rcx, rsi
0x14000f6f3  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,std::wstring const &)
0x14000f6f8  nop
0x14000f6f9  xor     r8d, r8d
0x14000f6fc  mov     dl, 1
0x14000f6fe  lea     rcx, [rsp+78h+var_58]
0x14000f703  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000f708  nop
0x14000f709  xor     r8d, r8d
0x14000f70c  mov     dl, 1
0x14000f70e  lea     rcx, [rsp+78h+var_38]
0x14000f713  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000f718  mov     rcx, [rsp+78h+var_18]
0x14000f71d  xor     rcx, rsp; StackCookie
0x14000f720  call    __security_check_cookie
0x14000f725  lea     r11, [rsp+78h+var_8]
0x14000f72a  mov     rbx, [r11+20h]
0x14000f72e  mov     rsi, [r11+28h]
0x14000f732  mov     rsp, r11
0x14000f735  pop     rdi
0x14000f736  retn
```
