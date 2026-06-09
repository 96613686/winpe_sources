# _vsnwprintf

- ea: `0x140001f74`
- end: `0x140001fc2`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140005ce8`
- `0x140006f24`

## callees

- `0x140001164`
- `0x140001e2e`

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
0x140001f74  push    rbx
0x140001f76  push    rbp
0x140001f77  push    rsi
0x140001f78  push    rdi
0x140001f79  sub     rsp, 38h
0x140001f7d  mov     rbx, r9
0x140001f80  mov     rdi, r8
0x140001f83  mov     rsi, rdx
0x140001f86  mov     rbp, rcx
0x140001f89  call    __local_stdio_printf_options
0x140001f8e  mov     [rsp+58h+ArgList], rbx; ArgList
0x140001f93  mov     r9, rdi; Format
0x140001f96  mov     r8, rsi; BufferCount
0x140001f99  mov     [rsp+58h+Locale], 0; Locale
0x140001fa2  mov     rdx, rbp; Buffer
0x140001fa5  mov     rcx, [rax]
0x140001fa8  or      rcx, 1; Options
0x140001fac  call    _o___stdio_common_vswprintf_0
0x140001fb1  or      ecx, 0FFFFFFFFh
0x140001fb4  test    eax, eax
0x140001fb6  cmovs   eax, ecx
0x140001fb9  add     rsp, 38h
0x140001fbd  pop     rdi
0x140001fbe  pop     rsi
0x140001fbf  pop     rbp
0x140001fc0  pop     rbx
0x140001fc1  retn
```
