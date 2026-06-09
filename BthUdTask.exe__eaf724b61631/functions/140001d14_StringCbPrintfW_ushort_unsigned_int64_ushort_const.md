# StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140001d14`
- end: `0x140001d98`
- name: `?StringCbPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001da0`

## callees

- `0x140001d14`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140001d53`
- `msvcrt!_vsnwprintf` at `0x140001d53`

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
0x140001d14  mov     [rsp+arg_10], r8
0x140001d19  mov     qword ptr [rsp+Args], r9
0x140001d1e  push    rbx
0x140001d1f  push    rdi
0x140001d20  sub     rsp, 38h
0x140001d24  mov     rax, rdx
0x140001d27  mov     rdi, rcx
0x140001d2a  shr     rax, 1
0x140001d2d  jz      short loc_140001D80
0x140001d2f  cmp     rax, 7FFFFFFFh
0x140001d35  jbe     short loc_140001D3E
0x140001d37  mov     edx, 80070057h
0x140001d3c  jmp     short loc_140001D8A
0x140001d3e  lea     rbx, [rax-1]
0x140001d42  mov     [rsp+48h+var_28], 0
0x140001d4b  mov     rdx, rbx; BufferCount
0x140001d4e  lea     r9, [rsp+48h+Args]; Args
0x140001d53  call    cs:__imp__vsnwprintf
0x140001d59  test    eax, eax
0x140001d5b  js      short loc_140001D73
0x140001d5d  cdqe
0x140001d5f  cmp     rax, rbx
0x140001d62  ja      short loc_140001D73
0x140001d64  xor     edx, edx
0x140001d66  cmp     rax, rbx
0x140001d69  jnz     short loc_140001D8F
0x140001d6b  xor     eax, eax
0x140001d6d  mov     [rdi+rbx*2], ax
0x140001d71  jmp     short loc_140001D8F
0x140001d73  xor     eax, eax
0x140001d75  mov     edx, 8007007Ah
0x140001d7a  mov     [rdi+rbx*2], ax
0x140001d7e  jmp     short loc_140001D8F
0x140001d80  mov     edx, 80070057h
0x140001d85  test    rax, rax
0x140001d88  jz      short loc_140001D8F
0x140001d8a  xor     ecx, ecx
0x140001d8c  mov     [rdi], cx
0x140001d8f  mov     eax, edx
0x140001d91  add     rsp, 38h
0x140001d95  pop     rdi
0x140001d96  pop     rbx
0x140001d97  retn
```
