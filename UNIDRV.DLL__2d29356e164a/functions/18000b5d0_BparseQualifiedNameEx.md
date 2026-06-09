# BparseQualifiedNameEx

- ea: `0x18000b5d0`
- end: `0x18000b7d9`
- name: `BparseQualifiedNameEx`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000aafc`

## callees

- `0x180007220`
- `0x180008a10`
- `0x180008c80`
- `0x18000b5d0`
- `0x18000bcb4`
- `0x18000bf30`
- `0x1800335c8`

## string_xrefs

- `0x18000b775`: `References to ResourceDLLs must be placed in the feature with symbolname: RESDLL.`

## pseudocode

```c
__int64 __fastcall BparseQualifiedNameEx(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v4; // r11
  unsigned int v5; // r10d
  char *v7; // r8
  unsigned int v10; // ecx
  __int64 i; // rdx
  char v12; // r9
  const char *v13; // rdx
  unsigned int v15; // r14d
  unsigned int v16; // eax
  unsigned int v17; // ebx
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v20; // ecx
  __int128 v21; // [rsp+20h] [rbp-20h] BYREF
  __int128 v22; // [rsp+30h] [rbp-10h] BYREF
  char v23; // [rsp+60h] [rbp+20h] BYREF

  v4 = (char *)*a1;
  v5 = *((_DWORD *)a1 + 2);
  v21 = 0;
  v7 = v4;
  v22 = 0;
  v10 = v5;
LABEL_2:
  if ( !v10 )
    return BparseInteger(a1, a2, 1, a4);
  for ( i = 0; ; i = 1 )
  {
    if ( (_DWORD)i )
    {
      ++v7;
      --v10;
      goto LABEL_2;
    }
    v12 = *v7;
    if ( *v7 == pszSrc[i] && (v12 != 34 && v12 != 60 || v10 >= v5 || *(v7 - 1) != 37) )
      break;
  }
  *(_QWORD *)&v21 = v4;
  *a1 = v7 + 1;
  DWORD2(v21) = v5 - v10;
  *((_DWORD *)a1 + 2) = v10 - 1;
  if ( !(unsigned int)BeatSurroundingWhiteSpaces((__int64)&v21) )
  {
    v13 = "no feature found in qualified valueEx: %0.*s";
LABEL_14:
    WriteDbgTraceErrorGpd("BparseQualifiedNameEx", v13, *((unsigned int *)a1 + 2), *a1);
    return 0;
  }
  if ( !(unsigned int)BdelimitToken(a1, ".", &v22, &v23) )
  {
    v13 = "required 2nd delimiter '.' missing in qualified valueEx: %0.*s";
    goto LABEL_14;
  }
  if ( !(unsigned int)BeatSurroundingWhiteSpaces((__int64)&v22) )
  {
    WriteDbgTraceErrorGpd(
      "BparseQualifiedNameEx",
      "no option found in qualified valueEx: %0.*s",
      DWORD2(v21),
      (_QWORD)v21);
    return 0;
  }
  if ( !(unsigned int)BparseInteger(a1, a2, 1, a4) )
  {
    v13 = "Err parsing integer portion of qualified valueEx: %0.*s";
    goto LABEL_14;
  }
  v15 = **(_DWORD **)(a4 + 384);
  v16 = DWsearchSymbolListForAAR(&v21, v15, a4);
  v17 = v16;
  if ( v16 == -1 )
  {
    WriteDbgTraceErrorGpd(
      "BparseQualifiedNameEx",
      "qualified name references a non-existent Feature symbol: %0.*s",
      DWORD2(v21),
      (_QWORD)v21);
    return 0;
  }
  v18 = DWsearchSymbolListForID(v16, v15, a4);
  v19 = DWsearchSymbolListForAAR(&v22, *(unsigned int *)(*(_QWORD *)(a4 + 408) + 20LL * v18 + 16), a4);
  if ( v19 == -1 )
  {
    WriteDbgTraceErrorGpd(
      "BparseQualifiedNameEx",
      "qualified name references a non-existent Option symbol: %0.*s",
      DWORD2(v22),
      (_QWORD)v22);
    return 0;
  }
  v20 = *(_DWORD *)(a4 + 2556);
  if ( v20 )
  {
    if ( v20 != v17 )
    {
      WriteDbgTraceErrorGpd(
        "BparseQualifiedNameEx",
        "References to ResourceDLLs must be placed in the feature with symbolname: RESDLL.");
      return 0;
    }
  }
  else
  {
    *(_DWORD *)(a4 + 2556) = v17;
  }
  if ( v19 >= 0x80 )
  {
    WriteDbgTraceErrorGpd("BparseQualifiedNameEx", "GPD may not reference more than 127 resource files.");
    return 0;
  }
  *(_BYTE *)(a2 + 2) = v17;
  *(_BYTE *)(a2 + 3) = v19 & 0x7F;
  return 1;
}

```

## disassembly

```asm
0x18000b5d0  mov     [rsp-18h+arg_8], rbx
0x18000b5d5  mov     [rsp-18h+arg_10], rsi
0x18000b5da  push    rbp
0x18000b5db  push    rdi
0x18000b5dc  push    r14
0x18000b5de  mov     rbp, rsp
0x18000b5e1  sub     rsp, 40h
0x18000b5e5  mov     r11, [rcx]
0x18000b5e8  lea     r14, pszSrc; "."
0x18000b5ef  mov     r10d, [rcx+8]
0x18000b5f3  xorps   xmm0, xmm0
0x18000b5f6  xorps   xmm1, xmm1
0x18000b5f9  mov     rbx, rcx
0x18000b5fc  movups  [rbp+var_20], xmm0
0x18000b600  mov     r8, r11
0x18000b603  mov     rdi, r9
0x18000b606  movups  [rbp+var_10], xmm1
0x18000b60a  mov     rsi, rdx
0x18000b60d  mov     ecx, r10d
0x18000b610  test    ecx, ecx
0x18000b612  jz      loc_18000B7B2
0x18000b618  xor     edx, edx
0x18000b61a  cmp     edx, 1
0x18000b61d  jnb     short loc_18000B644
0x18000b61f  mov     r9b, [r8]
0x18000b622  cmp     r9b, [rdx+r14]
0x18000b626  jnz     short loc_18000B640
0x18000b628  cmp     r9b, 22h ; '"'
0x18000b62c  jz      short loc_18000B634
0x18000b62e  cmp     r9b, 3Ch ; '<'
0x18000b632  jnz     short loc_18000B64B
0x18000b634  cmp     ecx, r10d
0x18000b637  jnb     short loc_18000B64B
0x18000b639  cmp     byte ptr [r8-1], 25h ; '%'
0x18000b63e  jnz     short loc_18000B64B
0x18000b640  inc     edx
0x18000b642  jmp     short loc_18000B61A
0x18000b644  inc     r8
0x18000b647  dec     ecx
0x18000b649  jmp     short loc_18000B610
0x18000b64b  lea     rax, [r8+1]
0x18000b64f  mov     qword ptr [rbp+var_20], r11
0x18000b653  sub     r10d, ecx
0x18000b656  mov     [rbx], rax
0x18000b659  lea     eax, [rcx-1]
0x18000b65c  mov     dword ptr [rbp+var_20+8], r10d
0x18000b660  lea     rcx, [rbp+var_20]
0x18000b664  mov     [rbx+8], eax
0x18000b667  call    BeatSurroundingWhiteSpaces
0x18000b66c  test    eax, eax
0x18000b66e  jnz     short loc_18000B691
0x18000b670  lea     rdx, aNoFeatureFound_1; "no feature found in qualified valueEx: "...
0x18000b677  mov     r9, [rbx]
0x18000b67a  mov     r8d, [rbx+8]
0x18000b67e  lea     rcx, aBparsequalifie; "BparseQualifiedNameEx"
0x18000b685  call    WriteDbgTraceErrorGpd
0x18000b68a  xor     eax, eax
0x18000b68c  jmp     loc_18000B7C6
0x18000b691  lea     r9, [rbp+arg_0]
0x18000b695  mov     rdx, r14
0x18000b698  lea     r8, [rbp+var_10]
0x18000b69c  mov     rcx, rbx
0x18000b69f  call    BdelimitToken
0x18000b6a4  test    eax, eax
0x18000b6a6  jnz     short loc_18000B6B1
0x18000b6a8  lea     rdx, aRequired2ndDel; "required 2nd delimiter '.' missing in q"...
0x18000b6af  jmp     short loc_18000B677
0x18000b6b1  lea     rcx, [rbp+var_10]
0x18000b6b5  call    BeatSurroundingWhiteSpaces
0x18000b6ba  test    eax, eax
0x18000b6bc  jnz     short loc_18000B6CF
0x18000b6be  mov     r9, qword ptr [rbp+var_20]
0x18000b6c2  lea     rdx, aNoOptionFoundI; "no option found in qualified valueEx: %"...
0x18000b6c9  mov     r8d, dword ptr [rbp+var_20+8]
0x18000b6cd  jmp     short loc_18000B67E
0x18000b6cf  mov     r9, rdi
0x18000b6d2  mov     r8d, 1
0x18000b6d8  mov     rdx, rsi
0x18000b6db  mov     rcx, rbx
0x18000b6de  call    BparseInteger
0x18000b6e3  test    eax, eax
0x18000b6e5  jnz     short loc_18000B6F0
0x18000b6e7  lea     rdx, aErrParsingInte; "Err parsing integer portion of qualifie"...
0x18000b6ee  jmp     short loc_18000B677
0x18000b6f0  mov     rax, [rdi+180h]
0x18000b6f7  lea     rcx, [rbp+var_20]
0x18000b6fb  mov     r8, rdi
0x18000b6fe  mov     r14d, [rax]
0x18000b701  mov     edx, r14d
0x18000b704  call    DWsearchSymbolListForAAR
0x18000b709  mov     ebx, eax
0x18000b70b  cmp     eax, 0FFFFFFFFh
0x18000b70e  jnz     short loc_18000B724
0x18000b710  mov     r9, qword ptr [rbp+var_20]
0x18000b714  lea     rdx, aQualifiedNameR; "qualified name references a non-existen"...
0x18000b71b  mov     r8d, dword ptr [rbp+var_20+8]
0x18000b71f  jmp     loc_18000B67E
0x18000b724  mov     r8, rdi
0x18000b727  mov     edx, r14d
0x18000b72a  mov     ecx, ebx
0x18000b72c  call    DWsearchSymbolListForID
0x18000b731  mov     rdx, [rdi+198h]
0x18000b738  mov     r8, rdi
0x18000b73b  mov     ecx, eax
0x18000b73d  lea     rax, [rcx+rcx*4]
0x18000b741  mov     edx, [rdx+rax*4+10h]
0x18000b745  lea     rcx, [rbp+var_10]
0x18000b749  call    DWsearchSymbolListForAAR
0x18000b74e  cmp     eax, 0FFFFFFFFh
0x18000b751  jnz     short loc_18000B767
0x18000b753  mov     r9, qword ptr [rbp+var_10]
0x18000b757  lea     rdx, aQualifiedNameR_0; "qualified name references a non-existen"...
0x18000b75e  mov     r8d, dword ptr [rbp+var_10+8]
0x18000b762  jmp     loc_18000B67E
0x18000b767  mov     ecx, [rdi+9FCh]
0x18000b76d  test    ecx, ecx
0x18000b76f  jz      short loc_18000B78D
0x18000b771  cmp     ecx, ebx
0x18000b773  jz      short loc_18000B793
0x18000b775  lea     rdx, aReferencesToRe_0; "References to ResourceDLLs must be plac"...
0x18000b77c  lea     rcx, aBparsequalifie; "BparseQualifiedNameEx"
0x18000b783  call    WriteDbgTraceErrorGpd
0x18000b788  jmp     loc_18000B68A
0x18000b78d  mov     [rdi+9FCh], ebx
0x18000b793  cmp     eax, 80h
0x18000b798  jb      short loc_18000B7A3
0x18000b79a  lea     rdx, aGpdMayNotRefer; "GPD may not reference more than 127 res"...
0x18000b7a1  jmp     short loc_18000B77C
0x18000b7a3  and     al, 7Fh
0x18000b7a5  mov     [rsi+2], bl
0x18000b7a8  mov     [rsi+3], al
0x18000b7ab  mov     eax, 1
0x18000b7b0  jmp     short loc_18000B7C6
0x18000b7b2  mov     r9, rdi
0x18000b7b5  mov     r8d, 1
0x18000b7bb  mov     rdx, rsi
0x18000b7be  mov     rcx, rbx
0x18000b7c1  call    BparseInteger
0x18000b7c6  mov     rbx, [rsp+40h+arg_8]
0x18000b7cb  mov     rsi, [rsp+40h+arg_10]
0x18000b7d0  add     rsp, 40h
0x18000b7d4  pop     r14
0x18000b7d6  pop     rdi
0x18000b7d7  pop     rbp
0x18000b7d8  retn
```
