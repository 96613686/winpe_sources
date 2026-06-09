# _vsnprintf

- ea: `0x1800022d8`
- end: `0x180002326`
- name: `_vsnprintf`
- size: `78`
- prototype: `int __cdecl(char *const Buffer, const size_t BufferCount, const char *const Format, va_list ArgList)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800024bc`
- `0x18000308c`

## callees

- `0x180001354`
- `0x18000222e`

## pseudocode

```c
int __cdecl vsnprintf(char *const Buffer, const size_t BufferCount, const char *const Format, va_list ArgList)
{
  unsigned __int64 *v8; // rax
  int result; // eax

  v8 = _local_stdio_printf_options();
  result = o___stdio_common_vsprintf_0(*v8 | 1, Buffer, BufferCount, Format, 0, ArgList);
  if ( result < 0 )
    return -1;
  return result;
}

```

## disassembly

```asm
0x1800022d8  push    rbx
0x1800022da  push    rbp
0x1800022db  push    rsi
0x1800022dc  push    rdi
0x1800022dd  sub     rsp, 38h
0x1800022e1  mov     rbx, r9
0x1800022e4  mov     rdi, r8
0x1800022e7  mov     rsi, rdx
0x1800022ea  mov     rbp, rcx
0x1800022ed  call    __local_stdio_printf_options
0x1800022f2  mov     [rsp+58h+ArgList], rbx; ArgList
0x1800022f7  mov     r9, rdi; Format
0x1800022fa  mov     r8, rsi; BufferCount
0x1800022fd  mov     [rsp+58h+Locale], 0; Locale
0x180002306  mov     rdx, rbp; Buffer
0x180002309  mov     rcx, [rax]
0x18000230c  or      rcx, 1; Options
0x180002310  call    _o___stdio_common_vsprintf_0
0x180002315  or      ecx, 0FFFFFFFFh
0x180002318  test    eax, eax
0x18000231a  cmovs   eax, ecx
0x18000231d  add     rsp, 38h
0x180002321  pop     rdi
0x180002322  pop     rsi
0x180002323  pop     rbp
0x180002324  pop     rbx
0x180002325  retn
```
