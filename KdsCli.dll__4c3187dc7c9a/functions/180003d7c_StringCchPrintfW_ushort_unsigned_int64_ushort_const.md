# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180003d7c`
- end: `0x180003dff`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003160`
- `0x180009e04`
- `0x18001223c`
- `0x1800125e0`

## callees

- `0x180001f88`
- `0x180003d7c`

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
0x180003d7c  mov     [rsp+arg_10], r8
0x180003d81  mov     qword ptr [rsp+Args], r9
0x180003d86  push    rbx
0x180003d87  push    rdi
0x180003d88  sub     rsp, 38h
0x180003d8c  mov     rax, rdx
0x180003d8f  mov     rdi, rcx
0x180003d92  test    rdx, rdx
0x180003d95  jz      short loc_180003DE7
0x180003d97  cmp     rax, 7FFFFFFFh
0x180003d9d  jbe     short loc_180003DA6
0x180003d9f  mov     edx, 80070057h
0x180003da4  jmp     short loc_180003DF1
0x180003da6  lea     rbx, [rdx-1]
0x180003daa  mov     [rsp+48h+var_28], 0
0x180003db3  mov     rdx, rbx; BufferCount
0x180003db6  lea     r9, [rsp+48h+Args]; Args
0x180003dbb  call    _vsnwprintf
0x180003dc0  test    eax, eax
0x180003dc2  js      short loc_180003DDA
0x180003dc4  cdqe
0x180003dc6  cmp     rax, rbx
0x180003dc9  ja      short loc_180003DDA
0x180003dcb  xor     edx, edx
0x180003dcd  cmp     rax, rbx
0x180003dd0  jnz     short loc_180003DF6
0x180003dd2  xor     eax, eax
0x180003dd4  mov     [rdi+rbx*2], ax
0x180003dd8  jmp     short loc_180003DF6
0x180003dda  xor     eax, eax
0x180003ddc  mov     edx, 8007007Ah
0x180003de1  mov     [rdi+rbx*2], ax
0x180003de5  jmp     short loc_180003DF6
0x180003de7  mov     edx, 80070057h
0x180003dec  test    rax, rax
0x180003def  jz      short loc_180003DF6
0x180003df1  xor     ecx, ecx
0x180003df3  mov     [rdi], cx
0x180003df6  mov     eax, edx
0x180003df8  add     rsp, 38h
0x180003dfc  pop     rdi
0x180003dfd  pop     rbx
0x180003dfe  retn
```
