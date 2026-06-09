# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x140004ecc`
- end: `0x140004ef8`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005358`
- `0x140006684`
- `0x1400074f4`

## callees

- `0x140004ecc`
- `0x14001ed86`

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
0x140004ecc  sub     rsp, 28h
0x140004ed0  movzx   eax, word ptr [rcx+8]
0x140004ed4  mov     r9, rdx
0x140004ed7  cmp     r8, rax
0x140004eda  jnz     short loc_140004EED
0x140004edc  mov     rdx, [rcx+18h]; Buf2
0x140004ee0  mov     rcx, r9; Buf1
0x140004ee3  call    memcmp_0
0x140004ee8  mov     r8d, eax
0x140004eeb  jmp     short loc_140004EF0
0x140004eed  sub     r8d, eax
0x140004ef0  mov     eax, r8d
0x140004ef3  add     rsp, 28h
0x140004ef7  retn
```
