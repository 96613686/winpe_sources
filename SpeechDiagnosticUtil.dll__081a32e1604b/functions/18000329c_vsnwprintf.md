# _vsnwprintf

- ea: `0x18000329c`
- end: `0x1800032ea`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800053b4`
- `0x180005f08`
- `0x1800071fc`

## callees

- `0x180002544`
- `0x1800031c2`

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
0x18000329c  push    rbx
0x18000329e  push    rbp
0x18000329f  push    rsi
0x1800032a0  push    rdi
0x1800032a1  sub     rsp, 38h
0x1800032a5  mov     rbx, r9
0x1800032a8  mov     rdi, r8
0x1800032ab  mov     rsi, rdx
0x1800032ae  mov     rbp, rcx
0x1800032b1  call    __local_stdio_printf_options
0x1800032b6  mov     [rsp+58h+ArgList], rbx; ArgList
0x1800032bb  mov     r9, rdi; Format
0x1800032be  mov     r8, rsi; BufferCount
0x1800032c1  mov     [rsp+58h+Locale], 0; Locale
0x1800032ca  mov     rdx, rbp; Buffer
0x1800032cd  mov     rcx, [rax]
0x1800032d0  or      rcx, 1; Options
0x1800032d4  call    _o___stdio_common_vswprintf_0
0x1800032d9  or      ecx, 0FFFFFFFFh
0x1800032dc  test    eax, eax
0x1800032de  cmovs   eax, ecx
0x1800032e1  add     rsp, 38h
0x1800032e5  pop     rdi
0x1800032e6  pop     rsi
0x1800032e7  pop     rbp
0x1800032e8  pop     rbx
0x1800032e9  retn
```
