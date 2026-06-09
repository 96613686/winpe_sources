# wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)

- ea: `0x140003a40`
- end: `0x140003ab7`
- name: `?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ`
- size: `119`
- prototype: `unsigned __int16 *(wil::details *__hidden this, unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002de4`

## callees

- `0x140003a40`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140003a79`
- `msvcrt!_vsnwprintf` at `0x140003a79`

## pseudocode

```c
unsigned __int16 *wil::details::LogStringPrintf(
        wil::details *this,
        char *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        ...)
{
  unsigned __int64 v4; // rdi
  unsigned __int16 *v6; // rbx
  size_t v7; // rdi
  int v8; // eax
  __int64 v9; // rax
  const unsigned __int16 *Args; // [rsp+78h] [rbp+20h] BYREF

  Args = a4;
  v4 = (a2 - (char *)this) >> 1;
  v6 = (unsigned __int16 *)this;
  if ( v4 )
  {
    if ( v4 > 0x7FFFFFFF )
    {
      *(_WORD *)this = 0;
    }
    else
    {
      v7 = v4 - 1;
      v8 = _vsnwprintf((wchar_t *)this, v7, a3, (va_list)&Args);
      if ( v8 < 0 || v8 >= v7 )
        v6[v7] = 0;
    }
  }
  if ( a2 != (char *)v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v6[v9] );
    v6 += v9;
  }
  return v6;
}

```

## disassembly

```asm
0x140003a40  mov     [rsp+arg_10], r8
0x140003a45  mov     [rsp+Args], r9
0x140003a4a  push    rbx
0x140003a4b  push    rbp
0x140003a4c  push    rsi
0x140003a4d  push    rdi
0x140003a4e  sub     rsp, 38h
0x140003a52  mov     rdi, rdx
0x140003a55  lea     r9, [rsp+58h+Args]; Args
0x140003a5a  sub     rdi, rcx
0x140003a5d  xor     ebp, ebp
0x140003a5f  sar     rdi, 1
0x140003a62  mov     rsi, rdx
0x140003a65  mov     rbx, rcx
0x140003a68  jz      short loc_140003A95
0x140003a6a  cmp     rdi, 7FFFFFFFh
0x140003a71  ja      short loc_140003A92
0x140003a73  dec     rdi
0x140003a76  mov     rdx, rdi; BufferCount
0x140003a79  call    cs:__imp__vsnwprintf
0x140003a7f  test    eax, eax
0x140003a81  js      short loc_140003A8C
0x140003a83  cdqe
0x140003a85  cmp     rax, rdi
0x140003a88  ja      short loc_140003A8C
0x140003a8a  jnz     short loc_140003A95
0x140003a8c  mov     [rbx+rdi*2], bp
0x140003a90  jmp     short loc_140003A95
0x140003a92  mov     [rcx], bp
0x140003a95  cmp     rsi, rbx
0x140003a98  jz      short loc_140003AAB
0x140003a9a  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003a9e  inc     rax
0x140003aa1  cmp     [rbx+rax*2], bp
0x140003aa5  jnz     short loc_140003A9E
0x140003aa7  lea     rbx, [rbx+rax*2]
0x140003aab  mov     rax, rbx
0x140003aae  add     rsp, 38h
0x140003ab2  pop     rdi
0x140003ab3  pop     rsi
0x140003ab4  pop     rbp
0x140003ab5  pop     rbx
0x140003ab6  retn
```
