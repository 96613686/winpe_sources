# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180001fd4`
- end: `0x180002057`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002520`
- `0x180002e50`

## callees

- `0x180001d38`
- `0x180001fd4`

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
0x180001fd4  mov     [rsp+arg_10], r8
0x180001fd9  mov     qword ptr [rsp+Args], r9
0x180001fde  push    rbx
0x180001fdf  push    rdi
0x180001fe0  sub     rsp, 38h
0x180001fe4  mov     rax, rdx
0x180001fe7  mov     rdi, rcx
0x180001fea  test    rdx, rdx
0x180001fed  jz      short loc_18000203F
0x180001fef  cmp     rax, 7FFFFFFFh
0x180001ff5  jbe     short loc_180001FFE
0x180001ff7  mov     edx, 80070057h
0x180001ffc  jmp     short loc_180002049
0x180001ffe  lea     rbx, [rdx-1]
0x180002002  mov     [rsp+48h+var_28], 0
0x18000200b  mov     rdx, rbx; BufferCount
0x18000200e  lea     r9, [rsp+48h+Args]; Args
0x180002013  call    _vsnwprintf
0x180002018  test    eax, eax
0x18000201a  js      short loc_180002032
0x18000201c  cdqe
0x18000201e  cmp     rax, rbx
0x180002021  ja      short loc_180002032
0x180002023  xor     edx, edx
0x180002025  cmp     rax, rbx
0x180002028  jnz     short loc_18000204E
0x18000202a  xor     eax, eax
0x18000202c  mov     [rdi+rbx*2], ax
0x180002030  jmp     short loc_18000204E
0x180002032  xor     eax, eax
0x180002034  mov     edx, 8007007Ah
0x180002039  mov     [rdi+rbx*2], ax
0x18000203d  jmp     short loc_18000204E
0x18000203f  mov     edx, 80070057h
0x180002044  test    rax, rax
0x180002047  jz      short loc_18000204E
0x180002049  xor     ecx, ecx
0x18000204b  mov     [rdi], cx
0x18000204e  mov     eax, edx
0x180002050  add     rsp, 38h
0x180002054  pop     rdi
0x180002055  pop     rbx
0x180002056  retn
```
