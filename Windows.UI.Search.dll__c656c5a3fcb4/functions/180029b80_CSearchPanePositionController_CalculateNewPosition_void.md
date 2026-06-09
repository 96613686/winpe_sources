# CSearchPanePositionController::_CalculateNewPosition(void)

- ea: `0x180029b80`
- end: `0x180029cc6`
- name: `?_CalculateNewPosition@CSearchPanePositionController@@MEAAXXZ`
- size: `326`
- prototype: `void __fastcall(CSearchPanePositionController *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180029b80`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180029c69`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180029c69`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180029c43`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x180029c43`
- `SHCORE!GetScaleFactorForMonitor` at `0x180029c0d`
- `SHCORE!GetScaleFactorForMonitor` at `0x180029c0d`
- `USER32!SetRectEmpty` at `0x180029bad`
- `USER32!SetRectEmpty` at `0x180029bad`

## pseudocode

```c
void __fastcall CSearchPanePositionController::_CalculateNewPosition(struct tagRECT *this)
{
  struct tagRECT *v1; // rsi
  __int64 v3; // rcx
  __int64 v4; // rcx
  int v5; // eax
  int v6; // edi
  __int32 v7; // ebx
  LANGID UserDefaultUILanguage; // ax
  int v9; // [rsp+20h] [rbp-30h] BYREF
  WCHAR LCData[2]; // [rsp+24h] [rbp-2Ch] BYREF
  __int64 v11; // [rsp+28h] [rbp-28h] BYREF
  struct tagRECT v12; // [rsp+30h] [rbp-20h] BYREF

  v1 = this + 3;
  SetRectEmpty(this + 3);
  v3 = *(_QWORD *)&this[8].right;
  v12 = 0;
  if ( (*(int (__fastcall **)(__int64, __int64, struct tagRECT *))(*(_QWORD *)v3 + 56LL))(v3, 8, &v12) >= 0 )
  {
    v4 = *(_QWORD *)&this[6].left;
    v11 = 0;
    if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 40LL))(v4, &v11) >= 0 )
    {
      v9 = 0;
      if ( (int)GetScaleFactorForMonitor(v11, &v9) >= 0 )
      {
        v5 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
        v6 = (int)(float)((float)(346 * v9) / 100.0);
        if ( `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi == -1 )
        {
          v7 = 0;
          UserDefaultUILanguage = GetUserDefaultUILanguage();
          `IsBiDiLocalizedSystemEx'::`2'::s_langID = UserDefaultUILanguage;
          if ( UserDefaultUILanguage )
          {
            *(_DWORD *)LCData = 0;
            if ( GetLocaleInfoW(UserDefaultUILanguage, 0x20000070u, LCData, 2) > 0 )
              LOBYTE(v7) = *(_DWORD *)LCData == 1;
          }
          _InterlockedExchange(&`IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi, v7);
          v5 = `IsBiDiLocalizedSystemEx'::`2'::s_tbBiDi;
        }
        if ( v5 == 1 )
          v12.right = v6 + v12.left;
        else
          v12.left = v12.right - v6;
        *v1 = v12;
      }
    }
  }
}

```

## disassembly

```asm
0x180029b80  mov     [rsp-18h+arg_8], rbx
0x180029b85  mov     [rsp-18h+arg_10], rsi
0x180029b8a  push    rbp
0x180029b8b  push    rdi
0x180029b8c  push    r14
0x180029b8e  mov     rbp, rsp
0x180029b91  sub     rsp, 50h
0x180029b95  mov     rax, cs:__security_cookie
0x180029b9c  xor     rax, rsp
0x180029b9f  mov     [rbp+var_10], rax
0x180029ba3  lea     rsi, [rcx+30h]
0x180029ba7  mov     rbx, rcx
0x180029baa  mov     rcx, rsi; lprc
0x180029bad  call    cs:__imp_SetRectEmpty
0x180029bb3  mov     rcx, [rbx+88h]
0x180029bba  lea     r8, [rbp+var_20]
0x180029bbe  xorps   xmm0, xmm0
0x180029bc1  mov     edx, 8
0x180029bc6  movups  [rbp+var_20], xmm0
0x180029bca  mov     rax, [rcx]
0x180029bcd  mov     rax, [rax+38h]
0x180029bd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bd6  xor     r14d, r14d
0x180029bd9  test    eax, eax
0x180029bdb  js      loc_180029CA5
0x180029be1  mov     rcx, [rbx+60h]
0x180029be5  lea     rdx, [rbp+var_28]
0x180029be9  mov     [rbp+var_28], r14
0x180029bed  mov     rax, [rcx]
0x180029bf0  mov     rax, [rax+28h]
0x180029bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bf9  test    eax, eax
0x180029bfb  js      loc_180029CA5
0x180029c01  mov     rcx, [rbp+var_28]
0x180029c05  lea     rdx, [rbp+var_30]
0x180029c09  mov     [rbp+var_30], r14d
0x180029c0d  call    cs:__imp_GetScaleFactorForMonitor
0x180029c13  test    eax, eax
0x180029c15  js      loc_180029CA5
0x180029c1b  imul    eax, [rbp+var_30], 15Ah
0x180029c22  movd    xmm0, eax
0x180029c26  mov     eax, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x180029c2c  cvtdq2ps xmm0, xmm0
0x180029c2f  divss   xmm0, cs:__real@42c80000
0x180029c37  cvttss2si edi, xmm0
0x180029c3b  cmp     eax, 0FFFFFFFFh
0x180029c3e  jnz     short loc_180029C86
0x180029c40  mov     ebx, r14d
0x180029c43  call    cs:__imp_GetUserDefaultUILanguage
0x180029c49  mov     cs:?s_langID@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4GA, ax; ushort `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_langID
0x180029c50  test    ax, ax
0x180029c53  jz      short loc_180029C7A
0x180029c55  movzx   ecx, ax; Locale
0x180029c58  lea     r9d, [r14+2]; cchData
0x180029c5c  lea     r8, [rbp+LCData]; lpLCData
0x180029c60  mov     dword ptr [rbp+LCData], r14d
0x180029c64  mov     edx, 20000070h; LCType
0x180029c69  call    cs:__imp_GetLocaleInfoW
0x180029c6f  test    eax, eax
0x180029c71  jle     short loc_180029C7A
0x180029c73  cmp     dword ptr [rbp+LCData], 1
0x180029c77  setz    bl
0x180029c7a  xchg    ebx, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x180029c80  mov     eax, cs:?s_tbBiDi@?1??IsBiDiLocalizedSystemEx@@YAHPEAG@Z@4JA; long `IsBiDiLocalizedSystemEx(ushort *)'::`2'::s_tbBiDi
0x180029c86  cmp     eax, 1
0x180029c89  jnz     short loc_180029C95
0x180029c8b  mov     ecx, dword ptr [rbp+var_20]
0x180029c8e  add     ecx, edi
0x180029c90  mov     dword ptr [rbp+var_20+8], ecx
0x180029c93  jmp     short loc_180029C9D
0x180029c95  mov     eax, dword ptr [rbp+var_20+8]
0x180029c98  sub     eax, edi
0x180029c9a  mov     dword ptr [rbp+var_20], eax
0x180029c9d  movups  xmm0, [rbp+var_20]
0x180029ca1  movdqu  xmmword ptr [rsi], xmm0
0x180029ca5  mov     rcx, [rbp+var_10]
0x180029ca9  xor     rcx, rsp; StackCookie
0x180029cac  call    __security_check_cookie
0x180029cb1  lea     r11, [rsp+50h+var_s0]
0x180029cb6  mov     rbx, [r11+28h]
0x180029cba  mov     rsi, [r11+30h]
0x180029cbe  mov     rsp, r11
0x180029cc1  pop     r14
0x180029cc3  pop     rdi
0x180029cc4  pop     rbp
0x180029cc5  retn
```
