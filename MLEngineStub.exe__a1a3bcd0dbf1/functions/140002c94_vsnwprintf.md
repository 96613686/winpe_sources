# _vsnwprintf

- ea: `0x140002c94`
- end: `0x140002ce2`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004fe0`
- `0x140005de0`
- `0x14000980c`

## callees

- `0x140001e24`
- `0x140002b52`

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
0x140002c94  push    rbx
0x140002c96  push    rbp
0x140002c97  push    rsi
0x140002c98  push    rdi
0x140002c99  sub     rsp, 38h
0x140002c9d  mov     rbx, r9
0x140002ca0  mov     rdi, r8
0x140002ca3  mov     rsi, rdx
0x140002ca6  mov     rbp, rcx
0x140002ca9  call    __local_stdio_printf_options
0x140002cae  mov     [rsp+58h+ArgList], rbx; ArgList
0x140002cb3  mov     r9, rdi; Format
0x140002cb6  mov     r8, rsi; BufferCount
0x140002cb9  mov     [rsp+58h+Locale], 0; Locale
0x140002cc2  mov     rdx, rbp; Buffer
0x140002cc5  mov     rcx, [rax]
0x140002cc8  or      rcx, 1; Options
0x140002ccc  call    _o___stdio_common_vswprintf_0
0x140002cd1  or      ecx, 0FFFFFFFFh
0x140002cd4  test    eax, eax
0x140002cd6  cmovs   eax, ecx
0x140002cd9  add     rsp, 38h
0x140002cdd  pop     rdi
0x140002cde  pop     rsi
0x140002cdf  pop     rbp
0x140002ce0  pop     rbx
0x140002ce1  retn
```
