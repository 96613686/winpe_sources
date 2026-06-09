# swprintf_s

- ea: `0x180001fdc`
- end: `0x180002039`
- name: `swprintf_s`
- size: `93`
- prototype: `int(wchar_t *const Buffer, const size_t BufferCount, const wchar_t *const Format, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002bf0`
- `0x1800035a0`
- `0x1800038c0`
- `0x180005934`
- `0x180006908`
- `0x18000f47c`

## callees

- `0x180001264`
- `0x180001eb6`

## pseudocode

```c
int swprintf_s(wchar_t *const Buffer, const size_t BufferCount, const wchar_t *const Format, ...)
{
  unsigned __int64 *v6; // rax
  int result; // eax
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, Format);
  v6 = _local_stdio_printf_options();
  result = _stdio_common_vswprintf_s(*v6, Buffer, BufferCount, Format, 0, va);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x180001fdc  mov     rax, rsp
0x180001fdf  mov     [rax+18h], r8
0x180001fe3  mov     [rax+20h], r9
0x180001fe7  push    rbx
0x180001fe8  push    rbp
0x180001fe9  push    rsi
0x180001fea  push    rdi
0x180001feb  sub     rsp, 48h
0x180001fef  mov     rsi, r8
0x180001ff2  mov     qword ptr [rax-38h], 0
0x180001ffa  mov     rbx, rdx
0x180001ffd  lea     rbp, [rax+20h]
0x180002001  mov     rdi, rcx
0x180002004  call    __local_stdio_printf_options
0x180002009  mov     [rsp+68h+ArgList], rbp; ArgList
0x18000200e  mov     r9, rsi; Format
0x180002011  mov     r8, rbx; BufferCount
0x180002014  mov     [rsp+68h+Locale], 0; Locale
0x18000201d  mov     rdx, rdi; Buffer
0x180002020  mov     rcx, [rax]; Options
0x180002023  call    __stdio_common_vswprintf_s
0x180002028  or      ecx, 0FFFFFFFFh
0x18000202b  test    eax, eax
0x18000202d  cmovs   eax, ecx
0x180002030  add     rsp, 48h
0x180002034  pop     rdi
0x180002035  pop     rsi
0x180002036  pop     rbp
0x180002037  pop     rbx
0x180002038  retn
```
