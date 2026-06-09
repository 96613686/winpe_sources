# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006ed0`
- end: `0x180006f54`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003648`
- `0x180003ee0`
- `0x180007a20`

## callees

- `0x180006ed0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180006f0f`
- `msvcrt!_vsnwprintf` at `0x180006f0f`

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
0x180006ed0  mov     [rsp+arg_10], r8
0x180006ed5  mov     qword ptr [rsp+Args], r9
0x180006eda  push    rbx
0x180006edb  push    rdi
0x180006edc  sub     rsp, 38h
0x180006ee0  mov     rax, rdx
0x180006ee3  mov     rdi, rcx
0x180006ee6  test    rdx, rdx
0x180006ee9  jz      short loc_180006F3C
0x180006eeb  cmp     rax, 7FFFFFFFh
0x180006ef1  jbe     short loc_180006EFA
0x180006ef3  mov     edx, 80070057h
0x180006ef8  jmp     short loc_180006F46
0x180006efa  lea     rbx, [rdx-1]
0x180006efe  mov     [rsp+48h+var_28], 0
0x180006f07  mov     rdx, rbx; BufferCount
0x180006f0a  lea     r9, [rsp+48h+Args]; Args
0x180006f0f  call    cs:__imp__vsnwprintf
0x180006f15  test    eax, eax
0x180006f17  js      short loc_180006F2F
0x180006f19  cdqe
0x180006f1b  cmp     rax, rbx
0x180006f1e  ja      short loc_180006F2F
0x180006f20  xor     edx, edx
0x180006f22  cmp     rax, rbx
0x180006f25  jnz     short loc_180006F4B
0x180006f27  xor     eax, eax
0x180006f29  mov     [rdi+rbx*2], ax
0x180006f2d  jmp     short loc_180006F4B
0x180006f2f  xor     eax, eax
0x180006f31  mov     edx, 8007007Ah
0x180006f36  mov     [rdi+rbx*2], ax
0x180006f3a  jmp     short loc_180006F4B
0x180006f3c  mov     edx, 80070057h
0x180006f41  test    rax, rax
0x180006f44  jz      short loc_180006F4B
0x180006f46  xor     ecx, ecx
0x180006f48  mov     [rdi], cx
0x180006f4b  mov     eax, edx
0x180006f4d  add     rsp, 38h
0x180006f51  pop     rdi
0x180006f52  pop     rbx
0x180006f53  retn
```
