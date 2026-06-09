# _vsnwprintf

- ea: `0x1800022f8`
- end: `0x180002346`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004cc4`
- `0x180005c54`
- `0x1800114a0`

## callees

- `0x180001594`
- `0x18000225a`

## pseudocode

```c
int __cdecl vsnwprintf(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)
{
  unsigned __int64 *v8; // rax
  int result; // eax

  v8 = _local_stdio_printf_options();
  result = o___stdio_common_vswprintf_0(*v8 | 1, Buffer, BufferCount, Format, 0, Args);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x1800022f8  push    rbx
0x1800022fa  push    rbp
0x1800022fb  push    rsi
0x1800022fc  push    rdi
0x1800022fd  sub     rsp, 38h
0x180002301  mov     rbx, r9
0x180002304  mov     rdi, r8
0x180002307  mov     rsi, rdx
0x18000230a  mov     rbp, rcx
0x18000230d  call    __local_stdio_printf_options
0x180002312  mov     [rsp+58h+ArgList], rbx; ArgList
0x180002317  mov     r9, rdi; Format
0x18000231a  mov     r8, rsi; BufferCount
0x18000231d  mov     [rsp+58h+Locale], 0; Locale
0x180002326  mov     rdx, rbp; Buffer
0x180002329  mov     rcx, [rax]
0x18000232c  or      rcx, 1; Options
0x180002330  call    _o___stdio_common_vswprintf_0
0x180002335  or      ecx, 0FFFFFFFFh
0x180002338  test    eax, eax
0x18000233a  cmovs   eax, ecx
0x18000233d  add     rsp, 38h
0x180002341  pop     rdi
0x180002342  pop     rsi
0x180002343  pop     rbp
0x180002344  pop     rbx
0x180002345  retn
```
