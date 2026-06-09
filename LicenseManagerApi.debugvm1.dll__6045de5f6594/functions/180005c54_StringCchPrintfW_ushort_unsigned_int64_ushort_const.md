# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180005c54`
- end: `0x180005cd7`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800037a8`
- `0x180011248`
- `0x180011e7a`
- `0x180011f72`
- `0x1800120a6`
- `0x180012111`

## callees

- `0x1800022f8`
- `0x180005c54`

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
0x180005c54  mov     [rsp+arg_10], r8
0x180005c59  mov     qword ptr [rsp+Args], r9
0x180005c5e  push    rbx
0x180005c5f  push    rdi
0x180005c60  sub     rsp, 38h
0x180005c64  mov     rax, rdx
0x180005c67  mov     rdi, rcx
0x180005c6a  test    rdx, rdx
0x180005c6d  jz      short loc_180005CBF
0x180005c6f  cmp     rax, 7FFFFFFFh
0x180005c75  jbe     short loc_180005C7E
0x180005c77  mov     edx, 80070057h
0x180005c7c  jmp     short loc_180005CC9
0x180005c7e  lea     rbx, [rdx-1]
0x180005c82  mov     [rsp+48h+var_28], 0
0x180005c8b  mov     rdx, rbx; BufferCount
0x180005c8e  lea     r9, [rsp+48h+Args]; Args
0x180005c93  call    _vsnwprintf
0x180005c98  test    eax, eax
0x180005c9a  js      short loc_180005CB2
0x180005c9c  cdqe
0x180005c9e  cmp     rax, rbx
0x180005ca1  ja      short loc_180005CB2
0x180005ca3  xor     edx, edx
0x180005ca5  cmp     rax, rbx
0x180005ca8  jnz     short loc_180005CCE
0x180005caa  xor     eax, eax
0x180005cac  mov     [rdi+rbx*2], ax
0x180005cb0  jmp     short loc_180005CCE
0x180005cb2  xor     eax, eax
0x180005cb4  mov     edx, 8007007Ah
0x180005cb9  mov     [rdi+rbx*2], ax
0x180005cbd  jmp     short loc_180005CCE
0x180005cbf  mov     edx, 80070057h
0x180005cc4  test    rax, rax
0x180005cc7  jz      short loc_180005CCE
0x180005cc9  xor     ecx, ecx
0x180005ccb  mov     [rdi], cx
0x180005cce  mov     eax, edx
0x180005cd0  add     rsp, 38h
0x180005cd4  pop     rdi
0x180005cd5  pop     rbx
0x180005cd6  retn
```
