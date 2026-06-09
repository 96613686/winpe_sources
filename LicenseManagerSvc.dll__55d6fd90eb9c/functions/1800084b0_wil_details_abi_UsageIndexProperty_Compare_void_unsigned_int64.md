# wil::details_abi::UsageIndexProperty::Compare(void *,unsigned __int64)

- ea: `0x1800084b0`
- end: `0x1800084dc`
- name: `?Compare@UsageIndexProperty@details_abi@wil@@QEBAHPEAX_K@Z`
- size: `44`
- prototype: `int(wil::details_abi::UsageIndexProperty *__hidden this, void *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008774`
- `0x18000931c`
- `0x180009f68`

## callees

- `0x1800084b0`
- `0x180017450`

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
0x1800084b0  sub     rsp, 28h
0x1800084b4  movzx   eax, word ptr [rcx+8]
0x1800084b8  mov     r9, rdx
0x1800084bb  cmp     r8, rax
0x1800084be  jnz     short loc_1800084D1
0x1800084c0  mov     rdx, [rcx+18h]; Buf2
0x1800084c4  mov     rcx, r9; Buf1
0x1800084c7  call    memcmp_0
0x1800084cc  mov     r8d, eax
0x1800084cf  jmp     short loc_1800084D4
0x1800084d1  sub     r8d, eax
0x1800084d4  mov     eax, r8d
0x1800084d7  add     rsp, 28h
0x1800084db  retn
```
