# swprintf_s

- ea: `0x18001c3a0`
- end: `0x18001c3f8`
- name: `swprintf_s`
- size: `88`
- prototype: `int(wchar_t *const Buffer, const size_t BufferCount, const wchar_t *const Format, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016760`

## callees

- `0x180002e50`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf_s` at `0x18001c3df`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf_s` at `0x18001c3df`

## pseudocode

```c
int swprintf_s(wchar_t *const Buffer, const size_t BufferCount, const wchar_t *const Format, ...)
{
  unsigned __int64 *v6; // rax
  int result; // eax
  va_list va; // [rsp+78h] [rbp+20h] BYREF

  va_start(va, Format);
  v6 = _local_stdio_printf_options();
  result = __stdio_common_vswprintf_s(*v6, Buffer, BufferCount, Format, 0, va);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x18001c3a0  mov     [rsp+arg_10], r8
0x18001c3a5  mov     qword ptr [rsp+arg_18], r9
0x18001c3aa  push    rbx
0x18001c3ab  push    rbp
0x18001c3ac  push    rsi
0x18001c3ad  push    rdi
0x18001c3ae  sub     rsp, 38h
0x18001c3b2  mov     rsi, r8
0x18001c3b5  lea     rbp, [rsp+58h+arg_18]
0x18001c3ba  mov     rdi, rdx
0x18001c3bd  mov     rbx, rcx
0x18001c3c0  call    __local_stdio_printf_options
0x18001c3c5  mov     [rsp+58h+ArgList], rbp; ArgList
0x18001c3ca  mov     r9, rsi; Format
0x18001c3cd  mov     r8, rdi; BufferCount
0x18001c3d0  mov     [rsp+58h+Locale], 0; Locale
0x18001c3d9  mov     rdx, rbx; Buffer
0x18001c3dc  mov     rcx, [rax]; Options
0x18001c3df  call    cs:__imp___stdio_common_vswprintf_s
0x18001c3e5  test    eax, eax
0x18001c3e7  mov     ecx, 0FFFFFFFFh
0x18001c3ec  cmovs   eax, ecx
0x18001c3ef  add     rsp, 38h
0x18001c3f3  pop     rdi
0x18001c3f4  pop     rsi
0x18001c3f5  pop     rbp
0x18001c3f6  pop     rbx
0x18001c3f7  retn
```
