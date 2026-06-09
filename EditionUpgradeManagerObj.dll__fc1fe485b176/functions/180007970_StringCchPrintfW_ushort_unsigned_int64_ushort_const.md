# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180007970`
- end: `0x1800079f3`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180003bc4`
- `0x180003f94`
- `0x18000bb10`
- `0x18000c754`
- `0x18000d2ac`
- `0x18000d95c`
- `0x180013b8c`
- `0x180022088`
- `0x180022720`

## callees

- `0x1800026cc`
- `0x180007970`

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
0x180007970  mov     [rsp+arg_10], r8
0x180007975  mov     qword ptr [rsp+Args], r9
0x18000797a  push    rbx
0x18000797b  push    rdi
0x18000797c  sub     rsp, 38h
0x180007980  mov     rax, rdx
0x180007983  mov     rdi, rcx
0x180007986  test    rdx, rdx
0x180007989  jz      short loc_1800079DB
0x18000798b  cmp     rax, 7FFFFFFFh
0x180007991  jbe     short loc_18000799A
0x180007993  mov     edx, 80070057h
0x180007998  jmp     short loc_1800079E5
0x18000799a  lea     rbx, [rdx-1]
0x18000799e  mov     [rsp+48h+var_28], 0
0x1800079a7  mov     rdx, rbx; BufferCount
0x1800079aa  lea     r9, [rsp+48h+Args]; Args
0x1800079af  call    _vsnwprintf
0x1800079b4  test    eax, eax
0x1800079b6  js      short loc_1800079CE
0x1800079b8  cdqe
0x1800079ba  cmp     rax, rbx
0x1800079bd  ja      short loc_1800079CE
0x1800079bf  xor     edx, edx
0x1800079c1  cmp     rax, rbx
0x1800079c4  jnz     short loc_1800079EA
0x1800079c6  xor     eax, eax
0x1800079c8  mov     [rdi+rbx*2], ax
0x1800079cc  jmp     short loc_1800079EA
0x1800079ce  xor     eax, eax
0x1800079d0  mov     edx, 8007007Ah
0x1800079d5  mov     [rdi+rbx*2], ax
0x1800079d9  jmp     short loc_1800079EA
0x1800079db  mov     edx, 80070057h
0x1800079e0  test    rax, rax
0x1800079e3  jz      short loc_1800079EA
0x1800079e5  xor     ecx, ecx
0x1800079e7  mov     [rdi], cx
0x1800079ea  mov     eax, edx
0x1800079ec  add     rsp, 38h
0x1800079f0  pop     rdi
0x1800079f1  pop     rbx
0x1800079f2  retn
```
