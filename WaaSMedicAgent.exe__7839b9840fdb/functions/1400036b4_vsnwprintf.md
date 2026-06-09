# _vsnwprintf

- ea: `0x1400036b4`
- end: `0x140003702`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000603c`
- `0x140006e60`
- `0x1400087ac`
- `0x14000b470`

## callees

- `0x140002724`
- `0x140003566`

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
0x1400036b4  push    rbx
0x1400036b6  push    rbp
0x1400036b7  push    rsi
0x1400036b8  push    rdi
0x1400036b9  sub     rsp, 38h
0x1400036bd  mov     rbx, r9
0x1400036c0  mov     rdi, r8
0x1400036c3  mov     rsi, rdx
0x1400036c6  mov     rbp, rcx
0x1400036c9  call    __local_stdio_printf_options
0x1400036ce  mov     [rsp+58h+ArgList], rbx; ArgList
0x1400036d3  mov     r9, rdi; Format
0x1400036d6  mov     r8, rsi; BufferCount
0x1400036d9  mov     [rsp+58h+Locale], 0; Locale
0x1400036e2  mov     rdx, rbp; Buffer
0x1400036e5  mov     rcx, [rax]
0x1400036e8  or      rcx, 1; Options
0x1400036ec  call    _o___stdio_common_vswprintf_0
0x1400036f1  or      ecx, 0FFFFFFFFh
0x1400036f4  test    eax, eax
0x1400036f6  cmovs   eax, ecx
0x1400036f9  add     rsp, 38h
0x1400036fd  pop     rdi
0x1400036fe  pop     rsi
0x1400036ff  pop     rbp
0x140003700  pop     rbx
0x140003701  retn
```
