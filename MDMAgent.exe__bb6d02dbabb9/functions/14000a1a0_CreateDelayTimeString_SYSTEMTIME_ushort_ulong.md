# CreateDelayTimeString(_SYSTEMTIME *,ushort *,ulong)

- ea: `0x14000a1a0`
- end: `0x14000a36d`
- name: `?CreateDelayTimeString@@YAJPEAU_SYSTEMTIME@@PEAGK@Z`
- size: `461`
- prototype: `int(struct _SYSTEMTIME *, unsigned __int16 *, unsigned int)`
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
- `0x14000a1a0`

## pseudocode

```c
int __fastcall CreateDelayTimeString(struct _SYSTEMTIME *a1, unsigned __int16 *a2)
{
  int result; // eax
  const unsigned __int16 *v5; // r8
  const unsigned __int16 *v6; // r8
  const unsigned __int16 *v7; // r8
  const unsigned __int16 *v8; // r8
  unsigned __int16 v9[264]; // [rsp+20h] [rbp-238h] BYREF

  v9[0] = 0;
  memset_0(&v9[1], 0, 0x206u);
  if ( !a1 || !a2 )
    return -2147024809;
  result = StringCchPrintfW(a2, 0x104u, L"%d-", a1->wYear, *(_QWORD *)v9);
  if ( result >= 0 )
  {
    v5 = L"0%d-";
    if ( a1->wMonth >= 0xAu )
      v5 = L"%d-";
    result = StringCchPrintfW(v9, 0x104u, v5, a1->wMonth);
    if ( result >= 0 )
    {
      result = StringCchCatW(a2, 0x104u, v9);
      if ( result >= 0 )
      {
        v6 = L"0%dT";
        if ( a1->wDay >= 0xAu )
          v6 = L"%dT";
        result = StringCchPrintfW(v9, 0x104u, v6, a1->wDay);
        if ( result >= 0 )
        {
          result = StringCchCatW(a2, 0x104u, v9);
          if ( result >= 0 )
          {
            v7 = L"0%d:";
            if ( a1->wHour >= 0xAu )
              v7 = L"%d:";
            result = StringCchPrintfW(v9, 0x104u, v7, a1->wHour);
            if ( result >= 0 )
            {
              result = StringCchCatW(a2, 0x104u, v9);
              if ( result >= 0 )
              {
                v8 = L"0%d:00";
                if ( a1->wMinute >= 0xAu )
                  v8 = L"%d:00";
                result = StringCchPrintfW(v9, 0x104u, v8, a1->wMinute);
                if ( result >= 0 )
                {
                  result = StringCchCatW(a2, 0x104u, v9);
                  if ( result >= 0 )
                    return StringCchCatW(a2, 0x104u, L"Z");
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000a1a0  mov     [rsp+arg_10], rbx
0x14000a1a5  mov     [rsp+arg_18], rbp
0x14000a1aa  push    rsi
0x14000a1ab  push    rdi
0x14000a1ac  push    r14
0x14000a1ae  sub     rsp, 240h
0x14000a1b5  mov     rax, cs:__security_cookie
0x14000a1bc  xor     rax, rsp
0x14000a1bf  mov     [rsp+258h+var_28], rax
0x14000a1c7  mov     rbx, rdx
0x14000a1ca  mov     rdi, rcx
0x14000a1cd  xor     eax, eax
0x14000a1cf  lea     rcx, [rsp+258h+var_236]; void *
0x14000a1d4  xor     edx, edx; Val
0x14000a1d6  mov     [rsp+258h+var_238], ax
0x14000a1db  mov     r8d, 206h; Size
0x14000a1e1  call    memset_0
0x14000a1e6  test    rdi, rdi
0x14000a1e9  jz      loc_14000A33F
0x14000a1ef  test    rbx, rbx
0x14000a1f2  jz      loc_14000A33F
0x14000a1f8  movzx   r9d, word ptr [rdi]
0x14000a1fc  lea     rbp, aD_0; "%d-"
0x14000a203  mov     esi, 104h
0x14000a208  mov     r8, rbp; unsigned __int16 *
0x14000a20b  mov     edx, esi; unsigned __int64
0x14000a20d  mov     rcx, rbx; unsigned __int16 *
0x14000a210  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a215  test    eax, eax
0x14000a217  js      loc_14000A344
0x14000a21d  movzx   eax, word ptr [rdi+2]
0x14000a221  lea     r8, a0D_0; "0%d-"
0x14000a228  mov     r14d, 0Ah
0x14000a22e  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x14000a233  cmp     r14w, ax
0x14000a237  mov     r9d, eax
0x14000a23a  mov     edx, esi; unsigned __int64
0x14000a23c  cmovbe  r8, rbp; unsigned __int16 *
0x14000a240  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a245  test    eax, eax
0x14000a247  js      loc_14000A344
0x14000a24d  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x14000a252  mov     edx, esi; unsigned __int64
0x14000a254  mov     rcx, rbx; unsigned __int16 *
0x14000a257  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a25c  test    eax, eax
0x14000a25e  js      loc_14000A344
0x14000a264  movzx   eax, word ptr [rdi+6]
0x14000a268  lea     rcx, aDt; "%dT"
0x14000a26f  cmp     r14w, ax
0x14000a273  lea     r8, a0Dt; "0%dT"
0x14000a27a  mov     r9d, eax
0x14000a27d  mov     edx, esi; unsigned __int64
0x14000a27f  cmovbe  r8, rcx; unsigned __int16 *
0x14000a283  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x14000a288  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a28d  test    eax, eax
0x14000a28f  js      loc_14000A344
0x14000a295  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x14000a29a  mov     edx, esi; unsigned __int64
0x14000a29c  mov     rcx, rbx; unsigned __int16 *
0x14000a29f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a2a4  test    eax, eax
0x14000a2a6  js      loc_14000A344
0x14000a2ac  movzx   eax, word ptr [rdi+8]
0x14000a2b0  lea     rcx, aD; "%d:"
0x14000a2b7  cmp     r14w, ax
0x14000a2bb  lea     r8, a0D; "0%d:"
0x14000a2c2  mov     r9d, eax
0x14000a2c5  mov     edx, esi; unsigned __int64
0x14000a2c7  cmovbe  r8, rcx; unsigned __int16 *
0x14000a2cb  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x14000a2d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a2d5  test    eax, eax
0x14000a2d7  js      short loc_14000A344
0x14000a2d9  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x14000a2de  mov     edx, esi; unsigned __int64
0x14000a2e0  mov     rcx, rbx; unsigned __int16 *
0x14000a2e3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a2e8  test    eax, eax
0x14000a2ea  js      short loc_14000A344
0x14000a2ec  movzx   eax, word ptr [rdi+0Ah]
0x14000a2f0  lea     rcx, aD00; "%d:00"
0x14000a2f7  cmp     r14w, ax
0x14000a2fb  lea     r8, a0D00; "0%d:00"
0x14000a302  mov     r9d, eax
0x14000a305  mov     edx, esi; unsigned __int64
0x14000a307  cmovbe  r8, rcx; unsigned __int16 *
0x14000a30b  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x14000a310  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14000a315  test    eax, eax
0x14000a317  js      short loc_14000A344
0x14000a319  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x14000a31e  mov     edx, esi; unsigned __int64
0x14000a320  mov     rcx, rbx; unsigned __int16 *
0x14000a323  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a328  test    eax, eax
0x14000a32a  js      short loc_14000A344
0x14000a32c  lea     r8, aZ; "Z"
0x14000a333  mov     edx, esi; unsigned __int64
0x14000a335  mov     rcx, rbx; unsigned __int16 *
0x14000a338  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a33d  jmp     short loc_14000A344
0x14000a33f  mov     eax, 80070057h
0x14000a344  mov     rcx, [rsp+258h+var_28]
0x14000a34c  xor     rcx, rsp; StackCookie
0x14000a34f  call    __security_check_cookie
0x14000a354  lea     r11, [rsp+258h+var_18]
0x14000a35c  mov     rbx, [r11+30h]
0x14000a360  mov     rbp, [r11+38h]
0x14000a364  mov     rsp, r11
0x14000a367  pop     r14
0x14000a369  pop     rdi
0x14000a36a  pop     rsi
0x14000a36b  retn
```
