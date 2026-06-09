# _vsscanf_s_l

- ea: `0x1800b01a4`
- end: `0x1800b0206`
- name: `_vsscanf_s_l`
- size: `98`
- prototype: `int __cdecl(const char *const Buffer, const char *const Format, const _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800b0240`

## callees

- `0x1800b0128`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsscanf` at `0x1800b01e4`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsscanf` at `0x1800b01e4`

## pseudocode

```c
int __cdecl vsscanf_s_l(const char *const Buffer, const char *const Format, const _locale_t Locale, va_list ArgList)
{
  unsigned __int64 *v8; // rax

  v8 = _local_stdio_scanf_options();
  return __stdio_common_vsscanf(*v8 | 1, Buffer, 0xFFFFFFFFFFFFFFFFuLL, Format, Locale, ArgList);
}

```

## disassembly

```asm
0x1800b01a4  mov     [rsp+arg_0], rbx
0x1800b01a9  mov     [rsp+arg_8], rbp
0x1800b01ae  mov     [rsp+arg_10], rsi
0x1800b01b3  push    rdi
0x1800b01b4  sub     rsp, 30h
0x1800b01b8  mov     rbx, r9
0x1800b01bb  mov     rdi, r8
0x1800b01be  mov     rsi, rdx
0x1800b01c1  mov     rbp, rcx
0x1800b01c4  call    __local_stdio_scanf_options
0x1800b01c9  mov     [rsp+38h+ArgList], rbx; ArgList
0x1800b01ce  mov     r9, rsi; Format
0x1800b01d1  or      r8, 0FFFFFFFFFFFFFFFFh; BufferCount
0x1800b01d5  mov     [rsp+38h+Locale], rdi; Locale
0x1800b01da  mov     rdx, rbp; Buffer
0x1800b01dd  mov     rcx, [rax]
0x1800b01e0  or      rcx, 1; Options
0x1800b01e4  call    cs:__imp___stdio_common_vsscanf
0x1800b01eb  nop     dword ptr [rax+rax+00h]
0x1800b01f0  mov     rbx, [rsp+38h+arg_0]
0x1800b01f5  mov     rbp, [rsp+38h+arg_8]
0x1800b01fa  mov     rsi, [rsp+38h+arg_10]
0x1800b01ff  add     rsp, 30h
0x1800b0203  pop     rdi
0x1800b0204  retn
```
