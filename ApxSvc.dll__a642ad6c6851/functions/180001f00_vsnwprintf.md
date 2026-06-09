# _vsnwprintf

- ea: `0x180001f00`
- end: `0x180001f4e`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800044a8`
- `0x1800052b0`

## callees

- `0x180001184`
- `0x180001e4a`

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
0x180001f00  push    rbx
0x180001f02  push    rbp
0x180001f03  push    rsi
0x180001f04  push    rdi
0x180001f05  sub     rsp, 38h
0x180001f09  mov     rbx, r9
0x180001f0c  mov     rdi, r8
0x180001f0f  mov     rsi, rdx
0x180001f12  mov     rbp, rcx
0x180001f15  call    __local_stdio_printf_options
0x180001f1a  mov     [rsp+58h+ArgList], rbx; ArgList
0x180001f1f  mov     r9, rdi; Format
0x180001f22  mov     r8, rsi; BufferCount
0x180001f25  mov     [rsp+58h+Locale], 0; Locale
0x180001f2e  mov     rdx, rbp; Buffer
0x180001f31  mov     rcx, [rax]
0x180001f34  or      rcx, 1; Options
0x180001f38  call    _o___stdio_common_vswprintf_0
0x180001f3d  or      ecx, 0FFFFFFFFh
0x180001f40  test    eax, eax
0x180001f42  cmovs   eax, ecx
0x180001f45  add     rsp, 38h
0x180001f49  pop     rdi
0x180001f4a  pop     rsi
0x180001f4b  pop     rbp
0x180001f4c  pop     rbx
0x180001f4d  retn
```
