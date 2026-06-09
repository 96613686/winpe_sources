# ATL::CComAggObject<CIdentityStore>::~CComAggObject<CIdentityStore>(void)

- ea: `0x180010940`
- end: `0x180010983`
- name: `??1?$CComAggObject@VCIdentityStore@@@ATL@@UEAA@XZ`
- size: `67`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010a50`

## callees

- `0x18000afb0`
- `0x18000e1e0`
- `0x18001b010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CIdentityStore>::~CComAggObject<CIdentityStore>(__int64 a1)
{
  CIdentityStore *v1; // rbx

  *(_DWORD *)(a1 + 8) = -1073741823;
  v1 = (CIdentityStore *)(a1 + 24);
  *(_QWORD *)a1 = &ATL::CComAggObject<CIdentityStore>::`vftable';
  CIdentityStore::FinalRelease((CIdentityStore *)(a1 + 24));
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CIdentityStore::~CIdentityStore(v1);
}

```

## disassembly

```asm
0x180010940  push    rbx
0x180010942  sub     rsp, 20h
0x180010946  lea     rax, ??_7?$CComAggObject@VCIdentityStore@@@ATL@@6B@; const ATL::CComAggObject<CIdentityStore>::`vftable'
0x18001094d  mov     dword ptr [rcx+8], 0C0000001h
0x180010954  lea     rbx, [rcx+18h]
0x180010958  mov     [rcx], rax
0x18001095b  mov     rcx, rbx; this
0x18001095e  call    ?FinalRelease@CIdentityStore@@QEAAXXZ; CIdentityStore::FinalRelease(void)
0x180010963  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001096a  mov     rax, [rcx]
0x18001096d  mov     rax, [rax+10h]
0x180010971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010976  mov     rcx, rbx; this
0x180010979  add     rsp, 20h
0x18001097d  pop     rbx
0x18001097e  jmp     ??1CIdentityStore@@UEAA@XZ; CIdentityStore::~CIdentityStore(void)
```
