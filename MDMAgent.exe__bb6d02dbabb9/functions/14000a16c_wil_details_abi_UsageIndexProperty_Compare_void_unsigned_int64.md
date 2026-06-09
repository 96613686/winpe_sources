# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x14000a16c`
- end: `0x14000a199`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `45`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b918`
- `0x14000c0dc`
- `0x14000d290`

## callees

- `0x14000a16c`
- `0x140019394`

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
0x14000a16c  sub     rsp, 28h
0x14000a170  movzx   eax, word ptr [rcx+8]
0x14000a174  mov     r9, rdx
0x14000a177  cmp     r8, rax
0x14000a17a  jnz     short loc_14000A18D
0x14000a17c  mov     rdx, [rcx+18h]; Buf2
0x14000a180  mov     rcx, r9; Buf1
0x14000a183  call    memcmp_0
0x14000a188  mov     r8d, eax
0x14000a18b  jmp     short loc_14000A190
0x14000a18d  sub     r8d, eax
0x14000a190  mov     eax, r8d
0x14000a193  add     rsp, 28h
0x14000a197  retn
```
