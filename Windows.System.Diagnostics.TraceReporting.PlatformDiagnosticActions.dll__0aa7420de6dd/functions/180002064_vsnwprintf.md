# _vsnwprintf

- ea: `0x180002064`
- end: `0x1800020b2`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800045b8`
- `0x180005550`

## callees

- `0x1800012d4`
- `0x180001f9a`

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
0x180002064  push    rbx
0x180002066  push    rbp
0x180002067  push    rsi
0x180002068  push    rdi
0x180002069  sub     rsp, 38h
0x18000206d  mov     rbx, r9
0x180002070  mov     rdi, r8
0x180002073  mov     rsi, rdx
0x180002076  mov     rbp, rcx
0x180002079  call    __local_stdio_printf_options
0x18000207e  mov     [rsp+58h+ArgList], rbx; ArgList
0x180002083  mov     r9, rdi; Format
0x180002086  mov     r8, rsi; BufferCount
0x180002089  mov     [rsp+58h+Locale], 0; Locale
0x180002092  mov     rdx, rbp; Buffer
0x180002095  mov     rcx, [rax]
0x180002098  or      rcx, 1; Options
0x18000209c  call    _o___stdio_common_vswprintf_0
0x1800020a1  or      ecx, 0FFFFFFFFh
0x1800020a4  test    eax, eax
0x1800020a6  cmovs   eax, ecx
0x1800020a9  add     rsp, 38h
0x1800020ad  pop     rdi
0x1800020ae  pop     rsi
0x1800020af  pop     rbp
0x1800020b0  pop     rbx
0x1800020b1  retn
```
