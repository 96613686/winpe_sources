# StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000df74`
- end: `0x18000dff8`
- name: `?StringCbPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000db58`
- `0x18001238c`
- `0x180012478`

## callees

- `0x18000df74`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000dfb3`
- `msvcrt!_vsnwprintf` at `0x18000dfb3`

## pseudocode

```c
__int64 StringCbPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned __int64 v4; // rax
  unsigned int v5; // edx
  unsigned __int64 v6; // rbx
  int v7; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  v4 = a2 >> 1;
  if ( a2 >> 1 )
  {
    if ( v4 <= 0x7FFFFFFF )
    {
      v6 = v4 - 1;
      v7 = _vsnwprintf(a1, v4 - 1, a3, Args);
      if ( v7 < 0 || v7 > v6 )
      {
        v5 = -2147024774;
        a1[v6] = 0;
      }
      else
      {
        v5 = 0;
        if ( v7 == v6 )
          a1[v6] = 0;
      }
    }
    else
    {
      v5 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x18000df74  mov     [rsp+arg_10], r8
0x18000df79  mov     qword ptr [rsp+Args], r9
0x18000df7e  push    rbx
0x18000df7f  push    rdi
0x18000df80  sub     rsp, 38h
0x18000df84  mov     rax, rdx
0x18000df87  mov     rdi, rcx
0x18000df8a  shr     rax, 1
0x18000df8d  jz      short loc_18000DFE0
0x18000df8f  cmp     rax, 7FFFFFFFh
0x18000df95  jbe     short loc_18000DF9E
0x18000df97  mov     edx, 80070057h
0x18000df9c  jmp     short loc_18000DFEA
0x18000df9e  lea     rbx, [rax-1]
0x18000dfa2  mov     [rsp+48h+var_28], 0
0x18000dfab  mov     rdx, rbx; BufferCount
0x18000dfae  lea     r9, [rsp+48h+Args]; Args
0x18000dfb3  call    cs:__imp__vsnwprintf
0x18000dfb9  test    eax, eax
0x18000dfbb  js      short loc_18000DFD3
0x18000dfbd  cdqe
0x18000dfbf  cmp     rax, rbx
0x18000dfc2  ja      short loc_18000DFD3
0x18000dfc4  xor     edx, edx
0x18000dfc6  cmp     rax, rbx
0x18000dfc9  jnz     short loc_18000DFEF
0x18000dfcb  xor     eax, eax
0x18000dfcd  mov     [rdi+rbx*2], ax
0x18000dfd1  jmp     short loc_18000DFEF
0x18000dfd3  xor     eax, eax
0x18000dfd5  mov     edx, 8007007Ah
0x18000dfda  mov     [rdi+rbx*2], ax
0x18000dfde  jmp     short loc_18000DFEF
0x18000dfe0  mov     edx, 80070057h
0x18000dfe5  test    rax, rax
0x18000dfe8  jz      short loc_18000DFEF
0x18000dfea  xor     ecx, ecx
0x18000dfec  mov     [rdi], cx
0x18000dfef  mov     eax, edx
0x18000dff1  add     rsp, 38h
0x18000dff5  pop     rdi
0x18000dff6  pop     rbx
0x18000dff7  retn
```
