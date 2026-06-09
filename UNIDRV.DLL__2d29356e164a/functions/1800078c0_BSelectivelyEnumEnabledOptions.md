# BSelectivelyEnumEnabledOptions

- ea: `0x1800078c0`
- end: `0x180007fe3`
- name: `BSelectivelyEnumEnabledOptions`
- size: `1827`
- prototype: `__int64 __fastcall(int, int, int, int, void *Src, int, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800073f0`
- `0x18004ef38`
- `0x18004fa54`

## callees

- `0x180007220`
- `0x1800078c0`
- `0x18003b60c`
- `0x1800487e0`
- `0x1800491dc`
- `0x180074580`

## string_xrefs

- `0x180007f5f`: `Internal error.  BSelectivelyEnumEnabledOptions - Unexpected Sublevel found for atrInvalidCombos.`

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
            "BEnumImposedConstraintsOnFeature",
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
        "DwFindNodeInCurLevel",
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
        "DwFindNodeInCurLevel",
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
          "BSelectivelyEnumEnabledOptions",
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
        "DwFindNodeInCurLevel",
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
        "BSelectivelyEnumEnabledOptions",
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
        v55 = BIsFeaOptionCurSelected(
                a2,
                *(unsigned int *)(v26 + 16LL * v50),
                *(unsigned int *)(v26 + 16LL * v50 + 4),
                v25);
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
0x1800078c0  push    rbx
0x1800078c2  push    rbp
0x1800078c3  push    rdi
0x1800078c4  push    r12
0x1800078c6  push    r15
0x1800078c8  sub     rsp, 890h
0x1800078cf  mov     rax, cs:__security_cookie
0x1800078d6  xor     rax, rsp
0x1800078d9  mov     [rsp+8B8h+var_48], rax
0x1800078e1  mov     r12, [rsp+8B8h+Src]
0x1800078e9  mov     r11, rcx
0x1800078ec  mov     r15, [rsp+8B8h+arg_30]
0x1800078f4  mov     rbx, r9
0x1800078f7  mov     edi, [rsp+8B8h+arg_28]
0x1800078fe  mov     r10d, r8d
0x180007901  mov     r8, rdx
0x180007904  mov     rax, [r11+70h]
0x180007908  mov     [rsp+8B8h+var_890], rcx
0x18000790d  imul    rcx, r10, 18Ch
0x180007914  mov     [rsp+8B8h+var_898], r10d
0x180007919  mov     [rsp+8B8h+var_888], rdx
0x18000791e  mov     [rsp+8B8h+var_868], r12
0x180007923  mov     [rsp+8B8h+var_878], r15
0x180007928  mov     ebp, [rax+rcx+188h]
0x18000792f  mov     [rsp+8B8h+var_860], rcx
0x180007934  mov     [rsp+8B8h+var_880], ebp
0x180007938  cmp     ebp, 200h
0x18000793e  ja      loc_180007C20
0x180007944  mov     rax, [r11+60h]
0x180007948  mov     eax, [rax+6Ch]
0x18000794b  mov     [rsp+8B8h+var_870], eax
0x18000794f  mov     rax, [r11+48h]
0x180007953  mov     [rsp+8B8h+var_858], rax
0x180007958  test    r15, r15
0x18000795b  jnz     loc_180007C27
0x180007961  test    ebp, ebp
0x180007963  jnz     loc_180007EDC
0x180007969  test    r12, r12
0x18000796c  jz      loc_180007C20
0x180007972  xor     edx, edx
0x180007974  mov     [rsp+8B8h+arg_18], rsi
0x18000797c  mov     [rsp+8B8h+var_87C], edx
0x180007980  xor     edi, edi
0x180007982  cmp     edi, [r11+78h]
0x180007986  jnb     loc_180007A25
0x18000798c  cmp     edi, r10d
0x18000798f  jz      short loc_1800079DE
0x180007991  test    rbx, rbx
0x180007994  jz      short loc_18000799C
0x180007996  cmp     dword ptr [rbx+rdi*4], 0
0x18000799a  jz      short loc_1800079DE
0x18000799c  mov     eax, edi
0x18000799e  mov     ecx, edi
0x1800079a0  imul    rsi, rax, 18Ch
0x1800079a7  mov     [rsp+8B8h+var_87C], 1
0x1800079af  mov     eax, ecx
0x1800079b1  lea     rbp, [r8+rax*2]
0x1800079b5  mov     rax, [r11+70h]
0x1800079b9  mov     edx, [rsi+rax+88h]
0x1800079c0  cmp     edx, 7FFFFFFFh
0x1800079c6  jnz     short loc_1800079E2
0x1800079c8  test    r15, r15
0x1800079cb  jnz     loc_180007BFF
0x1800079d1  movzx   ecx, byte ptr [rbp+1]
0x1800079d5  mov     r8, [rsp+8B8h+var_888]
0x1800079da  test    ecx, ecx
0x1800079dc  jnz     short loc_1800079AF
0x1800079de  inc     edi
0x1800079e0  jmp     short loc_180007982
0x1800079e2  test    edx, edx
0x1800079e4  js      loc_180007EEE
0x1800079ea  movzx   r9d, byte ptr [rbp+0]
0x1800079ef  mov     r8, [r11+90h]
0x1800079f6  nop     word ptr [rax+rax+00000000h]
0x180007a00  mov     eax, edx
0x180007a02  lea     rcx, [rax+rax*4]
0x180007a06  cmp     [r8+rcx*4+4], r9d
0x180007a0b  lea     rcx, ds:0[rcx*4]
0x180007a13  jz      loc_180007B78
0x180007a19  mov     edx, [rcx+r8+8]
0x180007a1e  cmp     edx, 0FFFFFFFFh
0x180007a21  jnz     short loc_180007A00
0x180007a23  jmp     short loc_1800079C8
0x180007a25  mov     ebp, [rsp+8B8h+var_880]
0x180007a29  mov     [rsp+8B8h+var_38], r14
0x180007a31  mov     r14, [r11+70h]
0x180007a35  add     r14, [rsp+8B8h+var_860]
0x180007a3a  xor     esi, esi
0x180007a3c  nop     dword ptr [rax+00h]
0x180007a40  cmp     esi, ebp
0x180007a42  jnb     short loc_180007A66
0x180007a44  cmp     dword ptr [r12+rsi*4], 0
0x180007a49  lea     r10, [r12+rsi*4]
0x180007a4d  jz      short loc_180007A62
0x180007a4f  mov     edx, [r14+88h]
0x180007a56  cmp     edx, 7FFFFFFFh
0x180007a5c  jnz     loc_180007B41
0x180007a62  inc     esi
0x180007a64  jmp     short loc_180007A40
0x180007a66  mov     r12d, [rsp+8B8h+var_870]
0x180007a6b  xor     r9d, r9d
0x180007a6e  mov     r15, [r11+70h]
0x180007a72  add     r12, [rsp+8B8h+var_858]
0x180007a77  add     r15, [rsp+8B8h+var_860]
0x180007a7c  mov     [rsp+8B8h+var_30], r13
0x180007a84  xor     r13d, r13d
0x180007a87  xor     edi, edi
0x180007a89  mov     [rsp+8B8h+var_894], r9d
0x180007a8e  xchg    ax, ax
0x180007a90  cmp     edi, ebp
0x180007a92  jnb     short loc_180007ADD
0x180007a94  mov     rcx, [rsp+8B8h+var_868]
0x180007a99  cmp     dword ptr [rcx+rdi*4], 0
0x180007a9d  lea     r10, [rcx+rdi*4]
0x180007aa1  jnz     short loc_180007AA7
0x180007aa3  inc     edi
0x180007aa5  jmp     short loc_180007A90
0x180007aa7  mov     edx, [r15+8Ch]
0x180007aae  cmp     edx, 7FFFFFFFh
0x180007ab4  jz      short loc_180007AA3
0x180007ab6  test    edx, edx
0x180007ab8  jns     loc_180007C72
0x180007abe  lea     rdx, aInternalErrorD_0; "Internal error.  DwFindNodeInCurLevel -"...
0x180007ac5  lea     rcx, aDwfindnodeincu; "DwFindNodeInCurLevel"
0x180007acc  call    WriteDbgTraceErrorGpd
0x180007ad1  mov     r9d, [rsp+8B8h+var_894]
0x180007ad6  mov     r11, [rsp+8B8h+var_890]
0x180007adb  jmp     short loc_180007AA3
0x180007add  mov     rax, [rsp+8B8h+var_878]
0x180007ae2  test    rax, rax
0x180007ae5  jnz     loc_180007FC7
0x180007aeb  xor     ecx, ecx
0x180007aed  test    ebp, ebp
0x180007aef  jz      loc_180007FDC
0x180007af5  mov     rdx, [rsp+8B8h+var_868]
0x180007afa  cmp     dword ptr [rdx+rcx*4], 0
0x180007afe  jz      loc_180007FD2
0x180007b04  mov     edx, [rsp+8B8h+var_87C]
0x180007b08  mov     eax, edx
0x180007b0a  mov     r13, [rsp+8B8h+var_30]
0x180007b12  mov     r14, [rsp+8B8h+var_38]
0x180007b1a  mov     rsi, [rsp+8B8h+arg_18]
0x180007b22  mov     rcx, [rsp+8B8h+var_48]
0x180007b2a  xor     rcx, rsp; StackCookie
0x180007b2d  call    __security_check_cookie
0x180007b32  add     rsp, 890h
0x180007b39  pop     r15
0x180007b3b  pop     r12
0x180007b3d  pop     rdi
0x180007b3e  pop     rbp
0x180007b3f  pop     rbx
0x180007b40  retn
0x180007b41  test    edx, edx
0x180007b43  js      loc_180007C4E
0x180007b49  mov     rdi, [r11+90h]
0x180007b50  mov     eax, edx
0x180007b52  lea     rcx, [rax+rax*4]
0x180007b56  lea     rcx, ds:0[rcx*4]
0x180007b5e  cmp     [rcx+rdi+4], esi
0x180007b62  jz      loc_180007CAA
0x180007b68  mov     edx, [rcx+rdi+8]
0x180007b6c  cmp     edx, 0FFFFFFFFh
0x180007b6f  jnz     short loc_180007B50
0x180007b71  inc     esi
0x180007b73  jmp     loc_180007A40
0x180007b78  cmp     edx, 0FFFFFFFFh
0x180007b7b  jz      loc_1800079C8
0x180007b81  cmp     dword ptr [rcx+r8+10h], 1
0x180007b87  lea     rax, [rcx+r8]
0x180007b8b  jnz     loc_180007F03
0x180007b91  mov     ecx, [rax+0Ch]
0x180007b94  mov     rax, [r11+80h]
0x180007b9b  mov     edx, [rcx+rax]
0x180007b9e  xchg    ax, ax
0x180007ba0  mov     eax, edx
0x180007ba2  lea     rcx, [rax+rax*2]
0x180007ba6  mov     rax, [r11+0A0h]
0x180007bad  lea     rcx, ds:0[rcx*4]
0x180007bb5  cmp     [rcx+rax+4], r10d
0x180007bba  jz      short loc_180007BD0
0x180007bbc  mov     rax, [r11+0A0h]
0x180007bc3  mov     edx, [rcx+rax]
0x180007bc6  cmp     edx, 0FFFFFFFFh
0x180007bc9  jnz     short loc_180007BA0
0x180007bcb  jmp     loc_1800079C8
0x180007bd0  mov     eax, [rcx+rax+8]
0x180007bd4  cmp     dword ptr [r12+rax*4], 1
0x180007bd9  jnz     short loc_180007BBC
0x180007bdb  mov     dword ptr [r12+rax*4], 0
0x180007be3  test    r15, r15
0x180007be6  jz      short loc_180007BBC
0x180007be8  mov     rax, [r11+0A0h]
0x180007bef  mov     ecx, [rcx+rax+8]
0x180007bf3  mov     [r15+4], ecx
0x180007bf7  mov     [r15+8], edi
0x180007bfb  mov     [r15+0Ch], r9d
0x180007bff  cmp     dword ptr [r15+8], 0FFFFFFFFh
0x180007c04  jz      loc_1800079D1
0x180007c0a  mov     eax, 1
0x180007c0f  jmp     loc_180007B1A
0x180007c14  cmp     edi, 200h
0x180007c1a  jb      loc_180007D51
0x180007c20  xor     eax, eax
0x180007c22  jmp     loc_180007B22
0x180007c27  mov     [r15], r10d
0x180007c2a  mov     dword ptr [r15+8], 0FFFFFFFFh
0x180007c32  test    r12, r12
0x180007c35  jz      short loc_180007C14
0x180007c37  test    ebp, ebp
0x180007c39  jnz     loc_180007E8D
0x180007c3f  lea     r12, [rsp+8B8h+var_848]
0x180007c44  mov     [rsp+8B8h+var_868], r12
0x180007c49  jmp     loc_180007972
0x180007c4e  lea     rdx, aInternalErrorD_0; "Internal error.  DwFindNodeInCurLevel -"...
0x180007c55  lea     rcx, aDwfindnodeincu; "DwFindNodeInCurLevel"
0x180007c5c  call    WriteDbgTraceErrorGpd
0x180007c61  mov     r11, [rsp+8B8h+var_890]
0x180007c66  inc     esi
0x180007c68  mov     r8, [rsp+8B8h+var_888]
0x180007c6d  jmp     loc_180007A40
0x180007c72  mov     r8, [r11+90h]
0x180007c79  nop     dword ptr [rax+00000000h]
0x180007c80  mov     eax, edx
0x180007c82  lea     rcx, [rax+rax*4]
0x180007c86  lea     rcx, ds:0[rcx*4]
0x180007c8e  cmp     [rcx+r8+4], edi
0x180007c93  jz      loc_180007D8A
0x180007c99  mov     edx, [rcx+r8+8]
0x180007c9e  cmp     edx, 0FFFFFFFFh
0x180007ca1  jnz     short loc_180007C80
0x180007ca3  inc     edi
0x180007ca5  jmp     loc_180007A90
0x180007caa  cmp     edx, 0FFFFFFFFh
0x180007cad  jz      loc_180007A62
0x180007cb3  cmp     dword ptr [rcx+rdi+10h], 1
0x180007cb8  lea     rax, [rcx+rdi]
0x180007cbc  jnz     loc_180007D66
0x180007cc2  mov     ecx, [rax+0Ch]
0x180007cc5  mov     rax, [r11+80h]
0x180007ccc  mov     r9, [r11+0A0h]
0x180007cd3  mov     edx, [rcx+rax]
0x180007cd6  nop     word ptr [rax+rax+00000000h]
0x180007ce0  mov     eax, edx
0x180007ce2  lea     rcx, [rax+rax*2]
0x180007ce6  lea     rdx, ds:0[rcx*4]
0x180007cee  test    rbx, rbx
0x180007cf1  jz      short loc_180007D10
0x180007cf3  mov     ecx, [r9+rdx+4]
0x180007cf8  lea     rax, [r9+rdx]
0x180007cfc  cmp     dword ptr [rbx+rcx*4], 0
0x180007d00  jnz     short loc_180007D10
0x180007d02  mov     edx, [rax]
0x180007d04  cmp     edx, 0FFFFFFFFh
0x180007d07  jnz     short loc_180007CE0
0x180007d09  inc     esi
0x180007d0b  jmp     loc_180007A40
0x180007d10  mov     edi, [rdx+r9+8]
0x180007d15  lea     rax, [rdx+r9]
0x180007d19  mov     edx, [rdx+r9+4]
0x180007d1e  movzx   ecx, byte ptr [r8+rdx*2]
0x180007d23  cmp     ecx, edi
0x180007d25  jz      loc_180007F32
0x180007d2b  movzx   ecx, byte ptr [r8+rdx*2+1]
0x180007d31  test    ecx, ecx
0x180007d33  jz      short loc_180007D02
0x180007d35  lea     r8, [r8+rcx*2]
0x180007d39  movzx   ecx, byte ptr [r8]
0x180007d3d  cmp     ecx, edi
0x180007d3f  jz      loc_180007F2D
0x180007d45  movzx   ecx, byte ptr [r8+1]
0x180007d4a  mov     r8, [rsp+8B8h+var_888]
0x180007d4f  jmp     short loc_180007D31
0x180007d51  test    ebp, ebp
0x180007d53  jnz     loc_180007EB5
0x180007d59  mov     [rsp+rdi*4+8B8h+var_848], 1
0x180007d61  jmp     loc_180007C3F
0x180007d66  lea     rdx, aInternalErrorB_5; "Internal error.  BSelectivelyEnumEnable"...
0x180007d6d  lea     rcx, aBselectivelyen; "BSelectivelyEnumEnabledOptions"
0x180007d74  call    WriteDbgTraceErrorGpd
0x180007d79  mov     r11, [rsp+8B8h+var_890]
0x180007d7e  inc     esi
0x180007d80  mov     r8, [rsp+8B8h+var_888]
0x180007d85  jmp     loc_180007A40
0x180007d8a  cmp     edx, 0FFFFFFFFh
0x180007d8d  jz      loc_180007AA3
0x180007d93  cmp     dword ptr [rcx+r8+10h], 1
0x180007d99  jnz     loc_180007F5F
0x180007d9f  mov     ecx, [rcx+r8+0Ch]
0x180007da4  cmp     ecx, 0FFFFFFFFh
0x180007da7  jnz     short loc_180007DB2
0x180007da9  mov     ebp, [rsp+8B8h+var_880]
0x180007dad  jmp     loc_180007AD6
0x180007db2  mov     esi, 1
0x180007db7  xor     ebp, ebp
0x180007db9  mov     r14d, 0FFFFFFFFh
0x180007dbf  test    ebp, ebp
0x180007dc1  jnz     short loc_180007DD5
0x180007dc3  mov     edx, [rsp+8B8h+var_898]
0x180007dc7  mov     eax, ecx
0x180007dc9  add     rax, rax
  ... truncated ...
```
