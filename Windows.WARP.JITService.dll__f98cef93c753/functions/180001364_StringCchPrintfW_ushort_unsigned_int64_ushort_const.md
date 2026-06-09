# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180001364`
- end: `0x1800013e7`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003924`
- `0x180005b00`
- `0x180007f2c`

## callees

- `0x180001364`
- `0x180009428`

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
0x180001364  mov     [rsp+arg_10], r8
0x180001369  mov     qword ptr [rsp+Args], r9
0x18000136e  push    rbx
0x18000136f  push    rdi
0x180001370  sub     rsp, 38h
0x180001374  mov     rax, rdx
0x180001377  mov     rdi, rcx
0x18000137a  test    rdx, rdx
0x18000137d  jz      short loc_1800013CF
0x18000137f  cmp     rax, 7FFFFFFFh
0x180001385  jbe     short loc_18000138E
0x180001387  mov     edx, 80070057h
0x18000138c  jmp     short loc_1800013D9
0x18000138e  lea     rbx, [rdx-1]
0x180001392  mov     [rsp+48h+var_28], 0
0x18000139b  mov     rdx, rbx; BufferCount
0x18000139e  lea     r9, [rsp+48h+Args]; Args
0x1800013a3  call    _vsnwprintf
0x1800013a8  test    eax, eax
0x1800013aa  js      short loc_1800013C2
0x1800013ac  cdqe
0x1800013ae  cmp     rax, rbx
0x1800013b1  ja      short loc_1800013C2
0x1800013b3  xor     edx, edx
0x1800013b5  cmp     rax, rbx
0x1800013b8  jnz     short loc_1800013DE
0x1800013ba  xor     eax, eax
0x1800013bc  mov     [rdi+rbx*2], ax
0x1800013c0  jmp     short loc_1800013DE
0x1800013c2  xor     eax, eax
0x1800013c4  mov     edx, 8007007Ah
0x1800013c9  mov     [rdi+rbx*2], ax
0x1800013cd  jmp     short loc_1800013DE
0x1800013cf  mov     edx, 80070057h
0x1800013d4  test    rax, rax
0x1800013d7  jz      short loc_1800013DE
0x1800013d9  xor     ecx, ecx
0x1800013db  mov     [rdi], cx
0x1800013de  mov     eax, edx
0x1800013e0  add     rsp, 38h
0x1800013e4  pop     rdi
0x1800013e5  pop     rbx
0x1800013e6  retn
```
