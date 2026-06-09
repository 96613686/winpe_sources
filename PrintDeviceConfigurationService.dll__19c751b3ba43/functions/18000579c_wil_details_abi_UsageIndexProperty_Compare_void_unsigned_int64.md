# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000579c`
- end: `0x1800057c8`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005bb4`
- `0x180006ee4`
- `0x180007e68`

## callees

- `0x180003609`
- `0x18000579c`

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
0x18000579c  sub     rsp, 28h
0x1800057a0  movzx   eax, word ptr [rcx+8]
0x1800057a4  mov     r9, rdx
0x1800057a7  cmp     r8, rax
0x1800057aa  jnz     short loc_1800057BD
0x1800057ac  mov     rdx, [rcx+18h]; Buf2
0x1800057b0  mov     rcx, r9; Buf1
0x1800057b3  call    memcmp_0
0x1800057b8  mov     r8d, eax
0x1800057bb  jmp     short loc_1800057C0
0x1800057bd  sub     r8d, eax
0x1800057c0  mov     eax, r8d
0x1800057c3  add     rsp, 28h
0x1800057c7  retn
```
