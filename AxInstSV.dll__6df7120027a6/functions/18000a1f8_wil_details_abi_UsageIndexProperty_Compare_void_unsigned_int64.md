# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000a1f8`
- end: `0x18000a224`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ad78`
- `0x18000ccd0`
- `0x18000df24`

## callees

- `0x18000a1f8`
- `0x180014310`

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
0x18000a1f8  sub     rsp, 28h
0x18000a1fc  movzx   eax, word ptr [rcx+8]
0x18000a200  mov     r9, rdx
0x18000a203  cmp     r8, rax
0x18000a206  jnz     short loc_18000A219
0x18000a208  mov     rdx, [rcx+18h]; Buf2
0x18000a20c  mov     rcx, r9; Buf1
0x18000a20f  call    memcmp_0
0x18000a214  mov     r8d, eax
0x18000a217  jmp     short loc_18000A21C
0x18000a219  sub     r8d, eax
0x18000a21c  mov     eax, r8d
0x18000a21f  add     rsp, 28h
0x18000a223  retn
```
