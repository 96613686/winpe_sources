# ATL::CComObject<CRemoveDeviceElevatedHandler>::`vector deleting destructor'(uint)

- ea: `0x180006370`
- end: `0x1800063be`
- name: `??_E?$CComObject@VCRemoveDeviceElevatedHandler@@@ATL@@UEAAPEAXI@Z`
- size: `78`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001be0`
- `0x180006370`
- `0x18000e010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CRemoveDeviceElevatedHandler>::`vector deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CRemoveDeviceElevatedHandler>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180006370  mov     [rsp+arg_0], rbx
0x180006375  push    rdi
0x180006376  sub     rsp, 20h
0x18000637a  mov     dword ptr [rcx+8], 0C0000001h
0x180006381  lea     rax, ??_7?$CComObject@VCRemoveDeviceElevatedHandler@@@ATL@@6B@; const ATL::CComObject<CRemoveDeviceElevatedHandler>::`vftable'
0x180006388  mov     [rcx], rax
0x18000638b  mov     rdi, rcx
0x18000638e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006395  mov     ebx, edx
0x180006397  mov     rax, [rcx]
0x18000639a  mov     rax, [rax+10h]
0x18000639e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063a3  test    bl, 1
0x1800063a6  jz      short loc_1800063B0
0x1800063a8  mov     rcx, rdi; Block
0x1800063ab  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800063b0  mov     rbx, [rsp+28h+arg_0]
0x1800063b5  mov     rax, rdi
0x1800063b8  add     rsp, 20h
0x1800063bc  pop     rdi
0x1800063bd  retn
```
