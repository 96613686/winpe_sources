# _vsnwprintf_s

- ea: `0x140001f5c`
- end: `0x140001fb3`
- name: `_vsnwprintf_s`
- size: `87`
- prototype: `int __cdecl(wchar_t *const Buffer, const size_t BufferCount, const size_t MaxCount, const wchar_t *const Format, va_list ArgList)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140004368`
- `0x140005154`

## callees

- `0x140001234`
- `0x140001e42`

## pseudocode

```c
int __cdecl vsnwprintf_s(
        wchar_t *const Buffer,
        const size_t BufferCount,
        const size_t MaxCount,
        const wchar_t *const Format,
        va_list ArgList)
{
  unsigned __int64 *v9; // rax
  int result; // eax

  v9 = _local_stdio_printf_options();
  result = _stdio_common_vsnwprintf_s(*v9, Buffer, BufferCount, MaxCount, Format, 0, ArgList);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x140001f5c  push    rbx
0x140001f5e  push    rbp
0x140001f5f  push    rsi
0x140001f60  push    rdi
0x140001f61  sub     rsp, 48h
0x140001f65  mov     rbx, r9
0x140001f68  mov     rdi, r8
0x140001f6b  mov     rsi, rdx
0x140001f6e  mov     rbp, rcx
0x140001f71  call    __local_stdio_printf_options
0x140001f76  mov     r10, [rsp+68h+ArgList]
0x140001f7e  mov     r9, rdi; MaxCount
0x140001f81  mov     [rsp+68h+var_38], r10; ArgList
0x140001f86  mov     r8, rsi; BufferCount
0x140001f89  mov     [rsp+68h+Locale], 0; Locale
0x140001f92  mov     rdx, rbp; Buffer
0x140001f95  mov     rcx, [rax]; Options
0x140001f98  mov     [rsp+68h+Format], rbx; Format
0x140001f9d  call    __stdio_common_vsnwprintf_s
0x140001fa2  or      ecx, 0FFFFFFFFh
0x140001fa5  test    eax, eax
0x140001fa7  cmovs   eax, ecx
0x140001faa  add     rsp, 48h
0x140001fae  pop     rdi
0x140001faf  pop     rsi
0x140001fb0  pop     rbp
0x140001fb1  pop     rbx
0x140001fb2  retn
```
