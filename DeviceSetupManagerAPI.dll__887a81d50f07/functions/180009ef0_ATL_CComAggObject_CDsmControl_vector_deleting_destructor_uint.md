# ATL::CComAggObject<CDsmControl>::`vector deleting destructor'(uint)

- ea: `0x180009ef0`
- end: `0x180009f43`
- name: `??_E?$CComAggObject@VCDsmControl@@@ATL@@UEAAPEAXI@Z`
- size: `83`
- prototype: `_DWORD *__fastcall(_DWORD *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001c6c`
- `0x180009ef0`
- `0x18000f010`

## pseudocode

```c
_DWORD *__fastcall ATL::CComAggObject<CDsmControl>::`vector deleting destructor'(_DWORD *Block, char a2)
{
  Block[2] = -1073741823;
  *(_QWORD *)Block = &ATL::CComAggObject<CDsmControl>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180009ef0  mov     [rsp+arg_0], rbx
0x180009ef5  push    rdi
0x180009ef6  sub     rsp, 20h
0x180009efa  mov     dword ptr [rcx+8], 0C0000001h
0x180009f01  lea     rax, ??_7?$CComAggObject@VCDsmControl@@@ATL@@6B@; const ATL::CComAggObject<CDsmControl>::`vftable'
0x180009f08  mov     [rcx], rax
0x180009f0b  mov     rdi, rcx
0x180009f0e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009f15  mov     ebx, edx
0x180009f17  mov     rax, [rcx]
0x180009f1a  mov     rax, [rax+10h]
0x180009f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f23  test    bl, 1
0x180009f26  jz      short loc_180009F35
0x180009f28  mov     edx, 20h ; ' '
0x180009f2d  mov     rcx, rdi; Block
0x180009f30  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009f35  mov     rbx, [rsp+28h+arg_0]
0x180009f3a  mov     rax, rdi
0x180009f3d  add     rsp, 20h
0x180009f41  pop     rdi
0x180009f42  retn
```
