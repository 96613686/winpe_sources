# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180008ea8`
- end: `0x180008f2b`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180004988`
- `0x180004d38`
- `0x180017fa6`
- `0x1800180d4`
- `0x180018208`
- `0x180018273`

## callees

- `0x180002a40`
- `0x180008ea8`

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
0x180008ea8  mov     [rsp+arg_10], r8
0x180008ead  mov     qword ptr [rsp+Args], r9
0x180008eb2  push    rbx
0x180008eb3  push    rdi
0x180008eb4  sub     rsp, 38h
0x180008eb8  mov     rax, rdx
0x180008ebb  mov     rdi, rcx
0x180008ebe  test    rdx, rdx
0x180008ec1  jz      short loc_180008F13
0x180008ec3  cmp     rax, 7FFFFFFFh
0x180008ec9  jbe     short loc_180008ED2
0x180008ecb  mov     edx, 80070057h
0x180008ed0  jmp     short loc_180008F1D
0x180008ed2  lea     rbx, [rdx-1]
0x180008ed6  mov     [rsp+48h+var_28], 0
0x180008edf  mov     rdx, rbx; BufferCount
0x180008ee2  lea     r9, [rsp+48h+Args]; Args
0x180008ee7  call    _vsnwprintf
0x180008eec  test    eax, eax
0x180008eee  js      short loc_180008F06
0x180008ef0  cdqe
0x180008ef2  cmp     rax, rbx
0x180008ef5  ja      short loc_180008F06
0x180008ef7  xor     edx, edx
0x180008ef9  cmp     rax, rbx
0x180008efc  jnz     short loc_180008F22
0x180008efe  xor     eax, eax
0x180008f00  mov     [rdi+rbx*2], ax
0x180008f04  jmp     short loc_180008F22
0x180008f06  xor     eax, eax
0x180008f08  mov     edx, 8007007Ah
0x180008f0d  mov     [rdi+rbx*2], ax
0x180008f11  jmp     short loc_180008F22
0x180008f13  mov     edx, 80070057h
0x180008f18  test    rax, rax
0x180008f1b  jz      short loc_180008F22
0x180008f1d  xor     ecx, ecx
0x180008f1f  mov     [rdi], cx
0x180008f22  mov     eax, edx
0x180008f24  add     rsp, 38h
0x180008f28  pop     rdi
0x180008f29  pop     rbx
0x180008f2a  retn
```
