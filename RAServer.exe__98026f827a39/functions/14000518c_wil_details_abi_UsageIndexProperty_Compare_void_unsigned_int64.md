# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x14000518c`
- end: `0x1400051b8`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005fd8`
- `0x140007cc8`
- `0x140008f40`

## callees

- `0x14000518c`
- `0x140015a56`

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
0x14000518c  sub     rsp, 28h
0x140005190  movzx   eax, word ptr [rcx+8]
0x140005194  mov     r9, rdx
0x140005197  cmp     r8, rax
0x14000519a  jnz     short loc_1400051AD
0x14000519c  mov     rdx, [rcx+18h]; Buf2
0x1400051a0  mov     rcx, r9; Buf1
0x1400051a3  call    memcmp_0
0x1400051a8  mov     r8d, eax
0x1400051ab  jmp     short loc_1400051B0
0x1400051ad  sub     r8d, eax
0x1400051b0  mov     eax, r8d
0x1400051b3  add     rsp, 28h
0x1400051b7  retn
```
