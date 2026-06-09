# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180007404`
- end: `0x1800074b2`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `174`
- prototype: `__int64(wchar_t *Buffer, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800048d8`
- `0x180009dec`
- `0x18000e660`
- `0x180013690`
- `0x1800162a0`
- `0x18002879c`

## callees

- `0x180007404`
- `0x180007c68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf` at `0x18000746b`
- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf` at `0x18000746b`

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
0x180007404  mov     [rsp+arg_10], r8
0x180007409  mov     qword ptr [rsp+arg_18], r9
0x18000740e  push    rbx
0x18000740f  push    rbp
0x180007410  push    rsi
0x180007411  push    rdi
0x180007412  sub     rsp, 48h
0x180007416  mov     rsi, r8
0x180007419  mov     rax, rdx
0x18000741c  mov     rdi, rcx
0x18000741f  test    rdx, rdx
0x180007422  jz      short loc_180007498
0x180007424  cmp     rax, 7FFFFFFFh
0x18000742a  jbe     short loc_180007433
0x18000742c  mov     edx, 80070057h
0x180007431  jmp     short loc_1800074A2
0x180007433  mov     [rsp+68h+var_38], 0
0x18000743c  lea     rbp, [rsp+68h+arg_18]
0x180007444  lea     rbx, [rdx-1]
0x180007448  call    __local_stdio_printf_options
0x18000744d  mov     [rsp+68h+ArgList], rbp; ArgList
0x180007452  mov     r9, rsi; Format
0x180007455  mov     r8, rbx; BufferCount
0x180007458  mov     [rsp+68h+Locale], 0; Locale
0x180007461  mov     rdx, rdi; Buffer
0x180007464  mov     rcx, [rax]
0x180007467  or      rcx, 1; Options
0x18000746b  call    cs:__imp___stdio_common_vswprintf
0x180007471  test    eax, eax
0x180007473  js      short loc_18000748B
0x180007475  cdqe
0x180007477  cmp     rax, rbx
0x18000747a  ja      short loc_18000748B
0x18000747c  xor     edx, edx
0x18000747e  cmp     rax, rbx
0x180007481  jnz     short loc_1800074A7
0x180007483  xor     eax, eax
0x180007485  mov     [rdi+rbx*2], ax
0x180007489  jmp     short loc_1800074A7
0x18000748b  xor     eax, eax
0x18000748d  mov     edx, 8007007Ah
0x180007492  mov     [rdi+rbx*2], ax
0x180007496  jmp     short loc_1800074A7
0x180007498  mov     edx, 80070057h
0x18000749d  test    rax, rax
0x1800074a0  jz      short loc_1800074A7
0x1800074a2  xor     ecx, ecx
0x1800074a4  mov     [rdi], cx
0x1800074a7  mov     eax, edx
0x1800074a9  add     rsp, 48h
0x1800074ad  pop     rdi
0x1800074ae  pop     rsi
0x1800074af  pop     rbp
0x1800074b0  pop     rbx
0x1800074b1  retn
```
