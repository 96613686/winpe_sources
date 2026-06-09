# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x18000bae4`
- end: `0x18000bb10`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `__int64 __fastcall(const void **this, void *, size_t)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ab8`
- `0x18000bc48`
- `0x18000bf58`

## callees

- `0x18000bae4`
- `0x180013640`

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
0x18000bae4  sub     rsp, 28h
0x18000bae8  movzx   eax, word ptr [rcx+8]
0x18000baec  mov     r9, rdx
0x18000baef  cmp     r8, rax
0x18000baf2  jnz     short loc_18000BB05
0x18000baf4  mov     rdx, [rcx+18h]; Buf2
0x18000baf8  mov     rcx, r9; Buf1
0x18000bafb  call    memcmp_0
0x18000bb00  mov     r8d, eax
0x18000bb03  jmp     short loc_18000BB08
0x18000bb05  sub     r8d, eax
0x18000bb08  mov     eax, r8d
0x18000bb0b  add     rsp, 28h
0x18000bb0f  retn
```
