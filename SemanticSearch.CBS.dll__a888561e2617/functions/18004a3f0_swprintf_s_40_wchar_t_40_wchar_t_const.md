# swprintf_s<40>(wchar_t (&)[40],wchar_t const *,...)

- ea: `0x18004a3f0`
- end: `0x18004a44b`
- name: `??$swprintf_s@$0CI@@@YAHAEAY0CI@_WPEB_WZZ`
- size: `91`
- prototype: `int(wchar_t *Buffer, wchar_t *Format, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800487e0`

## callees

- `0x1800161c0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf_s` at `0x18004a433`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf_s` at `0x18004a433`

## pseudocode

```c
int swprintf_s<40>(wchar_t *Buffer, wchar_t *Format, ...)
{
  unsigned __int64 *v4; // rax
  int result; // eax
  va_list va; // [rsp+60h] [rbp+18h] BYREF

  va_start(va, Format);
  v4 = _local_stdio_printf_options();
  result = __stdio_common_vswprintf_s(*v4, Buffer, 0x28u, Format, 0, va);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x18004a3f0  mov     [rsp+arg_8], rdx
0x18004a3f5  mov     qword ptr [rsp+arg_10], r8
0x18004a3fa  mov     [rsp+arg_18], r9
0x18004a3ff  push    rbx
0x18004a400  push    rsi
0x18004a401  push    rdi
0x18004a402  sub     rsp, 30h
0x18004a406  mov     rdi, rdx
0x18004a409  lea     rsi, [rsp+48h+arg_10]
0x18004a40e  mov     rbx, rcx
0x18004a411  call    __local_stdio_printf_options
0x18004a416  mov     [rsp+48h+ArgList], rsi; ArgList
0x18004a41b  mov     r9, rdi; Format
0x18004a41e  mov     r8d, 28h ; '('; BufferCount
0x18004a424  mov     [rsp+48h+Locale], 0; Locale
0x18004a42d  mov     rdx, rbx; Buffer
0x18004a430  mov     rcx, [rax]; Options
0x18004a433  call    cs:__imp___stdio_common_vswprintf_s
0x18004a439  test    eax, eax
0x18004a43b  mov     ecx, 0FFFFFFFFh
0x18004a440  cmovs   eax, ecx
0x18004a443  add     rsp, 30h
0x18004a447  pop     rdi
0x18004a448  pop     rsi
0x18004a449  pop     rbx
0x18004a44a  retn
```
