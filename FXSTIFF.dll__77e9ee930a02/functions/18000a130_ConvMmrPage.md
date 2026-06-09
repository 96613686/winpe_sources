# ConvMmrPage

- ea: `0x18000a130`
- end: `0x18000a985`
- name: `ConvMmrPage`
- size: `2133`
- prototype: `__int64 __fastcall(__int64, _DWORD *, unsigned int *, int, unsigned __int8, int)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000a990`
- `0x18000a9c0`
- `0x18000a9f0`

## callees

- `0x180009f04`
- `0x180009f34`
- `0x18000a130`
- `0x18000ab60`
- `0x18000ad58`
- `0x18000c750`
- `0x18000df04`
- `0x18001899e`
- `0x1800189d0`
- `0x180018a60`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000a825`
- `KERNEL32!SetLastError` at `0x18000a840`
- `KERNEL32!SetLastError` at `0x18000a856`
- `KERNEL32!SetLastError` at `0x18000a90e`
- `KERNEL32!SetLastError` at `0x18000a825`
- `KERNEL32!SetLastError` at `0x18000a840`
- `KERNEL32!SetLastError` at `0x18000a856`
- `KERNEL32!SetLastError` at `0x18000a90e`

## pseudocode

```c
__int64 __fastcall ConvMmrPage(__int64 a1, _DWORD *a2, unsigned int *a3, int a4, unsigned __int8 a5, int a6)
{
  _QWORD *v10; // rcx
  int v11; // esi
  int v12; // ebx
  __int64 v13; // rcx
  const wchar_t *v14; // r9
  size_t v15; // r8
  unsigned __int64 v16; // r14
  _BYTE *v17; // r12
  unsigned int *v18; // rbx
  unsigned __int8 v19; // di
  unsigned __int64 v20; // rcx
  int v21; // r8d
  __int64 v22; // rax
  _DWORD *v23; // r13
  unsigned __int64 v24; // rdx
  _BYTE *v25; // r15
  int MrLine; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  char v30; // al
  unsigned int *v31; // rbx
  unsigned __int8 v32; // dl
  int v33; // eax
  char v34; // dl
  unsigned __int8 v35; // r10
  unsigned __int8 v36; // r15
  int v37; // r9d
  char v38; // r11
  int v39; // edi
  unsigned int v40; // r8d
  char v41; // r9
  char v42; // di
  char v43; // dl
  char v44; // di
  unsigned int v45; // r9d
  char v46; // dl
  unsigned __int8 v47; // dl
  unsigned int v48; // edx
  _DWORD *v49; // r8
  char v50; // r8
  unsigned int v51; // edx
  _BYTE *v52; // rcx
  int v53; // r8d
  _BYTE *v54; // rcx
  __int64 *v55; // rcx
  int v56; // eax
  DWORD v58; // ecx
  _QWORD *v59; // rcx
  __int64 v60; // rdx
  _QWORD *v61; // rcx
  __int64 v62; // rdx
  char v63; // [rsp+40h] [rbp-C0h] BYREF
  char v64; // [rsp+41h] [rbp-BFh]
  unsigned __int8 v65; // [rsp+42h] [rbp-BEh] BYREF
  unsigned int *v66; // [rsp+48h] [rbp-B8h] BYREF
  _WORD *v67; // [rsp+50h] [rbp-B0h]
  int v68; // [rsp+58h] [rbp-A8h]
  _DWORD *v69; // [rsp+60h] [rbp-A0h] BYREF
  int v70; // [rsp+68h] [rbp-98h]
  int v71; // [rsp+6Ch] [rbp-94h]
  int v72; // [rsp+70h] [rbp-90h]
  _DWORD *v73; // [rsp+78h] [rbp-88h]
  unsigned __int64 v74; // [rsp+80h] [rbp-80h]
  _DWORD *v75; // [rsp+88h] [rbp-78h]
  _DWORD *v76; // [rsp+90h] [rbp-70h]
  _WORD v77[1736]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v78[3472]; // [rsp+E30h] [rbp+D30h] BYREF
  _BYTE v79[3472]; // [rsp+1BC0h] [rbp+1AC0h] BYREF

  v72 = a4;
  v76 = a3;
  v75 = a2;
  v70 = 0;
  v10 = WPP_GLOBAL_Control;
  v11 = 2;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    goto LABEL_11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 2) == 0 )
  {
LABEL_11:
    v12 = a6;
  }
  else
  {
    v12 = a6;
    if ( *((_BYTE *)v10 + 25) >= 5u )
    {
      v13 = v10[2];
      v14 = L"MH";
      if ( a4 != 2 )
        v14 = L"MR";
      WPP_SF_Sdd(v13, (unsigned int)L"MR", (_DWORD)a3, (_DWORD)v14, a5, a6);
    }
  }
  v15 = *a3;
  v67 = v77;
  v16 = (unsigned __int64)&a2[v15 >> 2];
  if ( a4 != 3 || (v17 = v78, !v12) )
    v17 = v79;
  v18 = a2;
  v66 = a2;
  v19 = 0;
  memset_0(a2, 0, v15);
  v20 = *(_QWORD *)(a1 + 1536);
  v21 = *(_DWORD *)(a1 + 1564);
  v22 = *(unsigned int *)(a1 + 1552);
  v23 = (_DWORD *)(v20 & 0xFFFFFFFFFFFFFFFCuLL);
  *(_QWORD *)(a1 + 1572) = 0;
  *(_QWORD *)(a1 + 1668) = 0;
  v24 = (v22 + v20 - 1) & 0xFFFFFFFFFFFFFFFCuLL;
  v71 = v21;
  LOBYTE(v20) = (8 * v20) & 0x18;
  v74 = v24;
  v73 = (_DWORD *)v20;
  v65 = v20;
  v69 = v23;
  v77[0] = v21;
  v68 = 1;
  v64 = 0;
  while ( 1 )
  {
    if ( (unsigned __int64)v18 >= v16 || (unsigned __int64)((__int64)(v16 - (_QWORD)v18) >> 2) < 4 )
    {
      SetLastError(0x7Au);
      v59 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 0;
      }
      v60 = 27;
      goto LABEL_127;
    }
    v25 = v67;
    MrLine = ReadMrLine((unsigned int)&v69, (unsigned int)&v65, (_DWORD)v67, (_DWORD)v17, v24, 1, v21);
    if ( !MrLine )
    {
      v30 = ++v70;
      if ( v72 == 2 )
      {
        if ( a6 && (v30 & 1) == 0 )
        {
LABEL_40:
          v67 = v17;
          v17 = v25;
          goto LABEL_96;
        }
        if ( v19 <= 4u )
        {
          *v18 += 0x8000;
LABEL_37:
          v63 = 16;
          goto LABEL_38;
        }
        if ( v19 > 0xCu )
        {
          if ( v19 > 0x14u )
          {
            v31 = v18 + 1;
            v66 = v31;
            if ( v19 > 0x1Cu )
            {
              *v31 = 0x8000;
              goto LABEL_37;
            }
            *v31 = 128;
            v63 = 8;
          }
          else
          {
            *v18 += 0x80000000;
            v63 = 0;
            v66 = v18 + 1;
          }
        }
        else
        {
          *v18 += 0x800000;
          v63 = 24;
        }
LABEL_38:
        if ( !(unsigned int)OutputMhLine(v17, &v66, &v63, v16) )
          goto LABEL_116;
        v19 = v63;
        v18 = v66;
        goto LABEL_40;
      }
      if ( !a6 )
      {
        if ( v19 < 0x20u )
        {
          v32 = *((_BYTE *)gc_AlignEolTable + v19);
          if ( v32 < v19 )
            v66 = ++v18;
          v33 = 1 << v32;
          v34 = v32 + 1;
          *v18 += v33;
          if ( v34 == 32 )
          {
            ++v18;
            v34 = 0;
            v66 = v18;
          }
          v35 = v34 + 1;
          v36 = v65;
          if ( v68 )
          {
            v63 = v34 + 1;
            *v18 += 1 << v34;
            if ( !(unsigned int)OutputMhLine(v17, &v66, &v63, v16) )
              goto LABEL_116;
            v19 = v63;
            v18 = v66;
            v68 = 0;
            goto LABEL_78;
          }
          v37 = *v23;
          v38 = (char)v73;
          v39 = -1 << (char)v73;
          if ( v69 == v23 )
          {
            v23 = v73;
            v40 = v39 & v37 & (0xFFFFFFFF >> (32 - v65));
            if ( v35 < (unsigned __int8)v73 )
            {
              v44 = v34 - (_BYTE)v73 + 1;
              *v18 += v40 >> ((_BYTE)v73 - v35);
              v19 = v36 + v44;
            }
            else
            {
              v41 = 31 - v34;
              v42 = v65 - (_BYTE)v73;
              *v18 += v40 << (v35 - (_BYTE)v73);
              if ( (unsigned __int8)(31 - v34) < (unsigned __int8)(v36 - (_BYTE)v23) )
              {
                ++v18;
                v19 = v42 - v41;
                *v18 = v40 >> (v38 + v41);
LABEL_75:
                v66 = v18;
                goto LABEL_76;
              }
              v43 = v42 + v34;
              v19 = v43 + 1;
              if ( (unsigned __int8)(v43 + 1) > 0x1Fu )
              {
                v19 = v43 - 31;
LABEL_74:
                ++v18;
                goto LABEL_75;
              }
            }
            goto LABEL_76;
          }
          v45 = v39 & v37;
          ++v23;
          v46 = v34 - (_BYTE)v73;
          if ( v35 <= (unsigned __int8)v73 )
          {
            v47 = v46 + 33;
            v19 = v47;
            *v18 += v45 >> ((_BYTE)v73 - v35);
            if ( v47 <= 0x1Fu )
              goto LABEL_62;
            v19 = v47 - 32;
            ++v18;
          }
          else
          {
            v19 = v46 + 1;
            *v18++ += v45 << (v46 + 1);
            *v18 = v45 >> (32 - (v46 + 1));
          }
          v66 = v18;
LABEL_62:
          if ( v23 >= v69 )
          {
LABEL_69:
            if ( v36 )
            {
              v50 = 32 - v19;
              v51 = *v23 & (0xFFFFFFFF >> (32 - v36));
              *v18 += v51 << v19;
              if ( (unsigned __int8)(32 - v19) < v36 )
              {
                ++v18;
                v19 = v36 - v50;
                *v18 = v51 >> v50;
                goto LABEL_75;
              }
              v19 += v36;
              if ( v19 > 0x1Fu )
              {
                v19 -= 32;
                goto LABEL_74;
              }
            }
LABEL_76:
            if ( (unsigned __int8)++v64 < a5 )
            {
LABEL_79:
              v52 = v67;
              LOBYTE(v23) = v36;
              v73 = v23;
              v23 = v69;
              v67 = v17;
              v17 = v52;
              goto LABEL_96;
            }
            v68 = 1;
LABEL_78:
            v64 = 0;
            goto LABEL_79;
          }
          while ( (unsigned __int64)v18 < v16 && (unsigned __int64)((__int64)(v16 - (_QWORD)v18) >> 2) >= 4 )
          {
            v48 = *v23;
            v49 = v23 + 1;
            if ( v19 )
            {
              *v18++ += v48 << v19;
              *v18 = *v23 >> (32 - v19);
            }
            else
            {
              *v18++ = v48;
            }
            ++v23;
            v66 = v18;
            if ( v49 >= v69 )
              goto LABEL_69;
          }
          SetLastError(0x7Au);
          v59 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v60 = 29;
LABEL_127:
            WPP_SF_d(
              v59[2],
              v60,
              &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids,
              (unsigned int)((__int64)(v16 - (_QWORD)v18) >> 2));
          }
          return 0;
        }
        v61 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_122;
        }
        v62 = 28;
        goto LABEL_121;
      }
      v53 = v30 & 3;
      if ( v53 == 2 )
      {
        v54 = v77;
        v17 = v79;
      }
      else if ( (v30 & 3) != 0 )
      {
        if ( v19 >= 0x20u )
        {
          v61 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_122;
          }
          v62 = 30;
LABEL_121:
          WPP_SF_d(v61[2], v62, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids, v19);
LABEL_122:
          v58 = 1359;
          goto LABEL_107;
        }
        v55 = gc_AlignEolTable;
        LOBYTE(v55) = *((_BYTE *)gc_AlignEolTable + v19);
        if ( (unsigned __int8)v55 < v19 )
          v66 = ++v18;
        v56 = 1 << (char)v55;
        LOBYTE(v55) = (_BYTE)v55 + 1;
        *v18 += v56;
        if ( (_BYTE)v55 == 32 )
        {
          ++v18;
          LOBYTE(v55) = 0;
          v66 = v18;
        }
        v63 = (_BYTE)v55 + 1;
        if ( v53 == 1 )
        {
          *v18 += 1 << (char)v55;
          if ( !(unsigned int)OutputMhLine(v17, &v66, &v63, v16) )
            goto LABEL_116;
          v54 = v78;
        }
        else
        {
          if ( !(unsigned int)OutputMmrLine(
                                (_DWORD)v18,
                                (int)v55 + 1,
                                (_DWORD)v17,
                                (unsigned int)v78,
                                (__int64)&v66,
                                (__int64)&v63,
                                v16,
                                v71) )
          {
LABEL_116:
            v58 = 122;
LABEL_107:
            SetLastError(v58);
            return 0;
          }
          v54 = v79;
        }
        v18 = v66;
        v17 = v77;
        v19 = v63;
      }
      else
      {
        v54 = v77;
        v17 = v78;
      }
      v67 = v54;
      goto LABEL_96;
    }
    v27 = MrLine - 1;
    if ( !v27 || (v28 = v27 - 1) == 0 || (v29 = v28 - 1) == 0 )
    {
LABEL_106:
      v58 = 1392;
      goto LABEL_107;
    }
    if ( v29 == 1 )
      break;
LABEL_96:
    v24 = v74;
    if ( (unsigned __int64)v69 > v74 )
      goto LABEL_106;
    v21 = v71;
  }
  if ( v19 > 4u )
  {
    if ( v19 > 0xCu )
    {
      if ( v19 > 0x14u )
      {
        ++v18;
        if ( v19 > 0x1Cu )
        {
          *v18 = 0x8000;
        }
        else
        {
          *v18 = 128;
          v11 = 1;
        }
      }
      else
      {
        *v18 += 0x80000000;
        v11 = 0;
        ++v18;
      }
    }
    else
    {
      *v18 += 0x800000;
      v11 = 3;
    }
  }
  else
  {
    *v18 += 0x8000;
  }
  *v76 = v11 + 4 * (v18 - v75);
  SetLastError(0);
  return 1;
}

```

## disassembly

```asm
0x18000a130  mov     [rsp-8+arg_18], rbx
0x18000a135  push    rbp
0x18000a136  push    rsi
0x18000a137  push    rdi
0x18000a138  push    r12
0x18000a13a  push    r13
0x18000a13c  push    r14
0x18000a13e  push    r15
0x18000a140  lea     rbp, [rsp-2860h]
0x18000a148  mov     eax, 2960h
0x18000a14d  call    _alloca_probe
0x18000a152  sub     rsp, rax
0x18000a155  mov     rax, cs:__security_cookie
0x18000a15c  xor     rax, rsp
0x18000a15f  mov     [rbp+2890h+var_40], rax
0x18000a166  mov     edi, r9d
0x18000a169  mov     [rsp+2990h+var_2920], r9d
0x18000a16e  mov     r14, r8
0x18000a171  mov     [rbp+2890h+var_2900], r8
0x18000a175  mov     r13, rdx
0x18000a178  mov     [rbp+2890h+var_2908], rdx
0x18000a17c  mov     r15, rcx
0x18000a17f  mov     [rsp+2990h+var_2928], 0
0x18000a187  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a18e  lea     rbx, WPP_GLOBAL_Control
0x18000a195  mov     esi, 2
0x18000a19a  cmp     rcx, rbx
0x18000a19d  jz      short loc_18000A20A
0x18000a19f  test    [rcx+1Ch], sil
0x18000a1a3  jz      short loc_18000A1C5
0x18000a1a5  cmp     byte ptr [rcx+19h], 5
0x18000a1a9  jb      short loc_18000A1C5
0x18000a1ab  mov     rcx, [rcx+10h]
0x18000a1af  lea     edx, [rsi+17h]
0x18000a1b2  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000a1b9  call    WPP_SF_
0x18000a1be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a1c5  cmp     rcx, rbx
0x18000a1c8  jz      short loc_18000A20A
0x18000a1ca  test    [rcx+1Ch], sil
0x18000a1ce  jz      short loc_18000A20A
0x18000a1d0  cmp     byte ptr [rcx+19h], 5
0x18000a1d4  mov     ebx, [rbp+2890h+arg_28]
0x18000a1da  jb      short loc_18000A210
0x18000a1dc  movzx   eax, [rbp+2890h+arg_20]
0x18000a1e3  lea     rdx, aMr; "MR"
0x18000a1ea  mov     rcx, [rcx+10h]
0x18000a1ee  lea     r9, aMh; "MH"
0x18000a1f5  cmp     edi, esi
0x18000a1f7  mov     dword ptr [rsp+2990h+var_2968], ebx
0x18000a1fb  mov     dword ptr [rsp+2990h+var_2970], eax
0x18000a1ff  cmovnz  r9, rdx
0x18000a203  call    WPP_SF_Sdd
0x18000a208  jmp     short loc_18000A210
0x18000a20a  mov     ebx, [rbp+2890h+arg_28]
0x18000a210  mov     r8d, [r14]; Size
0x18000a213  lea     rcx, [rbp+2890h+var_28F0]
0x18000a217  mov     eax, r8d
0x18000a21a  mov     [rsp+2990h+var_2940], rcx
0x18000a21f  shr     rax, 2
0x18000a223  lea     r14, ds:0[rax*4]
0x18000a22b  add     r14, r13
0x18000a22e  cmp     edi, 3
0x18000a231  jnz     short loc_18000A23E
0x18000a233  lea     r12, [rbp+2890h+var_1B60]
0x18000a23a  test    ebx, ebx
0x18000a23c  jnz     short loc_18000A245
0x18000a23e  lea     r12, [rbp+2890h+var_DD0]
0x18000a245  mov     rbx, r13
0x18000a248  xor     edx, edx; Val
0x18000a24a  mov     rcx, r13; void *
0x18000a24d  mov     [rsp+2990h+var_2948], rbx
0x18000a252  xor     dil, dil
0x18000a255  call    memset_0
0x18000a25a  mov     rcx, [r15+600h]
0x18000a261  xor     r9d, r9d
0x18000a264  mov     r8d, [r15+61Ch]
0x18000a26b  mov     r13, rcx
0x18000a26e  mov     eax, [r15+610h]
0x18000a275  and     r13, 0FFFFFFFFFFFFFFFCh
0x18000a279  mov     [r15+624h], r9
0x18000a280  lea     rdx, [rcx-1]
0x18000a284  mov     [r15+684h], r9
0x18000a28b  add     rdx, rax
0x18000a28e  shl     cl, 3
0x18000a291  and     rdx, 0FFFFFFFFFFFFFFFCh
0x18000a295  mov     [rsp+2990h+var_2924], r8d
0x18000a29a  and     cl, 18h
0x18000a29d  mov     [rbp+2890h+var_2910], rdx
0x18000a2a1  mov     [rsp+2990h+var_2918], rcx
0x18000a2a6  mov     [rsp+2990h+var_294E], cl
0x18000a2aa  mov     [rsp+2990h+var_2930], r13
0x18000a2af  mov     [rbp+2890h+var_28F0], r8w
0x18000a2b4  mov     [rsp+2990h+var_2938], 1
0x18000a2bc  mov     [rsp+2990h+var_294F], r9b
0x18000a2c1  cmp     rbx, r14
0x18000a2c4  jnb     loc_18000A909
0x18000a2ca  mov     rax, r14
0x18000a2cd  sub     rax, rbx
0x18000a2d0  sar     rax, 2
0x18000a2d4  cmp     rax, 4
0x18000a2d8  jb      loc_18000A909
0x18000a2de  mov     r15, [rsp+2990h+var_2940]
0x18000a2e3  lea     rcx, [rsp+2990h+var_2930]
0x18000a2e8  mov     dword ptr [rsp+2990h+var_2960], r8d
0x18000a2ed  mov     r9, r12
0x18000a2f0  mov     dword ptr [rsp+2990h+var_2968], 1
0x18000a2f8  mov     r8, r15
0x18000a2fb  mov     [rsp+2990h+var_2970], rdx
0x18000a300  lea     rdx, [rsp+2990h+var_294E]
0x18000a305  call    ReadMrLine
0x18000a30a  xor     r9d, r9d
0x18000a30d  mov     ecx, eax
0x18000a30f  test    eax, eax
0x18000a311  jz      short loc_18000A34C
0x18000a313  sub     ecx, 1
0x18000a316  jz      loc_18000A83B
0x18000a31c  sub     ecx, 1
0x18000a31f  jz      loc_18000A83B
0x18000a325  sub     ecx, 1
0x18000a328  jz      loc_18000A83B
0x18000a32e  cmp     ecx, 1
0x18000a331  jnz     loc_18000A7B8
0x18000a337  cmp     dil, 4
0x18000a33b  ja      loc_18000A7CD
0x18000a341  add     dword ptr [rbx], 8000h
0x18000a347  jmp     loc_18000A812
0x18000a34c  mov     eax, [rsp+2990h+var_2928]
0x18000a350  mov     r11d, 1
0x18000a356  add     eax, r11d
0x18000a359  mov     [rsp+2990h+var_2928], eax
0x18000a35d  cmp     [rsp+2990h+var_2920], esi
0x18000a361  jnz     loc_18000A411
0x18000a367  cmp     [rbp+2890h+arg_28], r9d
0x18000a36e  jz      short loc_18000A379
0x18000a370  test    r11b, al
0x18000a373  jz      loc_18000A404
0x18000a379  cmp     dil, 4
0x18000a37d  ja      short loc_18000A387
0x18000a37f  add     dword ptr [rbx], 8000h
0x18000a385  jmp     short loc_18000A3D8
0x18000a387  cmp     dil, 0Ch
0x18000a38b  ja      short loc_18000A39A
0x18000a38d  add     dword ptr [rbx], 800000h
0x18000a393  mov     [rsp+2990h+var_2950], 18h
0x18000a398  jmp     short loc_18000A3DD
0x18000a39a  cmp     dil, 14h
0x18000a39e  ja      short loc_18000A3B6
0x18000a3a0  add     dword ptr [rbx], 80000000h
0x18000a3a6  add     rbx, 4
0x18000a3aa  mov     [rsp+2990h+var_2950], r9b
0x18000a3af  mov     [rsp+2990h+var_2948], rbx
0x18000a3b4  jmp     short loc_18000A3DD
0x18000a3b6  add     rbx, 4
0x18000a3ba  mov     [rsp+2990h+var_2948], rbx
0x18000a3bf  cmp     dil, 1Ch
0x18000a3c3  ja      short loc_18000A3D2
0x18000a3c5  mov     dword ptr [rbx], 80h
0x18000a3cb  mov     [rsp+2990h+var_2950], 8
0x18000a3d0  jmp     short loc_18000A3DD
0x18000a3d2  mov     dword ptr [rbx], 8000h
0x18000a3d8  mov     [rsp+2990h+var_2950], 10h
0x18000a3dd  mov     r9, r14
0x18000a3e0  lea     r8, [rsp+2990h+var_2950]
0x18000a3e5  lea     rdx, [rsp+2990h+var_2948]
0x18000a3ea  mov     rcx, r12
0x18000a3ed  call    OutputMhLine
0x18000a3f2  test    eax, eax
0x18000a3f4  jz      loc_18000A8BD
0x18000a3fa  mov     dil, [rsp+2990h+var_2950]
0x18000a3ff  mov     rbx, [rsp+2990h+var_2948]
0x18000a404  mov     [rsp+2990h+var_2940], r12
0x18000a409  mov     r12, r15
0x18000a40c  jmp     loc_18000A7B8
0x18000a411  cmp     [rbp+2890h+arg_28], r9d
0x18000a418  jnz     loc_18000A6B7
0x18000a41e  mov     r8d, 20h ; ' '
0x18000a424  cmp     dil, r8b
0x18000a427  jnb     loc_18000A897
0x18000a42d  movzx   eax, dil
0x18000a431  lea     rcx, gc_AlignEolTable
0x18000a438  mov     dl, [rax+rcx]
0x18000a43b  cmp     dl, dil
0x18000a43e  jnb     short loc_18000A449
0x18000a440  add     rbx, 4
0x18000a444  mov     [rsp+2990h+var_2948], rbx
0x18000a449  mov     cl, dl
0x18000a44b  mov     eax, r11d
0x18000a44e  shl     eax, cl
0x18000a450  add     dl, r11b
0x18000a453  add     [rbx], eax
0x18000a455  cmp     dl, r8b
0x18000a458  jnz     short loc_18000A466
0x18000a45a  add     rbx, 4
0x18000a45e  mov     dl, r9b
0x18000a461  mov     [rsp+2990h+var_2948], rbx
0x18000a466  lea     r10d, [r11+rdx]
0x18000a46a  movzx   r15d, [rsp+2990h+var_294E]
0x18000a470  cmp     [rsp+2990h+var_2938], r9d
0x18000a475  jz      short loc_18000A4B9
0x18000a477  mov     cl, dl
0x18000a479  mov     [rsp+2990h+var_2950], r10b
0x18000a47e  mov     eax, r11d
0x18000a481  lea     r8, [rsp+2990h+var_2950]
0x18000a486  shl     eax, cl
0x18000a488  lea     rdx, [rsp+2990h+var_2948]
0x18000a48d  add     [rbx], eax
0x18000a48f  mov     rcx, r12
0x18000a492  mov     r9, r14
0x18000a495  call    OutputMhLine
0x18000a49a  test    eax, eax
0x18000a49c  jz      loc_18000A8BD
0x18000a4a2  mov     dil, [rsp+2990h+var_2950]
0x18000a4a7  mov     rbx, [rsp+2990h+var_2948]
0x18000a4ac  mov     [rsp+2990h+var_2938], 0
0x18000a4b4  jmp     loc_18000A692
0x18000a4b9  mov     rax, [rsp+2990h+var_2918]
0x18000a4be  or      edi, 0FFFFFFFFh
0x18000a4c1  mov     r9d, [r13+0]
0x18000a4c5  movzx   r11d, al
0x18000a4c9  mov     ecx, r11d
0x18000a4cc  shl     edi, cl
0x18000a4ce  cmp     [rsp+2990h+var_2930], r13
0x18000a4d3  jnz     loc_18000A568
0x18000a4d9  mov     r13, [rsp+2990h+var_2918]
0x18000a4de  mov     ecx, r8d
0x18000a4e1  or      r8d, 0FFFFFFFFh
0x18000a4e5  movzx   eax, r10b
0x18000a4e9  sub     ecx, r15d
0x18000a4ec  shr     r8d, cl
0x18000a4ef  and     r8d, r9d
0x18000a4f2  and     r8d, edi
0x18000a4f5  cmp     r10b, r13b
0x18000a4f8  jb      short loc_18000A54B
0x18000a4fa  sub     eax, r11d
0x18000a4fd  mov     r9d, 1Fh
0x18000a503  mov     cl, al
0x18000a505  mov     dil, r15b
0x18000a508  mov     eax, r8d
0x18000a50b  sub     r9b, dl
0x18000a50e  shl     eax, cl
0x18000a510  sub     dil, r13b
0x18000a513  add     [rbx], eax
0x18000a515  cmp     r9b, dil
0x18000a518  jnb     short loc_18000A533
0x18000a51a  add     rbx, 4
0x18000a51e  movzx   ecx, r9b
0x18000a522  add     ecx, r11d
0x18000a525  shr     r8d, cl
0x18000a528  sub     dil, r9b
0x18000a52b  mov     [rbx], r8d
0x18000a52e  jmp     loc_18000A673
0x18000a533  add     dl, dil
0x18000a536  lea     edi, [rdx+1]
0x18000a539  cmp     dil, 1Fh
0x18000a53d  jbe     loc_18000A678
0x18000a543  lea     edi, [rdx-1Fh]
0x18000a546  jmp     loc_18000A66F
0x18000a54b  sub     r11d, eax
0x18000a54e  mov     dil, dl
0x18000a551  sub     dil, r13b
0x18000a554  mov     cl, r11b
0x18000a557  shr     r8d, cl
0x18000a55a  inc     dil
0x18000a55d  add     [rbx], r8d
0x18000a560  add     dil, r15b
0x18000a563  jmp     loc_18000A678
0x18000a568  and     r9d, edi
0x18000a56b  add     r13, 4
0x18000a56f  sub     dl, al
0x18000a571  cmp     r10b, al
0x18000a574  jbe     short loc_18000A595
0x18000a576  inc     dl
0x18000a578  mov     eax, r9d
0x18000a57b  movzx   edi, dl
0x18000a57e  mov     ecx, edi
0x18000a580  shl     eax, cl
0x18000a582  mov     ecx, r8d
0x18000a585  add     [rbx], eax
0x18000a587  sub     ecx, edi
0x18000a589  add     rbx, 4
0x18000a58d  shr     r9d, cl
0x18000a590  mov     [rbx], r9d
0x18000a593  jmp     short loc_18000A5BA
0x18000a595  add     dl, 21h ; '!'
0x18000a598  movzx   eax, r10b
0x18000a59c  sub     r11d, eax
0x18000a59f  mov     dil, dl
0x18000a5a2  mov     cl, r11b
0x18000a5a5  shr     r9d, cl
0x18000a5a8  add     [rbx], r9d
0x18000a5ab  cmp     dl, 1Fh
0x18000a5ae  jbe     short loc_18000A5BF
0x18000a5b0  sub     dl, r8b
0x18000a5b3  mov     dil, dl
0x18000a5b6  add     rbx, 4
0x18000a5ba  mov     [rsp+2990h+var_2948], rbx
0x18000a5bf  cmp     r13, [rsp+2990h+var_2930]
0x18000a5c4  jnb     short loc_18000A62A
0x18000a5c6  cmp     rbx, r14
  ... truncated ...
```
