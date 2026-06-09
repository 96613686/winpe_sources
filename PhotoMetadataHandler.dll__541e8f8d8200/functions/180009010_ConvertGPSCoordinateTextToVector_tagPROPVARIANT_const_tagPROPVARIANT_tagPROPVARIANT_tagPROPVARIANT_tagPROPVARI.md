# ConvertGPSCoordinateTextToVector(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x180009010`
- end: `0x180009533`
- name: `?ConvertGPSCoordinateTextToVector@@YAJPEBUtagPROPVARIANT@@PEAU1@111@Z`
- size: `1315`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, PROPVARIANT *pvar, PROPVARIANT *, PROPVARIANT *, PROPVARIANT *)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003970`
- `0x180007250`
- `0x180011c48`
- `0x180012440`
- `0x18001b1fc`

## callees

- `0x180009010`
- `0x1800169b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x1800092b3`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x180009309`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x180009419`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x1800092b3`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x180009309`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x180009419`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800092c5`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000942f`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800092c5`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18000942f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1800092a7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180009300`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180009408`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180009470`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1800092a7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180009300`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180009408`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180009470`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180009076`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180009076`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009036`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000903f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009048`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009059`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009113`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800094df`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009036`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000903f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009048`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009059`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009113`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800094df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009139`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000917f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800091c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000920e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009139`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000917f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800091c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000920e`

## pseudocode

```c
__int64 __fastcall ConvertGPSCoordinateTextToVector(
        PROPVARIANT *pvarSrc,
        PROPVARIANT *pvar,
        PROPVARIANT *a3,
        PROPVARIANT *a4,
        PROPVARIANT *pvara)
{
  HRESULT v9; // ebx
  BSTR bstrVal; // rax
  __int64 v11; // rcx
  int v12; // r13d
  unsigned int v13; // esi
  unsigned __int64 v14; // rdx
  __int16 v15; // bp
  BYTE *v17; // rax
  BYTE *v18; // rax
  BYTE *v19; // rax
  BYTE *v20; // rax
  wchar_t *v21; // r10
  int v22; // r8d
  int v23; // r9d
  wchar_t *v24; // rcx
  wchar_t v25; // dx
  int v26; // eax
  int v27; // eax
  wchar_t *v28; // rbx
  wchar_t *v29; // rax
  double v30; // xmm0_8
  BYTE *pData; // rax
  double v32; // xmm0_8
  wchar_t *v33; // rsi
  PROPVARIANT pvarDest; // [rsp+28h] [rbp-40h] BYREF

  PropVariantClear(pvar);
  PropVariantClear(a3);
  PropVariantClear(a4);
  PropVariantClear(pvara);
  memset(&pvarDest, 0, sizeof(pvarDest));
  v9 = PropVariantCopy(&pvarDest, pvarSrc);
  if ( v9 < 0 )
    goto LABEL_13;
  if ( pvarDest.hVal.QuadPart )
  {
    bstrVal = pvarDest.bstrVal;
    v11 = 0x7FFFFFFF;
    do
    {
      if ( !*bstrVal )
        break;
      ++bstrVal;
      --v11;
    }
    while ( v11 );
    v12 = 0;
    v9 = -2147024809;
    v13 = -2147024809;
    if ( v11 )
    {
      v13 = 0;
      v14 = 0x7FFFFFFF - v11;
    }
    else
    {
      v14 = 0;
    }
    if ( v11 )
    {
      v15 = 78;
      if ( v14 > 1 )
      {
        v15 = *(_WORD *)(pvarDest.hVal.QuadPart + 2 * v14 - 2);
        *(_WORD *)(pvarDest.hVal.QuadPart + 2 * v14 - 2) = 0;
      }
      if ( !is_mul_ok(4u, 8u) )
        goto LABEL_12;
      v17 = (BYTE *)CoTaskMemAlloc(0x20u);
      pvara->bstrblobVal.pData = v17;
      if ( v17 )
      {
        memset_0(v17, 0, 0x20u);
        pvara->lVal = 4;
        pvara->vt = 4117;
        if ( !is_mul_ok(3u, 8u) )
          goto LABEL_12;
        v18 = (BYTE *)CoTaskMemAlloc(0x18u);
        a4->bstrblobVal.pData = v18;
        if ( !v18 )
          goto LABEL_34;
        memset_0(v18, 0, 0x18u);
        a4->vt = 4101;
        a4->lVal = 3;
        if ( !is_mul_ok(3u, 4u) )
          goto LABEL_12;
        v19 = (BYTE *)CoTaskMemAlloc(0xCu);
        pvar->bstrblobVal.pData = v19;
        if ( !v19 )
          goto LABEL_34;
        memset_0(v19, 0, 0xCu);
        pvar->vt = 4115;
        pvar->lVal = 3;
        if ( !is_mul_ok(3u, 4u) )
        {
LABEL_12:
          v9 = -2147024362;
          goto LABEL_13;
        }
        v20 = (BYTE *)CoTaskMemAlloc(0xCu);
        a3->bstrblobVal.pData = v20;
        if ( v20 )
        {
          memset_0(v20, 0, 0xCu);
          v21 = pvarDest.bstrVal;
          v22 = 0;
          a3->lVal = 3;
          v23 = 0;
          a3->vt = 4115;
          v24 = v21;
          if ( v21 )
          {
            do
            {
              v25 = *v24;
              if ( !*v24 )
                break;
              v26 = v22 + 1;
              if ( v25 != 44 )
                v26 = v22;
              v22 = v26;
              v27 = v23 + 1;
              if ( v25 != 46 )
                v27 = v23;
              v23 = v27;
              ++v24;
            }
            while ( v24 );
            if ( v22 == 2 )
            {
              if ( v23 )
                goto LABEL_13;
              v33 = wcstok(v21, L",", 0);
              do
              {
                if ( !v33 )
                  break;
                *(double *)&a4->bstrblobVal.pData[8 * v12] = _wtof(v33);
                *(_DWORD *)&pvar->bstrblobVal.pData[4 * v12] = _o__wtol(v33);
                *(_DWORD *)&a3->bstrblobVal.pData[4 * v12] = 1;
                *(_DWORD *)&pvara->bstrblobVal.pData[8 * v12] = *(_DWORD *)&pvar->bstrblobVal.pData[4 * v12];
                *(_DWORD *)&pvara->bstrblobVal.pData[8 * v12 + 4] = *(_DWORD *)&a3->bstrblobVal.pData[4 * v12];
                ++v12;
                v33 = wcstok(0, L",", 0);
              }
              while ( v12 < 3 );
            }
            else
            {
              if ( v22 != 1 || v23 != 1 )
                goto LABEL_13;
              v28 = wcstok(v21, L",", 0);
              *a4->cadbl.pElems = _wtof(v28);
              *pvar->cal.pElems = _o__wtol(v28);
              *a3->cal.pElems = 1;
              *pvara->cal.pElems = *pvar->cal.pElems;
              *((_DWORD *)pvara->bstrblobVal.pData + 1) = *a3->cal.pElems;
              v29 = wcstok(0, L",", 0);
              v30 = _wtof(v29);
              *((double *)a4->bstrblobVal.pData + 1) = (double)(int)v30;
              *((_DWORD *)pvar->bstrblobVal.pData + 1) = (int)v30;
              *((_DWORD *)a3->bstrblobVal.pData + 1) = 1;
              *((_DWORD *)pvara->bstrblobVal.pData + 2) = *((_DWORD *)pvar->bstrblobVal.pData + 1);
              *((_DWORD *)pvara->bstrblobVal.pData + 3) = *((_DWORD *)a3->bstrblobVal.pData + 1);
              pData = a4->bstrblobVal.pData;
              v32 = (v30 - *((double *)pData + 1)) * 60.0;
              *((double *)pData + 2) = v32;
              *((_DWORD *)pvar->bstrblobVal.pData + 2) = (int)(v32 * 10000.0);
              *((_DWORD *)a3->bstrblobVal.pData + 2) = 10000;
              *((_DWORD *)pvara->bstrblobVal.pData + 4) = *((_DWORD *)pvar->bstrblobVal.pData + 2);
              *((_DWORD *)pvara->bstrblobVal.pData + 5) = *((_DWORD *)a3->bstrblobVal.pData + 2);
            }
            v9 = 0;
            if ( v15 == 101 )
            {
LABEL_33:
              *((_QWORD *)pvara->bstrblobVal.pData + 3) = 3;
            }
            else if ( v15 == 110 )
            {
LABEL_36:
              *((_QWORD *)pvara->bstrblobVal.pData + 3) = 1;
            }
            else
            {
              switch ( v15 )
              {
                case 'E':
                  goto LABEL_33;
                case 'N':
                  goto LABEL_36;
                case 'S':
                case 's':
                  *((_QWORD *)pvara->bstrblobVal.pData + 3) = 2;
                  break;
                case 'W':
                case 'w':
                  *((_QWORD *)pvara->bstrblobVal.pData + 3) = 4;
                  break;
                default:
                  break;
              }
            }
          }
LABEL_13:
          PropVariantClear(&pvarDest);
          return (unsigned int)v9;
        }
      }
LABEL_34:
      v9 = -2147024882;
      goto LABEL_13;
    }
  }
  else
  {
    v13 = -2147024809;
  }
  PropVariantClear(&pvarDest);
  return v13;
}

```

## disassembly

```asm
0x180009010  mov     [rsp+arg_8], rbx
0x180009015  mov     [rsp+arg_10], rsi
0x18000901a  push    rdi
0x18000901b  push    r12
0x18000901d  push    r13
0x18000901f  push    r14
0x180009021  push    r15
0x180009023  sub     rsp, 40h
0x180009027  mov     rbx, rcx
0x18000902a  mov     r12, r9
0x18000902d  mov     rcx, rdx; pvar
0x180009030  mov     rdi, r8
0x180009033  mov     r14, rdx
0x180009036  call    cs:__imp_PropVariantClear
0x18000903c  mov     rcx, rdi; pvar
0x18000903f  call    cs:__imp_PropVariantClear
0x180009045  mov     rcx, r12; pvar
0x180009048  call    cs:__imp_PropVariantClear
0x18000904e  mov     r15, [rsp+68h+pvar]
0x180009056  mov     rcx, r15; pvar
0x180009059  call    cs:__imp_PropVariantClear
0x18000905f  xorps   xmm0, xmm0
0x180009062  lea     rcx, [rsp+68h+pvarDest]; pvarDest
0x180009067  xor     eax, eax
0x180009069  mov     rdx, rbx; pvarSrc
0x18000906c  movups  xmmword ptr [rsp+68h+pvarDest], xmm0
0x180009071  mov     qword ptr [rsp+68h+pvarDest+10h], rax
0x180009076  call    cs:__imp_PropVariantCopy
0x18000907c  mov     ebx, eax
0x18000907e  test    eax, eax
0x180009080  js      loc_18000910E
0x180009086  mov     r8, qword ptr [rsp+68h+pvarDest+8]
0x18000908b  test    r8, r8
0x18000908e  jz      loc_1800094D5
0x180009094  mov     edx, 7FFFFFFFh
0x180009099  mov     rax, r8
0x18000909c  mov     ecx, edx
0x18000909e  xchg    ax, ax
0x1800090a0  cmp     word ptr [rax], 0
0x1800090a4  jz      short loc_1800090B0
0x1800090a6  add     rax, 2
0x1800090aa  sub     rcx, 1
0x1800090ae  jnz     short loc_1800090A0
0x1800090b0  xor     r13d, r13d
0x1800090b3  mov     ebx, 80070057h
0x1800090b8  test    rcx, rcx
0x1800090bb  mov     esi, ebx
0x1800090bd  cmovnz  esi, r13d
0x1800090c1  jz      loc_1800093EA
0x1800090c7  sub     rdx, rcx
0x1800090ca  test    rcx, rcx
0x1800090cd  jz      loc_1800094DA
0x1800090d3  mov     [rsp+68h+arg_0], rbp
0x1800090d8  mov     ebp, 4Eh ; 'N'
0x1800090dd  cmp     rdx, 1
0x1800090e1  jbe     short loc_1800090EF
0x1800090e3  movzx   ebp, word ptr [r8+rdx*2-2]
0x1800090e9  mov     [r8+rdx*2-2], r13w
0x1800090ef  mov     ecx, 4
0x1800090f4  mov     eax, 8
0x1800090f9  mul     rcx
0x1800090fc  mov     rsi, rax
0x1800090ff  test    rdx, rdx
0x180009102  jz      short loc_180009136
0x180009104  mov     ebx, 80070216h
0x180009109  mov     rbp, [rsp+68h+arg_0]; jumptable 00000001800094B1 default case, cases 70-77,79-82,84-86,88-114,116-118
0x18000910e  lea     rcx, [rsp+68h+pvarDest]; pvar
0x180009113  call    cs:__imp_PropVariantClear
0x180009119  mov     eax, ebx
0x18000911b  mov     rbx, [rsp+68h+arg_8]
0x180009120  mov     rsi, [rsp+68h+arg_10]
0x180009128  add     rsp, 40h
0x18000912c  pop     r15
0x18000912e  pop     r14
0x180009130  pop     r13
0x180009132  pop     r12
0x180009134  pop     rdi
0x180009135  retn
0x180009136  mov     rcx, rsi; cb
0x180009139  call    cs:__imp_CoTaskMemAlloc
0x18000913f  mov     [r15+10h], rax
0x180009143  test    rax, rax
0x180009146  jz      loc_1800093C6
0x18000914c  mov     r8, rsi; Size
0x18000914f  xor     edx, edx; Val
0x180009151  mov     rcx, rax; void *
0x180009154  call    memset_0
0x180009159  mov     ecx, 3
0x18000915e  mov     dword ptr [r15+8], 4
0x180009166  mov     eax, 8
0x18000916b  mov     word ptr [r15], 1015h
0x180009171  mul     rcx
0x180009174  mov     rsi, rax
0x180009177  test    rdx, rdx
0x18000917a  jnz     short loc_180009104
0x18000917c  mov     rcx, rax; cb
0x18000917f  call    cs:__imp_CoTaskMemAlloc
0x180009185  mov     [r12+10h], rax
0x18000918a  test    rax, rax
0x18000918d  jz      loc_1800093C6
0x180009193  mov     r8, rsi; Size
0x180009196  xor     edx, edx; Val
0x180009198  mov     rcx, rax; void *
0x18000919b  call    memset_0
0x1800091a0  mov     ecx, 3
0x1800091a5  mov     word ptr [r12], 1005h
0x1800091ac  mov     eax, 4
0x1800091b1  mov     [r12+8], ecx
0x1800091b6  mul     rcx
0x1800091b9  mov     rsi, rax
0x1800091bc  test    rdx, rdx
0x1800091bf  jnz     loc_180009104
0x1800091c5  mov     rcx, rax; cb
0x1800091c8  call    cs:__imp_CoTaskMemAlloc
0x1800091ce  mov     [r14+10h], rax
0x1800091d2  test    rax, rax
0x1800091d5  jz      loc_1800093C6
0x1800091db  mov     r8, rsi; Size
0x1800091de  xor     edx, edx; Val
0x1800091e0  mov     rcx, rax; void *
0x1800091e3  call    memset_0
0x1800091e8  mov     ecx, 3
0x1800091ed  mov     word ptr [r14], 1013h
0x1800091f3  mov     eax, 4
0x1800091f8  mov     [r14+8], ecx
0x1800091fc  mul     rcx
0x1800091ff  mov     rsi, rax
0x180009202  test    rdx, rdx
0x180009205  jnz     loc_180009104
0x18000920b  mov     rcx, rax; cb
0x18000920e  call    cs:__imp_CoTaskMemAlloc
0x180009214  mov     [rdi+10h], rax
0x180009218  test    rax, rax
0x18000921b  jz      loc_1800093C6
0x180009221  mov     r8, rsi; Size
0x180009224  xor     edx, edx; Val
0x180009226  mov     rcx, rax; void *
0x180009229  call    memset_0
0x18000922e  mov     r10, qword ptr [rsp+68h+pvarDest+8]
0x180009233  mov     r8d, r13d
0x180009236  mov     dword ptr [rdi+8], 3
0x18000923d  mov     r9d, r13d
0x180009240  mov     word ptr [rdi], 1013h
0x180009245  mov     rcx, r10
0x180009248  test    r10, r10
0x18000924b  jz      def_1800094B1; jumptable 00000001800094B1 default case, cases 70-77,79-82,84-86,88-114,116-118
0x180009251  movzx   edx, word ptr [rcx]
0x180009254  test    dx, dx
0x180009257  jz      short loc_18000927D
0x180009259  cmp     dx, 2Ch ; ','
0x18000925d  lea     eax, [r8+1]
0x180009261  cmovnz  eax, r8d
0x180009265  cmp     dx, 2Eh ; '.'
0x180009269  mov     r8d, eax
0x18000926c  lea     eax, [r9+1]
0x180009270  cmovnz  eax, r9d
0x180009274  mov     r9d, eax
0x180009277  add     rcx, 2
0x18000927b  jnz     short loc_180009251
0x18000927d  cmp     r8d, 2
0x180009281  jz      loc_1800093F2
0x180009287  cmp     r8d, 1
0x18000928b  jnz     def_1800094B1; jumptable 00000001800094B1 default case, cases 70-77,79-82,84-86,88-114,116-118
0x180009291  cmp     r9d, r8d
0x180009294  jnz     def_1800094B1; jumptable 00000001800094B1 default case, cases 70-77,79-82,84-86,88-114,116-118
0x18000929a  xor     r8d, r8d; Context
0x18000929d  lea     rdx, Delimiter; ","
0x1800092a4  mov     rcx, r10; String
0x1800092a7  call    cs:__imp_wcstok
0x1800092ad  mov     rcx, rax; String
0x1800092b0  mov     rbx, rax
0x1800092b3  call    cs:__imp__wtof
0x1800092b9  mov     rcx, [r12+10h]
0x1800092be  movsd   qword ptr [rcx], xmm0
0x1800092c2  mov     rcx, rbx
0x1800092c5  call    cs:__imp__o__wtol
0x1800092cb  mov     rcx, [r14+10h]
0x1800092cf  lea     rdx, Delimiter; ","
0x1800092d6  xor     r8d, r8d; Context
0x1800092d9  mov     [rcx], eax
0x1800092db  mov     rax, [rdi+10h]
0x1800092df  mov     dword ptr [rax], 1
0x1800092e5  mov     rax, [r14+10h]
0x1800092e9  mov     rcx, [r15+10h]
0x1800092ed  mov     eax, [rax]
0x1800092ef  mov     [rcx], eax
0x1800092f1  mov     rax, [rdi+10h]
0x1800092f5  mov     rcx, [r15+10h]
0x1800092f9  mov     eax, [rax]
0x1800092fb  mov     [rcx+4], eax
0x1800092fe  xor     ecx, ecx; String
0x180009300  call    cs:__imp_wcstok
0x180009306  mov     rcx, rax; String
0x180009309  call    cs:__imp__wtof
0x18000930f  cvttsd2si eax, xmm0
0x180009313  cvttsd2si rcx, xmm0
0x180009318  movd    xmm1, eax
0x18000931c  mov     rax, [r12+10h]
0x180009321  cvtdq2pd xmm1, xmm1
0x180009325  movsd   qword ptr [rax+8], xmm1
0x18000932a  mov     rax, [r14+10h]
0x18000932e  mov     [rax+4], ecx
0x180009331  mov     rax, [rdi+10h]
0x180009335  mov     dword ptr [rax+4], 1
0x18000933c  mov     rax, [r14+10h]
0x180009340  mov     rcx, [r15+10h]
0x180009344  mov     eax, [rax+4]
0x180009347  mov     [rcx+8], eax
0x18000934a  mov     rax, [rdi+10h]
0x18000934e  mov     rcx, [r15+10h]
0x180009352  mov     eax, [rax+4]
0x180009355  mov     [rcx+0Ch], eax
0x180009358  mov     rax, [r12+10h]
0x18000935d  subsd   xmm0, qword ptr [rax+8]
0x180009362  mulsd   xmm0, cs:__real@404e000000000000
0x18000936a  movsd   qword ptr [rax+10h], xmm0
0x18000936f  mov     rax, [r14+10h]
0x180009373  mulsd   xmm0, cs:__real@40c3880000000000
0x18000937b  cvttsd2si rcx, xmm0
0x180009380  mov     [rax+8], ecx
0x180009383  mov     rax, [rdi+10h]
0x180009387  mov     dword ptr [rax+8], 2710h
0x18000938e  mov     rax, [r14+10h]
0x180009392  mov     rcx, [r15+10h]
0x180009396  mov     eax, [rax+8]
0x180009399  mov     [rcx+10h], eax
0x18000939c  mov     rax, [rdi+10h]
0x1800093a0  mov     rcx, [r15+10h]
0x1800093a4  mov     eax, [rax+8]
0x1800093a7  mov     [rcx+14h], eax
0x1800093aa  movzx   eax, bp
0x1800093ad  mov     ebx, r13d
0x1800093b0  cmp     eax, 65h ; 'e'
0x1800093b3  jnz     short loc_1800093D0
0x1800093b5  mov     rax, [r15+10h]; jumptable 00000001800094B1 case 69
0x1800093b9  mov     qword ptr [rax+18h], 3
0x1800093c1  jmp     def_1800094B1; jumptable 00000001800094B1 default case, cases 70-77,79-82,84-86,88-114,116-118
0x1800093c6  mov     ebx, 8007000Eh
0x1800093cb  jmp     def_1800094B1; jumptable 00000001800094B1 default case, cases 70-77,79-82,84-86,88-114,116-118
0x1800093d0  cmp     eax, 6Eh ; 'n'
0x1800093d3  jnz     loc_18000948A
0x1800093d9  mov     rax, [r15+10h]; jumptable 00000001800094B1 case 78
0x1800093dd  mov     qword ptr [rax+18h], 1
0x1800093e5  jmp     def_1800094B1; jumptable 00000001800094B1 default case, cases 70-77,79-82,84-86,88-114,116-118
0x1800093ea  mov     rdx, r13
0x1800093ed  jmp     loc_1800090CA
0x1800093f2  test    r9d, r9d
0x1800093f5  jnz     def_1800094B1; jumptable 00000001800094B1 default case, cases 70-77,79-82,84-86,88-114,116-118
0x1800093fb  xor     r8d, r8d; Context
0x1800093fe  lea     rdx, Delimiter; ","
0x180009405  mov     rcx, r10; String
0x180009408  call    cs:__imp_wcstok
0x18000940e  mov     rsi, rax
0x180009411  test    rsi, rsi
0x180009414  jz      short loc_180009482
0x180009416  mov     rcx, rsi; String
0x180009419  call    cs:__imp__wtof
0x18000941f  mov     rcx, [r12+10h]
0x180009424  mov     ebx, r13d
0x180009427  movsd   qword ptr [rcx+rbx*8], xmm0
0x18000942c  mov     rcx, rsi
0x18000942f  call    cs:__imp__o__wtol
0x180009435  mov     rcx, [r14+10h]
0x180009439  lea     rdx, Delimiter; ","
0x180009440  xor     r8d, r8d; Context
0x180009443  mov     [rcx+rbx*4], eax
0x180009446  mov     rax, [rdi+10h]
0x18000944a  mov     dword ptr [rax+rbx*4], 1
0x180009451  mov     rax, [r14+10h]
0x180009455  mov     rcx, [r15+10h]
0x180009459  mov     eax, [rax+rbx*4]
0x18000945c  mov     [rcx+rbx*8], eax
0x18000945f  mov     rax, [rdi+10h]
0x180009463  mov     rcx, [r15+10h]
0x180009467  mov     eax, [rax+rbx*4]
0x18000946a  mov     [rcx+rbx*8+4], eax
0x18000946e  xor     ecx, ecx; String
0x180009470  call    cs:__imp_wcstok
0x180009476  inc     r13d
0x180009479  mov     rsi, rax
0x18000947c  cmp     r13d, 3
0x180009480  jl      short loc_180009411
0x180009482  xor     r13d, r13d
0x180009485  jmp     loc_1800093AA
0x18000948a  add     eax, 0FFFFFFBBh; switch 51 cases
0x18000948d  cmp     eax, 32h
0x180009490  ja      def_1800094B1; jumptable 00000001800094B1 default case, cases 70-77,79-82,84-86,88-114,116-118
0x180009496  lea     rdx, __ImageBase
0x18000949d  cdqe
0x18000949f  movzx   eax, ds:(byte_180009500 - 180000000h)[rdx+rax]
0x1800094a7  mov     ecx, ds:(jpt_1800094B1 - 180000000h)[rdx+rax*4]
0x1800094ae  add     rcx, rdx
0x1800094b1  jmp     rcx; switch jump
0x1800094b3  mov     rax, [r15+10h]; jumptable 00000001800094B1 cases 83,115
0x1800094b7  mov     qword ptr [rax+18h], 2
0x1800094bf  jmp     def_1800094B1; jumptable 00000001800094B1 default case, cases 70-77,79-82,84-86,88-114,116-118
0x1800094c4  mov     rax, [r15+10h]; jumptable 00000001800094B1 cases 87,119
0x1800094c8  mov     qword ptr [rax+18h], 4
0x1800094d0  jmp     def_1800094B1; jumptable 00000001800094B1 default case, cases 70-77,79-82,84-86,88-114,116-118
0x1800094d5  mov     esi, 80070057h
  ... truncated ...
```
