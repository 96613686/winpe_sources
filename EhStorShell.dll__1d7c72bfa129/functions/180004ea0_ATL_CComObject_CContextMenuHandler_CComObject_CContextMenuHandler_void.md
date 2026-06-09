# ATL::CComObject<CContextMenuHandler>::~CComObject<CContextMenuHandler>(void)

- ea: `0x180004ea0`
- end: `0x180004eea`
- name: `??1?$CComObject@VCContextMenuHandler@@@ATL@@UEAA@XZ`
- size: `74`
- prototype: `void __fastcall(CContextMenuHandler *this, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007b40`

## callees

- `0x180004ef0`
- `0x1800065b4`
- `0x18000c010`

## pseudocode

```c
void __fastcall ATL::CComObject<CContextMenuHandler>::~CComObject<CContextMenuHandler>(
        CContextMenuHandler *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  *(_QWORD *)this = &ATL::CComObject<CContextMenuHandler>::`vftable'{for `IContextMenu'};
  *((_QWORD *)this + 1) = &ATL::CComObject<CContextMenuHandler>::`vftable'{for `IShellExtInit'};
  *((_DWORD *)this + 4) = -1073741823;
  CContextMenuHandler::FinalRelease(this, a2, a3, a4);
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CContextMenuHandler::~CContextMenuHandler(this);
}

```

## disassembly

```asm
0x180004ea0  push    rbx
0x180004ea2  sub     rsp, 20h
0x180004ea6  mov     rbx, rcx
0x180004ea9  lea     rax, ??_7?$CComObject@VCContextMenuHandler@@@ATL@@6BIContextMenu@@@; const ATL::CComObject<CContextMenuHandler>::`vftable'{for `IContextMenu'}
0x180004eb0  mov     [rcx], rax
0x180004eb3  lea     rax, ??_7?$CComObject@VCContextMenuHandler@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<CContextMenuHandler>::`vftable'{for `IShellExtInit'}
0x180004eba  mov     [rcx+8], rax
0x180004ebe  mov     dword ptr [rcx+10h], 0C0000001h
0x180004ec5  call    ?FinalRelease@CContextMenuHandler@@QEAAXXZ; CContextMenuHandler::FinalRelease(void)
0x180004eca  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004ed1  mov     rax, [rcx]
0x180004ed4  mov     rax, [rax+10h]
0x180004ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004edd  mov     rcx, rbx; this
0x180004ee0  add     rsp, 20h
0x180004ee4  pop     rbx
0x180004ee5  jmp     ??1CContextMenuHandler@@QEAA@XZ; CContextMenuHandler::~CContextMenuHandler(void)
```
