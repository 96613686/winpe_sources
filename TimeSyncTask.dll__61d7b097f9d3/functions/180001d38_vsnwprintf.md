# _vsnwprintf

- ea: `0x180001d38`
- end: `0x180001d86`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001fd4`

## callees

- `0x180001094`
- `0x180001ca6`

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
0x180001d38  push    rbx
0x180001d3a  push    rbp
0x180001d3b  push    rsi
0x180001d3c  push    rdi
0x180001d3d  sub     rsp, 38h
0x180001d41  mov     rbx, r9
0x180001d44  mov     rdi, r8
0x180001d47  mov     rsi, rdx
0x180001d4a  mov     rbp, rcx
0x180001d4d  call    __local_stdio_printf_options
0x180001d52  mov     [rsp+58h+ArgList], rbx; ArgList
0x180001d57  mov     r9, rdi; Format
0x180001d5a  mov     r8, rsi; BufferCount
0x180001d5d  mov     [rsp+58h+Locale], 0; Locale
0x180001d66  mov     rdx, rbp; Buffer
0x180001d69  mov     rcx, [rax]
0x180001d6c  or      rcx, 1; Options
0x180001d70  call    _o___stdio_common_vswprintf_0
0x180001d75  or      ecx, 0FFFFFFFFh
0x180001d78  test    eax, eax
0x180001d7a  cmovs   eax, ecx
0x180001d7d  add     rsp, 38h
0x180001d81  pop     rdi
0x180001d82  pop     rsi
0x180001d83  pop     rbp
0x180001d84  pop     rbx
0x180001d85  retn
```
