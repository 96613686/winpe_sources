# _snwprintf_s

- ea: `0x1800032a0`
- end: `0x180003300`
- name: `_snwprintf_s`
- size: `96`
- prototype: `int(wchar_t *const Buffer, const size_t BufferCount, const size_t MaxCount, const wchar_t *const Format, ...)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004ca2`
- `0x180004d0c`

## callees

- `0x180003300`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x1800032e7`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x1800032e7`

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
0x1800032a0  mov     [rsp+arg_18], r9
0x1800032a5  push    rbx
0x1800032a6  push    rbp
0x1800032a7  push    rsi
0x1800032a8  push    rdi
0x1800032a9  push    r14
0x1800032ab  sub     rsp, 40h
0x1800032af  mov     rbp, r9
0x1800032b2  lea     r14, [rsp+68h+arg_20]
0x1800032ba  mov     rbx, r8
0x1800032bd  mov     rdi, rdx
0x1800032c0  mov     rsi, rcx
0x1800032c3  call    __local_stdio_printf_options
0x1800032c8  mov     [rsp+68h+ArgList], r14; ArgList
0x1800032cd  mov     r9, rbx; MaxCount
0x1800032d0  mov     [rsp+68h+Locale], 0; Locale
0x1800032d9  mov     r8, rdi; BufferCount
0x1800032dc  mov     rdx, rsi; Buffer
0x1800032df  mov     [rsp+68h+Format], rbp; Format
0x1800032e4  mov     rcx, [rax]; Options
0x1800032e7  call    cs:__imp___stdio_common_vsnwprintf_s
0x1800032ed  or      ecx, 0FFFFFFFFh
0x1800032f0  test    eax, eax
0x1800032f2  cmovs   eax, ecx
0x1800032f5  add     rsp, 40h
0x1800032f9  pop     r14
0x1800032fb  pop     rdi
0x1800032fc  pop     rsi
0x1800032fd  pop     rbp
0x1800032fe  pop     rbx
0x1800032ff  retn
```
