# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x1400069dc`
- end: `0x140006a08`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006e48`
- `0x140008950`
- `0x140009ae0`

## callees

- `0x140003a94`
- `0x1400069dc`

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
0x1400069dc  sub     rsp, 28h
0x1400069e0  movzx   eax, word ptr [rcx+8]
0x1400069e4  mov     r9, rdx
0x1400069e7  cmp     r8, rax
0x1400069ea  jnz     short loc_1400069FD
0x1400069ec  mov     rdx, [rcx+18h]; Buf2
0x1400069f0  mov     rcx, r9; Buf1
0x1400069f3  call    memcmp_0
0x1400069f8  mov     r8d, eax
0x1400069fb  jmp     short loc_140006A00
0x1400069fd  sub     r8d, eax
0x140006a00  mov     eax, r8d
0x140006a03  add     rsp, 28h
0x140006a07  retn
```
