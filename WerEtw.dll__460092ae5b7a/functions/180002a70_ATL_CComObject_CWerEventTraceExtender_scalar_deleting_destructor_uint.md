# ATL::CComObject<CWerEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x180002a70`
- end: `0x180002aa4`
- name: `??_G?$CComObject@VCWerEventTraceExtender@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001894`
- `0x1800028cc`
- `0x180002a70`

## pseudocode

```c
void *__fastcall ATL::CComObject<CWerEventTraceExtender>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComObject<CWerEventTraceExtender>::~CComObject<CWerEventTraceExtender>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180002a70  mov     [rsp+arg_0], rbx
0x180002a75  push    rdi
0x180002a76  sub     rsp, 20h
0x180002a7a  mov     ebx, edx
0x180002a7c  mov     rdi, rcx
0x180002a7f  call    ??1?$CComObject@VCWerEventTraceExtender@@@ATL@@UEAA@XZ; ATL::CComObject<CWerEventTraceExtender>::~CComObject<CWerEventTraceExtender>(void)
0x180002a84  test    bl, 1
0x180002a87  jz      short loc_180002A96
0x180002a89  mov     edx, 0AE8h
0x180002a8e  mov     rcx, rdi; Block
0x180002a91  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002a96  mov     rbx, [rsp+28h+arg_0]
0x180002a9b  mov     rax, rdi
0x180002a9e  add     rsp, 20h
0x180002aa2  pop     rdi
0x180002aa3  retn
```
