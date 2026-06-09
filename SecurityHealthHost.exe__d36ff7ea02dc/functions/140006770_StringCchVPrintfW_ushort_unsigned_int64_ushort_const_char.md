# StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)

- ea: `0x140006770`
- end: `0x140006807`
- name: `?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z`
- size: `151`
- prototype: `__int64 __fastcall(wchar_t *Buffer, unsigned __int64, const unsigned __int16 *, va_list)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140006688`
- `0x14000dc20`

## callees

- `0x140006770`
- `0x1400068fc`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1400067c0`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1400067c0`

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
0x140006770  push    rbx
0x140006772  push    rbp
0x140006773  push    rsi
0x140006774  push    rdi
0x140006775  sub     rsp, 38h
0x140006779  mov     rsi, r9
0x14000677c  mov     rbp, r8
0x14000677f  mov     rax, rdx
0x140006782  mov     rdi, rcx
0x140006785  test    rdx, rdx
0x140006788  jz      short loc_1400067ED
0x14000678a  cmp     rax, 7FFFFFFFh
0x140006790  jbe     short loc_140006799
0x140006792  mov     edx, 80070057h
0x140006797  jmp     short loc_1400067F7
0x140006799  lea     rbx, [rdx-1]
0x14000679d  call    __local_stdio_printf_options
0x1400067a2  mov     [rsp+58h+ArgList], rsi; ArgList
0x1400067a7  mov     r9, rbp; Format
0x1400067aa  mov     r8, rbx; BufferCount
0x1400067ad  mov     [rsp+58h+Locale], 0; Locale
0x1400067b6  mov     rdx, rdi; Buffer
0x1400067b9  mov     rcx, [rax]
0x1400067bc  or      rcx, 1; Options
0x1400067c0  call    cs:__imp___stdio_common_vswprintf
0x1400067c6  test    eax, eax
0x1400067c8  js      short loc_1400067E0
0x1400067ca  cdqe
0x1400067cc  cmp     rax, rbx
0x1400067cf  ja      short loc_1400067E0
0x1400067d1  xor     edx, edx
0x1400067d3  cmp     rax, rbx
0x1400067d6  jnz     short loc_1400067FC
0x1400067d8  xor     eax, eax
0x1400067da  mov     [rdi+rbx*2], ax
0x1400067de  jmp     short loc_1400067FC
0x1400067e0  xor     eax, eax
0x1400067e2  mov     edx, 8007007Ah
0x1400067e7  mov     [rdi+rbx*2], ax
0x1400067eb  jmp     short loc_1400067FC
0x1400067ed  mov     edx, 80070057h
0x1400067f2  test    rax, rax
0x1400067f5  jz      short loc_1400067FC
0x1400067f7  xor     ecx, ecx
0x1400067f9  mov     [rdi], cx
0x1400067fc  mov     eax, edx
0x1400067fe  add     rsp, 38h
0x140006802  pop     rdi
0x140006803  pop     rsi
0x140006804  pop     rbp
0x140006805  pop     rbx
0x140006806  retn
```
