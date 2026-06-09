# BfpMappingInsertExceptions

- ea: `0x14001b280`
- end: `0x14001ba06`
- name: `BfpMappingInsertExceptions`
- size: `1926`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019c44`

## callees

- `0x140001348`
- `0x140003304`
- `0x140017bb8`
- `0x140019b40`
- `0x14001b280`
- `0x14001ba10`
- `0x14001cd84`
- `0x14001d2c0`
- `0x140020180`

## import_xrefs

- `ntoskrnl!RtlRbInsertNodeEx` at `0x14001b5c5`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14001b6d5`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14001b5c5`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14001b6d5`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b5df`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b600`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b5df`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001b600`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b736`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b9f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b736`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b9f5`

## pseudocode

```c
__int64 __fastcall BfpMappingInsertExceptions(_QWORD *a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5)
{
  __int64 v5; // r8
  __int64 v6; // r15
  _QWORD *v7; // r14
  int PathTree; // ebx
  unsigned __int16 v9; // dx
  unsigned __int16 v10; // di
  unsigned __int16 v11; // si
  unsigned __int16 v12; // ax
  unsigned int v13; // eax
  __int64 v14; // r13
  __int64 v15; // r12
  int v16; // edx
  __int64 v17; // rdx
  unsigned __int16 v18; // r9
  __int64 v19; // rcx
  unsigned __int16 v20; // dx
  __int16 v21; // cx
  char v22; // r14
  __int64 v23; // rsi
  __int64 v24; // rbx
  int v25; // edi
  int v26; // eax
  int v27; // edx
  __int64 v28; // rax
  __int64 *v29; // rdi
  int v30; // r15d
  __int64 v31; // r8
  __int64 v32; // r13
  __int64 v33; // rdi
  int v34; // r14d
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // r8
  __int64 v38; // r15
  __int64 v39; // rdi
  int v40; // r14d
  __int64 v41; // rax
  int v43; // r9d
  int v44; // r9d
  __int64 v45; // [rsp+30h] [rbp-A9h]
  char v46; // [rsp+38h] [rbp-A1h]
  char v47; // [rsp+38h] [rbp-A1h]
  __int64 v48; // [rsp+40h] [rbp-99h]
  char v49; // [rsp+58h] [rbp-81h]
  unsigned int v50; // [rsp+5Ch] [rbp-7Dh]
  unsigned __int16 v51; // [rsp+60h] [rbp-79h]
  unsigned __int16 v52; // [rsp+64h] [rbp-75h]
  PVOID P; // [rsp+68h] [rbp-71h] BYREF
  __int64 v54[2]; // [rsp+70h] [rbp-69h] BYREF
  UNICODE_STRING String2; // [rsp+80h] [rbp-59h] BYREF
  __int128 v56; // [rsp+90h] [rbp-49h] BYREF
  __int128 v57; // [rsp+A0h] [rbp-39h] BYREF
  UNICODE_STRING String1; // [rsp+B0h] [rbp-29h] BYREF
  __int128 v59; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v60; // [rsp+D0h] [rbp-9h] BYREF
  __int64 v61; // [rsp+D8h] [rbp-1h]
  unsigned int v65; // [rsp+150h] [rbp+77h]

  v65 = a4;
  v5 = *a1;
  P = 0;
  v60 = 0;
  v6 = a2;
  v51 = 0;
  String2 = 0;
  v7 = a1;
  PathTree = 0;
  String1 = 0;
  v9 = *(_WORD *)(v5 + 4) >> 1;
  v10 = 0;
  v52 = 0;
  v11 = 0;
  v57 = 0;
  v59 = 0;
  if ( v9 )
  {
    do
    {
      v12 = v10 + 1;
      if ( *(_WORD *)(v5 + 2LL * v11 + 6) != 92 )
        v12 = v10;
      ++v11;
      v10 = v12;
    }
    while ( v11 < v9 );
    v52 = v11;
    v51 = v12;
  }
  v13 = 0;
LABEL_7:
  v50 = v13;
  if ( v13 >= a4 )
    return (unsigned int)PathTree;
  v14 = a5;
  v15 = v13;
  v61 = v13;
  PathTree = BfConvertContainerRootIdToShortNames(*(_QWORD *)(a5 + 8LL * v13), &P);
  if ( PathTree < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(v48) = PathTree;
      v43 = 55;
      v46 = 125;
      goto LABEL_82;
    }
    goto LABEL_69;
  }
  v17 = *(_QWORD *)(a5 + 8 * v15);
  v18 = *((_WORD *)P + 2);
  LOWORD(v57) = *(_WORD *)(v17 + 4) - *(_WORD *)(*v7 + 4LL);
  WORD1(v57) = v57;
  v19 = v17 + 2 * (v11 + 3LL);
  v20 = 0;
  *((_QWORD *)&v57 + 1) = v19;
  v21 = 0;
  if ( v18 >> 1 )
  {
    do
    {
      if ( *((_WORD *)P + v20 + 3) == 92 && (unsigned __int16)++v21 > v10 )
        break;
      ++v20;
    }
    while ( v20 < (unsigned __int16)(v18 >> 1) );
    v15 = v61;
  }
  LOWORD(v59) = v18 - 2 * v20;
  WORD1(v59) = v59;
  *((_QWORD *)&v59 + 1) = (char *)P + 2 * v20 + 6;
  v49 = BfpWalkPath(&v57, 0, &String2);
  v22 = v49;
  BfpWalkPath(&v59, 0, &String1);
  v23 = *(_QWORD *)(v6 + 80);
  while ( 1 )
  {
    v24 = *(_QWORD *)v23;
    v54[0] = (__int64)&String2;
    v54[1] = 0;
    if ( (*(_BYTE *)(v23 + 8) & 1) != 0 )
    {
      if ( v24 )
        v24 ^= v23;
      else
        v24 = 0;
    }
    v25 = *(_BYTE *)(v23 + 8) & 1;
    if ( !v24 )
      goto LABEL_32;
    do
    {
      v26 = BfpRBComparePathNodes((__int64)v54, v24);
      if ( v26 < 0 )
      {
        v28 = *(_QWORD *)v24;
      }
      else
      {
        if ( v26 <= 0 )
          break;
        v28 = *(_QWORD *)(v24 + 8);
      }
      if ( v25 && v28 )
        v24 ^= v28;
      else
        v24 = v28;
    }
    while ( v24 );
    v14 = a5;
    if ( !v24 )
      goto LABEL_32;
    if ( (*(_DWORD *)(v24 - 8) & 2) != 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v44 = 56;
        v47 = -56;
        goto LABEL_105;
      }
      goto LABEL_68;
    }
    if ( !v22 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v44 = 57;
        v47 = -42;
        goto LABEL_105;
      }
LABEL_68:
      PathTree = -1073741811;
      goto LABEL_69;
    }
    v49 = BfpWalkPath(&v57, 0, &String2);
    v22 = v49;
    BfpWalkPath(&v59, 0, &String1);
    v29 = (__int64 *)(v24 + 72);
    v23 = *(_QWORD *)(v24 + 72);
    if ( (unsigned __int8)BfpPathTreeEmpty(v23) )
      break;
    v54[0] = 0;
  }
  if ( (*(_DWORD *)(v24 - 8) & 1) == 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v44 = 58;
      v47 = -7;
LABEL_105:
      LOBYTE(v27) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v27,
        8,
        v44,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        v47);
      goto LABEL_68;
    }
    goto LABEL_68;
  }
  if ( v23 || (PathTree = BfpCreatePathTree(v29), PathTree >= 0) )
  {
    v23 = *v29;
LABEL_32:
    v54[0] = 0;
    while ( 1 )
    {
      v30 = v22 == 0 ? 4 : 0;
      v45 = *(_QWORD *)(v14 + 8 * v15);
      v56 = 0;
      PathTree = BfpCreatePathTierNode(&String2, v30, v22, 0, a3, v45, 0, 0, v54);
      if ( PathTree < 0 )
        break;
      v32 = v54[0];
      v33 = *(_QWORD *)v23;
      BYTE8(v56) = 0;
      *(_QWORD *)&v56 = v54[0] + 32;
      if ( (*(_BYTE *)(v23 + 8) & 1) != 0 )
      {
        if ( v33 )
          v33 ^= v23;
        else
          v33 = 0;
      }
      LOBYTE(v31) = 0;
      v34 = *(_BYTE *)(v23 + 8) & 1;
      if ( v33 )
      {
        while ( 1 )
        {
          if ( (int)BfpRBComparePathNodes((__int64)&v56, v33) < 0 )
          {
            v35 = *(_QWORD *)v33;
            if ( v34 )
            {
              if ( !v35 )
              {
LABEL_60:
                LOBYTE(v31) = 0;
                break;
              }
              v35 ^= v33;
            }
            if ( !v35 )
              goto LABEL_60;
          }
          else
          {
            v35 = *(_QWORD *)(v33 + 8);
            if ( v34 )
            {
              if ( !v35 )
              {
LABEL_40:
                LOBYTE(v31) = 1;
                break;
              }
              v35 ^= v33;
            }
            if ( !v35 )
              goto LABEL_40;
          }
          v33 = v35;
        }
      }
      RtlRbInsertNodeEx(v23, v33, v31, v32 + 8);
      if ( RtlCompareUnicodeString(&String1, &g_NoShortComponent, 0) && RtlCompareUnicodeString(&String1, &String2, 0) )
      {
        v56 = 0;
        if ( v49 )
          v36 = *(_QWORD *)(v32 + 80);
        else
          v36 = 0;
        PathTree = BfpCreatePathTierNode(&String1, v30 | 2u, v49, 0, 0, 0, 0, v36, &v60);
        if ( PathTree < 0 )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_69;
          LODWORD(v48) = PathTree;
          v43 = 61;
          v46 = 117;
          goto LABEL_82;
        }
        v38 = v60;
        v39 = *(_QWORD *)v23;
        BYTE8(v56) = 0;
        *(_QWORD *)&v56 = v60 + 32;
        if ( (*(_BYTE *)(v23 + 8) & 1) != 0 )
        {
          if ( v39 )
            v39 ^= v23;
          else
            v39 = 0;
        }
        LOBYTE(v37) = 0;
        v40 = *(_BYTE *)(v23 + 8) & 1;
        if ( v39 )
        {
          while ( 1 )
          {
            if ( (int)BfpRBComparePathNodes((__int64)&v56, v39) < 0 )
            {
              v41 = *(_QWORD *)v39;
              if ( v40 )
              {
                if ( !v41 )
                {
LABEL_64:
                  LOBYTE(v37) = 0;
                  break;
                }
                v41 ^= v39;
              }
              if ( !v41 )
                goto LABEL_64;
            }
            else
            {
              v41 = *(_QWORD *)(v39 + 8);
              if ( v40 )
              {
                if ( !v41 )
                {
LABEL_52:
                  LOBYTE(v37) = 1;
                  break;
                }
                v41 ^= v39;
              }
              if ( !v41 )
                goto LABEL_52;
            }
            v39 = v41;
          }
        }
        RtlRbInsertNodeEx(v23, v39, v37, v38 + 8);
        *(_QWORD *)(v32 + 88) = v38;
      }
      if ( v49 )
        v23 = *(_QWORD *)(v32 + 80);
      v49 = BfpWalkPath(&v57, 0, &String2);
      v22 = v49;
      BfpWalkPath(&v59, 0, &String1);
      v15 = v61;
      v14 = a5;
      if ( !String2.Length )
      {
        ExFreePoolWithTag(P, 0x706D4642u);
        v11 = v52;
        v13 = v50 + 1;
        a4 = v65;
        v7 = a1;
        v6 = a2;
        P = 0;
        v10 = v51;
        goto LABEL_7;
      }
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_69;
    LODWORD(v48) = PathTree;
    v43 = 60;
    v46 = 67;
LABEL_82:
    LOBYTE(v16) = 2;
    WPP_RECORDER_SF_sDd(
      WPP_GLOBAL_Control->DeviceExtension,
      v16,
      8,
      v43,
      (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
      (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
      v46,
      v48);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v48) = PathTree;
    v43 = 59;
    v46 = 10;
    goto LABEL_82;
  }
LABEL_69:
  if ( P )
    ExFreePoolWithTag(P, 0x706D4642u);
  return (unsigned int)PathTree;
}

```

## disassembly

```asm
0x14001b280  mov     rax, rsp
0x14001b283  mov     [rax+20h], r9d
0x14001b287  mov     [rax+18h], r8
0x14001b28b  mov     [rax+10h], rdx
0x14001b28f  mov     [rax+8], rcx
0x14001b293  push    rbp
0x14001b294  push    rbx
0x14001b295  push    rsi
0x14001b296  push    rdi
0x14001b297  push    r12
0x14001b299  push    r13
0x14001b29b  push    r14
0x14001b29d  push    r15
0x14001b29f  lea     rbp, [rax-57h]
0x14001b2a3  sub     rsp, 0E8h
0x14001b2aa  mov     r8, [rcx]
0x14001b2ad  xor     r10d, r10d
0x14001b2b0  xorps   xmm0, xmm0
0x14001b2b3  mov     [rbp+4Fh+P], r10
0x14001b2b7  xorps   xmm1, xmm1
0x14001b2ba  mov     [rbp+4Fh+var_58], r10
0x14001b2be  mov     r15, rdx
0x14001b2c1  mov     [rbp+4Fh+var_C8], r10d
0x14001b2c5  movups  xmmword ptr [rbp+4Fh+String2.Length], xmm0
0x14001b2c9  mov     r14, rcx
0x14001b2cc  mov     ebx, r10d
0x14001b2cf  movups  xmmword ptr [rbp+4Fh+String1.Length], xmm1
0x14001b2d3  movzx   edx, word ptr [r8+4]
0x14001b2d8  lea     r11d, [r10+1]
0x14001b2dc  shr     dx, 1
0x14001b2df  mov     edi, r10d
0x14001b2e2  mov     [rbp+4Fh+var_C4], r10d
0x14001b2e6  mov     esi, r10d
0x14001b2e9  movups  [rbp+4Fh+var_88], xmm0
0x14001b2ed  movups  [rbp+4Fh+var_68], xmm1
0x14001b2f1  cmp     r10w, dx
0x14001b2f5  jnb     short loc_14001B31E
0x14001b2f7  movzx   eax, si
0x14001b2fa  movzx   ecx, word ptr [r8+rax*2+6]
0x14001b300  lea     eax, [r11+rdi]
0x14001b304  cmp     cx, 5Ch ; '\'
0x14001b308  cmovnz  ax, di
0x14001b30c  add     si, r11w
0x14001b310  movzx   edi, ax
0x14001b313  cmp     si, dx
0x14001b316  jb      short loc_14001B2F7
0x14001b318  mov     [rbp+4Fh+var_C4], esi
0x14001b31b  mov     [rbp+4Fh+var_C8], edi
0x14001b31e  mov     eax, r10d
0x14001b321  mov     [rbp+4Fh+var_CC], eax
0x14001b324  cmp     eax, r9d
0x14001b327  jnb     loc_14001B7DD
0x14001b32d  mov     r13, [rbp+4Fh+arg_20]
0x14001b331  lea     rdx, [rbp+4Fh+P]
0x14001b335  mov     r12d, eax
0x14001b338  mov     [rbp+4Fh+var_50], r12
0x14001b33c  mov     rcx, [r13+r12*8+0]
0x14001b341  call    BfConvertContainerRootIdToShortNames
0x14001b346  xor     r11d, r11d
0x14001b349  mov     ebx, eax
0x14001b34b  test    eax, eax
0x14001b34d  js      loc_14001B843
0x14001b353  mov     rdx, [r13+r12*8+0]
0x14001b358  mov     rax, [r14]
0x14001b35b  mov     r10, [rbp+4Fh+P]
0x14001b35f  movzx   ecx, word ptr [rax+4]
0x14001b363  movzx   eax, word ptr [rdx+4]
0x14001b367  movzx   r9d, word ptr [r10+4]
0x14001b36c  sub     ax, cx
0x14001b36f  movzx   ecx, si
0x14001b372  movzx   r8d, r9w
0x14001b376  add     rcx, 3
0x14001b37a  shr     r8w, 1
0x14001b37e  mov     word ptr [rbp+4Fh+var_88], ax
0x14001b382  mov     word ptr [rbp+4Fh+var_88+2], ax
0x14001b386  lea     rcx, [rdx+rcx*2]
0x14001b38a  mov     edx, r11d
0x14001b38d  mov     qword ptr [rbp+4Fh+var_88+8], rcx
0x14001b391  mov     ecx, r11d
0x14001b394  cmp     r11w, r8w
0x14001b398  jnb     short loc_14001B3BC
0x14001b39a  lea     r12d, [r11+1]
0x14001b39e  movzx   eax, dx
0x14001b3a1  cmp     word ptr [r10+rax*2+6], 5Ch ; '\'
0x14001b3a8  jz      loc_14001B4D3
0x14001b3ae  add     dx, r12w
0x14001b3b2  cmp     dx, r8w
0x14001b3b6  jb      short loc_14001B39E
0x14001b3b8  mov     r12, [rbp+4Fh+var_50]
0x14001b3bc  movzx   eax, dx
0x14001b3bf  lea     r8, [rbp+4Fh+String2]
0x14001b3c3  add     ax, ax
0x14001b3c6  add     r10, 6
0x14001b3ca  sub     r9w, ax
0x14001b3ce  movzx   eax, dx
0x14001b3d1  xor     edx, edx
0x14001b3d3  mov     word ptr [rbp+4Fh+var_68], r9w
0x14001b3d8  mov     word ptr [rbp+4Fh+var_68+2], r9w
0x14001b3dd  lea     rcx, [r10+rax*2]
0x14001b3e1  mov     qword ptr [rbp+4Fh+var_68+8], rcx
0x14001b3e5  lea     rcx, [rbp+4Fh+var_88]
0x14001b3e9  call    BfpWalkPath
0x14001b3ee  xor     edx, edx
0x14001b3f0  mov     [rsp+50h], al
0x14001b3f4  lea     r8, [rbp+4Fh+String1]
0x14001b3f8  mov     r14b, al
0x14001b3fb  lea     rcx, [rbp+4Fh+var_68]
0x14001b3ff  call    BfpWalkPath
0x14001b404  mov     rsi, [r15+50h]
0x14001b408  xor     r11d, r11d
0x14001b40b  lea     r15d, [r11+1]
0x14001b40f  lea     rax, [rbp+4Fh+String2]
0x14001b413  mov     rbx, [rsi]
0x14001b416  xorps   xmm0, xmm0
0x14001b419  movups  xmmword ptr [rbp+4Fh+var_B8], xmm0
0x14001b41d  mov     [rbp+4Fh+var_B8], rax
0x14001b421  mov     byte ptr [rbp+4Fh+var_B8+8], r11b
0x14001b425  test    [rsi+8], r15b
0x14001b429  jnz     loc_14001B829
0x14001b42f  movzx   edi, byte ptr [rsi+8]
0x14001b433  and     edi, r15d
0x14001b436  test    rbx, rbx
0x14001b439  jz      loc_14001B4F9
0x14001b43f  mov     rdx, rbx
0x14001b442  lea     rcx, [rbp+4Fh+var_B8]
0x14001b446  call    BfpRBComparePathNodes
0x14001b44b  test    eax, eax
0x14001b44d  js      short loc_14001B4CE
0x14001b44f  jle     short loc_14001B465
0x14001b451  mov     rax, [rbx+8]
0x14001b455  test    edi, edi
0x14001b457  jnz     loc_14001B4E5
0x14001b45d  mov     rbx, rax
0x14001b460  test    rbx, rbx
0x14001b463  jnz     short loc_14001B43F
0x14001b465  mov     r13, [rbp+4Fh+arg_20]
0x14001b469  test    rbx, rbx
0x14001b46c  jz      loc_14001B4F6
0x14001b472  mov     eax, [rbx-8]
0x14001b475  test    al, 2
0x14001b477  jnz     loc_14001B999
0x14001b47d  test    r14b, r14b
0x14001b480  jz      loc_14001B7B7
0x14001b486  xor     edx, edx
0x14001b488  lea     r8, [rbp+4Fh+String2]
0x14001b48c  lea     rcx, [rbp+4Fh+var_88]
0x14001b490  call    BfpWalkPath
0x14001b495  xor     edx, edx
0x14001b497  mov     [rsp+50h], al
0x14001b49b  lea     r8, [rbp+4Fh+String1]
0x14001b49f  mov     r14b, al
0x14001b4a2  lea     rcx, [rbp+4Fh+var_68]
0x14001b4a6  call    BfpWalkPath
0x14001b4ab  lea     rdi, [rbx+48h]
0x14001b4af  mov     rsi, [rdi]
0x14001b4b2  mov     rcx, rsi
0x14001b4b5  call    BfpPathTreeEmpty
0x14001b4ba  xor     r11d, r11d
0x14001b4bd  test    al, al
0x14001b4bf  jnz     loc_14001B8CC
0x14001b4c5  mov     [rbp+4Fh+var_B8], r11
0x14001b4c9  jmp     loc_14001B40F
0x14001b4ce  mov     rax, [rbx]
0x14001b4d1  jmp     short loc_14001B455
0x14001b4d3  add     cx, r12w
0x14001b4d7  cmp     cx, di
0x14001b4da  jbe     loc_14001B3AE
0x14001b4e0  jmp     loc_14001B3B8
0x14001b4e5  test    rax, rax
0x14001b4e8  jz      loc_14001B45D
0x14001b4ee  xor     rbx, rax
0x14001b4f1  jmp     loc_14001B460
0x14001b4f6  xor     r11d, r11d
0x14001b4f9  mov     rax, r11
0x14001b4fc  mov     [rbp+4Fh+var_B8], rax
0x14001b500  mov     al, r14b
0x14001b503  lea     rcx, [rbp+4Fh+String2]; SourceString
0x14001b507  neg     al
0x14001b509  xorps   xmm0, xmm0
0x14001b50c  lea     rax, [rbp+4Fh+var_B8]
0x14001b510  mov     r8b, r14b
0x14001b513  mov     [rsp+40h], rax; __int64
0x14001b518  sbb     r15d, r15d
0x14001b51b  mov     rax, [r13+r12*8+0]
0x14001b520  not     r15d
0x14001b523  mov     [rsp+120h+var_E8], r11; __int64
0x14001b528  and     r15d, 4
0x14001b52c  mov     [rsp+120h+var_F0], r11; __int64
0x14001b531  mov     edx, r15d
0x14001b534  mov     [rsp+120h+var_F8], rax; __int64
0x14001b539  xor     r9d, r9d
0x14001b53c  mov     rax, [rbp+4Fh+arg_10]
0x14001b540  mov     [rsp+120h+var_100], rax; __int64
0x14001b545  movups  [rbp+4Fh+var_98], xmm0
0x14001b549  call    BfpCreatePathTierNode
0x14001b54e  xor     r11d, r11d
0x14001b551  mov     ebx, eax
0x14001b553  test    eax, eax
0x14001b555  js      loc_14001B8FE
0x14001b55b  mov     r13, [rbp+4Fh+var_B8]
0x14001b55f  lea     ecx, [r11+1]
0x14001b563  mov     rdi, [rsi]
0x14001b566  mov     byte ptr [rbp+4Fh+var_98+8], r11b
0x14001b56a  lea     rax, [r13+20h]
0x14001b56e  mov     qword ptr [rbp+4Fh+var_98], rax
0x14001b572  test    [rsi+8], cl
0x14001b575  jnz     loc_14001B836
0x14001b57b  movzx   r14d, byte ptr [rsi+8]
0x14001b580  mov     r8b, r11b
0x14001b583  and     r14d, ecx
0x14001b586  test    rdi, rdi
0x14001b589  jz      short loc_14001B5BB
0x14001b58b  mov     rdx, rdi
0x14001b58e  lea     rcx, [rbp+4Fh+var_98]
0x14001b592  call    BfpRBComparePathNodes
0x14001b597  xor     ecx, ecx
0x14001b599  test    eax, eax
0x14001b59b  js      loc_14001B764
0x14001b5a1  mov     rax, [rdi+8]
0x14001b5a5  test    r14d, r14d
0x14001b5a8  jnz     loc_14001B7A6
0x14001b5ae  test    rax, rax
0x14001b5b1  jz      short loc_14001B5B8
0x14001b5b3  mov     rdi, rax
0x14001b5b6  jmp     short loc_14001B58B
0x14001b5b8  mov     r8b, 1
0x14001b5bb  lea     r9, [r13+8]
0x14001b5bf  mov     rdx, rdi
0x14001b5c2  mov     rcx, rsi
0x14001b5c5  call    cs:__imp_RtlRbInsertNodeEx
0x14001b5cc  nop     dword ptr [rax+rax+00h]
0x14001b5d1  xor     r8d, r8d; CaseInSensitive
0x14001b5d4  lea     rdx, g_NoShortComponent; String2
0x14001b5db  lea     rcx, [rbp+4Fh+String1]; String1
0x14001b5df  call    cs:__imp_RtlCompareUnicodeString
0x14001b5e6  nop     dword ptr [rax+rax+00h]
0x14001b5eb  xor     edi, edi
0x14001b5ed  test    eax, eax
0x14001b5ef  jz      loc_14001B6E7
0x14001b5f5  xor     r8d, r8d; CaseInSensitive
0x14001b5f8  lea     rdx, [rbp+4Fh+String2]; String2
0x14001b5fc  lea     rcx, [rbp+4Fh+String1]; String1
0x14001b600  call    cs:__imp_RtlCompareUnicodeString
0x14001b607  nop     dword ptr [rax+rax+00h]
0x14001b60c  test    eax, eax
0x14001b60e  jz      loc_14001B6E7
0x14001b614  mov     cl, [rsp+50h]
0x14001b618  xorps   xmm0, xmm0
0x14001b61b  movups  [rbp+4Fh+var_98], xmm0
0x14001b61f  test    cl, cl
0x14001b621  jz      loc_14001B781
0x14001b627  mov     rax, [r13+50h]
0x14001b62b  lea     rdx, [rbp+4Fh+var_58]
0x14001b62f  mov     r8b, cl
0x14001b632  mov     [rsp+40h], rdx; __int64
0x14001b637  lea     rcx, [rbp+4Fh+String1]; SourceString
0x14001b63b  mov     [rsp+120h+var_E8], rax; __int64
0x14001b640  or      r15d, 2
0x14001b644  mov     [rsp+120h+var_F0], rdi; __int64
0x14001b649  xor     r9d, r9d
0x14001b64c  mov     [rsp+120h+var_F8], rdi; __int64
0x14001b651  mov     edx, r15d
0x14001b654  mov     [rsp+120h+var_100], rdi; __int64
0x14001b659  call    BfpCreatePathTierNode
0x14001b65e  xor     r11d, r11d
0x14001b661  mov     ebx, eax
0x14001b663  test    eax, eax
0x14001b665  js      loc_14001B805
0x14001b66b  mov     r15, [rbp+4Fh+var_58]
0x14001b66f  lea     ecx, [r11+1]
0x14001b673  mov     rdi, [rsi]
0x14001b676  mov     byte ptr [rbp+4Fh+var_98+8], r11b
0x14001b67a  lea     rax, [r15+20h]
0x14001b67e  mov     qword ptr [rbp+4Fh+var_98], rax
0x14001b682  test    [rsi+8], cl
0x14001b685  jnz     loc_14001B8AE
0x14001b68b  movzx   r14d, byte ptr [rsi+8]
0x14001b690  mov     r8b, r11b
0x14001b693  and     r14d, ecx
0x14001b696  test    rdi, rdi
0x14001b699  jz      short loc_14001B6CB
0x14001b69b  mov     rdx, rdi
0x14001b69e  lea     rcx, [rbp+4Fh+var_98]
0x14001b6a2  call    BfpRBComparePathNodes
0x14001b6a7  xor     ecx, ecx
0x14001b6a9  test    eax, eax
0x14001b6ab  js      loc_14001B789
0x14001b6b1  mov     rax, [rdi+8]
0x14001b6b5  test    r14d, r14d
0x14001b6b8  jnz     loc_14001B7F4
0x14001b6be  test    rax, rax
0x14001b6c1  jz      short loc_14001B6C8
0x14001b6c3  mov     rdi, rax
0x14001b6c6  jmp     short loc_14001B69B
0x14001b6c8  mov     r8b, 1
0x14001b6cb  lea     r9, [r15+8]
0x14001b6cf  mov     rdx, rdi
0x14001b6d2  mov     rcx, rsi
0x14001b6d5  call    cs:__imp_RtlRbInsertNodeEx
0x14001b6dc  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
