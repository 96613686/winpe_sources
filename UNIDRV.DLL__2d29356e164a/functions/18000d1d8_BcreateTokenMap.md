# BcreateTokenMap

- ea: `0x18000d1d8`
- end: `0x18000d4f6`
- name: `BcreateTokenMap`
- size: `798`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800701a8`

## callees

- `0x180007220`
- `0x180008fc8`
- `0x18000ca18`
- `0x18000d1d8`
- `0x18000d500`
- `0x18000da70`
- `0x18000def0`
- `0x18000e0c0`
- `0x18000e498`
- `0x18000e508`
- `0x18003d144`
- `0x18004485c`
- `0x180047da0`

## string_xrefs

- `0x18000d4b9`: `Internal: no more tokenmap elements - restart.`
- `0x18000d452`: `BcreateTokenMap`
- `0x18000d487`: `BcreateTokenMap`
- `0x18000d4c0`: `BcreateTokenMap`

## pseudocode

```c
__int64 __fastcall BcreateTokenMap(STRSAFE_LPCWSTR pszSrc, __int64 a2)
{
  int v4; // r8d
  int v6; // edi
  int v7; // edi
  int v8; // edi
  int v9; // edi
  int v10; // edi
  int v11; // eax
  __int64 v12; // rdi
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // r9
  char v16; // dl
  int v17; // edi
  _QWORD v18[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v19; // [rsp+68h] [rbp+28h] BYREF

  v19 = 0;
  *(_DWORD *)(a2 + 2560) = 0;
  *(_DWORD *)(a2 + 736) = 0;
  if ( !(unsigned int)DefineSymbol("WINNT_40")
    || !(unsigned int)DefineSymbol("WINNT_50")
    || !(unsigned int)DefineSymbol("WINNT_51")
    || !(unsigned int)DefineSymbol("WINNT_60") )
  {
    return 0;
  }
  v18[1] = 14;
  v18[0] = "PARSER_VER_1.0";
  if ( (unsigned int)DWregisterSymbol((unsigned int)v18, 15, v4, -1, a2) != -1 )
  {
    if ( !(unsigned int)BloadFile(pszSrc, a2) || !(unsigned int)BPreProcess(a2) )
      return 0;
LABEL_10:
    v6 = 2;
    while ( 1 )
    {
      if ( !v6 )
        return 1;
      if ( v19 >= *(_DWORD *)(a2 + 488) )
      {
        WriteDbgTraceErrorGpd("BcreateTokenMap", "Internal: no more tokenmap elements - restart.");
        if ( *(int *)(a2 + 2220) < 2 )
        {
          *(_DWORD *)(a2 + 2220) = 2;
          *(_DWORD *)(a2 + 2224) = 2;
          *(_DWORD *)(a2 + 2216) = 20;
        }
        return 0;
      }
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          v9 = v8 - 1;
          if ( v9 )
          {
            v10 = v9 - 1;
            if ( !v10 )
            {
              v11 = PARSTparseValue(&v19, a2);
              goto LABEL_18;
            }
            v17 = v10 - 1;
            if ( v17 )
            {
              if ( v17 != 1 )
              {
                WriteDbgTraceErrorGpd("BcreateTokenMap", "Internal error: no other PARST_ states exist!");
                if ( *(int *)(a2 + 2220) < 3 )
                {
                  *(_DWORD *)(a2 + 2220) = 3;
                  *(_DWORD *)(a2 + 2224) = 4;
                }
              }
              return 0;
            }
            v6 = PARSTloadIncludeFile(&v19, pszSrc, a2);
LABEL_27:
            if ( !(unsigned int)BPreProcess(a2) )
              return 0;
          }
          else
          {
            v12 = *(_QWORD *)(a2 + 480);
            if ( !(unsigned int)BeatArbitraryWhite(a2) )
              goto LABEL_23;
            v13 = *(_QWORD *)(a2 + 456);
            v14 = 32LL * (unsigned int)(*(_DWORD *)(a2 + 468) - 1);
            v15 = *(unsigned int *)(v14 + v13 + 8);
            v16 = *(_BYTE *)(v15 + *(_QWORD *)(v14 + v13));
            if ( v16 != 58 )
            {
              if ( v16 == 10 || v16 == 13 )
              {
LABEL_23:
                *(_DWORD *)(56LL * v19++ + v12 + 52) |= 1u;
                goto LABEL_10;
              }
              vIdentifySource(v12 + 56LL * v19, a2);
              WriteDbgTraceErrorGpd(
                "PARSTparseColon",
                "Colon expected after keyword: *%0.*s.",
                *(_DWORD *)(56LL * v19 + v12 + 16),
                *(const char **)(56LL * v19 + v12 + 8));
              BeatComment(a2);
              *(_DWORD *)(56LL * v19 + v12 + 52) = 0;
              goto LABEL_10;
            }
            v6 = 4;
            *(_DWORD *)(v14 + v13 + 8) = v15 + 1;
          }
        }
        else
        {
          v11 = PARSTscanForKeyword(&v19, a2);
LABEL_18:
          v6 = v11;
        }
      }
      else
      {
        v6 = PARSTrestorePrevsFile(&v19, a2);
        if ( v6 )
          goto LABEL_27;
        if ( *(_DWORD *)(a2 + 708) && *(_DWORD *)(a2 + 2220) != 3 )
        {
          WriteDbgTraceErrorGpd("BcreateTokenMap", "EOF reached before #Endif: was parsed!");
          *(_DWORD *)(a2 + 2224) = 1;
          *(_DWORD *)(a2 + 2220) = 3;
          return 0;
        }
      }
    }
  }
  WriteDbgTraceErrorGpd("DefineSymbol", "Internal error, unable to define %s!", "PARSER_VER_1.0");
  return 0;
}

```

## disassembly

```asm
0x18000d1d8  mov     [rsp-18h+arg_0], rbx
0x18000d1dd  mov     [rsp-18h+arg_10], rsi
0x18000d1e2  push    rbp
0x18000d1e3  push    rdi
0x18000d1e4  push    r15
0x18000d1e6  mov     rbp, rsp
0x18000d1e9  sub     rsp, 40h
0x18000d1ed  mov     rsi, rcx
0x18000d1f0  mov     [rbp+arg_8], 0
0x18000d1f7  lea     rcx, aWinnt40; "WINNT_40"
0x18000d1fe  mov     dword ptr [rdx+0A00h], 0
0x18000d208  mov     rbx, rdx
0x18000d20b  mov     dword ptr [rdx+2E0h], 0
0x18000d215  call    DefineSymbol
0x18000d21a  test    eax, eax
0x18000d21c  jz      short loc_18000D29D
0x18000d21e  mov     rdx, rbx
0x18000d221  lea     rcx, aWinnt50; "WINNT_50"
0x18000d228  call    DefineSymbol
0x18000d22d  test    eax, eax
0x18000d22f  jz      short loc_18000D29D
0x18000d231  mov     rdx, rbx
0x18000d234  lea     rcx, aWinnt51; "WINNT_51"
0x18000d23b  call    DefineSymbol
0x18000d240  test    eax, eax
0x18000d242  jz      short loc_18000D29D
0x18000d244  mov     rdx, rbx
0x18000d247  lea     rcx, aWinnt60; "WINNT_60"
0x18000d24e  call    DefineSymbol
0x18000d253  test    eax, eax
0x18000d255  jz      short loc_18000D29D
0x18000d257  or      edi, 0FFFFFFFFh
0x18000d25a  mov     [rbp+var_8], 0Eh
0x18000d262  lea     r15, aParserVer10; "PARSER_VER_1.0"
0x18000d269  mov     [rsp+40h+var_20], rbx
0x18000d26e  mov     r9d, edi
0x18000d271  mov     [rbp+var_10], r15
0x18000d275  mov     edx, 0Fh
0x18000d27a  lea     rcx, [rbp+var_10]
0x18000d27e  call    DWregisterSymbol
0x18000d283  cmp     eax, edi
0x18000d285  jnz     short loc_18000D2B2
0x18000d287  mov     r8, r15
0x18000d28a  lea     rdx, aInternalErrorU; "Internal error, unable to define %s!"
0x18000d291  lea     rcx, aDefinesymbol; "DefineSymbol"
0x18000d298  call    WriteDbgTraceErrorGpd
0x18000d29d  xor     eax, eax
0x18000d29f  mov     rbx, [rsp+40h+arg_0]
0x18000d2a4  mov     rsi, [rsp+40h+arg_10]
0x18000d2a9  add     rsp, 40h
0x18000d2ad  pop     r15
0x18000d2af  pop     rdi
0x18000d2b0  pop     rbp
0x18000d2b1  retn
0x18000d2b2  mov     rdx, rbx
0x18000d2b5  mov     rcx, rsi; pszSrc
0x18000d2b8  call    BloadFile
0x18000d2bd  test    eax, eax
0x18000d2bf  jz      short loc_18000D29D
0x18000d2c1  mov     rcx, rbx
0x18000d2c4  call    BPreProcess
0x18000d2c9  test    eax, eax
0x18000d2cb  jz      short loc_18000D29D
0x18000d2cd  mov     r15d, 2
0x18000d2d3  mov     edi, r15d
0x18000d2d6  test    edi, edi
0x18000d2d8  jz      loc_18000D386
0x18000d2de  mov     eax, [rbx+1E8h]
0x18000d2e4  cmp     [rbp+arg_8], eax
0x18000d2e7  jnb     loc_18000D4B9
0x18000d2ed  sub     edi, 1
0x18000d2f0  jz      loc_18000D41C
0x18000d2f6  sub     edi, 1
0x18000d2f9  jz      short loc_18000D364
0x18000d2fb  sub     edi, 1
0x18000d2fe  jz      short loc_18000D319
0x18000d300  sub     edi, 1
0x18000d303  jnz     loc_18000D390
0x18000d309  mov     rdx, rbx
0x18000d30c  lea     rcx, [rbp+arg_8]
0x18000d310  call    PARSTparseValue
0x18000d315  mov     edi, eax
0x18000d317  jmp     short loc_18000D2D6
0x18000d319  mov     rdi, [rbx+1E0h]
0x18000d320  mov     rcx, rbx
0x18000d323  call    BeatArbitraryWhite
0x18000d328  test    eax, eax
0x18000d32a  jz      short loc_18000D372
0x18000d32c  mov     ecx, [rbx+1D4h]
0x18000d332  mov     r8, [rbx+1C8h]
0x18000d339  dec     ecx
0x18000d33b  shl     rcx, 5
0x18000d33f  mov     r9d, [rcx+r8+8]
0x18000d344  mov     rax, [rcx+r8]
0x18000d348  mov     dl, [r9+rax]
0x18000d34c  cmp     dl, 3Ah ; ':'
0x18000d34f  jnz     short loc_18000D3BF
0x18000d351  lea     eax, [r9+1]
0x18000d355  mov     edi, 4
0x18000d35a  mov     [rcx+r8+8], eax
0x18000d35f  jmp     loc_18000D2D6
0x18000d364  mov     rdx, rbx
0x18000d367  lea     rcx, [rbp+arg_8]
0x18000d36b  call    PARSTscanForKeyword
0x18000d370  jmp     short loc_18000D315
0x18000d372  mov     eax, [rbp+arg_8]
0x18000d375  imul    rcx, rax, 38h ; '8'
0x18000d379  or      dword ptr [rcx+rdi+34h], 1
0x18000d37e  inc     [rbp+arg_8]
0x18000d381  jmp     loc_18000D2D3
0x18000d386  mov     eax, 1
0x18000d38b  jmp     loc_18000D29F
0x18000d390  sub     edi, 1
0x18000d393  jnz     loc_18000D477
0x18000d399  mov     r8, rbx
0x18000d39c  lea     rcx, [rbp+arg_8]
0x18000d3a0  mov     rdx, rsi
0x18000d3a3  call    PARSTloadIncludeFile
0x18000d3a8  mov     edi, eax
0x18000d3aa  mov     rcx, rbx
0x18000d3ad  call    BPreProcess
0x18000d3b2  test    eax, eax
0x18000d3b4  jnz     loc_18000D2D6
0x18000d3ba  jmp     loc_18000D29D
0x18000d3bf  cmp     dl, 0Ah
0x18000d3c2  jz      short loc_18000D372
0x18000d3c4  cmp     dl, 0Dh
0x18000d3c7  jz      short loc_18000D372
0x18000d3c9  mov     eax, [rbp+arg_8]
0x18000d3cc  mov     rdx, rbx
0x18000d3cf  imul    rcx, rax, 38h ; '8'
0x18000d3d3  add     rcx, rdi
0x18000d3d6  call    vIdentifySource
0x18000d3db  mov     eax, [rbp+arg_8]
0x18000d3de  lea     rdx, aColonExpectedA; "Colon expected after keyword: *%0.*s."
0x18000d3e5  imul    r8, rax, 38h ; '8'
0x18000d3e9  lea     rcx, aParstparsecolo; "PARSTparseColon"
0x18000d3f0  mov     r9, [r8+rdi+8]
0x18000d3f5  mov     r8d, [r8+rdi+10h]
0x18000d3fa  call    WriteDbgTraceErrorGpd
0x18000d3ff  mov     rcx, rbx
0x18000d402  call    BeatComment
0x18000d407  mov     r11d, [rbp+arg_8]
0x18000d40b  imul    rax, r11, 38h ; '8'
0x18000d40f  mov     dword ptr [rax+rdi+34h], 0
0x18000d417  jmp     loc_18000D2D3
0x18000d41c  mov     rdx, rbx
0x18000d41f  lea     rcx, [rbp+arg_8]
0x18000d423  call    PARSTrestorePrevsFile
0x18000d428  mov     edi, eax
0x18000d42a  test    eax, eax
0x18000d42c  jnz     loc_18000D3AA
0x18000d432  cmp     [rbx+2C4h], eax
0x18000d438  jz      loc_18000D2D6
0x18000d43e  cmp     dword ptr [rbx+8ACh], 3
0x18000d445  jz      loc_18000D2D6
0x18000d44b  lea     rdx, aEofReachedBefo; "EOF reached before #Endif: was parsed!"
0x18000d452  lea     rcx, aBcreatetokenma; "BcreateTokenMap"
0x18000d459  call    WriteDbgTraceErrorGpd
0x18000d45e  mov     dword ptr [rbx+8B0h], 1
0x18000d468  mov     dword ptr [rbx+8ACh], 3
0x18000d472  jmp     loc_18000D29D
0x18000d477  cmp     edi, 1
0x18000d47a  jz      loc_18000D29D
0x18000d480  lea     rdx, aInternalErrorN; "Internal error: no other PARST_ states "...
0x18000d487  lea     rcx, aBcreatetokenma; "BcreateTokenMap"
0x18000d48e  call    WriteDbgTraceErrorGpd
0x18000d493  cmp     dword ptr [rbx+8ACh], 3
0x18000d49a  jge     loc_18000D29D
0x18000d4a0  mov     dword ptr [rbx+8ACh], 3
0x18000d4aa  mov     dword ptr [rbx+8B0h], 4
0x18000d4b4  jmp     loc_18000D29D
0x18000d4b9  lea     rdx, aInternalNoMore; "Internal: no more tokenmap elements - r"...
0x18000d4c0  lea     rcx, aBcreatetokenma; "BcreateTokenMap"
0x18000d4c7  call    WriteDbgTraceErrorGpd
0x18000d4cc  cmp     [rbx+8ACh], r15d
0x18000d4d3  jge     loc_18000D29D
0x18000d4d9  mov     [rbx+8ACh], r15d
0x18000d4e0  mov     [rbx+8B0h], r15d
0x18000d4e7  mov     dword ptr [rbx+8A8h], 14h
0x18000d4f1  jmp     loc_18000D29D
```
