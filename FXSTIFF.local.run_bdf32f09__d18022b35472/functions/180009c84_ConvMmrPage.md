# ConvMmrPage

- ea: `0x180009c84`
- end: `0x18000a4bd`
- name: `ConvMmrPage`
- size: `2105`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000a4d0`
- `0x18000a500`
- `0x18000a530`

## callees

- `0x180009a7c`
- `0x180009aa4`
- `0x180009c84`
- `0x18000a69c`
- `0x18000a88c`
- `0x18000c1a4`
- `0x18000d93c`
- `0x180017bce`
- `0x180017c00`
- `0x180017c90`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000a379`
- `KERNEL32!SetLastError` at `0x18000a38e`
- `KERNEL32!SetLastError` at `0x18000a39e`
- `KERNEL32!SetLastError` at `0x18000a44d`
- `KERNEL32!SetLastError` at `0x18000a379`
- `KERNEL32!SetLastError` at `0x18000a38e`
- `KERNEL32!SetLastError` at `0x18000a39e`
- `KERNEL32!SetLastError` at `0x18000a44d`

## pseudocode

```c
__int64 __fastcall ConvMmrPage(__int64 a1, unsigned int *a2, unsigned int *a3, int a4, unsigned __int8 a5, int a6)
{
  _QWORD *v10; // rcx
  int v11; // esi
  int v12; // ebx
  __int64 v13; // rcx
  const wchar_t *v14; // r9
  size_t v15; // r8
  unsigned __int64 v16; // r14
  unsigned __int16 *v17; // r12
  unsigned int *v18; // rbx
  unsigned __int8 v19; // di
  unsigned __int64 v20; // rcx
  unsigned int v21; // r8d
  __int64 v22; // rax
  _DWORD *v23; // r13
  unsigned __int64 v24; // rdx
  unsigned __int16 *v25; // r15
  int v26; // ecx
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
  unsigned __int64 v49; // r8
  char v50; // r8
  unsigned int v51; // edx
  unsigned __int16 *v52; // rcx
  int v53; // r8d
  unsigned __int16 *v54; // rcx
  unsigned __int8 v55; // cl
  int v56; // eax
  char v57; // cl
  DWORD v59; // ecx
  _QWORD *v60; // rcx
  __int64 v61; // rdx
  _QWORD *v62; // rcx
  __int64 v63; // rdx
  unsigned __int8 v64; // [rsp+40h] [rbp-C0h] BYREF
  char v65; // [rsp+41h] [rbp-BFh]
  unsigned __int8 v66[6]; // [rsp+42h] [rbp-BEh] BYREF
  unsigned int *v67; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 *v68; // [rsp+50h] [rbp-B0h]
  int v69; // [rsp+58h] [rbp-A8h]
  _DWORD *v70; // [rsp+60h] [rbp-A0h] BYREF
  int v71; // [rsp+68h] [rbp-98h]
  unsigned int v72; // [rsp+6Ch] [rbp-94h]
  int v73; // [rsp+70h] [rbp-90h]
  _DWORD *v74; // [rsp+78h] [rbp-88h]
  unsigned __int64 v75; // [rsp+80h] [rbp-80h]
  unsigned int *v76; // [rsp+88h] [rbp-78h]
  _DWORD *v77; // [rsp+90h] [rbp-70h]
  _WORD v78[1736]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v79[1736]; // [rsp+E30h] [rbp+D30h] BYREF
  _BYTE v80[3472]; // [rsp+1BC0h] [rbp+1AC0h] BYREF

  v73 = a4;
  v77 = a3;
  v76 = a2;
  v71 = 0;
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
  v68 = v78;
  v16 = (unsigned __int64)&a2[v15 >> 2];
  if ( a4 != 3 || (v17 = v79, !v12) )
    v17 = (unsigned __int16 *)v80;
  v18 = a2;
  v67 = a2;
  v19 = 0;
  memset_0(a2, 0, v15);
  v20 = *(_QWORD *)(a1 + 1536);
  v21 = *(_DWORD *)(a1 + 1564);
  v22 = *(unsigned int *)(a1 + 1552);
  v23 = (_DWORD *)(v20 & 0xFFFFFFFFFFFFFFFCuLL);
  *(_QWORD *)(a1 + 1572) = 0;
  *(_QWORD *)(a1 + 1668) = 0;
  v24 = (v22 + v20 - 1) & 0xFFFFFFFFFFFFFFFCuLL;
  v72 = v21;
  LOBYTE(v20) = (8 * v20) & 0x18;
  v75 = v24;
  v74 = (_DWORD *)v20;
  v66[0] = v20;
  v70 = v23;
  v78[0] = v21;
  v69 = 1;
  v65 = 0;
  while ( 1 )
  {
    if ( (unsigned __int64)v18 >= v16 || (unsigned __int64)((__int64)(v16 - (_QWORD)v18) >> 2) < 4 )
    {
      SetLastError(0x7Au);
      v60 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 0;
      }
      v61 = 27;
      goto LABEL_127;
    }
    v25 = v68;
    v26 = ReadMrLine(&v70, v66, v68, (__int64)v17, v24, 1, v21);
    if ( !v26 )
    {
      v30 = ++v71;
      if ( v73 == 2 )
      {
        if ( a6 && (v30 & 1) == 0 )
        {
LABEL_40:
          v68 = v17;
          v17 = v25;
          goto LABEL_96;
        }
        if ( v19 <= 4u )
        {
          *v18 += 0x8000;
LABEL_37:
          v64 = 16;
          goto LABEL_38;
        }
        if ( v19 > 0xCu )
        {
          if ( v19 > 0x14u )
          {
            v31 = v18 + 1;
            v67 = v31;
            if ( v19 > 0x1Cu )
            {
              *v31 = 0x8000;
              goto LABEL_37;
            }
            *v31 = 128;
            v64 = 8;
          }
          else
          {
            *v18 += 0x80000000;
            v64 = 0;
            v67 = v18 + 1;
          }
        }
        else
        {
          *v18 += 0x800000;
          v64 = 24;
        }
LABEL_38:
        if ( !(unsigned int)OutputMhLine(v17, &v67, &v64, v16) )
          goto LABEL_116;
        v19 = v64;
        v18 = v67;
        goto LABEL_40;
      }
      if ( !a6 )
      {
        if ( v19 < 0x20u )
        {
          v32 = *((_BYTE *)gc_AlignEolTable + v19);
          if ( v32 < v19 )
            v67 = ++v18;
          v33 = 1 << v32;
          v34 = v32 + 1;
          *v18 += v33;
          if ( v34 == 32 )
          {
            ++v18;
            v34 = 0;
            v67 = v18;
          }
          v35 = v34 + 1;
          v36 = v66[0];
          if ( v69 )
          {
            v64 = v34 + 1;
            *v18 += 1 << v34;
            if ( !(unsigned int)OutputMhLine(v17, &v67, &v64, v16) )
              goto LABEL_116;
            v19 = v64;
            v18 = v67;
            v69 = 0;
            goto LABEL_78;
          }
          v37 = *v23;
          v38 = (char)v74;
          v39 = -1 << (char)v74;
          if ( v70 == v23 )
          {
            v23 = v74;
            v40 = v39 & v37 & (0xFFFFFFFF >> (32 - v66[0]));
            if ( v35 < (unsigned __int8)v74 )
            {
              v44 = v34 - (_BYTE)v74 + 1;
              *v18 += v40 >> ((_BYTE)v74 - v35);
              v19 = v36 + v44;
            }
            else
            {
              v41 = 31 - v34;
              v42 = v66[0] - (_BYTE)v74;
              *v18 += v40 << (v35 - (_BYTE)v74);
              if ( (unsigned __int8)(31 - v34) < (unsigned __int8)(v36 - (_BYTE)v23) )
              {
                ++v18;
                v19 = v42 - v41;
                *v18 = v40 >> (v38 + v41);
LABEL_75:
                v67 = v18;
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
          v46 = v34 - (_BYTE)v74;
          if ( v35 <= (unsigned __int8)v74 )
          {
            v47 = v46 + 33;
            v19 = v47;
            *v18 += v45 >> ((_BYTE)v74 - v35);
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
          v67 = v18;
LABEL_62:
          if ( v23 >= v70 )
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
            if ( (unsigned __int8)++v65 < a5 )
            {
LABEL_79:
              v52 = v68;
              LOBYTE(v23) = v36;
              v74 = v23;
              v23 = v70;
              v68 = v17;
              v17 = v52;
              goto LABEL_96;
            }
            v69 = 1;
LABEL_78:
            v65 = 0;
            goto LABEL_79;
          }
          while ( (unsigned __int64)v18 < v16 && (unsigned __int64)((__int64)(v16 - (_QWORD)v18) >> 2) >= 4 )
          {
            v48 = *v23;
            v49 = (unsigned __int64)(v23 + 1);
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
            v67 = v18;
            if ( v49 >= (unsigned __int64)v70 )
              goto LABEL_69;
          }
          SetLastError(0x7Au);
          v60 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v61 = 29;
LABEL_127:
            WPP_SF_d(
              v60[2],
              v61,
              &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids,
              (unsigned int)((__int64)(v16 - (_QWORD)v18) >> 2));
          }
          return 0;
        }
        v62 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_122;
        }
        v63 = 28;
        goto LABEL_121;
      }
      v53 = v30 & 3;
      if ( v53 == 2 )
      {
        v54 = v78;
        v17 = (unsigned __int16 *)v80;
      }
      else if ( (v30 & 3) != 0 )
      {
        if ( v19 >= 0x20u )
        {
          v62 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_122;
          }
          v63 = 30;
LABEL_121:
          WPP_SF_d(v62[2], v63, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids, v19);
LABEL_122:
          v59 = 1359;
          goto LABEL_107;
        }
        v55 = *((_BYTE *)gc_AlignEolTable + v19);
        if ( v55 < v19 )
          v67 = ++v18;
        v56 = 1 << v55;
        v57 = v55 + 1;
        *v18 += v56;
        if ( v57 == 32 )
        {
          ++v18;
          v57 = 0;
          v67 = v18;
        }
        v64 = v57 + 1;
        if ( v53 == 1 )
        {
          *v18 += 1 << v57;
          if ( !(unsigned int)OutputMhLine(v17, &v67, &v64, v16) )
            goto LABEL_116;
          v54 = v79;
        }
        else
        {
          if ( !(unsigned int)OutputMmrLine(v18, v57 + 1, v17, v79, &v67, &v64, v16, v72) )
          {
LABEL_116:
            v59 = 122;
LABEL_107:
            SetLastError(v59);
            return 0;
          }
          v54 = (unsigned __int16 *)v80;
        }
        v18 = v67;
        v17 = v78;
        v19 = v64;
      }
      else
      {
        v54 = v78;
        v17 = v79;
      }
      v68 = v54;
      goto LABEL_96;
    }
    v27 = v26 - 1;
    if ( !v27 || (v28 = v27 - 1) == 0 || (v29 = v28 - 1) == 0 )
    {
LABEL_106:
      v59 = 1392;
      goto LABEL_107;
    }
    if ( v29 == 1 )
      break;
LABEL_96:
    v24 = v75;
    if ( (unsigned __int64)v70 > v75 )
      goto LABEL_106;
    v21 = v72;
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
  *v77 = v11 + 4 * (v18 - v76);
  SetLastError(0);
  return 1;
}

```

## disassembly

```asm
0x180009c84  mov     [rsp-8+arg_18], rbx
0x180009c89  push    rbp
0x180009c8a  push    rsi
0x180009c8b  push    rdi
0x180009c8c  push    r12
0x180009c8e  push    r13
0x180009c90  push    r14
0x180009c92  push    r15
0x180009c94  lea     rbp, [rsp-2860h]
0x180009c9c  mov     eax, 2960h
0x180009ca1  call    _alloca_probe
0x180009ca6  sub     rsp, rax
0x180009ca9  mov     rax, cs:__security_cookie
0x180009cb0  xor     rax, rsp
0x180009cb3  mov     [rbp+2890h+var_40], rax
0x180009cba  mov     edi, r9d
0x180009cbd  mov     [rsp+2990h+var_2920], r9d
0x180009cc2  mov     r14, r8
0x180009cc5  mov     [rbp+2890h+var_2900], r8
0x180009cc9  mov     r13, rdx
0x180009ccc  mov     [rbp+2890h+var_2908], rdx
0x180009cd0  mov     r15, rcx
0x180009cd3  mov     [rsp+2990h+var_2928], 0
0x180009cdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ce2  lea     rbx, WPP_GLOBAL_Control
0x180009ce9  mov     esi, 2
0x180009cee  cmp     rcx, rbx
0x180009cf1  jz      short loc_180009D5E
0x180009cf3  test    [rcx+1Ch], sil
0x180009cf7  jz      short loc_180009D19
0x180009cf9  cmp     byte ptr [rcx+19h], 5
0x180009cfd  jb      short loc_180009D19
0x180009cff  mov     rcx, [rcx+10h]
0x180009d03  lea     edx, [rsi+17h]
0x180009d06  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x180009d0d  call    WPP_SF_
0x180009d12  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d19  cmp     rcx, rbx
0x180009d1c  jz      short loc_180009D5E
0x180009d1e  test    [rcx+1Ch], sil
0x180009d22  jz      short loc_180009D5E
0x180009d24  cmp     byte ptr [rcx+19h], 5
0x180009d28  mov     ebx, [rbp+2890h+arg_28]
0x180009d2e  jb      short loc_180009D64
0x180009d30  movzx   eax, [rbp+2890h+arg_20]
0x180009d37  lea     rdx, aMr; "MR"
0x180009d3e  mov     rcx, [rcx+10h]
0x180009d42  lea     r9, aMh; "MH"
0x180009d49  cmp     edi, esi
0x180009d4b  mov     dword ptr [rsp+2990h+var_2968], ebx
0x180009d4f  mov     dword ptr [rsp+2990h+var_2970], eax
0x180009d53  cmovnz  r9, rdx
0x180009d57  call    WPP_SF_Sdd
0x180009d5c  jmp     short loc_180009D64
0x180009d5e  mov     ebx, [rbp+2890h+arg_28]
0x180009d64  mov     r8d, [r14]; Size
0x180009d67  lea     rcx, [rbp+2890h+var_28F0]
0x180009d6b  mov     eax, r8d
0x180009d6e  mov     [rsp+2990h+var_2940], rcx
0x180009d73  shr     rax, 2
0x180009d77  lea     r14, ds:0[rax*4]
0x180009d7f  add     r14, r13
0x180009d82  cmp     edi, 3
0x180009d85  jnz     short loc_180009D92
0x180009d87  lea     r12, [rbp+2890h+var_1B60]
0x180009d8e  test    ebx, ebx
0x180009d90  jnz     short loc_180009D99
0x180009d92  lea     r12, [rbp+2890h+var_DD0]
0x180009d99  mov     rbx, r13
0x180009d9c  xor     edx, edx; Val
0x180009d9e  mov     rcx, r13; void *
0x180009da1  mov     [rsp+2990h+var_2948], rbx
0x180009da6  xor     dil, dil
0x180009da9  call    memset_0
0x180009dae  mov     rcx, [r15+600h]
0x180009db5  xor     r9d, r9d
0x180009db8  mov     r8d, [r15+61Ch]
0x180009dbf  mov     r13, rcx
0x180009dc2  mov     eax, [r15+610h]
0x180009dc9  and     r13, 0FFFFFFFFFFFFFFFCh
0x180009dcd  mov     [r15+624h], r9
0x180009dd4  lea     rdx, [rcx-1]
0x180009dd8  mov     [r15+684h], r9
0x180009ddf  add     rdx, rax
0x180009de2  shl     cl, 3
0x180009de5  and     rdx, 0FFFFFFFFFFFFFFFCh
0x180009de9  mov     [rsp+2990h+var_2924], r8d
0x180009dee  and     cl, 18h
0x180009df1  mov     [rbp+2890h+var_2910], rdx
0x180009df5  mov     [rsp+2990h+var_2918], rcx
0x180009dfa  mov     [rsp+2990h+var_294E], cl
0x180009dfe  mov     [rsp+2990h+var_2930], r13
0x180009e03  mov     [rbp+2890h+var_28F0], r8w
0x180009e08  mov     [rsp+2990h+var_2938], 1
0x180009e10  mov     [rsp+2990h+var_294F], r9b
0x180009e15  cmp     rbx, r14
0x180009e18  jnb     loc_18000A448
0x180009e1e  mov     rax, r14
0x180009e21  sub     rax, rbx
0x180009e24  sar     rax, 2
0x180009e28  cmp     rax, 4
0x180009e2c  jb      loc_18000A448
0x180009e32  mov     r15, [rsp+2990h+var_2940]
0x180009e37  lea     rcx, [rsp+2990h+var_2930]
0x180009e3c  mov     dword ptr [rsp+2990h+var_2960], r8d
0x180009e41  mov     r9, r12
0x180009e44  mov     dword ptr [rsp+2990h+var_2968], 1
0x180009e4c  mov     r8, r15
0x180009e4f  mov     [rsp+2990h+var_2970], rdx
0x180009e54  lea     rdx, [rsp+2990h+var_294E]
0x180009e59  call    ReadMrLine
0x180009e5e  xor     r9d, r9d
0x180009e61  mov     ecx, eax
0x180009e63  test    eax, eax
0x180009e65  jz      short loc_180009EA0
0x180009e67  sub     ecx, 1
0x180009e6a  jz      loc_18000A389
0x180009e70  sub     ecx, 1
0x180009e73  jz      loc_18000A389
0x180009e79  sub     ecx, 1
0x180009e7c  jz      loc_18000A389
0x180009e82  cmp     ecx, 1
0x180009e85  jnz     loc_18000A30C
0x180009e8b  cmp     dil, 4
0x180009e8f  ja      loc_18000A321
0x180009e95  add     dword ptr [rbx], 8000h
0x180009e9b  jmp     loc_18000A366
0x180009ea0  mov     eax, [rsp+2990h+var_2928]
0x180009ea4  mov     r11d, 1
0x180009eaa  add     eax, r11d
0x180009ead  mov     [rsp+2990h+var_2928], eax
0x180009eb1  cmp     [rsp+2990h+var_2920], esi
0x180009eb5  jnz     loc_180009F65
0x180009ebb  cmp     [rbp+2890h+arg_28], r9d
0x180009ec2  jz      short loc_180009ECD
0x180009ec4  test    r11b, al
0x180009ec7  jz      loc_180009F58
0x180009ecd  cmp     dil, 4
0x180009ed1  ja      short loc_180009EDB
0x180009ed3  add     dword ptr [rbx], 8000h
0x180009ed9  jmp     short loc_180009F2C
0x180009edb  cmp     dil, 0Ch
0x180009edf  ja      short loc_180009EEE
0x180009ee1  add     dword ptr [rbx], 800000h
0x180009ee7  mov     [rsp+2990h+var_2950], 18h
0x180009eec  jmp     short loc_180009F31
0x180009eee  cmp     dil, 14h
0x180009ef2  ja      short loc_180009F0A
0x180009ef4  add     dword ptr [rbx], 80000000h
0x180009efa  add     rbx, 4
0x180009efe  mov     [rsp+2990h+var_2950], r9b
0x180009f03  mov     [rsp+2990h+var_2948], rbx
0x180009f08  jmp     short loc_180009F31
0x180009f0a  add     rbx, 4
0x180009f0e  mov     [rsp+2990h+var_2948], rbx
0x180009f13  cmp     dil, 1Ch
0x180009f17  ja      short loc_180009F26
0x180009f19  mov     dword ptr [rbx], 80h
0x180009f1f  mov     [rsp+2990h+var_2950], 8
0x180009f24  jmp     short loc_180009F31
0x180009f26  mov     dword ptr [rbx], 8000h
0x180009f2c  mov     [rsp+2990h+var_2950], 10h
0x180009f31  mov     r9, r14
0x180009f34  lea     r8, [rsp+2990h+var_2950]
0x180009f39  lea     rdx, [rsp+2990h+var_2948]
0x180009f3e  mov     rcx, r12
0x180009f41  call    OutputMhLine
0x180009f46  test    eax, eax
0x180009f48  jz      loc_18000A3FF
0x180009f4e  mov     dil, [rsp+2990h+var_2950]
0x180009f53  mov     rbx, [rsp+2990h+var_2948]
0x180009f58  mov     [rsp+2990h+var_2940], r12
0x180009f5d  mov     r12, r15
0x180009f60  jmp     loc_18000A30C
0x180009f65  cmp     [rbp+2890h+arg_28], r9d
0x180009f6c  jnz     loc_18000A20B
0x180009f72  mov     r8d, 20h ; ' '
0x180009f78  cmp     dil, r8b
0x180009f7b  jnb     loc_18000A3D9
0x180009f81  movzx   eax, dil
0x180009f85  lea     rcx, gc_AlignEolTable
0x180009f8c  mov     dl, [rax+rcx]
0x180009f8f  cmp     dl, dil
0x180009f92  jnb     short loc_180009F9D
0x180009f94  add     rbx, 4
0x180009f98  mov     [rsp+2990h+var_2948], rbx
0x180009f9d  mov     cl, dl
0x180009f9f  mov     eax, r11d
0x180009fa2  shl     eax, cl
0x180009fa4  add     dl, r11b
0x180009fa7  add     [rbx], eax
0x180009fa9  cmp     dl, r8b
0x180009fac  jnz     short loc_180009FBA
0x180009fae  add     rbx, 4
0x180009fb2  mov     dl, r9b
0x180009fb5  mov     [rsp+2990h+var_2948], rbx
0x180009fba  lea     r10d, [r11+rdx]
0x180009fbe  movzx   r15d, [rsp+2990h+var_294E]
0x180009fc4  cmp     [rsp+2990h+var_2938], r9d
0x180009fc9  jz      short loc_18000A00D
0x180009fcb  mov     cl, dl
0x180009fcd  mov     [rsp+2990h+var_2950], r10b
0x180009fd2  mov     eax, r11d
0x180009fd5  lea     r8, [rsp+2990h+var_2950]
0x180009fda  shl     eax, cl
0x180009fdc  lea     rdx, [rsp+2990h+var_2948]
0x180009fe1  add     [rbx], eax
0x180009fe3  mov     rcx, r12
0x180009fe6  mov     r9, r14
0x180009fe9  call    OutputMhLine
0x180009fee  test    eax, eax
0x180009ff0  jz      loc_18000A3FF
0x180009ff6  mov     dil, [rsp+2990h+var_2950]
0x180009ffb  mov     rbx, [rsp+2990h+var_2948]
0x18000a000  mov     [rsp+2990h+var_2938], 0
0x18000a008  jmp     loc_18000A1E6
0x18000a00d  mov     rax, [rsp+2990h+var_2918]
0x18000a012  or      edi, 0FFFFFFFFh
0x18000a015  mov     r9d, [r13+0]
0x18000a019  movzx   r11d, al
0x18000a01d  mov     ecx, r11d
0x18000a020  shl     edi, cl
0x18000a022  cmp     [rsp+2990h+var_2930], r13
0x18000a027  jnz     loc_18000A0BC
0x18000a02d  mov     r13, [rsp+2990h+var_2918]
0x18000a032  mov     ecx, r8d
0x18000a035  or      r8d, 0FFFFFFFFh
0x18000a039  movzx   eax, r10b
0x18000a03d  sub     ecx, r15d
0x18000a040  shr     r8d, cl
0x18000a043  and     r8d, r9d
0x18000a046  and     r8d, edi
0x18000a049  cmp     r10b, r13b
0x18000a04c  jb      short loc_18000A09F
0x18000a04e  sub     eax, r11d
0x18000a051  mov     r9d, 1Fh
0x18000a057  mov     cl, al
0x18000a059  mov     dil, r15b
0x18000a05c  mov     eax, r8d
0x18000a05f  sub     r9b, dl
0x18000a062  shl     eax, cl
0x18000a064  sub     dil, r13b
0x18000a067  add     [rbx], eax
0x18000a069  cmp     r9b, dil
0x18000a06c  jnb     short loc_18000A087
0x18000a06e  add     rbx, 4
0x18000a072  movzx   ecx, r9b
0x18000a076  add     ecx, r11d
0x18000a079  shr     r8d, cl
0x18000a07c  sub     dil, r9b
0x18000a07f  mov     [rbx], r8d
0x18000a082  jmp     loc_18000A1C7
0x18000a087  add     dl, dil
0x18000a08a  lea     edi, [rdx+1]
0x18000a08d  cmp     dil, 1Fh
0x18000a091  jbe     loc_18000A1CC
0x18000a097  lea     edi, [rdx-1Fh]
0x18000a09a  jmp     loc_18000A1C3
0x18000a09f  sub     r11d, eax
0x18000a0a2  mov     dil, dl
0x18000a0a5  sub     dil, r13b
0x18000a0a8  mov     cl, r11b
0x18000a0ab  shr     r8d, cl
0x18000a0ae  inc     dil
0x18000a0b1  add     [rbx], r8d
0x18000a0b4  add     dil, r15b
0x18000a0b7  jmp     loc_18000A1CC
0x18000a0bc  and     r9d, edi
0x18000a0bf  add     r13, 4
0x18000a0c3  sub     dl, al
0x18000a0c5  cmp     r10b, al
0x18000a0c8  jbe     short loc_18000A0E9
0x18000a0ca  inc     dl
0x18000a0cc  mov     eax, r9d
0x18000a0cf  movzx   edi, dl
0x18000a0d2  mov     ecx, edi
0x18000a0d4  shl     eax, cl
0x18000a0d6  mov     ecx, r8d
0x18000a0d9  add     [rbx], eax
0x18000a0db  sub     ecx, edi
0x18000a0dd  add     rbx, 4
0x18000a0e1  shr     r9d, cl
0x18000a0e4  mov     [rbx], r9d
0x18000a0e7  jmp     short loc_18000A10E
0x18000a0e9  add     dl, 21h ; '!'
0x18000a0ec  movzx   eax, r10b
0x18000a0f0  sub     r11d, eax
0x18000a0f3  mov     dil, dl
0x18000a0f6  mov     cl, r11b
0x18000a0f9  shr     r9d, cl
0x18000a0fc  add     [rbx], r9d
0x18000a0ff  cmp     dl, 1Fh
0x18000a102  jbe     short loc_18000A113
0x18000a104  sub     dl, r8b
0x18000a107  mov     dil, dl
0x18000a10a  add     rbx, 4
0x18000a10e  mov     [rsp+2990h+var_2948], rbx
0x18000a113  cmp     r13, [rsp+2990h+var_2930]
0x18000a118  jnb     short loc_18000A17E
0x18000a11a  cmp     rbx, r14
  ... truncated ...
```
