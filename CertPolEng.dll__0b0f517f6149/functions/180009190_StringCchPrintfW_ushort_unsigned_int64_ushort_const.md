# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180009190`
- end: `0x180009212`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `130`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005c20`
- `0x180009ce8`
- `0x180009e54`
- `0x1800131d0`

## callees

- `0x180009190`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800091cb`
- `msvcrt!_vsnwprintf` at `0x1800091cb`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  __int64 result; // rax
  unsigned __int64 v5; // rsi
  unsigned int v6; // ebx
  int v7; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( !a2 )
    return 2147942487LL;
  if ( a2 <= 0x7FFFFFFF )
  {
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
    }
    return v6;
  }
  else
  {
    result = 2147942487LL;
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180009190  mov     [rsp+arg_10], r8
0x180009195  mov     qword ptr [rsp+Args], r9
0x18000919a  push    rbx
0x18000919b  push    rdi
0x18000919c  sub     rsp, 38h
0x1800091a0  mov     rdi, rcx
0x1800091a3  test    rdx, rdx
0x1800091a6  jz      short loc_1800091FC
0x1800091a8  cmp     rdx, 7FFFFFFFh
0x1800091af  jbe     short loc_1800091B8
0x1800091b1  mov     eax, 80070057h
0x1800091b6  jmp     short loc_180009206
0x1800091b8  mov     [rsp+48h+var_18], rsi
0x1800091bd  lea     r9, [rsp+48h+Args]; Args
0x1800091c2  lea     rsi, [rdx-1]
0x1800091c6  xor     ebx, ebx
0x1800091c8  mov     rdx, rsi; BufferCount
0x1800091cb  call    cs:__imp__vsnwprintf
0x1800091d1  test    eax, eax
0x1800091d3  js      short loc_1800091E5
0x1800091d5  movsxd  rcx, eax
0x1800091d8  cmp     rcx, rsi
0x1800091db  ja      short loc_1800091E5
0x1800091dd  jnz     short loc_1800091EE
0x1800091df  mov     [rdi+rsi*2], bx
0x1800091e3  jmp     short loc_1800091EE
0x1800091e5  mov     [rdi+rsi*2], bx
0x1800091e9  mov     ebx, 8007007Ah
0x1800091ee  mov     rsi, [rsp+48h+var_18]
0x1800091f3  mov     eax, ebx
0x1800091f5  add     rsp, 38h
0x1800091f9  pop     rdi
0x1800091fa  pop     rbx
0x1800091fb  retn
0x1800091fc  mov     eax, 80070057h
0x180009201  test    rdx, rdx
0x180009204  jz      short loc_18000920B
0x180009206  xor     ebx, ebx
0x180009208  mov     [rcx], bx
0x18000920b  add     rsp, 38h
0x18000920f  pop     rdi
0x180009210  pop     rbx
0x180009211  retn
```
