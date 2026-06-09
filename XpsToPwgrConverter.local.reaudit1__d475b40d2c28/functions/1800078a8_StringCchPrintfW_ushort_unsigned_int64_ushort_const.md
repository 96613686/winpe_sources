# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800078a8`
- end: `0x18000792b`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x180003818`
- `0x180003bbc`
- `0x18000eb64`
- `0x18000f6a7`
- `0x18000f7d5`
- `0x18000f909`
- `0x18000f974`
- `0x1800100ed`
- `0x180010203`
- `0x18001025f`
- `0x1800102bb`
- `0x1800103bd`
- `0x1800104d3`
- `0x18001052f`
- `0x18001058b`
- `0x1800105e7`

## callees

- `0x1800021ac`
- `0x1800078a8`

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
0x1800078a8  mov     [rsp+arg_10], r8
0x1800078ad  mov     qword ptr [rsp+Args], r9
0x1800078b2  push    rbx
0x1800078b3  push    rdi
0x1800078b4  sub     rsp, 38h
0x1800078b8  mov     rax, rdx
0x1800078bb  mov     rdi, rcx
0x1800078be  test    rdx, rdx
0x1800078c1  jz      short loc_180007913
0x1800078c3  cmp     rax, 7FFFFFFFh
0x1800078c9  jbe     short loc_1800078D2
0x1800078cb  mov     edx, 80070057h
0x1800078d0  jmp     short loc_18000791D
0x1800078d2  lea     rbx, [rdx-1]
0x1800078d6  mov     [rsp+48h+var_28], 0
0x1800078df  mov     rdx, rbx; BufferCount
0x1800078e2  lea     r9, [rsp+48h+Args]; Args
0x1800078e7  call    _vsnwprintf
0x1800078ec  test    eax, eax
0x1800078ee  js      short loc_180007906
0x1800078f0  cdqe
0x1800078f2  cmp     rax, rbx
0x1800078f5  ja      short loc_180007906
0x1800078f7  xor     edx, edx
0x1800078f9  cmp     rax, rbx
0x1800078fc  jnz     short loc_180007922
0x1800078fe  xor     eax, eax
0x180007900  mov     [rdi+rbx*2], ax
0x180007904  jmp     short loc_180007922
0x180007906  xor     eax, eax
0x180007908  mov     edx, 8007007Ah
0x18000790d  mov     [rdi+rbx*2], ax
0x180007911  jmp     short loc_180007922
0x180007913  mov     edx, 80070057h
0x180007918  test    rax, rax
0x18000791b  jz      short loc_180007922
0x18000791d  xor     ecx, ecx
0x18000791f  mov     [rdi], cx
0x180007922  mov     eax, edx
0x180007924  add     rsp, 38h
0x180007928  pop     rdi
0x180007929  pop     rbx
0x18000792a  retn
```
