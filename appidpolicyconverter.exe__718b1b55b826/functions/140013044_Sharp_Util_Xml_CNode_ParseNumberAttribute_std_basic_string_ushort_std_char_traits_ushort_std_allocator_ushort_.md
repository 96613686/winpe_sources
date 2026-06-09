# Sharp::Util::Xml::CNode::ParseNumberAttribute(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140013044`
- end: `0x1400130e4`
- name: `?ParseNumberAttribute@CNode@Xml@Util@Sharp@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140010d90`

## callees

- `0x1400070e4`
- `0x140008368`
- `0x140013044`
- `0x1400130ec`
- `0x140013b10`

## import_xrefs

- `msvcrt!_wtoi` at `0x1400130b3`
- `msvcrt!_wtoi` at `0x1400130b3`

## pseudocode

```c
__int64 __fastcall Sharp::Util::Xml::CNode::ParseNumberAttribute(__int64 a1, __int64 a2)
{
  const wchar_t *v4; // rcx
  unsigned int v5; // ebx
  wchar_t *String[4]; // [rsp+20h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
  Sharp::Util::Xml::CNode::ParseStringAttribute(a1, String, a2);
  v4 = (const wchar_t *)String;
  if ( String[3] >= (wchar_t *)8 )
    v4 = String[0];
  v5 = _wtoi(v4);
  std::wstring::_Tidy(String, 1, 0);
  return v5;
}

```

## disassembly

```asm
0x140013044  mov     [rsp+arg_10], rbx
0x140013049  push    rdi
0x14001304a  sub     rsp, 50h
0x14001304e  mov     rax, cs:__security_cookie
0x140013055  xor     rax, rsp
0x140013058  mov     [rsp+58h+var_18], rax
0x14001305d  mov     rdi, rdx
0x140013060  mov     rbx, rcx
0x140013063  lea     rax, WPP_GLOBAL_Control
0x14001306a  mov     rcx, cs:WPP_GLOBAL_Control
0x140013071  cmp     rcx, rax
0x140013074  jz      short loc_140013091
0x140013076  test    byte ptr [rcx+1Ch], 8
0x14001307a  jz      short loc_140013091
0x14001307c  mov     edx, 2Eh ; '.'
0x140013081  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140013088  mov     rcx, [rcx+10h]
0x14001308c  call    WPP_SF_
0x140013091  mov     r8, rdi
0x140013094  lea     rdx, [rsp+58h+String]
0x140013099  mov     rcx, rbx
0x14001309c  call    ?ParseStringAttribute@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Sharp::Util::Xml::CNode::ParseStringAttribute(std::wstring const &)
0x1400130a1  nop
0x1400130a2  lea     rcx, [rsp+58h+String]
0x1400130a7  cmp     [rsp+58h+var_20], 8
0x1400130ad  cmovnb  rcx, [rsp+58h+String]; String
0x1400130b3  call    cs:__imp__wtoi
0x1400130b9  mov     ebx, eax
0x1400130bb  xor     r8d, r8d
0x1400130be  mov     dl, 1
0x1400130c0  lea     rcx, [rsp+58h+String]
0x1400130c5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1400130ca  mov     eax, ebx
0x1400130cc  mov     rcx, [rsp+58h+var_18]
0x1400130d1  xor     rcx, rsp; StackCookie
0x1400130d4  call    __security_check_cookie
0x1400130d9  mov     rbx, [rsp+58h+arg_10]
0x1400130de  add     rsp, 50h
0x1400130e2  pop     rdi
0x1400130e3  retn
```
