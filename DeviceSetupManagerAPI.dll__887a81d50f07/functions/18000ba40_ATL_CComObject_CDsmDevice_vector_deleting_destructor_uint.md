# ATL::CComObject<CDsmDevice>::`vector deleting destructor'(uint)

- ea: `0x18000ba40`
- end: `0x18000ba74`
- name: `??_E?$CComObject@VCDsmDevice@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001c6c`
- `0x18000b988`
- `0x18000ba40`

## pseudocode

```c
void *__fastcall ATL::CComObject<CDsmDevice>::`vector deleting destructor'(void *Block, char a2)
{
  ATL::CComObject<CDsmDevice>::~CComObject<CDsmDevice>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000ba40  mov     [rsp+arg_0], rbx
0x18000ba45  push    rdi
0x18000ba46  sub     rsp, 20h
0x18000ba4a  mov     ebx, edx
0x18000ba4c  mov     rdi, rcx
0x18000ba4f  call    ??1?$CComObject@VCDsmDevice@@@ATL@@UEAA@XZ; ATL::CComObject<CDsmDevice>::~CComObject<CDsmDevice>(void)
0x18000ba54  test    bl, 1
0x18000ba57  jz      short loc_18000BA66
0x18000ba59  mov     edx, 70h ; 'p'
0x18000ba5e  mov     rcx, rdi; Block
0x18000ba61  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ba66  mov     rbx, [rsp+28h+arg_0]
0x18000ba6b  mov     rax, rdi
0x18000ba6e  add     rsp, 20h
0x18000ba72  pop     rdi
0x18000ba73  retn
```
