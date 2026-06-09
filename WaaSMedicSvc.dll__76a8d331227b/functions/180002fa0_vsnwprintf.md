# _vsnwprintf

- ea: `0x180002fa0`
- end: `0x180002fee`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005380`
- `0x180006310`
- `0x18000a36c`

## callees

- `0x180001e34`
- `0x180002eca`

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
0x180002fa0  push    rbx
0x180002fa2  push    rbp
0x180002fa3  push    rsi
0x180002fa4  push    rdi
0x180002fa5  sub     rsp, 38h
0x180002fa9  mov     rbx, r9
0x180002fac  mov     rdi, r8
0x180002faf  mov     rsi, rdx
0x180002fb2  mov     rbp, rcx
0x180002fb5  call    __local_stdio_printf_options
0x180002fba  mov     [rsp+58h+ArgList], rbx; ArgList
0x180002fbf  mov     r9, rdi; Format
0x180002fc2  mov     r8, rsi; BufferCount
0x180002fc5  mov     [rsp+58h+Locale], 0; Locale
0x180002fce  mov     rdx, rbp; Buffer
0x180002fd1  mov     rcx, [rax]
0x180002fd4  or      rcx, 1; Options
0x180002fd8  call    _o___stdio_common_vswprintf_0
0x180002fdd  or      ecx, 0FFFFFFFFh
0x180002fe0  test    eax, eax
0x180002fe2  cmovs   eax, ecx
0x180002fe5  add     rsp, 38h
0x180002fe9  pop     rdi
0x180002fea  pop     rsi
0x180002feb  pop     rbp
0x180002fec  pop     rbx
0x180002fed  retn
```
