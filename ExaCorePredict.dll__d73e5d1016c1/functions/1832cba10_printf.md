# printf

- ea: `0x1832cba10`
- end: `0x1832cba65`
- name: `printf`
- size: `85`
- prototype: `int(const char *const Format, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1832cb9b0`

## callees

- `0x1815ce4b0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__acrt_iob_func` at `0x1832cba38`
- `api-ms-win-crt-stdio-l1-1-0!__acrt_iob_func` at `0x1832cba38`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vfprintf` at `0x1832cba57`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vfprintf` at `0x1832cba57`

## pseudocode

```c
int printf(const char *const Format, ...)
{
  FILE *v2; // rbx
  unsigned __int64 *v3; // rax
  va_list va; // [rsp+58h] [rbp+10h] BYREF

  va_start(va, Format);
  v2 = __acrt_iob_func(1u);
  v3 = _local_stdio_printf_options();
  return __stdio_common_vfprintf(*v3, v2, Format, 0, va);
}

```

## disassembly

```asm
0x1832cba10  mov     [rsp+arg_0], rcx
0x1832cba15  mov     qword ptr [rsp+arg_8], rdx
0x1832cba1a  mov     [rsp+arg_10], r8
0x1832cba1f  mov     [rsp+arg_18], r9
0x1832cba24  push    rbx
0x1832cba25  push    rsi
0x1832cba26  push    rdi
0x1832cba27  sub     rsp, 30h
0x1832cba2b  mov     rdi, rcx
0x1832cba2e  lea     rsi, [rsp+48h+arg_8]
0x1832cba33  mov     ecx, 1; Ix
0x1832cba38  call    cs:__imp___acrt_iob_func
0x1832cba3e  mov     rbx, rax
0x1832cba41  call    __local_stdio_printf_options
0x1832cba46  xor     r9d, r9d; Locale
0x1832cba49  mov     [rsp+48h+ArgList], rsi; ArgList
0x1832cba4e  mov     r8, rdi; Format
0x1832cba51  mov     rdx, rbx; Stream
0x1832cba54  mov     rcx, [rax]; Options
0x1832cba57  call    cs:__imp___stdio_common_vfprintf
0x1832cba5d  add     rsp, 30h
0x1832cba61  pop     rdi
0x1832cba62  pop     rsi
0x1832cba63  pop     rbx
0x1832cba64  retn
```
