# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800053c8`
- end: `0x180005426`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `94`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800031e4`
- `0x1800035b4`
- `0x180004880`
- `0x180008318`
- `0x180008680`
- `0x180008b50`
- `0x180008bc0`

## callees

- `0x1800053c8`
- `0x180005484`

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
0x1800053c8  mov     [rsp+arg_10], r8
0x1800053cd  mov     qword ptr [rsp+arg_18], r9
0x1800053d2  sub     rsp, 48h
0x1800053d6  mov     rax, rdx
0x1800053d9  test    rdx, rdx
0x1800053dc  jz      short loc_18000540F
0x1800053de  cmp     rax, 7FFFFFFFh
0x1800053e4  jbe     short loc_1800053ED
0x1800053e6  mov     edx, 80070057h
0x1800053eb  jmp     short loc_180005419
0x1800053ed  lea     rdx, [rsp+48h+arg_18]
0x1800053f2  mov     [rsp+48h+var_18], 0
0x1800053fb  mov     [rsp+48h+argList], rdx; argList
0x180005400  mov     r9, r8; pszFormat
0x180005403  mov     rdx, rax; cchDest
0x180005406  call    StringVPrintfWorkerW
0x18000540b  mov     edx, eax
0x18000540d  jmp     short loc_18000541E
0x18000540f  mov     edx, 80070057h
0x180005414  test    rax, rax
0x180005417  jz      short loc_18000541E
0x180005419  xor     eax, eax
0x18000541b  mov     [rcx], ax
0x18000541e  mov     eax, edx
0x180005420  add     rsp, 48h
0x180005424  retn
```
