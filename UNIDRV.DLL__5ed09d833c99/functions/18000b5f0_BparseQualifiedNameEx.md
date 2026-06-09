# BparseQualifiedNameEx

- ea: `0x18000b5f0`
- end: `0x18000b7fa`
- name: `BparseQualifiedNameEx`
- size: `522`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000aafc`

## callees

- `0x180007150`
- `0x18000898c`
- `0x180008bf0`
- `0x180009c2c`
- `0x18000b5f0`
- `0x18000bf20`
- `0x180033f3c`

## string_xrefs

- `0x18000b795`: `References to ResourceDLLs must be placed in the feature with symbolname: RESDLL.`

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
  int v16; // eax
  int v17; // ebx
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v20; // ecx
  __int128 v21; // [rsp+20h] [rbp-20h] BYREF
  __int128 v22; // [rsp+30h] [rbp-10h] BYREF
  int v23; // [rsp+60h] [rbp+20h] BYREF

  v4 = (char *)*a1;
  v5 = *((_DWORD *)a1 + 2);
  v21 = 0;
  v7 = v4;
  v22 = 0;
  v10 = v5;
LABEL_2:
  if ( !v10 )
    return BparseInteger((__int64)a1, (unsigned int *)a2, 1);
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
    WriteDbgTraceErrorGpd((__int64)"BparseQualifiedNameEx", v13, *((unsigned int *)a1 + 2), *a1);
    return 0;
  }
  if ( !(unsigned int)BdelimitToken((__int64)a1, (__int64)".", (__int64)&v22, &v23) )
  {
    v13 = "required 2nd delimiter '.' missing in qualified valueEx: %0.*s";
    goto LABEL_14;
  }
  if ( !(unsigned int)BeatSurroundingWhiteSpaces((__int64)&v22) )
  {
    WriteDbgTraceErrorGpd(
      (__int64)"BparseQualifiedNameEx",
      "no option found in qualified valueEx: %0.*s",
      DWORD2(v21),
      (_QWORD)v21);
    return 0;
  }
  if ( !(unsigned int)BparseInteger((__int64)a1, (unsigned int *)a2, 1) )
  {
    v13 = "Err parsing integer portion of qualified valueEx: %0.*s";
    goto LABEL_14;
  }
  v15 = **(_DWORD **)(a4 + 384);
  v16 = DWsearchSymbolListForAAR((__int64)&v21, v15, a4);
  v17 = v16;
  if ( v16 == -1 )
  {
    WriteDbgTraceErrorGpd(
      (__int64)"BparseQualifiedNameEx",
      "qualified name references a non-existent Feature symbol: %0.*s",
      DWORD2(v21),
      (_QWORD)v21);
    return 0;
  }
  v18 = DWsearchSymbolListForID(v16, v15, a4);
  v19 = DWsearchSymbolListForAAR((__int64)&v22, *(_DWORD *)(*(_QWORD *)(a4 + 408) + 20LL * v18 + 16), a4);
  if ( v19 == -1 )
  {
    WriteDbgTraceErrorGpd(
      (__int64)"BparseQualifiedNameEx",
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
        (__int64)"BparseQualifiedNameEx",
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
    WriteDbgTraceErrorGpd((__int64)"BparseQualifiedNameEx", "GPD may not reference more than 127 resource files.");
    return 0;
  }
  *(_BYTE *)(a2 + 2) = v17;
  *(_BYTE *)(a2 + 3) = v19 & 0x7F;
  return 1;
}

```

## disassembly

```asm
0x18000b5f0  mov     [rsp-18h+arg_8], rbx
0x18000b5f5  mov     [rsp-18h+arg_10], rsi
0x18000b5fa  push    rbp
0x18000b5fb  push    rdi
0x18000b5fc  push    r14
0x18000b5fe  mov     rbp, rsp
0x18000b601  sub     rsp, 40h
0x18000b605  mov     r11, [rcx]
0x18000b608  lea     r14, pszSrc; "."
0x18000b60f  mov     r10d, [rcx+8]
0x18000b613  xorps   xmm0, xmm0
0x18000b616  xorps   xmm1, xmm1
0x18000b619  mov     rbx, rcx
0x18000b61c  movups  [rbp+var_20], xmm0
0x18000b620  mov     r8, r11
0x18000b623  mov     rdi, r9
0x18000b626  movups  [rbp+var_10], xmm1
0x18000b62a  mov     rsi, rdx
0x18000b62d  mov     ecx, r10d
0x18000b630  test    ecx, ecx
0x18000b632  jz      loc_18000B7D2
0x18000b638  xor     edx, edx
0x18000b63a  cmp     edx, 1
0x18000b63d  jnb     short loc_18000B664
0x18000b63f  mov     r9b, [r8]
0x18000b642  cmp     r9b, [rdx+r14]
0x18000b646  jnz     short loc_18000B660
0x18000b648  cmp     r9b, 22h ; '"'
0x18000b64c  jz      short loc_18000B654
0x18000b64e  cmp     r9b, 3Ch ; '<'
0x18000b652  jnz     short loc_18000B66B
0x18000b654  cmp     ecx, r10d
0x18000b657  jnb     short loc_18000B66B
0x18000b659  cmp     byte ptr [r8-1], 25h ; '%'
0x18000b65e  jnz     short loc_18000B66B
0x18000b660  inc     edx
0x18000b662  jmp     short loc_18000B63A
0x18000b664  inc     r8
0x18000b667  dec     ecx
0x18000b669  jmp     short loc_18000B630
0x18000b66b  lea     rax, [r8+1]
0x18000b66f  mov     qword ptr [rbp+var_20], r11
0x18000b673  sub     r10d, ecx
0x18000b676  mov     [rbx], rax
0x18000b679  lea     eax, [rcx-1]
0x18000b67c  mov     dword ptr [rbp+var_20+8], r10d
0x18000b680  lea     rcx, [rbp+var_20]
0x18000b684  mov     [rbx+8], eax
0x18000b687  call    BeatSurroundingWhiteSpaces
0x18000b68c  test    eax, eax
0x18000b68e  jnz     short loc_18000B6B1
0x18000b690  lea     rdx, aNoFeatureFound_1; "no feature found in qualified valueEx: "...
0x18000b697  mov     r9, [rbx]
0x18000b69a  mov     r8d, [rbx+8]
0x18000b69e  lea     rcx, aBparsequalifie; "BparseQualifiedNameEx"
0x18000b6a5  call    WriteDbgTraceErrorGpd
0x18000b6aa  xor     eax, eax
0x18000b6ac  jmp     loc_18000B7E6
0x18000b6b1  lea     r9, [rbp+arg_0]
0x18000b6b5  mov     rdx, r14
0x18000b6b8  lea     r8, [rbp+var_10]
0x18000b6bc  mov     rcx, rbx
0x18000b6bf  call    BdelimitToken
0x18000b6c4  test    eax, eax
0x18000b6c6  jnz     short loc_18000B6D1
0x18000b6c8  lea     rdx, aRequired2ndDel; "required 2nd delimiter '.' missing in q"...
0x18000b6cf  jmp     short loc_18000B697
0x18000b6d1  lea     rcx, [rbp+var_10]
0x18000b6d5  call    BeatSurroundingWhiteSpaces
0x18000b6da  test    eax, eax
0x18000b6dc  jnz     short loc_18000B6EF
0x18000b6de  mov     r9, qword ptr [rbp+var_20]
0x18000b6e2  lea     rdx, aNoOptionFoundI; "no option found in qualified valueEx: %"...
0x18000b6e9  mov     r8d, dword ptr [rbp+var_20+8]
0x18000b6ed  jmp     short loc_18000B69E
0x18000b6ef  mov     r9, rdi
0x18000b6f2  mov     r8d, 1
0x18000b6f8  mov     rdx, rsi
0x18000b6fb  mov     rcx, rbx
0x18000b6fe  call    BparseInteger
0x18000b703  test    eax, eax
0x18000b705  jnz     short loc_18000B710
0x18000b707  lea     rdx, aErrParsingInte; "Err parsing integer portion of qualifie"...
0x18000b70e  jmp     short loc_18000B697
0x18000b710  mov     rax, [rdi+180h]
0x18000b717  lea     rcx, [rbp+var_20]
0x18000b71b  mov     r8, rdi
0x18000b71e  mov     r14d, [rax]
0x18000b721  mov     edx, r14d
0x18000b724  call    DWsearchSymbolListForAAR
0x18000b729  mov     ebx, eax
0x18000b72b  cmp     eax, 0FFFFFFFFh
0x18000b72e  jnz     short loc_18000B744
0x18000b730  mov     r9, qword ptr [rbp+var_20]
0x18000b734  lea     rdx, aQualifiedNameR; "qualified name references a non-existen"...
0x18000b73b  mov     r8d, dword ptr [rbp+var_20+8]
0x18000b73f  jmp     loc_18000B69E
0x18000b744  mov     r8, rdi
0x18000b747  mov     edx, r14d
0x18000b74a  mov     ecx, ebx
0x18000b74c  call    DWsearchSymbolListForID
0x18000b751  mov     rdx, [rdi+198h]
0x18000b758  mov     r8, rdi
0x18000b75b  mov     ecx, eax
0x18000b75d  lea     rax, [rcx+rcx*4]
0x18000b761  mov     edx, [rdx+rax*4+10h]
0x18000b765  lea     rcx, [rbp+var_10]
0x18000b769  call    DWsearchSymbolListForAAR
0x18000b76e  cmp     eax, 0FFFFFFFFh
0x18000b771  jnz     short loc_18000B787
0x18000b773  mov     r9, qword ptr [rbp+var_10]
0x18000b777  lea     rdx, aQualifiedNameR_0; "qualified name references a non-existen"...
0x18000b77e  mov     r8d, dword ptr [rbp+var_10+8]
0x18000b782  jmp     loc_18000B69E
0x18000b787  mov     ecx, [rdi+9FCh]
0x18000b78d  test    ecx, ecx
0x18000b78f  jz      short loc_18000B7AD
0x18000b791  cmp     ecx, ebx
0x18000b793  jz      short loc_18000B7B3
0x18000b795  lea     rdx, aReferencesToRe_0; "References to ResourceDLLs must be plac"...
0x18000b79c  lea     rcx, aBparsequalifie; "BparseQualifiedNameEx"
0x18000b7a3  call    WriteDbgTraceErrorGpd
0x18000b7a8  jmp     loc_18000B6AA
0x18000b7ad  mov     [rdi+9FCh], ebx
0x18000b7b3  cmp     eax, 80h
0x18000b7b8  jb      short loc_18000B7C3
0x18000b7ba  lea     rdx, aGpdMayNotRefer; "GPD may not reference more than 127 res"...
0x18000b7c1  jmp     short loc_18000B79C
0x18000b7c3  and     al, 7Fh
0x18000b7c5  mov     [rsi+2], bl
0x18000b7c8  mov     [rsi+3], al
0x18000b7cb  mov     eax, 1
0x18000b7d0  jmp     short loc_18000B7E6
0x18000b7d2  mov     r9, rdi
0x18000b7d5  mov     r8d, 1
0x18000b7db  mov     rdx, rsi
0x18000b7de  mov     rcx, rbx
0x18000b7e1  call    BparseInteger
0x18000b7e6  mov     rbx, [rsp+40h+arg_8]
0x18000b7eb  mov     rsi, [rsp+40h+arg_10]
0x18000b7f0  add     rsp, 40h
0x18000b7f4  pop     r14
0x18000b7f6  pop     rdi
0x18000b7f7  pop     rbp
0x18000b7f8  retn
```
