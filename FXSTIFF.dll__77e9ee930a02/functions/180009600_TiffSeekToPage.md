# TiffSeekToPage

- ea: `0x180009600`
- end: `0x180009c48`
- name: `TiffSeekToPage`
- size: `1608`
- prototype: `__int64 __fastcall(__int64, unsigned int, int)`
- caller_count: `7`
- callee_count: `8`
- tags: ``

## callers

- `0x180004540`
- `0x180005ed0`
- `0x1800066d0`
- `0x180008b70`
- `0x18000b120`
- `0x18000bb50`
- `0x18000e784`

## callees

- `0x1800051cc`
- `0x180009600`
- `0x180009f04`
- `0x18000a070`
- `0x18000f128`
- `0x18000f1c8`
- `0x180018992`
- `0x18001899e`

## import_xrefs

- `KERNEL32!VirtualAlloc` at `0x180009aae`
- `KERNEL32!VirtualAlloc` at `0x180009aae`
- `KERNEL32!VirtualFree` at `0x180009a8e`
- `KERNEL32!VirtualFree` at `0x180009a8e`

## pseudocode

```c
__int64 __fastcall TiffSeekToPage(__int64 a1, unsigned int a2, int a3)
{
  __int64 v5; // rcx
  _QWORD *v6; // r12
  __int64 v7; // r9
  int v8; // r8d
  __int64 v9; // r10
  __int64 v10; // r11
  _DWORD *v11; // r14
  unsigned int v12; // r15d
  __int64 v13; // r13
  __int64 v14; // r10
  unsigned __int16 v15; // dx
  __int64 v16; // r8
  unsigned __int16 *v17; // rdi
  unsigned int v18; // eax
  __int64 v19; // r9
  unsigned int v20; // esi
  unsigned int *v21; // rbp
  unsigned int v22; // ecx
  unsigned int v23; // esi
  __int64 v24; // rbp
  unsigned __int64 v25; // rcx
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rdx
  unsigned __int64 v28; // rdx
  unsigned int v29; // ecx
  unsigned int v30; // edi
  unsigned int v31; // edx
  void *v32; // rcx
  LPVOID v33; // rax
  char *v35; // rdi
  unsigned int v36; // ebp
  unsigned int v37; // r9d
  char *v38; // rdx
  char *v39; // r8
  __int64 j; // r8
  unsigned int i; // [rsp+30h] [rbp-58h]
  __int64 v42; // [rsp+38h] [rbp-50h]
  unsigned __int16 v43; // [rsp+90h] [rbp+8h]
  int v46; // [rsp+A8h] [rbp+20h] BYREF

  v46 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
  }
  if ( a2 > *(_DWORD *)(a1 + 836) )
    return 0;
  if ( a2 == *(_DWORD *)(a1 + 1528) + 1 )
  {
    v5 = *(unsigned int *)(a1 + 844);
    v6 = (_QWORD *)(a1 + 16);
    LOWORD(v7) = *(_WORD *)(v5 + *(_QWORD *)(a1 + 16));
  }
  else
  {
    LODWORD(v5) = *(_DWORD *)(a1 + 568);
    if ( !(_DWORD)v5 )
      return 0;
    v8 = 0;
    v9 = *(_QWORD *)(a1 + 16);
    do
    {
      ++v8;
      v6 = (_QWORD *)(a1 + 16);
      v7 = *(unsigned __int16 *)((unsigned int)v5 + v9);
      if ( v8 == a2 )
        break;
      LODWORD(v5) = *(_DWORD *)((unsigned int)v5 + 12 * v7 + v9 + 2);
    }
    while ( (_DWORD)v5 );
  }
  if ( !(_DWORD)v5 )
    return 0;
  v10 = a1 + 1628;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = (unsigned int)v5 + *v6 + 2LL;
  v42 = v14;
  v15 = 0;
  v16 = a1 + 1624;
  *(_DWORD *)(a1 + 844) = *(_DWORD *)((unsigned int)v5 + 12LL * (unsigned __int16)v7 + *v6 + 2);
  *(_DWORD *)(a1 + 1628) = 1;
  *(_DWORD *)(a1 + 1624) = 0;
  for ( i = (unsigned __int16)v7; (unsigned int)v13 < i; v13 = (unsigned int)(v13 + 1) )
  {
    v17 = (unsigned __int16 *)(v14 + 12 * v13);
    v18 = *v17;
    v43 = v18;
    if ( (unsigned __int16)v18 < v15 )
      goto LABEL_74;
    if ( v18 > 0x111 )
    {
      if ( v18 == 278 )
      {
        *(_QWORD *)(a1 + 1640) = v17;
        v19 = a1 + 1556;
        goto LABEL_64;
      }
      if ( v18 != 279 )
      {
        if ( v18 == 282 )
        {
          v19 = a1 + 1688;
        }
        else
        {
          if ( v18 != 283 )
          {
            if ( v18 == 292 )
            {
              if ( !(unsigned int)GetTagData(a1, 0, v14 + 12 * v13, &v46) )
                goto LABEL_74;
              v16 = a1 + 1624;
              v14 = v42;
              v10 = a1 + 1628;
              if ( (v46 & 1) != 0 )
              {
                if ( *(_DWORD *)(a1 + 852) != 4 )
                  *(_DWORD *)(a1 + 852) = 3;
              }
              else if ( (v46 & 2) != 0 )
              {
                *(_DWORD *)(a1 + 852) = 1;
              }
            }
            goto LABEL_66;
          }
          v19 = a1 + 1684;
        }
        goto LABEL_64;
      }
      if ( !v11 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids);
        }
        return 0;
      }
      if ( v12 != *((_DWORD *)v17 + 1) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            &WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids,
            v12,
            *((_DWORD *)v17 + 1));
        }
        goto LABEL_75;
      }
      v23 = 0;
      *(_QWORD *)(a1 + 1648) = v17;
      if ( *((_DWORD *)v17 + 1) )
      {
        while ( 1 )
        {
          v24 = 4LL * v23;
          if ( !(unsigned int)GetTagData(a1, v23, v17, &v11[v24 + 1]) )
            goto LABEL_75;
          v25 = (unsigned int)v11[v24 + 1];
          v26 = *(unsigned int *)(a1 + 1664);
          v27 = v25 + (unsigned int)v11[4 * v23];
          if ( v27 > v26 )
          {
            v28 = v27 - v26;
            if ( v28 >= v25 )
              goto LABEL_75;
            v11[v24 + 1] = v25 - v28;
          }
          if ( ++v23 >= *((_DWORD *)v17 + 1) )
            goto LABEL_65;
        }
      }
    }
    else
    {
      switch ( v18 )
      {
        case 0x111u:
          v12 = *((_DWORD *)v17 + 1);
          if ( v12 > 0x2FAF08 )
            goto LABEL_74;
          v11 = (_DWORD *)pMemAlloc(16LL * v12);
          if ( !v11 )
            return 0;
          v20 = 0;
          if ( *((_DWORD *)v17 + 1) )
          {
            while ( 1 )
            {
              v21 = &v11[4 * v20];
              if ( !(unsigned int)GetTagData(a1, v20, v17, v21) )
                goto LABEL_75;
              v22 = *v21;
              *((_QWORD *)v21 + 1) = *v6 + *v21;
              ++v20;
              *(_DWORD *)(a1 + 1560) = v22;
              if ( v20 >= *((_DWORD *)v17 + 1) )
                goto LABEL_65;
            }
          }
          goto LABEL_65;
        case 0x100u:
          if ( !(unsigned int)GetTagData(a1, 0, v14 + 12 * v13, a1 + 1564) )
            goto LABEL_74;
          *(_DWORD *)(a1 + 1692) = (*(_DWORD *)(a1 + 1564) >> 3) + ((*(_DWORD *)(a1 + 1564) & 7) != 0);
          goto LABEL_65;
        case 0x101u:
          *(_QWORD *)(a1 + 1632) = v17;
          v19 = a1 + 1568;
          goto LABEL_64;
        case 0x103u:
          if ( !(unsigned int)GetTagData(a1, 0, v14 + 12 * v13, &v46) )
            goto LABEL_74;
          switch ( v46 )
          {
            case 1:
              *(_DWORD *)(a1 + 852) = 1;
              break;
            case 2:
            case 3:
              *(_DWORD *)(a1 + 852) = 2;
              break;
            case 4:
              *(_DWORD *)(a1 + 852) = 4;
              break;
            default:
              goto LABEL_74;
          }
LABEL_65:
          v14 = v42;
          v10 = a1 + 1628;
          v16 = a1 + 1624;
          break;
        case 0x106u:
          v19 = v16;
LABEL_64:
          if ( !(unsigned int)GetTagData(a1, 0, v14 + 12 * v13, v19) )
            goto LABEL_74;
          goto LABEL_65;
        case 0x10Au:
          *(_QWORD *)(a1 + 1656) = v17;
          v19 = v10;
          goto LABEL_64;
      }
    }
LABEL_66:
    v15 = v43;
  }
  v29 = 0;
  v30 = 0;
  if ( v12 )
  {
    while ( 1 )
    {
      v31 = v30 + v11[4 * v29 + 1];
      if ( v31 < v30 )
        break;
      ++v29;
      v30 = v31;
      if ( v29 >= v12 )
        goto LABEL_70;
    }
LABEL_74:
    if ( v11 )
LABEL_75:
      pMemFree(v11);
    return 0;
  }
LABEL_70:
  v32 = *(void **)(a1 + 1536);
  if ( v30 < *(_DWORD *)(a1 + 1552) )
  {
    if ( v32 )
      memset_0(v32, 0, *(unsigned int *)(a1 + 1552));
  }
  else
  {
    if ( v32 )
      VirtualFree(v32, 0, 0x8000u);
    *(_DWORD *)(a1 + 1552) = v30;
    v33 = VirtualAlloc(0, v30, 0x1000u, 4u);
    *(_QWORD *)(a1 + 1536) = v33;
    if ( !v33 )
      goto LABEL_74;
  }
  v35 = *(char **)(a1 + 1536);
  v36 = 0;
  if ( v12 )
  {
    do
    {
      v37 = v11[4 * v36 + 1];
      if ( v37 )
      {
        v38 = *(char **)&v11[4 * v36 + 2];
        v39 = &v38[v37 - 1];
        if ( v39 < v38 || (unsigned __int64)v39 < *v6 || (unsigned __int64)&v39[-*v6] > *(unsigned int *)(a1 + 1664) )
          goto LABEL_74;
        memcpy_0(v35, v38, v37);
        v35 += (unsigned int)v11[4 * v36 + 1];
      }
      ++v36;
    }
    while ( v36 < v12 );
    v35 = *(char **)(a1 + 1536);
  }
  if ( *(_DWORD *)(a1 + 1628) != a3 )
  {
    for ( j = 0; (unsigned int)j < *(_DWORD *)(a1 + 1552); j = (unsigned int)(j + 1) )
      v35[j] = *((_BYTE *)qword_18001B800 + (unsigned __int8)v35[j]);
  }
  *(_QWORD *)(a1 + 1544) = *(_QWORD *)(a1 + 1536);
  *(_DWORD *)(a1 + 1528) = a2;
  pMemFree(v11);
  return 1;
}

```

## disassembly

```asm
0x180009600  mov     rax, rsp
0x180009603  mov     [rax+18h], r8d
0x180009607  mov     [rax+10h], edx
0x18000960a  push    rbx
0x18000960b  push    rbp
0x18000960c  push    rsi
0x18000960d  push    rdi
0x18000960e  push    r12
0x180009610  push    r13
0x180009612  push    r14
0x180009614  push    r15
0x180009616  sub     rsp, 48h
0x18000961a  mov     edi, edx
0x18000961c  mov     dword ptr [rax+20h], 0
0x180009623  mov     rbx, rcx
0x180009626  mov     rcx, cs:WPP_GLOBAL_Control
0x18000962d  lea     rsi, WPP_GLOBAL_Control
0x180009634  cmp     rcx, rsi
0x180009637  jz      short loc_18000965A
0x180009639  test    byte ptr [rcx+1Ch], 2
0x18000963d  jz      short loc_18000965A
0x18000963f  cmp     byte ptr [rcx+19h], 5
0x180009643  jb      short loc_18000965A
0x180009645  mov     rcx, [rcx+10h]
0x180009649  lea     r8, WPP_bf8091a3347330f76d15a5eedab08f37_Traceguids
0x180009650  mov     edx, 12h
0x180009655  call    WPP_SF_
0x18000965a  cmp     edi, [rbx+344h]
0x180009660  ja      loc_180009AD7
0x180009666  mov     eax, [rbx+5F8h]
0x18000966c  mov     ebp, 1
0x180009671  add     eax, ebp
0x180009673  cmp     edi, eax
0x180009675  jnz     short loc_18000968C
0x180009677  mov     ecx, [rbx+34Ch]
0x18000967d  lea     r12, [rbx+10h]
0x180009681  mov     rax, [r12]
0x180009685  movzx   r9d, word ptr [rcx+rax]
0x18000968a  jmp     short loc_1800096C8
0x18000968c  mov     ecx, [rbx+238h]
0x180009692  test    ecx, ecx
0x180009694  jz      loc_180009AD7
0x18000969a  lea     rdx, [rbx+10h]
0x18000969e  xor     r8d, r8d
0x1800096a1  mov     r10, [rdx]
0x1800096a4  mov     r11d, ecx
0x1800096a7  add     r8d, ebp
0x1800096aa  mov     r12, rdx
0x1800096ad  movzx   r9d, word ptr [r11+r10]
0x1800096b2  cmp     r8d, edi
0x1800096b5  jz      short loc_1800096C8
0x1800096b7  lea     rcx, [r9+r9*2]
0x1800096bb  lea     rax, [r11+rcx*4]
0x1800096bf  mov     ecx, [rax+r10+2]
0x1800096c4  test    ecx, ecx
0x1800096c6  jnz     short loc_1800096A4
0x1800096c8  test    ecx, ecx
0x1800096ca  jz      loc_180009AD7
0x1800096d0  mov     r8, [r12]
0x1800096d4  lea     r11, [rbx+65Ch]
0x1800096db  mov     edx, ecx
0x1800096dd  xor     r14d, r14d
0x1800096e0  movzx   eax, r9w
0x1800096e4  xor     r15d, r15d
0x1800096e7  xor     r13d, r13d
0x1800096ea  lea     r10, [r8+2]
0x1800096ee  add     r10, rdx
0x1800096f1  lea     rcx, [rax+rax*2]
0x1800096f5  mov     [rsp+88h+var_50], r10
0x1800096fa  lea     rax, [rdx+rcx*4]
0x1800096fe  xor     edx, edx
0x180009700  mov     ecx, [rax+r8+2]
0x180009705  lea     r8, [rbx+658h]
0x18000970c  movzx   eax, r9w
0x180009710  mov     [rbx+34Ch], ecx
0x180009716  mov     [r11], ebp
0x180009719  mov     [r8], r14d
0x18000971c  mov     [rsp+88h+var_58], eax
0x180009720  test    eax, eax
0x180009722  jz      loc_180009A4A
0x180009728  lea     rcx, ds:0[r13*2]
0x180009730  add     rcx, r13
0x180009733  lea     rdi, [r10+rcx*4]
0x180009737  movzx   eax, word ptr [rdi]
0x18000973a  mov     [rsp+88h+arg_0], ax
0x180009742  cmp     ax, dx
0x180009745  jb      loc_180009ACA
0x18000974b  mov     ecx, eax
0x18000974d  cmp     eax, 111h
0x180009752  ja      loc_1800098CA
0x180009758  jz      loc_180009851
0x18000975e  sub     ecx, 100h
0x180009764  jz      loc_180009815
0x18000976a  sub     ecx, 1
0x18000976d  jz      loc_180009802
0x180009773  sub     ecx, 2
0x180009776  jz      short loc_18000979D
0x180009778  sub     ecx, 3
0x18000977b  jz      short loc_180009795
0x18000977d  cmp     ecx, 4
0x180009780  jnz     loc_180009A34
0x180009786  mov     [rbx+678h], rdi
0x18000978d  mov     r9, r11
0x180009790  jmp     loc_180009A0C
0x180009795  mov     r9, r8
0x180009798  jmp     loc_180009A0C
0x18000979d  lea     r9, [rsp+88h+arg_18]
0x1800097a5  mov     r8, rdi
0x1800097a8  xor     edx, edx
0x1800097aa  mov     rcx, rbx
0x1800097ad  call    GetTagData
0x1800097b2  test    eax, eax
0x1800097b4  jz      loc_180009ACA
0x1800097ba  mov     eax, [rsp+88h+arg_18]
0x1800097c1  sub     eax, 1
0x1800097c4  jz      short loc_1800097F7
0x1800097c6  sub     eax, 1
0x1800097c9  jz      short loc_1800097E8
0x1800097cb  sub     eax, 1
0x1800097ce  jz      short loc_1800097E8
0x1800097d0  cmp     eax, 1
0x1800097d3  jnz     loc_180009ACA
0x1800097d9  mov     dword ptr [rbx+354h], 4
0x1800097e3  jmp     loc_180009A21
0x1800097e8  mov     dword ptr [rbx+354h], 2
0x1800097f2  jmp     loc_180009A21
0x1800097f7  mov     [rbx+354h], ebp
0x1800097fd  jmp     loc_180009A21
0x180009802  mov     [rbx+660h], rdi
0x180009809  lea     r9, [rbx+620h]
0x180009810  jmp     loc_180009A0C
0x180009815  lea     rsi, [rbx+61Ch]
0x18000981c  mov     r8, rdi
0x18000981f  mov     r9, rsi
0x180009822  xor     edx, edx
0x180009824  mov     rcx, rbx
0x180009827  call    GetTagData
0x18000982c  test    eax, eax
0x18000982e  jz      loc_180009ACA
0x180009834  mov     ecx, [rsi]
0x180009836  mov     eax, 0
0x18000983b  test    cl, 7
0x18000983e  setnz   al
0x180009841  shr     ecx, 3
0x180009844  add     eax, ecx
0x180009846  mov     [rbx+69Ch], eax
0x18000984c  jmp     loc_180009A21
0x180009851  mov     r15d, [rdi+4]
0x180009855  cmp     r15d, 2FAF08h
0x18000985c  ja      loc_180009ACA
0x180009862  mov     ecx, r15d
0x180009865  shl     rcx, 4; dwBytes
0x180009869  call    pMemAlloc
0x18000986e  mov     r14, rax
0x180009871  test    rax, rax
0x180009874  jz      loc_180009AD7
0x18000987a  xor     esi, esi
0x18000987c  cmp     [rdi+4], esi
0x18000987f  jbe     loc_180009A21
0x180009885  mov     ebp, esi
0x180009887  mov     r8, rdi
0x18000988a  shl     rbp, 4
0x18000988e  mov     edx, esi
0x180009890  add     rbp, r14
0x180009893  mov     rcx, rbx
0x180009896  mov     r9, rbp
0x180009899  call    GetTagData
0x18000989e  test    eax, eax
0x1800098a0  jz      loc_180009ACF
0x1800098a6  mov     ecx, [rbp+0]
0x1800098a9  mov     eax, ecx
0x1800098ab  add     rax, [r12]
0x1800098af  mov     [rbp+8], rax
0x1800098b3  mov     ebp, 1
0x1800098b8  add     esi, ebp
0x1800098ba  mov     [rbx+618h], ecx
0x1800098c0  cmp     esi, [rdi+4]
0x1800098c3  jb      short loc_180009885
0x1800098c5  jmp     loc_180009A21
0x1800098ca  sub     ecx, 116h
0x1800098d0  jz      loc_1800099FE
0x1800098d6  sub     ecx, 1
0x1800098d9  jz      loc_18000997D
0x1800098df  sub     ecx, 3
0x1800098e2  jz      loc_180009971
0x1800098e8  sub     ecx, 1
0x1800098eb  jz      short loc_180009965
0x1800098ed  cmp     ecx, 9
0x1800098f0  jnz     loc_180009A34
0x1800098f6  lea     r9, [rsp+88h+arg_18]
0x1800098fe  mov     r8, rdi
0x180009901  xor     edx, edx
0x180009903  mov     rcx, rbx
0x180009906  call    GetTagData
0x18000990b  test    eax, eax
0x18000990d  jz      loc_180009ACA
0x180009913  lea     r8, [rbx+658h]
0x18000991a  mov     r10, [rsp+88h+var_50]
0x18000991f  lea     r11, [rbx+65Ch]
0x180009926  test    byte ptr [rsp+88h+arg_18], bpl
0x18000992e  jz      short loc_18000994C
0x180009930  cmp     dword ptr [rbx+354h], 4
0x180009937  jz      loc_180009A34
0x18000993d  mov     dword ptr [rbx+354h], 3
0x180009947  jmp     loc_180009A34
0x18000994c  test    byte ptr [rsp+88h+arg_18], 2
0x180009954  jz      loc_180009A34
0x18000995a  mov     [rbx+354h], ebp
0x180009960  jmp     loc_180009A34
0x180009965  lea     r9, [rbx+694h]
0x18000996c  jmp     loc_180009A0C
0x180009971  lea     r9, [rbx+698h]
0x180009978  jmp     loc_180009A0C
0x18000997d  test    r14, r14
0x180009980  jz      loc_180009B28
0x180009986  mov     eax, [rdi+4]
0x180009989  cmp     r15d, eax
0x18000998c  jnz     loc_180009AEB
0x180009992  xor     esi, esi
0x180009994  mov     [rbx+670h], rdi
0x18000999b  cmp     [rdi+4], esi
0x18000999e  jbe     loc_180009A34
0x1800099a4  mov     ebp, esi
0x1800099a6  mov     r8, rdi
0x1800099a9  shl     rbp, 4
0x1800099ad  mov     edx, esi
0x1800099af  mov     rcx, rbx
0x1800099b2  lea     r9, [rbp+4]
0x1800099b6  add     r9, r14
0x1800099b9  call    GetTagData
0x1800099be  test    eax, eax
0x1800099c0  jz      loc_180009ACF
0x1800099c6  mov     ecx, [r14+rbp+4]
0x1800099cb  mov     edx, [r14+rbp]
0x1800099cf  mov     eax, [rbx+680h]
0x1800099d5  add     rdx, rcx
0x1800099d8  cmp     rdx, rax
0x1800099db  jbe     short loc_1800099F0
0x1800099dd  sub     rdx, rax
0x1800099e0  cmp     rdx, rcx
0x1800099e3  jnb     loc_180009ACF
0x1800099e9  sub     ecx, edx
0x1800099eb  mov     [r14+rbp+4], ecx
0x1800099f0  mov     ebp, 1
0x1800099f5  add     esi, ebp
0x1800099f7  cmp     esi, [rdi+4]
0x1800099fa  jb      short loc_1800099A4
0x1800099fc  jmp     short loc_180009A21
0x1800099fe  mov     [rbx+668h], rdi
0x180009a05  lea     r9, [rbx+614h]
0x180009a0c  mov     r8, rdi
0x180009a0f  xor     edx, edx
0x180009a11  mov     rcx, rbx
0x180009a14  call    GetTagData
0x180009a19  test    eax, eax
0x180009a1b  jz      loc_180009ACA
0x180009a21  mov     r10, [rsp+88h+var_50]
0x180009a26  lea     r11, [rbx+65Ch]
0x180009a2d  lea     r8, [rbx+658h]
0x180009a34  movzx   edx, [rsp+88h+arg_0]
0x180009a3c  add     r13d, ebp
0x180009a3f  cmp     r13d, [rsp+88h+var_58]
0x180009a44  jb      loc_180009728
0x180009a4a  xor     ecx, ecx
0x180009a4c  xor     edi, edi
0x180009a4e  test    r15d, r15d
0x180009a51  jz      short loc_180009A6C
0x180009a53  mov     eax, ecx
0x180009a55  add     rax, rax
0x180009a58  mov     edx, [r14+rax*8+4]
0x180009a5d  add     edx, edi
0x180009a5f  cmp     edx, edi
0x180009a61  jb      short loc_180009ACA
0x180009a63  add     ecx, ebp
0x180009a65  mov     edi, edx
0x180009a67  cmp     ecx, r15d
0x180009a6a  jb      short loc_180009A53
0x180009a6c  mov     eax, [rbx+610h]
0x180009a72  mov     rcx, [rbx+600h]; void *
0x180009a79  cmp     edi, eax
0x180009a7b  jb      loc_180009B61
0x180009a81  test    rcx, rcx
0x180009a84  jz      short loc_180009A9A
0x180009a86  xor     edx, edx; dwSize
0x180009a88  mov     r8d, 8000h; dwFreeType
0x180009a8e  call    cs:__imp_VirtualFree
0x180009a95  nop     dword ptr [rax+rax+00h]
0x180009a9a  xor     ecx, ecx; lpAddress
0x180009a9c  mov     edx, edi; dwSize
0x180009a9e  mov     r8d, 1000h; flAllocationType
0x180009aa4  mov     [rbx+610h], edi
0x180009aaa  lea     r9d, [rcx+4]; flProtect
0x180009aae  call    cs:__imp_VirtualAlloc
0x180009ab5  nop     dword ptr [rax+rax+00h]
0x180009aba  mov     [rbx+600h], rax
0x180009ac1  test    rax, rax
0x180009ac4  jnz     loc_180009B70
0x180009aca  test    r14, r14
0x180009acd  jz      short loc_180009AD7
0x180009acf  mov     rcx, r14; lpMem
  ... truncated ...
```
