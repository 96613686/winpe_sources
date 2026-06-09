# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x14000777c`
- end: `0x1400077a8`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400035bc`
- `0x14000417c`

## callees

- `0x14000777c`
- `0x14000f2c0`

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
0x14000777c  sub     rsp, 28h
0x140007780  movzx   eax, word ptr [rcx+8]
0x140007784  mov     r9, rdx
0x140007787  cmp     r8, rax
0x14000778a  jnz     short loc_14000779D
0x14000778c  mov     rdx, [rcx+18h]; Buf2
0x140007790  mov     rcx, r9; Buf1
0x140007793  call    memcmp_0
0x140007798  mov     r8d, eax
0x14000779b  jmp     short loc_1400077A0
0x14000779d  sub     r8d, eax
0x1400077a0  mov     eax, r8d
0x1400077a3  add     rsp, 28h
0x1400077a7  retn
```
