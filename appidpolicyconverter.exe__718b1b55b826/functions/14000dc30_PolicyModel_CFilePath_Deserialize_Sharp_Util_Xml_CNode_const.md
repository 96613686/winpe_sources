# PolicyModel::CFilePath::Deserialize(Sharp::Util::Xml::CNode const &)

- ea: `0x14000dc30`
- end: `0x14000dce9`
- name: `?Deserialize@CFilePath@PolicyModel@@MEAAXAEBVCNode@Xml@Util@Sharp@@@Z`
- size: `185`
- prototype: `void __fastcall(PolicyModel::CFilePath *__hidden this, const struct Sharp::Util::Xml::CNode *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x140008368`
- `0x1400099b4`
- `0x14000a0d4`
- `0x14000dc30`
- `0x1400130ec`
- `0x140013b10`

## pseudocode

```c
void __fastcall PolicyModel::CFilePath::Deserialize(
        PolicyModel::CFilePath *this,
        const struct Sharp::Util::Xml::CNode *a2)
{
  __int64 v4; // rax
  _QWORD v5[4]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v6[4]; // [rsp+40h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_4396747c8fbb3df68c27b0af1ef1da37_Traceguids);
  std::wstring::wstring((__int64)v5);
  v4 = Sharp::Util::Xml::CNode::ParseStringAttribute(a2, v6, v5);
  std::wstring::operator=((__int64)this + 8, v4);
  std::wstring::_Tidy(v6, 1, 0);
  std::wstring::_Tidy(v5, 1, 0);
}

```

## disassembly

```asm
0x14000dc30  mov     [rsp+arg_10], rbx
0x14000dc35  push    rdi
0x14000dc36  sub     rsp, 70h
0x14000dc3a  mov     rax, cs:__security_cookie
0x14000dc41  xor     rax, rsp
0x14000dc44  mov     [rsp+78h+var_18], rax
0x14000dc49  mov     rdi, rdx
0x14000dc4c  mov     rbx, rcx
0x14000dc4f  lea     rax, WPP_GLOBAL_Control
0x14000dc56  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dc5d  cmp     rcx, rax
0x14000dc60  jz      short loc_14000DC7D
0x14000dc62  test    byte ptr [rcx+1Ch], 8
0x14000dc66  jz      short loc_14000DC7D
0x14000dc68  mov     edx, 0Dh
0x14000dc6d  lea     r8, WPP_4396747c8fbb3df68c27b0af1ef1da37_Traceguids
0x14000dc74  mov     rcx, [rcx+10h]
0x14000dc78  call    WPP_SF_
0x14000dc7d  lea     rdx, aPath; "Path"
0x14000dc84  lea     rcx, [rsp+78h+var_58]
0x14000dc89  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000dc8e  nop
0x14000dc8f  lea     r8, [rsp+78h+var_58]
0x14000dc94  lea     rdx, [rsp+78h+var_38]
0x14000dc99  mov     rcx, rdi
0x14000dc9c  call    ?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Sharp::Util::Xml::CNode::ParseStringAttribute(std::wstring const &)
0x14000dca1  nop
0x14000dca2  lea     rcx, [rbx+8]
0x14000dca6  mov     rdx, rax
0x14000dca9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x14000dcae  nop
0x14000dcaf  xor     r8d, r8d
0x14000dcb2  mov     dl, 1
0x14000dcb4  lea     rcx, [rsp+78h+var_38]
0x14000dcb9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000dcbe  nop
0x14000dcbf  xor     r8d, r8d
0x14000dcc2  mov     dl, 1
0x14000dcc4  lea     rcx, [rsp+78h+var_58]
0x14000dcc9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000dcce  mov     rcx, [rsp+78h+var_18]
0x14000dcd3  xor     rcx, rsp; StackCookie
0x14000dcd6  call    __security_check_cookie
0x14000dcdb  mov     rbx, [rsp+78h+arg_10]
0x14000dce3  add     rsp, 70h
0x14000dce7  pop     rdi
0x14000dce8  retn
```
