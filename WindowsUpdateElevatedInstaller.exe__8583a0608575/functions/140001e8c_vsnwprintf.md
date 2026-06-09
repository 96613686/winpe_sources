# _vsnwprintf

- ea: `0x140001e8c`
- end: `0x140001eda`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400042d8`
- `0x140005284`
- `0x140006194`

## callees

- `0x140001174`
- `0x140001d6a`

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
0x140001e8c  push    rbx
0x140001e8e  push    rbp
0x140001e8f  push    rsi
0x140001e90  push    rdi
0x140001e91  sub     rsp, 38h
0x140001e95  mov     rbx, r9
0x140001e98  mov     rdi, r8
0x140001e9b  mov     rsi, rdx
0x140001e9e  mov     rbp, rcx
0x140001ea1  call    __local_stdio_printf_options
0x140001ea6  mov     [rsp+58h+ArgList], rbx; ArgList
0x140001eab  mov     r9, rdi; Format
0x140001eae  mov     r8, rsi; BufferCount
0x140001eb1  mov     [rsp+58h+Locale], 0; Locale
0x140001eba  mov     rdx, rbp; Buffer
0x140001ebd  mov     rcx, [rax]
0x140001ec0  or      rcx, 1; Options
0x140001ec4  call    _o___stdio_common_vswprintf_0
0x140001ec9  or      ecx, 0FFFFFFFFh
0x140001ecc  test    eax, eax
0x140001ece  cmovs   eax, ecx
0x140001ed1  add     rsp, 38h
0x140001ed5  pop     rdi
0x140001ed6  pop     rsi
0x140001ed7  pop     rbp
0x140001ed8  pop     rbx
0x140001ed9  retn
```
