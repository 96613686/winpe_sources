# _snwprintf_s<1024>(ushort (&)[1024],unsigned __int64,ushort const *,...)

- ea: `0x140001f2c`
- end: `0x140001f8a`
- name: `??$_snwprintf_s@$0EAA@@@YAHAEAY0EAA@G_KPEBGZZ`
- size: `94`
- prototype: `__int64 __fastcall(wchar_t *Buffer, size_t MaxCount, wchar_t *Format)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001230`

## callees

- `0x140002e64`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x140001f73`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x140001f73`

## pseudocode

```c
int _snwprintf_s<1024>(wchar_t *Buffer, size_t MaxCount, wchar_t *Format, ...)
{
  unsigned __int64 *v6; // rax
  int result; // eax
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, Format);
  v6 = _local_stdio_printf_options();
  result = __stdio_common_vsnwprintf_s(*v6, Buffer, 0x400u, MaxCount, Format, 0, va);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x140001f2c  mov     rax, rsp
0x140001f2f  mov     [rax+18h], r8
0x140001f33  mov     [rax+20h], r9
0x140001f37  push    rbx
0x140001f38  push    rbp
0x140001f39  push    rsi
0x140001f3a  push    rdi
0x140001f3b  sub     rsp, 48h
0x140001f3f  mov     rsi, r8
0x140001f42  lea     rbp, [rax+20h]
0x140001f46  mov     rbx, rdx
0x140001f49  mov     rdi, rcx
0x140001f4c  call    __local_stdio_printf_options
0x140001f51  mov     [rsp+68h+ArgList], rbp; ArgList
0x140001f56  mov     r9, rbx; MaxCount
0x140001f59  mov     [rsp+68h+Locale], 0; Locale
0x140001f62  mov     r8d, 400h; BufferCount
0x140001f68  mov     rdx, rdi; Buffer
0x140001f6b  mov     [rsp+68h+Format], rsi; Format
0x140001f70  mov     rcx, [rax]; Options
0x140001f73  call    cs:__imp___stdio_common_vsnwprintf_s
0x140001f79  or      ecx, 0FFFFFFFFh
0x140001f7c  test    eax, eax
0x140001f7e  cmovs   eax, ecx
0x140001f81  add     rsp, 48h
0x140001f85  pop     rdi
0x140001f86  pop     rsi
0x140001f87  pop     rbp
0x140001f88  pop     rbx
0x140001f89  retn
```
