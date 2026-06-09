# Sharp::Util::Xml::CNodeCollection::~CNodeCollection(void)

- ea: `0x14001377c`
- end: `0x1400137d0`
- name: `??1CNodeCollection@Xml@Util@Sharp@@UEAA@XZ`
- size: `84`
- prototype: `void __fastcall(Sharp::Util::Xml::CNodeCollection *__hidden this)`
- caller_count: `17`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140009410`
- `0x140009520`
- `0x1400096c4`
- `0x14000e340`
- `0x1400121a0`
- `0x140012b94`
- `0x140012c90`
- `0x140012f20`
- `0x1400141cf`
- `0x140014229`
- `0x140014b60`
- `0x1400151bd`
- `0x140015215`
- `0x140015265`
- `0x140015277`
- `0x1400152eb`
- `0x1400153c1`

## callees

- `0x1400070e4`
- `0x1400120e0`
- `0x14001377c`

## pseudocode

```c
void __fastcall Sharp::Util::Xml::CNodeCollection::~CNodeCollection(Sharp::Util::Xml::CNodeCollection *this)
{
  *(_QWORD *)this = &Sharp::Util::Xml::CNodeCollection::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_aa5cb3998772301bcbc4f4136f5a9bc8_Traceguids);
  std::list<Sharp::Util::Xml::CNode>::~list<Sharp::Util::Xml::CNode>((__int64)this + 8);
}

```

## disassembly

```asm
0x14001377c  mov     [rsp+arg_0], rcx
0x140013781  push    rbx
0x140013782  sub     rsp, 20h
0x140013786  mov     rbx, rcx
0x140013789  lea     rax, ??_7CNodeCollection@Xml@Util@Sharp@@6B@; const Sharp::Util::Xml::CNodeCollection::`vftable'
0x140013790  mov     [rcx], rax
0x140013793  lea     rax, WPP_GLOBAL_Control
0x14001379a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400137a1  cmp     rcx, rax
0x1400137a4  jz      short loc_1400137C2
0x1400137a6  test    byte ptr [rcx+1Ch], 8
0x1400137aa  jz      short loc_1400137C2
0x1400137ac  mov     edx, 0Fh
0x1400137b1  lea     r8, WPP_aa5cb3998772301bcbc4f4136f5a9bc8_Traceguids
0x1400137b8  mov     rcx, [rcx+10h]
0x1400137bc  call    WPP_SF_
0x1400137c1  nop
0x1400137c2  lea     rcx, [rbx+8]
0x1400137c6  add     rsp, 20h
0x1400137ca  pop     rbx
0x1400137cb  jmp     ??1?$list@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@QEAA@XZ; std::list<Sharp::Util::Xml::CNode>::~list<Sharp::Util::Xml::CNode>(void)
```
