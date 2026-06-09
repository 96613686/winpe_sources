# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000de50`
- end: `0x18000de71`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `33`
- prototype: `int __fastcall(const void **this, void *, size_t)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800072c0`

## callees

- `0x18000de50`
- `0x18001ae76`

## pseudocode

```c
int __fastcall wil::details_abi::UsageIndexProperty::Compare(const void **this, void *a2, size_t a3)
{
  __int64 v3; // rax

  v3 = *((unsigned __int16 *)this + 4);
  if ( a3 == v3 )
    return memcmp_0(a2, this[3], a3);
  else
    return a3 - v3;
}

```

## disassembly

```asm
0x18000de50  movzx   eax, word ptr [rcx+8]
0x18000de54  mov     r9, rdx
0x18000de57  cmp     r8, rax
0x18000de5a  jnz     short loc_18000DE69
0x18000de5c  mov     rdx, [rcx+18h]; Buf2
0x18000de60  mov     rcx, r9; Buf1
0x18000de63  jmp     memcmp_0
0x18000de68  retn
0x18000de69  sub     r8d, eax
0x18000de6c  mov     eax, r8d
0x18000de6f  jmp     short locret_18000DE68
```
