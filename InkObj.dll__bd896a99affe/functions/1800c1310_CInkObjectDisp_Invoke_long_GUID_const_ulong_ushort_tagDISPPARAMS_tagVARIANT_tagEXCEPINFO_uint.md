# CInkObjectDisp::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x1800c1310`
- end: `0x1800c179a`
- name: `?Invoke@CInkObjectDisp@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `1162`
- prototype: `int(CInkObjectDisp *__hidden this, int, const struct _GUID *, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180049d50`
- `0x1800575a8`
- `0x1800a3324`
- `0x1800b9e84`
- `0x1800c1310`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x1800c140f`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c1450`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c1511`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c155f`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c1650`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c1688`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c16d2`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c1770`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c140f`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c1450`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c1511`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c155f`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c1650`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c1688`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c16d2`
- `OLEAUT32!__imp_VariantCopy` at `0x1800c1770`

## pseudocode

```c
__int64 __fastcall CInkObjectDisp::Invoke(
        struct IDispatch *this,
        int a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6,
        struct tagVARIANT *a7,
        struct tagEXCEPINFO *a8,
        unsigned int *a9)
{
  struct tagDISPPARAMS *v9; // r14
  VARIANTARG *v10; // rbx
  LCID lcid; // r13d
  int v12; // edi
  UINT v13; // ecx
  UINT v14; // ecx
  UINT v15; // ecx
  VARIANTARG *v16; // r13
  const VARIANTARG *v17; // rdx
  char v18; // r15
  HRESULT v19; // eax
  const VARIANTARG *v20; // rdx
  char v21; // r13
  VARIANTARG *v22; // r14
  HRESULT v23; // eax
  unsigned int v24; // edx
  unsigned int v25; // edi
  VARIANTARG *v27; // r13
  const VARIANTARG *v28; // rdx
  char v29; // r15
  HRESULT v30; // eax
  const VARIANTARG *v31; // rdx
  char v32; // si
  VARIANTARG *v33; // r14
  HRESULT v34; // eax
  VARIANTARG *v35; // rcx
  VARIANTARG *v36; // rcx
  __int64 v37; // rdx
  UINT v38; // ecx
  UINT v39; // ecx
  UINT v40; // ecx
  VARIANTARG *v41; // r13
  const VARIANTARG *v42; // rdx
  char v43; // r15
  HRESULT v44; // eax
  const VARIANTARG *v45; // rdx
  char v46; // r14
  HRESULT v47; // eax
  const VARIANTARG *v48; // rdx
  char v49; // r15
  VARIANTARG *v50; // r14
  HRESULT v51; // eax
  UINT cArgs; // ecx
  UINT v53; // ecx
  const VARIANTARG *rgvarg; // rdx
  char v55; // r14
  VARIANTARG *pvargDest; // [rsp+50h] [rbp-20h] BYREF
  struct tagDISPPARAMS v57; // [rsp+58h] [rbp-18h] BYREF
  LCID v60; // [rsp+C8h] [rbp+58h]

  v60 = (unsigned int)a4;
  v9 = a6;
  v10 = 0;
  pvargDest = 0;
  lcid = (unsigned int)a4;
  v12 = a2;
  memset(&v57, 0, sizeof(v57));
  if ( !a6 || a6->cNamedArgs )
    goto LABEL_27;
  switch ( a2 )
  {
    case 4:
      goto LABEL_46;
    case 6:
      _RepackDispatchArguments(2, 1, &a6, &v57, (struct ATL::CComVariant **)&pvargDest);
      v10 = pvargDest;
      if ( !pvargDest )
        break;
      cArgs = v9->cArgs;
      if ( cArgs )
      {
        v53 = cArgs - 1;
        if ( v53 )
        {
          if ( v53 != 1 )
            goto LABEL_26;
          rgvarg = v9->rgvarg;
          v55 = 0;
          if ( pvargDest->vt == 4095 )
          {
            pvargDest->vt = 8;
            v55 = 1;
          }
          v47 = VariantCopy(v10, rgvarg);
          if ( v55 )
            v10->vt = 4095;
          v12 = a2;
          if ( v47 >= 0 )
            goto LABEL_26;
          v10->vt = 10;
          goto LABEL_65;
        }
      }
      v37 = 1;
LABEL_74:
      v36 = v10;
      goto LABEL_75;
    case 23:
      _RepackDispatchArguments(3, 1, &a6, &v57, (struct ATL::CComVariant **)&pvargDest);
      v10 = pvargDest;
      if ( !pvargDest )
        break;
      v38 = v9->cArgs;
      if ( v38 )
      {
        v39 = v38 - 1;
        if ( v39 )
        {
          v40 = v39 - 1;
          if ( !v40 )
          {
            v48 = v9->rgvarg;
            v49 = 0;
            v50 = pvargDest + 1;
            if ( pvargDest[1].vt == 4095 )
            {
              v50->vt = 8;
              v49 = 1;
            }
            v51 = VariantCopy(v10 + 1, v48);
            if ( v49 )
              v50->vt = 4095;
            if ( v51 < 0 )
            {
              v50->vt = 10;
              v10[1].lVal = v51;
            }
            v35 = v10;
            goto LABEL_44;
          }
          if ( v40 != 1 )
            goto LABEL_26;
          v41 = pvargDest + 1;
          v42 = v9->rgvarg + 1;
          v43 = 0;
          if ( pvargDest[1].vt == 4095 )
          {
            v41->vt = 8;
            v43 = 1;
          }
          v44 = VariantCopy(v10 + 1, v42);
          if ( v43 )
            v41->vt = 4095;
          if ( v44 < 0 )
          {
            v41->vt = 10;
            v10[1].lVal = v44;
          }
          v45 = v9->rgvarg;
          v46 = 0;
          if ( v10->vt == 4095 )
          {
            v10->vt = 8;
            v46 = 1;
          }
          v47 = VariantCopy(v10, v45);
          if ( v46 )
            v10->vt = 4095;
          v12 = a2;
          lcid = v60;
          if ( v47 >= 0 )
            goto LABEL_26;
          v10->vt = 10;
LABEL_65:
          v10->lVal = v47;
          goto LABEL_26;
        }
      }
      ATL::CComVariant::operator=(&pvargDest[1], 127);
      v37 = 0;
      goto LABEL_74;
    case 24:
LABEL_46:
      _RepackDispatchArguments(1, 1, &a6, &v57, (struct ATL::CComVariant **)&pvargDest);
      v10 = pvargDest;
      if ( pvargDest )
        goto LABEL_26;
      break;
    case 25:
      _RepackDispatchArguments(3, 3, &a6, &v57, (struct ATL::CComVariant **)&pvargDest);
      v10 = pvargDest;
      if ( pvargDest )
      {
        v13 = v9->cArgs;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            v15 = v14 - 1;
            if ( !v15 )
            {
              v27 = pvargDest + 2;
              v28 = v9->rgvarg + 1;
              v29 = 0;
              if ( pvargDest[2].vt == 4095 )
              {
                v27->vt = 8;
                v29 = 1;
              }
              v30 = VariantCopy(v10 + 2, v28);
              if ( v29 )
                v27->vt = 4095;
              if ( v30 < 0 )
              {
                v27->vt = 10;
                v10[2].lVal = v30;
              }
              v20 = v9->rgvarg;
              goto LABEL_20;
            }
            if ( v15 == 1 )
            {
              v16 = pvargDest + 2;
              v17 = v9->rgvarg + 2;
              v18 = 0;
              if ( pvargDest[2].vt == 4095 )
              {
                v16->vt = 8;
                v18 = 1;
              }
              v19 = VariantCopy(v10 + 2, v17);
              if ( v18 )
                v16->vt = 4095;
              if ( v19 < 0 )
              {
                v16->vt = 10;
                v10[2].lVal = v19;
              }
              v20 = v9->rgvarg + 1;
LABEL_20:
              v21 = 0;
              v22 = v10 + 1;
              if ( v10[1].vt == 4095 )
              {
                v22->vt = 8;
                v21 = 1;
              }
              v23 = VariantCopy(v10 + 1, v20);
              if ( v21 )
                v22->vt = 4095;
              v12 = a2;
              lcid = v60;
              if ( v23 < 0 )
              {
                v22->vt = 10;
                v10[1].lVal = v23;
              }
            }
LABEL_26:
            v9 = &v57;
            break;
          }
          v31 = v9->rgvarg;
          v32 = 0;
          v33 = pvargDest + 2;
          if ( pvargDest[2].vt == 4095 )
          {
            v33->vt = 8;
            v32 = 1;
          }
          v34 = VariantCopy(v10 + 2, v31);
          if ( v32 )
            v33->vt = 4095;
          if ( v34 < 0 )
          {
            v33->vt = 10;
            v10[2].lVal = v34;
          }
          v35 = v10 + 1;
LABEL_44:
          ATL::CComVariant::operator=(v35, 0);
          v12 = a2;
          goto LABEL_26;
        }
        ATL::CComVariant::operator=(&pvargDest[2], 0);
        v36 = v10 + 1;
        v37 = 0;
LABEL_75:
        ATL::CComVariant::operator=(v36, v37);
        goto LABEL_26;
      }
      break;
  }
LABEL_27:
  v25 = ATL::CComTypeInfoHolder::Invoke(
          (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IInkDisp,&_GUID const IID_IInkDisp,&_GUID const LIBID_MSINKAUTLib,1,0,ATL::CComTypeInfoHolder>::_tih,
          this,
          v12,
          a4,
          lcid,
          a5,
          v9,
          a7,
          a8,
          a9);
  if ( v10 )
    ATL::CComVariant::`vector deleting destructor'((ATL::CComVariant *)v10, v24);
  return v25;
}

```

## disassembly

```asm
0x1800c1310  mov     rax, rsp
0x1800c1313  mov     [rax+18h], rbx
0x1800c1317  mov     [rax+20h], r9d
0x1800c131b  mov     [rax+10h], edx
0x1800c131e  mov     [rax+8], rcx
0x1800c1322  push    rbp
0x1800c1323  push    rsi
0x1800c1324  push    rdi
0x1800c1325  push    r12
0x1800c1327  push    r13
0x1800c1329  push    r14
0x1800c132b  push    r15
0x1800c132d  mov     rbp, rsp
0x1800c1330  sub     rsp, 70h
0x1800c1334  mov     r14, [rbp+arg_28]
0x1800c1338  xor     ebx, ebx
0x1800c133a  mov     qword ptr [rbp+var_18.cArgs], 0
0x1800c1342  xorps   xmm0, xmm0
0x1800c1345  mov     [rbp+pvargDest], rbx
0x1800c1349  mov     r13d, r9d
0x1800c134c  mov     edi, edx
0x1800c134e  movdqu  xmmword ptr [rbp+var_18.rgvarg], xmm0
0x1800c1353  test    r14, r14
0x1800c1356  jz      loc_1800C1476
0x1800c135c  cmp     [r14+14h], ebx
0x1800c1360  jnz     loc_1800C1476
0x1800c1366  mov     ecx, edx
0x1800c1368  sub     ecx, 4
0x1800c136b  jz      loc_1800C15A5
0x1800c1371  sub     ecx, 2
0x1800c1374  jz      loc_1800C1714
0x1800c137a  sub     ecx, 11h
0x1800c137d  jz      loc_1800C15D6
0x1800c1383  sub     ecx, 1
0x1800c1386  jz      loc_1800C15A5
0x1800c138c  cmp     ecx, 1
0x1800c138f  jnz     loc_1800C1476
0x1800c1395  lea     ecx, [rbx+3]; int
0x1800c1398  lea     rax, [rbp+pvargDest]
0x1800c139c  mov     edx, ecx; int
0x1800c139e  lea     r9, [rbp+var_18]; struct tagDISPPARAMS *
0x1800c13a2  mov     qword ptr [rsp+70h+lcid], rax; struct ATL::CComVariant **
0x1800c13a7  lea     r8, [rbp+arg_28]; struct tagDISPPARAMS **
0x1800c13ab  call    ?_RepackDispatchArguments@@YAJJJAEAPEAUtagDISPPARAMS@@AEAU1@AEAPEAVCComVariant@ATL@@@Z; _RepackDispatchArguments(long,long,tagDISPPARAMS * &,tagDISPPARAMS &,ATL::CComVariant * &)
0x1800c13b0  mov     rbx, [rbp+pvargDest]
0x1800c13b4  test    rbx, rbx
0x1800c13b7  jz      loc_1800C1476
0x1800c13bd  mov     ecx, [r14+10h]
0x1800c13c1  test    ecx, ecx
0x1800c13c3  jz      loc_1800C158F
0x1800c13c9  sub     ecx, 1
0x1800c13cc  jz      loc_1800C153C
0x1800c13d2  sub     ecx, 1
0x1800c13d5  jz      loc_1800C14E3
0x1800c13db  cmp     ecx, 1
0x1800c13de  jnz     loc_1800C1472
0x1800c13e4  mov     rdx, [r14]
0x1800c13e7  lea     r13, [rbx+30h]
0x1800c13eb  add     rdx, 30h ; '0'; pvargSrc
0x1800c13ef  lea     r12d, [rcx+7]
0x1800c13f3  xor     r15b, r15b
0x1800c13f6  mov     edi, 0FFFh
0x1800c13fb  mov     esi, ecx
0x1800c13fd  cmp     [r13+0], di
0x1800c1402  jnz     short loc_1800C140C
0x1800c1404  mov     [r13+0], r12w
0x1800c1409  mov     r15b, sil
0x1800c140c  mov     rcx, r13; pvargDest
0x1800c140f  call    cs:__imp_VariantCopy
0x1800c1415  test    r15b, r15b
0x1800c1418  jz      short loc_1800C141F
0x1800c141a  mov     [r13+0], di
0x1800c141f  mov     r15d, 0Ah
0x1800c1425  test    eax, eax
0x1800c1427  jns     short loc_1800C1432
0x1800c1429  mov     [r13+0], r15w
0x1800c142e  mov     [r13+8], eax
0x1800c1432  mov     rdx, [r14]
0x1800c1435  add     rdx, 18h; pvargSrc
0x1800c1439  xor     r13b, r13b
0x1800c143c  lea     r14, [rbx+18h]
0x1800c1440  cmp     [r14], di
0x1800c1444  jnz     short loc_1800C144D
0x1800c1446  mov     [r14], r12w
0x1800c144a  mov     r13b, sil
0x1800c144d  mov     rcx, r14; pvargDest
0x1800c1450  call    cs:__imp_VariantCopy
0x1800c1456  test    r13b, r13b
0x1800c1459  jz      short loc_1800C145F
0x1800c145b  mov     [r14], di
0x1800c145f  mov     edi, [rbp+arg_8]
0x1800c1462  mov     r13d, [rbp+arg_18]
0x1800c1466  test    eax, eax
0x1800c1468  jns     short loc_1800C1472
0x1800c146a  mov     [r14], r15w
0x1800c146e  mov     [r14+8], eax
0x1800c1472  lea     r14, [rbp+var_18]
0x1800c1476  mov     rax, [rbp+arg_40]
0x1800c147d  lea     rcx, ?_tih@?$IDispatchImpl@UIInkDisp@@$1?IID_IInkDisp@@3U_GUID@@B$1?LIBID_MSINKAUTLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800c1484  mov     rdx, [rbp+arg_0]; struct IDispatch *
0x1800c1488  mov     r8d, edi; int
0x1800c148b  mov     [rsp+70h+var_28], rax; unsigned int *
0x1800c1490  mov     rax, [rbp+arg_38]
0x1800c1494  mov     [rsp+70h+var_30], rax; struct tagEXCEPINFO *
0x1800c1499  mov     rax, [rbp+arg_30]
0x1800c149d  mov     [rsp+70h+var_38], rax; struct tagVARIANT *
0x1800c14a2  movzx   eax, [rbp+arg_20]
0x1800c14a6  mov     [rsp+70h+var_40], r14; struct tagDISPPARAMS *
0x1800c14ab  mov     [rsp+70h+var_48], ax; unsigned __int16
0x1800c14b0  mov     [rsp+70h+lcid], r13d; lcid
0x1800c14b5  call    ?Invoke@CComTypeInfoHolder@ATL@@QEAAJPEAUIDispatch@@JAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z; ATL::CComTypeInfoHolder::Invoke(IDispatch *,long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)
0x1800c14ba  mov     edi, eax
0x1800c14bc  test    rbx, rbx
0x1800c14bf  jz      short loc_1800C14C9
0x1800c14c1  mov     rcx, rbx; this
0x1800c14c4  call    ??_ECComVariant@ATL@@QEAAPEAXI@Z; ATL::CComVariant::`vector deleting destructor'(uint)
0x1800c14c9  mov     rbx, [rsp+70h+arg_10]
0x1800c14d1  mov     eax, edi
0x1800c14d3  add     rsp, 70h
0x1800c14d7  pop     r15
0x1800c14d9  pop     r14
0x1800c14db  pop     r13
0x1800c14dd  pop     r12
0x1800c14df  pop     rdi
0x1800c14e0  pop     rsi
0x1800c14e1  pop     rbp
0x1800c14e2  retn
0x1800c14e3  mov     rdx, [r14]
0x1800c14e6  lea     r13, [rbx+30h]
0x1800c14ea  mov     esi, 1
0x1800c14ef  add     rdx, 18h; pvargSrc
0x1800c14f3  xor     r15b, r15b
0x1800c14f6  mov     edi, 0FFFh
0x1800c14fb  lea     r12d, [rsi+7]
0x1800c14ff  cmp     [r13+0], di
0x1800c1504  jnz     short loc_1800C150E
0x1800c1506  mov     [r13+0], r12w
0x1800c150b  mov     r15b, sil
0x1800c150e  mov     rcx, r13; pvargDest
0x1800c1511  call    cs:__imp_VariantCopy
0x1800c1517  test    r15b, r15b
0x1800c151a  jz      short loc_1800C1521
0x1800c151c  mov     [r13+0], di
0x1800c1521  mov     r15d, 0Ah
0x1800c1527  test    eax, eax
0x1800c1529  jns     short loc_1800C1534
0x1800c152b  mov     [r13+0], r15w
0x1800c1530  mov     [r13+8], eax
0x1800c1534  mov     rdx, [r14]
0x1800c1537  jmp     loc_1800C1439
0x1800c153c  mov     rdx, [r14]; pvargSrc
0x1800c153f  xor     sil, sil
0x1800c1542  lea     r14, [rbx+30h]
0x1800c1546  mov     edi, 0FFFh
0x1800c154b  cmp     [r14], di
0x1800c154f  jnz     short loc_1800C155C
0x1800c1551  mov     word ptr [r14], 8
0x1800c1557  mov     esi, 1
0x1800c155c  mov     rcx, r14; pvargDest
0x1800c155f  call    cs:__imp_VariantCopy
0x1800c1565  test    sil, sil
0x1800c1568  jz      short loc_1800C156E
0x1800c156a  mov     [r14], di
0x1800c156e  test    eax, eax
0x1800c1570  jns     short loc_1800C157C
0x1800c1572  mov     word ptr [r14], 0Ah
0x1800c1578  mov     [r14+8], eax
0x1800c157c  lea     rcx, [rbx+18h]
0x1800c1580  xor     edx, edx
0x1800c1582  call    ??4CComVariant@ATL@@QEAAAEAV01@J@Z; ATL::CComVariant::operator=(long)
0x1800c1587  mov     edi, [rbp+arg_8]
0x1800c158a  jmp     loc_1800C1472
0x1800c158f  lea     rcx, [rbx+30h]
0x1800c1593  xor     edx, edx
0x1800c1595  call    ??4CComVariant@ATL@@QEAAAEAV01@J@Z; ATL::CComVariant::operator=(long)
0x1800c159a  lea     rcx, [rbx+18h]
0x1800c159e  xor     edx, edx
0x1800c15a0  jmp     loc_1800C170A
0x1800c15a5  mov     esi, 1
0x1800c15aa  lea     rax, [rbp+pvargDest]
0x1800c15ae  mov     edx, esi; int
0x1800c15b0  mov     qword ptr [rsp+70h+lcid], rax; struct ATL::CComVariant **
0x1800c15b5  mov     ecx, esi; int
0x1800c15b7  lea     r9, [rbp+var_18]; struct tagDISPPARAMS *
0x1800c15bb  lea     r8, [rbp+arg_28]; struct tagDISPPARAMS **
0x1800c15bf  call    ?_RepackDispatchArguments@@YAJJJAEAPEAUtagDISPPARAMS@@AEAU1@AEAPEAVCComVariant@ATL@@@Z; _RepackDispatchArguments(long,long,tagDISPPARAMS * &,tagDISPPARAMS &,ATL::CComVariant * &)
0x1800c15c4  mov     rbx, [rbp+pvargDest]
0x1800c15c8  test    rbx, rbx
0x1800c15cb  jnz     loc_1800C1472
0x1800c15d1  jmp     loc_1800C1476
0x1800c15d6  mov     esi, 1
0x1800c15db  lea     rax, [rbp+pvargDest]
0x1800c15df  lea     r9, [rbp+var_18]; struct tagDISPPARAMS *
0x1800c15e3  mov     qword ptr [rsp+70h+lcid], rax; struct ATL::CComVariant **
0x1800c15e8  lea     r8, [rbp+arg_28]; struct tagDISPPARAMS **
0x1800c15ec  mov     edx, esi; int
0x1800c15ee  lea     ecx, [rsi+2]; int
0x1800c15f1  call    ?_RepackDispatchArguments@@YAJJJAEAPEAUtagDISPPARAMS@@AEAU1@AEAPEAVCComVariant@ATL@@@Z; _RepackDispatchArguments(long,long,tagDISPPARAMS * &,tagDISPPARAMS &,ATL::CComVariant * &)
0x1800c15f6  mov     rbx, [rbp+pvargDest]
0x1800c15fa  test    rbx, rbx
0x1800c15fd  jz      loc_1800C1476
0x1800c1603  mov     ecx, [r14+10h]
0x1800c1607  test    ecx, ecx
0x1800c1609  jz      loc_1800C16F7
0x1800c160f  sub     ecx, esi
0x1800c1611  jz      loc_1800C16F7
0x1800c1617  sub     ecx, esi
0x1800c1619  jz      loc_1800C16B1
0x1800c161f  cmp     ecx, esi
0x1800c1621  jnz     loc_1800C1472
0x1800c1627  mov     rdx, [r14]
0x1800c162a  lea     r13, [rbx+18h]
0x1800c162e  add     rdx, 18h; pvargSrc
0x1800c1632  lea     r12d, [rsi+7]
0x1800c1636  xor     r15b, r15b
0x1800c1639  mov     edi, 0FFFh
0x1800c163e  cmp     [r13+0], di
0x1800c1643  jnz     short loc_1800C164D
0x1800c1645  mov     [r13+0], r12w
0x1800c164a  mov     r15b, sil
0x1800c164d  mov     rcx, r13; pvargDest
0x1800c1650  call    cs:__imp_VariantCopy
0x1800c1656  test    r15b, r15b
0x1800c1659  jz      short loc_1800C1660
0x1800c165b  mov     [r13+0], di
0x1800c1660  mov     r15d, 0Ah
0x1800c1666  test    eax, eax
0x1800c1668  jns     short loc_1800C1673
0x1800c166a  mov     [r13+0], r15w
0x1800c166f  mov     [r13+8], eax
0x1800c1673  mov     rdx, [r14]; pvargSrc
0x1800c1676  xor     r14b, r14b
0x1800c1679  cmp     [rbx], di
0x1800c167c  jnz     short loc_1800C1685
0x1800c167e  mov     [rbx], r12w
0x1800c1682  mov     r14b, sil
0x1800c1685  mov     rcx, rbx; pvargDest
0x1800c1688  call    cs:__imp_VariantCopy
0x1800c168e  test    r14b, r14b
0x1800c1691  jz      short loc_1800C1696
0x1800c1693  mov     [rbx], di
0x1800c1696  mov     edi, [rbp+arg_8]
0x1800c1699  mov     r13d, [rbp+arg_18]
0x1800c169d  test    eax, eax
0x1800c169f  jns     loc_1800C1472
0x1800c16a5  mov     [rbx], r15w
0x1800c16a9  mov     [rbx+8], eax
0x1800c16ac  jmp     loc_1800C1472
0x1800c16b1  mov     rdx, [r14]; pvargSrc
0x1800c16b4  xor     r15b, r15b
0x1800c16b7  lea     r14, [rbx+18h]
0x1800c16bb  mov     edi, 0FFFh
0x1800c16c0  cmp     [r14], di
0x1800c16c4  jnz     short loc_1800C16CF
0x1800c16c6  mov     word ptr [r14], 8
0x1800c16cc  mov     r15b, sil
0x1800c16cf  mov     rcx, r14; pvargDest
0x1800c16d2  call    cs:__imp_VariantCopy
0x1800c16d8  test    r15b, r15b
0x1800c16db  jz      short loc_1800C16E1
0x1800c16dd  mov     [r14], di
0x1800c16e1  test    eax, eax
0x1800c16e3  jns     short loc_1800C16EF
0x1800c16e5  mov     word ptr [r14], 0Ah
0x1800c16eb  mov     [r14+8], eax
0x1800c16ef  mov     rcx, rbx
0x1800c16f2  jmp     loc_1800C1580
0x1800c16f7  lea     rcx, [rbx+18h]
0x1800c16fb  mov     edx, 7Fh
0x1800c1700  call    ??4CComVariant@ATL@@QEAAAEAV01@J@Z; ATL::CComVariant::operator=(long)
0x1800c1705  xor     edx, edx
0x1800c1707  mov     rcx, rbx
0x1800c170a  call    ??4CComVariant@ATL@@QEAAAEAV01@J@Z; ATL::CComVariant::operator=(long)
0x1800c170f  jmp     loc_1800C1472
0x1800c1714  mov     esi, 1
0x1800c1719  lea     rax, [rbp+pvargDest]
0x1800c171d  lea     r9, [rbp+var_18]; struct tagDISPPARAMS *
0x1800c1721  mov     qword ptr [rsp+70h+lcid], rax; struct ATL::CComVariant **
0x1800c1726  lea     r8, [rbp+arg_28]; struct tagDISPPARAMS **
0x1800c172a  mov     edx, esi; int
0x1800c172c  lea     ecx, [rsi+1]; int
0x1800c172f  call    ?_RepackDispatchArguments@@YAJJJAEAPEAUtagDISPPARAMS@@AEAU1@AEAPEAVCComVariant@ATL@@@Z; _RepackDispatchArguments(long,long,tagDISPPARAMS * &,tagDISPPARAMS &,ATL::CComVariant * &)
0x1800c1734  mov     rbx, [rbp+pvargDest]
0x1800c1738  test    rbx, rbx
0x1800c173b  jz      loc_1800C1476
0x1800c1741  mov     ecx, [r14+10h]
0x1800c1745  test    ecx, ecx
0x1800c1747  jz      short loc_1800C1793
0x1800c1749  sub     ecx, esi
0x1800c174b  jz      short loc_1800C1793
0x1800c174d  cmp     ecx, esi
0x1800c174f  jnz     loc_1800C1472
0x1800c1755  mov     rdx, [r14]; pvargSrc
0x1800c1758  mov     edi, 0FFFh
0x1800c175d  xor     r14b, r14b
0x1800c1760  cmp     [rbx], di
0x1800c1763  jnz     short loc_1800C176D
0x1800c1765  mov     word ptr [rbx], 8
0x1800c176a  mov     r14b, sil
0x1800c176d  mov     rcx, rbx; pvargDest
  ... truncated ...
```
