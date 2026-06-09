# BResolveValueMacroReference

- ea: `0x180005ee0`
- end: `0x180006491`
- name: `BResolveValueMacroReference`
- size: `1457`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800093f0`

## callees

- `0x180005ee0`
- `0x180007220`
- `0x180008a10`
- `0x180008c80`
- `0x1800335c8`
- `0x1800363ac`
- `0x1800363f4`
- `0x18004485c`
- `0x180074580`

## string_xrefs

- `0x180006079`: `BcopyToTmpHeap`
- `0x1800063fd`: `missing terminating '}'  in command parameter.`

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
  int v16; // r8d
  unsigned int v17; // r14d
  int v18; // eax
  unsigned int v19; // r8d
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
  __int64 result; // rax
  void *v31; // r12
  int v32; // eax
  int v33; // eax
  unsigned int v34; // r13d
  char *v35; // r8
  unsigned int v36; // r9d
  __int64 m; // rcx
  char v38; // dl
  char *v39; // r8
  unsigned int v40; // edx
  __int64 k; // rcx
  char v42; // r9
  char *v43; // rcx
  int v44; // eax
  __int128 v45; // [rsp+30h] [rbp-48h] BYREF
  __int128 v46; // [rsp+40h] [rbp-38h] BYREF
  __int128 v47; // [rsp+50h] [rbp-28h] BYREF
  __int128 v48; // [rsp+60h] [rbp-18h] BYREF
  int v51; // [rsp+D0h] [rbp+58h] BYREF
  char *v52; // [rsp+D8h] [rbp+60h]

  v47 = 0;
  v46 = 0;
  v4 = a1 + 56LL * a2;
  v5 = *(_DWORD *)(v4 + 32);
  v45 = *(_OWORD *)(v4 + 24);
  for ( i = (char *)v45; v5; --v5 )
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
  *(_QWORD *)&v45 = v10;
  DWORD2(v45) = v8;
LABEL_8:
  v11 = DWORD2(v47);
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
      *(_QWORD *)&v46 = v10;
      v15 = &v10[(unsigned int)j];
      v8 -= j;
      v16 = v13;
      DWORD2(v46) = j;
      if ( !v8 )
        v16 = 0;
      v52 = v15;
      v51 = v16;
      *(_QWORD *)&v45 = v15;
      DWORD2(v45) = v8;
      if ( (_DWORD)j )
      {
        if ( v8 )
        {
          DWORD2(v45) = --v8;
          v52 = v15 + 1;
          *(_QWORD *)&v45 = v15 + 1;
        }
        v17 = *(_DWORD *)(*(_QWORD *)(a3 + 384) + 16LL);
        if ( !(unsigned int)BeatSurroundingWhiteSpaces(&v46) )
          return 0;
        v18 = DWsearchSymbolListForAAR(&v46, v17, a3);
        if ( v18 == -1 )
        {
          WriteDbgTraceErrorGpd(
            "BparseSymbol",
            "user supplied a non-existent symbol: %0.*s in class: %d",
            SDWORD2(v46),
            (const char *)v46,
            4);
          return 0;
        }
        v19 = *(_DWORD *)(a3 + 564);
        v20 = 0;
        if ( v19 )
        {
          while ( 1 )
          {
            v21 = v19 - v20 - 1;
            v22 = *(_DWORD *)(v7 + 8 * v21) == v18;
            v23 = v7 + 8 * v21;
            if ( v22 )
              break;
            if ( ++v20 >= v19 )
              goto LABEL_31;
          }
          _mm_lfence();
          v24 = *(unsigned int *)(v23 + 4);
          if ( (unsigned int)v24 >= a2 )
          {
            vIdentifySource(v4, a3);
            WriteDbgTraceErrorGpd("BResolveValueMacroReference", "ValueMacro cannot reference itself.");
            return 0;
          }
          v25 = 56 * v24;
          v26 = *(unsigned int *)(a3 + 444);
          v27 = a1 + v25;
          v28 = *(_DWORD *)(v27 + 32);
          v29 = v26 + v28;
          if ( (int)v26 + v28 >= (unsigned int)v26 && v29 < *(_DWORD *)(a3 + 440) )
          {
            v31 = (void *)(v26 + *(_QWORD *)(a3 + 432));
            memcpy_0(v31, *(const void **)(v27 + 24), *(unsigned int *)(v27 + 32));
            v32 = DWORD2(v47);
            *(_DWORD *)(a3 + 444) = v29;
            if ( !v32 )
              *(_QWORD *)&v47 = v31;
            v9 = v51;
            v33 = v28 + v32;
            v10 = v52;
            DWORD2(v47) = v33;
            goto LABEL_8;
          }
          WriteDbgTraceErrorGpd("BcopyToTmpHeap", "Out of heap space, restart.");
          if ( *(int *)(a3 + 2220) < 2 )
          {
            *(_DWORD *)(a3 + 2220) = 2;
            *(_DWORD *)(a3 + 2224) = 2;
            *(_DWORD *)(a3 + 2216) = 18;
          }
LABEL_26:
          vIdentifySource(v4, a3);
          WriteDbgTraceErrorGpd("BResolveValueMacroReference", "Concatenation to produce expanded macro value failed.");
        }
        else
        {
LABEL_31:
          vIdentifySource(v4, a3);
          WriteDbgTraceErrorGpd("BResolveValueMacroReference", "=MacroRef not resolved. Not defined or out of scope.");
        }
      }
      else
      {
        vIdentifySource(v4, a3);
        WriteDbgTraceErrorGpd("BResolveValueMacroReference", "No MacroName detected after '='.");
      }
      return 0;
    }
    if ( !v9 )
      break;
    if ( v9 == 34 )
    {
      v39 = v10;
      v40 = v8;
LABEL_66:
      if ( !v40 )
      {
        vIdentifySource(v4, a3);
        WriteDbgTraceErrorGpd("BResolveValueMacroReference", "missing terminating '\"'  in substring.");
        return 0;
      }
      for ( k = 0; ; k = 1 )
      {
        if ( (_DWORD)k )
        {
          ++v39;
          --v40;
          goto LABEL_66;
        }
        v42 = *v39;
        if ( *v39 == asc_18007C920[k] && (v42 != 34 && v42 != 60 || v40 >= v8 || *(v39 - 1) != 37) )
          break;
      }
      v43 = v10;
      v10 = v39 + 1;
      v44 = v8 - v40 + 2;
      *(_QWORD *)&v45 = v39 + 1;
      v8 = v40 - 1;
      DWORD2(v46) = v44;
      DWORD2(v45) = v40 - 1;
      *(_QWORD *)&v46 = v43 - 1;
      v48 = 0;
      if ( !(unsigned int)BcopyToTmpHeap(&v48, &v46, a3) )
        goto LABEL_26;
      if ( !v11 )
        *(_QWORD *)&v47 = v48;
      v11 += DWORD2(v48);
      DWORD2(v47) = v11;
      if ( v8 )
      {
        v9 = *v10;
        --v8;
        ++v10;
        DWORD2(v45) = v8;
        *(_QWORD *)&v45 = v10;
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
        if ( !(unsigned int)BdelimitToken(&v45, "}", &v46, &v51) )
        {
          vIdentifySource(v4, a3);
          WriteDbgTraceErrorGpd("BResolveValueMacroReference", "missing terminating '}'  in command parameter.");
          return 0;
        }
        DWORD2(v46) += 2;
        *(_QWORD *)&v46 = v46 - 1;
        if ( !(unsigned int)BCatToTmpHeap(&v47, &v46, a3) )
          goto LABEL_26;
        v8 = DWORD2(v45);
        v10 = (char *)v45;
        if ( DWORD2(v45) )
        {
          v9 = *(_BYTE *)v45;
          v8 = DWORD2(v45) - 1;
          v10 = (char *)(v45 + 1);
          goto LABEL_7;
        }
        v9 = 0;
        goto LABEL_8;
      }
      v34 = v8 + 1;
      --v10;
      DWORD2(v45) = v34;
      *(_QWORD *)&v45 = v10;
      v35 = v10;
      v36 = v34;
LABEL_49:
      if ( v36 )
      {
        for ( m = 0; ; m = (unsigned int)(m + 1) )
        {
          if ( (unsigned int)m >= 3 )
          {
            ++v35;
            --v36;
            goto LABEL_49;
          }
          v38 = *v35;
          v9 = asc_180087B68[m];
          if ( *v35 == v9 && (v38 != 34 && v38 != 60 || v36 >= v34 || *(v35 - 1) != 37) )
            break;
        }
        *(_QWORD *)&v46 = v10;
        v10 = v35 + 1;
        DWORD2(v46) = v34 - v36;
        *(_QWORD *)&v45 = v35 + 1;
        v8 = v36 - 1;
      }
      else
      {
        v9 = 0;
        v46 = v45;
        v8 = 0;
      }
      DWORD2(v45) = v8;
      v48 = 0;
      if ( !(unsigned int)BcopyToTmpHeap(&v48, &v46, a3) )
        goto LABEL_26;
      if ( !v11 )
        *(_QWORD *)&v47 = v48;
      v11 += DWORD2(v48);
      DWORD2(v47) = v11;
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
      vIdentifySource(v4, a3);
      WriteDbgTraceErrorGpd(
        "BResolveValueMacroReference",
        "Error parsing value containing =MacroRef: %0.*s.",
        *(_DWORD *)(v4 + 32),
        *(const char **)(v4 + 24));
      WriteDbgTraceErrorGpd(
        "BResolveValueMacroReference",
        "    only %{parameter} or \"substrings\" may coexist with =MacroRefs.");
      return 0;
    }
  }
  result = 1;
  *(_OWORD *)(v4 + 24) = v47;
  return result;
}

```

## disassembly

```asm
0x180005ee0  mov     [rsp-40h+arg_8], edx
0x180005ee4  mov     [rsp-40h+arg_0], rcx
0x180005ee9  push    rbp
0x180005eea  push    rbx
0x180005eeb  push    rsi
0x180005eec  push    rdi
0x180005eed  push    r12
0x180005eef  push    r13
0x180005ef1  push    r14
0x180005ef3  push    r15
0x180005ef5  mov     rbp, rsp
0x180005ef8  sub     rsp, 78h
0x180005efc  mov     eax, edx
0x180005efe  xorps   xmm0, xmm0
0x180005f01  imul    rdi, rax, 38h ; '8'
0x180005f05  movups  [rbp+var_28], xmm0
0x180005f09  xorps   xmm1, xmm1
0x180005f0c  movups  [rbp+var_38], xmm1
0x180005f10  mov     rbx, r8
0x180005f13  add     rdi, rcx
0x180005f16  movups  xmm0, xmmword ptr [rdi+18h]
0x180005f1a  mov     edx, [rdi+20h]
0x180005f1d  movaps  [rbp+var_48], xmm0
0x180005f21  movq    rcx, xmm0
0x180005f26  test    edx, edx
0x180005f28  jz      short loc_180005F3F
0x180005f2a  movzx   eax, byte ptr [rcx]
0x180005f2d  cmp     al, 20h ; ' '
0x180005f2f  jnz     short loc_180005F3B
0x180005f31  inc     rcx
0x180005f34  add     edx, 0FFFFFFFFh
0x180005f37  jnz     short loc_180005F2A
0x180005f39  jmp     short loc_180005F3F
0x180005f3b  cmp     al, 9
0x180005f3d  jz      short loc_180005F31
0x180005f3f  mov     rsi, [r8+228h]
0x180005f46  lea     r13d, [rdx-1]
0x180005f4a  movzx   r15d, byte ptr [rcx]
0x180005f4e  lea     r14, [rcx+1]
0x180005f52  mov     qword ptr [rbp+var_48], r14
0x180005f56  mov     dword ptr [rbp+var_48+8], r13d
0x180005f5a  mov     r12d, dword ptr [rbp+var_28+8]
0x180005f5e  lea     r10, cs:180000000h
0x180005f65  mov     r8, 87FFFFFE03FFh
0x180005f6f  cmp     r15b, 3Dh ; '='
0x180005f73  jnz     loc_180006178
0x180005f79  xor     dl, dl
0x180005f7b  xor     ecx, ecx
0x180005f7d  test    r13d, r13d
0x180005f80  jz      short loc_180005FA7
0x180005f82  nop     dword ptr [rax+00h]
0x180005f86  nop     word ptr [rax+rax+00000000h]
0x180005f90  movzx   edx, byte ptr [rcx+r14]
0x180005f95  lea     eax, [rdx-61h]
0x180005f98  cmp     al, 19h
0x180005f9a  ja      loc_1800060C0
0x180005fa0  inc     ecx
0x180005fa2  cmp     ecx, r13d
0x180005fa5  jb      short loc_180005F90
0x180005fa7  mov     eax, ecx
0x180005fa9  mov     qword ptr [rbp+var_38], r14
0x180005fad  add     r14, rax
0x180005fb0  sub     r13d, ecx
0x180005fb3  movzx   r8d, dl
0x180005fb7  mov     eax, 0
0x180005fbc  mov     dword ptr [rbp+var_38+8], ecx
0x180005fbf  cmovz   r8d, eax
0x180005fc3  mov     [rbp+arg_18], r14
0x180005fc7  mov     [rbp+arg_10], r8d
0x180005fcb  mov     qword ptr [rbp+var_48], r14
0x180005fcf  mov     dword ptr [rbp+var_48+8], r13d
0x180005fd3  test    ecx, ecx
0x180005fd5  jz      loc_180006119
0x180005fdb  test    r13d, r13d
0x180005fde  jnz     loc_1800063D2
0x180005fe4  mov     rax, [rbx+180h]
0x180005feb  lea     rcx, [rbp+var_38]
0x180005fef  mov     r14d, [rax+10h]
0x180005ff3  call    BeatSurroundingWhiteSpaces
0x180005ff8  test    eax, eax
0x180005ffa  jz      loc_180006106
0x180006000  mov     r8, rbx
0x180006003  lea     rcx, [rbp+var_38]
0x180006007  mov     edx, r14d
0x18000600a  call    DWsearchSymbolListForAAR
0x18000600f  cmp     eax, 0FFFFFFFFh
0x180006012  jz      loc_180006469
0x180006018  mov     r8d, [rbx+234h]
0x18000601f  xor     ecx, ecx
0x180006021  test    r8d, r8d
0x180006024  jz      loc_1800060E8
0x18000602a  nop     word ptr [rax+rax+00h]
0x180006030  mov     edx, r8d
0x180006033  sub     edx, ecx
0x180006035  dec     edx
0x180006037  cmp     [rsi+rdx*8], eax
0x18000603a  lea     rdx, [rsi+rdx*8]
0x18000603e  jnz     loc_1800060DD
0x180006044  lfence
0x180006047  mov     eax, [rdx+4]
0x18000604a  cmp     eax, [rbp+arg_8]
0x18000604d  jnb     loc_180006452
0x180006053  imul    rdx, rax, 38h ; '8'
0x180006057  mov     eax, [rbx+1BCh]
0x18000605d  add     rdx, [rbp+arg_0]
0x180006061  mov     r14d, [rdx+20h]
0x180006065  lea     r15d, [rax+r14]
0x180006069  cmp     r15d, eax
0x18000606c  jnb     loc_18000612D
0x180006072  lea     rdx, aOutOfHeapSpace; "Out of heap space, restart."
0x180006079  lea     rcx, aBcopytotmpheap; "BcopyToTmpHeap"
0x180006080  call    WriteDbgTraceErrorGpd
0x180006085  cmp     dword ptr [rbx+8ACh], 2
0x18000608c  jge     short loc_1800060AC
0x18000608e  mov     dword ptr [rbx+8ACh], 2
0x180006098  mov     dword ptr [rbx+8B0h], 2
0x1800060a2  mov     dword ptr [rbx+8A8h], 12h
0x1800060ac  mov     rdx, rbx
0x1800060af  mov     rcx, rdi
0x1800060b2  call    vIdentifySource
0x1800060b7  lea     rdx, aConcatenationT_0; "Concatenation to produce expanded macro"...
0x1800060be  jmp     short loc_1800060FA
0x1800060c0  lea     eax, [rdx-30h]
0x1800060c3  cmp     al, 2Fh ; '/'
0x1800060c5  ja      loc_180005FA7
0x1800060cb  movzx   eax, al
0x1800060ce  bt      r8, rax
0x1800060d2  jb      loc_180005FA0
0x1800060d8  jmp     loc_180005FA7
0x1800060dd  inc     ecx
0x1800060df  cmp     ecx, r8d
0x1800060e2  jb      loc_180006030
0x1800060e8  mov     rdx, rbx
0x1800060eb  mov     rcx, rdi
0x1800060ee  call    vIdentifySource
0x1800060f3  lea     rdx, aMacrorefNotRes; "=MacroRef not resolved. Not defined or "...
0x1800060fa  lea     rcx, aBresolvevaluem; "BResolveValueMacroReference"
0x180006101  call    WriteDbgTraceErrorGpd
0x180006106  xor     eax, eax
0x180006108  add     rsp, 78h
0x18000610c  pop     r15
0x18000610e  pop     r14
0x180006110  pop     r13
0x180006112  pop     r12
0x180006114  pop     rdi
0x180006115  pop     rsi
0x180006116  pop     rbx
0x180006117  pop     rbp
0x180006118  retn
0x180006119  mov     rdx, rbx
0x18000611c  mov     rcx, rdi
0x18000611f  call    vIdentifySource
0x180006124  lea     rdx, aNoMacronameDet; "No MacroName detected after '='."
0x18000612b  jmp     short loc_1800060FA
0x18000612d  cmp     r15d, [rbx+1B8h]
0x180006134  jnb     loc_180006072
0x18000613a  mov     r12, [rbx+1B0h]
0x180006141  mov     r8, r14; Size
0x180006144  mov     rdx, [rdx+18h]; Src
0x180006148  add     r12, rax
0x18000614b  mov     rcx, r12; void *
0x18000614e  call    memcpy_0
0x180006153  mov     eax, dword ptr [rbp+var_28+8]
0x180006156  mov     [rbx+1BCh], r15d
0x18000615d  test    eax, eax
0x18000615f  jz      loc_1800063E9
0x180006165  mov     r15d, [rbp+arg_10]
0x180006169  add     eax, r14d
0x18000616c  mov     r14, [rbp+arg_18]
0x180006170  mov     dword ptr [rbp+var_28+8], eax
0x180006173  jmp     loc_180005F5A
0x180006178  test    r15b, r15b
0x18000617b  jnz     short loc_1800061B4
0x18000617d  test    r13d, r13d
0x180006180  jz      short loc_1800061A2
0x180006182  movzx   eax, byte ptr [r14]
0x180006186  cmp     al, 20h ; ' '
0x180006188  jnz     short loc_180006195
0x18000618a  inc     r14
0x18000618d  add     r13d, 0FFFFFFFFh
0x180006191  jnz     short loc_180006182
0x180006193  jmp     short loc_180006199
0x180006195  cmp     al, 9
0x180006197  jz      short loc_18000618A
0x180006199  test    r13d, r13d
0x18000619c  jnz     loc_180006420
0x1800061a2  movups  xmm0, [rbp+var_28]
0x1800061a6  mov     eax, 1
0x1800061ab  movups  xmmword ptr [rdi+18h], xmm0
0x1800061af  jmp     loc_180006108
0x1800061b4  cmp     r15b, 22h ; '"'
0x1800061b8  jz      loc_180006276
0x1800061be  cmp     r15b, 25h ; '%'
0x1800061c2  jz      loc_180006365
0x1800061c8  inc     r13d
0x1800061cb  dec     r14
0x1800061ce  mov     dword ptr [rbp+var_48+8], r13d
0x1800061d2  mov     qword ptr [rbp+var_48], r14
0x1800061d6  mov     r8, r14
0x1800061d9  mov     r9d, r13d
0x1800061dc  nop     dword ptr [rax+00h]
0x1800061e0  test    r9d, r9d
0x1800061e3  jz      loc_180006344
0x1800061e9  xor     ecx, ecx
0x1800061eb  cmp     ecx, 3
0x1800061ee  jnb     short loc_180006206
0x1800061f0  movzx   edx, byte ptr [r8]
0x1800061f4  movzx   r15d, byte ptr [rcx+r10+87B68h]
0x1800061fd  cmp     dl, r15b
0x180006200  jz      short loc_18000620E
0x180006202  inc     ecx
0x180006204  jmp     short loc_1800061EB
0x180006206  inc     r8
0x180006209  dec     r9d
0x18000620c  jmp     short loc_1800061E0
0x18000620e  cmp     dl, 22h ; '"'
0x180006211  jz      short loc_180006268
0x180006213  cmp     dl, 3Ch ; '<'
0x180006216  jz      short loc_180006268
0x180006218  sub     r13d, r9d
0x18000621b  mov     qword ptr [rbp+var_38], r14
0x18000621f  lea     r14, [r8+1]
0x180006223  mov     dword ptr [rbp+var_38+8], r13d
0x180006227  mov     qword ptr [rbp+var_48], r14
0x18000622b  lea     r13d, [r9-1]
0x18000622f  xorps   xmm0, xmm0
0x180006232  mov     dword ptr [rbp+var_48+8], r13d
0x180006236  mov     r8, rbx
0x180006239  lea     rdx, [rbp+var_38]
0x18000623d  lea     rcx, [rbp+var_18]
0x180006241  movups  [rbp+var_18], xmm0
0x180006245  call    BcopyToTmpHeap
0x18000624a  test    eax, eax
0x18000624c  jz      loc_1800060AC
0x180006252  test    r12d, r12d
0x180006255  jz      loc_180006358
0x18000625b  add     r12d, dword ptr [rbp+var_18+8]
0x18000625f  mov     dword ptr [rbp+var_28+8], r12d
0x180006263  jmp     loc_180005F5E
0x180006268  cmp     r9d, r13d
0x18000626b  jnb     short loc_180006218
0x18000626d  cmp     byte ptr [r8-1], 25h ; '%'
0x180006272  jz      short loc_180006202
0x180006274  jmp     short loc_180006218
0x180006276  mov     r8, r14
0x180006279  mov     edx, r13d
0x18000627c  nop     dword ptr [rax+00h]
0x180006280  test    edx, edx
0x180006282  jz      loc_180006409
0x180006288  xor     ecx, ecx
0x18000628a  cmp     ecx, 1
0x18000628d  jnb     short loc_1800062A1
0x18000628f  movzx   r9d, byte ptr [r8]
0x180006293  cmp     r9b, [rcx+r10+7C920h]
0x18000629b  jz      short loc_1800062A8
0x18000629d  inc     ecx
0x18000629f  jmp     short loc_18000628A
0x1800062a1  inc     r8
0x1800062a4  dec     edx
0x1800062a6  jmp     short loc_180006280
0x1800062a8  cmp     r9b, 22h ; '"'
0x1800062ac  jz      short loc_180006327
0x1800062ae  cmp     r9b, 3Ch ; '<'
0x1800062b2  jz      short loc_180006327
0x1800062b4  sub     r13d, edx
0x1800062b7  mov     rcx, r14
0x1800062ba  mov     eax, r13d
0x1800062bd  lea     r14, [r8+1]
0x1800062c1  add     eax, 2
0x1800062c4  mov     qword ptr [rbp+var_48], r14
0x1800062c8  lea     r13d, [rdx-1]
0x1800062cc  mov     dword ptr [rbp+var_38+8], eax
0x1800062cf  lea     rax, [rcx-1]
0x1800062d3  mov     dword ptr [rbp+var_48+8], r13d
0x1800062d7  xorps   xmm0, xmm0
0x1800062da  mov     qword ptr [rbp+var_38], rax
0x1800062de  lea     rcx, [rbp+var_18]
0x1800062e2  mov     r8, rbx
0x1800062e5  lea     rdx, [rbp+var_38]
0x1800062e9  movups  [rbp+var_18], xmm0
0x1800062ed  call    BcopyToTmpHeap
0x1800062f2  test    eax, eax
0x1800062f4  jz      loc_1800060AC
0x1800062fa  test    r12d, r12d
0x1800062fd  jz      loc_1800063C5
0x180006303  add     r12d, dword ptr [rbp+var_18+8]
0x180006307  mov     dword ptr [rbp+var_28+8], r12d
0x18000630b  test    r13d, r13d
0x18000630e  jz      short loc_18000633C
0x180006310  movzx   r15d, byte ptr [r14]
0x180006314  dec     r13d
0x180006317  inc     r14
0x18000631a  mov     dword ptr [rbp+var_48+8], r13d
0x18000631e  mov     qword ptr [rbp+var_48], r14
0x180006322  jmp     loc_180005F5E
0x180006327  cmp     edx, r13d
0x18000632a  jnb     short loc_1800062B4
0x18000632c  cmp     byte ptr [r8-1], 25h ; '%'
0x180006331  jz      loc_18000629D
0x180006337  jmp     loc_1800062B4
  ... truncated ...
```
