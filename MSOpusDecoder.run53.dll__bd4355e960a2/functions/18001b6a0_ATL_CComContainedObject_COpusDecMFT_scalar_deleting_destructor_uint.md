# ATL::CComContainedObject<COpusDecMFT>::`scalar deleting destructor'(uint)

- ea: `0x18001b6a0`
- end: `0x18001b6d4`
- name: `??_G?$CComContainedObject@VCOpusDecMFT@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001914`
- `0x18001b45c`
- `0x18001b6a0`

## pseudocode

```c
COpusDecMFT *__fastcall ATL::CComContainedObject<COpusDecMFT>::`scalar deleting destructor'(
        COpusDecMFT *Block,
        char a2)
{
  COpusDecMFT::~COpusDecMFT(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18001b6a0  mov     [rsp+arg_0], rbx
0x18001b6a5  push    rdi
0x18001b6a6  sub     rsp, 20h
0x18001b6aa  mov     ebx, edx
0x18001b6ac  mov     rdi, rcx
0x18001b6af  call    ??1COpusDecMFT@@UEAA@XZ; COpusDecMFT::~COpusDecMFT(void)
0x18001b6b4  test    bl, 1
0x18001b6b7  jz      short loc_18001B6C6
0x18001b6b9  mov     edx, 140h
0x18001b6be  mov     rcx, rdi; Block
0x18001b6c1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b6c6  mov     rbx, [rsp+28h+arg_0]
0x18001b6cb  mov     rax, rdi
0x18001b6ce  add     rsp, 20h
0x18001b6d2  pop     rdi
0x18001b6d3  retn
```
