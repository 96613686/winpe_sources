# ATL::CComObject<DIS11::ErrHandler>::~CComObject<DIS11::ErrHandler>(void)

- ea: `0x1800217c8`
- end: `0x180021816`
- name: `??1?$CComObject@VErrHandler@DIS11@@@ATL@@UEAA@XZ`
- size: `78`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180021870`
- `0x180021fac`
- `0x18002837d`

## callees

- `0x18000d404`
- `0x180029010`

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
0x1800217c8  mov     [rsp+arg_0], rbx
0x1800217cd  push    rdi
0x1800217ce  sub     rsp, 20h
0x1800217d2  mov     dword ptr [rcx+8], 0C0000001h
0x1800217d9  lea     rax, ??_7?$CComObject@VErrHandler@DIS11@@@ATL@@6B@; const ATL::CComObject<DIS11::ErrHandler>::`vftable'
0x1800217e0  mov     [rcx], rax
0x1800217e3  mov     rdi, rcx
0x1800217e6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800217ed  mov     rax, [rcx]
0x1800217f0  mov     rax, [rax+10h]
0x1800217f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217f9  lea     rax, ??_7ErrHandler@DIS11@@6B@; const DIS11::ErrHandler::`vftable'
0x180021800  lea     rcx, [rdi+8]
0x180021804  mov     [rdi], rax
0x180021807  mov     rbx, [rsp+28h+arg_0]
0x18002180c  add     rsp, 20h
0x180021810  pop     rdi
0x180021811  jmp     ??1?$CComObjectRootEx@VCComMultiThreadModel@ATL@@@ATL@@QEAA@XZ; ATL::CComObjectRootEx<ATL::CComMultiThreadModel>::~CComObjectRootEx<ATL::CComMultiThreadModel>(void)
```
