# PolicyModel::CFilePath::Serialize(Sharp::Util::Xml::CNode &)

- ea: `0x14000dd60`
- end: `0x14000ddf8`
- name: `?Serialize@CFilePath@PolicyModel@@MEBAXAEAVCNode@Xml@Util@Sharp@@@Z`
- size: `152`
- prototype: `void __fastcall(const OLECHAR *this, struct Sharp::Util::Xml::CNode *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x140008368`
- `0x1400099b4`
- `0x14000dd60`
- `0x140012604`
- `0x140013b10`

## pseudocode

```c
void __fastcall PolicyModel::CFilePath::Serialize(const OLECHAR *this, struct Sharp::Util::Xml::CNode *a2)
{
  unsigned __int16 v4[16]; // [rsp+20h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_4396747c8fbb3df68c27b0af1ef1da37_Traceguids);
  std::wstring::wstring((__int64)v4);
  Sharp::Util::Xml::CNode::CreateAttribute((__int64)a2, v4, this + 4);
  std::wstring::_Tidy(v4, 1, 0);
}

```

## disassembly

```asm
0x14000dd60  mov     [rsp+arg_10], rbx
0x14000dd65  push    rdi
0x14000dd66  sub     rsp, 50h
0x14000dd6a  mov     rax, cs:__security_cookie
0x14000dd71  xor     rax, rsp
0x14000dd74  mov     [rsp+58h+var_18], rax
0x14000dd79  mov     rdi, rdx
0x14000dd7c  mov     rbx, rcx
0x14000dd7f  lea     rax, WPP_GLOBAL_Control
0x14000dd86  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dd8d  cmp     rcx, rax
0x14000dd90  jz      short loc_14000DDAD
0x14000dd92  test    byte ptr [rcx+1Ch], 8
0x14000dd96  jz      short loc_14000DDAD
0x14000dd98  mov     edx, 0Ch
0x14000dd9d  lea     r8, WPP_4396747c8fbb3df68c27b0af1ef1da37_Traceguids
0x14000dda4  mov     rcx, [rcx+10h]
0x14000dda8  call    WPP_SF_
0x14000ddad  lea     rdx, aPath; "Path"
0x14000ddb4  lea     rcx, [rsp+58h+var_38]
0x14000ddb9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000ddbe  nop
0x14000ddbf  lea     r8, [rbx+8]
0x14000ddc3  lea     rdx, [rsp+58h+var_38]
0x14000ddc8  mov     rcx, rdi
0x14000ddcb  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,std::wstring const &)
0x14000ddd0  nop
0x14000ddd1  xor     r8d, r8d
0x14000ddd4  mov     dl, 1
0x14000ddd6  lea     rcx, [rsp+58h+var_38]
0x14000dddb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000dde0  mov     rcx, [rsp+58h+var_18]
0x14000dde5  xor     rcx, rsp; StackCookie
0x14000dde8  call    __security_check_cookie
0x14000dded  mov     rbx, [rsp+58h+arg_10]
0x14000ddf2  add     rsp, 50h
0x14000ddf6  pop     rdi
0x14000ddf7  retn
```
