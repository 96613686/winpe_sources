# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006310`
- end: `0x180006393`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180003dd8`
- `0x18000a36c`
- `0x18000bec6`
- `0x18000bfbe`
- `0x18000c0f2`
- `0x18000c15d`

## callees

- `0x180002fa0`
- `0x180006310`

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
0x180006310  mov     [rsp+arg_10], r8
0x180006315  mov     qword ptr [rsp+Args], r9
0x18000631a  push    rbx
0x18000631b  push    rdi
0x18000631c  sub     rsp, 38h
0x180006320  mov     rax, rdx
0x180006323  mov     rdi, rcx
0x180006326  test    rdx, rdx
0x180006329  jz      short loc_18000637B
0x18000632b  cmp     rax, 7FFFFFFFh
0x180006331  jbe     short loc_18000633A
0x180006333  mov     edx, 80070057h
0x180006338  jmp     short loc_180006385
0x18000633a  lea     rbx, [rdx-1]
0x18000633e  mov     [rsp+48h+var_28], 0
0x180006347  mov     rdx, rbx; BufferCount
0x18000634a  lea     r9, [rsp+48h+Args]; Args
0x18000634f  call    _vsnwprintf
0x180006354  test    eax, eax
0x180006356  js      short loc_18000636E
0x180006358  cdqe
0x18000635a  cmp     rax, rbx
0x18000635d  ja      short loc_18000636E
0x18000635f  xor     edx, edx
0x180006361  cmp     rax, rbx
0x180006364  jnz     short loc_18000638A
0x180006366  xor     eax, eax
0x180006368  mov     [rdi+rbx*2], ax
0x18000636c  jmp     short loc_18000638A
0x18000636e  xor     eax, eax
0x180006370  mov     edx, 8007007Ah
0x180006375  mov     [rdi+rbx*2], ax
0x180006379  jmp     short loc_18000638A
0x18000637b  mov     edx, 80070057h
0x180006380  test    rax, rax
0x180006383  jz      short loc_18000638A
0x180006385  xor     ecx, ecx
0x180006387  mov     [rdi], cx
0x18000638a  mov     eax, edx
0x18000638c  add     rsp, 38h
0x180006390  pop     rdi
0x180006391  pop     rbx
0x180006392  retn
```
