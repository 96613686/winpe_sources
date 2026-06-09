# _vsnwprintf

- ea: `0x1800026cc`
- end: `0x18000271a`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007970`
- `0x1800079fc`
- `0x18000d95c`
- `0x180013780`

## callees

- `0x1800016f4`
- `0x1800025f2`

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
0x1800026cc  push    rbx
0x1800026ce  push    rbp
0x1800026cf  push    rsi
0x1800026d0  push    rdi
0x1800026d1  sub     rsp, 38h
0x1800026d5  mov     rbx, r9
0x1800026d8  mov     rdi, r8
0x1800026db  mov     rsi, rdx
0x1800026de  mov     rbp, rcx
0x1800026e1  call    __local_stdio_printf_options
0x1800026e6  mov     [rsp+58h+ArgList], rbx; ArgList
0x1800026eb  mov     r9, rdi; Format
0x1800026ee  mov     r8, rsi; BufferCount
0x1800026f1  mov     [rsp+58h+Locale], 0; Locale
0x1800026fa  mov     rdx, rbp; Buffer
0x1800026fd  mov     rcx, [rax]
0x180002700  or      rcx, 1; Options
0x180002704  call    _o___stdio_common_vswprintf_0
0x180002709  or      ecx, 0FFFFFFFFh
0x18000270c  test    eax, eax
0x18000270e  cmovs   eax, ecx
0x180002711  add     rsp, 38h
0x180002715  pop     rdi
0x180002716  pop     rsi
0x180002717  pop     rbp
0x180002718  pop     rbx
0x180002719  retn
```
