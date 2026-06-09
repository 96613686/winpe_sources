# ATL::CComAggObject<CRASrv>::~CComAggObject<CRASrv>(void)

- ea: `0x140003398`
- end: `0x1400033d3`
- name: `??1?$CComAggObject@VCRASrv@@@ATL@@UEAA@XZ`
- size: `59`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003da0`

## callees

- `0x1400039e0`
- `0x140017010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CRASrv>::~CComAggObject<CRASrv>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CRASrv>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 48));
}

```

## disassembly

```asm
0x140003398  push    rbx
0x14000339a  sub     rsp, 20h
0x14000339e  mov     dword ptr [rcx+8], 0C0000001h
0x1400033a5  lea     rax, ??_7?$CComAggObject@VCRASrv@@@ATL@@6B@; const ATL::CComAggObject<CRASrv>::`vftable'
0x1400033ac  mov     [rcx], rax
0x1400033af  mov     rbx, rcx
0x1400033b2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1400033b9  mov     rax, [rcx]
0x1400033bc  mov     rax, [rax+10h]
0x1400033c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033c5  lea     rcx, [rbx+30h]; this
0x1400033c9  add     rsp, 20h
0x1400033cd  pop     rbx
0x1400033ce  jmp     ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
```
