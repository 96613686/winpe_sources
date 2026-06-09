# ATL::CComObject<CIMRequestRA>::~CComObject<CIMRequestRA>(void)

- ea: `0x140003480`
- end: `0x1400034ba`
- name: `??1?$CComObject@VCIMRequestRA@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(CIMRequestRA *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003e20`

## callees

- `0x140011404`
- `0x140017010`

## pseudocode

```c
void __fastcall ATL::CComObject<CIMRequestRA>::~CComObject<CIMRequestRA>(CIMRequestRA *this)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CIMRequestRA>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CIMRequestRA::~CIMRequestRA(this);
}

```

## disassembly

```asm
0x140003480  push    rbx
0x140003482  sub     rsp, 20h
0x140003486  mov     dword ptr [rcx+8], 0C0000001h
0x14000348d  lea     rax, ??_7?$CComObject@VCIMRequestRA@@@ATL@@6B@; const ATL::CComObject<CIMRequestRA>::`vftable'
0x140003494  mov     [rcx], rax
0x140003497  mov     rbx, rcx
0x14000349a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400034a1  mov     rax, [rcx]
0x1400034a4  mov     rax, [rax+10h]
0x1400034a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034ad  mov     rcx, rbx; this
0x1400034b0  add     rsp, 20h
0x1400034b4  pop     rbx
0x1400034b5  jmp     ??1CIMRequestRA@@UEAA@XZ; CIMRequestRA::~CIMRequestRA(void)
```
