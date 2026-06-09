# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18001c4b0`
- end: `0x18001c4dc`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c668`
- `0x18001c9d8`
- `0x18001d320`

## callees

- `0x1800132da`
- `0x18001c4b0`

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
0x18001c4b0  sub     rsp, 28h
0x18001c4b4  movzx   eax, word ptr [rcx+8]
0x18001c4b8  mov     r9, rdx
0x18001c4bb  cmp     r8, rax
0x18001c4be  jnz     short loc_18001C4D1
0x18001c4c0  mov     rdx, [rcx+18h]; Buf2
0x18001c4c4  mov     rcx, r9; Buf1
0x18001c4c7  call    memcmp_0
0x18001c4cc  mov     r8d, eax
0x18001c4cf  jmp     short loc_18001C4D4
0x18001c4d1  sub     r8d, eax
0x18001c4d4  mov     eax, r8d
0x18001c4d7  add     rsp, 28h
0x18001c4db  retn
```
