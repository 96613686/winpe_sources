# Sharp::Util::Xml::CNode::HasSpecificChild(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140012f20`
- end: `0x140012f97`
- name: `?HasSpecificChild@CNode@Xml@Util@Sharp@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `119`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000a560`
- `0x14000cba0`

## callees

- `0x1400070e4`
- `0x140012950`
- `0x140012f20`
- `0x14001377c`
- `0x140013918`

## pseudocode

```c
bool __fastcall Sharp::Util::Xml::CNode::HasSpecificChild(__int64 a1, __int64 a2)
{
  bool v4; // bl
  _QWORD v6[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
  Sharp::Util::Xml::CNode::GetChilds(a1, v6);
  v4 = Sharp::Util::Xml::CNodeCollection::FindFirst((__int64)v6, a2) != 0;
  Sharp::Util::Xml::CNodeCollection::~CNodeCollection((Sharp::Util::Xml::CNodeCollection *)v6);
  return v4;
}

```

## disassembly

```asm
0x140012f20  mov     [rsp+arg_0], rbx
0x140012f25  push    rdi
0x140012f26  sub     rsp, 40h
0x140012f2a  mov     rbx, rdx
0x140012f2d  mov     rdi, rcx
0x140012f30  lea     rax, WPP_GLOBAL_Control
0x140012f37  mov     rcx, cs:WPP_GLOBAL_Control
0x140012f3e  cmp     rcx, rax
0x140012f41  jz      short loc_140012F5E
0x140012f43  test    byte ptr [rcx+1Ch], 8
0x140012f47  jz      short loc_140012F5E
0x140012f49  mov     edx, 15h
0x140012f4e  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140012f55  mov     rcx, [rcx+10h]
0x140012f59  call    WPP_SF_
0x140012f5e  lea     rdx, [rsp+48h+var_28]
0x140012f63  mov     rcx, rdi
0x140012f66  call    ?GetChilds@CNode@Xml@Util@Sharp@@QEBA?AVCNodeCollection@234@XZ; Sharp::Util::Xml::CNode::GetChilds(void)
0x140012f6b  nop
0x140012f6c  mov     rdx, rbx
0x140012f6f  lea     rcx, [rsp+48h+var_28]
0x140012f74  call    ?FindFirst@CNodeCollection@Xml@Util@Sharp@@QEBAPEBVCNode@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNodeCollection::FindFirst(std::wstring const &)
0x140012f79  nop
0x140012f7a  test    rax, rax
0x140012f7d  setnz   bl
0x140012f80  lea     rcx, [rsp+48h+var_28]; this
0x140012f85  call    ??1CNodeCollection@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNodeCollection::~CNodeCollection(void)
0x140012f8a  mov     al, bl
0x140012f8c  mov     rbx, [rsp+48h+arg_0]
0x140012f91  add     rsp, 40h
0x140012f95  pop     rdi
0x140012f96  retn
```
