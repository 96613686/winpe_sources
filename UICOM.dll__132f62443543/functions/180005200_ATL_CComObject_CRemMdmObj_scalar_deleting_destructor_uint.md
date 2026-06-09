# ATL::CComObject<CRemMdmObj>::`scalar deleting destructor'(uint)

- ea: `0x180005200`
- end: `0x18000524e`
- name: `??_G?$CComObject@VCRemMdmObj@@@ATL@@UEAAPEAXI@Z`
- size: `78`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001170`
- `0x180005200`
- `0x180007010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CRemMdmObj>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CRemMdmObj>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180005200  mov     [rsp+arg_0], rbx
0x180005205  push    rdi
0x180005206  sub     rsp, 20h
0x18000520a  mov     dword ptr [rcx+8], 0C0000001h
0x180005211  lea     rax, ??_7?$CComObject@VCRemMdmObj@@@ATL@@6B@; const ATL::CComObject<CRemMdmObj>::`vftable'
0x180005218  mov     [rcx], rax
0x18000521b  mov     rdi, rcx
0x18000521e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005225  mov     ebx, edx
0x180005227  mov     rax, [rcx]
0x18000522a  mov     rax, [rax+10h]
0x18000522e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005233  test    bl, 1
0x180005236  jz      short loc_180005240
0x180005238  mov     rcx, rdi; Block
0x18000523b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005240  mov     rbx, [rsp+28h+arg_0]
0x180005245  mov     rax, rdi
0x180005248  add     rsp, 20h
0x18000524c  pop     rdi
0x18000524d  retn
```
