# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180007f00`
- end: `0x180007f9c`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `156`
- prototype: `__int64(wchar_t *Buffer, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800066dc`

## callees

- `0x180007ef8`
- `0x180007f00`

## import_xrefs

- `ucrtbase_clr0400!__stdio_common_vswprintf` at `0x180007f66`
- `ucrtbase_clr0400!__stdio_common_vswprintf` at `0x180007f66`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *Buffer, __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned int v5; // edi
  size_t v6; // rsi
  unsigned __int64 *v7; // rax
  int v8; // eax
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( (unsigned __int64)(a2 - 1) <= 0x7FFFFFFE )
  {
    v5 = 0;
    v6 = a2 - 1;
    v7 = _local_stdio_printf_options();
    v8 = __stdio_common_vswprintf(*v7 | 1, Buffer, v6, a3, 0, va);
    if ( v8 < 0 )
      v8 = -1;
    if ( v8 < 0 || v8 > v6 )
    {
      v5 = -2147024774;
    }
    else if ( v8 != v6 )
    {
      return v5;
    }
    Buffer[v6] = 0;
    return v5;
  }
  v5 = -2147024809;
  if ( a2 )
    *Buffer = 0;
  return v5;
}

```

## disassembly

```asm
0x180007f00  mov     [rsp+arg_10], r8
0x180007f05  mov     qword ptr [rsp+arg_18], r9
0x180007f0a  push    rbx
0x180007f0b  push    rbp
0x180007f0c  push    rsi
0x180007f0d  push    rdi
0x180007f0e  push    r14
0x180007f10  push    r15
0x180007f12  sub     rsp, 38h
0x180007f16  lea     rax, [rdx-1]
0x180007f1a  xor     ebx, ebx
0x180007f1c  mov     rbp, r8
0x180007f1f  mov     r14, rcx
0x180007f22  cmp     rax, 7FFFFFFEh
0x180007f28  jbe     short loc_180007F39
0x180007f2a  mov     edi, 80070057h
0x180007f2f  test    rdx, rdx
0x180007f32  jz      short loc_180007F8D
0x180007f34  mov     [rcx], bx
0x180007f37  jmp     short loc_180007F8D
0x180007f39  lea     r15, [rsp+68h+arg_18]
0x180007f41  mov     edi, ebx
0x180007f43  lea     rsi, [rdx-1]
0x180007f47  call    __local_stdio_printf_options
0x180007f4c  mov     [rsp+68h+ArgList], r15; ArgList
0x180007f51  mov     r9, rbp; Format
0x180007f54  mov     r8, rsi; BufferCount
0x180007f57  mov     [rsp+68h+Locale], rbx; Locale
0x180007f5c  mov     rdx, r14; Buffer
0x180007f5f  mov     rcx, [rax]
0x180007f62  or      rcx, 1; Options
0x180007f66  call    cs:__imp___stdio_common_vswprintf
0x180007f6c  or      ecx, 0FFFFFFFFh
0x180007f6f  test    eax, eax
0x180007f71  cmovs   eax, ecx
0x180007f74  test    eax, eax
0x180007f76  js      short loc_180007F83
0x180007f78  cdqe
0x180007f7a  cmp     rax, rsi
0x180007f7d  ja      short loc_180007F83
0x180007f7f  jnz     short loc_180007F8D
0x180007f81  jmp     short loc_180007F88
0x180007f83  mov     edi, 8007007Ah
0x180007f88  mov     [r14+rsi*2], bx
0x180007f8d  mov     eax, edi
0x180007f8f  add     rsp, 38h
0x180007f93  pop     r15
0x180007f95  pop     r14
0x180007f97  pop     rdi
0x180007f98  pop     rsi
0x180007f99  pop     rbp
0x180007f9a  pop     rbx
0x180007f9b  retn
```
