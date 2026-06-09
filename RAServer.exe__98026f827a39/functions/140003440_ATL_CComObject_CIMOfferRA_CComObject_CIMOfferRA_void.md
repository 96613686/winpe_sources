# ATL::CComObject<CIMOfferRA>::~CComObject<CIMOfferRA>(void)

- ea: `0x140003440`
- end: `0x14000347a`
- name: `??1?$CComObject@VCIMOfferRA@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(CIMOfferRA *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003de0`

## callees

- `0x140012b98`
- `0x140017010`

## pseudocode

```c
void __fastcall ATL::CComObject<CIMOfferRA>::~CComObject<CIMOfferRA>(CIMOfferRA *this)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CIMOfferRA>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CIMOfferRA::~CIMOfferRA(this);
}

```

## disassembly

```asm
0x140003440  push    rbx
0x140003442  sub     rsp, 20h
0x140003446  mov     dword ptr [rcx+8], 0C0000001h
0x14000344d  lea     rax, ??_7?$CComObject@VCIMOfferRA@@@ATL@@6B@; const ATL::CComObject<CIMOfferRA>::`vftable'
0x140003454  mov     [rcx], rax
0x140003457  mov     rbx, rcx
0x14000345a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140003461  mov     rax, [rcx]
0x140003464  mov     rax, [rax+10h]
0x140003468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000346d  mov     rcx, rbx; this
0x140003470  add     rsp, 20h
0x140003474  pop     rbx
0x140003475  jmp     ??1CIMOfferRA@@UEAA@XZ; CIMOfferRA::~CIMOfferRA(void)
```
