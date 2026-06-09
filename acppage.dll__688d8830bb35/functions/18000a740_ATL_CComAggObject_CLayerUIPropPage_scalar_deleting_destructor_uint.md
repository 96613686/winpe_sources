# ATL::CComAggObject<CLayerUIPropPage>::`scalar deleting destructor'(uint)

- ea: `0x18000a740`
- end: `0x18000a7a4`
- name: `??_G?$CComAggObject@VCLayerUIPropPage@@@ATL@@UEAAPEAXI@Z`
- size: `100`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001790`
- `0x18000a740`
- `0x180017010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CLayerUIPropPage>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  __int64 v4; // rcx

  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<CLayerUIPropPage>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  v4 = *((_QWORD *)Block + 6);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000a740  mov     [rsp+arg_0], rbx
0x18000a745  push    rdi
0x18000a746  sub     rsp, 20h
0x18000a74a  mov     dword ptr [rcx+8], 0C0000001h
0x18000a751  lea     rax, ??_7?$CComAggObject@VCLayerUIPropPage@@@ATL@@6B@; const ATL::CComAggObject<CLayerUIPropPage>::`vftable'
0x18000a758  mov     [rcx], rax
0x18000a75b  mov     rbx, rcx
0x18000a75e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a765  mov     edi, edx
0x18000a767  mov     rax, [rcx]
0x18000a76a  mov     rax, [rax+10h]
0x18000a76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a773  mov     rcx, [rbx+30h]
0x18000a777  test    rcx, rcx
0x18000a77a  jz      short loc_18000A788
0x18000a77c  mov     rax, [rcx]
0x18000a77f  mov     rax, [rax+10h]
0x18000a783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a788  test    dil, 1
0x18000a78c  jz      short loc_18000A796
0x18000a78e  mov     rcx, rbx; Block
0x18000a791  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a796  mov     rax, rbx
0x18000a799  mov     rbx, [rsp+28h+arg_0]
0x18000a79e  add     rsp, 20h
0x18000a7a2  pop     rdi
0x18000a7a3  retn
```
