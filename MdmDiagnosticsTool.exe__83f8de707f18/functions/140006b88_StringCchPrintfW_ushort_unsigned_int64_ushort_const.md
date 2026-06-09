# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140006b88`
- end: `0x140006be6`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `94`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003874`
- `0x140005ac0`
- `0x140008694`

## callees

- `0x140006b88`
- `0x140006c44`

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
0x140006b88  mov     [rsp+arg_10], r8
0x140006b8d  mov     qword ptr [rsp+arg_18], r9
0x140006b92  sub     rsp, 48h
0x140006b96  mov     rax, rdx
0x140006b99  test    rdx, rdx
0x140006b9c  jz      short loc_140006BCF
0x140006b9e  cmp     rax, 7FFFFFFFh
0x140006ba4  jbe     short loc_140006BAD
0x140006ba6  mov     edx, 80070057h
0x140006bab  jmp     short loc_140006BD9
0x140006bad  lea     rdx, [rsp+48h+arg_18]
0x140006bb2  mov     [rsp+48h+var_18], 0
0x140006bbb  mov     [rsp+48h+argList], rdx; argList
0x140006bc0  mov     r9, r8; pszFormat
0x140006bc3  mov     rdx, rax; cchDest
0x140006bc6  call    StringVPrintfWorkerW
0x140006bcb  mov     edx, eax
0x140006bcd  jmp     short loc_140006BDE
0x140006bcf  mov     edx, 80070057h
0x140006bd4  test    rax, rax
0x140006bd7  jz      short loc_140006BDE
0x140006bd9  xor     eax, eax
0x140006bdb  mov     [rcx], ax
0x140006bde  mov     eax, edx
0x140006be0  add     rsp, 48h
0x140006be4  retn
```
