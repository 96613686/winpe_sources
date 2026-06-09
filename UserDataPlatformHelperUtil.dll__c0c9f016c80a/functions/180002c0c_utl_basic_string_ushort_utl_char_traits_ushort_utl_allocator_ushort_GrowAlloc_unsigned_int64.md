# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowAlloc(unsigned __int64)

- ea: `0x180002c0c`
- end: `0x180002ca7`
- name: `?_GrowAlloc@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA?AU?$pair@PEAG_K@2@_K@Z`
- size: `155`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002cb0`
- `0x18000504c`

## callees

- `0x1800016e8`
- `0x180002c0c`

## pseudocode

```c
_QWORD *__fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowAlloc(
        _QWORD *a1,
        _QWORD *a2,
        unsigned __int64 a3)
{
  __int64 v4; // rax
  unsigned __int64 v5; // rdi
  unsigned __int64 v6; // rdi
  void *v7; // rax

  if ( (_QWORD *)*a1 == a1 + 2 )
    v4 = 7;
  else
    v4 = (__int64)(a1[2] - *a1) >> 1;
  v5 = 2 * v4 + 1;
  if ( v5 < a3 )
    v5 = a3;
  if ( v5 <= 0x3FFFFFFFFFFFFFF7LL )
  {
    v6 = v5 + 1;
    if ( v6 > 0x7FFFFFFFFFFFFFFFLL )
    {
      v7 = 0;
      goto LABEL_13;
    }
LABEL_11:
    v7 = operator new(2 * v6, (const struct std::nothrow_t *)&std::nothrow);
LABEL_13:
    *a2 = v7;
    a2[1] = v6;
    return a2;
  }
  if ( a3 <= 0x3FFFFFFFFFFFFFF7LL )
  {
    v6 = 0x3FFFFFFFFFFFFFF8LL;
    goto LABEL_11;
  }
  *a2 = 0;
  a2[1] = 0;
  return a2;
}

```

## disassembly

```asm
0x180002c0c  mov     [rsp+arg_0], rbx
0x180002c11  push    rdi
0x180002c12  sub     rsp, 20h
0x180002c16  lea     rax, [rcx+10h]
0x180002c1a  mov     rbx, rdx
0x180002c1d  cmp     [rcx], rax
0x180002c20  jnz     short loc_180002C29
0x180002c22  mov     eax, 7
0x180002c27  jmp     short loc_180002C32
0x180002c29  mov     rax, [rax]
0x180002c2c  sub     rax, [rcx]
0x180002c2f  sar     rax, 1
0x180002c32  lea     rdi, ds:1[rax*2]
0x180002c3a  mov     rax, 3FFFFFFFFFFFFFF7h
0x180002c44  cmp     rdi, r8
0x180002c47  cmovb   rdi, r8
0x180002c4b  cmp     rdi, rax
0x180002c4e  jbe     short loc_180002C6C
0x180002c50  cmp     r8, rax
0x180002c53  jbe     short loc_180002C60
0x180002c55  xor     eax, eax
0x180002c57  mov     [rdx], rax
0x180002c5a  mov     [rdx+8], rax
0x180002c5e  jmp     short loc_180002C99
0x180002c60  mov     rdi, 3FFFFFFFFFFFFFF8h
0x180002c6a  jmp     short loc_180002C7E
0x180002c6c  inc     rdi
0x180002c6f  mov     rax, 7FFFFFFFFFFFFFFFh
0x180002c79  cmp     rdi, rax
0x180002c7c  ja      short loc_180002C90
0x180002c7e  lea     rcx, [rdi+rdi]; unsigned __int64
0x180002c82  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002c89  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002c8e  jmp     short loc_180002C92
0x180002c90  xor     eax, eax
0x180002c92  mov     [rbx], rax
0x180002c95  mov     [rbx+8], rdi
0x180002c99  mov     rax, rbx
0x180002c9c  mov     rbx, [rsp+28h+arg_0]
0x180002ca1  add     rsp, 20h
0x180002ca5  pop     rdi
0x180002ca6  retn
```
