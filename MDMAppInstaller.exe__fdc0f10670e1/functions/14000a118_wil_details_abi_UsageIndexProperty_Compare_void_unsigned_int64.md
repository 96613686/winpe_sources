# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x14000a118`
- end: `0x14000a144`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b4b4`
- `0x14000de14`
- `0x14000f718`

## callees

- `0x14000a118`
- `0x14001a886`

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
0x14000a118  sub     rsp, 28h
0x14000a11c  movzx   eax, word ptr [rcx+8]
0x14000a120  mov     r9, rdx
0x14000a123  cmp     r8, rax
0x14000a126  jnz     short loc_14000A139
0x14000a128  mov     rdx, [rcx+18h]; Buf2
0x14000a12c  mov     rcx, r9; Buf1
0x14000a12f  call    memcmp_0
0x14000a134  mov     r8d, eax
0x14000a137  jmp     short loc_14000A13C
0x14000a139  sub     r8d, eax
0x14000a13c  mov     eax, r8d
0x14000a13f  add     rsp, 28h
0x14000a143  retn
```
