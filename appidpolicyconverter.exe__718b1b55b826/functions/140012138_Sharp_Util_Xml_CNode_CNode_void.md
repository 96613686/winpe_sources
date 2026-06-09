# Sharp::Util::Xml::CNode::~CNode(void)

- ea: `0x140012138`
- end: `0x140012191`
- name: `??1CNode@Xml@Util@Sharp@@UEAA@XZ`
- size: `89`
- prototype: `void __fastcall(Sharp::Util::Xml::CNode *__hidden this)`
- caller_count: `20`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a560`
- `0x14000a9ac`
- `0x14000ac40`
- `0x14000cba0`
- `0x14000cdf0`
- `0x14000e4f0`
- `0x140011b70`
- `0x140013548`
- `0x1400137d8`
- `0x140014509`
- `0x14001453f`
- `0x14001458f`
- `0x1400145e9`
- `0x14001460d`
- `0x140015015`
- `0x14001517f`
- `0x140015239`
- `0x140015375`
- `0x1400153af`
- `0x1400153ed`

## callees

- `0x1400070e4`
- `0x140011a6c`
- `0x140012138`

## pseudocode

```c
void __fastcall Sharp::Util::Xml::CNode::~CNode(Sharp::Util::Xml::CNode *this)
{
  *(_QWORD *)this = &Sharp::Util::Xml::CNode::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)this + 1);
}

```

## disassembly

```asm
0x140012138  mov     [rsp+arg_0], rcx
0x14001213d  push    rbx
0x14001213e  sub     rsp, 20h
0x140012142  mov     rbx, rcx
0x140012145  lea     rax, ??_7CNode@Xml@Util@Sharp@@6B@; const Sharp::Util::Xml::CNode::`vftable'
0x14001214c  mov     [rcx], rax
0x14001214f  lea     rax, WPP_GLOBAL_Control
0x140012156  mov     rcx, cs:WPP_GLOBAL_Control
0x14001215d  cmp     rcx, rax
0x140012160  jz      short loc_14001217E
0x140012162  test    byte ptr [rcx+1Ch], 8
0x140012166  jz      short loc_14001217E
0x140012168  mov     edx, 0Ch
0x14001216d  lea     r8, WPP_b4460e873c6934b14d8e4a234e51fa68_Traceguids
0x140012174  mov     rcx, [rcx+10h]
0x140012178  call    WPP_SF_
0x14001217d  nop
0x14001217e  lea     rcx, [rbx+8]
0x140012182  mov     [rsp+28h+arg_0], rcx
0x140012187  add     rsp, 20h
0x14001218b  pop     rbx
0x14001218c  jmp     ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
```
