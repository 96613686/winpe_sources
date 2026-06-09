# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180002514`
- end: `0x180002598`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003a78`
- `0x180003e1c`
- `0x1800094c8`
- `0x180010120`

## callees

- `0x180002514`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180002553`
- `msvcrt!_vsnwprintf` at `0x180002553`

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
0x180002514  mov     [rsp+arg_10], r8
0x180002519  mov     qword ptr [rsp+Args], r9
0x18000251e  push    rbx
0x18000251f  push    rdi
0x180002520  sub     rsp, 38h
0x180002524  mov     rax, rdx
0x180002527  mov     rdi, rcx
0x18000252a  test    rdx, rdx
0x18000252d  jz      short loc_180002580
0x18000252f  cmp     rax, 7FFFFFFFh
0x180002535  jbe     short loc_18000253E
0x180002537  mov     edx, 80070057h
0x18000253c  jmp     short loc_18000258A
0x18000253e  lea     rbx, [rdx-1]
0x180002542  mov     [rsp+48h+var_28], 0
0x18000254b  mov     rdx, rbx; BufferCount
0x18000254e  lea     r9, [rsp+48h+Args]; Args
0x180002553  call    cs:__imp__vsnwprintf
0x180002559  test    eax, eax
0x18000255b  js      short loc_180002573
0x18000255d  cdqe
0x18000255f  cmp     rax, rbx
0x180002562  ja      short loc_180002573
0x180002564  xor     edx, edx
0x180002566  cmp     rax, rbx
0x180002569  jnz     short loc_18000258F
0x18000256b  xor     eax, eax
0x18000256d  mov     [rdi+rbx*2], ax
0x180002571  jmp     short loc_18000258F
0x180002573  xor     eax, eax
0x180002575  mov     edx, 8007007Ah
0x18000257a  mov     [rdi+rbx*2], ax
0x18000257e  jmp     short loc_18000258F
0x180002580  mov     edx, 80070057h
0x180002585  test    rax, rax
0x180002588  jz      short loc_18000258F
0x18000258a  xor     ecx, ecx
0x18000258c  mov     [rdi], cx
0x18000258f  mov     eax, edx
0x180002591  add     rsp, 38h
0x180002595  pop     rdi
0x180002596  pop     rbx
0x180002597  retn
```
