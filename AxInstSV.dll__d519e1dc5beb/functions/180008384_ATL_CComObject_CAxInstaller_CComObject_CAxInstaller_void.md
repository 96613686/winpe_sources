# ATL::CComObject<CAxInstaller>::~CComObject<CAxInstaller>(void)

- ea: `0x180008384`
- end: `0x1800083c9`
- name: `??1?$CComObject@VCAxInstaller@@@ATL@@UEAA@XZ`
- size: `69`
- prototype: `__int64 __fastcall(CAxInstaller *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180008cc0`

## callees

- `0x180005e18`
- `0x180015010`

## pseudocode

```c
void __fastcall ATL::CComObject<CAxInstaller>::~CComObject<CAxInstaller>(CAxInstaller *this)
{
  *((_DWORD *)this + 4) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CAxInstaller>::`vftable'{for `IeAxiService2'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CAxInstaller>::`vftable'{for `IeAxiServiceCallback'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CAxInstaller::~CAxInstaller(this);
}

```

## disassembly

```asm
0x180008384  push    rbx
0x180008386  sub     rsp, 20h
0x18000838a  mov     dword ptr [rcx+10h], 0C0000001h
0x180008391  lea     rax, ??_7?$CComObject@VCAxInstaller@@@ATL@@6BIeAxiService2@@@; const ATL::CComObject<CAxInstaller>::`vftable'{for `IeAxiService2'}
0x180008398  mov     [rcx], rax
0x18000839b  mov     rbx, rcx
0x18000839e  lea     rax, ??_7?$CComObject@VCAxInstaller@@@ATL@@6BIeAxiServiceCallback@@@; const ATL::CComObject<CAxInstaller>::`vftable'{for `IeAxiServiceCallback'}
0x1800083a5  mov     [rcx+8], rax
0x1800083a9  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800083b0  mov     rax, [rcx]
0x1800083b3  mov     rax, [rax+10h]
0x1800083b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083bc  mov     rcx, rbx; this
0x1800083bf  add     rsp, 20h
0x1800083c3  pop     rbx
0x1800083c4  jmp     ??1CAxInstaller@@UEAA@XZ; CAxInstaller::~CAxInstaller(void)
```
