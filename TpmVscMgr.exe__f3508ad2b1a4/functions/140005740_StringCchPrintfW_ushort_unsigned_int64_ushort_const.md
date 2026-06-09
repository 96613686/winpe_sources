# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140005740`
- end: `0x1400057c3`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140003258`
- `0x1400097c0`
- `0x14001160f`
- `0x140011707`
- `0x14001183b`
- `0x1400118a6`

## callees

- `0x140002470`
- `0x140005740`

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
0x140005740  mov     [rsp+arg_10], r8
0x140005745  mov     qword ptr [rsp+Args], r9
0x14000574a  push    rbx
0x14000574b  push    rdi
0x14000574c  sub     rsp, 38h
0x140005750  mov     rax, rdx
0x140005753  mov     rdi, rcx
0x140005756  test    rdx, rdx
0x140005759  jz      short loc_1400057AB
0x14000575b  cmp     rax, 7FFFFFFFh
0x140005761  jbe     short loc_14000576A
0x140005763  mov     edx, 80070057h
0x140005768  jmp     short loc_1400057B5
0x14000576a  lea     rbx, [rdx-1]
0x14000576e  mov     [rsp+48h+var_28], 0
0x140005777  mov     rdx, rbx; BufferCount
0x14000577a  lea     r9, [rsp+48h+Args]; Args
0x14000577f  call    _vsnwprintf
0x140005784  test    eax, eax
0x140005786  js      short loc_14000579E
0x140005788  cdqe
0x14000578a  cmp     rax, rbx
0x14000578d  ja      short loc_14000579E
0x14000578f  xor     edx, edx
0x140005791  cmp     rax, rbx
0x140005794  jnz     short loc_1400057BA
0x140005796  xor     eax, eax
0x140005798  mov     [rdi+rbx*2], ax
0x14000579c  jmp     short loc_1400057BA
0x14000579e  xor     eax, eax
0x1400057a0  mov     edx, 8007007Ah
0x1400057a5  mov     [rdi+rbx*2], ax
0x1400057a9  jmp     short loc_1400057BA
0x1400057ab  mov     edx, 80070057h
0x1400057b0  test    rax, rax
0x1400057b3  jz      short loc_1400057BA
0x1400057b5  xor     ecx, ecx
0x1400057b7  mov     [rdi], cx
0x1400057ba  mov     eax, edx
0x1400057bc  add     rsp, 38h
0x1400057c0  pop     rdi
0x1400057c1  pop     rbx
0x1400057c2  retn
```
