# ATL::CComObject<CIdentityProfileHandler>::~CComObject<CIdentityProfileHandler>(void)

- ea: `0x18000dc38`
- end: `0x18000dc72`
- name: `??1?$CComObject@VCIdentityProfileHandler@@@ATL@@UEAA@XZ`
- size: `58`
- prototype: `void __fastcall(CIdentityProfileHandler *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dc00`

## callees

- `0x18000dc78`
- `0x18001b010`

## pseudocode

```c
void __fastcall ATL::CComObject<CIdentityProfileHandler>::~CComObject<CIdentityProfileHandler>(
        CIdentityProfileHandler *this)
{
  *((_DWORD *)this + 2) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CIdentityProfileHandler>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CIdentityProfileHandler::~CIdentityProfileHandler(this);
}

```

## disassembly

```asm
0x18000dc38  push    rbx
0x18000dc3a  sub     rsp, 20h
0x18000dc3e  mov     dword ptr [rcx+8], 0C0000001h
0x18000dc45  lea     rax, ??_7?$CComObject@VCIdentityProfileHandler@@@ATL@@6B@; const ATL::CComObject<CIdentityProfileHandler>::`vftable'
0x18000dc4c  mov     [rcx], rax
0x18000dc4f  mov     rbx, rcx
0x18000dc52  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000dc59  mov     rax, [rcx]
0x18000dc5c  mov     rax, [rax+10h]
0x18000dc60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc65  mov     rcx, rbx; this
0x18000dc68  add     rsp, 20h
0x18000dc6c  pop     rbx
0x18000dc6d  jmp     ??1CIdentityProfileHandler@@UEAA@XZ; CIdentityProfileHandler::~CIdentityProfileHandler(void)
```
