# ATL::CComObject<CTieringEngineTaskHandler>::`vector deleting destructor'(uint)

- ea: `0x140002c90`
- end: `0x140002cbf`
- name: `??_E?$CComObject@VCTieringEngineTaskHandler@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `CTieringEngineTaskHandler *__fastcall(CTieringEngineTaskHandler *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x140001a00`
- `0x140002a14`
- `0x140002c90`

## pseudocode

```c
CTieringEngineTaskHandler *__fastcall ATL::CComObject<CTieringEngineTaskHandler>::`vector deleting destructor'(
        CTieringEngineTaskHandler *Block,
        char a2)
{
  ATL::CComObject<CTieringEngineTaskHandler>::~CComObject<CTieringEngineTaskHandler>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x140002c90  mov     [rsp+arg_0], rbx
0x140002c95  push    rdi
0x140002c96  sub     rsp, 20h
0x140002c9a  mov     ebx, edx
0x140002c9c  mov     rdi, rcx
0x140002c9f  call    ??1?$CComObject@VCTieringEngineTaskHandler@@@ATL@@UEAA@XZ; ATL::CComObject<CTieringEngineTaskHandler>::~CComObject<CTieringEngineTaskHandler>(void)
0x140002ca4  test    bl, 1
0x140002ca7  jz      short loc_140002CB1
0x140002ca9  mov     rcx, rdi; Block
0x140002cac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002cb1  mov     rbx, [rsp+28h+arg_0]
0x140002cb6  mov     rax, rdi
0x140002cb9  add     rsp, 20h
0x140002cbd  pop     rdi
0x140002cbe  retn
```
