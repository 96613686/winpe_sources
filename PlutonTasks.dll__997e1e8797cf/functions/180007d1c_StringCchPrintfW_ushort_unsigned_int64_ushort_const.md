# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180007d1c`
- end: `0x180007d79`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `93`
- prototype: `__int64(unsigned __int16 *, size_t, size_t *, ...)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d18`
- `0x180003e80`
- `0x1800044f8`
- `0x1800046e4`
- `0x18000622c`

## callees

- `0x180007d1c`
- `0x180007e20`

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
0x180007d1c  mov     [rsp+arg_10], r8
0x180007d21  mov     qword ptr [rsp+arg_18], r9
0x180007d26  sub     rsp, 48h
0x180007d2a  mov     rax, rdx
0x180007d2d  test    rdx, rdx
0x180007d30  jz      short loc_180007D63
0x180007d32  cmp     rax, 7FFFFFFFh
0x180007d38  jbe     short loc_180007D41
0x180007d3a  mov     edx, 80070057h
0x180007d3f  jmp     short loc_180007D6D
0x180007d41  lea     rdx, [rsp+48h+arg_18]
0x180007d46  mov     [rsp+48h+var_18], 0
0x180007d4f  mov     [rsp+48h+argList], rdx; argList
0x180007d54  mov     r9, r8; pszFormat
0x180007d57  mov     rdx, rax; cchDest
0x180007d5a  call    StringVPrintfWorkerW
0x180007d5f  mov     edx, eax
0x180007d61  jmp     short loc_180007D72
0x180007d63  mov     edx, 80070057h
0x180007d68  test    rax, rax
0x180007d6b  jz      short loc_180007D72
0x180007d6d  xor     eax, eax
0x180007d6f  mov     [rcx], ax
0x180007d72  mov     eax, edx
0x180007d74  add     rsp, 48h
0x180007d78  retn
```
