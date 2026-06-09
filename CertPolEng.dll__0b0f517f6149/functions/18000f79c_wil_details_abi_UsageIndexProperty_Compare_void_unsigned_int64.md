# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000f79c`
- end: `0x18000f7c8`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000fa84`
- `0x1800106c0`
- `0x180010f1c`

## callees

- `0x18000f79c`
- `0x18001a336`

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
0x18000f79c  sub     rsp, 28h
0x18000f7a0  movzx   eax, word ptr [rcx+8]
0x18000f7a4  mov     r9, rdx
0x18000f7a7  cmp     r8, rax
0x18000f7aa  jnz     short loc_18000F7BD
0x18000f7ac  mov     rdx, [rcx+18h]; Buf2
0x18000f7b0  mov     rcx, r9; Buf1
0x18000f7b3  call    memcmp_0
0x18000f7b8  mov     r8d, eax
0x18000f7bb  jmp     short loc_18000F7C0
0x18000f7bd  sub     r8d, eax
0x18000f7c0  mov     eax, r8d
0x18000f7c3  add     rsp, 28h
0x18000f7c7  retn
```
