# _vsnwprintf

- ea: `0x180001d18`
- end: `0x180001d66`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ec4`
- `0x180005c14`
- `0x1800070ec`

## callees

- `0x180001094`
- `0x180001c7a`

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
0x180001d18  push    rbx
0x180001d1a  push    rbp
0x180001d1b  push    rsi
0x180001d1c  push    rdi
0x180001d1d  sub     rsp, 38h
0x180001d21  mov     rbx, r9
0x180001d24  mov     rdi, r8
0x180001d27  mov     rsi, rdx
0x180001d2a  mov     rbp, rcx
0x180001d2d  call    __local_stdio_printf_options
0x180001d32  mov     [rsp+58h+ArgList], rbx; ArgList
0x180001d37  mov     r9, rdi; Format
0x180001d3a  mov     r8, rsi; BufferCount
0x180001d3d  mov     [rsp+58h+Locale], 0; Locale
0x180001d46  mov     rdx, rbp; Buffer
0x180001d49  mov     rcx, [rax]
0x180001d4c  or      rcx, 1; Options
0x180001d50  call    _o___stdio_common_vswprintf_0
0x180001d55  or      ecx, 0FFFFFFFFh
0x180001d58  test    eax, eax
0x180001d5a  cmovs   eax, ecx
0x180001d5d  add     rsp, 38h
0x180001d61  pop     rdi
0x180001d62  pop     rsi
0x180001d63  pop     rbp
0x180001d64  pop     rbx
0x180001d65  retn
```
