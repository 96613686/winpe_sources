# _snwprintf_s

- ea: `0x18000a010`
- end: `0x18000a06e`
- name: `_snwprintf_s`
- size: `94`
- prototype: `int(wchar_t *const Buffer, const size_t BufferCount, const size_t MaxCount, const wchar_t *const Format, ...)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800070b8`
- `0x1800076b0`
- `0x180016c70`
- `0x1800182d0`
- `0x18001a364`
- `0x18001a3e0`

## callees

- `0x180001760`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x18000a055`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x18000a055`

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
0x18000a010  mov     rax, rsp
0x18000a013  mov     [rax+20h], r9
0x18000a017  push    rbx
0x18000a018  push    rbp
0x18000a019  push    rsi
0x18000a01a  push    rdi
0x18000a01b  push    r14
0x18000a01d  sub     rsp, 40h
0x18000a021  mov     rbp, r9
0x18000a024  lea     r14, [rax+28h]
0x18000a028  mov     rbx, r8
0x18000a02b  mov     rdi, rdx
0x18000a02e  mov     rsi, rcx
0x18000a031  call    __local_stdio_printf_options
0x18000a036  mov     [rsp+68h+ArgList], r14; ArgList
0x18000a03b  mov     r9, rbx; MaxCount
0x18000a03e  mov     [rsp+68h+Locale], 0; Locale
0x18000a047  mov     r8, rdi; BufferCount
0x18000a04a  mov     rdx, rsi; Buffer
0x18000a04d  mov     [rsp+68h+Format], rbp; Format
0x18000a052  mov     rcx, [rax]; Options
0x18000a055  call    cs:__imp___stdio_common_vsnwprintf_s
0x18000a05b  or      ecx, 0FFFFFFFFh
0x18000a05e  test    eax, eax
0x18000a060  cmovs   eax, ecx
0x18000a063  add     rsp, 40h
0x18000a067  pop     r14
0x18000a069  pop     rdi
0x18000a06a  pop     rsi
0x18000a06b  pop     rbp
0x18000a06c  pop     rbx
0x18000a06d  retn
```
