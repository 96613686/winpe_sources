# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180005dc0`
- end: `0x180005e57`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `151`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e60`
- `0x180006560`
- `0x1800090a0`

## callees

- `0x180005dc0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180005e05`
- `msvcrt!_vsnwprintf` at `0x180005e05`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  __int64 result; // rax
  unsigned __int64 v5; // rdi
  unsigned int v6; // ebx
  int v7; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( !a2 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 2147942487LL;
    *a1 = 0;
    return result;
  }
  v5 = a2 - 1;
  v6 = 0;
  v7 = _vsnwprintf(a1, a2 - 1, a3, Args);
  if ( v7 < 0 || v7 > v5 )
  {
    a1[v5] = 0;
    return (unsigned int)-2147024774;
  }
  else if ( v7 == v5 )
  {
    a1[v5] = 0;
    return 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180005dc0  mov     [rsp+arg_10], r8
0x180005dc5  mov     qword ptr [rsp+Args], r9
0x180005dca  push    rbx
0x180005dcb  push    rsi
0x180005dcc  sub     rsp, 38h
0x180005dd0  mov     rsi, rcx
0x180005dd3  test    rdx, rdx
0x180005dd6  jz      short loc_180005E41
0x180005dd8  cmp     rdx, 7FFFFFFFh
0x180005ddf  jbe     short loc_180005DF2
0x180005de1  xor     ebx, ebx
0x180005de3  mov     eax, 80070057h
0x180005de8  mov     [rcx], bx
0x180005deb  add     rsp, 38h
0x180005def  pop     rsi
0x180005df0  pop     rbx
0x180005df1  retn
0x180005df2  mov     [rsp+48h+var_18], rdi
0x180005df7  lea     r9, [rsp+48h+Args]; Args
0x180005dfc  lea     rdi, [rdx-1]
0x180005e00  xor     ebx, ebx
0x180005e02  mov     rdx, rdi; BufferCount
0x180005e05  call    cs:__imp__vsnwprintf
0x180005e0b  test    eax, eax
0x180005e0d  js      short loc_180005E2A
0x180005e0f  cdqe
0x180005e11  cmp     rax, rdi
0x180005e14  ja      short loc_180005E2A
0x180005e16  jnz     short loc_180005E33
0x180005e18  mov     [rsi+rdi*2], bx
0x180005e1c  mov     eax, ebx
0x180005e1e  mov     rdi, [rsp+48h+var_18]
0x180005e23  add     rsp, 38h
0x180005e27  pop     rsi
0x180005e28  pop     rbx
0x180005e29  retn
0x180005e2a  mov     [rsi+rdi*2], bx
0x180005e2e  mov     ebx, 8007007Ah
0x180005e33  mov     rdi, [rsp+48h+var_18]
0x180005e38  mov     eax, ebx
0x180005e3a  add     rsp, 38h
0x180005e3e  pop     rsi
0x180005e3f  pop     rbx
0x180005e40  retn
0x180005e41  mov     eax, 80070057h
0x180005e46  test    rdx, rdx
0x180005e49  jz      short loc_180005E50
0x180005e4b  xor     ebx, ebx
0x180005e4d  mov     [rcx], bx
0x180005e50  add     rsp, 38h
0x180005e54  pop     rsi
0x180005e55  pop     rbx
0x180005e56  retn
```
