# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006bb0`
- end: `0x180006c4f`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `159`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x1800042e8`
- `0x18000c10c`
- `0x18000c204`
- `0x18000c338`
- `0x18000c3a3`

## callees

- `0x180002650`
- `0x1800032ec`
- `0x180006bb0`

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
0x180006bb0  mov     [rsp+arg_10], r8
0x180006bb5  mov     qword ptr [rsp+Args], r9
0x180006bba  push    rbx
0x180006bbb  push    rdi
0x180006bbc  sub     rsp, 38h
0x180006bc0  mov     rax, cs:__security_cookie
0x180006bc7  xor     rax, rsp
0x180006bca  mov     [rsp+48h+var_20], rax
0x180006bcf  mov     rax, rdx
0x180006bd2  mov     rdi, rcx
0x180006bd5  test    rdx, rdx
0x180006bd8  jz      short loc_180006C2A
0x180006bda  cmp     rax, 7FFFFFFFh
0x180006be0  jbe     short loc_180006BE9
0x180006be2  mov     edx, 80070057h
0x180006be7  jmp     short loc_180006C34
0x180006be9  lea     rbx, [rdx-1]
0x180006bed  mov     [rsp+48h+var_28], 0
0x180006bf6  mov     rdx, rbx; BufferCount
0x180006bf9  lea     r9, [rsp+48h+Args]; Args
0x180006bfe  call    _vsnwprintf
0x180006c03  test    eax, eax
0x180006c05  js      short loc_180006C1D
0x180006c07  cdqe
0x180006c09  cmp     rax, rbx
0x180006c0c  ja      short loc_180006C1D
0x180006c0e  xor     edx, edx
0x180006c10  cmp     rax, rbx
0x180006c13  jnz     short loc_180006C39
0x180006c15  xor     eax, eax
0x180006c17  mov     [rdi+rbx*2], ax
0x180006c1b  jmp     short loc_180006C39
0x180006c1d  xor     eax, eax
0x180006c1f  mov     edx, 8007007Ah
0x180006c24  mov     [rdi+rbx*2], ax
0x180006c28  jmp     short loc_180006C39
0x180006c2a  mov     edx, 80070057h
0x180006c2f  test    rax, rax
0x180006c32  jz      short loc_180006C39
0x180006c34  xor     ecx, ecx
0x180006c36  mov     [rdi], cx
0x180006c39  mov     eax, edx
0x180006c3b  mov     rcx, [rsp+48h+var_20]
0x180006c40  xor     rcx, rsp; StackCookie
0x180006c43  call    __security_check_cookie
0x180006c48  add     rsp, 38h
0x180006c4c  pop     rdi
0x180006c4d  pop     rbx
0x180006c4e  retn
```
