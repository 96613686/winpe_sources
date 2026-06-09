# FindLastSegmentInCatalogTableWithFileId(unsigned __int64,unsigned __int64,_CatalogDatabaseDescriptor *,short,unsigned __int64,bool *,unsigned __int64 *,ulong *,ulong *,unsigned __int64 *,ulong *,ulong *,ulong *,ulong *)

- ea: `0x180061c58`
- end: `0x18006254f`
- name: `?FindLastSegmentInCatalogTableWithFileId@@YAK_K0PEAU_CatalogDatabaseDescriptor@@F0PEA_NPEA_KPEAK434444@Z`
- size: `2295`
- prototype: `unsigned int __usercall@<eax>(JET_SESID sesid@<rcx>, JET_TABLEID tableid@<rdx>, struct _CatalogDatabaseDescriptor *@<r8>, __int16@<r9w>, unsigned __int64, bool *, unsigned __int64 *, unsigned int *, unsigned int *, unsigned __int64 *, unsigned int *, unsigned int *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x1800468e4`
- `0x1800680bc`

## callees

- `0x180004374`
- `0x18000ceac`
- `0x18001fc30`
- `0x18002a8bc`
- `0x180061c58`
- `0x1800642e0`
- `0x1800646b0`
- `0x1800647b8`
- `0x18013ab7c`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `ESENT!JetRetrieveColumns` at `0x1800621ad`
- `ESENT!JetRetrieveColumns` at `0x1800621ad`
- `ESENT!JetMove` at `0x1800623ab`
- `ESENT!JetMove` at `0x1800623ab`
- `ESENT!JetSetCurrentIndexW` at `0x180061d70`
- `ESENT!JetSetCurrentIndexW` at `0x180061d70`
- `ESENT!JetMakeKey` at `0x180061e89`
- `ESENT!JetMakeKey` at `0x180061ee3`
- `ESENT!JetMakeKey` at `0x180061e89`
- `ESENT!JetMakeKey` at `0x180061ee3`
- `ESENT!JetSeek` at `0x180061f3b`
- `ESENT!JetSeek` at `0x180061f3b`

## pseudocode

```c
__int64 __fastcall FindLastSegmentInCatalogTableWithFileId(
        JET_SESID sesid,
        JET_TABLEID tableid,
        JET_COLUMNID *a3,
        __int16 a4,
        unsigned __int64 a5,
        bool *a6,
        unsigned __int64 *a7,
        unsigned int *a8,
        unsigned int *a9,
        unsigned __int64 *a10,
        unsigned int *a11,
        unsigned int *a12,
        unsigned int *a13,
        unsigned int *a14)
{
  bool *v14; // rdi
  char v15; // bl
  unsigned __int64 *v16; // r15
  unsigned int *v18; // rax
  unsigned int *v20; // rcx
  unsigned __int64 *v21; // r12
  unsigned int *v22; // r13
  unsigned int *v23; // rdx
  unsigned int *v24; // r8
  unsigned int *v25; // r9
  JET_ERR v26; // ecx
  unsigned int v27; // ebx
  CHostedCacheMsgEncoding *v28; // r10
  __int64 v29; // rdx
  unsigned int *v30; // rcx
  unsigned int *v31; // rdx
  unsigned int *v32; // r8
  const wchar_t *v33; // r9
  JET_ERR Key; // ecx
  JET_ERR v36; // ecx
  char v37; // r12
  JET_ERR v38; // ecx
  char v39; // r13
  unsigned int v40; // r15d
  JET_COLUMNID v41; // eax
  JET_ERR v42; // eax
  __int64 v43; // rdx
  unsigned __int64 v44; // r8
  unsigned __int64 v45; // r11
  JET_ERR v46; // eax
  const wchar_t *v47; // rcx
  unsigned int v48; // eax
  unsigned int *v49; // [rsp+60h] [rbp-A0h]
  unsigned int *v50; // [rsp+68h] [rbp-98h]
  unsigned int *v51; // [rsp+70h] [rbp-90h]
  __int16 v52; // [rsp+80h] [rbp-80h] BYREF
  __int16 pvData; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 *v54; // [rsp+90h] [rbp-70h]
  unsigned int v55; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 *v56; // [rsp+A0h] [rbp-60h]
  unsigned int *v57; // [rsp+A8h] [rbp-58h]
  unsigned int v58; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v59; // [rsp+B4h] [rbp-4Ch] BYREF
  unsigned int v60; // [rsp+B8h] [rbp-48h] BYREF
  unsigned int v61; // [rsp+BCh] [rbp-44h] BYREF
  unsigned int v62; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v63; // [rsp+C4h] [rbp-3Ch]
  unsigned int v64; // [rsp+C8h] [rbp-38h]
  unsigned int v65; // [rsp+CCh] [rbp-34h]
  unsigned int v66; // [rsp+D0h] [rbp-30h]
  unsigned int v67; // [rsp+D4h] [rbp-2Ch]
  unsigned __int64 v68; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v69; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int64 v70; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v71; // [rsp+F0h] [rbp-10h]
  JET_COLUMNID *v72; // [rsp+F8h] [rbp-8h]
  unsigned int *v73; // [rsp+100h] [rbp+0h]
  unsigned int *v74; // [rsp+108h] [rbp+8h]
  JET_RETRIEVECOLUMN pretrievecolumn; // [rsp+110h] [rbp+10h] BYREF
  __int64 v76; // [rsp+140h] [rbp+40h]
  unsigned int *v77; // [rsp+148h] [rbp+48h]
  __int128 v78; // [rsp+150h] [rbp+50h]
  __int128 v79; // [rsp+160h] [rbp+60h]
  __int64 v80; // [rsp+170h] [rbp+70h]
  unsigned int *v81; // [rsp+178h] [rbp+78h]
  __int128 v82; // [rsp+180h] [rbp+80h]
  __int128 v83; // [rsp+190h] [rbp+90h]
  __int64 v84; // [rsp+1A0h] [rbp+A0h]
  unsigned int *v85; // [rsp+1A8h] [rbp+A8h]
  __int128 v86; // [rsp+1B0h] [rbp+B0h]
  __int128 v87; // [rsp+1C0h] [rbp+C0h]
  __int64 v88; // [rsp+1D0h] [rbp+D0h]
  unsigned int *v89; // [rsp+1D8h] [rbp+D8h]
  __int128 v90; // [rsp+1E0h] [rbp+E0h]
  __int128 v91; // [rsp+1F0h] [rbp+F0h]
  __int64 v92; // [rsp+200h] [rbp+100h]
  unsigned __int64 *v93; // [rsp+208h] [rbp+108h]
  __int128 v94; // [rsp+210h] [rbp+110h]
  __int128 v95; // [rsp+220h] [rbp+120h]
  __int64 v96; // [rsp+230h] [rbp+130h]
  unsigned int *v97; // [rsp+238h] [rbp+138h]
  __int128 v98; // [rsp+240h] [rbp+140h]
  __int128 v99; // [rsp+250h] [rbp+150h]
  __int64 v100; // [rsp+260h] [rbp+160h]
  unsigned int *v101; // [rsp+268h] [rbp+168h]
  __int128 v102; // [rsp+270h] [rbp+170h]
  __int128 v103; // [rsp+280h] [rbp+180h]
  __int64 v104; // [rsp+290h] [rbp+190h]
  __int16 *v105; // [rsp+298h] [rbp+198h]
  __int128 v106; // [rsp+2A0h] [rbp+1A0h]
  __int128 v107; // [rsp+2B0h] [rbp+1B0h]

  v14 = a6;
  v15 = 0;
  v16 = a7;
  v18 = a8;
  v20 = a9;
  v21 = a10;
  v22 = a11;
  v23 = a12;
  *a6 = 0;
  *v16 = 0;
  *v18 = 0;
  *v20 = 0;
  *v21 = 0;
  *v22 = 0;
  *v23 = 0;
  v72 = a3;
  v24 = a13;
  pvData = a4;
  v25 = a14;
  *a13 = 0;
  v56 = v16;
  *v25 = 0;
  v73 = v18;
  v74 = v20;
  v54 = v21;
  v57 = v22;
  v49 = v23;
  v50 = v24;
  v51 = v25;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 88, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids);
  }
  v52 = 0;
  pretrievecolumn.columnid = 0;
  memset_0(&pretrievecolumn.pvData, 0, 0x1A8u);
  v26 = JetSetCurrentIndexW(sesid, tableid, L"FileIdIndex");
  if ( v26 )
  {
    v27 = TranslateJetError(v26);
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      return v27;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      goto LABEL_11;
    v29 = 89;
LABEL_10:
    WPP_SF_Dd(*((_QWORD *)v28 + 12), v29, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids);
    v28 = WPP_GLOBAL_Control;
    goto LABEL_11;
  }
  Key = JetMakeKey(sesid, tableid, &pvData, 2u, 1u);
  if ( Key )
  {
    v27 = TranslateJetError(Key);
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      return v27;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      goto LABEL_11;
    v29 = 90;
    goto LABEL_10;
  }
  v36 = JetMakeKey(sesid, tableid, &a5, 8u, 0);
  if ( v36 )
  {
    v27 = TranslateJetError(v36);
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
      return v27;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0 || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      goto LABEL_11;
    v29 = 91;
    goto LABEL_10;
  }
  v37 = 0;
  v38 = JetSeek(sesid, tableid, 4u);
  if ( v38 == -1601 )
  {
    v15 = 1;
  }
  else if ( v38 == 1039 )
  {
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_qDD(*((_QWORD *)WPP_GLOBAL_Control + 12), 92, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids, a5, 1039, 0);
    }
    v37 = 1;
  }
  else if ( v38 )
  {
    v27 = TranslateJetError(v38);
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 93, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids);
        v28 = WPP_GLOBAL_Control;
      }
      v21 = v54;
      goto LABEL_11;
    }
    return v27;
  }
  v39 = 0;
  v70 = 0;
  v40 = 0;
  v63 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v64 = 0;
  v71 = 0;
  do
  {
    while ( 1 )
    {
      if ( v15 )
      {
LABEL_85:
        v27 = 0;
        v21 = v54;
        v31 = v50;
        v32 = v51;
        *v56 = v70;
        *v73 = v63;
        *v74 = v64;
        v30 = v49;
        *v21 = v71;
        *v57 = v40;
        v16 = v56;
        *v49 = v65;
        *v50 = v66;
        *v51 = v67;
        *v14 = v39;
        v28 = WPP_GLOBAL_Control;
        v22 = v57;
        goto LABEL_12;
      }
      v69 = 0;
      memset(&pretrievecolumn, 0, sizeof(pretrievecolumn));
      v58 = 0;
      pretrievecolumn.columnid = v72[203];
      v59 = 0;
      pretrievecolumn.pvData = &v69;
      v76 = v72[218];
      v77 = &v58;
      v80 = v72[213];
      v81 = &v59;
      v84 = v72[208];
      v85 = &v61;
      v88 = v72[209];
      v89 = &v62;
      v92 = v72[214];
      v93 = &v68;
      v96 = v72[215];
      v97 = &v55;
      v41 = v72[216];
      v68 = 0;
      v55 = 0;
      v78 = 0;
      v60 = 0;
      v79 = 0;
      v61 = 0;
      v82 = 0;
      v62 = 0;
      v83 = 0;
      pretrievecolumn.cbData = 8;
      v86 = 0;
      pretrievecolumn.itagSequence = 1;
      v87 = 0;
      LODWORD(v78) = 4;
      v90 = 0;
      LODWORD(v79) = 1;
      v91 = 0;
      LODWORD(v82) = 4;
      v94 = 0;
      LODWORD(v83) = 1;
      v95 = 0;
      LODWORD(v86) = 4;
      v98 = 0;
      LODWORD(v87) = 1;
      v99 = 0;
      LODWORD(v90) = 4;
      v100 = v41;
      v102 = 0;
      LODWORD(v91) = 1;
      LODWORD(v94) = 8;
      LODWORD(v95) = 1;
      LODWORD(v98) = 4;
      LODWORD(v99) = 1;
      v103 = 0;
      LODWORD(v102) = 4;
      LODWORD(v103) = 1;
      v101 = &v60;
      v104 = v72[212];
      v106 = 0;
      v105 = &v52;
      v107 = 0;
      LODWORD(v106) = 2;
      LODWORD(v107) = 1;
      v42 = JetRetrieveColumns(sesid, tableid, &pretrievecolumn, 9u);
      if ( v42 )
      {
        v48 = TranslateJetError(v42);
        v28 = WPP_GLOBAL_Control;
        v27 = v48;
LABEL_83:
        v16 = v56;
        v21 = v54;
        v22 = v57;
        goto LABEL_11;
      }
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 12), 94, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids, v68, a5);
        v28 = WPP_GLOBAL_Control;
      }
      v44 = v68;
      v45 = a5;
      if ( v37 )
      {
        if ( v68 <= a5 )
        {
          v45 = v68;
          a5 = v68;
          v37 = 0;
          goto LABEL_59;
        }
        if ( v68 != 0x7FFFFFFFFFFFFFFFLL )
        {
          if ( v28 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_BYTE *)v28 + 108) & 4) != 0
            && *((_BYTE *)v28 + 105) )
          {
            WPP_SF_qq(*((_QWORD *)v28 + 12), 96, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids, v68, a5);
            v28 = WPP_GLOBAL_Control;
          }
          v27 = 534;
          goto LABEL_83;
        }
        if ( v28 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)v28 + 108) & 4) != 0
          && *((_BYTE *)v28 + 105) >= 2u )
        {
          WPP_SF_iI(*((_QWORD *)v28 + 12), v43, 0x7FFFFFFFFFFFFFFFLL, 0x7FFFFFFFFFFFFFFFLL, a5);
          v45 = a5;
          v28 = WPP_GLOBAL_Control;
          v44 = v68;
        }
        v15 = 1;
      }
LABEL_59:
      if ( v52 != pvData || v44 != v45 )
      {
        if ( v28 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)v28 + 108) & 4) != 0
          && *((_BYTE *)v28 + 105) >= 4u )
        {
          v47 = L"using previous values";
          if ( !v39 )
            v47 = L"no records found";
          WPP_SF_DIDIS(
            *((_QWORD *)v28 + 12),
            (unsigned int)L"no records found",
            v44,
            v52,
            v44,
            pvData,
            v45,
            (__int64)v47);
        }
        goto LABEL_77;
      }
      if ( v55 >= v40 )
      {
        v39 = 1;
        v40 = v55;
        v70 = v69;
        v63 = v58;
        v64 = v59;
        v65 = v60;
        v66 = v61;
        v67 = v62;
        v71 = v44;
      }
      if ( v15 )
        goto LABEL_85;
      v46 = JetMove(sesid, tableid, 1, 0);
      if ( v46 != -1603 )
        break;
LABEL_77:
      v15 = 1;
    }
  }
  while ( !v46 );
  v27 = TranslateJetError(v46);
  v28 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control )
    return v27;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 98, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids);
    v28 = WPP_GLOBAL_Control;
  }
  v16 = v56;
  v21 = v54;
  v22 = v57;
LABEL_11:
  v30 = v49;
  v31 = v50;
  v32 = v51;
LABEL_12:
  if ( v28 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)v28 + 108) & 4) != 0
    && *((_BYTE *)v28 + 105) >= 4u )
  {
    v33 = L"Y";
    if ( !*v14 )
      v33 = (const wchar_t *)L"N";
    WPP_SF_SIIDDDDD(
      *((_QWORD *)v28 + 12),
      (_DWORD)v31,
      (_DWORD)v32,
      (_DWORD)v33,
      *v16,
      *v21,
      *v22,
      *v30,
      *v31,
      *v32,
      v27);
  }
  return v27;
}

```

## disassembly

```asm
0x180061c58  mov     [rsp-8+arg_10], rbx
0x180061c5d  push    rbp
0x180061c5e  push    rsi
0x180061c5f  push    rdi
0x180061c60  push    r12
0x180061c62  push    r13
0x180061c64  push    r14
0x180061c66  push    r15
0x180061c68  lea     rbp, [rsp-1D0h]
0x180061c70  sub     rsp, 2D0h
0x180061c77  mov     rax, cs:__security_cookie
0x180061c7e  xor     rax, rsp
0x180061c81  mov     [rbp+200h+var_40], rax
0x180061c88  mov     rdi, [rbp+200h+arg_28]
0x180061c8f  xor     ebx, ebx
0x180061c91  mov     r15, [rbp+200h+arg_30]
0x180061c98  mov     rsi, rcx
0x180061c9b  mov     rax, [rbp+200h+arg_38]
0x180061ca2  mov     r14, rdx
0x180061ca5  mov     rcx, [rbp+200h+arg_40]
0x180061cac  mov     r12, [rbp+200h+arg_48]
0x180061cb3  mov     r13, [rbp+200h+arg_50]
0x180061cba  mov     rdx, [rbp+200h+arg_58]
0x180061cc1  mov     [rdi], bl
0x180061cc3  mov     [r15], rbx
0x180061cc6  mov     [rax], ebx
0x180061cc8  mov     [rcx], ebx
0x180061cca  mov     [r12], rbx
0x180061cce  mov     [r13+0], ebx
0x180061cd2  mov     [rdx], ebx
0x180061cd4  mov     [rbp+200h+var_208], r8
0x180061cd8  mov     r8, [rbp+200h+arg_60]
0x180061cdf  mov     [rbp+200h+pvData], r9w
0x180061ce4  mov     r9, [rbp+200h+arg_68]
0x180061ceb  mov     [rsp+300h+var_288], rdi
0x180061cf0  mov     [r8], ebx
0x180061cf3  mov     [rbp+200h+var_260], r15
0x180061cf7  mov     [r9], ebx
0x180061cfa  mov     [rbp+200h+var_200], rax
0x180061cfe  mov     [rbp+200h+var_1F8], rcx
0x180061d02  mov     [rbp+200h+var_270], r12
0x180061d06  mov     [rbp+200h+var_258], r13
0x180061d0a  mov     [rsp+300h+var_2A0], rdx
0x180061d0f  mov     [rsp+300h+var_298], r8
0x180061d14  mov     [rsp+300h+var_290], r9
0x180061d19  mov     rcx, cs:WPP_GLOBAL_Control
0x180061d20  lea     rax, WPP_GLOBAL_Control
0x180061d27  cmp     rcx, rax
0x180061d2a  jz      short loc_180061D4B
0x180061d2c  test    byte ptr [rcx+6Ch], 4
0x180061d30  jz      short loc_180061D4B
0x180061d32  cmp     byte ptr [rcx+69h], 4
0x180061d36  jb      short loc_180061D4B
0x180061d38  mov     rcx, [rcx+60h]
0x180061d3c  lea     edx, [rbx+58h]
0x180061d3f  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180061d46  call    WPP_SF_
0x180061d4b  xor     edx, edx; Val
0x180061d4d  mov     [rbp+200h+var_280], bx
0x180061d51  mov     r8d, 1A8h; Size
0x180061d57  mov     [rbp+200h+pretrievecolumn.columnid], ebx
0x180061d5a  lea     rcx, [rbp+200h+pretrievecolumn.pvData]; void *
0x180061d5e  call    memset_0
0x180061d63  mov     r8, cs:off_180161378; szIndexName
0x180061d6a  mov     rdx, r14; tableid
0x180061d6d  mov     rcx, rsi; sesid
0x180061d70  call    cs:__imp_JetSetCurrentIndexW
0x180061d76  mov     ecx, eax; int
0x180061d78  test    eax, eax
0x180061d7a  jz      loc_180061E72
0x180061d80  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180061d85  mov     ebx, eax
0x180061d87  mov     r10, cs:WPP_GLOBAL_Control
0x180061d8e  lea     rsi, WPP_GLOBAL_Control
0x180061d95  cmp     r10, rsi
0x180061d98  jz      loc_180061E46
0x180061d9e  test    byte ptr [r10+6Ch], 4
0x180061da3  jz      short loc_180061DD6
0x180061da5  mov     edi, 1
0x180061daa  cmp     [r10+69h], dil
0x180061dae  jb      short loc_180061DD1
0x180061db0  lea     edx, [rdi+58h]
0x180061db3  mov     r9d, ecx
0x180061db6  mov     [rsp+300h+grbit], eax
0x180061dba  mov     rcx, [r10+60h]
0x180061dbe  lea     r8, WPP_12aa5a3d42d7369b06858bb53f12be47_Traceguids
0x180061dc5  call    WPP_SF_Dd
0x180061dca  mov     r10, cs:WPP_GLOBAL_Control
0x180061dd1  mov     rdi, [rsp+300h+var_288]
0x180061dd6  mov     rcx, [rsp+300h+var_2A0]
0x180061ddb  mov     rdx, [rsp+300h+var_298]
0x180061de0  mov     r8, [rsp+300h+var_290]
0x180061de5  cmp     r10, rsi
0x180061de8  jz      short loc_180061E46
0x180061dea  test    byte ptr [r10+6Ch], 4
0x180061def  jz      short loc_180061E46
0x180061df1  cmp     byte ptr [r10+69h], 4
0x180061df6  jb      short loc_180061E46
0x180061df8  cmp     byte ptr [rdi], 0
0x180061dfb  lea     rax, aN; "N"
0x180061e02  mov     [rsp+300h+var_2B0], ebx
0x180061e06  lea     r9, aY; "Y"
0x180061e0d  cmovz   r9, rax
0x180061e11  mov     eax, [r8]
0x180061e14  mov     [rsp+300h+var_2B8], eax
0x180061e18  mov     eax, [rdx]
0x180061e1a  mov     [rsp+300h+var_2C0], eax
0x180061e1e  mov     eax, [rcx]
0x180061e20  mov     rcx, [r10+60h]
0x180061e24  mov     dword ptr [rsp+300h+var_2C8], eax
0x180061e28  mov     eax, [r13+0]
0x180061e2c  mov     dword ptr [rsp+300h+var_2D0], eax
0x180061e30  mov     rax, [r12]
0x180061e34  mov     [rsp+300h+var_2D8], rax
0x180061e39  mov     rax, [r15]
0x180061e3c  mov     qword ptr [rsp+300h+grbit], rax
0x180061e41  call    WPP_SF_SIIDDDDD
0x180061e46  mov     eax, ebx
0x180061e48  mov     rcx, [rbp+200h+var_40]
0x180061e4f  xor     rcx, rsp; StackCookie
0x180061e52  call    __security_check_cookie
0x180061e57  mov     rbx, [rsp+300h+arg_10]
0x180061e5f  add     rsp, 2D0h
0x180061e66  pop     r15
0x180061e68  pop     r14
0x180061e6a  pop     r13
0x180061e6c  pop     r12
0x180061e6e  pop     rdi
0x180061e6f  pop     rsi
0x180061e70  pop     rbp
0x180061e71  retn
0x180061e72  mov     edi, 1
0x180061e77  lea     r8, [rbp+200h+pvData]; pvData
0x180061e7b  mov     rdx, r14; tableid
0x180061e7e  mov     [rsp+300h+grbit], edi; grbit
0x180061e82  mov     rcx, rsi; sesid
0x180061e85  lea     r9d, [rdi+1]; cbData
0x180061e89  call    cs:__imp_JetMakeKey
0x180061e8f  mov     ecx, eax; int
0x180061e91  test    eax, eax
0x180061e93  jz      short loc_180061ECC
0x180061e95  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180061e9a  mov     ebx, eax
0x180061e9c  mov     r10, cs:WPP_GLOBAL_Control
0x180061ea3  lea     rsi, WPP_GLOBAL_Control
0x180061eaa  cmp     r10, rsi
0x180061ead  jz      short loc_180061E46
0x180061eaf  test    byte ptr [r10+6Ch], 4
0x180061eb4  jz      loc_180061DD1
0x180061eba  cmp     [r10+69h], dil
0x180061ebe  jb      loc_180061DD1
0x180061ec4  lea     edx, [rdi+59h]
0x180061ec7  jmp     loc_180061DB3
0x180061ecc  mov     r9d, 8; cbData
0x180061ed2  mov     [rsp+300h+grbit], ebx; grbit
0x180061ed6  lea     r8, [rbp+200h+arg_20]; pvData
0x180061edd  mov     rdx, r14; tableid
0x180061ee0  mov     rcx, rsi; sesid
0x180061ee3  call    cs:__imp_JetMakeKey
0x180061ee9  mov     ecx, eax; int
0x180061eeb  test    eax, eax
0x180061eed  jz      short loc_180061F2C
0x180061eef  call    ?TranslateJetError@@YAKJ@Z; TranslateJetError(long)
0x180061ef4  mov     ebx, eax
0x180061ef6  mov     r10, cs:WPP_GLOBAL_Control
0x180061efd  lea     rsi, WPP_GLOBAL_Control
0x180061f04  cmp     r10, rsi
0x180061f07  jz      loc_180061E46
0x180061f0d  test    byte ptr [r10+6Ch], 4
0x180061f12  jz      loc_180061DD1
0x180061f18  cmp     [r10+69h], dil
0x180061f1c  jb      loc_180061DD1
0x180061f22  mov     edx, 5Bh ; '['
0x180061f27  jmp     loc_180061DB3
0x180061f2c  mov     r8d, 4; grbit
0x180061f32  mov     rdx, r14; tableid
0x180061f35  mov     rcx, rsi; sesid
0x180061f38  xor     r12b, r12b
0x180061f3b  call    cs:__imp_JetSeek
0x180061f41  mov     ecx, eax; int
0x180061f43  cmp     eax, 0FFFFF9BFh
0x180061f48  jnz     loc_180062282
0x180061f4e  mov     bl, dil
0x180061f51  xor     r13b, r13b
0x180061f54  mov     [rbp+200h+var_218], 0
0x180061f5c  xor     r15d, r15d
0x180061f5f  mov     [rbp+200h+var_23C], 0
0x180061f66  mov     [rbp+200h+var_234], r15d
0x180061f6a  mov     [rbp+200h+var_230], r15d
0x180061f6e  mov     [rbp+200h+var_22C], r15d
0x180061f72  mov     [rbp+200h+var_238], 0
0x180061f79  mov     [rbp+200h+var_210], 0
0x180061f81  test    bl, bl
0x180061f83  jnz     loc_1800624DB
0x180061f89  mov     rcx, [rbp+200h+var_208]
0x180061f8d  xorps   xmm0, xmm0
0x180061f90  mov     r8d, 8
0x180061f96  mov     [rbp+200h+var_220], 0
0x180061f9e  movups  xmmword ptr [rbp+200h+pretrievecolumn.columnid], xmm0
0x180061fa2  mov     [rbp+200h+var_250], 0
0x180061fa9  mov     eax, [rcx+32Ch]
0x180061faf  mov     [rbp+200h+pretrievecolumn.columnid], eax
0x180061fb2  lea     edx, [r8-4]
0x180061fb6  lea     rax, [rbp+200h+var_220]
0x180061fba  mov     [rbp+200h+var_24C], 0
0x180061fc1  mov     [rbp+200h+pretrievecolumn.pvData], rax
0x180061fc5  mov     eax, [rcx+368h]
0x180061fcb  movups  [rbp+200h+var_1C0], xmm0
0x180061fcf  mov     dword ptr [rbp+200h+var_1C0], eax
0x180061fd2  lea     rax, [rbp+200h+var_250]
0x180061fd6  mov     qword ptr [rbp+200h+var_1C0+8], rax
0x180061fda  mov     eax, [rcx+354h]
0x180061fe0  movups  [rbp+200h+var_190], xmm0
0x180061fe4  mov     dword ptr [rbp+200h+var_190], eax
0x180061fe7  lea     rax, [rbp+200h+var_24C]
0x180061feb  mov     qword ptr [rbp+200h+var_190+8], rax
0x180061fef  mov     eax, [rcx+340h]
0x180061ff5  movups  [rbp+200h+var_160], xmm0
0x180061ffc  mov     dword ptr [rbp+200h+var_160], eax
0x180062002  lea     rax, [rbp+200h+var_244]
0x180062006  mov     qword ptr [rbp+200h+var_160+8], rax
0x18006200d  mov     eax, [rcx+344h]
0x180062013  movups  [rbp+200h+var_130], xmm0
0x18006201a  mov     dword ptr [rbp+200h+var_130], eax
0x180062020  lea     rax, [rbp+200h+var_240]
0x180062024  mov     qword ptr [rbp+200h+var_130+8], rax
0x18006202b  mov     eax, [rcx+358h]
0x180062031  movups  [rbp+200h+var_100], xmm0
0x180062038  mov     dword ptr [rbp+200h+var_100], eax
0x18006203e  lea     rax, [rbp+200h+var_228]
0x180062042  mov     qword ptr [rbp+200h+var_100+8], rax
0x180062049  mov     eax, [rcx+35Ch]
0x18006204f  movups  [rbp+200h+var_D0], xmm0
0x180062056  mov     dword ptr [rbp+200h+var_D0], eax
0x18006205c  lea     rax, [rbp+200h+var_268]
0x180062060  mov     qword ptr [rbp+200h+var_D0+8], rax
0x180062067  mov     eax, [rcx+360h]
0x18006206d  movups  xmmword ptr [rbp+200h+pretrievecolumn.cbData], xmm0
0x180062071  mov     [rbp+200h+var_228], 0
0x180062079  movups  xmmword ptr [rbp+200h+pretrievecolumn.itagSequence], xmm0
0x18006207d  mov     [rbp+200h+var_268], 0
0x180062084  movups  [rbp+200h+var_1B0], xmm0
0x180062088  mov     [rbp+200h+var_248], 0
0x18006208f  movups  [rbp+200h+var_1A0], xmm0
0x180062093  mov     [rbp+200h+var_244], 0
0x18006209a  movups  [rbp+200h+var_180], xmm0
0x1800620a1  mov     [rbp+200h+var_240], 0
0x1800620a8  movups  [rbp+200h+var_170], xmm0
0x1800620af  mov     [rbp+200h+pretrievecolumn.cbData], r8d
0x1800620b3  movups  [rbp+200h+var_150], xmm0
0x1800620ba  mov     [rbp+200h+pretrievecolumn.itagSequence], edi
0x1800620bd  movups  [rbp+200h+var_140], xmm0
0x1800620c4  mov     dword ptr [rbp+200h+var_1B0], edx
0x1800620c7  movups  [rbp+200h+var_120], xmm0
0x1800620ce  mov     dword ptr [rbp+200h+var_1A0], edi
0x1800620d1  movups  [rbp+200h+var_110], xmm0
0x1800620d8  mov     dword ptr [rbp+200h+var_180], edx
0x1800620de  movups  [rbp+200h+var_F0], xmm0
0x1800620e5  mov     dword ptr [rbp+200h+var_170], edi
0x1800620eb  movups  [rbp+200h+var_E0], xmm0
0x1800620f2  mov     dword ptr [rbp+200h+var_150], edx
0x1800620f8  movups  [rbp+200h+var_C0], xmm0
0x1800620ff  mov     dword ptr [rbp+200h+var_140], edi
0x180062105  movups  [rbp+200h+var_B0], xmm0
0x18006210c  mov     dword ptr [rbp+200h+var_120], edx
0x180062112  movups  [rbp+200h+var_A0], xmm0
0x180062119  mov     dword ptr [rbp+200h+var_A0], eax
0x18006211f  movups  [rbp+200h+var_90], xmm0
0x180062126  mov     dword ptr [rbp+200h+var_110], edi
0x18006212c  mov     dword ptr [rbp+200h+var_F0], r8d
0x180062133  mov     dword ptr [rbp+200h+var_E0], edi
0x180062139  mov     dword ptr [rbp+200h+var_C0], edx
0x18006213f  mov     dword ptr [rbp+200h+var_B0], edi
0x180062145  movups  [rbp+200h+var_80], xmm0
0x18006214c  mov     dword ptr [rbp+200h+var_90], edx
0x180062152  lea     rax, [rbp+200h+var_248]
0x180062156  mov     dword ptr [rbp+200h+var_80], edi
0x18006215c  mov     qword ptr [rbp+200h+var_A0+8], rax
0x180062163  lea     r9d, [r8+1]; cretrievecolumn
0x180062167  mov     eax, [rcx+350h]
0x18006216d  lea     r8, [rbp+200h+pretrievecolumn]; pretrievecolumn
0x180062171  movups  [rbp+200h+var_70], xmm0
0x180062178  mov     dword ptr [rbp+200h+var_70], eax
0x18006217e  mov     rdx, r14; tableid
0x180062181  lea     rax, [rbp+200h+var_280]
0x180062185  mov     rcx, rsi; sesid
0x180062188  movups  [rbp+200h+var_60], xmm0
0x18006218f  mov     qword ptr [rbp+200h+var_70+8], rax
0x180062196  movups  [rbp+200h+var_50], xmm0
0x18006219d  mov     dword ptr [rbp+200h+var_60], 2
0x1800621a7  mov     dword ptr [rbp+200h+var_50], edi
0x1800621ad  call    cs:__imp_JetRetrieveColumns
0x1800621b3  test    eax, eax
0x1800621b5  jnz     loc_1800624C9
0x1800621bb  mov     r10, cs:WPP_GLOBAL_Control
0x1800621c2  lea     rcx, WPP_GLOBAL_Control
0x1800621c9  cmp     r10, rcx
0x1800621cc  jz      short loc_18006220D
0x1800621ce  test    byte ptr [r10+6Ch], 4
0x1800621d3  jz      short loc_18006220D
  ... truncated ...
```
