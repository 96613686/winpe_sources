# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x14000a580`
- end: `0x14000a5ac`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000ac1c`
- `0x14000b5fc`
- `0x14000c0f8`

## callees

- `0x14000a580`
- `0x14002acec`

## pseudocode

```c
__int64 __fastcall wil::details_abi::UsageIndexProperty::Compare(const void **this, void *a2, size_t a3)
{
  __int64 v3; // rax

  v3 = *((unsigned __int16 *)this + 4);
  if ( a3 == v3 )
    return (unsigned int)memcmp_0(a2, this[3], a3);
  else
    return (unsigned int)(a3 - v3);
}

```

## disassembly

```asm
0x14000a580  sub     rsp, 28h
0x14000a584  movzx   eax, word ptr [rcx+8]
0x14000a588  mov     r9, rdx
0x14000a58b  cmp     r8, rax
0x14000a58e  jnz     short loc_14000A5A1
0x14000a590  mov     rdx, [rcx+18h]; Buf2
0x14000a594  mov     rcx, r9; Buf1
0x14000a597  call    memcmp_0
0x14000a59c  mov     r8d, eax
0x14000a59f  jmp     short loc_14000A5A4
0x14000a5a1  sub     r8d, eax
0x14000a5a4  mov     eax, r8d
0x14000a5a7  add     rsp, 28h
0x14000a5ab  retn
```
