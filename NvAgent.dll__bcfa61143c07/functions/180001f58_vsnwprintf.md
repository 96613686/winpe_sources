# _vsnwprintf

- ea: `0x180001f58`
- end: `0x180001fa6`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004264`
- `0x180005060`

## callees

- `0x1800011c4`
- `0x180001eba`

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
0x180001f58  push    rbx
0x180001f5a  push    rbp
0x180001f5b  push    rsi
0x180001f5c  push    rdi
0x180001f5d  sub     rsp, 38h
0x180001f61  mov     rbx, r9
0x180001f64  mov     rdi, r8
0x180001f67  mov     rsi, rdx
0x180001f6a  mov     rbp, rcx
0x180001f6d  call    __local_stdio_printf_options
0x180001f72  mov     [rsp+58h+ArgList], rbx; ArgList
0x180001f77  mov     r9, rdi; Format
0x180001f7a  mov     r8, rsi; BufferCount
0x180001f7d  mov     [rsp+58h+Locale], 0; Locale
0x180001f86  mov     rdx, rbp; Buffer
0x180001f89  mov     rcx, [rax]
0x180001f8c  or      rcx, 1; Options
0x180001f90  call    _o___stdio_common_vswprintf_0
0x180001f95  or      ecx, 0FFFFFFFFh
0x180001f98  test    eax, eax
0x180001f9a  cmovs   eax, ecx
0x180001f9d  add     rsp, 38h
0x180001fa1  pop     rdi
0x180001fa2  pop     rsi
0x180001fa3  pop     rbp
0x180001fa4  pop     rbx
0x180001fa5  retn
```
