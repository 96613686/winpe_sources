# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800056e4`
- end: `0x180005767`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180003168`
- `0x180007824`
- `0x18000a107`
- `0x18000a1ff`
- `0x18000a333`
- `0x18000a39e`

## callees

- `0x18000209c`
- `0x1800056e4`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
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
0x1800056e4  mov     [rsp+arg_10], r8
0x1800056e9  mov     qword ptr [rsp+Args], r9
0x1800056ee  push    rbx
0x1800056ef  push    rdi
0x1800056f0  sub     rsp, 38h
0x1800056f4  mov     rax, rdx
0x1800056f7  mov     rdi, rcx
0x1800056fa  test    rdx, rdx
0x1800056fd  jz      short loc_18000574F
0x1800056ff  cmp     rax, 7FFFFFFFh
0x180005705  jbe     short loc_18000570E
0x180005707  mov     edx, 80070057h
0x18000570c  jmp     short loc_180005759
0x18000570e  lea     rbx, [rdx-1]
0x180005712  mov     [rsp+48h+var_28], 0
0x18000571b  mov     rdx, rbx; BufferCount
0x18000571e  lea     r9, [rsp+48h+Args]; Args
0x180005723  call    _vsnwprintf
0x180005728  test    eax, eax
0x18000572a  js      short loc_180005742
0x18000572c  cdqe
0x18000572e  cmp     rax, rbx
0x180005731  ja      short loc_180005742
0x180005733  xor     edx, edx
0x180005735  cmp     rax, rbx
0x180005738  jnz     short loc_18000575E
0x18000573a  xor     eax, eax
0x18000573c  mov     [rdi+rbx*2], ax
0x180005740  jmp     short loc_18000575E
0x180005742  xor     eax, eax
0x180005744  mov     edx, 8007007Ah
0x180005749  mov     [rdi+rbx*2], ax
0x18000574d  jmp     short loc_18000575E
0x18000574f  mov     edx, 80070057h
0x180005754  test    rax, rax
0x180005757  jz      short loc_18000575E
0x180005759  xor     ecx, ecx
0x18000575b  mov     [rdi], cx
0x18000575e  mov     eax, edx
0x180005760  add     rsp, 38h
0x180005764  pop     rdi
0x180005765  pop     rbx
0x180005766  retn
```
