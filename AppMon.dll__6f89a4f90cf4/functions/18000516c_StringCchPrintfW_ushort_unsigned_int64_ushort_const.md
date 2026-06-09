# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000516c`
- end: `0x1800051c9`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `93`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800032f8`
- `0x180004658`
- `0x180005f98`
- `0x18000e0e4`

## callees

- `0x18000516c`
- `0x180005270`

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
0x18000516c  mov     [rsp+arg_10], r8
0x180005171  mov     qword ptr [rsp+arg_18], r9
0x180005176  sub     rsp, 48h
0x18000517a  mov     rax, rdx
0x18000517d  test    rdx, rdx
0x180005180  jz      short loc_1800051B3
0x180005182  cmp     rax, 7FFFFFFFh
0x180005188  jbe     short loc_180005191
0x18000518a  mov     edx, 80070057h
0x18000518f  jmp     short loc_1800051BD
0x180005191  lea     rdx, [rsp+48h+arg_18]
0x180005196  mov     [rsp+48h+var_18], 0
0x18000519f  mov     [rsp+48h+argList], rdx; argList
0x1800051a4  mov     r9, r8; pszFormat
0x1800051a7  mov     rdx, rax; cchDest
0x1800051aa  call    StringVPrintfWorkerW
0x1800051af  mov     edx, eax
0x1800051b1  jmp     short loc_1800051C2
0x1800051b3  mov     edx, 80070057h
0x1800051b8  test    rax, rax
0x1800051bb  jz      short loc_1800051C2
0x1800051bd  xor     eax, eax
0x1800051bf  mov     [rcx], ax
0x1800051c2  mov     eax, edx
0x1800051c4  add     rsp, 48h
0x1800051c8  retn
```
