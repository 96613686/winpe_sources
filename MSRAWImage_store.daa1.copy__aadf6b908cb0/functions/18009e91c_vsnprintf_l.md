# _vsnprintf_l

- ea: `0x18009e91c`
- end: `0x18009e98a`
- name: `_vsnprintf_l`
- size: `110`
- prototype: `int __cdecl(char *const Buffer, const size_t BufferCount, const char *const Format, const _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18009e09c`

## callees

- `0x18009e90c`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsprintf` at `0x18009e960`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsprintf` at `0x18009e960`

## pseudocode

```c
int __cdecl vsnprintf_l(
        char *const Buffer,
        const size_t BufferCount,
        const char *const Format,
        const _locale_t Locale,
        va_list ArgList)
{
  unsigned __int64 v9; // rcx
  int result; // eax

  v9 = *_local_stdio_printf_options();
  result = __stdio_common_vsprintf(v9 | 1, Buffer, BufferCount, Format, Locale, ArgList);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x18009e91c  mov     [rsp+arg_0], rbx
0x18009e921  mov     [rsp+arg_8], rbp
0x18009e926  mov     [rsp+arg_10], rsi
0x18009e92b  push    rdi
0x18009e92c  sub     rsp, 30h
0x18009e930  mov     rbx, r9
0x18009e933  mov     rdi, r8
0x18009e936  mov     rsi, rdx
0x18009e939  mov     rbp, rcx
0x18009e93c  call    __local_stdio_printf_options
0x18009e941  mov     r9, rdi; Format
0x18009e944  mov     r8, rsi; BufferCount
0x18009e947  mov     rdx, rbp; Buffer
0x18009e94a  mov     rcx, [rax]
0x18009e94d  mov     rax, [rsp+38h+ArgList]
0x18009e952  or      rcx, 1; Options
0x18009e956  mov     [rsp+38h+var_10], rax; ArgList
0x18009e95b  mov     [rsp+38h+Locale], rbx; Locale
0x18009e960  call    cs:__imp___stdio_common_vsprintf
0x18009e967  nop     dword ptr [rax+rax+00h]
0x18009e96c  mov     rbx, [rsp+38h+arg_0]
0x18009e971  or      ecx, 0FFFFFFFFh
0x18009e974  mov     rbp, [rsp+38h+arg_8]
0x18009e979  test    eax, eax
0x18009e97b  mov     rsi, [rsp+38h+arg_10]
0x18009e980  cmovs   eax, ecx
0x18009e983  add     rsp, 30h
0x18009e987  pop     rdi
0x18009e988  retn
```
