# ATL::CComContainedObject<CPnpxPairingHandler>::`scalar deleting destructor'(uint)

- ea: `0x1800054d0`
- end: `0x1800054ff`
- name: `??_G?$CComContainedObject@VCPnpxPairingHandler@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800019b0`
- `0x1800054d0`
- `0x18000d5b0`

## pseudocode

```c
CPnpxPairingHandler *__fastcall ATL::CComContainedObject<CPnpxPairingHandler>::`scalar deleting destructor'(
        CPnpxPairingHandler *Block,
        char a2)
{
  CPnpxPairingHandler::~CPnpxPairingHandler(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800054d0  mov     [rsp+arg_0], rbx
0x1800054d5  push    rdi
0x1800054d6  sub     rsp, 20h
0x1800054da  mov     ebx, edx
0x1800054dc  mov     rdi, rcx
0x1800054df  call    ??1CPnpxPairingHandler@@UEAA@XZ; CPnpxPairingHandler::~CPnpxPairingHandler(void)
0x1800054e4  test    bl, 1
0x1800054e7  jz      short loc_1800054F1
0x1800054e9  mov     rcx, rdi; Block
0x1800054ec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800054f1  mov     rbx, [rsp+28h+arg_0]
0x1800054f6  mov     rax, rdi
0x1800054f9  add     rsp, 20h
0x1800054fd  pop     rdi
0x1800054fe  retn
```
