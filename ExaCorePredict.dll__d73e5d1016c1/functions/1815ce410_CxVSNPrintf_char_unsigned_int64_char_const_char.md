# CxVSNPrintf(char *,unsigned __int64,char const *,char *)

- ea: `0x1815ce410`
- end: `0x1815ce478`
- name: `?CxVSNPrintf@@YAHPEAD_KPEBD0@Z`
- size: `104`
- prototype: `__int64 __fastcall(char *Buffer, size_t BufferCount, const char *Format, va_list ArgList)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1815cea60`
- `0x182dcc420`
- `0x182dcc5d0`
- `0x182dcc6d0`
- `0x182dcc8c0`
- `0x182dcca70`
- `0x18306ad00`

## callees

- `0x1815ce4b0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnprintf_s` at `0x1815ce458`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnprintf_s` at `0x1815ce458`

## pseudocode

```c
int __fastcall CxVSNPrintf(char *Buffer, size_t BufferCount, const char *Format, va_list ArgList)
{
  unsigned __int64 *v8; // rax
  int result; // eax

  v8 = _local_stdio_printf_options();
  result = __stdio_common_vsnprintf_s(*v8, Buffer, BufferCount, 0xFFFFFFFFFFFFFFFFuLL, Format, 0, ArgList);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x1815ce410  mov     [rsp+arg_0], rbx
0x1815ce415  mov     [rsp+arg_8], rbp
0x1815ce41a  mov     [rsp+arg_10], rsi
0x1815ce41f  push    rdi
0x1815ce420  sub     rsp, 40h
0x1815ce424  mov     rbx, r9
0x1815ce427  mov     rdi, r8
0x1815ce42a  mov     rsi, rdx
0x1815ce42d  mov     rbp, rcx
0x1815ce430  call    __local_stdio_printf_options
0x1815ce435  mov     [rsp+48h+ArgList], rbx; ArgList
0x1815ce43a  mov     r8, rsi; BufferCount
0x1815ce43d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1815ce441  mov     [rsp+48h+Locale], 0; Locale
0x1815ce44a  mov     r9, rbx; MaxCount
0x1815ce44d  mov     [rsp+48h+Format], rdi; Format
0x1815ce452  mov     rcx, [rax]; Options
0x1815ce455  mov     rdx, rbp; Buffer
0x1815ce458  call    cs:__imp___stdio_common_vsnprintf_s
0x1815ce45e  mov     rbp, [rsp+48h+arg_8]
0x1815ce463  test    eax, eax
0x1815ce465  mov     rsi, [rsp+48h+arg_10]
0x1815ce46a  cmovs   eax, ebx
0x1815ce46d  mov     rbx, [rsp+48h+arg_0]
0x1815ce472  add     rsp, 40h
0x1815ce476  pop     rdi
0x1815ce477  retn
```
