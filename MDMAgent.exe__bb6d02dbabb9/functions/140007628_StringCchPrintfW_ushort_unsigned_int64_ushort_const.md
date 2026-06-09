# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140007628`
- end: `0x140007686`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `94`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x140004e2c`
- `0x140005a44`
- `0x1400066a0`
- `0x140009804`
- `0x14000a1a0`
- `0x14000a374`
- `0x14000c314`
- `0x14000d780`
- `0x14000e3a4`
- `0x14000e934`
- `0x14000ec7c`
- `0x14000f604`
- `0x14000f69c`
- `0x14000f9a4`
- `0x14001351c`
- `0x1400151d8`
- `0x140016808`

## callees

- `0x140007628`
- `0x1400076e4`

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
0x140007628  mov     [rsp+arg_10], r8
0x14000762d  mov     qword ptr [rsp+arg_18], r9
0x140007632  sub     rsp, 48h
0x140007636  mov     rax, rdx
0x140007639  test    rdx, rdx
0x14000763c  jz      short loc_14000766F
0x14000763e  cmp     rax, 7FFFFFFFh
0x140007644  jbe     short loc_14000764D
0x140007646  mov     edx, 80070057h
0x14000764b  jmp     short loc_140007679
0x14000764d  lea     rdx, [rsp+48h+arg_18]
0x140007652  mov     [rsp+48h+var_18], 0
0x14000765b  mov     [rsp+48h+argList], rdx; argList
0x140007660  mov     r9, r8; pszFormat
0x140007663  mov     rdx, rax; cchDest
0x140007666  call    StringVPrintfWorkerW
0x14000766b  mov     edx, eax
0x14000766d  jmp     short loc_14000767E
0x14000766f  mov     edx, 80070057h
0x140007674  test    rax, rax
0x140007677  jz      short loc_14000767E
0x140007679  xor     eax, eax
0x14000767b  mov     [rcx], ax
0x14000767e  mov     eax, edx
0x140007680  add     rsp, 48h
0x140007684  retn
```
