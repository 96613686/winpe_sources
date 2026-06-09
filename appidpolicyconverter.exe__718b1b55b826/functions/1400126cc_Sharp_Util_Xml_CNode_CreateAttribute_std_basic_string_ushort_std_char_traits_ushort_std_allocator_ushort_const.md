# Sharp::Util::Xml::CNode::CreateAttribute(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_GUID const &)

- ea: `0x1400126cc`
- end: `0x14001275d`
- name: `?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z`
- size: `145`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x14000ac40`

## callees

- `0x1400070e4`
- `0x140008368`
- `0x140012604`
- `0x1400126cc`
- `0x140012d2c`
- `0x140013b10`

## pseudocode

```c
__int64 __fastcall Sharp::Util::Xml::CNode::CreateAttribute(__int64 a1, const unsigned __int16 *a2, __int64 a3)
{
  OLECHAR v7[16]; // [rsp+20h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
  Sharp::Util::StringHandler::GuidToString(v7, a3);
  Sharp::Util::Xml::CNode::CreateAttribute(a1, a2, v7);
  return std::wstring::_Tidy(v7, 1, 0);
}

```

## disassembly

```asm
0x1400126cc  push    rbx
0x1400126ce  push    rsi
0x1400126cf  push    rdi
0x1400126d0  sub     rsp, 50h
0x1400126d4  mov     rax, cs:__security_cookie
0x1400126db  xor     rax, rsp
0x1400126de  mov     [rsp+68h+var_28], rax
0x1400126e3  mov     rsi, r8
0x1400126e6  mov     rdi, rdx
0x1400126e9  mov     rbx, rcx
0x1400126ec  lea     rax, WPP_GLOBAL_Control
0x1400126f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400126fa  cmp     rcx, rax
0x1400126fd  jz      short loc_14001271A
0x1400126ff  test    byte ptr [rcx+1Ch], 8
0x140012703  jz      short loc_14001271A
0x140012705  mov     edx, 36h ; '6'
0x14001270a  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140012711  mov     rcx, [rcx+10h]
0x140012715  call    WPP_SF_
0x14001271a  mov     rdx, rsi
0x14001271d  lea     rcx, [rsp+68h+var_48]
0x140012722  call    ?GuidToString@StringHandler@Util@Sharp@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; Sharp::Util::StringHandler::GuidToString(_GUID const &)
0x140012727  nop
0x140012728  lea     r8, [rsp+68h+var_48]
0x14001272d  mov     rdx, rdi
0x140012730  mov     rcx, rbx
0x140012733  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,std::wstring const &)
0x140012738  nop
0x140012739  xor     r8d, r8d
0x14001273c  mov     dl, 1
0x14001273e  lea     rcx, [rsp+68h+var_48]
0x140012743  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140012748  mov     rcx, [rsp+68h+var_28]
0x14001274d  xor     rcx, rsp; StackCookie
0x140012750  call    __security_check_cookie
0x140012755  add     rsp, 50h
0x140012759  pop     rdi
0x14001275a  pop     rsi
0x14001275b  pop     rbx
0x14001275c  retn
```
