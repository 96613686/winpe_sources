# ATL::CComAggObject<CPnpxPairingHandler>::`scalar deleting destructor'(uint)

- ea: `0x180005410`
- end: `0x180005467`
- name: `??_G?$CComAggObject@VCPnpxPairingHandler@@@ATL@@UEAAPEAXI@Z`
- size: `87`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800019b0`
- `0x180005410`
- `0x18000d5b0`
- `0x180014010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CPnpxPairingHandler>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<CPnpxPairingHandler>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  CPnpxPairingHandler::~CPnpxPairingHandler((CPnpxPairingHandler *)(Block + 6));
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180005410  mov     [rsp+arg_0], rbx
0x180005415  push    rdi
0x180005416  sub     rsp, 20h
0x18000541a  mov     dword ptr [rcx+8], 0C0000001h
0x180005421  lea     rax, ??_7?$CComAggObject@VCPnpxPairingHandler@@@ATL@@6B@; const ATL::CComAggObject<CPnpxPairingHandler>::`vftable'
0x180005428  mov     [rcx], rax
0x18000542b  mov     rdi, rcx
0x18000542e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005435  mov     ebx, edx
0x180005437  mov     rax, [rcx]
0x18000543a  mov     rax, [rax+10h]
0x18000543e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005443  lea     rcx, [rdi+18h]; this
0x180005447  call    ??1CPnpxPairingHandler@@UEAA@XZ; CPnpxPairingHandler::~CPnpxPairingHandler(void)
0x18000544c  test    bl, 1
0x18000544f  jz      short loc_180005459
0x180005451  mov     rcx, rdi; Block
0x180005454  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005459  mov     rbx, [rsp+28h+arg_0]
0x18000545e  mov     rax, rdi
0x180005461  add     rsp, 20h
0x180005465  pop     rdi
0x180005466  retn
```
