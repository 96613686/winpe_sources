# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1400067b8`
- end: `0x140006815`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `93`
- prototype: `__int64(unsigned __int16 *, size_t, size_t *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400037d0`
- `0x1400057d4`
- `0x140008130`

## callees

- `0x1400067b8`
- `0x140006874`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, size_t a2, size_t *a3, ...)
{
  unsigned int v3; // edx
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringVPrintfWorkerW(a1, a2, a3, (STRSAFE_LPCWSTR)a3, va);
    }
    else
    {
      v3 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x1400067b8  mov     [rsp+arg_10], r8
0x1400067bd  mov     qword ptr [rsp+arg_18], r9
0x1400067c2  sub     rsp, 48h
0x1400067c6  mov     rax, rdx
0x1400067c9  test    rdx, rdx
0x1400067cc  jz      short loc_1400067FF
0x1400067ce  cmp     rax, 7FFFFFFFh
0x1400067d4  jbe     short loc_1400067DD
0x1400067d6  mov     edx, 80070057h
0x1400067db  jmp     short loc_140006809
0x1400067dd  lea     rdx, [rsp+48h+arg_18]
0x1400067e2  mov     [rsp+48h+var_18], 0
0x1400067eb  mov     [rsp+48h+argList], rdx; argList
0x1400067f0  mov     r9, r8; pszFormat
0x1400067f3  mov     rdx, rax; cchDest
0x1400067f6  call    StringVPrintfWorkerW
0x1400067fb  mov     edx, eax
0x1400067fd  jmp     short loc_14000680E
0x1400067ff  mov     edx, 80070057h
0x140006804  test    rax, rax
0x140006807  jz      short loc_14000680E
0x140006809  xor     eax, eax
0x14000680b  mov     [rcx], ax
0x14000680e  mov     eax, edx
0x140006810  add     rsp, 48h
0x140006814  retn
```
