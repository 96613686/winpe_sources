# _vsnwprintf

- ea: `0x1800020e8`
- end: `0x180002136`
- name: `_vsnwprintf`
- size: `78`
- prototype: `int __cdecl(wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, va_list Args)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800060b0`
- `0x1800072b0`
- `0x180008ec8`

## callees

- `0x180001254`
- `0x180001ffa`

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
0x1800020e8  push    rbx
0x1800020ea  push    rbp
0x1800020eb  push    rsi
0x1800020ec  push    rdi
0x1800020ed  sub     rsp, 38h
0x1800020f1  mov     rbx, r9
0x1800020f4  mov     rdi, r8
0x1800020f7  mov     rsi, rdx
0x1800020fa  mov     rbp, rcx
0x1800020fd  call    __local_stdio_printf_options
0x180002102  mov     [rsp+58h+ArgList], rbx; ArgList
0x180002107  mov     r9, rdi; Format
0x18000210a  mov     r8, rsi; BufferCount
0x18000210d  mov     [rsp+58h+Locale], 0; Locale
0x180002116  mov     rdx, rbp; Buffer
0x180002119  mov     rcx, [rax]
0x18000211c  or      rcx, 1; Options
0x180002120  call    _o___stdio_common_vswprintf_0
0x180002125  or      ecx, 0FFFFFFFFh
0x180002128  test    eax, eax
0x18000212a  cmovs   eax, ecx
0x18000212d  add     rsp, 38h
0x180002131  pop     rdi
0x180002132  pop     rsi
0x180002133  pop     rbp
0x180002134  pop     rbx
0x180002135  retn
```
