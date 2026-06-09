# ATL::CComAggObject<CAddMdmObj>::`scalar deleting destructor'(uint)

- ea: `0x1800059b0`
- end: `0x1800059fe`
- name: `??_G?$CComAggObject@VCAddMdmObj@@@ATL@@UEAAPEAXI@Z`
- size: `78`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001170`
- `0x1800059b0`
- `0x180007010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CAddMdmObj>::`scalar deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<CAddMdmObj>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800059b0  mov     [rsp+arg_0], rbx
0x1800059b5  push    rdi
0x1800059b6  sub     rsp, 20h
0x1800059ba  mov     dword ptr [rcx+8], 0C0000001h
0x1800059c1  lea     rax, ??_7?$CComAggObject@VCAddMdmObj@@@ATL@@6B@; const ATL::CComAggObject<CAddMdmObj>::`vftable'
0x1800059c8  mov     [rcx], rax
0x1800059cb  mov     rdi, rcx
0x1800059ce  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800059d5  mov     ebx, edx
0x1800059d7  mov     rax, [rcx]
0x1800059da  mov     rax, [rax+10h]
0x1800059de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e3  test    bl, 1
0x1800059e6  jz      short loc_1800059F0
0x1800059e8  mov     rcx, rdi; Block
0x1800059eb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800059f0  mov     rbx, [rsp+28h+arg_0]
0x1800059f5  mov     rax, rdi
0x1800059f8  add     rsp, 20h
0x1800059fc  pop     rdi
0x1800059fd  retn
```
