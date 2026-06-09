# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140007368`
- end: `0x1400073c5`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `93`
- prototype: `__int64(unsigned __int16 *, size_t, size_t *, ...)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x140004d88`
- `0x140005888`
- `0x140006478`
- `0x140009414`
- `0x140009d3c`
- `0x140009f10`
- `0x14000bdc4`
- `0x14000d0fc`
- `0x14000dca0`
- `0x14000e200`
- `0x14000e530`
- `0x14000ee6c`
- `0x14000ef04`
- `0x14000f1f8`
- `0x140012bd0`
- `0x14001464c`
- `0x140015b98`

## callees

- `0x140007368`
- `0x140007424`

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
0x140007368  mov     [rsp+arg_10], r8
0x14000736d  mov     qword ptr [rsp+arg_18], r9
0x140007372  sub     rsp, 48h
0x140007376  mov     rax, rdx
0x140007379  test    rdx, rdx
0x14000737c  jz      short loc_1400073AF
0x14000737e  cmp     rax, 7FFFFFFFh
0x140007384  jbe     short loc_14000738D
0x140007386  mov     edx, 80070057h
0x14000738b  jmp     short loc_1400073B9
0x14000738d  lea     rdx, [rsp+48h+arg_18]
0x140007392  mov     [rsp+48h+var_18], 0
0x14000739b  mov     [rsp+48h+argList], rdx; argList
0x1400073a0  mov     r9, r8; pszFormat
0x1400073a3  mov     rdx, rax; cchDest
0x1400073a6  call    StringVPrintfWorkerW
0x1400073ab  mov     edx, eax
0x1400073ad  jmp     short loc_1400073BE
0x1400073af  mov     edx, 80070057h
0x1400073b4  test    rax, rax
0x1400073b7  jz      short loc_1400073BE
0x1400073b9  xor     eax, eax
0x1400073bb  mov     [rcx], ax
0x1400073be  mov     eax, edx
0x1400073c0  add     rsp, 48h
0x1400073c4  retn
```
