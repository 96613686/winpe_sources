# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x1400092a4`
- end: `0x1400092d0`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400095ac`
- `0x14000ae50`
- `0x14000b978`

## callees

- `0x1400092a4`
- `0x140038cc6`

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
0x1400092a4  sub     rsp, 28h
0x1400092a8  movzx   eax, word ptr [rcx+8]
0x1400092ac  mov     r9, rdx
0x1400092af  cmp     r8, rax
0x1400092b2  jnz     short loc_1400092C5
0x1400092b4  mov     rdx, [rcx+18h]; Buf2
0x1400092b8  mov     rcx, r9; Buf1
0x1400092bb  call    memcmp_0
0x1400092c0  mov     r8d, eax
0x1400092c3  jmp     short loc_1400092C8
0x1400092c5  sub     r8d, eax
0x1400092c8  mov     eax, r8d
0x1400092cb  add     rsp, 28h
0x1400092cf  retn
```
