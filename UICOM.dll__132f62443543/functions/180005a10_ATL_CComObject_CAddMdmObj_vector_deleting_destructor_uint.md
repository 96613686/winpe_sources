# ATL::CComObject<CAddMdmObj>::`vector deleting destructor'(uint)

- ea: `0x180005a10`
- end: `0x180005a5e`
- name: `??_E?$CComObject@VCAddMdmObj@@@ATL@@UEAAPEAXI@Z`
- size: `78`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001170`
- `0x180005a10`
- `0x180007010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CAddMdmObj>::`vector deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CAddMdmObj>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180005a10  mov     [rsp+arg_0], rbx
0x180005a15  push    rdi
0x180005a16  sub     rsp, 20h
0x180005a1a  mov     dword ptr [rcx+8], 0C0000001h
0x180005a21  lea     rax, ??_7?$CComObject@VCAddMdmObj@@@ATL@@6B@; const ATL::CComObject<CAddMdmObj>::`vftable'
0x180005a28  mov     [rcx], rax
0x180005a2b  mov     rdi, rcx
0x180005a2e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180005a35  mov     ebx, edx
0x180005a37  mov     rax, [rcx]
0x180005a3a  mov     rax, [rax+10h]
0x180005a3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a43  test    bl, 1
0x180005a46  jz      short loc_180005A50
0x180005a48  mov     rcx, rdi; Block
0x180005a4b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005a50  mov     rbx, [rsp+28h+arg_0]
0x180005a55  mov     rax, rdi
0x180005a58  add     rsp, 20h
0x180005a5c  pop     rdi
0x180005a5d  retn
```
