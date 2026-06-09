# ATL::CComAggObject<CPimcManager>::`scalar deleting destructor'(uint)

- ea: `0x1800021b0`
- end: `0x1800021e4`
- name: `??_G?$CComAggObject@VCPimcManager@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800020a8`
- `0x1800021b0`
- `0x18000ce0c`

## pseudocode

```c
void *__fastcall ATL::CComAggObject<CPimcManager>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComAggObject<CPimcManager>::~CComAggObject<CPimcManager>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x1800021b0  mov     [rsp+arg_0], rbx
0x1800021b5  push    rdi
0x1800021b6  sub     rsp, 20h
0x1800021ba  mov     ebx, edx
0x1800021bc  mov     rdi, rcx
0x1800021bf  call    ??1?$CComAggObject@VCPimcManager@@@ATL@@UEAA@XZ
0x1800021c4  test    bl, 1
0x1800021c7  jz      short loc_1800021D6
0x1800021c9  mov     edx, 68h ; 'h'
0x1800021ce  mov     rcx, rdi; Block
0x1800021d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x1800021d6  mov     rbx, [rsp+28h+arg_0]
0x1800021db  mov     rax, rdi
0x1800021de  add     rsp, 20h
0x1800021e2  pop     rdi
0x1800021e3  retn
```
