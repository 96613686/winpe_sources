# swscanf_s

- ea: `0x18002ace0`
- end: `0x18002ad36`
- name: `swscanf_s`
- size: `86`
- prototype: `int(const wchar_t *const Buffer, const wchar_t *const Format, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x18002acd0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswscanf` at `0x18002ad28`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswscanf` at `0x18002ad28`

## pseudocode

```c
int swscanf_s(const wchar_t *const Buffer, const wchar_t *const Format, ...)
{
  unsigned __int64 *v4; // rax
  va_list va; // [rsp+60h] [rbp+18h] BYREF

  va_start(va, Format);
  v4 = _local_stdio_scanf_options();
  return __stdio_common_vswscanf(*v4 | 1, Buffer, 0xFFFFFFFFFFFFFFFFuLL, Format, 0, va);
}

```

## disassembly

```asm
0x18002ace0  mov     [rsp+arg_8], rdx
0x18002ace5  mov     qword ptr [rsp+arg_10], r8
0x18002acea  mov     [rsp+arg_18], r9
0x18002acef  push    rbx
0x18002acf0  push    rsi
0x18002acf1  push    rdi
0x18002acf2  sub     rsp, 30h
0x18002acf6  mov     rdi, rdx
0x18002acf9  lea     rsi, [rsp+48h+arg_10]
0x18002acfe  mov     rbx, rcx
0x18002ad01  call    __local_stdio_scanf_options
0x18002ad06  mov     [rsp+48h+ArgList], rsi; ArgList
0x18002ad0b  mov     r9, rdi; Format
0x18002ad0e  mov     r8, 0FFFFFFFFFFFFFFFFh; BufferCount
0x18002ad15  mov     [rsp+48h+Locale], 0; Locale
0x18002ad1e  mov     rdx, rbx; Buffer
0x18002ad21  mov     rcx, [rax]
0x18002ad24  or      rcx, 1; Options
0x18002ad28  call    cs:__imp___stdio_common_vswscanf
0x18002ad2e  add     rsp, 30h
0x18002ad32  pop     rdi
0x18002ad33  pop     rsi
0x18002ad34  pop     rbx
0x18002ad35  retn
```
