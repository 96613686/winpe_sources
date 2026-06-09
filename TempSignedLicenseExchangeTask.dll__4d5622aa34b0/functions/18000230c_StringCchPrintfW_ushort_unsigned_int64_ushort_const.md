# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000230c`
- end: `0x18000238f`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180002204`
- `0x180002900`
- `0x18000c5a0`

## callees

- `0x180001f78`
- `0x18000230c`

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
0x18000230c  mov     [rsp+arg_10], r8
0x180002311  mov     qword ptr [rsp+Args], r9
0x180002316  push    rbx
0x180002317  push    rdi
0x180002318  sub     rsp, 38h
0x18000231c  mov     rax, rdx
0x18000231f  mov     rdi, rcx
0x180002322  test    rdx, rdx
0x180002325  jz      short loc_180002377
0x180002327  cmp     rax, 7FFFFFFFh
0x18000232d  jbe     short loc_180002336
0x18000232f  mov     edx, 80070057h
0x180002334  jmp     short loc_180002381
0x180002336  lea     rbx, [rdx-1]
0x18000233a  mov     [rsp+48h+var_28], 0
0x180002343  mov     rdx, rbx; BufferCount
0x180002346  lea     r9, [rsp+48h+Args]; Args
0x18000234b  call    _vsnwprintf
0x180002350  test    eax, eax
0x180002352  js      short loc_18000236A
0x180002354  cdqe
0x180002356  cmp     rax, rbx
0x180002359  ja      short loc_18000236A
0x18000235b  xor     edx, edx
0x18000235d  cmp     rax, rbx
0x180002360  jnz     short loc_180002386
0x180002362  xor     eax, eax
0x180002364  mov     [rdi+rbx*2], ax
0x180002368  jmp     short loc_180002386
0x18000236a  xor     eax, eax
0x18000236c  mov     edx, 8007007Ah
0x180002371  mov     [rdi+rbx*2], ax
0x180002375  jmp     short loc_180002386
0x180002377  mov     edx, 80070057h
0x18000237c  test    rax, rax
0x18000237f  jz      short loc_180002386
0x180002381  xor     ecx, ecx
0x180002383  mov     [rdi], cx
0x180002386  mov     eax, edx
0x180002388  add     rsp, 38h
0x18000238c  pop     rdi
0x18000238d  pop     rbx
0x18000238e  retn
```
