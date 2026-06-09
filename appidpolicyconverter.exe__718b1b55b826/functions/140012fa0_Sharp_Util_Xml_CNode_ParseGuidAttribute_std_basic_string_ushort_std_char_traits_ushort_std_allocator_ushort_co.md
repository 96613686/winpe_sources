# Sharp::Util::Xml::CNode::ParseGuidAttribute(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140012fa0`
- end: `0x14001303c`
- name: `?ParseGuidAttribute@CNode@Xml@Util@Sharp@@QEBA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `156`
- prototype: `_OWORD *__fastcall(__int64, _OWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x14000a560`

## callees

- `0x1400070e4`
- `0x140008368`
- `0x140012fa0`
- `0x1400130ec`
- `0x140013338`
- `0x140013b10`

## pseudocode

```c
_OWORD *__fastcall Sharp::Util::Xml::CNode::ParseGuidAttribute(__int64 a1, _OWORD *a2, __int64 a3)
{
  _BYTE v7[16]; // [rsp+20h] [rbp-58h] BYREF
  _QWORD v8[4]; // [rsp+30h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
  Sharp::Util::Xml::CNode::ParseStringAttribute(a1, v8, a3);
  *a2 = *(_OWORD *)Sharp::Util::StringHandler::StringToGuid(v7, v8);
  std::wstring::_Tidy(v8, 1, 0);
  return a2;
}

```

## disassembly

```asm
0x140012fa0  push    rbx
0x140012fa2  push    rsi
0x140012fa3  push    rdi
0x140012fa4  sub     rsp, 60h
0x140012fa8  mov     rax, cs:__security_cookie
0x140012faf  xor     rax, rsp
0x140012fb2  mov     [rsp+78h+var_28], rax
0x140012fb7  mov     rsi, r8
0x140012fba  mov     rbx, rdx
0x140012fbd  mov     rdi, rcx
0x140012fc0  lea     rax, WPP_GLOBAL_Control
0x140012fc7  mov     rcx, cs:WPP_GLOBAL_Control
0x140012fce  cmp     rcx, rax
0x140012fd1  jz      short loc_140012FEE
0x140012fd3  test    byte ptr [rcx+1Ch], 8
0x140012fd7  jz      short loc_140012FEE
0x140012fd9  mov     edx, 30h ; '0'
0x140012fde  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140012fe5  mov     rcx, [rcx+10h]
0x140012fe9  call    WPP_SF_
0x140012fee  mov     r8, rsi
0x140012ff1  lea     rdx, [rsp+78h+var_48]
0x140012ff6  mov     rcx, rdi
0x140012ff9  call    ?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Sharp::Util::Xml::CNode::ParseStringAttribute(std::wstring const &)
0x140012ffe  nop
0x140012fff  lea     rdx, [rsp+78h+var_48]
0x140013004  lea     rcx, [rsp+78h+var_58]
0x140013009  call    ?StringToGuid@StringHandler@Util@Sharp@@YA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::StringHandler::StringToGuid(std::wstring const &)
0x14001300e  movups  xmm0, xmmword ptr [rax]
0x140013011  movdqu  xmmword ptr [rbx], xmm0
0x140013015  xor     r8d, r8d
0x140013018  mov     dl, 1
0x14001301a  lea     rcx, [rsp+78h+var_48]
0x14001301f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140013024  mov     rax, rbx
0x140013027  mov     rcx, [rsp+78h+var_28]
0x14001302c  xor     rcx, rsp; StackCookie
0x14001302f  call    __security_check_cookie
0x140013034  add     rsp, 60h
0x140013038  pop     rdi
0x140013039  pop     rsi
0x14001303a  pop     rbx
0x14001303b  retn
```
