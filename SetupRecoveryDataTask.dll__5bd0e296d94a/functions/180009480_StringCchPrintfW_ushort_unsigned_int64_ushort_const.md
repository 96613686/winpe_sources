# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180009480`
- end: `0x180009520`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `160`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003940`
- `0x180003ce4`
- `0x180004654`
- `0x18000b780`

## callees

- `0x180009480`
- `0x18000c610`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800094ce`
- `msvcrt!_vsnwprintf` at `0x1800094ce`

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
0x180009480  mov     [rsp+arg_10], r8
0x180009485  mov     qword ptr [rsp+Args], r9
0x18000948a  push    rbx
0x18000948b  push    rdi
0x18000948c  sub     rsp, 38h
0x180009490  mov     rax, cs:__security_cookie
0x180009497  xor     rax, rsp
0x18000949a  mov     [rsp+48h+var_20], rax
0x18000949f  mov     rax, rdx
0x1800094a2  mov     rdi, rcx
0x1800094a5  test    rdx, rdx
0x1800094a8  jz      short loc_1800094FB
0x1800094aa  cmp     rax, 7FFFFFFFh
0x1800094b0  jbe     short loc_1800094B9
0x1800094b2  mov     edx, 80070057h
0x1800094b7  jmp     short loc_180009505
0x1800094b9  lea     rbx, [rdx-1]
0x1800094bd  mov     [rsp+48h+var_28], 0
0x1800094c6  mov     rdx, rbx; BufferCount
0x1800094c9  lea     r9, [rsp+48h+Args]; Args
0x1800094ce  call    cs:__imp__vsnwprintf
0x1800094d4  test    eax, eax
0x1800094d6  js      short loc_1800094EE
0x1800094d8  cdqe
0x1800094da  cmp     rax, rbx
0x1800094dd  ja      short loc_1800094EE
0x1800094df  xor     edx, edx
0x1800094e1  cmp     rax, rbx
0x1800094e4  jnz     short loc_18000950A
0x1800094e6  xor     eax, eax
0x1800094e8  mov     [rdi+rbx*2], ax
0x1800094ec  jmp     short loc_18000950A
0x1800094ee  xor     eax, eax
0x1800094f0  mov     edx, 8007007Ah
0x1800094f5  mov     [rdi+rbx*2], ax
0x1800094f9  jmp     short loc_18000950A
0x1800094fb  mov     edx, 80070057h
0x180009500  test    rax, rax
0x180009503  jz      short loc_18000950A
0x180009505  xor     ecx, ecx
0x180009507  mov     [rdi], cx
0x18000950a  mov     eax, edx
0x18000950c  mov     rcx, [rsp+48h+var_20]
0x180009511  xor     rcx, rsp; StackCookie
0x180009514  call    __security_check_cookie
0x180009519  add     rsp, 38h
0x18000951d  pop     rdi
0x18000951e  pop     rbx
0x18000951f  retn
```
