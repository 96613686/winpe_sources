# BSelectivelyEnumEnabledOptions

- ea: `0x180007800`
- end: `0x180007f23`
- name: `BSelectivelyEnumEnabledOptions`
- size: `1827`
- prototype: `__int64 __fastcall(_QWORD *, __int64, unsigned int, __int64, _DWORD *Src, unsigned int, _DWORD *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007320`
- `0x180050688`
- `0x1800511a8`

## callees

- `0x180007150`
- `0x180007800`
- `0x18003bbb4`
- `0x180049d00`
- `0x18004a71c`
- `0x180076660`

## string_xrefs

- `0x180007e9f`: `Internal error.  BSelectivelyEnumEnabledOptions - Unexpected Sublevel found for atrInvalidCombos.`

## pseudocode

```c
__int64 __fastcall BSelectivelyEnumEnabledOptions(
        _QWORD *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        _DWORD *Src,
        unsigned int a6,
        _DWORD *a7)
{
  _DWORD *v7; // r12
  _QWORD *v8; // r11
  __int64 v10; // r10
  __int64 v11; // r8
  __int64 v12; // rbp
  __int64 i; // rdi
  unsigned int v14; // ecx
  unsigned __int8 *v15; // rbp
  int v16; // edx
  int v17; // r9d
  __int64 v18; // r8
  __int64 v19; // rcx
  unsigned int v20; // ebp
  __int64 v21; // r14
  __int64 v22; // rsi
  _DWORD *v23; // r10
  int v24; // edx
  __int64 v25; // r9
  __int64 v26; // r12
  __int64 v27; // r15
  int v28; // r13d
  __int64 v29; // rdi
  _DWORD *v30; // r10
  int v31; // edx
  __int64 v32; // rcx
  __int64 result; // rax
  __int64 v35; // rdi
  __int64 v36; // rcx
  unsigned int v37; // edx
  __int64 v38; // rax
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // r9
  unsigned int v43; // edx
  __int64 v44; // rdx
  unsigned int *v45; // rax
  int v46; // edi
  __int64 v47; // rdx
  __int64 v48; // rcx
  unsigned __int8 *v49; // r8
  unsigned int v50; // ecx
  int v51; // esi
  int v52; // ebp
  int v53; // r14d
  __int64 v54; // r11
  int v55; // eax
  _DWORD *v56; // rax
  int v57; // edx
  __int64 v58; // rcx
  _DWORD *v59; // rdi
  unsigned int v60; // ecx
  int v61; // [rsp+20h] [rbp-898h]
  unsigned int v62; // [rsp+24h] [rbp-894h]
  unsigned int v65; // [rsp+38h] [rbp-880h]
  unsigned int v66; // [rsp+3Ch] [rbp-87Ch]
  unsigned int v67; // [rsp+48h] [rbp-870h]
  _DWORD *v68; // [rsp+50h] [rbp-868h]
  __int64 v69; // [rsp+58h] [rbp-860h]
  __int64 v70; // [rsp+60h] [rbp-858h]
  _DWORD v71[512]; // [rsp+70h] [rbp-848h] BYREF

  v7 = Src;
  v8 = a1;
  v10 = a3;
  v11 = a2;
  v61 = v10;
  v68 = Src;
  v12 = *(unsigned int *)(a1[14] + 396 * v10 + 392);
  v69 = 396 * v10;
  v65 = v12;
  if ( (unsigned int)v12 > 0x200 )
    return 0;
  v67 = *(_DWORD *)(a1[12] + 108LL);
  v70 = a1[9];
  if ( !a7 )
  {
    if ( (_DWORD)v12 )
    {
      v58 = *(unsigned int *)(a1[14] + 396 * v10 + 392);
      v59 = Src;
      while ( v58 )
      {
        *v59++ = 1;
        --v58;
      }
    }
    if ( Src )
      goto LABEL_5;
    return 0;
  }
  *a7 = v10;
  a7[2] = -1;
  if ( Src )
  {
    if ( (_DWORD)v12 )
    {
      memcpy_0(v71, Src, 4 * v12);
      v8 = a1;
      LODWORD(v10) = v61;
      v11 = a2;
    }
  }
  else
  {
    if ( a6 >= 0x200 )
      return 0;
    if ( (_DWORD)v12 )
    {
      memset_0(v71, 0, 4 * v12);
      v8 = a1;
      LODWORD(v10) = v61;
      v11 = a2;
    }
    v71[a6] = 1;
  }
  v7 = v71;
  v68 = v71;
LABEL_5:
  v66 = 0;
  for ( i = 0; (unsigned int)i < *((_DWORD *)v8 + 30); i = (unsigned int)(i + 1) )
  {
    if ( (_DWORD)i != (_DWORD)v10 && (!a4 || *(_DWORD *)(a4 + 4 * i)) )
    {
      v14 = i;
      v66 = 1;
      while ( 1 )
      {
        v15 = (unsigned __int8 *)(v11 + 2LL * v14);
        v16 = *(_DWORD *)(396LL * (unsigned int)i + v8[14] + 136);
        if ( v16 == 0x7FFFFFFF )
          goto LABEL_12;
        if ( v16 < 0 )
          break;
        v17 = *v15;
        v18 = v8[18];
        while ( 1 )
        {
          v19 = 20LL * (unsigned int)v16;
          if ( *(_DWORD *)(v18 + v19 + 4) == v17 )
            break;
          v16 = *(_DWORD *)(v19 + v18 + 8);
          if ( v16 == -1 )
            goto LABEL_12;
        }
        if ( *(_DWORD *)(v19 + v18 + 16) != 1 )
        {
          WriteDbgTraceErrorGpd(
            (__int64)"BEnumImposedConstraintsOnFeature",
            "Internal error.  BEnumImposedConstraintsOnFeature - Unexpected Sublevel found for atrConstraints.");
          v66 = 0;
          goto LABEL_108;
        }
        v37 = *(_DWORD *)(*(unsigned int *)(v19 + v18 + 12) + v8[16]);
        while ( 1 )
        {
          v38 = v8[20];
          v39 = 12LL * v37;
          if ( *(_DWORD *)(v39 + v38 + 4) == (_DWORD)v10 )
          {
            v40 = *(unsigned int *)(v39 + v38 + 8);
            if ( v7[v40] == 1 )
            {
              v7[v40] = 0;
              if ( a7 )
                break;
            }
          }
          v37 = *(_DWORD *)(v39 + v8[20]);
          if ( v37 == -1 )
            goto LABEL_12;
        }
        a7[1] = *(_DWORD *)(v39 + v8[20] + 8);
        a7[2] = i;
        a7[3] = v17;
LABEL_51:
        if ( a7[2] != -1 )
          return 1;
LABEL_13:
        v14 = v15[1];
        v11 = a2;
        if ( !v15[1] )
          goto LABEL_14;
      }
      WriteDbgTraceErrorGpd(
        (__int64)"DwFindNodeInCurLevel",
        "Internal error.  DwFindNodeInCurLevel - Unexpected branchless node found.");
LABEL_108:
      v8 = a1;
      LODWORD(v10) = v61;
LABEL_12:
      if ( !a7 )
        goto LABEL_13;
      goto LABEL_51;
    }
LABEL_14:
    ;
  }
  v20 = v65;
  v21 = v69 + v8[14];
  v22 = 0;
LABEL_21:
  while ( (unsigned int)v22 < v65 )
  {
    v23 = &v7[v22];
    if ( !*v23 )
      goto LABEL_24;
    v24 = *(_DWORD *)(v21 + 136);
    if ( v24 == 0x7FFFFFFF )
      goto LABEL_24;
    if ( v24 < 0 )
    {
      WriteDbgTraceErrorGpd(
        (__int64)"DwFindNodeInCurLevel",
        "Internal error.  DwFindNodeInCurLevel - Unexpected branchless node found.",
        v11);
      v8 = a1;
      v22 = (unsigned int)(v22 + 1);
      v11 = a2;
    }
    else
    {
      v35 = v8[18];
      while ( 1 )
      {
        v36 = 20LL * (unsigned int)v24;
        if ( *(_DWORD *)(v36 + v35 + 4) == (_DWORD)v22 )
          break;
        v24 = *(_DWORD *)(v36 + v35 + 8);
        if ( v24 == -1 )
        {
          v22 = (unsigned int)(v22 + 1);
          goto LABEL_21;
        }
      }
      if ( *(_DWORD *)(v36 + v35 + 16) == 1 )
      {
        v42 = v8[20];
        v43 = *(_DWORD *)(*(unsigned int *)(v36 + v35 + 12) + v8[16]);
        while ( 1 )
        {
          v44 = 12LL * v43;
          if ( !a4 )
            break;
          v45 = (unsigned int *)(v42 + v44);
          if ( *(_DWORD *)(a4 + 4LL * *(unsigned int *)(v42 + v44 + 4)) )
            break;
LABEL_68:
          v43 = *v45;
          if ( *v45 == -1 )
          {
            v22 = (unsigned int)(v22 + 1);
            goto LABEL_21;
          }
        }
        v46 = *(_DWORD *)(v44 + v42 + 8);
        v45 = (unsigned int *)(v44 + v42);
        v47 = *(unsigned int *)(v44 + v42 + 4);
        if ( *(unsigned __int8 *)(v11 + 2 * v47) != v46 )
        {
          v48 = *(unsigned __int8 *)(v11 + 2 * v47 + 1);
          while ( 1 )
          {
            if ( !(_DWORD)v48 )
              goto LABEL_68;
            v49 = (unsigned __int8 *)(v11 + 2 * v48);
            if ( *v49 == v46 )
              break;
            v48 = v49[1];
            v11 = a2;
          }
          v11 = a2;
        }
        if ( a7 )
        {
          a7[2] = v47;
          v60 = v45[2];
          result = 1;
          a7[3] = v60;
          *v23 = 0;
          a7[1] = v22;
          return result;
        }
        *v23 = 0;
LABEL_24:
        v22 = (unsigned int)(v22 + 1);
      }
      else
      {
        WriteDbgTraceErrorGpd(
          (__int64)"BSelectivelyEnumEnabledOptions",
          "Internal error.  BSelectivelyEnumEnabledOptions - Unexpected Sublevel found for atrConstraints.",
          v11);
        v8 = a1;
        v22 = (unsigned int)(v22 + 1);
        v11 = a2;
      }
    }
  }
  v25 = 0;
  v26 = v70 + v67;
  v27 = v69 + v8[14];
  v28 = 0;
  v29 = 0;
  v62 = 0;
LABEL_26:
  if ( (unsigned int)v29 < v20 )
  {
    v30 = &v68[v29];
    if ( !*v30 )
      goto LABEL_28;
    v31 = *(_DWORD *)(v27 + 140);
    if ( v31 == 0x7FFFFFFF )
      goto LABEL_28;
    if ( v31 < 0 )
    {
      WriteDbgTraceErrorGpd(
        (__int64)"DwFindNodeInCurLevel",
        "Internal error.  DwFindNodeInCurLevel - Unexpected branchless node found.",
        v11,
        v25);
      v25 = v62;
      goto LABEL_32;
    }
    v11 = v8[18];
    while ( 1 )
    {
      v41 = 20LL * (unsigned int)v31;
      if ( *(_DWORD *)(v41 + v11 + 4) == (_DWORD)v29 )
        break;
      v31 = *(_DWORD *)(v41 + v11 + 8);
      if ( v31 == -1 )
      {
        v29 = (unsigned int)(v29 + 1);
        goto LABEL_26;
      }
    }
    if ( *(_DWORD *)(v41 + v11 + 16) != 1 )
    {
      WriteDbgTraceErrorGpd(
        (__int64)"BSelectivelyEnumEnabledOptions",
        "Internal error.  BSelectivelyEnumEnabledOptions - Unexpected Sublevel found for atrInvalidCombos.",
        v11,
        v25);
      v25 = v62;
      goto LABEL_32;
    }
    v50 = *(_DWORD *)(v41 + v11 + 12);
LABEL_81:
    if ( v50 == -1 )
      goto LABEL_82;
    v51 = 1;
    v52 = 0;
    v53 = -1;
    while ( 1 )
    {
      if ( !v52 )
      {
        v54 = v50;
        if ( *(_DWORD *)(v26 + 16LL * v50) == v61 )
        {
          v57 = *(_DWORD *)(v26 + 16LL * v50 + 4);
          if ( v57 == (_DWORD)v29 )
            break;
          v11 = 0xFFFF;
          if ( (_WORD)v57 == 0xFFFF )
            break;
        }
      }
      if ( v51 )
      {
        if ( a4 )
        {
          v54 = v50;
          if ( !*(_DWORD *)(a4 + 4LL * *(unsigned int *)(v26 + 16LL * v50)) )
          {
            v56 = a7;
            v51 = 0;
LABEL_91:
            if ( v52 )
              goto LABEL_92;
            goto LABEL_97;
          }
        }
        v55 = BIsFeaOptionCurSelected(a2, *(_DWORD *)(v26 + 16LL * v50), *(_DWORD *)(v26 + 16LL * v50 + 4));
        v25 = v62;
        if ( !v55 )
        {
          v56 = a7;
          v51 = 0;
          goto LABEL_91;
        }
      }
      else
      {
        v54 = v50;
      }
      v56 = a7;
      if ( a7 )
      {
        v25 = *(unsigned int *)(v26 + 16 * v54 + 4);
        v28 = *(_DWORD *)(v26 + 16 * v54);
        v62 = *(_DWORD *)(v26 + 16 * v54 + 4);
        goto LABEL_95;
      }
LABEL_96:
      if ( !v51 )
        goto LABEL_91;
LABEL_97:
      v50 = *(_DWORD *)(v26 + 16 * v54 + 8);
      if ( v50 == -1 )
      {
        if ( !v51 )
        {
LABEL_92:
          v50 = v53;
          goto LABEL_81;
        }
        *v30 = 0;
        if ( v56 )
        {
          v56[1] = v29;
          v56[2] = v28;
          v56[3] = v25;
          return 1;
        }
LABEL_82:
        v20 = v65;
LABEL_32:
        v8 = a1;
LABEL_28:
        v29 = (unsigned int)(v29 + 1);
        goto LABEL_26;
      }
    }
    v53 = *(_DWORD *)(v26 + 16LL * v50 + 12);
    v52 = 1;
LABEL_95:
    v56 = a7;
    goto LABEL_96;
  }
  if ( !a7 )
  {
    v32 = 0;
    if ( v20 )
    {
      while ( !v68[v32] )
      {
        v32 = (unsigned int)(v32 + 1);
        if ( (unsigned int)v32 >= v20 )
          return 0;
      }
      return v66;
    }
    else
    {
      return 0;
    }
  }
  *a7 = -1;
  return 1;
}

```

## disassembly

```asm
0x180007800  push    rbx
0x180007802  push    rbp
0x180007803  push    rdi
0x180007804  push    r12
0x180007806  push    r15
0x180007808  sub     rsp, 890h
0x18000780f  mov     rax, cs:__security_cookie
0x180007816  xor     rax, rsp
0x180007819  mov     [rsp+8B8h+var_48], rax
0x180007821  mov     r12, [rsp+8B8h+Src]
0x180007829  mov     r11, rcx
0x18000782c  mov     r15, [rsp+8B8h+arg_30]
0x180007834  mov     rbx, r9
0x180007837  mov     edi, [rsp+8B8h+arg_28]
0x18000783e  mov     r10d, r8d
0x180007841  mov     r8, rdx
0x180007844  mov     rax, [r11+70h]
0x180007848  mov     [rsp+8B8h+var_890], rcx
0x18000784d  imul    rcx, r10, 18Ch
0x180007854  mov     [rsp+8B8h+var_898], r10d
0x180007859  mov     [rsp+8B8h+var_888], rdx
0x18000785e  mov     [rsp+8B8h+var_868], r12
0x180007863  mov     [rsp+8B8h+var_878], r15
0x180007868  mov     ebp, [rax+rcx+188h]
0x18000786f  mov     [rsp+8B8h+var_860], rcx
0x180007874  mov     [rsp+8B8h+var_880], ebp
0x180007878  cmp     ebp, 200h
0x18000787e  ja      loc_180007B60
0x180007884  mov     rax, [r11+60h]
0x180007888  mov     eax, [rax+6Ch]
0x18000788b  mov     [rsp+8B8h+var_870], eax
0x18000788f  mov     rax, [r11+48h]
0x180007893  mov     [rsp+8B8h+var_858], rax
0x180007898  test    r15, r15
0x18000789b  jnz     loc_180007B67
0x1800078a1  test    ebp, ebp
0x1800078a3  jnz     loc_180007E1C
0x1800078a9  test    r12, r12
0x1800078ac  jz      loc_180007B60
0x1800078b2  xor     edx, edx
0x1800078b4  mov     [rsp+8B8h+arg_18], rsi
0x1800078bc  mov     [rsp+8B8h+var_87C], edx
0x1800078c0  xor     edi, edi
0x1800078c2  cmp     edi, [r11+78h]
0x1800078c6  jnb     loc_180007965
0x1800078cc  cmp     edi, r10d
0x1800078cf  jz      short loc_18000791E
0x1800078d1  test    rbx, rbx
0x1800078d4  jz      short loc_1800078DC
0x1800078d6  cmp     dword ptr [rbx+rdi*4], 0
0x1800078da  jz      short loc_18000791E
0x1800078dc  mov     eax, edi
0x1800078de  mov     ecx, edi
0x1800078e0  imul    rsi, rax, 18Ch
0x1800078e7  mov     [rsp+8B8h+var_87C], 1
0x1800078ef  mov     eax, ecx
0x1800078f1  lea     rbp, [r8+rax*2]
0x1800078f5  mov     rax, [r11+70h]
0x1800078f9  mov     edx, [rsi+rax+88h]
0x180007900  cmp     edx, 7FFFFFFFh
0x180007906  jnz     short loc_180007922
0x180007908  test    r15, r15
0x18000790b  jnz     loc_180007B3F
0x180007911  movzx   ecx, byte ptr [rbp+1]
0x180007915  mov     r8, [rsp+8B8h+var_888]
0x18000791a  test    ecx, ecx
0x18000791c  jnz     short loc_1800078EF
0x18000791e  inc     edi
0x180007920  jmp     short loc_1800078C2
0x180007922  test    edx, edx
0x180007924  js      loc_180007E2E
0x18000792a  movzx   r9d, byte ptr [rbp+0]
0x18000792f  mov     r8, [r11+90h]
0x180007936  nop     word ptr [rax+rax+00000000h]
0x180007940  mov     eax, edx
0x180007942  lea     rcx, [rax+rax*4]
0x180007946  cmp     [r8+rcx*4+4], r9d
0x18000794b  lea     rcx, ds:0[rcx*4]
0x180007953  jz      loc_180007AB9
0x180007959  mov     edx, [rcx+r8+8]
0x18000795e  cmp     edx, 0FFFFFFFFh
0x180007961  jnz     short loc_180007940
0x180007963  jmp     short loc_180007908
0x180007965  mov     ebp, [rsp+8B8h+var_880]
0x180007969  mov     [rsp+8B8h+var_38], r14
0x180007971  mov     r14, [r11+70h]
0x180007975  add     r14, [rsp+8B8h+var_860]
0x18000797a  xor     esi, esi
0x18000797c  nop     dword ptr [rax+00h]
0x180007980  cmp     esi, ebp
0x180007982  jnb     short loc_1800079A6
0x180007984  cmp     dword ptr [r12+rsi*4], 0
0x180007989  lea     r10, [r12+rsi*4]
0x18000798d  jz      short loc_1800079A2
0x18000798f  mov     edx, [r14+88h]
0x180007996  cmp     edx, 7FFFFFFFh
0x18000799c  jnz     loc_180007A82
0x1800079a2  inc     esi
0x1800079a4  jmp     short loc_180007980
0x1800079a6  mov     r12d, [rsp+8B8h+var_870]
0x1800079ab  xor     r9d, r9d
0x1800079ae  mov     r15, [r11+70h]
0x1800079b2  add     r12, [rsp+8B8h+var_858]
0x1800079b7  add     r15, [rsp+8B8h+var_860]
0x1800079bc  mov     [rsp+8B8h+var_30], r13
0x1800079c4  xor     r13d, r13d
0x1800079c7  xor     edi, edi
0x1800079c9  mov     [rsp+8B8h+var_894], r9d
0x1800079ce  xchg    ax, ax
0x1800079d0  cmp     edi, ebp
0x1800079d2  jnb     short loc_180007A1D
0x1800079d4  mov     rcx, [rsp+8B8h+var_868]
0x1800079d9  cmp     dword ptr [rcx+rdi*4], 0
0x1800079dd  lea     r10, [rcx+rdi*4]
0x1800079e1  jnz     short loc_1800079E7
0x1800079e3  inc     edi
0x1800079e5  jmp     short loc_1800079D0
0x1800079e7  mov     edx, [r15+8Ch]
0x1800079ee  cmp     edx, 7FFFFFFFh
0x1800079f4  jz      short loc_1800079E3
0x1800079f6  test    edx, edx
0x1800079f8  jns     loc_180007BB2
0x1800079fe  lea     rdx, aInternalErrorD_0; "Internal error.  DwFindNodeInCurLevel -"...
0x180007a05  lea     rcx, aDwfindnodeincu; "DwFindNodeInCurLevel"
0x180007a0c  call    WriteDbgTraceErrorGpd
0x180007a11  mov     r9d, [rsp+8B8h+var_894]
0x180007a16  mov     r11, [rsp+8B8h+var_890]
0x180007a1b  jmp     short loc_1800079E3
0x180007a1d  mov     rax, [rsp+8B8h+var_878]
0x180007a22  test    rax, rax
0x180007a25  jnz     loc_180007F07
0x180007a2b  xor     ecx, ecx
0x180007a2d  test    ebp, ebp
0x180007a2f  jz      loc_180007F1C
0x180007a35  mov     rdx, [rsp+8B8h+var_868]
0x180007a3a  cmp     dword ptr [rdx+rcx*4], 0
0x180007a3e  jz      loc_180007F12
0x180007a44  mov     edx, [rsp+8B8h+var_87C]
0x180007a48  mov     eax, edx
0x180007a4a  mov     r13, [rsp+8B8h+var_30]
0x180007a52  mov     r14, [rsp+8B8h+var_38]
0x180007a5a  mov     rsi, [rsp+8B8h+arg_18]
0x180007a62  mov     rcx, [rsp+8B8h+var_48]
0x180007a6a  xor     rcx, rsp; StackCookie
0x180007a6d  call    __security_check_cookie
0x180007a72  add     rsp, 890h
0x180007a79  pop     r15
0x180007a7b  pop     r12
0x180007a7d  pop     rdi
0x180007a7e  pop     rbp
0x180007a7f  pop     rbx
0x180007a80  retn
0x180007a82  test    edx, edx
0x180007a84  js      loc_180007B8E
0x180007a8a  mov     rdi, [r11+90h]
0x180007a91  mov     eax, edx
0x180007a93  lea     rcx, [rax+rax*4]
0x180007a97  lea     rcx, ds:0[rcx*4]
0x180007a9f  cmp     [rcx+rdi+4], esi
0x180007aa3  jz      loc_180007BEA
0x180007aa9  mov     edx, [rcx+rdi+8]
0x180007aad  cmp     edx, 0FFFFFFFFh
0x180007ab0  jnz     short loc_180007A91
0x180007ab2  inc     esi
0x180007ab4  jmp     loc_180007980
0x180007ab9  cmp     edx, 0FFFFFFFFh
0x180007abc  jz      loc_180007908
0x180007ac2  cmp     dword ptr [rcx+r8+10h], 1
0x180007ac8  lea     rax, [rcx+r8]
0x180007acc  jnz     loc_180007E43
0x180007ad2  mov     ecx, [rax+0Ch]
0x180007ad5  mov     rax, [r11+80h]
0x180007adc  mov     edx, [rcx+rax]
0x180007adf  nop
0x180007ae0  mov     eax, edx
0x180007ae2  lea     rcx, [rax+rax*2]
0x180007ae6  mov     rax, [r11+0A0h]
0x180007aed  lea     rcx, ds:0[rcx*4]
0x180007af5  cmp     [rcx+rax+4], r10d
0x180007afa  jz      short loc_180007B10
0x180007afc  mov     rax, [r11+0A0h]
0x180007b03  mov     edx, [rcx+rax]
0x180007b06  cmp     edx, 0FFFFFFFFh
0x180007b09  jnz     short loc_180007AE0
0x180007b0b  jmp     loc_180007908
0x180007b10  mov     eax, [rcx+rax+8]
0x180007b14  cmp     dword ptr [r12+rax*4], 1
0x180007b19  jnz     short loc_180007AFC
0x180007b1b  mov     dword ptr [r12+rax*4], 0
0x180007b23  test    r15, r15
0x180007b26  jz      short loc_180007AFC
0x180007b28  mov     rax, [r11+0A0h]
0x180007b2f  mov     ecx, [rcx+rax+8]
0x180007b33  mov     [r15+4], ecx
0x180007b37  mov     [r15+8], edi
0x180007b3b  mov     [r15+0Ch], r9d
0x180007b3f  cmp     dword ptr [r15+8], 0FFFFFFFFh
0x180007b44  jz      loc_180007911
0x180007b4a  mov     eax, 1
0x180007b4f  jmp     loc_180007A5A
0x180007b54  cmp     edi, 200h
0x180007b5a  jb      loc_180007C91
0x180007b60  xor     eax, eax
0x180007b62  jmp     loc_180007A62
0x180007b67  mov     [r15], r10d
0x180007b6a  mov     dword ptr [r15+8], 0FFFFFFFFh
0x180007b72  test    r12, r12
0x180007b75  jz      short loc_180007B54
0x180007b77  test    ebp, ebp
0x180007b79  jnz     loc_180007DCD
0x180007b7f  lea     r12, [rsp+8B8h+var_848]
0x180007b84  mov     [rsp+8B8h+var_868], r12
0x180007b89  jmp     loc_1800078B2
0x180007b8e  lea     rdx, aInternalErrorD_0; "Internal error.  DwFindNodeInCurLevel -"...
0x180007b95  lea     rcx, aDwfindnodeincu; "DwFindNodeInCurLevel"
0x180007b9c  call    WriteDbgTraceErrorGpd
0x180007ba1  mov     r11, [rsp+8B8h+var_890]
0x180007ba6  inc     esi
0x180007ba8  mov     r8, [rsp+8B8h+var_888]
0x180007bad  jmp     loc_180007980
0x180007bb2  mov     r8, [r11+90h]
0x180007bb9  nop     dword ptr [rax+00000000h]
0x180007bc0  mov     eax, edx
0x180007bc2  lea     rcx, [rax+rax*4]
0x180007bc6  lea     rcx, ds:0[rcx*4]
0x180007bce  cmp     [rcx+r8+4], edi
0x180007bd3  jz      loc_180007CCA
0x180007bd9  mov     edx, [rcx+r8+8]
0x180007bde  cmp     edx, 0FFFFFFFFh
0x180007be1  jnz     short loc_180007BC0
0x180007be3  inc     edi
0x180007be5  jmp     loc_1800079D0
0x180007bea  cmp     edx, 0FFFFFFFFh
0x180007bed  jz      loc_1800079A2
0x180007bf3  cmp     dword ptr [rcx+rdi+10h], 1
0x180007bf8  lea     rax, [rcx+rdi]
0x180007bfc  jnz     loc_180007CA6
0x180007c02  mov     ecx, [rax+0Ch]
0x180007c05  mov     rax, [r11+80h]
0x180007c0c  mov     r9, [r11+0A0h]
0x180007c13  mov     edx, [rcx+rax]
0x180007c16  nop     word ptr [rax+rax+00000000h]
0x180007c20  mov     eax, edx
0x180007c22  lea     rcx, [rax+rax*2]
0x180007c26  lea     rdx, ds:0[rcx*4]
0x180007c2e  test    rbx, rbx
0x180007c31  jz      short loc_180007C50
0x180007c33  mov     ecx, [r9+rdx+4]
0x180007c38  lea     rax, [r9+rdx]
0x180007c3c  cmp     dword ptr [rbx+rcx*4], 0
0x180007c40  jnz     short loc_180007C50
0x180007c42  mov     edx, [rax]
0x180007c44  cmp     edx, 0FFFFFFFFh
0x180007c47  jnz     short loc_180007C20
0x180007c49  inc     esi
0x180007c4b  jmp     loc_180007980
0x180007c50  mov     edi, [rdx+r9+8]
0x180007c55  lea     rax, [rdx+r9]
0x180007c59  mov     edx, [rdx+r9+4]
0x180007c5e  movzx   ecx, byte ptr [r8+rdx*2]
0x180007c63  cmp     ecx, edi
0x180007c65  jz      loc_180007E72
0x180007c6b  movzx   ecx, byte ptr [r8+rdx*2+1]
0x180007c71  test    ecx, ecx
0x180007c73  jz      short loc_180007C42
0x180007c75  lea     r8, [r8+rcx*2]
0x180007c79  movzx   ecx, byte ptr [r8]
0x180007c7d  cmp     ecx, edi
0x180007c7f  jz      loc_180007E6D
0x180007c85  movzx   ecx, byte ptr [r8+1]
0x180007c8a  mov     r8, [rsp+8B8h+var_888]
0x180007c8f  jmp     short loc_180007C71
0x180007c91  test    ebp, ebp
0x180007c93  jnz     loc_180007DF5
0x180007c99  mov     [rsp+rdi*4+8B8h+var_848], 1
0x180007ca1  jmp     loc_180007B7F
0x180007ca6  lea     rdx, aInternalErrorB_5; "Internal error.  BSelectivelyEnumEnable"...
0x180007cad  lea     rcx, aBselectivelyen; "BSelectivelyEnumEnabledOptions"
0x180007cb4  call    WriteDbgTraceErrorGpd
0x180007cb9  mov     r11, [rsp+8B8h+var_890]
0x180007cbe  inc     esi
0x180007cc0  mov     r8, [rsp+8B8h+var_888]
0x180007cc5  jmp     loc_180007980
0x180007cca  cmp     edx, 0FFFFFFFFh
0x180007ccd  jz      loc_1800079E3
0x180007cd3  cmp     dword ptr [rcx+r8+10h], 1
0x180007cd9  jnz     loc_180007E9F
0x180007cdf  mov     ecx, [rcx+r8+0Ch]
0x180007ce4  cmp     ecx, 0FFFFFFFFh
0x180007ce7  jnz     short loc_180007CF2
0x180007ce9  mov     ebp, [rsp+8B8h+var_880]
0x180007ced  jmp     loc_180007A16
0x180007cf2  mov     esi, 1
0x180007cf7  xor     ebp, ebp
0x180007cf9  mov     r14d, 0FFFFFFFFh
0x180007cff  test    ebp, ebp
0x180007d01  jnz     short loc_180007D15
0x180007d03  mov     edx, [rsp+8B8h+var_898]
0x180007d07  mov     eax, ecx
0x180007d09  add     rax, rax
  ... truncated ...
```
