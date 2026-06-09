# ATL::CComObject<CTieringEngineApiServer>::`scalar deleting destructor'(uint)

- ea: `0x140002c50`
- end: `0x140002c7f`
- name: `??_G?$CComObject@VCTieringEngineApiServer@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `CTieringEngineApiServer *__fastcall(CTieringEngineApiServer *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001a00`
- `0x1400029a0`
- `0x140002c50`

## pseudocode

```c
CTieringEngineApiServer *__fastcall ATL::CComObject<CTieringEngineApiServer>::`scalar deleting destructor'(
        CTieringEngineApiServer *Block,
        char a2)
{
  ATL::CComObject<CTieringEngineApiServer>::~CComObject<CTieringEngineApiServer>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x140002c50  mov     [rsp+arg_0], rbx
0x140002c55  push    rdi
0x140002c56  sub     rsp, 20h
0x140002c5a  mov     ebx, edx
0x140002c5c  mov     rdi, rcx
0x140002c5f  call    ??1?$CComObject@VCTieringEngineApiServer@@@ATL@@UEAA@XZ; ATL::CComObject<CTieringEngineApiServer>::~CComObject<CTieringEngineApiServer>(void)
0x140002c64  test    bl, 1
0x140002c67  jz      short loc_140002C71
0x140002c69  mov     rcx, rdi; Block
0x140002c6c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002c71  mov     rbx, [rsp+28h+arg_0]
0x140002c76  mov     rax, rdi
0x140002c79  add     rsp, 20h
0x140002c7d  pop     rdi
0x140002c7e  retn
```
