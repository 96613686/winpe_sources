# ATL::CComAggObject<CIdentityProfileHandler>::~CComAggObject<CIdentityProfileHandler>(void)

- ea: `0x1800108fc`
- end: `0x180010937`
- name: `??1?$CComAggObject@VCIdentityProfileHandler@@@ATL@@UEAA@XZ`
- size: `59`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010a10`

## callees

- `0x18000dc78`
- `0x18001b010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CIdentityProfileHandler>::~CComAggObject<CIdentityProfileHandler>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CIdentityProfileHandler>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CIdentityProfileHandler::~CIdentityProfileHandler((CIdentityProfileHandler *)(a1 + 24));
}

```

## disassembly

```asm
0x1800108fc  push    rbx
0x1800108fe  sub     rsp, 20h
0x180010902  mov     dword ptr [rcx+8], 0C0000001h
0x180010909  lea     rax, ??_7?$CComAggObject@VCIdentityProfileHandler@@@ATL@@6B@; const ATL::CComAggObject<CIdentityProfileHandler>::`vftable'
0x180010910  mov     [rcx], rax
0x180010913  mov     rbx, rcx
0x180010916  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001091d  mov     rax, [rcx]
0x180010920  mov     rax, [rax+10h]
0x180010924  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010929  lea     rcx, [rbx+18h]; this
0x18001092d  add     rsp, 20h
0x180010931  pop     rbx
0x180010932  jmp     ??1CIdentityProfileHandler@@UEAA@XZ; CIdentityProfileHandler::~CIdentityProfileHandler(void)
```
