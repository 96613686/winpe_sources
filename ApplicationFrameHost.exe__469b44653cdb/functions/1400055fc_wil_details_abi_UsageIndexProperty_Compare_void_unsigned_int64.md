# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x1400055fc`
- end: `0x140005628`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005d20`
- `0x140006d48`
- `0x140007a7c`

## callees

- `0x1400055fc`
- `0x14000a404`

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
0x1400055fc  sub     rsp, 28h
0x140005600  movzx   eax, word ptr [rcx+8]
0x140005604  mov     r9, rdx
0x140005607  cmp     r8, rax
0x14000560a  jnz     short loc_14000561D
0x14000560c  mov     rdx, [rcx+18h]; Buf2
0x140005610  mov     rcx, r9; Buf1
0x140005613  call    memcmp_0
0x140005618  mov     r8d, eax
0x14000561b  jmp     short loc_140005620
0x14000561d  sub     r8d, eax
0x140005620  mov     eax, r8d
0x140005623  add     rsp, 28h
0x140005627  retn
```
