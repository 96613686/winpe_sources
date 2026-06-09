# _snwprintf_s

- ea: `0x1832cada0`
- end: `0x1832cae00`
- name: `_snwprintf_s`
- size: `96`
- prototype: `int(wchar_t *const Buffer, const size_t BufferCount, const size_t MaxCount, const wchar_t *const Format, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1832fa3db`
- `0x1832fa445`
- `0x1832fa696`
- `0x1832fa700`
- `0x1832fa82a`
- `0x1832fa894`

## callees

- `0x1815ce4b0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x1832cade7`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x1832cade7`

## pseudocode

```c
int snwprintf_s(
        wchar_t *const Buffer,
        const size_t BufferCount,
        const size_t MaxCount,
        const wchar_t *const Format,
        ...)
{
  unsigned __int64 *v8; // rax
  int result; // eax
  va_list va; // [rsp+90h] [rbp+28h] BYREF

  va_start(va, Format);
  v8 = _local_stdio_printf_options();
  result = __stdio_common_vsnwprintf_s(*v8, Buffer, BufferCount, MaxCount, Format, 0, va);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x1832cada0  mov     [rsp+arg_18], r9
0x1832cada5  push    rbx
0x1832cada6  push    rbp
0x1832cada7  push    rsi
0x1832cada8  push    rdi
0x1832cada9  push    r14
0x1832cadab  sub     rsp, 40h
0x1832cadaf  mov     rbp, r9
0x1832cadb2  lea     r14, [rsp+68h+arg_20]
0x1832cadba  mov     rsi, r8
0x1832cadbd  mov     rdi, rdx
0x1832cadc0  mov     rbx, rcx
0x1832cadc3  call    __local_stdio_printf_options
0x1832cadc8  mov     [rsp+68h+ArgList], r14; ArgList
0x1832cadcd  mov     r9, rsi; MaxCount
0x1832cadd0  mov     [rsp+68h+Locale], 0; Locale
0x1832cadd9  mov     r8, rdi; BufferCount
0x1832caddc  mov     rdx, rbx; Buffer
0x1832caddf  mov     [rsp+68h+Format], rbp; Format
0x1832cade4  mov     rcx, [rax]; Options
0x1832cade7  call    cs:__imp___stdio_common_vsnwprintf_s
0x1832caded  or      ecx, 0FFFFFFFFh
0x1832cadf0  test    eax, eax
0x1832cadf2  cmovs   eax, ecx
0x1832cadf5  add     rsp, 40h
0x1832cadf9  pop     r14
0x1832cadfb  pop     rdi
0x1832cadfc  pop     rsi
0x1832cadfd  pop     rbp
0x1832cadfe  pop     rbx
0x1832cadff  retn
```
