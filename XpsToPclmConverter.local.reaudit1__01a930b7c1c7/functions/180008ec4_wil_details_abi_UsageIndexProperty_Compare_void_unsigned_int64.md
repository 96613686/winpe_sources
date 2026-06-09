# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180008ec4`
- end: `0x180008ef0`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800091f4`
- `0x18000a488`
- `0x18000b1a4`

## callees

- `0x180007745`
- `0x180008ec4`

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
0x180008ec4  sub     rsp, 28h
0x180008ec8  movzx   eax, word ptr [rcx+8]
0x180008ecc  mov     r9, rdx
0x180008ecf  cmp     r8, rax
0x180008ed2  jnz     short loc_180008EE5
0x180008ed4  mov     rdx, [rcx+18h]; Buf2
0x180008ed8  mov     rcx, r9; Buf1
0x180008edb  call    memcmp_0
0x180008ee0  mov     r8d, eax
0x180008ee3  jmp     short loc_180008EE8
0x180008ee5  sub     r8d, eax
0x180008ee8  mov     eax, r8d
0x180008eeb  add     rsp, 28h
0x180008eef  retn
```
