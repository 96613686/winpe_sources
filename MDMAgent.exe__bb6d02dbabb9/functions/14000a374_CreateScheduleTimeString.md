# CreateScheduleTimeString

- ea: `0x14000a374`
- end: `0x14000a514`
- name: `CreateScheduleTimeString`
- size: `416`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140009ae8`
- `0x14000fd3c`

## callees

- `0x1400029c0`
- `0x14000353c`
- `0x1400074ec`
- `0x140007628`
- `0x14000a374`

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
    v4 = StringCchPrintfW(a2, 0x104u, L"P");
    if ( v4 < 0 )
      return (unsigned int)v4;
    if ( !*a1 )
    {
      if ( a1[1] )
        a1[3] = 31;
      if ( !a1[3]
        || (v4 = StringCchPrintfW(&v6, 0x104u, L"%dD", (unsigned __int16)a1[3]), v4 >= 0)
        && (v4 = StringCchCatW(a2, 0x104u, &v6), v4 >= 0) )
      {
        if ( a1[4] || a1[5] )
        {
          v4 = StringCchCatW(a2, 0x104u, L"T");
          if ( v4 >= 0 )
          {
            if ( !a1[4]
              || (v4 = StringCchPrintfW(&v6, 0x104u, L"%dH", (unsigned __int16)a1[4]), v4 >= 0)
              && (v4 = StringCchCatW(a2, 0x104u, &v6), v4 >= 0) )
            {
              if ( a1[5] )
              {
                v4 = StringCchPrintfW(&v6, 0x104u, L"%dM", (unsigned __int16)a1[5]);
                if ( v4 >= 0 )
                  return (unsigned int)StringCchCatW(a2, 0x104u, &v6);
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
0x14000a374  mov     [rsp+arg_10], rbx
0x14000a379  mov     [rsp+arg_18], rsi
0x14000a37e  push    rdi
0x14000a37f  sub     rsp, 240h
0x14000a386  mov     rax, cs:__security_cookie
0x14000a38d  xor     rax, rsp
0x14000a390  mov     [rsp+248h+var_18], rax
0x14000a398  mov     rdi, rdx
0x14000a39b  mov     rbx, rcx
0x14000a39e  xor     eax, eax
0x14000a3a0  lea     rcx, [rsp+248h+var_226]; void *
0x14000a3a5  xor     edx, edx; Val
0x14000a3a7  mov     [rsp+248h+var_228], ax
0x14000a3ac  mov     r8d, 206h; Size
0x14000a3b2  call    memset_0
0x14000a3b7  test    rbx, rbx
0x14000a3ba  jz      loc_14000A4E9
0x14000a3c0  test    rdi, rdi
0x14000a3c3  jz      loc_14000A4E9
0x14000a3c9  mov     esi, 104h
0x14000a3ce  lea     r8, aP; "P"
0x14000a3d5  mov     edx, esi; unsigned __int64
0x14000a3d7  mov     rcx, rdi; unsigned __int16 *
0x14000a3da  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a3df  mov     edx, eax
0x14000a3e1  test    eax, eax
0x14000a3e3  js      loc_14000A4E5
0x14000a3e9  xor     ecx, ecx
0x14000a3eb  cmp     cx, [rbx]
0x14000a3ee  jnz     loc_14000A4E9
0x14000a3f4  cmp     cx, [rbx+2]
0x14000a3f8  jz      short loc_14000A400
0x14000a3fa  mov     word ptr [rbx+6], 1Fh
0x14000a400  xor     eax, eax
0x14000a402  cmp     ax, [rbx+6]
0x14000a406  jz      short loc_14000A445
0x14000a408  movzx   r9d, word ptr [rbx+6]
0x14000a40d  lea     r8, aDd; "%dD"
0x14000a414  mov     rdx, rsi; unsigned __int64
0x14000a417  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x14000a41c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a421  mov     edx, eax
0x14000a423  test    eax, eax
0x14000a425  js      loc_14000A4E5
0x14000a42b  lea     r8, [rsp+248h+var_228]; unsigned __int16 *
0x14000a430  mov     rdx, rsi; unsigned __int64
0x14000a433  mov     rcx, rdi; unsigned __int16 *
0x14000a436  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a43b  mov     edx, eax
0x14000a43d  test    eax, eax
0x14000a43f  js      loc_14000A4E5
0x14000a445  xor     eax, eax
0x14000a447  cmp     ax, [rbx+8]
0x14000a44b  jnz     short loc_14000A457
0x14000a44d  cmp     ax, [rbx+0Ah]
0x14000a451  jz      loc_14000A4E5
0x14000a457  lea     r8, aT; "T"
0x14000a45e  mov     rdx, rsi; unsigned __int64
0x14000a461  mov     rcx, rdi; unsigned __int16 *
0x14000a464  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a469  mov     edx, eax
0x14000a46b  test    eax, eax
0x14000a46d  js      short loc_14000A4E5
0x14000a46f  xor     eax, eax
0x14000a471  cmp     ax, [rbx+8]
0x14000a475  jz      short loc_14000A4AC
0x14000a477  movzx   r9d, word ptr [rbx+8]
0x14000a47c  lea     r8, aDh; "%dH"
0x14000a483  mov     rdx, rsi; unsigned __int64
0x14000a486  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x14000a48b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a490  mov     edx, eax
0x14000a492  test    eax, eax
0x14000a494  js      short loc_14000A4E5
0x14000a496  lea     r8, [rsp+248h+var_228]; unsigned __int16 *
0x14000a49b  mov     rdx, rsi; unsigned __int64
0x14000a49e  mov     rcx, rdi; unsigned __int16 *
0x14000a4a1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a4a6  mov     edx, eax
0x14000a4a8  test    eax, eax
0x14000a4aa  js      short loc_14000A4E5
0x14000a4ac  xor     eax, eax
0x14000a4ae  cmp     ax, [rbx+0Ah]
0x14000a4b2  jz      short loc_14000A4E5
0x14000a4b4  movzx   r9d, word ptr [rbx+0Ah]
0x14000a4b9  lea     r8, aDm; "%dM"
0x14000a4c0  mov     rdx, rsi; unsigned __int64
0x14000a4c3  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x14000a4c8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a4cd  mov     edx, eax
0x14000a4cf  test    eax, eax
0x14000a4d1  js      short loc_14000A4E5
0x14000a4d3  lea     r8, [rsp+248h+var_228]; unsigned __int16 *
0x14000a4d8  mov     rdx, rsi; unsigned __int64
0x14000a4db  mov     rcx, rdi; unsigned __int16 *
0x14000a4de  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a4e3  mov     edx, eax
0x14000a4e5  mov     eax, edx
0x14000a4e7  jmp     short loc_14000A4EE
0x14000a4e9  mov     eax, 80070057h
0x14000a4ee  mov     rcx, [rsp+248h+var_18]
0x14000a4f6  xor     rcx, rsp; StackCookie
0x14000a4f9  call    __security_check_cookie
0x14000a4fe  lea     r11, [rsp+248h+var_8]
0x14000a506  mov     rbx, [r11+20h]
0x14000a50a  mov     rsi, [r11+28h]
0x14000a50e  mov     rsp, r11
0x14000a511  pop     rdi
0x14000a512  retn
```
