# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x1800082f8`
- end: `0x180008324`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800089b0`
- `0x180008f6c`
- `0x180009938`

## callees

- `0x1800082f8`
- `0x18001b434`

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
0x1800082f8  sub     rsp, 28h
0x1800082fc  movzx   eax, word ptr [rcx+8]
0x180008300  mov     r9, rdx
0x180008303  cmp     r8, rax
0x180008306  jnz     short loc_180008319
0x180008308  mov     rdx, [rcx+18h]; Buf2
0x18000830c  mov     rcx, r9; Buf1
0x18000830f  call    memcmp_0
0x180008314  mov     r8d, eax
0x180008317  jmp     short loc_18000831C
0x180008319  sub     r8d, eax
0x18000831c  mov     eax, r8d
0x18000831f  add     rsp, 28h
0x180008323  retn
```
