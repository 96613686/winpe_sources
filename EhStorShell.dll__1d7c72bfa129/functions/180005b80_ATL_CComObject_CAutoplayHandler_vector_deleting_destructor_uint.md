# ATL::CComObject<CAutoplayHandler>::`vector deleting destructor'(uint)

- ea: `0x180005b80`
- end: `0x180005baf`
- name: `??_E?$CComObject@VCAutoplayHandler@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(void *Block, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180005b80`
- `0x180005bb8`
- `0x180006b74`

## pseudocode

```c
void *__fastcall ATL::CComObject<CAutoplayHandler>::`vector deleting destructor'(
        void *Block,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char v4; // bl

  v4 = a2;
  ATL::CComObject<CAutoplayHandler>::~CComObject<CAutoplayHandler>((__int64)Block, a2, a3, a4);
  if ( (v4 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180005b80  mov     [rsp+arg_0], rbx
0x180005b85  push    rdi
0x180005b86  sub     rsp, 20h
0x180005b8a  mov     ebx, edx
0x180005b8c  mov     rdi, rcx
0x180005b8f  call    ??1?$CComObject@VCAutoplayHandler@@@ATL@@UEAA@XZ; ATL::CComObject<CAutoplayHandler>::~CComObject<CAutoplayHandler>(void)
0x180005b94  test    bl, 1
0x180005b97  jz      short loc_180005BA1
0x180005b99  mov     rcx, rdi; Block
0x180005b9c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005ba1  mov     rbx, [rsp+28h+arg_0]
0x180005ba6  mov     rax, rdi
0x180005ba9  add     rsp, 20h
0x180005bad  pop     rdi
0x180005bae  retn
```
