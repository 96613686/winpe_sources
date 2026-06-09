# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x1400041e0`
- end: `0x14000420c`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001e60`
- `0x140004490`
- `0x1400053c0`

## callees

- `0x1400041e0`
- `0x140007930`

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
0x1400041e0  sub     rsp, 28h
0x1400041e4  movzx   eax, word ptr [rcx+8]
0x1400041e8  mov     r9, rdx
0x1400041eb  cmp     r8, rax
0x1400041ee  jnz     short loc_140004201
0x1400041f0  mov     rdx, [rcx+18h]; Buf2
0x1400041f4  mov     rcx, r9; Buf1
0x1400041f7  call    memcmp_0
0x1400041fc  mov     r8d, eax
0x1400041ff  jmp     short loc_140004204
0x140004201  sub     r8d, eax
0x140004204  mov     eax, r8d
0x140004207  add     rsp, 28h
0x14000420b  retn
```
