# ATL::CComAggObject<CTieringEngineApiServer>::`vector deleting destructor'(uint)

- ea: `0x140002bd0`
- end: `0x140002bff`
- name: `??_E?$CComAggObject@VCTieringEngineApiServer@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001a00`
- `0x1400028ac`
- `0x140002bd0`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CTieringEngineApiServer>::`vector deleting destructor'(void *Block, char a2)
{
  ATL::CComAggObject<CTieringEngineApiServer>::~CComAggObject<CTieringEngineApiServer>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x140002bd0  mov     [rsp+arg_0], rbx
0x140002bd5  push    rdi
0x140002bd6  sub     rsp, 20h
0x140002bda  mov     ebx, edx
0x140002bdc  mov     rdi, rcx
0x140002bdf  call    ??1?$CComAggObject@VCTieringEngineApiServer@@@ATL@@UEAA@XZ; ATL::CComAggObject<CTieringEngineApiServer>::~CComAggObject<CTieringEngineApiServer>(void)
0x140002be4  test    bl, 1
0x140002be7  jz      short loc_140002BF1
0x140002be9  mov     rcx, rdi; Block
0x140002bec  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002bf1  mov     rbx, [rsp+28h+arg_0]
0x140002bf6  mov     rax, rdi
0x140002bf9  add     rsp, 20h
0x140002bfd  pop     rdi
0x140002bfe  retn
```
