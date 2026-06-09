# ATL::CComObject<CPimcContext>::`vector deleting destructor'(uint)

- ea: `0x18000a030`
- end: `0x18000a064`
- name: `??_E?$CComObject@VCPimcContext@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009f28`
- `0x18000a030`
- `0x18000ce0c`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall ATL::CComObject<CPimcContext>::`vector deleting destructor'(
        struct _RTL_CRITICAL_SECTION *Block,
        char a2)
{
  ATL::CComObject<CPimcContext>::~CComObject<CPimcContext>(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000a030  mov     [rsp+arg_0], rbx
0x18000a035  push    rdi
0x18000a036  sub     rsp, 20h
0x18000a03a  mov     ebx, edx
0x18000a03c  mov     rdi, rcx
0x18000a03f  call    ??1?$CComObject@VCPimcContext@@@ATL@@UEAA@XZ; ATL::CComObject<CPimcContext>::~CComObject<CPimcContext>(void)
0x18000a044  test    bl, 1
0x18000a047  jz      short loc_18000A056
0x18000a049  mov     edx, 140h
0x18000a04e  mov     rcx, rdi; Block
0x18000a051  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000a056  mov     rbx, [rsp+28h+arg_0]
0x18000a05b  mov     rax, rdi
0x18000a05e  add     rsp, 20h
0x18000a062  pop     rdi
0x18000a063  retn
```
