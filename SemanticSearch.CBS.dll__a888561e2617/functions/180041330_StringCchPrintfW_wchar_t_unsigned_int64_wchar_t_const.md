# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x180041330`
- end: `0x1800413ef`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `191`
- prototype: `__int64(wchar_t *Buffer, unsigned __int64, const wchar_t *, ...)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180041f80`
- `0x1800435d0`
- `0x180063250`
- `0x180063332`
- `0x18006345a`
- `0x1800634cb`
- `0x180063602`
- `0x180063659`
- `0x1800636b0`
- `0x1800637f3`
- `0x18006384a`
- `0x1800638a1`
- `0x1800638f8`

## callees

- `0x1800161c0`
- `0x180041330`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1800413a2`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1800413a2`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *Buffer, __int64 a2, const wchar_t *a3, ...)
{
  __int64 result; // rax
  unsigned int v6; // ebx
  size_t v7; // rdi
  unsigned __int64 *v8; // rax
  int v9; // eax
  va_list va; // [rsp+78h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( (unsigned __int64)(a2 - 1) <= 0x7FFFFFFE )
  {
    v6 = 0;
    v7 = a2 - 1;
    v8 = _local_stdio_printf_options();
    v9 = __stdio_common_vswprintf(*v8 | 1, Buffer, v7, a3, 0, va);
    if ( v9 < 0 )
      v9 = -1;
    if ( v9 < 0 || v9 > v7 )
    {
      Buffer[v7] = 0;
      return (unsigned int)-2147024774;
    }
    else if ( v9 == v7 )
    {
      Buffer[v7] = 0;
      return 0;
    }
    return v6;
  }
  else
  {
    result = 2147942487LL;
    if ( a2 )
      *Buffer = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180041330  mov     [rsp+arg_10], r8
0x180041335  mov     qword ptr [rsp+arg_18], r9
0x18004133a  push    rbx
0x18004133b  push    rbp
0x18004133c  push    rsi
0x18004133d  sub     rsp, 40h
0x180041341  lea     rax, [rdx-1]
0x180041345  mov     rbp, r8
0x180041348  mov     rsi, rcx
0x18004134b  cmp     rax, 7FFFFFFEh
0x180041351  jbe     short loc_18004136E
0x180041353  mov     eax, 80070057h
0x180041358  test    rdx, rdx
0x18004135b  jz      loc_1800413E7
0x180041361  xor     ebx, ebx
0x180041363  mov     [rcx], bx
0x180041366  add     rsp, 40h
0x18004136a  pop     rsi
0x18004136b  pop     rbp
0x18004136c  pop     rbx
0x18004136d  retn
0x18004136e  mov     [rsp+58h+var_20], rdi
0x180041373  xor     ebx, ebx
0x180041375  mov     [rsp+58h+var_28], r14
0x18004137a  lea     rdi, [rdx-1]
0x18004137e  lea     r14, [rsp+58h+arg_18]
0x180041383  call    __local_stdio_printf_options
0x180041388  mov     [rsp+58h+ArgList], r14; ArgList
0x18004138d  mov     r9, rbp; Format
0x180041390  mov     r8, rdi; BufferCount
0x180041393  mov     [rsp+58h+Locale], rbx; Locale
0x180041398  mov     rdx, rsi; Buffer
0x18004139b  mov     rcx, [rax]
0x18004139e  or      rcx, 1; Options
0x1800413a2  call    cs:__imp___stdio_common_vswprintf
0x1800413a8  mov     r14, [rsp+58h+var_28]
0x1800413ad  mov     ecx, 0FFFFFFFFh
0x1800413b2  test    eax, eax
0x1800413b4  cmovs   eax, ecx
0x1800413b7  test    eax, eax
0x1800413b9  js      short loc_1800413D7
0x1800413bb  cdqe
0x1800413bd  cmp     rax, rdi
0x1800413c0  ja      short loc_1800413D7
0x1800413c2  jnz     short loc_1800413E0
0x1800413c4  mov     [rsi+rdi*2], bx
0x1800413c8  mov     eax, ebx
0x1800413ca  mov     rdi, [rsp+58h+var_20]
0x1800413cf  add     rsp, 40h
0x1800413d3  pop     rsi
0x1800413d4  pop     rbp
0x1800413d5  pop     rbx
0x1800413d6  retn
0x1800413d7  mov     [rsi+rdi*2], bx
0x1800413db  mov     ebx, 8007007Ah
0x1800413e0  mov     rdi, [rsp+58h+var_20]
0x1800413e5  mov     eax, ebx
0x1800413e7  add     rsp, 40h
0x1800413eb  pop     rsi
0x1800413ec  pop     rbp
0x1800413ed  pop     rbx
0x1800413ee  retn
```
