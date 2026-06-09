# CreateScheduleTimeString

- ea: `0x180008a2c`
- end: `0x180008bcc`
- name: `CreateScheduleTimeString`
- size: `416`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180007f4c`
- `0x18000ef24`

## callees

- `0x180001c60`
- `0x1800026d8`
- `0x1800051d8`
- `0x180008a2c`
- `0x18000ff18`

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
0x180008a2c  mov     [rsp+arg_10], rbx
0x180008a31  mov     [rsp+arg_18], rsi
0x180008a36  push    rdi
0x180008a37  sub     rsp, 240h
0x180008a3e  mov     rax, cs:__security_cookie
0x180008a45  xor     rax, rsp
0x180008a48  mov     [rsp+248h+var_18], rax
0x180008a50  mov     rdi, rdx
0x180008a53  mov     rbx, rcx
0x180008a56  xor     eax, eax
0x180008a58  lea     rcx, [rsp+248h+var_226]; void *
0x180008a5d  xor     edx, edx; Val
0x180008a5f  mov     [rsp+248h+var_228], ax
0x180008a64  mov     r8d, 206h; Size
0x180008a6a  call    memset_0
0x180008a6f  test    rbx, rbx
0x180008a72  jz      loc_180008BA1
0x180008a78  test    rdi, rdi
0x180008a7b  jz      loc_180008BA1
0x180008a81  mov     esi, 104h
0x180008a86  lea     r8, aP; "P"
0x180008a8d  mov     edx, esi; unsigned __int64
0x180008a8f  mov     rcx, rdi; unsigned __int16 *
0x180008a92  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008a97  mov     edx, eax
0x180008a99  test    eax, eax
0x180008a9b  js      loc_180008B9D
0x180008aa1  xor     ecx, ecx
0x180008aa3  cmp     cx, [rbx]
0x180008aa6  jnz     loc_180008BA1
0x180008aac  cmp     cx, [rbx+2]
0x180008ab0  jz      short loc_180008AB8
0x180008ab2  mov     word ptr [rbx+6], 1Fh
0x180008ab8  xor     eax, eax
0x180008aba  cmp     ax, [rbx+6]
0x180008abe  jz      short loc_180008AFD
0x180008ac0  movzx   r9d, word ptr [rbx+6]
0x180008ac5  lea     r8, aDd; "%dD"
0x180008acc  mov     rdx, rsi; unsigned __int64
0x180008acf  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x180008ad4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008ad9  mov     edx, eax
0x180008adb  test    eax, eax
0x180008add  js      loc_180008B9D
0x180008ae3  lea     r8, [rsp+248h+var_228]; unsigned __int16 *
0x180008ae8  mov     rdx, rsi; unsigned __int64
0x180008aeb  mov     rcx, rdi; unsigned __int16 *
0x180008aee  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008af3  mov     edx, eax
0x180008af5  test    eax, eax
0x180008af7  js      loc_180008B9D
0x180008afd  xor     eax, eax
0x180008aff  cmp     ax, [rbx+8]
0x180008b03  jnz     short loc_180008B0F
0x180008b05  cmp     ax, [rbx+0Ah]
0x180008b09  jz      loc_180008B9D
0x180008b0f  lea     r8, aT; "T"
0x180008b16  mov     rdx, rsi; unsigned __int64
0x180008b19  mov     rcx, rdi; unsigned __int16 *
0x180008b1c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008b21  mov     edx, eax
0x180008b23  test    eax, eax
0x180008b25  js      short loc_180008B9D
0x180008b27  xor     eax, eax
0x180008b29  cmp     ax, [rbx+8]
0x180008b2d  jz      short loc_180008B64
0x180008b2f  movzx   r9d, word ptr [rbx+8]
0x180008b34  lea     r8, aDh; "%dH"
0x180008b3b  mov     rdx, rsi; unsigned __int64
0x180008b3e  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x180008b43  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008b48  mov     edx, eax
0x180008b4a  test    eax, eax
0x180008b4c  js      short loc_180008B9D
0x180008b4e  lea     r8, [rsp+248h+var_228]; unsigned __int16 *
0x180008b53  mov     rdx, rsi; unsigned __int64
0x180008b56  mov     rcx, rdi; unsigned __int16 *
0x180008b59  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008b5e  mov     edx, eax
0x180008b60  test    eax, eax
0x180008b62  js      short loc_180008B9D
0x180008b64  xor     eax, eax
0x180008b66  cmp     ax, [rbx+0Ah]
0x180008b6a  jz      short loc_180008B9D
0x180008b6c  movzx   r9d, word ptr [rbx+0Ah]
0x180008b71  lea     r8, aDm; "%dM"
0x180008b78  mov     rdx, rsi; unsigned __int64
0x180008b7b  lea     rcx, [rsp+248h+var_228]; unsigned __int16 *
0x180008b80  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008b85  mov     edx, eax
0x180008b87  test    eax, eax
0x180008b89  js      short loc_180008B9D
0x180008b8b  lea     r8, [rsp+248h+var_228]; unsigned __int16 *
0x180008b90  mov     rdx, rsi; unsigned __int64
0x180008b93  mov     rcx, rdi; unsigned __int16 *
0x180008b96  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008b9b  mov     edx, eax
0x180008b9d  mov     eax, edx
0x180008b9f  jmp     short loc_180008BA6
0x180008ba1  mov     eax, 80070057h
0x180008ba6  mov     rcx, [rsp+248h+var_18]
0x180008bae  xor     rcx, rsp; StackCookie
0x180008bb1  call    __security_check_cookie
0x180008bb6  lea     r11, [rsp+248h+var_8]
0x180008bbe  mov     rbx, [r11+20h]
0x180008bc2  mov     rsi, [r11+28h]
0x180008bc6  mov     rsp, r11
0x180008bc9  pop     rdi
0x180008bca  retn
```
