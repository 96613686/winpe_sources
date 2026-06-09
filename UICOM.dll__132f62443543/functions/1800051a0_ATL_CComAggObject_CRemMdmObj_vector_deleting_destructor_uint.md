# ATL::CComAggObject<CRemMdmObj>::`vector deleting destructor'(uint)

- ea: `0x1800051a0`
- end: `0x1800051ee`
- name: `??_E?$CComAggObject@VCRemMdmObj@@@ATL@@UEAAPEAXI@Z`
- size: `78`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001170`
- `0x1800051a0`
- `0x180007010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CRemMdmObj>::`vector deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<CRemMdmObj>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800051a0  mov     [rsp+arg_0], rbx
0x1800051a5  push    rdi
0x1800051a6  sub     rsp, 20h
0x1800051aa  mov     dword ptr [rcx+8], 0C0000001h
0x1800051b1  lea     rax, ??_7?$CComAggObject@VCRemMdmObj@@@ATL@@6B@; const ATL::CComAggObject<CRemMdmObj>::`vftable'
0x1800051b8  mov     [rcx], rax
0x1800051bb  mov     rdi, rcx
0x1800051be  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800051c5  mov     ebx, edx
0x1800051c7  mov     rax, [rcx]
0x1800051ca  mov     rax, [rax+10h]
0x1800051ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051d3  test    bl, 1
0x1800051d6  jz      short loc_1800051E0
0x1800051d8  mov     rcx, rdi; Block
0x1800051db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800051e0  mov     rbx, [rsp+28h+arg_0]
0x1800051e5  mov     rax, rdi
0x1800051e8  add     rsp, 20h
0x1800051ec  pop     rdi
0x1800051ed  retn
```
