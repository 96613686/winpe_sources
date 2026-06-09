# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x14000bbd8`
- end: `0x14000bc86`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `174`
- prototype: `__int64(wchar_t *Buffer, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140008718`
- `0x140008ae8`

## callees

- `0x140007238`
- `0x14000bbd8`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x14000bc3f`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x14000bc3f`

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
0x14000bbd8  mov     [rsp+arg_10], r8
0x14000bbdd  mov     qword ptr [rsp+arg_18], r9
0x14000bbe2  push    rbx
0x14000bbe3  push    rbp
0x14000bbe4  push    rsi
0x14000bbe5  push    rdi
0x14000bbe6  sub     rsp, 48h
0x14000bbea  mov     rsi, r8
0x14000bbed  mov     rax, rdx
0x14000bbf0  mov     rdi, rcx
0x14000bbf3  test    rdx, rdx
0x14000bbf6  jz      short loc_14000BC6C
0x14000bbf8  cmp     rax, 7FFFFFFFh
0x14000bbfe  jbe     short loc_14000BC07
0x14000bc00  mov     edx, 80070057h
0x14000bc05  jmp     short loc_14000BC76
0x14000bc07  mov     [rsp+68h+var_38], 0
0x14000bc10  lea     rbp, [rsp+68h+arg_18]
0x14000bc18  lea     rbx, [rdx-1]
0x14000bc1c  call    __local_stdio_printf_options
0x14000bc21  mov     [rsp+68h+ArgList], rbp; ArgList
0x14000bc26  mov     r9, rsi; Format
0x14000bc29  mov     r8, rbx; BufferCount
0x14000bc2c  mov     [rsp+68h+Locale], 0; Locale
0x14000bc35  mov     rdx, rdi; Buffer
0x14000bc38  mov     rcx, [rax]
0x14000bc3b  or      rcx, 1; Options
0x14000bc3f  call    cs:__imp___stdio_common_vswprintf
0x14000bc45  test    eax, eax
0x14000bc47  js      short loc_14000BC5F
0x14000bc49  cdqe
0x14000bc4b  cmp     rax, rbx
0x14000bc4e  ja      short loc_14000BC5F
0x14000bc50  xor     edx, edx
0x14000bc52  cmp     rax, rbx
0x14000bc55  jnz     short loc_14000BC7B
0x14000bc57  xor     eax, eax
0x14000bc59  mov     [rdi+rbx*2], ax
0x14000bc5d  jmp     short loc_14000BC7B
0x14000bc5f  xor     eax, eax
0x14000bc61  mov     edx, 8007007Ah
0x14000bc66  mov     [rdi+rbx*2], ax
0x14000bc6a  jmp     short loc_14000BC7B
0x14000bc6c  mov     edx, 80070057h
0x14000bc71  test    rax, rax
0x14000bc74  jz      short loc_14000BC7B
0x14000bc76  xor     ecx, ecx
0x14000bc78  mov     [rdi], cx
0x14000bc7b  mov     eax, edx
0x14000bc7d  add     rsp, 48h
0x14000bc81  pop     rdi
0x14000bc82  pop     rsi
0x14000bc83  pop     rbp
0x14000bc84  pop     rbx
0x14000bc85  retn
```
