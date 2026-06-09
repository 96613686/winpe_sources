# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180005160`
- end: `0x18000518c`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005558`
- `0x1800068c8`
- `0x180007838`

## callees

- `0x1800036ec`
- `0x180005160`

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
0x180005160  sub     rsp, 28h
0x180005164  movzx   eax, word ptr [rcx+8]
0x180005168  mov     r9, rdx
0x18000516b  cmp     r8, rax
0x18000516e  jnz     short loc_180005181
0x180005170  mov     rdx, [rcx+18h]; Buf2
0x180005174  mov     rcx, r9; Buf1
0x180005177  call    memcmp_0
0x18000517c  mov     r8d, eax
0x18000517f  jmp     short loc_180005184
0x180005181  sub     r8d, eax
0x180005184  mov     eax, r8d
0x180005187  add     rsp, 28h
0x18000518b  retn
```
