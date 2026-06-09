# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x1800064c4`
- end: `0x180006547`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `131`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x180003e88`
- `0x180007c8c`
- `0x18000ded8`
- `0x18000dfd0`
- `0x18000e104`
- `0x18000e16f`
- `0x18000e257`
- `0x18000e31a`
- `0x18000e376`
- `0x18000e3d2`
- `0x18000e4d4`
- `0x18000e597`
- `0x18000e5f3`
- `0x18000e64f`
- `0x18000e6ab`

## callees

- `0x180002ccc`
- `0x1800064c4`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, ...)
{
  unsigned int v4; // edx
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v5 = a2 - 1;
      v6 = vsnwprintf(a1, a2 - 1, a3, Args);
      if ( v6 < 0 || v6 > v5 )
      {
        v4 = -2147024774;
        a1[v5] = 0;
      }
      else
      {
        v4 = 0;
        if ( v6 == v5 )
          a1[v5] = 0;
      }
    }
    else
    {
      v4 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x1800064c4  mov     [rsp+arg_10], r8
0x1800064c9  mov     qword ptr [rsp+Args], r9
0x1800064ce  push    rbx
0x1800064cf  push    rdi
0x1800064d0  sub     rsp, 38h
0x1800064d4  mov     rax, rdx
0x1800064d7  mov     rdi, rcx
0x1800064da  test    rdx, rdx
0x1800064dd  jz      short loc_18000652F
0x1800064df  cmp     rax, 7FFFFFFFh
0x1800064e5  jbe     short loc_1800064EE
0x1800064e7  mov     edx, 80070057h
0x1800064ec  jmp     short loc_180006539
0x1800064ee  lea     rbx, [rdx-1]
0x1800064f2  mov     [rsp+48h+var_28], 0
0x1800064fb  mov     rdx, rbx; BufferCount
0x1800064fe  lea     r9, [rsp+48h+Args]; Args
0x180006503  call    _vsnwprintf
0x180006508  test    eax, eax
0x18000650a  js      short loc_180006522
0x18000650c  cdqe
0x18000650e  cmp     rax, rbx
0x180006511  ja      short loc_180006522
0x180006513  xor     edx, edx
0x180006515  cmp     rax, rbx
0x180006518  jnz     short loc_18000653E
0x18000651a  xor     eax, eax
0x18000651c  mov     [rdi+rbx*2], ax
0x180006520  jmp     short loc_18000653E
0x180006522  xor     eax, eax
0x180006524  mov     edx, 8007007Ah
0x180006529  mov     [rdi+rbx*2], ax
0x18000652d  jmp     short loc_18000653E
0x18000652f  mov     edx, 80070057h
0x180006534  test    rax, rax
0x180006537  jz      short loc_18000653E
0x180006539  xor     ecx, ecx
0x18000653b  mov     [rdi], cx
0x18000653e  mov     eax, edx
0x180006540  add     rsp, 38h
0x180006544  pop     rdi
0x180006545  pop     rbx
0x180006546  retn
```
