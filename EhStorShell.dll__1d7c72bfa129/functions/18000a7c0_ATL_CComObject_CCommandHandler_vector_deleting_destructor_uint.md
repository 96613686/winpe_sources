# ATL::CComObject<CCommandHandler>::`vector deleting destructor'(uint)

- ea: `0x18000a7c0`
- end: `0x18000a7ef`
- name: `??_E?$CComObject@VCCommandHandler@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `CCommandHandler *__fastcall(CCommandHandler *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180006b74`
- `0x18000a694`
- `0x18000a7c0`

## pseudocode

```c
CCommandHandler *__fastcall ATL::CComObject<CCommandHandler>::`vector deleting destructor'(
        CCommandHandler *Block,
        char a2)
{
  ATL::CComObject<CCommandHandler>::~CComObject<CCommandHandler>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000a7c0  mov     [rsp+arg_0], rbx
0x18000a7c5  push    rdi
0x18000a7c6  sub     rsp, 20h
0x18000a7ca  mov     ebx, edx
0x18000a7cc  mov     rdi, rcx
0x18000a7cf  call    ??1?$CComObject@VCCommandHandler@@@ATL@@UEAA@XZ; ATL::CComObject<CCommandHandler>::~CComObject<CCommandHandler>(void)
0x18000a7d4  test    bl, 1
0x18000a7d7  jz      short loc_18000A7E1
0x18000a7d9  mov     rcx, rdi; Block
0x18000a7dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a7e1  mov     rbx, [rsp+28h+arg_0]
0x18000a7e6  mov     rax, rdi
0x18000a7e9  add     rsp, 20h
0x18000a7ed  pop     rdi
0x18000a7ee  retn
```
