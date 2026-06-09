# ATL::CComObject<CCommandHandler>::~CComObject<CCommandHandler>(void)

- ea: `0x18000a694`
- end: `0x18000a6ef`
- name: `??1?$CComObject@VCCommandHandler@@@ATL@@UEAA@XZ`
- size: `91`
- prototype: `void __fastcall(CCommandHandler *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a7c0`

## callees

- `0x18000a708`
- `0x18000c010`

## pseudocode

```c
void __fastcall ATL::CComObject<CCommandHandler>::~CComObject<CCommandHandler>(CCommandHandler *this)
{
  *((_DWORD *)this + 8) = -1073741823;
  *(_QWORD *)this = &ATL::CComObject<CCommandHandler>::`vftable'{for `IObjectWithSelection'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CCommandHandler>::`vftable'{for `IInitializeCommand'};
  *((_QWORD *)this + 2) = &ATL::CComObject<CCommandHandler>::`vftable'{for `IExplorerCommand'};
  *((_QWORD *)this + 3) = &ATL::CComObject<CCommandHandler>::`vftable'{for `IObjectWithSite'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CCommandHandler::~CCommandHandler(this);
}

```

## disassembly

```asm
0x18000a694  push    rbx
0x18000a696  sub     rsp, 20h
0x18000a69a  mov     dword ptr [rcx+20h], 0C0000001h
0x18000a6a1  lea     rax, ??_7?$CComObject@VCCommandHandler@@@ATL@@6BIObjectWithSelection@@@; const ATL::CComObject<CCommandHandler>::`vftable'{for `IObjectWithSelection'}
0x18000a6a8  mov     [rcx], rax
0x18000a6ab  mov     rbx, rcx
0x18000a6ae  lea     rax, ??_7?$CComObject@VCCommandHandler@@@ATL@@6BIInitializeCommand@@@; const ATL::CComObject<CCommandHandler>::`vftable'{for `IInitializeCommand'}
0x18000a6b5  mov     [rcx+8], rax
0x18000a6b9  lea     rax, ??_7?$CComObject@VCCommandHandler@@@ATL@@6BIExplorerCommand@@@; const ATL::CComObject<CCommandHandler>::`vftable'{for `IExplorerCommand'}
0x18000a6c0  mov     [rcx+10h], rax
0x18000a6c4  lea     rax, ??_7?$CComObject@VCCommandHandler@@@ATL@@6BIObjectWithSite@@@; const ATL::CComObject<CCommandHandler>::`vftable'{for `IObjectWithSite'}
0x18000a6cb  mov     [rcx+18h], rax
0x18000a6cf  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a6d6  mov     rax, [rcx]
0x18000a6d9  mov     rax, [rax+10h]
0x18000a6dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6e2  mov     rcx, rbx; this
0x18000a6e5  add     rsp, 20h
0x18000a6e9  pop     rbx
0x18000a6ea  jmp     ??1CCommandHandler@@QEAA@XZ; CCommandHandler::~CCommandHandler(void)
```
