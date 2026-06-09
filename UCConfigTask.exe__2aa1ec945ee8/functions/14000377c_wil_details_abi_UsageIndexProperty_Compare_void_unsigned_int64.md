# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x14000377c`
- end: `0x1400037a8`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003ac4`
- `0x140004d74`
- `0x1400059f4`

## callees

- `0x14000377c`
- `0x1400087a4`

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
0x14000377c  sub     rsp, 28h
0x140003780  movzx   eax, word ptr [rcx+8]
0x140003784  mov     r9, rdx
0x140003787  cmp     r8, rax
0x14000378a  jnz     short loc_14000379D
0x14000378c  mov     rdx, [rcx+18h]; Buf2
0x140003790  mov     rcx, r9; Buf1
0x140003793  call    memcmp_0
0x140003798  mov     r8d, eax
0x14000379b  jmp     short loc_1400037A0
0x14000379d  sub     r8d, eax
0x1400037a0  mov     eax, r8d
0x1400037a3  add     rsp, 28h
0x1400037a7  retn
```
