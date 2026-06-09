# ATL::CComAggObject<CRemoveDeviceContextHandler>::`scalar deleting destructor'(uint)

- ea: `0x180006250`
- end: `0x18000629e`
- name: `??_G?$CComAggObject@VCRemoveDeviceContextHandler@@@ATL@@UEAAPEAXI@Z`
- size: `78`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001be0`
- `0x180006250`
- `0x18000e010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CRemoveDeviceContextHandler>::`scalar deleting destructor'(
        _DWORD *Block,
        char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<CRemoveDeviceContextHandler>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180006250  mov     [rsp+arg_0], rbx
0x180006255  push    rdi
0x180006256  sub     rsp, 20h
0x18000625a  mov     dword ptr [rcx+8], 0C0000001h
0x180006261  lea     rax, ??_7?$CComAggObject@VCRemoveDeviceContextHandler@@@ATL@@6B@; const ATL::CComAggObject<CRemoveDeviceContextHandler>::`vftable'
0x180006268  mov     [rcx], rax
0x18000626b  mov     rdi, rcx
0x18000626e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006275  mov     ebx, edx
0x180006277  mov     rax, [rcx]
0x18000627a  mov     rax, [rax+10h]
0x18000627e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006283  test    bl, 1
0x180006286  jz      short loc_180006290
0x180006288  mov     rcx, rdi; Block
0x18000628b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006290  mov     rbx, [rsp+28h+arg_0]
0x180006295  mov     rax, rdi
0x180006298  add     rsp, 20h
0x18000629c  pop     rdi
0x18000629d  retn
```
