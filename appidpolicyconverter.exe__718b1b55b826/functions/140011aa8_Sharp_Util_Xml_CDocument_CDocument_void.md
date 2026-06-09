# Sharp::Util::Xml::CDocument::~CDocument(void)

- ea: `0x140011aa8`
- end: `0x140011b01`
- name: `??1CDocument@Xml@Util@Sharp@@UEAA@XZ`
- size: `89`
- prototype: `void __fastcall(Sharp::Util::Xml::CDocument *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a9ac`
- `0x140011b30`
- `0x14001452d`
- `0x14001457d`

## callees

- `0x1400070e4`
- `0x140011a6c`
- `0x140011aa8`

## pseudocode

```c
void __fastcall Sharp::Util::Xml::CDocument::~CDocument(Sharp::Util::Xml::CDocument *this)
{
  *(_QWORD *)this = &Sharp::Util::Xml::CDocument::`vftable';
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_e137bfdab7b23ac569be7b05e5d5c80a_Traceguids);
  ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)this + 1);
}

```

## disassembly

```asm
0x140011aa8  mov     [rsp+arg_0], rcx
0x140011aad  push    rbx
0x140011aae  sub     rsp, 20h
0x140011ab2  mov     rbx, rcx
0x140011ab5  lea     rax, ??_7CDocument@Xml@Util@Sharp@@6B@; const Sharp::Util::Xml::CDocument::`vftable'
0x140011abc  mov     [rcx], rax
0x140011abf  lea     rax, WPP_GLOBAL_Control
0x140011ac6  mov     rcx, cs:WPP_GLOBAL_Control
0x140011acd  cmp     rcx, rax
0x140011ad0  jz      short loc_140011AEE
0x140011ad2  test    byte ptr [rcx+1Ch], 8
0x140011ad6  jz      short loc_140011AEE
0x140011ad8  mov     edx, 0Bh
0x140011add  lea     r8, WPP_e137bfdab7b23ac569be7b05e5d5c80a_Traceguids
0x140011ae4  mov     rcx, [rcx+10h]
0x140011ae8  call    WPP_SF_
0x140011aed  nop
0x140011aee  lea     rcx, [rbx+8]
0x140011af2  mov     [rsp+28h+arg_0], rcx
0x140011af7  add     rsp, 20h
0x140011afb  pop     rbx
0x140011afc  jmp     ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
```
