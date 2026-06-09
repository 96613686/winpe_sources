# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x14000eb0c`
- end: `0x14000eb38`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000ed00`
- `0x14000f0b0`
- `0x14000fa98`

## callees

- `0x14000eb0c`
- `0x140029be8`

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
0x14000eb0c  sub     rsp, 28h
0x14000eb10  movzx   eax, word ptr [rcx+8]
0x14000eb14  mov     r9, rdx
0x14000eb17  cmp     r8, rax
0x14000eb1a  jnz     short loc_14000EB2D
0x14000eb1c  mov     rdx, [rcx+18h]; Buf2
0x14000eb20  mov     rcx, r9; Buf1
0x14000eb23  call    memcmp_0
0x14000eb28  mov     r8d, eax
0x14000eb2b  jmp     short loc_14000EB30
0x14000eb2d  sub     r8d, eax
0x14000eb30  mov     eax, r8d
0x14000eb33  add     rsp, 28h
0x14000eb37  retn
```
