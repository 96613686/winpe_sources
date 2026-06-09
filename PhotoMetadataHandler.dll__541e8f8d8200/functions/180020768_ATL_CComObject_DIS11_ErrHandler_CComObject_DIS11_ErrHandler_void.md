# ATL::CComObject<DIS11::ErrHandler>::~CComObject<DIS11::ErrHandler>(void)

- ea: `0x180020768`
- end: `0x1800207b6`
- name: `??1?$CComObject@VErrHandler@DIS11@@@ATL@@UEAA@XZ`
- size: `78`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180020810`
- `0x180020f20`
- `0x1800270cd`

## callees

- `0x18000d600`
- `0x180028010`

## pseudocode

```c
void __fastcall ATL::CComObject<DIS11::ErrHandler>::~CComObject<DIS11::ErrHandler>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComObject<DIS11::ErrHandler>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  *(_QWORD *)a1 = &DIS11::ErrHandler::`vftable';
  ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(a1 + 8);
}

```

## disassembly

```asm
0x180020768  mov     [rsp+arg_0], rbx
0x18002076d  push    rdi
0x18002076e  sub     rsp, 20h
0x180020772  mov     dword ptr [rcx+8], 0C0000001h
0x180020779  lea     rax, ??_7?$CComObject@VErrHandler@DIS11@@@ATL@@6B@; const ATL::CComObject<DIS11::ErrHandler>::`vftable'
0x180020780  mov     [rcx], rax
0x180020783  mov     rdi, rcx
0x180020786  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002078d  mov     rax, [rcx]
0x180020790  mov     rax, [rax+10h]
0x180020794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020799  lea     rax, ??_7ErrHandler@DIS11@@6B@; const DIS11::ErrHandler::`vftable'
0x1800207a0  lea     rcx, [rdi+8]
0x1800207a4  mov     [rdi], rax
0x1800207a7  mov     rbx, [rsp+28h+arg_0]
0x1800207ac  add     rsp, 20h
0x1800207b0  pop     rdi
0x1800207b1  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
