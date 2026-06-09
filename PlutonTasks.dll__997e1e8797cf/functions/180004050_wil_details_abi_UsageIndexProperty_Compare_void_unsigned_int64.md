# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180004050`
- end: `0x18000407c`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800049bc`
- `0x180005c8c`
- `0x180006b74`

## callees

- `0x180004050`
- `0x180009734`

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
0x180004050  sub     rsp, 28h
0x180004054  movzx   eax, word ptr [rcx+8]
0x180004058  mov     r9, rdx
0x18000405b  cmp     r8, rax
0x18000405e  jnz     short loc_180004071
0x180004060  mov     rdx, [rcx+18h]; Buf2
0x180004064  mov     rcx, r9; Buf1
0x180004067  call    memcmp_0
0x18000406c  mov     r8d, eax
0x18000406f  jmp     short loc_180004074
0x180004071  sub     r8d, eax
0x180004074  mov     eax, r8d
0x180004077  add     rsp, 28h
0x18000407b  retn
```
