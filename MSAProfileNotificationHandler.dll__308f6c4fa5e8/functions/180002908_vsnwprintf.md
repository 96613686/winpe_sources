# _vsnwprintf

- ea: `0x180002908`
- end: `0x180002956`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000555c`
- `0x180006120`
- `0x18000789c`

## callees

- `0x1800018e4`
- `0x180002830`

## pseudocode

```c
int __cdecl vsnwprintf(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)
{
  unsigned __int64 *v8; // rax
  int result; // eax

  v8 = _local_stdio_printf_options();
  result = o___stdio_common_vswprintf_0(*v8 | 1, Buffer, BufferCount, Format, 0, Args);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x180002908  push    rbx
0x18000290a  push    rbp
0x18000290b  push    rsi
0x18000290c  push    rdi
0x18000290d  sub     rsp, 38h
0x180002911  mov     rbx, r9
0x180002914  mov     rdi, r8
0x180002917  mov     rsi, rdx
0x18000291a  mov     rbp, rcx
0x18000291d  call    __local_stdio_printf_options
0x180002922  mov     [rsp+58h+ArgList], rbx; ArgList
0x180002927  mov     r9, rdi; Format
0x18000292a  mov     r8, rsi; BufferCount
0x18000292d  mov     [rsp+58h+Locale], 0; Locale
0x180002936  mov     rdx, rbp; Buffer
0x180002939  mov     rcx, [rax]
0x18000293c  or      rcx, 1; Options
0x180002940  call    _o___stdio_common_vswprintf_0
0x180002945  or      ecx, 0FFFFFFFFh
0x180002948  test    eax, eax
0x18000294a  cmovs   eax, ecx
0x18000294d  add     rsp, 38h
0x180002951  pop     rdi
0x180002952  pop     rsi
0x180002953  pop     rbp
0x180002954  pop     rbx
0x180002955  retn
```
