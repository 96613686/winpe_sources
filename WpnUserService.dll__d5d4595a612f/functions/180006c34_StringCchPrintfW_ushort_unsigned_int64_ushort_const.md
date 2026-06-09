# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006c34`
- end: `0x180006cb7`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800045b8`
- `0x18000896c`
- `0x18000a598`
- `0x180010d36`
- `0x180010e2e`
- `0x180010f62`
- `0x180010fcd`

## callees

- `0x180003558`
- `0x180006c34`

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
0x180006c34  mov     [rsp+arg_10], r8
0x180006c39  mov     qword ptr [rsp+Args], r9
0x180006c3e  push    rbx
0x180006c3f  push    rdi
0x180006c40  sub     rsp, 38h
0x180006c44  mov     rax, rdx
0x180006c47  mov     rdi, rcx
0x180006c4a  test    rdx, rdx
0x180006c4d  jz      short loc_180006C9F
0x180006c4f  cmp     rax, 7FFFFFFFh
0x180006c55  jbe     short loc_180006C5E
0x180006c57  mov     edx, 80070057h
0x180006c5c  jmp     short loc_180006CA9
0x180006c5e  lea     rbx, [rdx-1]
0x180006c62  mov     [rsp+48h+var_28], 0
0x180006c6b  mov     rdx, rbx; BufferCount
0x180006c6e  lea     r9, [rsp+48h+Args]; Args
0x180006c73  call    _vsnwprintf
0x180006c78  test    eax, eax
0x180006c7a  js      short loc_180006C92
0x180006c7c  cdqe
0x180006c7e  cmp     rax, rbx
0x180006c81  ja      short loc_180006C92
0x180006c83  xor     edx, edx
0x180006c85  cmp     rax, rbx
0x180006c88  jnz     short loc_180006CAE
0x180006c8a  xor     eax, eax
0x180006c8c  mov     [rdi+rbx*2], ax
0x180006c90  jmp     short loc_180006CAE
0x180006c92  xor     eax, eax
0x180006c94  mov     edx, 8007007Ah
0x180006c99  mov     [rdi+rbx*2], ax
0x180006c9d  jmp     short loc_180006CAE
0x180006c9f  mov     edx, 80070057h
0x180006ca4  test    rax, rax
0x180006ca7  jz      short loc_180006CAE
0x180006ca9  xor     ecx, ecx
0x180006cab  mov     [rdi], cx
0x180006cae  mov     eax, edx
0x180006cb0  add     rsp, 38h
0x180006cb4  pop     rdi
0x180006cb5  pop     rbx
0x180006cb6  retn
```
