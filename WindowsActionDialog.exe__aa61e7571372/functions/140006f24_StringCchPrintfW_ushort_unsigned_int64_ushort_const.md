# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140006f24`
- end: `0x140006fc3`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `159`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140003c20`
- `0x1400094f7`
- `0x1400095ef`
- `0x140009723`
- `0x14000978e`

## callees

- `0x140001460`
- `0x140001f74`
- `0x140006f24`

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
0x140006f24  mov     [rsp+arg_10], r8
0x140006f29  mov     qword ptr [rsp+Args], r9
0x140006f2e  push    rbx
0x140006f2f  push    rdi
0x140006f30  sub     rsp, 38h
0x140006f34  mov     rax, cs:__security_cookie
0x140006f3b  xor     rax, rsp
0x140006f3e  mov     [rsp+48h+var_20], rax
0x140006f43  mov     rax, rdx
0x140006f46  mov     rdi, rcx
0x140006f49  test    rdx, rdx
0x140006f4c  jz      short loc_140006F9E
0x140006f4e  cmp     rax, 7FFFFFFFh
0x140006f54  jbe     short loc_140006F5D
0x140006f56  mov     edx, 80070057h
0x140006f5b  jmp     short loc_140006FA8
0x140006f5d  lea     rbx, [rdx-1]
0x140006f61  mov     [rsp+48h+var_28], 0
0x140006f6a  mov     rdx, rbx; BufferCount
0x140006f6d  lea     r9, [rsp+48h+Args]; Args
0x140006f72  call    _vsnwprintf
0x140006f77  test    eax, eax
0x140006f79  js      short loc_140006F91
0x140006f7b  cdqe
0x140006f7d  cmp     rax, rbx
0x140006f80  ja      short loc_140006F91
0x140006f82  xor     edx, edx
0x140006f84  cmp     rax, rbx
0x140006f87  jnz     short loc_140006FAD
0x140006f89  xor     eax, eax
0x140006f8b  mov     [rdi+rbx*2], ax
0x140006f8f  jmp     short loc_140006FAD
0x140006f91  xor     eax, eax
0x140006f93  mov     edx, 8007007Ah
0x140006f98  mov     [rdi+rbx*2], ax
0x140006f9c  jmp     short loc_140006FAD
0x140006f9e  mov     edx, 80070057h
0x140006fa3  test    rax, rax
0x140006fa6  jz      short loc_140006FAD
0x140006fa8  xor     ecx, ecx
0x140006faa  mov     [rdi], cx
0x140006fad  mov     eax, edx
0x140006faf  mov     rcx, [rsp+48h+var_20]
0x140006fb4  xor     rcx, rsp; StackCookie
0x140006fb7  call    __security_check_cookie
0x140006fbc  add     rsp, 38h
0x140006fc0  pop     rdi
0x140006fc1  pop     rbx
0x140006fc2  retn
```
