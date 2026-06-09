# CreateScheduleTimeString

- ea: `0x140009f10`
- end: `0x14000a0af`
- name: `CreateScheduleTimeString`
- size: `415`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400096dc`
- `0x14000f56c`

## callees

- `0x140002930`
- `0x14000349c`
- `0x140007230`
- `0x140007368`
- `0x140009f10`

## pseudocode

```c
__int64 __fastcall CreateScheduleTimeString(_WORD *a1, unsigned __int16 *a2)
{
  int v4; // edx
  unsigned __int16 v6; // [rsp+20h] [rbp-228h] BYREF
  _BYTE v7[526]; // [rsp+22h] [rbp-226h] BYREF

  v6 = 0;
  memset_0(v7, 0, 0x206u);
  if ( a1 && a2 )
  {
    v4 = StringCchPrintfW(a2, 0x104u, (size_t *)L"P");
    if ( v4 < 0 )
      return (unsigned int)v4;
    if ( !*a1 )
    {
      if ( a1[1] )
        a1[3] = 31;
      if ( !a1[3]
        || (v4 = StringCchPrintfW(&v6, 0x104u, (size_t *)L"%dD", (unsigned __int16)a1[3]), v4 >= 0)
        && (v4 = StringCchCatW(a2, 260, &v6), v4 >= 0) )
      {
        if ( a1[4] || a1[5] )
        {
          v4 = StringCchCatW(a2, 260, L"T");
          if ( v4 >= 0 )
          {
            if ( !a1[4]
              || (v4 = StringCchPrintfW(&v6, 0x104u, (size_t *)L"%dH", (unsigned __int16)a1[4]), v4 >= 0)
              && (v4 = StringCchCatW(a2, 260, &v6), v4 >= 0) )
            {
              if ( a1[5] )
              {
                v4 = StringCchPrintfW(&v6, 0x104u, (size_t *)L"%dM", (unsigned __int16)a1[5]);
                if ( v4 >= 0 )
                  return (unsigned int)StringCchCatW(a2, 260, &v6);
              }
            }
          }
        }
      }
      return (unsigned int)v4;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x140009f10  mov     [rsp+arg_10], rbx
0x140009f15  mov     [rsp+arg_18], rsi
0x140009f1a  push    rdi
0x140009f1b  sub     rsp, 240h
0x140009f22  mov     rax, cs:__security_cookie
0x140009f29  xor     rax, rsp
0x140009f2c  mov     [rsp+248h+var_18], rax
0x140009f34  mov     rdi, rdx
0x140009f37  mov     rbx, rcx
0x140009f3a  xor     eax, eax
0x140009f3c  lea     rcx, [rsp+248h+var_226]; void *
0x140009f41  xor     edx, edx; Val
0x140009f43  mov     [rsp+248h+var_228], ax
0x140009f48  mov     r8d, 206h; Size
0x140009f4e  call    memset_0
0x140009f53  test    rbx, rbx
0x140009f56  jz      loc_14000A085
0x140009f5c  test    rdi, rdi
0x140009f5f  jz      loc_14000A085
0x140009f65  mov     esi, 104h
0x140009f6a  lea     r8, aP; "P"
0x140009f71  mov     edx, esi; unsigned __int64
0x140009f73  mov     rcx, rdi; unsigned __int16 *
0x140009f76  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009f7b  mov     edx, eax
0x140009f7d  test    eax, eax
0x140009f7f  js      loc_14000A081
0x140009f85  xor     ecx, ecx
0x140009f87  cmp     cx, [rbx]
0x140009f8a  jnz     loc_14000A085
0x140009f90  cmp     cx, [rbx+2]
0x140009f94  jz      short loc_140009F9C
0x140009f96  mov     word ptr [rbx+6], 1Fh
0x140009f9c  xor     eax, eax
0x140009f9e  cmp     ax, [rbx+6]
0x140009fa2  jz      short loc_140009FE1
0x140009fa4  movzx   r9d, word ptr [rbx+6]
0x140009fa9  lea     r8, aDd; "%dD"
0x140009fb0  mov     rdx, rsi; unsigned __int64
0x140009fb3  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x140009fb8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009fbd  mov     edx, eax
0x140009fbf  test    eax, eax
0x140009fc1  js      loc_14000A081
0x140009fc7  lea     r8, [rsp+248h+var_228]; unsigned __int16 *
0x140009fcc  mov     rdx, rsi; unsigned __int64
0x140009fcf  mov     rcx, rdi; unsigned __int16 *
0x140009fd2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009fd7  mov     edx, eax
0x140009fd9  test    eax, eax
0x140009fdb  js      loc_14000A081
0x140009fe1  xor     eax, eax
0x140009fe3  cmp     ax, [rbx+8]
0x140009fe7  jnz     short loc_140009FF3
0x140009fe9  cmp     ax, [rbx+0Ah]
0x140009fed  jz      loc_14000A081
0x140009ff3  lea     r8, aT; "T"
0x140009ffa  mov     rdx, rsi; unsigned __int64
0x140009ffd  mov     rcx, rdi; unsigned __int16 *
0x14000a000  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a005  mov     edx, eax
0x14000a007  test    eax, eax
0x14000a009  js      short loc_14000A081
0x14000a00b  xor     eax, eax
0x14000a00d  cmp     ax, [rbx+8]
0x14000a011  jz      short loc_14000A048
0x14000a013  movzx   r9d, word ptr [rbx+8]
0x14000a018  lea     r8, aDh; "%dH"
0x14000a01f  mov     rdx, rsi; unsigned __int64
0x14000a022  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x14000a027  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a02c  mov     edx, eax
0x14000a02e  test    eax, eax
0x14000a030  js      short loc_14000A081
0x14000a032  lea     r8, [rsp+248h+var_228]; unsigned __int16 *
0x14000a037  mov     rdx, rsi; unsigned __int64
0x14000a03a  mov     rcx, rdi; unsigned __int16 *
0x14000a03d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a042  mov     edx, eax
0x14000a044  test    eax, eax
0x14000a046  js      short loc_14000A081
0x14000a048  xor     eax, eax
0x14000a04a  cmp     ax, [rbx+0Ah]
0x14000a04e  jz      short loc_14000A081
0x14000a050  movzx   r9d, word ptr [rbx+0Ah]
0x14000a055  lea     r8, aDm; "%dM"
0x14000a05c  mov     rdx, rsi; unsigned __int64
0x14000a05f  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x14000a064  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a069  mov     edx, eax
0x14000a06b  test    eax, eax
0x14000a06d  js      short loc_14000A081
0x14000a06f  lea     r8, [rsp+248h+var_228]; unsigned __int16 *
0x14000a074  mov     rdx, rsi; unsigned __int64
0x14000a077  mov     rcx, rdi; unsigned __int16 *
0x14000a07a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a07f  mov     edx, eax
0x14000a081  mov     eax, edx
0x14000a083  jmp     short loc_14000A08A
0x14000a085  mov     eax, 80070057h
0x14000a08a  mov     rcx, [rsp+248h+var_18]
0x14000a092  xor     rcx, rsp; StackCookie
0x14000a095  call    __security_check_cookie
0x14000a09a  lea     r11, [rsp+248h+var_8]
0x14000a0a2  mov     rbx, [r11+20h]
0x14000a0a6  mov     rsi, [r11+28h]
0x14000a0aa  mov     rsp, r11
0x14000a0ad  pop     rdi
0x14000a0ae  retn
```
