# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x14000afc8`
- end: `0x14000b076`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `174`
- prototype: `__int64(wchar_t *Buffer, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400078ec`
- `0x140007cbc`

## callees

- `0x1400068fc`
- `0x14000afc8`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x14000b02f`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x14000b02f`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *Buffer, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned int v5; // edx
  size_t v6; // rbx
  unsigned __int64 *v7; // rax
  int v8; // eax
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v6 = a2 - 1;
      v7 = _local_stdio_printf_options();
      v8 = __stdio_common_vswprintf(*v7 | 1, Buffer, v6, a3, 0, va);
      if ( v8 < 0 || v8 > v6 )
      {
        v5 = -2147024774;
        Buffer[v6] = 0;
      }
      else
      {
        v5 = 0;
        if ( v8 == v6 )
          Buffer[v6] = 0;
      }
    }
    else
    {
      v5 = -2147024809;
      *Buffer = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x14000afc8  mov     [rsp+arg_10], r8
0x14000afcd  mov     qword ptr [rsp+arg_18], r9
0x14000afd2  push    rbx
0x14000afd3  push    rbp
0x14000afd4  push    rsi
0x14000afd5  push    rdi
0x14000afd6  sub     rsp, 48h
0x14000afda  mov     rsi, r8
0x14000afdd  mov     rax, rdx
0x14000afe0  mov     rdi, rcx
0x14000afe3  test    rdx, rdx
0x14000afe6  jz      short loc_14000B05C
0x14000afe8  cmp     rax, 7FFFFFFFh
0x14000afee  jbe     short loc_14000AFF7
0x14000aff0  mov     edx, 80070057h
0x14000aff5  jmp     short loc_14000B066
0x14000aff7  mov     [rsp+68h+var_38], 0
0x14000b000  lea     rbp, [rsp+68h+arg_18]
0x14000b008  lea     rbx, [rdx-1]
0x14000b00c  call    __local_stdio_printf_options
0x14000b011  mov     [rsp+68h+ArgList], rbp; ArgList
0x14000b016  mov     r9, rsi; Format
0x14000b019  mov     r8, rbx; BufferCount
0x14000b01c  mov     [rsp+68h+Locale], 0; Locale
0x14000b025  mov     rdx, rdi; Buffer
0x14000b028  mov     rcx, [rax]
0x14000b02b  or      rcx, 1; Options
0x14000b02f  call    cs:__imp___stdio_common_vswprintf
0x14000b035  test    eax, eax
0x14000b037  js      short loc_14000B04F
0x14000b039  cdqe
0x14000b03b  cmp     rax, rbx
0x14000b03e  ja      short loc_14000B04F
0x14000b040  xor     edx, edx
0x14000b042  cmp     rax, rbx
0x14000b045  jnz     short loc_14000B06B
0x14000b047  xor     eax, eax
0x14000b049  mov     [rdi+rbx*2], ax
0x14000b04d  jmp     short loc_14000B06B
0x14000b04f  xor     eax, eax
0x14000b051  mov     edx, 8007007Ah
0x14000b056  mov     [rdi+rbx*2], ax
0x14000b05a  jmp     short loc_14000B06B
0x14000b05c  mov     edx, 80070057h
0x14000b061  test    rax, rax
0x14000b064  jz      short loc_14000B06B
0x14000b066  xor     ecx, ecx
0x14000b068  mov     [rdi], cx
0x14000b06b  mov     eax, edx
0x14000b06d  add     rsp, 48h
0x14000b071  pop     rdi
0x14000b072  pop     rsi
0x14000b073  pop     rbp
0x14000b074  pop     rbx
0x14000b075  retn
```
