# ATL::CComAggObject<CTieringEngineTaskHandler>::`scalar deleting destructor'(uint)

- ea: `0x140002c10`
- end: `0x140002c3f`
- name: `??_G?$CComAggObject@VCTieringEngineTaskHandler@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x140001a00`
- `0x140002924`
- `0x140002c10`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CTieringEngineTaskHandler>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComAggObject<CTieringEngineTaskHandler>::~CComAggObject<CTieringEngineTaskHandler>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x140002c10  mov     [rsp+arg_0], rbx
0x140002c15  push    rdi
0x140002c16  sub     rsp, 20h
0x140002c1a  mov     ebx, edx
0x140002c1c  mov     rdi, rcx
0x140002c1f  call    ??1?$CComAggObject@VCTieringEngineTaskHandler@@@ATL@@UEAA@XZ; ATL::CComAggObject<CTieringEngineTaskHandler>::~CComAggObject<CTieringEngineTaskHandler>(void)
0x140002c24  test    bl, 1
0x140002c27  jz      short loc_140002C31
0x140002c29  mov     rcx, rdi; Block
0x140002c2c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002c31  mov     rbx, [rsp+28h+arg_0]
0x140002c36  mov     rax, rdi
0x140002c39  add     rsp, 20h
0x140002c3d  pop     rdi
0x140002c3e  retn
```
