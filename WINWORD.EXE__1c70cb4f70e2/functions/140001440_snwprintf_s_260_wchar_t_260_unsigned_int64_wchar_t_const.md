# _snwprintf_s<260>(wchar_t (&)[260],unsigned __int64,wchar_t const *,...)

- ea: `0x140001440`
- end: `0x1400014a6`
- name: `??$_snwprintf_s@$0BAE@@@YAHAEAY0BAE@_W_KPEB_WZZ`
- size: `102`
- prototype: `__int64 __fastcall(wchar_t *Buffer, size_t MaxCount, wchar_t *Format)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400011a0`
- `0x140003e24`

## callees

- `0x1400014b0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x14000148b`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vsnwprintf_s` at `0x14000148b`

## pseudocode

```c
int _snwprintf_s<260>(wchar_t *Buffer, size_t MaxCount, wchar_t *Format, ...)
{
  unsigned __int64 *v6; // rax
  int result; // eax
  va_list va; // [rsp+98h] [rbp+20h] BYREF

  va_start(va, Format);
  v6 = _local_stdio_printf_options();
  result = __stdio_common_vsnwprintf_s(*v6, Buffer, 0x104u, MaxCount, Format, 0, va);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x140001440  mov     [rsp+arg_10], r8
0x140001445  mov     qword ptr [rsp+arg_18], r9
0x14000144a  push    rbx
0x14000144b  push    rbp
0x14000144c  push    rsi
0x14000144d  push    rdi
0x14000144e  push    r14
0x140001450  sub     rsp, 50h
0x140001454  mov     rsi, r8
0x140001457  lea     rbp, [rsp+78h+arg_18]
0x14000145f  mov     rbx, rdx
0x140001462  mov     rdi, rcx
0x140001465  xor     r14d, r14d
0x140001468  call    __local_stdio_printf_options
0x14000146d  mov     [rsp+78h+ArgList], rbp; ArgList
0x140001472  mov     r9, rbx; MaxCount
0x140001475  mov     [rsp+78h+Locale], r14; Locale
0x14000147a  mov     r8d, 104h; BufferCount
0x140001480  mov     rdx, rdi; Buffer
0x140001483  mov     [rsp+78h+Format], rsi; Format
0x140001488  mov     rcx, [rax]; Options
0x14000148b  call    cs:__imp___stdio_common_vsnwprintf_s
0x140001491  test    eax, eax
0x140001493  mov     ecx, 0FFFFFFFFh
0x140001498  cmovs   eax, ecx
0x14000149b  add     rsp, 50h
0x14000149f  pop     r14
0x1400014a1  pop     rdi
0x1400014a2  pop     rsi
0x1400014a3  pop     rbp
0x1400014a4  pop     rbx
0x1400014a5  retn
```
