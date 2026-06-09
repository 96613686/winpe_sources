# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006c98`
- end: `0x180006d23`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `139`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003354`
- `0x180003700`
- `0x180005134`

## callees

- `0x180006c98`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180006cd7`
- `msvcrt!_vsnwprintf` at `0x180006cd7`

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
      v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
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
0x180006c98  mov     [rsp+arg_10], r8
0x180006c9d  mov     qword ptr [rsp+Args], r9
0x180006ca2  push    rbx
0x180006ca3  push    rdi
0x180006ca4  sub     rsp, 38h
0x180006ca8  mov     rax, rdx
0x180006cab  mov     rdi, rcx
0x180006cae  test    rdx, rdx
0x180006cb1  jz      short loc_180006D0A
0x180006cb3  cmp     rax, 7FFFFFFFh
0x180006cb9  jbe     short loc_180006CC2
0x180006cbb  mov     edx, 80070057h
0x180006cc0  jmp     short loc_180006D14
0x180006cc2  lea     rbx, [rdx-1]
0x180006cc6  mov     [rsp+48h+var_28], 0
0x180006ccf  mov     rdx, rbx; BufferCount
0x180006cd2  lea     r9, [rsp+48h+Args]; Args
0x180006cd7  call    cs:__imp__vsnwprintf
0x180006cde  nop     dword ptr [rax+rax+00h]
0x180006ce3  test    eax, eax
0x180006ce5  js      short loc_180006CFD
0x180006ce7  cdqe
0x180006ce9  cmp     rax, rbx
0x180006cec  ja      short loc_180006CFD
0x180006cee  xor     edx, edx
0x180006cf0  cmp     rax, rbx
0x180006cf3  jnz     short loc_180006D19
0x180006cf5  xor     eax, eax
0x180006cf7  mov     [rdi+rbx*2], ax
0x180006cfb  jmp     short loc_180006D19
0x180006cfd  xor     eax, eax
0x180006cff  mov     edx, 8007007Ah
0x180006d04  mov     [rdi+rbx*2], ax
0x180006d08  jmp     short loc_180006D19
0x180006d0a  mov     edx, 80070057h
0x180006d0f  test    rax, rax
0x180006d12  jz      short loc_180006D19
0x180006d14  xor     ecx, ecx
0x180006d16  mov     [rdi], cx
0x180006d19  mov     eax, edx
0x180006d1b  add     rsp, 38h
0x180006d1f  pop     rdi
0x180006d20  pop     rbx
0x180006d21  retn
```
