# BResolveValueMacroReference

- ea: `0x180005e10`
- end: `0x1800063c1`
- name: `BResolveValueMacroReference`
- size: `1457`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800093b0`

## callees

- `0x180005e10`
- `0x180007150`
- `0x18000898c`
- `0x180008bf0`
- `0x180033f3c`
- `0x1800365d8`
- `0x180036620`
- `0x180045aa4`
- `0x180076660`

## string_xrefs

- `0x180005fa9`: `BcopyToTmpHeap`
- `0x18000632d`: `missing terminating '}'  in command parameter.`

## pseudocode

```c
__int64 __fastcall BResolveValueMacroReference(__int64 a1, unsigned int a2, __int64 a3)
{
  __int64 v4; // rdi
  int v5; // edx
  char *i; // rcx
  __int64 v7; // rsi
  unsigned int v8; // r13d
  char v9; // r15
  char *v10; // r14
  int v11; // r12d
  __int64 v12; // r8
  unsigned __int8 v13; // dl
  __int64 j; // rcx
  char *v15; // r14
  __int64 v16; // r8
  unsigned int v17; // r14d
  int v18; // eax
  __int64 v19; // r8
  int v20; // ecx
  __int64 v21; // rdx
  bool v22; // zf
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rdx
  int v28; // r14d
  unsigned int v29; // r15d
  __int64 v30; // r8
  __int64 result; // rax
  void *v32; // r12
  int v33; // eax
  int v34; // eax
  unsigned int v35; // r13d
  char *v36; // r8
  unsigned int v37; // r9d
  __int64 m; // rcx
  char v39; // dl
  char *v40; // r8
  unsigned int v41; // edx
  __int64 k; // rcx
  char v43; // r9
  char *v44; // rcx
  int v45; // eax
  __int64 v46; // r8
  __int128 v47; // [rsp+30h] [rbp-48h] BYREF
  __int128 v48; // [rsp+40h] [rbp-38h] BYREF
  __int128 v49; // [rsp+50h] [rbp-28h] BYREF
  __int128 v50; // [rsp+60h] [rbp-18h] BYREF
  int v53; // [rsp+D0h] [rbp+58h] BYREF
  char *v54; // [rsp+D8h] [rbp+60h]

  v49 = 0;
  v48 = 0;
  v4 = a1 + 56LL * a2;
  v5 = *(_DWORD *)(v4 + 32);
  v47 = *(_OWORD *)(v4 + 24);
  for ( i = (char *)v47; v5; --v5 )
  {
    if ( *i != 32 && *i != 9 )
      break;
    ++i;
  }
  v7 = *(_QWORD *)(a3 + 552);
  v8 = v5 - 1;
  v9 = *i;
  v10 = i + 1;
LABEL_7:
  *(_QWORD *)&v47 = v10;
  DWORD2(v47) = v8;
LABEL_8:
  v11 = DWORD2(v49);
  while ( 1 )
  {
    v12 = 0x87FFFFFE03FFLL;
    if ( v9 == 61 )
    {
      v13 = 0;
      for ( j = 0; (unsigned int)j < v8; j = (unsigned int)(j + 1) )
      {
        v13 = v10[j];
        if ( (unsigned __int8)(v13 - 97) > 0x19u
          && ((unsigned __int8)(v13 - 48) > 0x2Fu || !_bittest64(&v12, (unsigned __int8)(v13 - 48))) )
        {
          break;
        }
      }
      *(_QWORD *)&v48 = v10;
      v15 = &v10[(unsigned int)j];
      v8 -= j;
      v16 = v13;
      DWORD2(v48) = j;
      if ( !v8 )
        v16 = 0;
      v54 = v15;
      v53 = v16;
      *(_QWORD *)&v47 = v15;
      DWORD2(v47) = v8;
      if ( (_DWORD)j )
      {
        if ( v8 )
        {
          DWORD2(v47) = --v8;
          v54 = v15 + 1;
          *(_QWORD *)&v47 = v15 + 1;
        }
        v17 = *(_DWORD *)(*(_QWORD *)(a3 + 384) + 16LL);
        if ( !(unsigned int)BeatSurroundingWhiteSpaces((__int64)&v48) )
          return 0;
        v18 = DWsearchSymbolListForAAR((__int64)&v48, v17, a3);
        if ( v18 == -1 )
        {
          WriteDbgTraceErrorGpd(
            (__int64)"BparseSymbol",
            "user supplied a non-existent symbol: %0.*s in class: %d",
            SDWORD2(v48),
            (const char *)v48,
            4);
          return 0;
        }
        v19 = *(unsigned int *)(a3 + 564);
        v20 = 0;
        if ( (_DWORD)v19 )
        {
          while ( 1 )
          {
            v21 = (unsigned int)(v19 - v20 - 1);
            v22 = *(_DWORD *)(v7 + 8 * v21) == v18;
            v23 = v7 + 8 * v21;
            if ( v22 )
              break;
            if ( ++v20 >= (unsigned int)v19 )
              goto LABEL_31;
          }
          _mm_lfence();
          v24 = *(unsigned int *)(v23 + 4);
          if ( (unsigned int)v24 >= a2 )
          {
            vIdentifySource((_DWORD *)v4, a3, v19);
            WriteDbgTraceErrorGpd((__int64)"BResolveValueMacroReference", "ValueMacro cannot reference itself.");
            return 0;
          }
          v25 = 56 * v24;
          v26 = *(unsigned int *)(a3 + 444);
          v27 = a1 + v25;
          v28 = *(_DWORD *)(v27 + 32);
          v29 = v26 + v28;
          if ( (int)v26 + v28 >= (unsigned int)v26 && v29 < *(_DWORD *)(a3 + 440) )
          {
            v32 = (void *)(v26 + *(_QWORD *)(a3 + 432));
            memcpy_0(v32, *(const void **)(v27 + 24), *(unsigned int *)(v27 + 32));
            v33 = DWORD2(v49);
            *(_DWORD *)(a3 + 444) = v29;
            if ( !v33 )
              *(_QWORD *)&v49 = v32;
            v9 = v53;
            v34 = v28 + v33;
            v10 = v54;
            DWORD2(v49) = v34;
            goto LABEL_8;
          }
          WriteDbgTraceErrorGpd((__int64)"BcopyToTmpHeap", "Out of heap space, restart.");
          if ( *(int *)(a3 + 2220) < 2 )
          {
            *(_DWORD *)(a3 + 2220) = 2;
            *(_DWORD *)(a3 + 2224) = 2;
            *(_DWORD *)(a3 + 2216) = 18;
          }
LABEL_26:
          vIdentifySource((_DWORD *)v4, a3, v30);
          WriteDbgTraceErrorGpd(
            (__int64)"BResolveValueMacroReference",
            "Concatenation to produce expanded macro value failed.");
        }
        else
        {
LABEL_31:
          vIdentifySource((_DWORD *)v4, a3, v19);
          WriteDbgTraceErrorGpd(
            (__int64)"BResolveValueMacroReference",
            "=MacroRef not resolved. Not defined or out of scope.");
        }
      }
      else
      {
        vIdentifySource((_DWORD *)v4, a3, v16);
        WriteDbgTraceErrorGpd((__int64)"BResolveValueMacroReference", "No MacroName detected after '='.");
      }
      return 0;
    }
    if ( !v9 )
      break;
    if ( v9 == 34 )
    {
      v40 = v10;
      v41 = v8;
LABEL_66:
      if ( !v41 )
      {
        vIdentifySource((_DWORD *)v4, a3, (__int64)v40);
        WriteDbgTraceErrorGpd((__int64)"BResolveValueMacroReference", "missing terminating '\"'  in substring.");
        return 0;
      }
      for ( k = 0; ; k = 1 )
      {
        if ( (_DWORD)k )
        {
          ++v40;
          --v41;
          goto LABEL_66;
        }
        v43 = *v40;
        if ( *v40 == asc_18007E920[k] && (v43 != 34 && v43 != 60 || v41 >= v8 || *(v40 - 1) != 37) )
          break;
      }
      v44 = v10;
      v10 = v40 + 1;
      v45 = v8 - v41 + 2;
      *(_QWORD *)&v47 = v40 + 1;
      v8 = v41 - 1;
      DWORD2(v48) = v45;
      DWORD2(v47) = v41 - 1;
      *(_QWORD *)&v48 = v44 - 1;
      v50 = 0;
      if ( !(unsigned int)BcopyToTmpHeap((__int64)&v50, (__int64)&v48, a3) )
        goto LABEL_26;
      if ( !v11 )
        *(_QWORD *)&v49 = v50;
      v11 += DWORD2(v50);
      DWORD2(v49) = v11;
      if ( v8 )
      {
        v9 = *v10;
        --v8;
        ++v10;
        DWORD2(v47) = v8;
        *(_QWORD *)&v47 = v10;
      }
      else
      {
        v9 = 0;
      }
    }
    else
    {
      if ( v9 == 37 )
      {
        if ( !(unsigned int)BdelimitToken((__int64)&v47, (__int64)"}", (__int64)&v48, &v53) )
        {
          vIdentifySource((_DWORD *)v4, a3, v46);
          WriteDbgTraceErrorGpd(
            (__int64)"BResolveValueMacroReference",
            "missing terminating '}'  in command parameter.");
          return 0;
        }
        DWORD2(v48) += 2;
        *(_QWORD *)&v48 = v48 - 1;
        if ( !(unsigned int)BCatToTmpHeap((__int64)&v49, (__int64)&v48, a3) )
          goto LABEL_26;
        v8 = DWORD2(v47);
        v10 = (char *)v47;
        if ( DWORD2(v47) )
        {
          v9 = *(_BYTE *)v47;
          v8 = DWORD2(v47) - 1;
          v10 = (char *)(v47 + 1);
          goto LABEL_7;
        }
        v9 = 0;
        goto LABEL_8;
      }
      v35 = v8 + 1;
      --v10;
      DWORD2(v47) = v35;
      *(_QWORD *)&v47 = v10;
      v36 = v10;
      v37 = v35;
LABEL_49:
      if ( v37 )
      {
        for ( m = 0; ; m = (unsigned int)(m + 1) )
        {
          if ( (unsigned int)m >= 3 )
          {
            ++v36;
            --v37;
            goto LABEL_49;
          }
          v39 = *v36;
          v9 = asc_180089B48[m];
          if ( *v36 == v9 && (v39 != 34 && v39 != 60 || v37 >= v35 || *(v36 - 1) != 37) )
            break;
        }
        *(_QWORD *)&v48 = v10;
        v10 = v36 + 1;
        DWORD2(v48) = v35 - v37;
        *(_QWORD *)&v47 = v36 + 1;
        v8 = v37 - 1;
      }
      else
      {
        v9 = 0;
        v48 = v47;
        v8 = 0;
      }
      DWORD2(v47) = v8;
      v50 = 0;
      if ( !(unsigned int)BcopyToTmpHeap((__int64)&v50, (__int64)&v48, a3) )
        goto LABEL_26;
      if ( !v11 )
        *(_QWORD *)&v49 = v50;
      v11 += DWORD2(v50);
      DWORD2(v49) = v11;
    }
  }
  if ( v8 )
  {
    do
    {
      if ( *v10 != 32 && *v10 != 9 )
        break;
      ++v10;
      --v8;
    }
    while ( v8 );
    if ( v8 )
    {
      vIdentifySource((_DWORD *)v4, a3, 0x87FFFFFE03FFLL);
      WriteDbgTraceErrorGpd(
        (__int64)"BResolveValueMacroReference",
        "Error parsing value containing =MacroRef: %0.*s.",
        *(_DWORD *)(v4 + 32),
        *(const char **)(v4 + 24));
      WriteDbgTraceErrorGpd(
        (__int64)"BResolveValueMacroReference",
        "    only %{parameter} or \"substrings\" may coexist with =MacroRefs.");
      return 0;
    }
  }
  result = 1;
  *(_OWORD *)(v4 + 24) = v49;
  return result;
}

```

## disassembly

```asm
0x180005e10  mov     [rsp-40h+arg_8], edx
0x180005e14  mov     [rsp-40h+arg_0], rcx
0x180005e19  push    rbp
0x180005e1a  push    rbx
0x180005e1b  push    rsi
0x180005e1c  push    rdi
0x180005e1d  push    r12
0x180005e1f  push    r13
0x180005e21  push    r14
0x180005e23  push    r15
0x180005e25  mov     rbp, rsp
0x180005e28  sub     rsp, 78h
0x180005e2c  mov     eax, edx
0x180005e2e  xorps   xmm0, xmm0
0x180005e31  imul    rdi, rax, 38h ; '8'
0x180005e35  movups  [rbp+var_28], xmm0
0x180005e39  xorps   xmm1, xmm1
0x180005e3c  movups  [rbp+var_38], xmm1
0x180005e40  mov     rbx, r8
0x180005e43  add     rdi, rcx
0x180005e46  movups  xmm0, xmmword ptr [rdi+18h]
0x180005e4a  mov     edx, [rdi+20h]
0x180005e4d  movaps  [rbp+var_48], xmm0
0x180005e51  movq    rcx, xmm0
0x180005e56  test    edx, edx
0x180005e58  jz      short loc_180005E6F
0x180005e5a  movzx   eax, byte ptr [rcx]
0x180005e5d  cmp     al, 20h ; ' '
0x180005e5f  jnz     short loc_180005E6B
0x180005e61  inc     rcx
0x180005e64  add     edx, 0FFFFFFFFh
0x180005e67  jnz     short loc_180005E5A
0x180005e69  jmp     short loc_180005E6F
0x180005e6b  cmp     al, 9
0x180005e6d  jz      short loc_180005E61
0x180005e6f  mov     rsi, [r8+228h]
0x180005e76  lea     r13d, [rdx-1]
0x180005e7a  movzx   r15d, byte ptr [rcx]
0x180005e7e  lea     r14, [rcx+1]
0x180005e82  mov     qword ptr [rbp+var_48], r14
0x180005e86  mov     dword ptr [rbp+var_48+8], r13d
0x180005e8a  mov     r12d, dword ptr [rbp+var_28+8]
0x180005e8e  lea     r10, cs:180000000h
0x180005e95  mov     r8, 87FFFFFE03FFh
0x180005e9f  cmp     r15b, 3Dh ; '='
0x180005ea3  jnz     loc_1800060A9
0x180005ea9  xor     dl, dl
0x180005eab  xor     ecx, ecx
0x180005ead  test    r13d, r13d
0x180005eb0  jz      short loc_180005ED7
0x180005eb2  nop     dword ptr [rax+00h]
0x180005eb6  nop     word ptr [rax+rax+00000000h]
0x180005ec0  movzx   edx, byte ptr [rcx+r14]
0x180005ec5  lea     eax, [rdx-61h]
0x180005ec8  cmp     al, 19h
0x180005eca  ja      loc_180005FF0
0x180005ed0  inc     ecx
0x180005ed2  cmp     ecx, r13d
0x180005ed5  jb      short loc_180005EC0
0x180005ed7  mov     eax, ecx
0x180005ed9  mov     qword ptr [rbp+var_38], r14
0x180005edd  add     r14, rax
0x180005ee0  sub     r13d, ecx
0x180005ee3  movzx   r8d, dl
0x180005ee7  mov     eax, 0
0x180005eec  mov     dword ptr [rbp+var_38+8], ecx
0x180005eef  cmovz   r8d, eax
0x180005ef3  mov     [rbp+arg_18], r14
0x180005ef7  mov     [rbp+arg_10], r8d
0x180005efb  mov     qword ptr [rbp+var_48], r14
0x180005eff  mov     dword ptr [rbp+var_48+8], r13d
0x180005f03  test    ecx, ecx
0x180005f05  jz      loc_18000604A
0x180005f0b  test    r13d, r13d
0x180005f0e  jnz     loc_180006302
0x180005f14  mov     rax, [rbx+180h]
0x180005f1b  lea     rcx, [rbp+var_38]
0x180005f1f  mov     r14d, [rax+10h]
0x180005f23  call    BeatSurroundingWhiteSpaces
0x180005f28  test    eax, eax
0x180005f2a  jz      loc_180006036
0x180005f30  mov     r8, rbx
0x180005f33  lea     rcx, [rbp+var_38]
0x180005f37  mov     edx, r14d
0x180005f3a  call    DWsearchSymbolListForAAR
0x180005f3f  cmp     eax, 0FFFFFFFFh
0x180005f42  jz      loc_180006399
0x180005f48  mov     r8d, [rbx+234h]
0x180005f4f  xor     ecx, ecx
0x180005f51  test    r8d, r8d
0x180005f54  jz      loc_180006018
0x180005f5a  nop     word ptr [rax+rax+00h]
0x180005f60  mov     edx, r8d
0x180005f63  sub     edx, ecx
0x180005f65  dec     edx
0x180005f67  cmp     [rsi+rdx*8], eax
0x180005f6a  lea     rdx, [rsi+rdx*8]
0x180005f6e  jnz     loc_18000600D
0x180005f74  lfence
0x180005f77  mov     eax, [rdx+4]
0x180005f7a  cmp     eax, [rbp+arg_8]
0x180005f7d  jnb     loc_180006382
0x180005f83  imul    rdx, rax, 38h ; '8'
0x180005f87  mov     eax, [rbx+1BCh]
0x180005f8d  add     rdx, [rbp+arg_0]
0x180005f91  mov     r14d, [rdx+20h]
0x180005f95  lea     r15d, [rax+r14]
0x180005f99  cmp     r15d, eax
0x180005f9c  jnb     loc_18000605E
0x180005fa2  lea     rdx, aOutOfHeapSpace; "Out of heap space, restart."
0x180005fa9  lea     rcx, aBcopytotmpheap; "BcopyToTmpHeap"
0x180005fb0  call    WriteDbgTraceErrorGpd
0x180005fb5  cmp     dword ptr [rbx+8ACh], 2
0x180005fbc  jge     short loc_180005FDC
0x180005fbe  mov     dword ptr [rbx+8ACh], 2
0x180005fc8  mov     dword ptr [rbx+8B0h], 2
0x180005fd2  mov     dword ptr [rbx+8A8h], 12h
0x180005fdc  mov     rdx, rbx
0x180005fdf  mov     rcx, rdi
0x180005fe2  call    vIdentifySource
0x180005fe7  lea     rdx, aConcatenationT_0; "Concatenation to produce expanded macro"...
0x180005fee  jmp     short loc_18000602A
0x180005ff0  lea     eax, [rdx-30h]
0x180005ff3  cmp     al, 2Fh ; '/'
0x180005ff5  ja      loc_180005ED7
0x180005ffb  movzx   eax, al
0x180005ffe  bt      r8, rax
0x180006002  jb      loc_180005ED0
0x180006008  jmp     loc_180005ED7
0x18000600d  inc     ecx
0x18000600f  cmp     ecx, r8d
0x180006012  jb      loc_180005F60
0x180006018  mov     rdx, rbx
0x18000601b  mov     rcx, rdi
0x18000601e  call    vIdentifySource
0x180006023  lea     rdx, aMacrorefNotRes; "=MacroRef not resolved. Not defined or "...
0x18000602a  lea     rcx, aBresolvevaluem; "BResolveValueMacroReference"
0x180006031  call    WriteDbgTraceErrorGpd
0x180006036  xor     eax, eax
0x180006038  add     rsp, 78h
0x18000603c  pop     r15
0x18000603e  pop     r14
0x180006040  pop     r13
0x180006042  pop     r12
0x180006044  pop     rdi
0x180006045  pop     rsi
0x180006046  pop     rbx
0x180006047  pop     rbp
0x180006048  retn
0x18000604a  mov     rdx, rbx
0x18000604d  mov     rcx, rdi
0x180006050  call    vIdentifySource
0x180006055  lea     rdx, aNoMacronameDet; "No MacroName detected after '='."
0x18000605c  jmp     short loc_18000602A
0x18000605e  cmp     r15d, [rbx+1B8h]
0x180006065  jnb     loc_180005FA2
0x18000606b  mov     r12, [rbx+1B0h]
0x180006072  mov     r8, r14; Size
0x180006075  mov     rdx, [rdx+18h]; Src
0x180006079  add     r12, rax
0x18000607c  mov     rcx, r12; void *
0x18000607f  call    memcpy_0
0x180006084  mov     eax, dword ptr [rbp+var_28+8]
0x180006087  mov     [rbx+1BCh], r15d
0x18000608e  test    eax, eax
0x180006090  jz      loc_180006319
0x180006096  mov     r15d, [rbp+arg_10]
0x18000609a  add     eax, r14d
0x18000609d  mov     r14, [rbp+arg_18]
0x1800060a1  mov     dword ptr [rbp+var_28+8], eax
0x1800060a4  jmp     loc_180005E8A
0x1800060a9  test    r15b, r15b
0x1800060ac  jnz     short loc_1800060E5
0x1800060ae  test    r13d, r13d
0x1800060b1  jz      short loc_1800060D3
0x1800060b3  movzx   eax, byte ptr [r14]
0x1800060b7  cmp     al, 20h ; ' '
0x1800060b9  jnz     short loc_1800060C6
0x1800060bb  inc     r14
0x1800060be  add     r13d, 0FFFFFFFFh
0x1800060c2  jnz     short loc_1800060B3
0x1800060c4  jmp     short loc_1800060CA
0x1800060c6  cmp     al, 9
0x1800060c8  jz      short loc_1800060BB
0x1800060ca  test    r13d, r13d
0x1800060cd  jnz     loc_180006350
0x1800060d3  movups  xmm0, [rbp+var_28]
0x1800060d7  mov     eax, 1
0x1800060dc  movups  xmmword ptr [rdi+18h], xmm0
0x1800060e0  jmp     loc_180006038
0x1800060e5  cmp     r15b, 22h ; '"'
0x1800060e9  jz      loc_1800061A6
0x1800060ef  cmp     r15b, 25h ; '%'
0x1800060f3  jz      loc_180006295
0x1800060f9  inc     r13d
0x1800060fc  dec     r14
0x1800060ff  mov     dword ptr [rbp+var_48+8], r13d
0x180006103  mov     qword ptr [rbp+var_48], r14
0x180006107  mov     r8, r14
0x18000610a  mov     r9d, r13d
0x18000610d  nop     dword ptr [rax]
0x180006110  test    r9d, r9d
0x180006113  jz      loc_180006274
0x180006119  xor     ecx, ecx
0x18000611b  cmp     ecx, 3
0x18000611e  jnb     short loc_180006136
0x180006120  movzx   edx, byte ptr [r8]
0x180006124  movzx   r15d, byte ptr [rcx+r10+89B48h]
0x18000612d  cmp     dl, r15b
0x180006130  jz      short loc_18000613E
0x180006132  inc     ecx
0x180006134  jmp     short loc_18000611B
0x180006136  inc     r8
0x180006139  dec     r9d
0x18000613c  jmp     short loc_180006110
0x18000613e  cmp     dl, 22h ; '"'
0x180006141  jz      short loc_180006198
0x180006143  cmp     dl, 3Ch ; '<'
0x180006146  jz      short loc_180006198
0x180006148  sub     r13d, r9d
0x18000614b  mov     qword ptr [rbp+var_38], r14
0x18000614f  lea     r14, [r8+1]
0x180006153  mov     dword ptr [rbp+var_38+8], r13d
0x180006157  mov     qword ptr [rbp+var_48], r14
0x18000615b  lea     r13d, [r9-1]
0x18000615f  xorps   xmm0, xmm0
0x180006162  mov     dword ptr [rbp+var_48+8], r13d
0x180006166  mov     r8, rbx
0x180006169  lea     rdx, [rbp+var_38]
0x18000616d  lea     rcx, [rbp+var_18]
0x180006171  movups  [rbp+var_18], xmm0
0x180006175  call    BcopyToTmpHeap
0x18000617a  test    eax, eax
0x18000617c  jz      loc_180005FDC
0x180006182  test    r12d, r12d
0x180006185  jz      loc_180006288
0x18000618b  add     r12d, dword ptr [rbp+var_18+8]
0x18000618f  mov     dword ptr [rbp+var_28+8], r12d
0x180006193  jmp     loc_180005E8E
0x180006198  cmp     r9d, r13d
0x18000619b  jnb     short loc_180006148
0x18000619d  cmp     byte ptr [r8-1], 25h ; '%'
0x1800061a2  jz      short loc_180006132
0x1800061a4  jmp     short loc_180006148
0x1800061a6  mov     r8, r14
0x1800061a9  mov     edx, r13d
0x1800061ac  nop     dword ptr [rax+00h]
0x1800061b0  test    edx, edx
0x1800061b2  jz      loc_180006339
0x1800061b8  xor     ecx, ecx
0x1800061ba  cmp     ecx, 1
0x1800061bd  jnb     short loc_1800061D1
0x1800061bf  movzx   r9d, byte ptr [r8]
0x1800061c3  cmp     r9b, [rcx+r10+7E920h]
0x1800061cb  jz      short loc_1800061D8
0x1800061cd  inc     ecx
0x1800061cf  jmp     short loc_1800061BA
0x1800061d1  inc     r8
0x1800061d4  dec     edx
0x1800061d6  jmp     short loc_1800061B0
0x1800061d8  cmp     r9b, 22h ; '"'
0x1800061dc  jz      short loc_180006257
0x1800061de  cmp     r9b, 3Ch ; '<'
0x1800061e2  jz      short loc_180006257
0x1800061e4  sub     r13d, edx
0x1800061e7  mov     rcx, r14
0x1800061ea  mov     eax, r13d
0x1800061ed  lea     r14, [r8+1]
0x1800061f1  add     eax, 2
0x1800061f4  mov     qword ptr [rbp+var_48], r14
0x1800061f8  lea     r13d, [rdx-1]
0x1800061fc  mov     dword ptr [rbp+var_38+8], eax
0x1800061ff  lea     rax, [rcx-1]
0x180006203  mov     dword ptr [rbp+var_48+8], r13d
0x180006207  xorps   xmm0, xmm0
0x18000620a  mov     qword ptr [rbp+var_38], rax
0x18000620e  lea     rcx, [rbp+var_18]
0x180006212  mov     r8, rbx
0x180006215  lea     rdx, [rbp+var_38]
0x180006219  movups  [rbp+var_18], xmm0
0x18000621d  call    BcopyToTmpHeap
0x180006222  test    eax, eax
0x180006224  jz      loc_180005FDC
0x18000622a  test    r12d, r12d
0x18000622d  jz      loc_1800062F5
0x180006233  add     r12d, dword ptr [rbp+var_18+8]
0x180006237  mov     dword ptr [rbp+var_28+8], r12d
0x18000623b  test    r13d, r13d
0x18000623e  jz      short loc_18000626C
0x180006240  movzx   r15d, byte ptr [r14]
0x180006244  dec     r13d
0x180006247  inc     r14
0x18000624a  mov     dword ptr [rbp+var_48+8], r13d
0x18000624e  mov     qword ptr [rbp+var_48], r14
0x180006252  jmp     loc_180005E8E
0x180006257  cmp     edx, r13d
0x18000625a  jnb     short loc_1800061E4
0x18000625c  cmp     byte ptr [r8-1], 25h ; '%'
0x180006261  jz      loc_1800061CD
0x180006267  jmp     loc_1800061E4
  ... truncated ...
```
