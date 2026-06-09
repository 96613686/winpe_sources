# ATL::CComObject<CDsmControl>::`vector deleting destructor'(uint)

- ea: `0x180009f50`
- end: `0x180009fa3`
- name: `??_E?$CComObject@VCDsmControl@@@ATL@@UEAAPEAXI@Z`
- size: `83`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001c6c`
- `0x180009f50`
- `0x18000f010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComObject<CDsmControl>::`vector deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComObject<CDsmControl>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180009f50  mov     [rsp+arg_0], rbx
0x180009f55  push    rdi
0x180009f56  sub     rsp, 20h
0x180009f5a  mov     dword ptr [rcx+8], 0C0000001h
0x180009f61  lea     rax, ??_7?$CComObject@VCDsmControl@@@ATL@@6B@; const ATL::CComObject<CDsmControl>::`vftable'
0x180009f68  mov     [rcx], rax
0x180009f6b  mov     rdi, rcx
0x180009f6e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009f75  mov     ebx, edx
0x180009f77  mov     rax, [rcx]
0x180009f7a  mov     rax, [rax+10h]
0x180009f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f83  test    bl, 1
0x180009f86  jz      short loc_180009F95
0x180009f88  mov     edx, 10h
0x180009f8d  mov     rcx, rdi; Block
0x180009f90  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009f95  mov     rbx, [rsp+28h+arg_0]
0x180009f9a  mov     rax, rdi
0x180009f9d  add     rsp, 20h
0x180009fa1  pop     rdi
0x180009fa2  retn
```
