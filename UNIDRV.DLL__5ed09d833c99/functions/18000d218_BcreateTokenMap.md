# BcreateTokenMap

- ea: `0x18000d218`
- end: `0x18000d537`
- name: `BcreateTokenMap`
- size: `799`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800721d0`

## callees

- `0x180007150`
- `0x180008f8c`
- `0x18000ca1c`
- `0x18000d218`
- `0x18000d540`
- `0x18000dac0`
- `0x18000df40`
- `0x18000e110`
- `0x18000e4ec`
- `0x18000e55c`
- `0x18003df5c`
- `0x180045aa4`
- `0x180049248`

## string_xrefs

- `0x18000d4fa`: `Internal: no more tokenmap elements - restart.`
- `0x18000d493`: `BcreateTokenMap`
- `0x18000d4c8`: `BcreateTokenMap`
- `0x18000d501`: `BcreateTokenMap`

## pseudocode

```c
__int64 __fastcall BcreateTokenMap(STRSAFE_LPCWSTR pszSrc, __int64 a2, __int64 a3)
{
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8
  int v10; // edi
  int v11; // edi
  int v12; // edi
  int v13; // edi
  int v14; // edi
  int v15; // eax
  __int64 v16; // rdi
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // r9
  char v20; // dl
  int v21; // edi
  _QWORD v22[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v23; // [rsp+68h] [rbp+28h] BYREF

  v23 = 0;
  *(_DWORD *)(a2 + 2560) = 0;
  *(_DWORD *)(a2 + 736) = 0;
  if ( !(unsigned int)DefineSymbol("WINNT_40", a2, a3)
    || !(unsigned int)DefineSymbol("WINNT_50", a2, v5)
    || !(unsigned int)DefineSymbol("WINNT_51", a2, v6)
    || !(unsigned int)DefineSymbol("WINNT_60", a2, v7) )
  {
    return 0;
  }
  v22[1] = 14;
  v22[0] = "PARSER_VER_1.0";
  if ( (unsigned int)DWregisterSymbol((__int64)v22, 15, v8, -1, a2) != -1 )
  {
    if ( !(unsigned int)BloadFile(pszSrc, a2) || !(unsigned int)BPreProcess(a2) )
      return 0;
LABEL_10:
    v10 = 2;
    while ( 1 )
    {
      if ( !v10 )
        return 1;
      if ( v23 >= *(_DWORD *)(a2 + 488) )
      {
        WriteDbgTraceErrorGpd((__int64)"BcreateTokenMap", "Internal: no more tokenmap elements - restart.");
        if ( *(int *)(a2 + 2220) < 2 )
        {
          *(_DWORD *)(a2 + 2220) = 2;
          *(_DWORD *)(a2 + 2224) = 2;
          *(_DWORD *)(a2 + 2216) = 20;
        }
        return 0;
      }
      v11 = v10 - 1;
      if ( v11 )
      {
        v12 = v11 - 1;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( !v14 )
            {
              v15 = PARSTparseValue(&v23, a2);
              goto LABEL_18;
            }
            v21 = v14 - 1;
            if ( v21 )
            {
              if ( v21 != 1 )
              {
                WriteDbgTraceErrorGpd((__int64)"BcreateTokenMap", "Internal error: no other PARST_ states exist!");
                if ( *(int *)(a2 + 2220) < 3 )
                {
                  *(_DWORD *)(a2 + 2220) = 3;
                  *(_DWORD *)(a2 + 2224) = 4;
                }
              }
              return 0;
            }
            v10 = PARSTloadIncludeFile(&v23, pszSrc, a2);
LABEL_27:
            if ( !(unsigned int)BPreProcess(a2) )
              return 0;
          }
          else
          {
            v16 = *(_QWORD *)(a2 + 480);
            if ( !(unsigned int)BeatArbitraryWhite(a2) )
              goto LABEL_23;
            v17 = *(_QWORD *)(a2 + 456);
            v18 = 32LL * (unsigned int)(*(_DWORD *)(a2 + 468) - 1);
            v19 = *(unsigned int *)(v18 + v17 + 8);
            v20 = *(_BYTE *)(v19 + *(_QWORD *)(v18 + v17));
            if ( v20 != 58 )
            {
              if ( v20 == 10 || v20 == 13 )
              {
LABEL_23:
                *(_DWORD *)(56LL * v23++ + v16 + 52) |= 1u;
                goto LABEL_10;
              }
              vIdentifySource((_DWORD *)(v16 + 56LL * v23), a2, v17);
              WriteDbgTraceErrorGpd(
                (__int64)"PARSTparseColon",
                "Colon expected after keyword: *%0.*s.",
                *(_DWORD *)(56LL * v23 + v16 + 16),
                *(const char **)(56LL * v23 + v16 + 8));
              BeatComment(a2);
              *(_DWORD *)(56LL * v23 + v16 + 52) = 0;
              goto LABEL_10;
            }
            v10 = 4;
            *(_DWORD *)(v18 + v17 + 8) = v19 + 1;
          }
        }
        else
        {
          v15 = PARSTscanForKeyword(&v23, a2);
LABEL_18:
          v10 = v15;
        }
      }
      else
      {
        v10 = PARSTrestorePrevsFile(&v23, a2);
        if ( v10 )
          goto LABEL_27;
        if ( *(_DWORD *)(a2 + 708) && *(_DWORD *)(a2 + 2220) != 3 )
        {
          WriteDbgTraceErrorGpd((__int64)"BcreateTokenMap", "EOF reached before #Endif: was parsed!");
          *(_DWORD *)(a2 + 2224) = 1;
          *(_DWORD *)(a2 + 2220) = 3;
          return 0;
        }
      }
    }
  }
  WriteDbgTraceErrorGpd((__int64)"DefineSymbol", "Internal error, unable to define %s!", "PARSER_VER_1.0");
  return 0;
}

```

## disassembly

```asm
0x18000d218  mov     [rsp-18h+arg_0], rbx
0x18000d21d  mov     [rsp-18h+arg_10], rsi
0x18000d222  push    rbp
0x18000d223  push    rdi
0x18000d224  push    r15
0x18000d226  mov     rbp, rsp
0x18000d229  sub     rsp, 40h
0x18000d22d  mov     rsi, rcx
0x18000d230  mov     [rbp+arg_8], 0
0x18000d237  lea     rcx, aWinnt40; "WINNT_40"
0x18000d23e  mov     dword ptr [rdx+0A00h], 0
0x18000d248  mov     rbx, rdx
0x18000d24b  mov     dword ptr [rdx+2E0h], 0
0x18000d255  call    DefineSymbol
0x18000d25a  test    eax, eax
0x18000d25c  jz      short loc_18000D2DD
0x18000d25e  mov     rdx, rbx
0x18000d261  lea     rcx, aWinnt50; "WINNT_50"
0x18000d268  call    DefineSymbol
0x18000d26d  test    eax, eax
0x18000d26f  jz      short loc_18000D2DD
0x18000d271  mov     rdx, rbx
0x18000d274  lea     rcx, aWinnt51; "WINNT_51"
0x18000d27b  call    DefineSymbol
0x18000d280  test    eax, eax
0x18000d282  jz      short loc_18000D2DD
0x18000d284  mov     rdx, rbx
0x18000d287  lea     rcx, aWinnt60; "WINNT_60"
0x18000d28e  call    DefineSymbol
0x18000d293  test    eax, eax
0x18000d295  jz      short loc_18000D2DD
0x18000d297  or      edi, 0FFFFFFFFh
0x18000d29a  mov     [rbp+var_8], 0Eh
0x18000d2a2  lea     r15, aParserVer10; "PARSER_VER_1.0"
0x18000d2a9  mov     [rsp+40h+var_20], rbx
0x18000d2ae  mov     r9d, edi
0x18000d2b1  mov     [rbp+var_10], r15
0x18000d2b5  mov     edx, 0Fh
0x18000d2ba  lea     rcx, [rbp+var_10]
0x18000d2be  call    DWregisterSymbol
0x18000d2c3  cmp     eax, edi
0x18000d2c5  jnz     short loc_18000D2F3
0x18000d2c7  mov     r8, r15
0x18000d2ca  lea     rdx, aInternalErrorU; "Internal error, unable to define %s!"
0x18000d2d1  lea     rcx, aDefinesymbol; "DefineSymbol"
0x18000d2d8  call    WriteDbgTraceErrorGpd
0x18000d2dd  xor     eax, eax
0x18000d2df  mov     rbx, [rsp+40h+arg_0]
0x18000d2e4  mov     rsi, [rsp+40h+arg_10]
0x18000d2e9  add     rsp, 40h
0x18000d2ed  pop     r15
0x18000d2ef  pop     rdi
0x18000d2f0  pop     rbp
0x18000d2f1  retn
0x18000d2f3  mov     rdx, rbx
0x18000d2f6  mov     rcx, rsi; pszSrc
0x18000d2f9  call    BloadFile
0x18000d2fe  test    eax, eax
0x18000d300  jz      short loc_18000D2DD
0x18000d302  mov     rcx, rbx
0x18000d305  call    BPreProcess
0x18000d30a  test    eax, eax
0x18000d30c  jz      short loc_18000D2DD
0x18000d30e  mov     r15d, 2
0x18000d314  mov     edi, r15d
0x18000d317  test    edi, edi
0x18000d319  jz      loc_18000D3C7
0x18000d31f  mov     eax, [rbx+1E8h]
0x18000d325  cmp     [rbp+arg_8], eax
0x18000d328  jnb     loc_18000D4FA
0x18000d32e  sub     edi, 1
0x18000d331  jz      loc_18000D45D
0x18000d337  sub     edi, 1
0x18000d33a  jz      short loc_18000D3A5
0x18000d33c  sub     edi, 1
0x18000d33f  jz      short loc_18000D35A
0x18000d341  sub     edi, 1
0x18000d344  jnz     loc_18000D3D1
0x18000d34a  mov     rdx, rbx
0x18000d34d  lea     rcx, [rbp+arg_8]
0x18000d351  call    PARSTparseValue
0x18000d356  mov     edi, eax
0x18000d358  jmp     short loc_18000D317
0x18000d35a  mov     rdi, [rbx+1E0h]
0x18000d361  mov     rcx, rbx
0x18000d364  call    BeatArbitraryWhite
0x18000d369  test    eax, eax
0x18000d36b  jz      short loc_18000D3B3
0x18000d36d  mov     ecx, [rbx+1D4h]
0x18000d373  mov     r8, [rbx+1C8h]
0x18000d37a  dec     ecx
0x18000d37c  shl     rcx, 5
0x18000d380  mov     r9d, [rcx+r8+8]
0x18000d385  mov     rax, [rcx+r8]
0x18000d389  mov     dl, [r9+rax]
0x18000d38d  cmp     dl, 3Ah ; ':'
0x18000d390  jnz     short loc_18000D400
0x18000d392  lea     eax, [r9+1]
0x18000d396  mov     edi, 4
0x18000d39b  mov     [rcx+r8+8], eax
0x18000d3a0  jmp     loc_18000D317
0x18000d3a5  mov     rdx, rbx
0x18000d3a8  lea     rcx, [rbp+arg_8]
0x18000d3ac  call    PARSTscanForKeyword
0x18000d3b1  jmp     short loc_18000D356
0x18000d3b3  mov     eax, [rbp+arg_8]
0x18000d3b6  imul    rcx, rax, 38h ; '8'
0x18000d3ba  or      dword ptr [rcx+rdi+34h], 1
0x18000d3bf  inc     [rbp+arg_8]
0x18000d3c2  jmp     loc_18000D314
0x18000d3c7  mov     eax, 1
0x18000d3cc  jmp     loc_18000D2DF
0x18000d3d1  sub     edi, 1
0x18000d3d4  jnz     loc_18000D4B8
0x18000d3da  mov     r8, rbx
0x18000d3dd  lea     rcx, [rbp+arg_8]
0x18000d3e1  mov     rdx, rsi
0x18000d3e4  call    PARSTloadIncludeFile
0x18000d3e9  mov     edi, eax
0x18000d3eb  mov     rcx, rbx
0x18000d3ee  call    BPreProcess
0x18000d3f3  test    eax, eax
0x18000d3f5  jnz     loc_18000D317
0x18000d3fb  jmp     loc_18000D2DD
0x18000d400  cmp     dl, 0Ah
0x18000d403  jz      short loc_18000D3B3
0x18000d405  cmp     dl, 0Dh
0x18000d408  jz      short loc_18000D3B3
0x18000d40a  mov     eax, [rbp+arg_8]
0x18000d40d  mov     rdx, rbx
0x18000d410  imul    rcx, rax, 38h ; '8'
0x18000d414  add     rcx, rdi
0x18000d417  call    vIdentifySource
0x18000d41c  mov     eax, [rbp+arg_8]
0x18000d41f  lea     rdx, aColonExpectedA; "Colon expected after keyword: *%0.*s."
0x18000d426  imul    r8, rax, 38h ; '8'
0x18000d42a  lea     rcx, aParstparsecolo; "PARSTparseColon"
0x18000d431  mov     r9, [r8+rdi+8]
0x18000d436  mov     r8d, [r8+rdi+10h]
0x18000d43b  call    WriteDbgTraceErrorGpd
0x18000d440  mov     rcx, rbx
0x18000d443  call    BeatComment
0x18000d448  mov     r11d, [rbp+arg_8]
0x18000d44c  imul    rax, r11, 38h ; '8'
0x18000d450  mov     dword ptr [rax+rdi+34h], 0
0x18000d458  jmp     loc_18000D314
0x18000d45d  mov     rdx, rbx
0x18000d460  lea     rcx, [rbp+arg_8]
0x18000d464  call    PARSTrestorePrevsFile
0x18000d469  mov     edi, eax
0x18000d46b  test    eax, eax
0x18000d46d  jnz     loc_18000D3EB
0x18000d473  cmp     [rbx+2C4h], eax
0x18000d479  jz      loc_18000D317
0x18000d47f  cmp     dword ptr [rbx+8ACh], 3
0x18000d486  jz      loc_18000D317
0x18000d48c  lea     rdx, aEofReachedBefo; "EOF reached before #Endif: was parsed!"
0x18000d493  lea     rcx, aBcreatetokenma; "BcreateTokenMap"
0x18000d49a  call    WriteDbgTraceErrorGpd
0x18000d49f  mov     dword ptr [rbx+8B0h], 1
0x18000d4a9  mov     dword ptr [rbx+8ACh], 3
0x18000d4b3  jmp     loc_18000D2DD
0x18000d4b8  cmp     edi, 1
0x18000d4bb  jz      loc_18000D2DD
0x18000d4c1  lea     rdx, aInternalErrorN; "Internal error: no other PARST_ states "...
0x18000d4c8  lea     rcx, aBcreatetokenma; "BcreateTokenMap"
0x18000d4cf  call    WriteDbgTraceErrorGpd
0x18000d4d4  cmp     dword ptr [rbx+8ACh], 3
0x18000d4db  jge     loc_18000D2DD
0x18000d4e1  mov     dword ptr [rbx+8ACh], 3
0x18000d4eb  mov     dword ptr [rbx+8B0h], 4
0x18000d4f5  jmp     loc_18000D2DD
0x18000d4fa  lea     rdx, aInternalNoMore; "Internal: no more tokenmap elements - r"...
0x18000d501  lea     rcx, aBcreatetokenma; "BcreateTokenMap"
0x18000d508  call    WriteDbgTraceErrorGpd
0x18000d50d  cmp     [rbx+8ACh], r15d
0x18000d514  jge     loc_18000D2DD
0x18000d51a  mov     [rbx+8ACh], r15d
0x18000d521  mov     [rbx+8B0h], r15d
0x18000d528  mov     dword ptr [rbx+8A8h], 14h
0x18000d532  jmp     loc_18000D2DD
```
