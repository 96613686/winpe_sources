# ATL::CComAggObject<CAxInstaller>::~CComAggObject<CAxInstaller>(void)

- ea: `0x180008340`
- end: `0x18000837b`
- name: `??1?$CComAggObject@VCAxInstaller@@@ATL@@UEAA@XZ`
- size: `59`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008c40`

## callees

- `0x180005e18`
- `0x180015010`

## pseudocode

```c
void __fastcall ATL::CComAggObject<CAxInstaller>::~CComAggObject<CAxInstaller>(__int64 a1)
{
  *(_DWORD *)(a1 + 8) = -1073741823;
  *(_QWORD *)a1 = &ATL::CComAggObject<CAxInstaller>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CAxInstaller::~CAxInstaller((CAxInstaller *)(a1 + 24));
}

```

## disassembly

```asm
0x180008340  push    rbx
0x180008342  sub     rsp, 20h
0x180008346  mov     dword ptr [rcx+8], 0C0000001h
0x18000834d  lea     rax, ??_7?$CComAggObject@VCAxInstaller@@@ATL@@6B@; const ATL::CComAggObject<CAxInstaller>::`vftable'
0x180008354  mov     [rcx], rax
0x180008357  mov     rbx, rcx
0x18000835a  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180008361  mov     rax, [rcx]
0x180008364  mov     rax, [rax+10h]
0x180008368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000836d  lea     rcx, [rbx+18h]; this
0x180008371  add     rsp, 20h
0x180008375  pop     rbx
0x180008376  jmp     ??1CAxInstaller@@UEAA@XZ; CAxInstaller::~CAxInstaller(void)
```
