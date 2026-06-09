# ATL::CComAggObject<CRemoveDeviceElevatedHandler>::`vector deleting destructor'(uint)

- ea: `0x1800062b0`
- end: `0x1800062fe`
- name: `??_E?$CComAggObject@VCRemoveDeviceElevatedHandler@@@ATL@@UEAAPEAXI@Z`
- size: `78`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001be0`
- `0x1800062b0`
- `0x18000e010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CRemoveDeviceElevatedHandler>::`vector deleting destructor'(
        _DWORD *Block,
        char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<CRemoveDeviceElevatedHandler>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800062b0  mov     [rsp+arg_0], rbx
0x1800062b5  push    rdi
0x1800062b6  sub     rsp, 20h
0x1800062ba  mov     dword ptr [rcx+8], 0C0000001h
0x1800062c1  lea     rax, ??_7?$CComAggObject@VCRemoveDeviceElevatedHandler@@@ATL@@6B@; const ATL::CComAggObject<CRemoveDeviceElevatedHandler>::`vftable'
0x1800062c8  mov     [rcx], rax
0x1800062cb  mov     rdi, rcx
0x1800062ce  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800062d5  mov     ebx, edx
0x1800062d7  mov     rax, [rcx]
0x1800062da  mov     rax, [rax+10h]
0x1800062de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062e3  test    bl, 1
0x1800062e6  jz      short loc_1800062F0
0x1800062e8  mov     rcx, rdi; Block
0x1800062eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800062f0  mov     rbx, [rsp+28h+arg_0]
0x1800062f5  mov     rax, rdi
0x1800062f8  add     rsp, 20h
0x1800062fc  pop     rdi
0x1800062fd  retn
```
