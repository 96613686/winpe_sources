# GPDCombineOptionArray

- ea: `0x180005100`
- end: `0x1800054f5`
- name: `GPDCombineOptionArray`
- size: `1013`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000420c`
- `0x180004550`
- `0x18002540c`
- `0x18003388c`
- `0x18003ea30`

## callees

- `0x1800047c0`
- `0x180005100`
- `0x180006970`
- `0x180007220`

## import_xrefs

- `KERNEL32!GetSystemDefaultLCID` at `0x180005318`
- `KERNEL32!GetSystemDefaultLCID` at `0x180005318`

## string_xrefs

- `0x1800052e2`: `GPDCombineOptionArray`
- `0x1800053d8`: `GPDCombineOptionArray`
- `0x1800053d1`: `CombineOptionArray: EextractValueFromTree failed.`

## pseudocode

```c
__int64 __fastcall GPDCombineOptionArray(__int64 a1, __int64 a2, __int64 j, __int64 a4, __int64 a5)
{
  unsigned int v7; // ecx
  unsigned int v8; // r14d
  unsigned int v10; // edx
  unsigned int v11; // ecx
  __int64 v12; // r13
  unsigned int v13; // r10d
  unsigned int v14; // ebx
  __int64 v15; // rax
  int *v16; // rsi
  __int64 v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // rax
  _BYTE *v20; // rcx
  __int64 v21; // rbx
  int v22; // ecx
  __int64 v23; // rcx
  LCID SystemDefaultLCID; // eax
  unsigned __int64 v26; // rdx
  __int64 v27; // r9
  bool v28; // zf
  unsigned int v29; // r10d
  unsigned int i; // edx
  __int64 v31; // r9
  _BYTE *v32; // rdx
  int v33; // [rsp+50h] [rbp-48h] BYREF
  int v34; // [rsp+54h] [rbp-44h] BYREF
  int v35; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int v36; // [rsp+B0h] [rbp+18h] BYREF
  int v37; // [rsp+B8h] [rbp+20h] BYREF

  v7 = *(_DWORD *)(a1 + 20);
  v8 = j;
  if ( a4 )
  {
    v29 = v7;
    for ( i = 0; i < v29; ++i )
    {
      j = *(unsigned __int8 *)(a4 + 2LL * i + 1);
      if ( *(_BYTE *)(a4 + 2LL * i + 1) )
      {
        do
        {
          j = *(unsigned __int8 *)(a4 + 2 * j + 1);
          ++v7;
        }
        while ( (_DWORD)j );
      }
    }
  }
  v10 = *(_DWORD *)(a1 + 24);
  v11 = v10 + v7;
  v12 = a5;
  if ( a5 )
  {
    for ( j = 0; (unsigned int)j < v10; j = (unsigned int)(j + 1) )
    {
      if ( *(_BYTE *)(a5 + 2LL * (unsigned int)j + 1) )
      {
        do
          ++v11;
        while ( *(_BYTE *)(a5 + 2LL * *(unsigned __int8 *)(a5 + 2LL * (unsigned int)j + 1) + 1) );
      }
    }
  }
  if ( !v8 )
    return 0;
  if ( v11 > v8 )
    return 0;
  v13 = *(_DWORD *)(a1 + 120);
  v36 = v13;
  if ( v13 > v8 )
    return 0;
  v34 = 0;
  v14 = 0;
  v35 = 0;
  while ( 1 )
  {
    if ( v14 >= *(_DWORD *)(a1 + 120) || v14 >= v8 )
    {
      v36 = -1;
      if ( !(unsigned int)BgetLocFeaIndex(a1, &v36, j, 0) )
        return 0;
      v21 = v36;
      v22 = -1;
      if ( v36 != -1 && v36 < *(_DWORD *)(a1 + 120) )
      {
        SystemDefaultLCID = GetSystemDefaultLCID();
        if ( SystemDefaultLCID )
        {
          v26 = *(unsigned int *)(396 * v21 + *(_QWORD *)(a1 + 112) + 360);
          if ( (_DWORD)v26 != 0x7FFFFFFF )
          {
            if ( (v26 & 0x80000000) != 0LL )
            {
LABEL_34:
              WriteDbgTraceErrorGpd(
                "BgetLocFeaOptIndex",
                "OptionID for Feature Locale cannot be determined",
                SystemDefaultLCID);
            }
            else
            {
              v27 = *(_QWORD *)(a1 + 144);
              if ( *(_DWORD *)(v27 + 20 * v26) != -1 )
                goto LABEL_30;
              if ( *(_DWORD *)(v27 + 20 * v26 + 8) != -1 )
              {
                _mm_lfence();
                v27 = *(_QWORD *)(a1 + 144);
                LODWORD(v26) = *(_DWORD *)(v27 + 20 * v26 + 8);
LABEL_30:
                while ( (_DWORD)v26 != -1 )
                {
                  v28 = *(_DWORD *)(v27 + 20LL * (unsigned int)v26 + 16) == 1;
                  v26 = v27 + 20LL * (unsigned int)v26;
                  if ( !v28 )
                    goto LABEL_34;
                  if ( *(_DWORD *)(*(unsigned int *)(v26 + 12) + *(_QWORD *)(a1 + 128)) == SystemDefaultLCID )
                  {
                    v22 = *(_DWORD *)(v26 + 4);
                    goto LABEL_20;
                  }
                  LODWORD(v26) = *(_DWORD *)(v26 + 8);
                }
              }
            }
          }
        }
        else
        {
          WriteDbgTraceErrorGpd("BgetLocFeaOptIndex", "Cannot determine System locale\n", 0);
        }
        v22 = -1;
      }
LABEL_20:
      if ( (_DWORD)v21 == -1 )
        return 1;
      if ( v22 == -1 )
      {
        v23 = *(unsigned int *)(396 * v21 + *(_QWORD *)(a1 + 112) + 8);
        if ( (int)v23 >= 0 )
          goto LABEL_23;
        LODWORD(v23) = v23 & 0x7FFFFFFF;
        v22 = *(_DWORD *)(v23 + *(_QWORD *)(a1 + 128));
      }
      if ( (unsigned int)v21 < v8 )
      {
        *(_BYTE *)(a2 + 2 * v21) = v22;
        *(_BYTE *)(a2 + 2 * v21 + 1) = 0;
        return 1;
      }
LABEL_23:
      WriteDbgTraceErrorGpd(
        "GPDCombineOptionArray",
        "Error in processing Default Option for Feature Locale. Continuing....");
      return 1;
    }
    v15 = *(_QWORD *)(a1 + 96);
    v16 = &v35;
    LODWORD(a5) = 0;
    v17 = v12;
    v33 = 0;
    if ( v14 < *(_DWORD *)(v15 + 136) )
      break;
LABEL_13:
    v20 = (_BYTE *)(a2 + 2LL * v14);
    if ( v17 )
    {
      j = (unsigned int)*v16;
      *v20 = *(_BYTE *)(v17 + 2 * j);
      if ( *(_BYTE *)(v17 + 2 * j + 1) )
      {
        v20[1] = v13;
        LODWORD(v31) = j;
        if ( v13 >= v8 )
          return 0;
        while ( 1 )
        {
          v31 = *(unsigned __int8 *)(v17 + 2LL * (unsigned int)v31 + 1);
          if ( !(_DWORD)v31 )
            break;
          if ( v13 >= v8 )
            return 0;
          v32 = (_BYTE *)(a2 + 2LL * v13);
          *v32 = *(_BYTE *)(v17 + 2 * v31);
          v32[1] = ++v13;
          v36 = v13;
        }
        *(_BYTE *)(a2 + 2LL * (v13 - 1) + 1) = 0;
      }
      else
      {
        v20[1] = 0;
      }
      ++v14;
      *v16 = j + 1;
    }
    else
    {
      *(_WORD *)v20 = 255;
      ++v14;
    }
  }
  v18 = *(unsigned int *)(a1 + 208);
  v19 = *(_QWORD *)(a1 + 112);
  v37 = 0;
  if ( (unsigned int)EextractValueFromTree(a1, v18, &a5, 4, &v33, *(_DWORD *)(396LL * v14 + v19), a2, 0, &v37) == 1 )
  {
    v13 = v36;
    if ( (_DWORD)a5 != 2 )
    {
      v17 = a4;
      v16 = &v34;
    }
    goto LABEL_13;
  }
  WriteDbgTraceErrorGpd("GPDCombineOptionArray", "CombineOptionArray: EextractValueFromTree failed.");
  return 0;
}

```

## disassembly

```asm
0x180005100  push    rbp
0x180005102  push    r12
0x180005104  push    r13
0x180005106  push    r14
0x180005108  push    r15
0x18000510a  sub     rsp, 70h
0x18000510e  mov     r12, r9
0x180005111  mov     rbp, rcx
0x180005114  mov     ecx, [rcx+14h]
0x180005117  xor     r9d, r9d
0x18000511a  mov     r14d, r8d
0x18000511d  mov     r15, rdx
0x180005120  test    r12, r12
0x180005123  jnz     loc_18000543F
0x180005129  mov     edx, [rbp+18h]
0x18000512c  add     ecx, edx
0x18000512e  mov     r13, [rsp+98h+arg_20]
0x180005136  test    r13, r13
0x180005139  jnz     loc_180005416
0x18000513f  mov     [rsp+98h+arg_8], rbx
0x180005147  mov     [rsp+98h+var_30], rsi
0x18000514c  mov     [rsp+98h+var_38], rdi
0x180005151  test    r14d, r14d
0x180005154  jz      loc_1800053E4
0x18000515a  cmp     ecx, r14d
0x18000515d  ja      loc_1800053E4
0x180005163  mov     r10d, [rbp+78h]
0x180005167  mov     [rsp+98h+arg_10], r10d
0x18000516f  cmp     r10d, r14d
0x180005172  ja      loc_1800053E4
0x180005178  mov     [rsp+98h+var_44], r9d
0x18000517d  mov     ebx, r9d
0x180005180  mov     [rsp+98h+arg_0], r9d
0x180005188  nop     dword ptr [rax+rax+00000000h]
0x180005190  cmp     ebx, [rbp+78h]
0x180005193  jnb     loc_180005283
0x180005199  cmp     ebx, r14d
0x18000519c  jnb     loc_180005283
0x1800051a2  mov     rax, [rbp+60h]
0x1800051a6  lea     rsi, [rsp+98h+arg_0]
0x1800051ae  mov     dword ptr [rsp+98h+arg_20], r9d
0x1800051b6  mov     rdi, r13
0x1800051b9  mov     [rsp+98h+var_48], r9d
0x1800051be  cmp     ebx, [rax+88h]
0x1800051c4  jnb     short loc_180005245
0x1800051c6  lea     rdx, [rsp+98h+arg_18]
0x1800051ce  mov     eax, ebx
0x1800051d0  mov     [rsp+98h+var_58], rdx
0x1800051d5  lea     r8, [rsp+98h+arg_20]
0x1800051dd  mov     edx, [rbp+0D0h]
0x1800051e3  imul    rcx, rax, 18Ch
0x1800051ea  mov     rax, [rbp+70h]
0x1800051ee  mov     [rsp+98h+var_60], r9d
0x1800051f3  mov     [rsp+98h+var_68], r15
0x1800051f8  mov     [rsp+98h+arg_18], r9d
0x180005200  mov     r9d, 4
0x180005206  mov     eax, [rcx+rax]
0x180005209  mov     rcx, rbp
0x18000520c  mov     [rsp+98h+var_70], eax
0x180005210  lea     rax, [rsp+98h+var_48]
0x180005215  mov     [rsp+98h+var_78], rax
0x18000521a  call    EextractValueFromTree
0x18000521f  cmp     eax, 1
0x180005222  jnz     loc_1800053D1
0x180005228  mov     r10d, [rsp+98h+arg_10]
0x180005230  xor     r9d, r9d
0x180005233  cmp     dword ptr [rsp+98h+arg_20], 2
0x18000523b  jz      short loc_180005245
0x18000523d  mov     rdi, r12
0x180005240  lea     rsi, [rsp+98h+var_44]
0x180005245  mov     eax, ebx
0x180005247  lea     rcx, [r15+rax*2]
0x18000524b  test    rdi, rdi
0x18000524e  jz      short loc_180005277
0x180005250  mov     r8d, [rsi]
0x180005253  movzx   eax, byte ptr [rdi+r8*2]
0x180005258  mov     [rcx], al
0x18000525a  cmp     byte ptr [rdi+r8*2+1], 0
0x180005260  jnz     loc_180005487
0x180005266  mov     byte ptr [rcx+1], 0
0x18000526a  lea     eax, [r8+1]
0x18000526e  inc     ebx
0x180005270  mov     [rsi], eax
0x180005272  jmp     loc_180005190
0x180005277  mov     word ptr [rcx], 0FFh
0x18000527c  inc     ebx
0x18000527e  jmp     loc_180005190
0x180005283  lea     rdx, [rsp+98h+arg_10]
0x18000528b  mov     [rsp+98h+arg_10], 0FFFFFFFFh
0x180005296  mov     rcx, rbp
0x180005299  call    BgetLocFeaIndex
0x18000529e  test    eax, eax
0x1800052a0  jz      loc_1800053E4
0x1800052a6  mov     ebx, [rsp+98h+arg_10]
0x1800052ad  mov     ecx, 0FFFFFFFFh
0x1800052b2  cmp     ebx, ecx
0x1800052b4  jnz     short loc_180005313
0x1800052b6  cmp     ebx, 0FFFFFFFFh
0x1800052b9  jz      short loc_1800052EE
0x1800052bb  cmp     ecx, 0FFFFFFFFh
0x1800052be  jnz     loc_1800053B9
0x1800052c4  mov     rax, [rbp+70h]
0x1800052c8  imul    rcx, rbx, 18Ch
0x1800052cf  mov     ecx, [rcx+rax+8]
0x1800052d3  test    ecx, ecx
0x1800052d5  js      loc_1800054E2
0x1800052db  lea     rdx, aErrorInProcess; "Error in processing Default Option for "...
0x1800052e2  lea     rcx, aGpdcombineopti; "GPDCombineOptionArray"
0x1800052e9  call    WriteDbgTraceErrorGpd
0x1800052ee  mov     eax, 1
0x1800052f3  mov     rdi, [rsp+98h+var_38]
0x1800052f8  mov     rsi, [rsp+98h+var_30]
0x1800052fd  mov     rbx, [rsp+98h+arg_8]
0x180005305  add     rsp, 70h
0x180005309  pop     r15
0x18000530b  pop     r14
0x18000530d  pop     r13
0x18000530f  pop     r12
0x180005311  pop     rbp
0x180005312  retn
0x180005313  cmp     ebx, [rbp+78h]
0x180005316  jnb     short loc_1800052B6
0x180005318  call    cs:__imp_GetSystemDefaultLCID
0x18000531e  mov     r8d, eax
0x180005321  test    eax, eax
0x180005323  jz      loc_18000540D
0x180005329  mov     rax, [rbp+70h]
0x18000532d  imul    rcx, rbx, 18Ch
0x180005334  mov     edx, [rcx+rax+168h]
0x18000533b  cmp     edx, 7FFFFFFFh
0x180005341  jz      short loc_1800053AF
0x180005343  test    edx, edx
0x180005345  js      short loc_18000539C
0x180005347  mov     r9, [rbp+90h]
0x18000534e  lea     rcx, [rdx+rdx*4]
0x180005352  lea     rcx, ds:0[rcx*4]
0x18000535a  cmp     dword ptr [r9+rcx], 0FFFFFFFFh
0x18000535f  lea     rax, [r9+rcx]
0x180005363  jz      loc_1800053F3
0x180005369  nop     dword ptr [rax+00000000h]
0x180005370  cmp     edx, 0FFFFFFFFh
0x180005373  jz      short loc_1800053AF
0x180005375  mov     eax, edx
0x180005377  lea     rcx, [rax+rax*4]
0x18000537b  cmp     dword ptr [r9+rcx*4+10h], 1
0x180005381  lea     rdx, [r9+rcx*4]
0x180005385  jnz     short loc_18000539C
0x180005387  mov     ecx, [rdx+0Ch]
0x18000538a  mov     rax, [rbp+80h]
0x180005391  cmp     [rcx+rax], r8d
0x180005395  jz      short loc_1800053EB
0x180005397  mov     edx, [rdx+8]
0x18000539a  jmp     short loc_180005370
0x18000539c  lea     rdx, aOptionidForFea; "OptionID for Feature Locale cannot be d"...
0x1800053a3  lea     rcx, aBgetlocfeaopti; "BgetLocFeaOptIndex"
0x1800053aa  call    WriteDbgTraceErrorGpd
0x1800053af  mov     ecx, 0FFFFFFFFh
0x1800053b4  jmp     loc_1800052B6
0x1800053b9  cmp     ebx, r14d
0x1800053bc  jnb     loc_1800052DB
0x1800053c2  mov     [r15+rbx*2], cl
0x1800053c6  mov     byte ptr [r15+rbx*2+1], 0
0x1800053cc  jmp     loc_1800052EE
0x1800053d1  lea     rdx, aCombineoptiona; "CombineOptionArray: EextractValueFromTr"...
0x1800053d8  lea     rcx, aGpdcombineopti; "GPDCombineOptionArray"
0x1800053df  call    WriteDbgTraceErrorGpd
0x1800053e4  xor     eax, eax
0x1800053e6  jmp     loc_1800052F3
0x1800053eb  mov     ecx, [rdx+4]
0x1800053ee  jmp     loc_1800052B6
0x1800053f3  cmp     dword ptr [rax+8], 0FFFFFFFFh
0x1800053f7  jz      short loc_1800053AF
0x1800053f9  lfence
0x1800053fc  mov     r9, [rbp+90h]
0x180005403  mov     edx, [r9+rcx+8]
0x180005408  jmp     loc_180005370
0x18000540d  lea     rdx, aCannotDetermin; "Cannot determine System locale\n"
0x180005414  jmp     short loc_1800053A3
0x180005416  mov     r8d, r9d
0x180005419  test    edx, edx
0x18000541b  jz      loc_18000513F
0x180005421  mov     eax, r8d
0x180005424  movzx   r9d, byte ptr [r13+rax*2+1]
0x18000542a  test    r9d, r9d
0x18000542d  jnz     short loc_180005478
0x18000542f  inc     r8d
0x180005432  cmp     r8d, edx
0x180005435  jb      short loc_180005421
0x180005437  xor     r9d, r9d
0x18000543a  jmp     loc_18000513F
0x18000543f  mov     r10d, ecx
0x180005442  mov     edx, r9d
0x180005445  test    ecx, ecx
0x180005447  jz      loc_180005129
0x18000544d  nop     dword ptr [rax]
0x180005450  mov     eax, edx
0x180005452  movzx   r8d, byte ptr [r12+rax*2+1]
0x180005458  test    r8d, r8d
0x18000545b  jnz     short loc_180005469
0x18000545d  inc     edx
0x18000545f  cmp     edx, r10d
0x180005462  jb      short loc_180005450
0x180005464  jmp     loc_180005129
0x180005469  movzx   r8d, byte ptr [r12+r8*2+1]
0x18000546f  inc     ecx
0x180005471  test    r8d, r8d
0x180005474  jnz     short loc_180005469
0x180005476  jmp     short loc_18000545D
0x180005478  movzx   r9d, byte ptr [r13+r9*2+1]
0x18000547e  inc     ecx
0x180005480  test    r9d, r9d
0x180005483  jnz     short loc_180005478
0x180005485  jmp     short loc_18000542F
0x180005487  mov     [rcx+1], r10b
0x18000548b  mov     r9d, r8d
0x18000548e  cmp     r10d, r14d
0x180005491  jnb     loc_1800053E4
0x180005497  mov     eax, r9d
0x18000549a  movzx   r9d, byte ptr [rdi+rax*2+1]
0x1800054a0  test    r9d, r9d
0x1800054a3  jz      short loc_1800054D0
0x1800054a5  cmp     r10d, r14d
0x1800054a8  jnb     loc_1800053E4
0x1800054ae  movzx   ecx, byte ptr [rdi+r9*2]
0x1800054b3  mov     eax, r10d
0x1800054b6  lea     rdx, [r15+rax*2]
0x1800054ba  lea     eax, [r10+1]
0x1800054be  mov     [rdx], cl
0x1800054c0  inc     r10d
0x1800054c3  mov     [rdx+1], al
0x1800054c6  mov     [rsp+98h+arg_10], r10d
0x1800054ce  jmp     short loc_180005497
0x1800054d0  lea     eax, [r10-1]
0x1800054d4  xor     r9d, r9d
0x1800054d7  mov     byte ptr [r15+rax*2+1], 0
0x1800054dd  jmp     loc_18000526A
0x1800054e2  mov     rax, [rbp+80h]
0x1800054e9  btr     ecx, 1Fh
0x1800054ed  mov     ecx, [rcx+rax]
0x1800054f0  jmp     loc_1800053B9
```
