# StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)

- ea: `0x1800074b8`
- end: `0x18000754f`
- name: `?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z`
- size: `151`
- prototype: `__int64 __fastcall(wchar_t *Buffer, unsigned __int64, const unsigned __int16 *, char *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000640c`
- `0x18000e660`

## callees

- `0x1800074b8`
- `0x180007c68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf` at `0x180007508`
- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf` at `0x180007508`

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
0x1800074b8  push    rbx
0x1800074ba  push    rbp
0x1800074bb  push    rsi
0x1800074bc  push    rdi
0x1800074bd  sub     rsp, 38h
0x1800074c1  mov     rsi, r9
0x1800074c4  mov     rbp, r8
0x1800074c7  mov     rax, rdx
0x1800074ca  mov     rdi, rcx
0x1800074cd  test    rdx, rdx
0x1800074d0  jz      short loc_180007535
0x1800074d2  cmp     rax, 7FFFFFFFh
0x1800074d8  jbe     short loc_1800074E1
0x1800074da  mov     edx, 80070057h
0x1800074df  jmp     short loc_18000753F
0x1800074e1  lea     rbx, [rdx-1]
0x1800074e5  call    __local_stdio_printf_options
0x1800074ea  mov     [rsp+58h+ArgList], rsi; ArgList
0x1800074ef  mov     r9, rbp; Format
0x1800074f2  mov     r8, rbx; BufferCount
0x1800074f5  mov     [rsp+58h+Locale], 0; Locale
0x1800074fe  mov     rdx, rdi; Buffer
0x180007501  mov     rcx, [rax]
0x180007504  or      rcx, 1; Options
0x180007508  call    cs:__imp___stdio_common_vswprintf
0x18000750e  test    eax, eax
0x180007510  js      short loc_180007528
0x180007512  cdqe
0x180007514  cmp     rax, rbx
0x180007517  ja      short loc_180007528
0x180007519  xor     edx, edx
0x18000751b  cmp     rax, rbx
0x18000751e  jnz     short loc_180007544
0x180007520  xor     eax, eax
0x180007522  mov     [rdi+rbx*2], ax
0x180007526  jmp     short loc_180007544
0x180007528  xor     eax, eax
0x18000752a  mov     edx, 8007007Ah
0x18000752f  mov     [rdi+rbx*2], ax
0x180007533  jmp     short loc_180007544
0x180007535  mov     edx, 80070057h
0x18000753a  test    rax, rax
0x18000753d  jz      short loc_180007544
0x18000753f  xor     ecx, ecx
0x180007541  mov     [rdi], cx
0x180007544  mov     eax, edx
0x180007546  add     rsp, 38h
0x18000754a  pop     rdi
0x18000754b  pop     rsi
0x18000754c  pop     rbp
0x18000754d  pop     rbx
0x18000754e  retn
```
