# ATL::CComObject<CPimcTablet>::`vector deleting destructor'(uint)

- ea: `0x18000c110`
- end: `0x18000c144`
- name: `??_E?$CComObject@VCPimcTablet@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000bddc`
- `0x18000c110`
- `0x18000ce0c`

## pseudocode

```c
CPimcTablet *__fastcall ATL::CComObject<CPimcTablet>::`vector deleting destructor'(CPimcTablet *Block, char a2)
{
  ATL::CComObject<CPimcTablet>::~CComObject<CPimcTablet>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000c110  mov     [rsp+arg_0], rbx
0x18000c115  push    rdi
0x18000c116  sub     rsp, 20h
0x18000c11a  mov     ebx, edx
0x18000c11c  mov     rdi, rcx
0x18000c11f  call    ??1?$CComObject@VCPimcTablet@@@ATL@@UEAA@XZ; ATL::CComObject<CPimcTablet>::~CComObject<CPimcTablet>(void)
0x18000c124  test    bl, 1
0x18000c127  jz      short loc_18000C136
0x18000c129  mov     edx, 60h ; '`'
0x18000c12e  mov     rcx, rdi; Block
0x18000c131  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c136  mov     rbx, [rsp+28h+arg_0]
0x18000c13b  mov     rax, rdi
0x18000c13e  add     rsp, 20h
0x18000c142  pop     rdi
0x18000c143  retn
```
