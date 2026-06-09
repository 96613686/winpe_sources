# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006850`
- end: `0x1800068d3`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800038c8`
- `0x180004490`
- `0x180007160`

## callees

- `0x180002660`
- `0x180006850`

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
0x180006850  mov     [rsp+arg_10], r8
0x180006855  mov     qword ptr [rsp+Args], r9
0x18000685a  push    rbx
0x18000685b  push    rdi
0x18000685c  sub     rsp, 38h
0x180006860  mov     rax, rdx
0x180006863  mov     rdi, rcx
0x180006866  test    rdx, rdx
0x180006869  jz      short loc_1800068BB
0x18000686b  cmp     rax, 7FFFFFFFh
0x180006871  jbe     short loc_18000687A
0x180006873  mov     edx, 80070057h
0x180006878  jmp     short loc_1800068C5
0x18000687a  lea     rbx, [rdx-1]
0x18000687e  mov     [rsp+48h+var_28], 0
0x180006887  mov     rdx, rbx; BufferCount
0x18000688a  lea     r9, [rsp+48h+Args]; Args
0x18000688f  call    _vsnwprintf
0x180006894  test    eax, eax
0x180006896  js      short loc_1800068AE
0x180006898  cdqe
0x18000689a  cmp     rax, rbx
0x18000689d  ja      short loc_1800068AE
0x18000689f  xor     edx, edx
0x1800068a1  cmp     rax, rbx
0x1800068a4  jnz     short loc_1800068CA
0x1800068a6  xor     eax, eax
0x1800068a8  mov     [rdi+rbx*2], ax
0x1800068ac  jmp     short loc_1800068CA
0x1800068ae  xor     eax, eax
0x1800068b0  mov     edx, 8007007Ah
0x1800068b5  mov     [rdi+rbx*2], ax
0x1800068b9  jmp     short loc_1800068CA
0x1800068bb  mov     edx, 80070057h
0x1800068c0  test    rax, rax
0x1800068c3  jz      short loc_1800068CA
0x1800068c5  xor     ecx, ecx
0x1800068c7  mov     [rdi], cx
0x1800068ca  mov     eax, edx
0x1800068cc  add     rsp, 38h
0x1800068d0  pop     rdi
0x1800068d1  pop     rbx
0x1800068d2  retn
```
