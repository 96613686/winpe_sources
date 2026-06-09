# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1400028b4`
- end: `0x140002950`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `156`
- prototype: `__int64(wchar_t *Buffer, __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002950`

## callees

- `0x1400028b4`
- `0x140002a70`

## import_xrefs

- `ucrtbase_clr0400!__stdio_common_vswprintf` at `0x14000291a`
- `ucrtbase_clr0400!__stdio_common_vswprintf` at `0x14000291a`

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
0x1400028b4  mov     [rsp+arg_10], r8
0x1400028b9  mov     qword ptr [rsp+arg_18], r9
0x1400028be  push    rbx
0x1400028bf  push    rbp
0x1400028c0  push    rsi
0x1400028c1  push    rdi
0x1400028c2  push    r14
0x1400028c4  push    r15
0x1400028c6  sub     rsp, 38h
0x1400028ca  lea     rax, [rdx-1]
0x1400028ce  xor     ebx, ebx
0x1400028d0  mov     rbp, r8
0x1400028d3  mov     r14, rcx
0x1400028d6  cmp     rax, 7FFFFFFEh
0x1400028dc  jbe     short loc_1400028ED
0x1400028de  mov     edi, 80070057h
0x1400028e3  test    rdx, rdx
0x1400028e6  jz      short loc_140002941
0x1400028e8  mov     [rcx], bx
0x1400028eb  jmp     short loc_140002941
0x1400028ed  lea     r15, [rsp+68h+arg_18]
0x1400028f5  mov     edi, ebx
0x1400028f7  lea     rsi, [rdx-1]
0x1400028fb  call    __local_stdio_printf_options
0x140002900  mov     [rsp+68h+ArgList], r15; ArgList
0x140002905  mov     r9, rbp; Format
0x140002908  mov     r8, rsi; BufferCount
0x14000290b  mov     [rsp+68h+Locale], rbx; Locale
0x140002910  mov     rdx, r14; Buffer
0x140002913  mov     rcx, [rax]
0x140002916  or      rcx, 1; Options
0x14000291a  call    cs:__imp___stdio_common_vswprintf
0x140002920  or      ecx, 0FFFFFFFFh
0x140002923  test    eax, eax
0x140002925  cmovs   eax, ecx
0x140002928  test    eax, eax
0x14000292a  js      short loc_140002937
0x14000292c  cdqe
0x14000292e  cmp     rax, rsi
0x140002931  ja      short loc_140002937
0x140002933  jnz     short loc_140002941
0x140002935  jmp     short loc_14000293C
0x140002937  mov     edi, 8007007Ah
0x14000293c  mov     [r14+rsi*2], bx
0x140002941  mov     eax, edi
0x140002943  add     rsp, 38h
0x140002947  pop     r15
0x140002949  pop     r14
0x14000294b  pop     rdi
0x14000294c  pop     rsi
0x14000294d  pop     rbp
0x14000294e  pop     rbx
0x14000294f  retn
```
