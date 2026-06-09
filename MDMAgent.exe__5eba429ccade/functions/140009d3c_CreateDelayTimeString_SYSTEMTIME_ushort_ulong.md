# CreateDelayTimeString(_SYSTEMTIME *,ushort *,ulong)

- ea: `0x140009d3c`
- end: `0x140009f08`
- name: `?CreateDelayTimeString@@YAJPEAU_SYSTEMTIME@@PEAGK@Z`
- size: `460`
- prototype: `int __fastcall(struct _SYSTEMTIME *, unsigned __int16 *)`
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
- `0x140009d3c`

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
0x140009d3c  mov     [rsp+arg_10], rbx
0x140009d41  mov     [rsp+arg_18], rbp
0x140009d46  push    rsi
0x140009d47  push    rdi
0x140009d48  push    r14
0x140009d4a  sub     rsp, 240h
0x140009d51  mov     rax, cs:__security_cookie
0x140009d58  xor     rax, rsp
0x140009d5b  mov     [rsp+258h+var_28], rax
0x140009d63  mov     rbx, rdx
0x140009d66  mov     rdi, rcx
0x140009d69  xor     eax, eax
0x140009d6b  lea     rcx, [rsp+258h+var_236]; void *
0x140009d70  xor     edx, edx; Val
0x140009d72  mov     [rsp+258h+var_238], ax
0x140009d77  mov     r8d, 206h; Size
0x140009d7d  call    memset_0
0x140009d82  test    rdi, rdi
0x140009d85  jz      loc_140009EDB
0x140009d8b  test    rbx, rbx
0x140009d8e  jz      loc_140009EDB
0x140009d94  movzx   r9d, word ptr [rdi]
0x140009d98  lea     rbp, aD_0; "%d-"
0x140009d9f  mov     esi, 104h
0x140009da4  mov     r8, rbp; unsigned __int16 *
0x140009da7  mov     edx, esi; unsigned __int64
0x140009da9  mov     rcx, rbx; unsigned __int16 *
0x140009dac  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009db1  test    eax, eax
0x140009db3  js      loc_140009EE0
0x140009db9  movzx   eax, word ptr [rdi+2]
0x140009dbd  lea     r8, a0D_0; "0%d-"
0x140009dc4  mov     r14d, 0Ah
0x140009dca  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x140009dcf  cmp     r14w, ax
0x140009dd3  mov     r9d, eax
0x140009dd6  mov     edx, esi; unsigned __int64
0x140009dd8  cmovbe  r8, rbp; unsigned __int16 *
0x140009ddc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009de1  test    eax, eax
0x140009de3  js      loc_140009EE0
0x140009de9  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x140009dee  mov     edx, esi; unsigned __int64
0x140009df0  mov     rcx, rbx; unsigned __int16 *
0x140009df3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009df8  test    eax, eax
0x140009dfa  js      loc_140009EE0
0x140009e00  movzx   eax, word ptr [rdi+6]
0x140009e04  lea     rcx, aDt; "%dT"
0x140009e0b  cmp     r14w, ax
0x140009e0f  lea     r8, a0Dt; "0%dT"
0x140009e16  mov     r9d, eax
0x140009e19  mov     edx, esi; unsigned __int64
0x140009e1b  cmovbe  r8, rcx; unsigned __int16 *
0x140009e1f  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x140009e24  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009e29  test    eax, eax
0x140009e2b  js      loc_140009EE0
0x140009e31  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x140009e36  mov     edx, esi; unsigned __int64
0x140009e38  mov     rcx, rbx; unsigned __int16 *
0x140009e3b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009e40  test    eax, eax
0x140009e42  js      loc_140009EE0
0x140009e48  movzx   eax, word ptr [rdi+8]
0x140009e4c  lea     rcx, aD; "%d:"
0x140009e53  cmp     r14w, ax
0x140009e57  lea     r8, a0D; "0%d:"
0x140009e5e  mov     r9d, eax
0x140009e61  mov     edx, esi; unsigned __int64
0x140009e63  cmovbe  r8, rcx; unsigned __int16 *
0x140009e67  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x140009e6c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009e71  test    eax, eax
0x140009e73  js      short loc_140009EE0
0x140009e75  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x140009e7a  mov     edx, esi; unsigned __int64
0x140009e7c  mov     rcx, rbx; unsigned __int16 *
0x140009e7f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009e84  test    eax, eax
0x140009e86  js      short loc_140009EE0
0x140009e88  movzx   eax, word ptr [rdi+0Ah]
0x140009e8c  lea     rcx, aD00; "%d:00"
0x140009e93  cmp     r14w, ax
0x140009e97  lea     r8, a0D00; "0%d:00"
0x140009e9e  mov     r9d, eax
0x140009ea1  mov     edx, esi; unsigned __int64
0x140009ea3  cmovbe  r8, rcx; unsigned __int16 *
0x140009ea7  lea     rcx, [rsp+258h+var_238]; unsigned __int16 *
0x140009eac  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009eb1  test    eax, eax
0x140009eb3  js      short loc_140009EE0
0x140009eb5  lea     r8, [rsp+258h+var_238]; unsigned __int16 *
0x140009eba  mov     edx, esi; unsigned __int64
0x140009ebc  mov     rcx, rbx; unsigned __int16 *
0x140009ebf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009ec4  test    eax, eax
0x140009ec6  js      short loc_140009EE0
0x140009ec8  lea     r8, aZ; "Z"
0x140009ecf  mov     edx, esi; unsigned __int64
0x140009ed1  mov     rcx, rbx; unsigned __int16 *
0x140009ed4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140009ed9  jmp     short loc_140009EE0
0x140009edb  mov     eax, 80070057h
0x140009ee0  mov     rcx, [rsp+258h+var_28]
0x140009ee8  xor     rcx, rsp; StackCookie
0x140009eeb  call    __security_check_cookie
0x140009ef0  lea     r11, [rsp+258h+var_18]
0x140009ef8  mov     rbx, [r11+30h]
0x140009efc  mov     rbp, [r11+38h]
0x140009f00  mov     rsp, r11
0x140009f03  pop     r14
0x140009f05  pop     rdi
0x140009f06  pop     rsi
0x140009f07  retn
```
