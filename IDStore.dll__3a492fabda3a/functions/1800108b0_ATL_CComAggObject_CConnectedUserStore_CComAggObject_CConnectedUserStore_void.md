# ATL::CComAggObject<CConnectedUserStore>::~CComAggObject<CConnectedUserStore>(void)

- ea: `0x1800108b0`
- end: `0x1800108f3`
- name: `??1?$CComAggObject@VCConnectedUserStore@@@ATL@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800109d0`

## callees

- `0x18000be80`
- `0x18000e080`
- `0x18001b010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CConnectedUserStore>::~CComAggObject<CConnectedUserStore>(__int64 a1)
{
  CConnectedUserStore *v1; // rbx

  *(_QWORD *)a1 = &ATL::CComAggObject<CConnectedUserStore>::`vftable';
  *(_DWORD *)(a1 + 8) = -1073741823;
  v1 = (CConnectedUserStore *)(a1 + 24);
  CConnectedUserStore::FinalRelease((CConnectedUserStore *)(a1 + 24));
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CConnectedUserStore::~CConnectedUserStore(v1);
}

```

## disassembly

```asm
0x1800108b0  push    rbx
0x1800108b2  sub     rsp, 20h
0x1800108b6  lea     rax, ??_7?$CComAggObject@VCConnectedUserStore@@@ATL@@6B@; const ATL::CComAggObject<CConnectedUserStore>::`vftable'
0x1800108bd  mov     [rcx], rax
0x1800108c0  mov     dword ptr [rcx+8], 0C0000001h
0x1800108c7  lea     rbx, [rcx+18h]
0x1800108cb  mov     rcx, rbx; this
0x1800108ce  call    ?FinalRelease@CConnectedUserStore@@QEAAXXZ; CConnectedUserStore::FinalRelease(void)
0x1800108d3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800108da  mov     rax, [rcx]
0x1800108dd  mov     rax, [rax+10h]
0x1800108e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108e6  mov     rcx, rbx; this
0x1800108e9  add     rsp, 20h
0x1800108ed  pop     rbx
0x1800108ee  jmp     ??1CConnectedUserStore@@QEAA@XZ; CConnectedUserStore::~CConnectedUserStore(void)
```
