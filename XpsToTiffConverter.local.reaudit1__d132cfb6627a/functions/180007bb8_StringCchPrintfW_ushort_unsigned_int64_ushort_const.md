# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180007bb8`
- end: `0x180007c3b`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ab8`
- `0x180003e5c`
- `0x18000a384`
- `0x18000cca7`
- `0x18000cdd5`
- `0x18000cf09`
- `0x18000cf74`
- `0x18000d05c`
- `0x18000d172`
- `0x18000d1ce`
- `0x18000d22a`
- `0x18000d32c`
- `0x18000d442`
- `0x18000d49e`
- `0x18000d4fa`
- `0x18000d556`

## callees

- `0x1800020fc`
- `0x180007bb8`

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
0x180007bb8  mov     [rsp+arg_10], r8
0x180007bbd  mov     qword ptr [rsp+Args], r9
0x180007bc2  push    rbx
0x180007bc3  push    rdi
0x180007bc4  sub     rsp, 38h
0x180007bc8  mov     rax, rdx
0x180007bcb  mov     rdi, rcx
0x180007bce  test    rdx, rdx
0x180007bd1  jz      short loc_180007C23
0x180007bd3  cmp     rax, 7FFFFFFFh
0x180007bd9  jbe     short loc_180007BE2
0x180007bdb  mov     edx, 80070057h
0x180007be0  jmp     short loc_180007C2D
0x180007be2  lea     rbx, [rdx-1]
0x180007be6  mov     [rsp+48h+var_28], 0
0x180007bef  mov     rdx, rbx; BufferCount
0x180007bf2  lea     r9, [rsp+48h+Args]; Args
0x180007bf7  call    _vsnwprintf
0x180007bfc  test    eax, eax
0x180007bfe  js      short loc_180007C16
0x180007c00  cdqe
0x180007c02  cmp     rax, rbx
0x180007c05  ja      short loc_180007C16
0x180007c07  xor     edx, edx
0x180007c09  cmp     rax, rbx
0x180007c0c  jnz     short loc_180007C32
0x180007c0e  xor     eax, eax
0x180007c10  mov     [rdi+rbx*2], ax
0x180007c14  jmp     short loc_180007C32
0x180007c16  xor     eax, eax
0x180007c18  mov     edx, 8007007Ah
0x180007c1d  mov     [rdi+rbx*2], ax
0x180007c21  jmp     short loc_180007C32
0x180007c23  mov     edx, 80070057h
0x180007c28  test    rax, rax
0x180007c2b  jz      short loc_180007C32
0x180007c2d  xor     ecx, ecx
0x180007c2f  mov     [rdi], cx
0x180007c32  mov     eax, edx
0x180007c34  add     rsp, 38h
0x180007c38  pop     rdi
0x180007c39  pop     rbx
0x180007c3a  retn
```
