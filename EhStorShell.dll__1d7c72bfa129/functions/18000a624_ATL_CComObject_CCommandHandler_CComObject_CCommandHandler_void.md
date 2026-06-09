# ATL::CComObject<CCommandHandler>::CComObject<CCommandHandler>(void *)

- ea: `0x18000a624`
- end: `0x18000a68e`
- name: `??0?$CComObject@VCCommandHandler@@@ATL@@QEAA@PEAX@Z`
- size: `106`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003104`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCommandHandler>::CComObject<CCommandHandler>(__int64 a1)
{
  *(_DWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_BYTE *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_DWORD *)(a1 + 80) = 0;
  *(_QWORD *)a1 = &ATL::CComObject<CCommandHandler>::`vftable'{for `IObjectWithSelection'};
  *(_QWORD *)(a1 + 8) = &ATL::CComObject<CCommandHandler>::`vftable'{for `IInitializeCommand'};
  *(_QWORD *)(a1 + 16) = &ATL::CComObject<CCommandHandler>::`vftable'{for `IExplorerCommand'};
  *(_QWORD *)(a1 + 24) = &ATL::CComObject<CCommandHandler>::`vftable'{for `IObjectWithSite'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  return a1;
}

```

## disassembly

```asm
0x18000a624  push    rbx
0x18000a626  sub     rsp, 20h
0x18000a62a  xor     eax, eax
0x18000a62c  mov     rbx, rcx
0x18000a62f  mov     [rcx+20h], eax
0x18000a632  mov     [rcx+28h], eax
0x18000a635  mov     [rcx+30h], rax
0x18000a639  mov     [rcx+38h], rax
0x18000a63d  mov     [rcx+40h], al
0x18000a640  mov     [rcx+48h], rax
0x18000a644  mov     [rcx+50h], eax
0x18000a647  lea     rax, ??_7?$CComObject@VCCommandHandler@@@ATL@@6BIObjectWithSelection@@@; const ATL::CComObject<CCommandHandler>::`vftable'{for `IObjectWithSelection'}
0x18000a64e  mov     [rcx], rax
0x18000a651  lea     rax, ??_7?$CComObject@VCCommandHandler@@@ATL@@6BIInitializeCommand@@@; const ATL::CComObject<CCommandHandler>::`vftable'{for `IInitializeCommand'}
0x18000a658  mov     [rcx+8], rax
0x18000a65c  lea     rax, ??_7?$CComObject@VCCommandHandler@@@ATL@@6BIExplorerCommand@@@; const ATL::CComObject<CCommandHandler>::`vftable'{for `IExplorerCommand'}
0x18000a663  mov     [rcx+10h], rax
0x18000a667  lea     rax, ??_7?$CComObject@VCCommandHandler@@@ATL@@6BIObjectWithSite@@@; const ATL::CComObject<CCommandHandler>::`vftable'{for `IObjectWithSite'}
0x18000a66e  mov     [rcx+18h], rax
0x18000a672  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a679  mov     rax, [rcx]
0x18000a67c  mov     rax, [rax+8]
0x18000a680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a685  mov     rax, rbx
0x18000a688  add     rsp, 20h
0x18000a68c  pop     rbx
0x18000a68d  retn
```
