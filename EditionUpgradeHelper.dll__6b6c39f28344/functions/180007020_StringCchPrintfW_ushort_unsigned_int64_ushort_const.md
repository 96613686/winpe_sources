# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180007020`
- end: `0x1800070a3`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800036f4`
- `0x180003a98`
- `0x180009560`

## callees

- `0x1800024ec`
- `0x180007020`

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
0x180007020  mov     [rsp+arg_10], r8
0x180007025  mov     qword ptr [rsp+Args], r9
0x18000702a  push    rbx
0x18000702b  push    rdi
0x18000702c  sub     rsp, 38h
0x180007030  mov     rax, rdx
0x180007033  mov     rdi, rcx
0x180007036  test    rdx, rdx
0x180007039  jz      short loc_18000708B
0x18000703b  cmp     rax, 7FFFFFFFh
0x180007041  jbe     short loc_18000704A
0x180007043  mov     edx, 80070057h
0x180007048  jmp     short loc_180007095
0x18000704a  lea     rbx, [rdx-1]
0x18000704e  mov     [rsp+48h+var_28], 0
0x180007057  mov     rdx, rbx; BufferCount
0x18000705a  lea     r9, [rsp+48h+Args]; Args
0x18000705f  call    _vsnwprintf
0x180007064  test    eax, eax
0x180007066  js      short loc_18000707E
0x180007068  cdqe
0x18000706a  cmp     rax, rbx
0x18000706d  ja      short loc_18000707E
0x18000706f  xor     edx, edx
0x180007071  cmp     rax, rbx
0x180007074  jnz     short loc_18000709A
0x180007076  xor     eax, eax
0x180007078  mov     [rdi+rbx*2], ax
0x18000707c  jmp     short loc_18000709A
0x18000707e  xor     eax, eax
0x180007080  mov     edx, 8007007Ah
0x180007085  mov     [rdi+rbx*2], ax
0x180007089  jmp     short loc_18000709A
0x18000708b  mov     edx, 80070057h
0x180007090  test    rax, rax
0x180007093  jz      short loc_18000709A
0x180007095  xor     ecx, ecx
0x180007097  mov     [rdi], cx
0x18000709a  mov     eax, edx
0x18000709c  add     rsp, 38h
0x1800070a0  pop     rdi
0x1800070a1  pop     rbx
0x1800070a2  retn
```
