# CXMLReader::ProcessRowsetAttribute(ulong,ushort *,ushort *,CXMLRowset *)

- ea: `0x1800272f0`
- end: `0x180027696`
- name: `?ProcessRowsetAttribute@CXMLReader@@AEAAJKPEAG0PEAVCXMLRowset@@@Z`
- size: `934`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, unsigned int, unsigned __int16 *, unsigned __int16 *, struct CXMLRowset *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025a7c`
- `0x18002769c`

## callees

- `0x180001d94`
- `0x180001dd8`
- `0x1800185c0`
- `0x180026560`
- `0x1800272f0`
- `0x180027c4c`
- `0x180028724`
- `0x180028ee0`
- `0x18002ad20`
- `0x18002ca58`
- `0x18002e02a`
- `0x18002e060`
- `0x180030010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800275cc`
- `msvcrt!wcschr` at `0x1800275cc`
- `OLEAUT32!__imp_SysStringLen` at `0x180027431`
- `OLEAUT32!__imp_SysStringLen` at `0x180027533`
- `OLEAUT32!__imp_SysStringLen` at `0x180027431`
- `OLEAUT32!__imp_SysStringLen` at `0x180027533`
- `OLEAUT32!__imp_VariantInit` at `0x18002741d`
- `OLEAUT32!__imp_VariantInit` at `0x18002741d`
- `OLEAUT32!__imp_VariantClear` at `0x180027501`
- `OLEAUT32!__imp_VariantClear` at `0x180027501`
- `OLEAUT32!__imp_VariantChangeType` at `0x180027457`
- `OLEAUT32!__imp_VariantChangeType` at `0x180027457`

## pseudocode

```c
__int64 __fastcall CXMLReader::ProcessRowsetAttribute(
        CCollectionList **this,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        struct CXMLRowset *a5)
{
  unsigned int v6; // edi
  int v7; // eax
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rax
  VARTYPE v11; // di
  unsigned __int64 v12; // rax
  GUID v13; // xmm0
  struct tagDBPROPIDSET near *v14; // rax
  unsigned int v15; // edx
  CUtlProps *v16; // r14
  const struct CBidGenericBase *v17; // r13
  __int64 v18; // rax
  unsigned int v19; // edx
  UINT v20; // edi
  unsigned int v21; // edx
  unsigned __int8 *v22; // rax
  unsigned __int8 *v23; // rbx
  wchar_t *v24; // rbx
  wchar_t *v25; // rax
  wchar_t *v26; // r12
  __int64 v27; // rsi
  CCollectionList *v28; // rcx
  int v30; // [rsp+30h] [rbp-A1h] BYREF
  unsigned int v31[2]; // [rsp+38h] [rbp-99h] BYREF
  unsigned __int64 v32; // [rsp+40h] [rbp-91h] BYREF
  _QWORD pvarSrc[4]; // [rsp+48h] [rbp-89h] BYREF
  struct tagDBPROPSET v34; // [rsp+68h] [rbp-69h] BYREF
  int v35; // [rsp+90h] [rbp-41h] BYREF
  __int64 v36; // [rsp+94h] [rbp-3Dh]
  DBID v37; // [rsp+A0h] [rbp-31h]
  VARIANTARG pvarg; // [rsp+C0h] [rbp-11h] BYREF

  memset(pvarSrc, 0, sizeof(pvarSrc));
  v6 = 0;
  if ( CXMLReader::LookupAttributeInfo((CXMLReader *)this, a2, a3, a4, (struct tagDBATTRIBINFO *)pvarSrc) )
    return v6;
  v7 = *((_DWORD *)this + 120);
  if ( v7 != 3 )
  {
    if ( v7 != 5 )
      return v6;
    if ( HIDWORD(pvarSrc[0]) != 1 )
      return v6;
    v24 = (wchar_t *)pvarSrc[2];
    v32 = 0;
    if ( !*(_WORD *)pvarSrc[2] )
      return v6;
    do
    {
      v25 = wcschr(v24, 0x20u);
      v26 = v25;
      if ( v25 )
      {
        v27 = v25 - v24;
      }
      else
      {
        v27 = -1;
        do
          ++v27;
        while ( v24[v27] );
      }
      v28 = this[17];
      *(_QWORD *)v31 = 0;
      CCollectionList::LookUpByKey(v28, v24, v27, (unsigned __int64 *)v31);
      if ( *(_QWORD *)v31
        && **(_DWORD **)v31 == 3
        && !(unsigned int)CCollectionList::LookUpByKey((struct CXMLRowset *)((char *)a5 + 552), v24, v27, &v32) )
      {
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a5 + 35) + 8LL * (unsigned int)v32) + 4LL) = 3;
      }
      if ( v26 )
        ++v24;
      v24 += (unsigned int)v27;
    }
    while ( *v24 );
    return 0;
  }
  if ( !XMLProps::m_fInitialized )
    XMLProps::_InitProps();
  v8 = HIDWORD(pvarSrc[0]) - (_DWORD)XMLProps::m_rgRSAttr;
  if ( (unsigned int)(HIDWORD(pvarSrc[0]) - (_DWORD)XMLProps::m_rgRSAttr) > 0xB )
  {
    if ( HIDWORD(pvarSrc[0]) == 16 )
    {
      ATL::CComBSTR::operator=((char *)a5 + 640, pvarSrc[2]);
      return v6;
    }
    if ( HIDWORD(pvarSrc[0]) != 3 )
      return v6;
    v30 = 0;
    v20 = SysStringLen((BSTR)pvarSrc[2]);
    v22 = MMMAlloc(v20 >> 1, v21);
    v23 = v22;
    if ( !v22 )
      return (unsigned int)-2147024882;
    v6 = DecodeBin((unsigned __int16 *)pvarSrc[2], v22, v20, &v30);
    if ( (v6 & 0x80000000) != 0 )
    {
      MMMFree(v23);
      return v6;
    }
    *((_DWORD *)a5 + 154) = v30;
    *((_QWORD *)a5 + 78) = v23;
    return 0;
  }
  memset(&v34, 0, sizeof(v34));
  memset_0(&v35, 0, 0x48u);
  v9 = (unsigned int)(v8 - 3);
  v10 = 0;
  if ( v8 >= 3 )
    v10 = 1;
  else
    v9 = (unsigned int)v8;
  v11 = (VARTYPE)(&XMLProps::m_rgDefaultSets)[v10][3 * v9];
  v34.cProperties = 1;
  v12 = 0;
  if ( v8 >= 3 )
    v12 = 4;
  v34.rgProperties = (DBPROP *)&v35;
  v13 = (GUID)xmmword_18004555C[v12 / 2];
  v14 = (&XMLProps::m_rgPropSets)[v12];
  v34.guidPropertySet = v13;
  v35 = *((_DWORD *)&v14->rgPropertyIDs + v9);
  v36 = 0;
  v37 = DB_NULLID;
  VariantInit(&pvarg);
  if ( v11 != 11 || SysStringLen((BSTR)pvarSrc[2]) )
  {
    v6 = VariantChangeType(&pvarg, (const VARIANTARG *)&pvarSrc[1], 0, v11);
    if ( (v6 & 0x80000000) != 0 )
      return v6;
  }
  else
  {
    pvarg.vt = 11;
    pvarg.iVal = -1;
  }
  v16 = (struct CXMLRowset *)((char *)a5 + 400);
  v17 = (const struct CBidGenericBase *)(this + 62);
  v6 = CUtlProps::utlSetProperties((struct CXMLRowset *)((char *)a5 + 400), v15, 1u, &v34, v17, 1);
  if ( (v6 & 0x80000000) == 0 && HIDWORD(pvarSrc[0]) == 5 && pvarg.iVal == -1 )
  {
    v18 = *(_QWORD *)v16;
    v31[0] = 0;
    v30 = 0;
    (*(void (__fastcall **)(CUtlProps *, GUID *, unsigned int *))(v18 + 8))(v16, &v34.guidPropertySet, v31);
    CUtlProps::GetPropState(v16, v31[0], 0x86u, (enum PROPSTATES *)&v30);
    if ( v30 != 1 )
    {
      v35 = 134;
      v6 = CUtlProps::utlSetProperties(v16, v19, 1u, &v34, v17, 1);
    }
  }
  VariantClear(&pvarg);
  return v6;
}

```

## disassembly

```asm
0x1800272f0  mov     [rsp-8+arg_18], rbx
0x1800272f5  push    rbp
0x1800272f6  push    rsi
0x1800272f7  push    rdi
0x1800272f8  push    r12
0x1800272fa  push    r13
0x1800272fc  push    r14
0x1800272fe  push    r15
0x180027300  lea     rbp, [rsp-1Fh]
0x180027305  sub     rsp, 0F0h
0x18002730c  mov     rax, cs:__security_cookie
0x180027313  xor     rax, rsp
0x180027316  mov     [rbp+4Fh+var_40], rax
0x18002731a  mov     r14, [rbp+4Fh+arg_20]
0x18002731e  lea     rax, [rsp+120h+pvarSrc]
0x180027323  xorps   xmm0, xmm0
0x180027326  mov     [rsp+120h+var_100], rax; struct tagDBATTRIBINFO *
0x18002732b  xor     esi, esi
0x18002732d  mov     r13, rcx
0x180027330  movups  xmmword ptr [rsp+120h+pvarSrc], xmm0
0x180027335  mov     edi, esi
0x180027337  movups  xmmword ptr [rbp+4Fh+pvarSrc+10h], xmm0
0x18002733b  call    ?LookupAttributeInfo@CXMLReader@@AEAAJKPEAG0PEAUtagDBATTRIBINFO@@@Z; CXMLReader::LookupAttributeInfo(ulong,ushort *,ushort *,tagDBATTRIBINFO *)
0x180027340  test    eax, eax
0x180027342  jnz     loc_18002766D
0x180027348  mov     eax, [r13+1E0h]
0x18002734f  cmp     eax, 3
0x180027352  jnz     loc_180027598
0x180027358  cmp     cs:?m_fInitialized@XMLProps@@0KA, esi; ulong XMLProps::m_fInitialized
0x18002735e  jnz     short loc_180027365
0x180027360  call    ?_InitProps@XMLProps@@CAXXZ; XMLProps::_InitProps(void)
0x180027365  mov     eax, dword ptr [rsp+120h+pvarSrc+4]
0x180027369  mov     r12d, 0Bh
0x18002736f  mov     ebx, eax
0x180027371  sub     ebx, cs:?m_rgRSAttr@XMLProps@@0PAW4ROWSETATTRIBUTES@@A; ROWSETATTRIBUTES near * XMLProps::m_rgRSAttr
0x180027377  cmp     ebx, r12d
0x18002737a  ja      loc_18002750C
0x180027380  xorps   xmm0, xmm0
0x180027383  lea     r8d, [r12+3Dh]; Size
0x180027388  xor     edx, edx; Val
0x18002738a  lea     rcx, [rbp+4Fh+var_90]; void *
0x18002738e  movups  xmmword ptr [rbp+4Fh+var_B8.rgProperties], xmm0
0x180027392  movups  xmmword ptr [rbp+4Fh+var_B8.guidPropertySet.Data2], xmm0
0x180027396  call    memset_0
0x18002739b  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x1800273a2  lea     edx, [rbx-3]
0x1800273a5  cmp     ebx, 3
0x1800273a8  lea     r8, cs:180000000h
0x1800273af  mov     rax, rsi
0x1800273b2  cmovl   edx, ebx
0x1800273b5  lea     ecx, [r12-3]
0x1800273ba  cmovge  rax, rcx
0x1800273be  lea     ebx, [r12-0Ah]
0x1800273c3  lea     rcx, [rdx+rdx*2]
0x1800273c7  mov     rax, [rax+r8+45540h]
0x1800273cf  movzx   edi, word ptr [rax+rcx*8]
0x1800273d3  lea     ecx, [r12+15h]
0x1800273d8  mov     [rbp+4Fh+var_B8.cProperties], ebx
0x1800273db  mov     rax, rsi
0x1800273de  cmovge  rax, rcx
0x1800273e2  lea     rcx, [rbp+4Fh+var_90]
0x1800273e6  mov     [rbp+4Fh+var_B8.rgProperties], rcx
0x1800273ea  movups  xmm0, xmmword ptr [rax+r8+4555Ch]
0x1800273f3  mov     rax, [rax+r8+45550h]
0x1800273fb  movdqu  xmmword ptr [rbp+4Fh+var_B8.guidPropertySet.Data1], xmm0
0x180027400  mov     ecx, [rax+rdx*4]
0x180027403  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x18002740a  mov     [rbp+4Fh+var_90], ecx
0x18002740d  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180027411  mov     [rbp+4Fh+var_8C], rsi
0x180027415  movaps  [rbp+4Fh+var_80], xmm0
0x180027419  movaps  [rbp+4Fh+var_70], xmm1
0x18002741d  call    cs:__imp_VariantInit
0x180027423  or      r15, 0FFFFFFFFFFFFFFFFh
0x180027427  cmp     di, r12w
0x18002742b  jnz     short loc_180027447
0x18002742d  mov     rcx, qword ptr [rbp+4Fh+pvarSrc+10h]; pbstr
0x180027431  call    cs:__imp_SysStringLen
0x180027437  test    eax, eax
0x180027439  jnz     short loc_180027447
0x18002743b  mov     word ptr [rbp+4Fh+pvarg], r12w
0x180027440  mov     word ptr [rbp+4Fh+pvarg+8], r15w
0x180027445  jmp     short loc_180027467
0x180027447  xor     r8d, r8d; wFlags
0x18002744a  lea     rdx, [rsp+120h+pvarSrc+8]; pvarSrc
0x18002744f  movzx   r9d, di; vt
0x180027453  lea     rcx, [rbp+4Fh+pvarg]; pvargDest
0x180027457  call    cs:__imp_VariantChangeType
0x18002745d  mov     edi, eax
0x18002745f  test    eax, eax
0x180027461  js      loc_18002766D
0x180027467  add     r14, 190h
0x18002746e  mov     [rsp+120h+var_F8], ebx; int
0x180027472  add     r13, 1F0h
0x180027479  lea     r9, [rbp+4Fh+var_B8]; struct tagDBPROPSET *
0x18002747d  mov     rcx, r14; this
0x180027480  mov     [rsp+120h+var_100], r13; struct CBidGenericBase *
0x180027485  mov     r8d, ebx; unsigned int
0x180027488  call    ?utlSetProperties@CUtlProps@@QEAAJKKQEBUtagDBPROPSET@@AEBVCBidGenericBase@@H@Z; CUtlProps::utlSetProperties(ulong,ulong,tagDBPROPSET const * const,CBidGenericBase const &,int)
0x18002748d  mov     edi, eax
0x18002748f  test    eax, eax
0x180027491  js      short loc_1800274FD
0x180027493  cmp     dword ptr [rsp+120h+pvarSrc+4], 5
0x180027498  jnz     short loc_1800274FD
0x18002749a  cmp     r15w, word ptr [rbp+4Fh+pvarg+8]
0x18002749f  jnz     short loc_1800274FD
0x1800274a1  mov     rax, [r14]
0x1800274a4  lea     r8, [rsp+120h+var_E8]
0x1800274a9  lea     rdx, [rbp+4Fh+var_B8.guidPropertySet]
0x1800274ad  mov     [rsp+120h+var_E8], esi
0x1800274b1  mov     rcx, r14
0x1800274b4  mov     [rsp+120h+var_F0], esi
0x1800274b8  mov     rax, [rax+8]
0x1800274bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274c1  mov     edx, [rsp+120h+var_E8]; unsigned int
0x1800274c5  lea     r9, [rsp+120h+var_F0]; enum PROPSTATES *
0x1800274ca  mov     esi, 86h
0x1800274cf  mov     rcx, r14; this
0x1800274d2  mov     r8d, esi; unsigned int
0x1800274d5  call    ?GetPropState@CUtlProps@@QEAAHKKPEAW4PROPSTATES@@@Z; CUtlProps::GetPropState(ulong,ulong,PROPSTATES *)
0x1800274da  cmp     [rsp+120h+var_F0], ebx
0x1800274de  jz      short loc_1800274FD
0x1800274e0  mov     [rsp+120h+var_F8], ebx; int
0x1800274e4  lea     r9, [rbp+4Fh+var_B8]; struct tagDBPROPSET *
0x1800274e8  mov     r8d, ebx; unsigned int
0x1800274eb  mov     [rsp+120h+var_100], r13; struct CBidGenericBase *
0x1800274f0  mov     rcx, r14; this
0x1800274f3  mov     [rbp+4Fh+var_90], esi
0x1800274f6  call    ?utlSetProperties@CUtlProps@@QEAAJKKQEBUtagDBPROPSET@@AEBVCBidGenericBase@@H@Z; CUtlProps::utlSetProperties(ulong,ulong,tagDBPROPSET const * const,CBidGenericBase const &,int)
0x1800274fb  mov     edi, eax
0x1800274fd  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x180027501  call    cs:__imp_VariantClear
0x180027507  jmp     loc_18002766D
0x18002750c  cmp     eax, 10h
0x18002750f  jnz     short loc_180027526
0x180027511  mov     rdx, qword ptr [rbp+4Fh+pvarSrc+10h]
0x180027515  lea     rcx, [r14+280h]
0x18002751c  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180027521  jmp     loc_18002766D
0x180027526  cmp     eax, 3
0x180027529  jnz     loc_18002766D
0x18002752f  mov     rcx, qword ptr [rbp+4Fh+pvarSrc+10h]; pbstr
0x180027533  call    cs:__imp_SysStringLen
0x180027539  mov     ecx, eax
0x18002753b  mov     [rsp+120h+var_F0], esi
0x18002753f  shr     ecx, 1; unsigned int
0x180027541  mov     edi, eax
0x180027543  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180027548  mov     rbx, rax
0x18002754b  test    rax, rax
0x18002754e  jnz     short loc_18002755A
0x180027550  mov     edi, 8007000Eh
0x180027555  jmp     loc_18002766D
0x18002755a  mov     rcx, qword ptr [rbp+4Fh+pvarSrc+10h]; unsigned __int16 *
0x18002755e  lea     r9, [rsp+120h+var_F0]; int *
0x180027563  mov     r8d, edi; unsigned int
0x180027566  mov     rdx, rbx; unsigned __int8 *
0x180027569  call    ?DecodeBin@@YAJPEAGPEAEKPEAJ@Z; DecodeBin(ushort *,uchar *,ulong,long *)
0x18002756e  mov     edi, eax
0x180027570  test    eax, eax
0x180027572  jns     short loc_180027581
0x180027574  mov     rcx, rbx; unsigned __int8 *
0x180027577  call    ?MMMFree@@YAXPEAE@Z; MMMFree(uchar *)
0x18002757c  jmp     loc_18002766D
0x180027581  mov     eax, [rsp+120h+var_F0]
0x180027585  mov     [r14+268h], eax
0x18002758c  mov     [r14+270h], rbx
0x180027593  jmp     loc_18002766B
0x180027598  cmp     eax, 5
0x18002759b  jnz     loc_18002766D
0x1800275a1  lea     ebx, [rax-4]
0x1800275a4  cmp     dword ptr [rsp+120h+pvarSrc+4], ebx
0x1800275a8  jnz     loc_18002766D
0x1800275ae  mov     rbx, qword ptr [rbp+4Fh+pvarSrc+10h]
0x1800275b2  mov     [rsp+120h+var_E0], rsi
0x1800275b7  cmp     [rbx], si
0x1800275ba  jz      loc_18002766D
0x1800275c0  lea     edi, [rax+1Bh]
0x1800275c3  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800275c7  mov     edx, edi; Ch
0x1800275c9  mov     rcx, rbx; Str
0x1800275cc  call    cs:__imp_wcschr
0x1800275d2  mov     r12, rax
0x1800275d5  test    rax, rax
0x1800275d8  jz      short loc_1800275E7
0x1800275da  mov     rsi, rax
0x1800275dd  sub     rsi, rbx
0x1800275e0  sar     rsi, 1
0x1800275e3  xor     eax, eax
0x1800275e5  jmp     short loc_1800275F5
0x1800275e7  mov     rsi, r15
0x1800275ea  xor     eax, eax
0x1800275ec  inc     rsi
0x1800275ef  cmp     [rbx+rsi*2], ax
0x1800275f3  jnz     short loc_1800275EC
0x1800275f5  mov     rcx, [r13+88h]; this
0x1800275fc  lea     r9, [rsp+120h+var_E8]; unsigned __int64 *
0x180027601  mov     r8d, esi; unsigned int
0x180027604  mov     qword ptr [rsp+120h+var_E8], rax
0x180027609  mov     rdx, rbx; unsigned __int16 *
0x18002760c  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180027611  mov     rax, qword ptr [rsp+120h+var_E8]
0x180027616  test    rax, rax
0x180027619  jz      short loc_180027651
0x18002761b  cmp     dword ptr [rax], 3
0x18002761e  jnz     short loc_180027651
0x180027620  lea     rcx, [r14+228h]; this
0x180027627  mov     r8d, esi; unsigned int
0x18002762a  lea     r9, [rsp+120h+var_E0]; unsigned __int64 *
0x18002762f  mov     rdx, rbx; unsigned __int16 *
0x180027632  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180027637  test    eax, eax
0x180027639  jnz     short loc_180027651
0x18002763b  mov     rax, [r14+118h]
0x180027642  mov     ecx, dword ptr [rsp+120h+var_E0]
0x180027646  mov     rcx, [rax+rcx*8]
0x18002764a  mov     dword ptr [rcx+4], 3
0x180027651  test    r12, r12
0x180027654  jz      short loc_18002765A
0x180027656  add     rbx, 2
0x18002765a  mov     eax, esi
0x18002765c  xor     esi, esi
0x18002765e  lea     rbx, [rbx+rax*2]
0x180027662  cmp     [rbx], si
0x180027665  jnz     loc_1800275C7
0x18002766b  mov     edi, esi
0x18002766d  mov     eax, edi
0x18002766f  mov     rcx, [rbp+4Fh+var_40]
0x180027673  xor     rcx, rsp; StackCookie
0x180027676  call    __security_check_cookie
0x18002767b  mov     rbx, [rsp+120h+arg_18]
0x180027683  add     rsp, 0F0h
0x18002768a  pop     r15
0x18002768c  pop     r14
0x18002768e  pop     r13
0x180027690  pop     r12
0x180027692  pop     rdi
0x180027693  pop     rsi
0x180027694  pop     rbp
0x180027695  retn
```
