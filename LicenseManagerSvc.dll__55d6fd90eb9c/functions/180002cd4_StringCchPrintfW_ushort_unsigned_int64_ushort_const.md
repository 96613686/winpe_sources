# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180002cd4`
- end: `0x180002d31`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `93`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000279c`
- `0x1800066c8`
- `0x180008344`
- `0x18000c0a0`

## callees

- `0x180002cd4`
- `0x180007280`

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
0x180002cd4  mov     [rsp+arg_10], r8
0x180002cd9  mov     qword ptr [rsp+arg_18], r9
0x180002cde  sub     rsp, 48h
0x180002ce2  mov     rax, rdx
0x180002ce5  test    rdx, rdx
0x180002ce8  jz      short loc_180002D1B
0x180002cea  cmp     rax, 7FFFFFFFh
0x180002cf0  jbe     short loc_180002CF9
0x180002cf2  mov     edx, 80070057h
0x180002cf7  jmp     short loc_180002D25
0x180002cf9  lea     rdx, [rsp+48h+arg_18]
0x180002cfe  mov     [rsp+48h+var_18], 0
0x180002d07  mov     [rsp+48h+argList], rdx; argList
0x180002d0c  mov     r9, r8; pszFormat
0x180002d0f  mov     rdx, rax; cchDest
0x180002d12  call    StringVPrintfWorkerW
0x180002d17  mov     edx, eax
0x180002d19  jmp     short loc_180002D2A
0x180002d1b  mov     edx, 80070057h
0x180002d20  test    rax, rax
0x180002d23  jz      short loc_180002D2A
0x180002d25  xor     eax, eax
0x180002d27  mov     [rcx], ax
0x180002d2a  mov     eax, edx
0x180002d2c  add     rsp, 48h
0x180002d30  retn
```
