# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800070ec`
- end: `0x18000718b`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `159`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180006d80`
- `0x1800072a0`
- `0x180007e50`
- `0x18000a060`

## callees

- `0x180001460`
- `0x180001d18`
- `0x1800070ec`

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
0x1800070ec  mov     [rsp+arg_10], r8
0x1800070f1  mov     qword ptr [rsp+Args], r9
0x1800070f6  push    rbx
0x1800070f7  push    rdi
0x1800070f8  sub     rsp, 38h
0x1800070fc  mov     rax, cs:__security_cookie
0x180007103  xor     rax, rsp
0x180007106  mov     [rsp+48h+var_20], rax
0x18000710b  mov     rax, rdx
0x18000710e  mov     rdi, rcx
0x180007111  test    rdx, rdx
0x180007114  jz      short loc_180007166
0x180007116  cmp     rax, 7FFFFFFFh
0x18000711c  jbe     short loc_180007125
0x18000711e  mov     edx, 80070057h
0x180007123  jmp     short loc_180007170
0x180007125  lea     rbx, [rdx-1]
0x180007129  mov     [rsp+48h+var_28], 0
0x180007132  mov     rdx, rbx; BufferCount
0x180007135  lea     r9, [rsp+48h+Args]; Args
0x18000713a  call    _vsnwprintf
0x18000713f  test    eax, eax
0x180007141  js      short loc_180007159
0x180007143  cdqe
0x180007145  cmp     rax, rbx
0x180007148  ja      short loc_180007159
0x18000714a  xor     edx, edx
0x18000714c  cmp     rax, rbx
0x18000714f  jnz     short loc_180007175
0x180007151  xor     eax, eax
0x180007153  mov     [rdi+rbx*2], ax
0x180007157  jmp     short loc_180007175
0x180007159  xor     eax, eax
0x18000715b  mov     edx, 8007007Ah
0x180007160  mov     [rdi+rbx*2], ax
0x180007164  jmp     short loc_180007175
0x180007166  mov     edx, 80070057h
0x18000716b  test    rax, rax
0x18000716e  jz      short loc_180007175
0x180007170  xor     ecx, ecx
0x180007172  mov     [rdi], cx
0x180007175  mov     eax, edx
0x180007177  mov     rcx, [rsp+48h+var_20]
0x18000717c  xor     rcx, rsp; StackCookie
0x18000717f  call    __security_check_cookie
0x180007184  add     rsp, 38h
0x180007188  pop     rdi
0x180007189  pop     rbx
0x18000718a  retn
```
