# StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)

- ea: `0x140006cc0`
- end: `0x140006d57`
- name: `?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z`
- size: `151`
- prototype: `__int64 __fastcall(wchar_t *Buffer, unsigned __int64, const unsigned __int16 *, va_list)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006620`
- `0x14000f194`

## callees

- `0x140006cc0`
- `0x140007238`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x140006d10`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x140006d10`

## pseudocode

```c
__int64 __fastcall StringCchVPrintfW(wchar_t *Buffer, unsigned __int64 a2, const unsigned __int16 *a3, va_list a4)
{
  unsigned int v7; // edx
  size_t v8; // rbx
  unsigned __int64 *v9; // rax
  int v10; // eax

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v8 = a2 - 1;
      v9 = _local_stdio_printf_options();
      v10 = __stdio_common_vswprintf(*v9 | 1, Buffer, v8, a3, 0, a4);
      if ( v10 < 0 || v10 > v8 )
      {
        v7 = -2147024774;
        Buffer[v8] = 0;
      }
      else
      {
        v7 = 0;
        if ( v10 == v8 )
          Buffer[v8] = 0;
      }
    }
    else
    {
      v7 = -2147024809;
      *Buffer = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v7;
}

```

## disassembly

```asm
0x140006cc0  push    rbx
0x140006cc2  push    rbp
0x140006cc3  push    rsi
0x140006cc4  push    rdi
0x140006cc5  sub     rsp, 38h
0x140006cc9  mov     rsi, r9
0x140006ccc  mov     rbp, r8
0x140006ccf  mov     rax, rdx
0x140006cd2  mov     rdi, rcx
0x140006cd5  test    rdx, rdx
0x140006cd8  jz      short loc_140006D3D
0x140006cda  cmp     rax, 7FFFFFFFh
0x140006ce0  jbe     short loc_140006CE9
0x140006ce2  mov     edx, 80070057h
0x140006ce7  jmp     short loc_140006D47
0x140006ce9  lea     rbx, [rdx-1]
0x140006ced  call    __local_stdio_printf_options
0x140006cf2  mov     [rsp+58h+ArgList], rsi; ArgList
0x140006cf7  mov     r9, rbp; Format
0x140006cfa  mov     r8, rbx; BufferCount
0x140006cfd  mov     [rsp+58h+Locale], 0; Locale
0x140006d06  mov     rdx, rdi; Buffer
0x140006d09  mov     rcx, [rax]
0x140006d0c  or      rcx, 1; Options
0x140006d10  call    cs:__imp___stdio_common_vswprintf
0x140006d16  test    eax, eax
0x140006d18  js      short loc_140006D30
0x140006d1a  cdqe
0x140006d1c  cmp     rax, rbx
0x140006d1f  ja      short loc_140006D30
0x140006d21  xor     edx, edx
0x140006d23  cmp     rax, rbx
0x140006d26  jnz     short loc_140006D4C
0x140006d28  xor     eax, eax
0x140006d2a  mov     [rdi+rbx*2], ax
0x140006d2e  jmp     short loc_140006D4C
0x140006d30  xor     eax, eax
0x140006d32  mov     edx, 8007007Ah
0x140006d37  mov     [rdi+rbx*2], ax
0x140006d3b  jmp     short loc_140006D4C
0x140006d3d  mov     edx, 80070057h
0x140006d42  test    rax, rax
0x140006d45  jz      short loc_140006D4C
0x140006d47  xor     ecx, ecx
0x140006d49  mov     [rdi], cx
0x140006d4c  mov     eax, edx
0x140006d4e  add     rsp, 38h
0x140006d52  pop     rdi
0x140006d53  pop     rsi
0x140006d54  pop     rbp
0x140006d55  pop     rbx
0x140006d56  retn
```
