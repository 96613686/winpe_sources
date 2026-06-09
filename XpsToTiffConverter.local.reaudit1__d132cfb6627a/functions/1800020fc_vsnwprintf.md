# _vsnwprintf

- ea: `0x1800020fc`
- end: `0x18000214a`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800058e4`
- `0x180007bb8`
- `0x18000a384`

## callees

- `0x1800012d4`
- `0x18000201a`

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
0x1800020fc  push    rbx
0x1800020fe  push    rbp
0x1800020ff  push    rsi
0x180002100  push    rdi
0x180002101  sub     rsp, 38h
0x180002105  mov     rbx, r9
0x180002108  mov     rdi, r8
0x18000210b  mov     rsi, rdx
0x18000210e  mov     rbp, rcx
0x180002111  call    __local_stdio_printf_options
0x180002116  mov     [rsp+58h+ArgList], rbx; ArgList
0x18000211b  mov     r9, rdi; Format
0x18000211e  mov     r8, rsi; BufferCount
0x180002121  mov     [rsp+58h+Locale], 0; Locale
0x18000212a  mov     rdx, rbp; Buffer
0x18000212d  mov     rcx, [rax]
0x180002130  or      rcx, 1; Options
0x180002134  call    _o___stdio_common_vswprintf_0
0x180002139  or      ecx, 0FFFFFFFFh
0x18000213c  test    eax, eax
0x18000213e  cmovs   eax, ecx
0x180002141  add     rsp, 38h
0x180002145  pop     rdi
0x180002146  pop     rsi
0x180002147  pop     rbp
0x180002148  pop     rbx
0x180002149  retn
```
