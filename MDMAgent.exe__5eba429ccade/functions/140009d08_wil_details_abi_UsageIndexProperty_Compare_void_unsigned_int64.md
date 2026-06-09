# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x140009d08`
- end: `0x140009d34`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b3f8`
- `0x14000bb90`
- `0x14000cca8`

## callees

- `0x140009d08`
- `0x140018634`

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
0x140009d08  sub     rsp, 28h
0x140009d0c  movzx   eax, word ptr [rcx+8]
0x140009d10  mov     r9, rdx
0x140009d13  cmp     r8, rax
0x140009d16  jnz     short loc_140009D29
0x140009d18  mov     rdx, [rcx+18h]; Buf2
0x140009d1c  mov     rcx, r9; Buf1
0x140009d1f  call    memcmp_0
0x140009d24  mov     r8d, eax
0x140009d27  jmp     short loc_140009D2C
0x140009d29  sub     r8d, eax
0x140009d2c  mov     eax, r8d
0x140009d2f  add     rsp, 28h
0x140009d33  retn
```
