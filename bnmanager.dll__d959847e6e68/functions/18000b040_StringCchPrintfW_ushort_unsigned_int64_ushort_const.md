# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000b040`
- end: `0x18000b0c3`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ad8`
- `0x180005e7c`
- `0x1800062e0`

## callees

- `0x1800022c0`
- `0x18000b040`

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
0x18000b040  mov     [rsp+arg_10], r8
0x18000b045  mov     qword ptr [rsp+Args], r9
0x18000b04a  push    rbx
0x18000b04b  push    rdi
0x18000b04c  sub     rsp, 38h
0x18000b050  mov     rax, rdx
0x18000b053  mov     rdi, rcx
0x18000b056  test    rdx, rdx
0x18000b059  jz      short loc_18000B0AB
0x18000b05b  cmp     rax, 7FFFFFFFh
0x18000b061  jbe     short loc_18000B06A
0x18000b063  mov     edx, 80070057h
0x18000b068  jmp     short loc_18000B0B5
0x18000b06a  lea     rbx, [rdx-1]
0x18000b06e  mov     [rsp+48h+var_28], 0
0x18000b077  mov     rdx, rbx; BufferCount
0x18000b07a  lea     r9, [rsp+48h+Args]; Args
0x18000b07f  call    _vsnwprintf
0x18000b084  test    eax, eax
0x18000b086  js      short loc_18000B09E
0x18000b088  cdqe
0x18000b08a  cmp     rax, rbx
0x18000b08d  ja      short loc_18000B09E
0x18000b08f  xor     edx, edx
0x18000b091  cmp     rax, rbx
0x18000b094  jnz     short loc_18000B0BA
0x18000b096  xor     eax, eax
0x18000b098  mov     [rdi+rbx*2], ax
0x18000b09c  jmp     short loc_18000B0BA
0x18000b09e  xor     eax, eax
0x18000b0a0  mov     edx, 8007007Ah
0x18000b0a5  mov     [rdi+rbx*2], ax
0x18000b0a9  jmp     short loc_18000B0BA
0x18000b0ab  mov     edx, 80070057h
0x18000b0b0  test    rax, rax
0x18000b0b3  jz      short loc_18000B0BA
0x18000b0b5  xor     ecx, ecx
0x18000b0b7  mov     [rdi], cx
0x18000b0ba  mov     eax, edx
0x18000b0bc  add     rsp, 38h
0x18000b0c0  pop     rdi
0x18000b0c1  pop     rbx
0x18000b0c2  retn
```
