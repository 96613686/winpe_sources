# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006100`
- end: `0x180006183`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180003c14`
- `0x18000af60`
- `0x18000b2dc`
- `0x18000b5a4`
- `0x18000c060`
- `0x18000e9fc`
- `0x18000eaf4`
- `0x18000ec28`
- `0x18000ec93`

## callees

- `0x18000281c`
- `0x180006100`

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
0x180006100  mov     [rsp+arg_10], r8
0x180006105  mov     qword ptr [rsp+Args], r9
0x18000610a  push    rbx
0x18000610b  push    rdi
0x18000610c  sub     rsp, 38h
0x180006110  mov     rax, rdx
0x180006113  mov     rdi, rcx
0x180006116  test    rdx, rdx
0x180006119  jz      short loc_18000616B
0x18000611b  cmp     rax, 7FFFFFFFh
0x180006121  jbe     short loc_18000612A
0x180006123  mov     edx, 80070057h
0x180006128  jmp     short loc_180006175
0x18000612a  lea     rbx, [rdx-1]
0x18000612e  mov     [rsp+48h+var_28], 0
0x180006137  mov     rdx, rbx; BufferCount
0x18000613a  lea     r9, [rsp+48h+Args]; Args
0x18000613f  call    _vsnwprintf
0x180006144  test    eax, eax
0x180006146  js      short loc_18000615E
0x180006148  cdqe
0x18000614a  cmp     rax, rbx
0x18000614d  ja      short loc_18000615E
0x18000614f  xor     edx, edx
0x180006151  cmp     rax, rbx
0x180006154  jnz     short loc_18000617A
0x180006156  xor     eax, eax
0x180006158  mov     [rdi+rbx*2], ax
0x18000615c  jmp     short loc_18000617A
0x18000615e  xor     eax, eax
0x180006160  mov     edx, 8007007Ah
0x180006165  mov     [rdi+rbx*2], ax
0x180006169  jmp     short loc_18000617A
0x18000616b  mov     edx, 80070057h
0x180006170  test    rax, rax
0x180006173  jz      short loc_18000617A
0x180006175  xor     ecx, ecx
0x180006177  mov     [rdi], cx
0x18000617a  mov     eax, edx
0x18000617c  add     rsp, 38h
0x180006180  pop     rdi
0x180006181  pop     rbx
0x180006182  retn
```
