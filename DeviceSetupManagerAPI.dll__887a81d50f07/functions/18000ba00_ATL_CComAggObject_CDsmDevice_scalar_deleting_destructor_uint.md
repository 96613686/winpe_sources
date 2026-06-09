# ATL::CComAggObject<CDsmDevice>::`scalar deleting destructor'(uint)

- ea: `0x18000ba00`
- end: `0x18000ba34`
- name: `??_G?$CComAggObject@VCDsmDevice@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001c6c`
- `0x18000b900`
- `0x18000ba00`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CDsmDevice>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComAggObject<CDsmDevice>::~CComAggObject<CDsmDevice>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000ba00  mov     [rsp+arg_0], rbx
0x18000ba05  push    rdi
0x18000ba06  sub     rsp, 20h
0x18000ba0a  mov     ebx, edx
0x18000ba0c  mov     rdi, rcx
0x18000ba0f  call    ??1?$CComAggObject@VCDsmDevice@@@ATL@@UEAA@XZ; ATL::CComAggObject<CDsmDevice>::~CComAggObject<CDsmDevice>(void)
0x18000ba14  test    bl, 1
0x18000ba17  jz      short loc_18000BA26
0x18000ba19  mov     edx, 80h
0x18000ba1e  mov     rcx, rdi; Block
0x18000ba21  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ba26  mov     rbx, [rsp+28h+arg_0]
0x18000ba2b  mov     rax, rdi
0x18000ba2e  add     rsp, 20h
0x18000ba32  pop     rdi
0x18000ba33  retn
```
