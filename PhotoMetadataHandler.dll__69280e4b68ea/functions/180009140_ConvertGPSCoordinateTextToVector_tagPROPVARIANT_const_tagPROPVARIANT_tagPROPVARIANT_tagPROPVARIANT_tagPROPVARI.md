# ConvertGPSCoordinateTextToVector(tagPROPVARIANT const *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *,tagPROPVARIANT *)

- ea: `0x180009140`
- end: `0x18000968f`
- name: `?ConvertGPSCoordinateTextToVector@@YAJPEBUtagPROPVARIANT@@PEAU1@111@Z`
- size: `1359`
- prototype: `__int64 __fastcall(PROPVARIANT *pvarSrc, PROPVARIANT *pvar, PROPVARIANT *, PROPVARIANT *, PROPVARIANT *)`
- caller_count: `5`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003900`
- `0x180008550`
- `0x1800124b4`
- `0x180012d00`
- `0x18001beb8`

## callees

- `0x180009140`
- `0x1800096a0`
- `0x180017408`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x1800093e8`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x18000944d`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x180009569`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x1800093e8`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x18000944d`
- `api-ms-win-crt-private-l1-1-0!_o__wtof` at `0x180009569`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800093ff`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180009584`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800093ff`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180009584`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1800093d6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18000943e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180009552`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1800095c9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1800093d6`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18000943e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180009552`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1800095c9`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800091b8`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x1800091b8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009160`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000916f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000917e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009195`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000925c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009160`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000916f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000917e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009195`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000925c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009337`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009337`

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
  unsigned __int64 v12; // rdx
  __int16 v13; // bp
  BYTE **p_pData; // r12
  BYTE **v16; // r13
  unsigned int v17; // r15d
  BYTE **v18; // r14
  BYTE *v19; // rax
  wchar_t *v20; // r10
  int v21; // r8d
  int v22; // r9d
  wchar_t *v23; // rcx
  wchar_t v24; // dx
  int v25; // eax
  int v26; // eax
  wchar_t *v27; // rbx
  wchar_t *v28; // rax
  double v29; // xmm0_8
  double v30; // xmm0_8
  wchar_t *v31; // rsi
  PROPVARIANT pvarDest; // [rsp+28h] [rbp-40h] BYREF

  PropVariantClear(pvar);
  PropVariantClear(a3);
  PropVariantClear(a4);
  PropVariantClear(pvara);
  memset(&pvarDest, 0, sizeof(pvarDest));
  v9 = PropVariantCopy(&pvarDest, pvarSrc);
  if ( v9 >= 0 )
  {
    if ( !pvarDest.hVal.QuadPart )
    {
      v9 = -2147024809;
      goto LABEL_14;
    }
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
    v9 = -2147024809;
    if ( v11 )
    {
      v9 = 0;
      v12 = 0x7FFFFFFF - v11;
    }
    else
    {
      v12 = 0;
    }
    if ( v11 )
    {
      v13 = 78;
      if ( v12 > 1 )
      {
        v13 = *(_WORD *)(pvarDest.hVal.QuadPart + 2 * v12 - 2);
        *(_WORD *)(pvarDest.hVal.QuadPart + 2 * v12 - 2) = 0;
      }
      if ( !is_mul_ok(4u, 8u) )
      {
        v9 = -2147024362;
        goto LABEL_14;
      }
      p_pData = &pvara->bstrblobVal.pData;
      v9 = CoTaskMemAllocWithInit(0x20u, (void **)&pvara->bstrblobVal.pData);
      if ( v9 < 0 )
        goto LABEL_14;
      pvara->lVal = 4;
      pvara->vt = 4117;
      if ( !is_mul_ok(3u, 8u) )
        goto LABEL_35;
      v16 = &a4->bstrblobVal.pData;
      v9 = CoTaskMemAllocWithInit(0x18u, (void **)&a4->bstrblobVal.pData);
      if ( v9 < 0 )
        goto LABEL_14;
      a4->lVal = 3;
      a4->vt = 4101;
      v17 = 0;
      if ( !is_mul_ok(3u, 4u) )
        goto LABEL_35;
      v18 = &pvar->bstrblobVal.pData;
      v9 = CoTaskMemAllocWithInit(0xCu, (void **)&pvar->bstrblobVal.pData);
      if ( v9 < 0 )
        goto LABEL_14;
      pvar->lVal = 3;
      pvar->vt = 4115;
      if ( !is_mul_ok(3u, 4u) )
      {
LABEL_35:
        v9 = -2147024362;
        goto LABEL_14;
      }
      v19 = (BYTE *)CoTaskMemAlloc(0xCu);
      a3->bstrblobVal.pData = v19;
      if ( !v19 )
      {
        v9 = -2147024882;
        goto LABEL_14;
      }
      memset_0(v19, 0, 0xCu);
      v20 = pvarDest.bstrVal;
      v21 = 0;
      a3->lVal = 3;
      v22 = 0;
      a3->vt = 4115;
      v23 = v20;
      if ( v20 )
      {
        do
        {
          v24 = *v23;
          if ( !*v23 )
            break;
          v25 = v21 + 1;
          if ( v24 != 44 )
            v25 = v21;
          v21 = v25;
          v26 = v22 + 1;
          if ( v24 != 46 )
            v26 = v22;
          v22 = v26;
          ++v23;
        }
        while ( v23 );
        if ( v21 == 2 )
        {
          if ( !v22 )
          {
            v31 = wcstok(v20, L",", 0);
            do
            {
              if ( !v31 )
                break;
              *(double *)&(*v16)[8 * v17] = _wtof(v31);
              *(_DWORD *)&(*v18)[4 * v17] = _o__wtol(v31);
              *(_DWORD *)&a3->bstrblobVal.pData[4 * v17] = 1;
              *(_DWORD *)&(*p_pData)[8 * v17] = *(_DWORD *)&(*v18)[4 * v17];
              *(_DWORD *)&(*p_pData)[8 * v17 + 4] = *(_DWORD *)&a3->bstrblobVal.pData[4 * v17];
              ++v17;
              v31 = wcstok(0, L",", 0);
            }
            while ( (int)v17 < 3 );
LABEL_33:
            v9 = 0;
            if ( v13 == 101 )
            {
LABEL_34:
              *((_QWORD *)*p_pData + 3) = 3;
            }
            else if ( v13 == 110 )
            {
LABEL_37:
              *((_QWORD *)*p_pData + 3) = 1;
            }
            else
            {
              switch ( v13 )
              {
                case 'E':
                  goto LABEL_34;
                case 'N':
                  goto LABEL_37;
                case 'S':
                case 's':
                  *((_QWORD *)*p_pData + 3) = 2;
                  break;
                case 'W':
                case 'w':
                  *((_QWORD *)*p_pData + 3) = 4;
                  break;
                default:
                  goto LABEL_14;
              }
            }
            goto LABEL_14;
          }
        }
        else if ( v21 == 1 && v22 == 1 )
        {
          v27 = wcstok(v20, L",", 0);
          *(double *)*v16 = _wtof(v27);
          *(_DWORD *)*v18 = _o__wtol(v27);
          *a3->cal.pElems = 1;
          *(_DWORD *)*p_pData = *(_DWORD *)*v18;
          *((_DWORD *)*p_pData + 1) = *a3->cal.pElems;
          v28 = wcstok(0, L",", 0);
          v29 = _wtof(v28);
          *((double *)*v16 + 1) = (double)(int)v29;
          *((_DWORD *)*v18 + 1) = (int)v29;
          *((_DWORD *)a3->bstrblobVal.pData + 1) = 1;
          *((_DWORD *)*p_pData + 2) = *((_DWORD *)*v18 + 1);
          *((_DWORD *)*p_pData + 3) = *((_DWORD *)a3->bstrblobVal.pData + 1);
          v30 = (v29 - *((double *)*v16 + 1)) * 60.0;
          *((double *)*v16 + 2) = v30;
          *((_DWORD *)*v18 + 2) = (int)(v30 * 10000.0);
          *((_DWORD *)a3->bstrblobVal.pData + 2) = 10000;
          *((_DWORD *)*p_pData + 4) = *((_DWORD *)*v18 + 2);
          *((_DWORD *)*p_pData + 5) = *((_DWORD *)a3->bstrblobVal.pData + 2);
          goto LABEL_33;
        }
      }
      v9 = -2147024809;
    }
  }
LABEL_14:
  PropVariantClear(&pvarDest);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180009140  mov     [rsp+arg_10], rbx
0x180009145  push    rsi
0x180009146  push    rdi
0x180009147  push    r13
0x180009149  push    r14
0x18000914b  push    r15
0x18000914d  sub     rsp, 40h
0x180009151  mov     rbx, rcx
0x180009154  mov     r15, r9
0x180009157  mov     rcx, rdx; pvar
0x18000915a  mov     rdi, r8
0x18000915d  mov     rsi, rdx
0x180009160  call    cs:__imp_PropVariantClear
0x180009167  nop     dword ptr [rax+rax+00h]
0x18000916c  mov     rcx, rdi; pvar
0x18000916f  call    cs:__imp_PropVariantClear
0x180009176  nop     dword ptr [rax+rax+00h]
0x18000917b  mov     rcx, r15; pvar
0x18000917e  call    cs:__imp_PropVariantClear
0x180009185  nop     dword ptr [rax+rax+00h]
0x18000918a  mov     r14, [rsp+68h+pvar]
0x180009192  mov     rcx, r14; pvar
0x180009195  call    cs:__imp_PropVariantClear
0x18000919c  nop     dword ptr [rax+rax+00h]
0x1800091a1  xorps   xmm0, xmm0
0x1800091a4  lea     rcx, [rsp+68h+pvarDest]; pvarDest
0x1800091a9  xor     eax, eax
0x1800091ab  mov     rdx, rbx; pvarSrc
0x1800091ae  movups  xmmword ptr [rsp+68h+pvarDest], xmm0
0x1800091b3  mov     qword ptr [rsp+68h+pvarDest+10h], rax
0x1800091b8  call    cs:__imp_PropVariantCopy
0x1800091bf  nop     dword ptr [rax+rax+00h]
0x1800091c4  mov     ebx, eax
0x1800091c6  test    eax, eax
0x1800091c8  js      loc_180009257
0x1800091ce  mov     r8, qword ptr [rsp+68h+pvarDest+8]
0x1800091d3  test    r8, r8
0x1800091d6  jz      loc_18000963D
0x1800091dc  mov     edx, 7FFFFFFFh
0x1800091e1  mov     rax, r8
0x1800091e4  mov     ecx, edx
0x1800091e6  cmp     word ptr [rax], 0
0x1800091ea  jz      short loc_1800091F6
0x1800091ec  add     rax, 2
0x1800091f0  sub     rcx, 1
0x1800091f4  jnz     short loc_1800091E6
0x1800091f6  xor     r13d, r13d
0x1800091f9  mov     ebx, 80070057h
0x1800091fe  test    rcx, rcx
0x180009201  cmovnz  ebx, r13d
0x180009205  jz      loc_180009534
0x18000920b  sub     rdx, rcx
0x18000920e  test    rcx, rcx
0x180009211  jz      short loc_180009257
0x180009213  mov     [rsp+68h+arg_0], rbp
0x180009218  mov     ebp, 4Eh ; 'N'
0x18000921d  cmp     rdx, 1
0x180009221  jbe     short loc_18000922F
0x180009223  movzx   ebp, word ptr [r8+rdx*2-2]
0x180009229  mov     [r8+rdx*2-2], r13w
0x18000922f  mov     ecx, 4
0x180009234  mov     eax, 8
0x180009239  mul     rcx
0x18000923c  test    rdx, rdx
0x18000923f  jz      short loc_180009280
0x180009241  mov     ebx, 80070216h
0x180009246  jmp     short loc_180009252
0x180009248  mov     ebx, 80070057h
0x18000924d  mov     r12, [rsp+68h+arg_8]; jumptable 0000000180009615 default case, cases 70-77,79-82,84-86,88-114,116-118
0x180009252  mov     rbp, [rsp+68h+arg_0]
0x180009257  lea     rcx, [rsp+68h+pvarDest]; pvar
0x18000925c  call    cs:__imp_PropVariantClear
0x180009263  nop     dword ptr [rax+rax+00h]
0x180009268  mov     eax, ebx
0x18000926a  mov     rbx, [rsp+68h+arg_10]
0x180009272  add     rsp, 40h
0x180009276  pop     r15
0x180009278  pop     r14
0x18000927a  pop     r13
0x18000927c  pop     rdi
0x18000927d  pop     rsi
0x18000927e  retn
0x180009280  mov     [rsp+68h+arg_8], r12
0x180009285  mov     rcx, rax; Size
0x180009288  lea     r12, [r14+10h]
0x18000928c  mov     rdx, r12; void **
0x18000928f  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180009294  mov     ebx, eax
0x180009296  test    eax, eax
0x180009298  js      short def_180009615; jumptable 0000000180009615 default case, cases 70-77,79-82,84-86,88-114,116-118
0x18000929a  mov     dword ptr [r14+8], 4
0x1800092a2  mov     eax, 8
0x1800092a7  mov     word ptr [r14], 1015h
0x1800092ad  mov     r14d, 3
0x1800092b3  mul     r14
0x1800092b6  test    rdx, rdx
0x1800092b9  jnz     loc_180009506
0x1800092bf  lea     r13, [r15+10h]
0x1800092c3  mov     rcx, rax; Size
0x1800092c6  mov     rdx, r13; void **
0x1800092c9  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x1800092ce  mov     ebx, eax
0x1800092d0  test    eax, eax
0x1800092d2  js      def_180009615; jumptable 0000000180009615 default case, cases 70-77,79-82,84-86,88-114,116-118
0x1800092d8  mov     eax, 4
0x1800092dd  mov     [r15+8], r14d
0x1800092e1  mul     r14
0x1800092e4  mov     word ptr [r15], 1005h
0x1800092ea  xor     r15d, r15d
0x1800092ed  test    rdx, rdx
0x1800092f0  jnz     loc_180009506
0x1800092f6  lea     r14, [rsi+10h]
0x1800092fa  mov     rcx, rax; Size
0x1800092fd  mov     rdx, r14; void **
0x180009300  call    ?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z; CoTaskMemAllocWithInit(unsigned __int64,void * *)
0x180009305  mov     ebx, eax
0x180009307  test    eax, eax
0x180009309  js      def_180009615; jumptable 0000000180009615 default case, cases 70-77,79-82,84-86,88-114,116-118
0x18000930f  mov     dword ptr [rsi+8], 3
0x180009316  mov     eax, 4
0x18000931b  mov     word ptr [rsi], 1013h
0x180009320  mov     esi, 3
0x180009325  mul     rsi
0x180009328  mov     rbx, rax
0x18000932b  test    rdx, rdx
0x18000932e  jnz     loc_180009506
0x180009334  mov     rcx, rax; cb
0x180009337  call    cs:__imp_CoTaskMemAlloc
0x18000933e  nop     dword ptr [rax+rax+00h]
0x180009343  mov     [rdi+10h], rax
0x180009347  test    rax, rax
0x18000934a  jz      loc_18000952A
0x180009350  mov     r8, rbx; Size
0x180009353  xor     edx, edx; Val
0x180009355  mov     rcx, rax; void *
0x180009358  call    memset_0
0x18000935d  mov     r10, qword ptr [rsp+68h+pvarDest+8]
0x180009362  mov     r8d, r15d
0x180009365  mov     [rdi+8], esi
0x180009368  mov     r9d, r15d
0x18000936b  mov     word ptr [rdi], 1013h
0x180009370  mov     rcx, r10
0x180009373  test    r10, r10
0x180009376  jz      loc_180009248
0x18000937c  nop     dword ptr [rax+00h]
0x180009380  movzx   edx, word ptr [rcx]
0x180009383  test    dx, dx
0x180009386  jz      short loc_1800093AC
0x180009388  cmp     dx, 2Ch ; ','
0x18000938c  lea     eax, [r8+1]
0x180009390  cmovnz  eax, r8d
0x180009394  cmp     dx, 2Eh ; '.'
0x180009398  mov     r8d, eax
0x18000939b  lea     eax, [r9+1]
0x18000939f  cmovnz  eax, r9d
0x1800093a3  mov     r9d, eax
0x1800093a6  add     rcx, 2
0x1800093aa  jnz     short loc_180009380
0x1800093ac  cmp     r8d, 2
0x1800093b0  jz      loc_18000953C
0x1800093b6  cmp     r8d, 1
0x1800093ba  jnz     loc_180009248
0x1800093c0  cmp     r9d, r8d
0x1800093c3  jnz     loc_180009248
0x1800093c9  xor     r8d, r8d; Context
0x1800093cc  lea     rdx, Delimiter; ","
0x1800093d3  mov     rcx, r10; String
0x1800093d6  call    cs:__imp_wcstok
0x1800093dd  nop     dword ptr [rax+rax+00h]
0x1800093e2  mov     rcx, rax; String
0x1800093e5  mov     rbx, rax
0x1800093e8  call    cs:__imp__wtof
0x1800093ef  nop     dword ptr [rax+rax+00h]
0x1800093f4  mov     rcx, [r13+0]
0x1800093f8  movsd   qword ptr [rcx], xmm0
0x1800093fc  mov     rcx, rbx
0x1800093ff  call    cs:__imp__o__wtol
0x180009406  nop     dword ptr [rax+rax+00h]
0x18000940b  mov     rcx, [r14]
0x18000940e  lea     rdx, Delimiter; ","
0x180009415  xor     r8d, r8d; Context
0x180009418  mov     [rcx], eax
0x18000941a  mov     rax, [rdi+10h]
0x18000941e  mov     dword ptr [rax], 1
0x180009424  mov     rax, [r14]
0x180009427  mov     rcx, [r12]
0x18000942b  mov     eax, [rax]
0x18000942d  mov     [rcx], eax
0x18000942f  mov     rax, [rdi+10h]
0x180009433  mov     rcx, [r12]
0x180009437  mov     eax, [rax]
0x180009439  mov     [rcx+4], eax
0x18000943c  xor     ecx, ecx; String
0x18000943e  call    cs:__imp_wcstok
0x180009445  nop     dword ptr [rax+rax+00h]
0x18000944a  mov     rcx, rax; String
0x18000944d  call    cs:__imp__wtof
0x180009454  nop     dword ptr [rax+rax+00h]
0x180009459  cvttsd2si eax, xmm0
0x18000945d  cvttsd2si rcx, xmm0
0x180009462  movd    xmm1, eax
0x180009466  mov     rax, [r13+0]
0x18000946a  cvtdq2pd xmm1, xmm1
0x18000946e  movsd   qword ptr [rax+8], xmm1
0x180009473  mov     rax, [r14]
0x180009476  mov     [rax+4], ecx
0x180009479  mov     rax, [rdi+10h]
0x18000947d  mov     dword ptr [rax+4], 1
0x180009484  mov     rax, [r14]
0x180009487  mov     rcx, [r12]
0x18000948b  mov     eax, [rax+4]
0x18000948e  mov     [rcx+8], eax
0x180009491  mov     rax, [rdi+10h]
0x180009495  mov     rcx, [r12]
0x180009499  mov     eax, [rax+4]
0x18000949c  mov     [rcx+0Ch], eax
0x18000949f  mov     rax, [r13+0]
0x1800094a3  subsd   xmm0, qword ptr [rax+8]
0x1800094a8  mulsd   xmm0, cs:__real@404e000000000000
0x1800094b0  movsd   qword ptr [rax+10h], xmm0
0x1800094b5  mov     rax, [r14]
0x1800094b8  mulsd   xmm0, cs:__real@40c3880000000000
0x1800094c0  cvttsd2si rcx, xmm0
0x1800094c5  mov     [rax+8], ecx
0x1800094c8  mov     rax, [rdi+10h]
0x1800094cc  mov     dword ptr [rax+8], 2710h
0x1800094d3  mov     rax, [r14]
0x1800094d6  mov     rcx, [r12]
0x1800094da  mov     eax, [rax+8]
0x1800094dd  mov     [rcx+10h], eax
0x1800094e0  mov     rax, [rdi+10h]
0x1800094e4  mov     rcx, [r12]
0x1800094e8  mov     eax, [rax+8]
0x1800094eb  mov     [rcx+14h], eax
0x1800094ee  movzx   eax, bp
0x1800094f1  mov     ebx, r15d
0x1800094f4  cmp     eax, 65h ; 'e'
0x1800094f7  jnz     short loc_180009510
0x1800094f9  mov     rax, [r12]; jumptable 0000000180009615 case 69
0x1800094fd  mov     [rax+18h], rsi
0x180009501  jmp     def_180009615; jumptable 0000000180009615 default case, cases 70-77,79-82,84-86,88-114,116-118
0x180009506  mov     ebx, 80070216h
0x18000950b  jmp     def_180009615; jumptable 0000000180009615 default case, cases 70-77,79-82,84-86,88-114,116-118
0x180009510  cmp     eax, 6Eh ; 'n'
0x180009513  jnz     loc_1800095EE
0x180009519  mov     rax, [r12]; jumptable 0000000180009615 case 78
0x18000951d  mov     qword ptr [rax+18h], 1
0x180009525  jmp     def_180009615; jumptable 0000000180009615 default case, cases 70-77,79-82,84-86,88-114,116-118
0x18000952a  mov     ebx, 8007000Eh
0x18000952f  jmp     def_180009615; jumptable 0000000180009615 default case, cases 70-77,79-82,84-86,88-114,116-118
0x180009534  mov     rdx, r13
0x180009537  jmp     loc_18000920E
0x18000953c  test    r9d, r9d
0x18000953f  jnz     loc_180009248
0x180009545  xor     r8d, r8d; Context
0x180009548  lea     rdx, Delimiter; ","
0x18000954f  mov     rcx, r10; String
0x180009552  call    cs:__imp_wcstok
0x180009559  nop     dword ptr [rax+rax+00h]
0x18000955e  mov     rsi, rax
0x180009561  test    rsi, rsi
0x180009564  jz      short loc_1800095E1
0x180009566  mov     rcx, rsi; String
0x180009569  call    cs:__imp__wtof
0x180009570  nop     dword ptr [rax+rax+00h]
0x180009575  mov     rcx, [r13+0]
0x180009579  mov     ebx, r15d
0x18000957c  movsd   qword ptr [rcx+rbx*8], xmm0
0x180009581  mov     rcx, rsi
0x180009584  call    cs:__imp__o__wtol
0x18000958b  nop     dword ptr [rax+rax+00h]
0x180009590  mov     rcx, [r14]
0x180009593  lea     rdx, Delimiter; ","
0x18000959a  xor     r8d, r8d; Context
0x18000959d  mov     [rcx+rbx*4], eax
0x1800095a0  mov     rax, [rdi+10h]
0x1800095a4  mov     dword ptr [rax+rbx*4], 1
0x1800095ab  mov     rax, [r14]
0x1800095ae  mov     rcx, [r12]
0x1800095b2  mov     eax, [rax+rbx*4]
0x1800095b5  mov     [rcx+rbx*8], eax
0x1800095b8  mov     rax, [rdi+10h]
0x1800095bc  mov     rcx, [r12]
0x1800095c0  mov     eax, [rax+rbx*4]
0x1800095c3  mov     [rcx+rbx*8+4], eax
0x1800095c7  xor     ecx, ecx; String
0x1800095c9  call    cs:__imp_wcstok
0x1800095d0  nop     dword ptr [rax+rax+00h]
0x1800095d5  inc     r15d
0x1800095d8  mov     rsi, rax
0x1800095db  cmp     r15d, 3
0x1800095df  jl      short loc_180009561
0x1800095e1  mov     esi, 3
0x1800095e6  xor     r15d, r15d
0x1800095e9  jmp     loc_1800094EE
0x1800095ee  add     eax, 0FFFFFFBBh; switch 51 cases
0x1800095f1  cmp     eax, 32h
0x1800095f4  ja      def_180009615; jumptable 0000000180009615 default case, cases 70-77,79-82,84-86,88-114,116-118
0x1800095fa  lea     rdx, __ImageBase
0x180009601  cdqe
  ... truncated ...
```
