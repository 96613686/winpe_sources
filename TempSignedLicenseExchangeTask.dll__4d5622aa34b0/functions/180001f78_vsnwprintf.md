# _vsnwprintf

- ea: `0x180001f78`
- end: `0x180001fc6`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002008`
- `0x18000230c`

## callees

- `0x180001034`
- `0x180001eda`

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
0x180001f78  push    rbx
0x180001f7a  push    rbp
0x180001f7b  push    rsi
0x180001f7c  push    rdi
0x180001f7d  sub     rsp, 38h
0x180001f81  mov     rbx, r9
0x180001f84  mov     rdi, r8
0x180001f87  mov     rsi, rdx
0x180001f8a  mov     rbp, rcx
0x180001f8d  call    __local_stdio_printf_options
0x180001f92  mov     [rsp+58h+ArgList], rbx; ArgList
0x180001f97  mov     r9, rdi; Format
0x180001f9a  mov     r8, rsi; BufferCount
0x180001f9d  mov     [rsp+58h+Locale], 0; Locale
0x180001fa6  mov     rdx, rbp; Buffer
0x180001fa9  mov     rcx, [rax]
0x180001fac  or      rcx, 1; Options
0x180001fb0  call    _o___stdio_common_vswprintf_0
0x180001fb5  or      ecx, 0FFFFFFFFh
0x180001fb8  test    eax, eax
0x180001fba  cmovs   eax, ecx
0x180001fbd  add     rsp, 38h
0x180001fc1  pop     rdi
0x180001fc2  pop     rsi
0x180001fc3  pop     rbp
0x180001fc4  pop     rbx
0x180001fc5  retn
```
