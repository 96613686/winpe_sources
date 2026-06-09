# ATL::CComObject<CContextMenuHandler>::`vector deleting destructor'(uint)

- ea: `0x180007b40`
- end: `0x180007b6f`
- name: `??_E?$CComObject@VCContextMenuHandler@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `CContextMenuHandler *__fastcall(CContextMenuHandler *Block, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180004ea0`
- `0x180006b74`
- `0x180007b40`

## pseudocode

```c
CContextMenuHandler *__fastcall ATL::CComObject<CContextMenuHandler>::`vector deleting destructor'(
        CContextMenuHandler *Block,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char v4; // bl

  v4 = a2;
  ATL::CComObject<CContextMenuHandler>::~CComObject<CContextMenuHandler>(Block, a2, a3, a4);
  if ( (v4 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180007b40  mov     [rsp+arg_0], rbx
0x180007b45  push    rdi
0x180007b46  sub     rsp, 20h
0x180007b4a  mov     ebx, edx
0x180007b4c  mov     rdi, rcx
0x180007b4f  call    ??1?$CComObject@VCContextMenuHandler@@@ATL@@UEAA@XZ; ATL::CComObject<CContextMenuHandler>::~CComObject<CContextMenuHandler>(void)
0x180007b54  test    bl, 1
0x180007b57  jz      short loc_180007B61
0x180007b59  mov     rcx, rdi; Block
0x180007b5c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007b61  mov     rbx, [rsp+28h+arg_0]
0x180007b66  mov     rax, rdi
0x180007b69  add     rsp, 20h
0x180007b6d  pop     rdi
0x180007b6e  retn
```
