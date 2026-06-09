# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000717c`
- end: `0x1800071a8`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004eb0`
- `0x180009388`

## callees

- `0x18000717c`
- `0x18000d2b6`

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
0x18000717c  sub     rsp, 28h
0x180007180  movzx   eax, word ptr [rcx+8]
0x180007184  mov     r9, rdx
0x180007187  cmp     r8, rax
0x18000718a  jnz     short loc_18000719D
0x18000718c  mov     rdx, [rcx+18h]; Buf2
0x180007190  mov     rcx, r9; Buf1
0x180007193  call    memcmp_0
0x180007198  mov     r8d, eax
0x18000719b  jmp     short loc_1800071A0
0x18000719d  sub     r8d, eax
0x1800071a0  mov     eax, r8d
0x1800071a3  add     rsp, 28h
0x1800071a7  retn
```
