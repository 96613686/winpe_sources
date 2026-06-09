# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1400052c8`
- end: `0x140005325`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `93`
- prototype: `__int64(unsigned __int16 *, size_t, size_t *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003440`
- `0x140004860`
- `0x140008010`

## callees

- `0x1400052c8`
- `0x140005384`

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
0x1400052c8  mov     [rsp+arg_10], r8
0x1400052cd  mov     qword ptr [rsp+arg_18], r9
0x1400052d2  sub     rsp, 48h
0x1400052d6  mov     rax, rdx
0x1400052d9  test    rdx, rdx
0x1400052dc  jz      short loc_14000530F
0x1400052de  cmp     rax, 7FFFFFFFh
0x1400052e4  jbe     short loc_1400052ED
0x1400052e6  mov     edx, 80070057h
0x1400052eb  jmp     short loc_140005319
0x1400052ed  lea     rdx, [rsp+48h+arg_18]
0x1400052f2  mov     [rsp+48h+var_18], 0
0x1400052fb  mov     [rsp+48h+argList], rdx; argList
0x140005300  mov     r9, r8; pszFormat
0x140005303  mov     rdx, rax; cchDest
0x140005306  call    StringVPrintfWorkerW
0x14000530b  mov     edx, eax
0x14000530d  jmp     short loc_14000531E
0x14000530f  mov     edx, 80070057h
0x140005314  test    rax, rax
0x140005317  jz      short loc_14000531E
0x140005319  xor     eax, eax
0x14000531b  mov     [rcx], ax
0x14000531e  mov     eax, edx
0x140005320  add     rsp, 48h
0x140005324  retn
```
