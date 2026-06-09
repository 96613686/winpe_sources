# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180010a20`
- end: `0x180010a4c`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dd5c`
- `0x180010d94`
- `0x1800121f4`

## callees

- `0x180010a20`
- `0x1800283f0`

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
0x180010a20  sub     rsp, 28h
0x180010a24  movzx   eax, word ptr [rcx+8]
0x180010a28  mov     r9, rdx
0x180010a2b  cmp     r8, rax
0x180010a2e  jnz     short loc_180010A41
0x180010a30  mov     rdx, [rcx+18h]; Buf2
0x180010a34  mov     rcx, r9; Buf1
0x180010a37  call    memcmp_0
0x180010a3c  mov     r8d, eax
0x180010a3f  jmp     short loc_180010A44
0x180010a41  sub     r8d, eax
0x180010a44  mov     eax, r8d
0x180010a47  add     rsp, 28h
0x180010a4b  retn
```
