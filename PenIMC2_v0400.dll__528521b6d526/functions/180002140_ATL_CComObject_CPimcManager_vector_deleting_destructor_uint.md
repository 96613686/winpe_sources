# ATL::CComObject<CPimcManager>::`vector deleting destructor'(uint)

- ea: `0x180002140`
- end: `0x180002174`
- name: `??_E?$CComObject@VCPimcManager@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001edc`
- `0x180002140`
- `0x18000ce0c`

## pseudocode

```c
void *__fastcall ATL::CComObject<CPimcManager>::`vector deleting destructor'(void *Block, char a2)
{
  ATL::CComObject<CPimcManager>::~CComObject<CPimcManager>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180002140  mov     [rsp+arg_0], rbx
0x180002145  push    rdi
0x180002146  sub     rsp, 20h
0x18000214a  mov     ebx, edx
0x18000214c  mov     rdi, rcx
0x18000214f  call    ??1?$CComObject@VCPimcManager@@@ATL@@UEAA@XZ; ATL::CComObject<CPimcManager>::~CComObject<CPimcManager>(void)
0x180002154  test    bl, 1
0x180002157  jz      short loc_180002166
0x180002159  mov     edx, 58h ; 'X'
0x18000215e  mov     rcx, rdi; Block
0x180002161  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180002166  mov     rbx, [rsp+28h+arg_0]
0x18000216b  mov     rax, rdi
0x18000216e  add     rsp, 20h
0x180002172  pop     rdi
0x180002173  retn
```
