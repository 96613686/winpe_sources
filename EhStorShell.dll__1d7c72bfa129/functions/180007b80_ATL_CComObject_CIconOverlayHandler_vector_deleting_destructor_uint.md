# ATL::CComObject<CIconOverlayHandler>::`vector deleting destructor'(uint)

- ea: `0x180007b80`
- end: `0x180007baf`
- name: `??_E?$CComObject@VCIconOverlayHandler@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(void *Block, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180006b74`
- `0x180007a5c`
- `0x180007b80`

## pseudocode

```c
void *__fastcall ATL::CComObject<CIconOverlayHandler>::`vector deleting destructor'(
        void *Block,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char v4; // bl

  v4 = a2;
  ATL::CComObject<CIconOverlayHandler>::~CComObject<CIconOverlayHandler>((__int64)Block, a2, a3, a4);
  if ( (v4 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180007b80  mov     [rsp+arg_0], rbx
0x180007b85  push    rdi
0x180007b86  sub     rsp, 20h
0x180007b8a  mov     ebx, edx
0x180007b8c  mov     rdi, rcx
0x180007b8f  call    ??1?$CComObject@VCIconOverlayHandler@@@ATL@@UEAA@XZ; ATL::CComObject<CIconOverlayHandler>::~CComObject<CIconOverlayHandler>(void)
0x180007b94  test    bl, 1
0x180007b97  jz      short loc_180007BA1
0x180007b99  mov     rcx, rdi; Block
0x180007b9c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007ba1  mov     rbx, [rsp+28h+arg_0]
0x180007ba6  mov     rax, rdi
0x180007ba9  add     rsp, 20h
0x180007bad  pop     rdi
0x180007bae  retn
```
