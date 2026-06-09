# CreateDelayTimeString(_SYSTEMTIME *,ushort *,ulong)

- ea: `0x180008730`
- end: `0x1800088fd`
- name: `?CreateDelayTimeString@@YAJPEAU_SYSTEMTIME@@PEAGK@Z`
- size: `461`
- prototype: `int(struct _SYSTEMTIME *, unsigned __int16 *, unsigned int)`
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
- `0x180008730`
- `0x18000ff18`

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
0x180008730  mov     [rsp+arg_10], rbx
0x180008735  mov     [rsp+arg_18], rbp
0x18000873a  push    rsi
0x18000873b  push    rdi
0x18000873c  push    r14
0x18000873e  sub     rsp, 240h
0x180008745  mov     rax, cs:__security_cookie
0x18000874c  xor     rax, rsp
0x18000874f  mov     [rsp+258h+var_28], rax
0x180008757  mov     rbx, rdx
0x18000875a  mov     rdi, rcx
0x18000875d  xor     eax, eax
0x18000875f  lea     rcx, [rsp+258h+var_236]; void *
0x180008764  xor     edx, edx; Val
0x180008766  mov     [rsp+258h+var_238], ax
0x18000876b  mov     r8d, 206h; Size
0x180008771  call    memset_0
0x180008776  test    rdi, rdi
0x180008779  jz      loc_1800088CF
0x18000877f  test    rbx, rbx
0x180008782  jz      loc_1800088CF
0x180008788  movzx   r9d, word ptr [rdi]
0x18000878c  lea     rbp, aD_1; "%d-"
0x180008793  mov     esi, 104h
0x180008798  mov     r8, rbp; unsigned __int16 *
0x18000879b  mov     edx, esi; unsigned __int64
0x18000879d  mov     rcx, rbx; unsigned __int16 *
0x1800087a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800087a5  test    eax, eax
0x1800087a7  js      loc_1800088D4
0x1800087ad  movzx   eax, word ptr [rdi+2]
0x1800087b1  lea     r8, a0D_0; "0%d-"
0x1800087b8  mov     r14d, 0Ah
0x1800087be  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x1800087c3  cmp     r14w, ax
0x1800087c7  mov     r9d, eax
0x1800087ca  mov     edx, esi; unsigned __int64
0x1800087cc  cmovbe  r8, rbp; unsigned __int16 *
0x1800087d0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800087d5  test    eax, eax
0x1800087d7  js      loc_1800088D4
0x1800087dd  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x1800087e2  mov     edx, esi; unsigned __int64
0x1800087e4  mov     rcx, rbx; unsigned __int16 *
0x1800087e7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800087ec  test    eax, eax
0x1800087ee  js      loc_1800088D4
0x1800087f4  movzx   eax, word ptr [rdi+6]
0x1800087f8  lea     rcx, aDt; "%dT"
0x1800087ff  cmp     r14w, ax
0x180008803  lea     r8, a0Dt; "0%dT"
0x18000880a  mov     r9d, eax
0x18000880d  mov     edx, esi; unsigned __int64
0x18000880f  cmovbe  r8, rcx; unsigned __int16 *
0x180008813  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x180008818  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000881d  test    eax, eax
0x18000881f  js      loc_1800088D4
0x180008825  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x18000882a  mov     edx, esi; unsigned __int64
0x18000882c  mov     rcx, rbx; unsigned __int16 *
0x18000882f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008834  test    eax, eax
0x180008836  js      loc_1800088D4
0x18000883c  movzx   eax, word ptr [rdi+8]
0x180008840  lea     rcx, aD; "%d:"
0x180008847  cmp     r14w, ax
0x18000884b  lea     r8, a0D; "0%d:"
0x180008852  mov     r9d, eax
0x180008855  mov     edx, esi; unsigned __int64
0x180008857  cmovbe  r8, rcx; unsigned __int16 *
0x18000885b  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x180008860  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008865  test    eax, eax
0x180008867  js      short loc_1800088D4
0x180008869  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x18000886e  mov     edx, esi; unsigned __int64
0x180008870  mov     rcx, rbx; unsigned __int16 *
0x180008873  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008878  test    eax, eax
0x18000887a  js      short loc_1800088D4
0x18000887c  movzx   eax, word ptr [rdi+0Ah]
0x180008880  lea     rcx, aD00; "%d:00"
0x180008887  cmp     r14w, ax
0x18000888b  lea     r8, a0D00; "0%d:00"
0x180008892  mov     r9d, eax
0x180008895  mov     edx, esi; unsigned __int64
0x180008897  cmovbe  r8, rcx; unsigned __int16 *
0x18000889b  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x1800088a0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800088a5  test    eax, eax
0x1800088a7  js      short loc_1800088D4
0x1800088a9  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x1800088ae  mov     edx, esi; unsigned __int64
0x1800088b0  mov     rcx, rbx; unsigned __int16 *
0x1800088b3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800088b8  test    eax, eax
0x1800088ba  js      short loc_1800088D4
0x1800088bc  lea     r8, aZ; "Z"
0x1800088c3  mov     edx, esi; unsigned __int64
0x1800088c5  mov     rcx, rbx; unsigned __int16 *
0x1800088c8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800088cd  jmp     short loc_1800088D4
0x1800088cf  mov     eax, 80070057h
0x1800088d4  mov     rcx, [rsp+258h+var_28]
0x1800088dc  xor     rcx, rsp; StackCookie
0x1800088df  call    __security_check_cookie
0x1800088e4  lea     r11, [rsp+258h+var_18]
0x1800088ec  mov     rbx, [r11+30h]
0x1800088f0  mov     rbp, [r11+38h]
0x1800088f4  mov     rsp, r11
0x1800088f7  pop     r14
0x1800088f9  pop     rdi
0x1800088fa  pop     rsi
0x1800088fb  retn
```
