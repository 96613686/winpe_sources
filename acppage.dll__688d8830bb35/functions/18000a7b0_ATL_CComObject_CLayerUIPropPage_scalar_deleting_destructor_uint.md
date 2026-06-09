# ATL::CComObject<CLayerUIPropPage>::`scalar deleting destructor'(uint)

- ea: `0x18000a7b0`
- end: `0x18000a82a`
- name: `??_G?$CComObject@VCLayerUIPropPage@@@ATL@@UEAAPEAXI@Z`
- size: `122`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001790`
- `0x18000a7b0`
- `0x180017010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CLayerUIPropPage>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  __int64 v4; // rcx

  Block[6] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CLayerUIPropPage>::`vftable'{for `ILayerUIPropPage'};
  *((_QWORD *)Block + 1) = &ATL::CComObject<CLayerUIPropPage>::`vftable'{for `IShellExtInit'};
  *((_QWORD *)Block + 2) = &ATL::CComObject<CLayerUIPropPage>::`vftable'{for `IShellPropSheetExt'};
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = *((_QWORD *)Block + 4);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000a7b0  mov     [rsp+arg_0], rbx
0x18000a7b5  push    rdi
0x18000a7b6  sub     rsp, 20h
0x18000a7ba  mov     dword ptr [rcx+18h], 0C0000001h
0x18000a7c1  lea     rax, ??_7?$CComObject@VCLayerUIPropPage@@@ATL@@6BILayerUIPropPage@@@; const ATL::CComObject<CLayerUIPropPage>::`vftable'{for `ILayerUIPropPage'}
0x18000a7c8  mov     [rcx], rax
0x18000a7cb  mov     rbx, rcx
0x18000a7ce  lea     rax, ??_7?$CComObject@VCLayerUIPropPage@@@ATL@@6BIShellExtInit@@@; const ATL::CComObject<CLayerUIPropPage>::`vftable'{for `IShellExtInit'}
0x18000a7d5  mov     edi, edx
0x18000a7d7  mov     [rcx+8], rax
0x18000a7db  lea     rax, ??_7?$CComObject@VCLayerUIPropPage@@@ATL@@6BIShellPropSheetExt@@@; const ATL::CComObject<CLayerUIPropPage>::`vftable'{for `IShellPropSheetExt'}
0x18000a7e2  mov     [rcx+10h], rax
0x18000a7e6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a7ed  mov     rax, [rcx]
0x18000a7f0  mov     rax, [rax+10h]
0x18000a7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7f9  mov     rcx, [rbx+20h]
0x18000a7fd  test    rcx, rcx
0x18000a800  jz      short loc_18000A80E
0x18000a802  mov     rax, [rcx]
0x18000a805  mov     rax, [rax+10h]
0x18000a809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a80e  test    dil, 1
0x18000a812  jz      short loc_18000A81C
0x18000a814  mov     rcx, rbx; Block
0x18000a817  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a81c  mov     rax, rbx
0x18000a81f  mov     rbx, [rsp+28h+arg_0]
0x18000a824  add     rsp, 20h
0x18000a828  pop     rdi
0x18000a829  retn
```
