# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x180011f2c`
- end: `0x180011f58`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012264`
- `0x180013518`
- `0x1800141a4`

## callees

- `0x180011f2c`
- `0x180020bf6`

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
0x180011f2c  sub     rsp, 28h
0x180011f30  movzx   eax, word ptr [rcx+8]
0x180011f34  mov     r9, rdx
0x180011f37  cmp     r8, rax
0x180011f3a  jnz     short loc_180011F4D
0x180011f3c  mov     rdx, [rcx+18h]; Buf2
0x180011f40  mov     rcx, r9; Buf1
0x180011f43  call    memcmp_0
0x180011f48  mov     r8d, eax
0x180011f4b  jmp     short loc_180011F50
0x180011f4d  sub     r8d, eax
0x180011f50  mov     eax, r8d
0x180011f53  add     rsp, 28h
0x180011f57  retn
```
