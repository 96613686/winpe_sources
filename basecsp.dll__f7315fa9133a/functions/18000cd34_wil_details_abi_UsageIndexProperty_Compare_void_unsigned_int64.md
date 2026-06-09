# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000cd34`
- end: `0x18000cd60`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dc70`
- `0x180014544`
- `0x180015698`

## callees

- `0x18000cd34`
- `0x18002cf46`

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
0x18000cd34  sub     rsp, 28h
0x18000cd38  movzx   eax, word ptr [rcx+8]
0x18000cd3c  mov     r9, rdx
0x18000cd3f  cmp     r8, rax
0x18000cd42  jnz     short loc_18000CD55
0x18000cd44  mov     rdx, [rcx+18h]; Buf2
0x18000cd48  mov     rcx, r9; Buf1
0x18000cd4b  call    memcmp_0
0x18000cd50  mov     r8d, eax
0x18000cd53  jmp     short loc_18000CD58
0x18000cd55  sub     r8d, eax
0x18000cd58  mov     eax, r8d
0x18000cd5b  add     rsp, 28h
0x18000cd5f  retn
```
