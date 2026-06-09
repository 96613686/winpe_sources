# CRTFObject::InitReadStaticObject(_reobject &,void * &,int,int,int,CTxtRange *,IStream *)

- ea: `0x18015849c`
- end: `0x180158af6`
- name: `?InitReadStaticObject@CRTFObject@@AEAAJAEAU_reobject@@AEAPEAXHHHPEAVCTxtRange@@PEAUIStream@@@Z`
- size: `1626`
- prototype: `__int64 __fastcall(CRTFObject *__hidden this, struct _reobject *, void **, int, int, int, struct CTxtRange *, struct IStream *)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180093e8c`
- `0x18017f6b8`
- `0x1801991fc`

## callees

- `0x180040d10`
- `0x180040d4c`
- `0x1800693d4`
- `0x18006e770`
- `0x18009247c`
- `0x18012ac54`
- `0x18013beb8`
- `0x180148064`
- `0x18015849c`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180158ab7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180158ab7`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteEnhMetaFile` at `0x180158aab`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteEnhMetaFile` at `0x180158aab`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801587a7`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180158acc`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x1801587a7`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180158acc`

## string_xrefs

- `0x18015882a`: `OleCreateDefaultHandler`

## pseudocode

```c
__int64 __fastcall CRTFObject::InitReadStaticObject(
        CRTFObject *this,
        struct _reobject *a2,
        void **a3,
        int a4,
        int a5,
        int a6,
        struct CTxtRange *a7,
        struct IStream *a8)
{
  __int64 v10; // rcx
  __int64 v11; // r15
  __int64 v12; // rbx
  __int64 v13; // rax
  unsigned int v14; // eax
  void *(__fastcall *v15)(struct CRTFObject *, void **); // r14
  GUID v16; // xmm0
  int v17; // r11d
  LONG v18; // eax
  int v19; // r12d
  LONG v20; // eax
  int v21; // r11d
  int v22; // r13d
  int v23; // edx
  int v24; // edx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // ecx
  bool v31; // zf
  void **v32; // r12
  __int64 v33; // rcx
  void *v34; // rcx
  int v35; // ebx
  int v36; // r13d
  struct COLE32_PROC *Ole32Procs; // rax
  struct COLE32_PROC *v38; // r14
  __int64 (__fastcall *v39)(CLSID *, _QWORD, GUID *, LPOLEOBJECT *); // rax
  LPOLEOBJECT *p_poleobj; // r14
  unsigned int v41; // r12d
  struct IOleClientSiteVtbl *lpVtbl; // rcx
  int v43; // eax
  LPOLECLIENTSITE v44; // rbx
  _DWORD *v45; // rdx
  void **v46; // rcx
  LPOLECLIENTSITE polesite; // [rsp+30h] [rbp-50h]
  LPOLECLIENTSITE *p_polesite; // [rsp+38h] [rbp-48h]
  HENHMETAFILE hmf[3]; // [rsp+40h] [rbp-40h] BYREF
  __int128 v51; // [rsp+58h] [rbp-28h] BYREF
  __int128 v52; // [rsp+68h] [rbp-18h]
  int v53; // [rsp+C8h] [rbp+48h] BYREF
  void **v54; // [rsp+D0h] [rbp+50h]
  int v55; // [rsp+D8h] [rbp+58h]

  v55 = a4;
  v54 = a3;
  v53 = 0;
  v10 = *((_QWORD *)a7 + 3);
  if ( v10 )
    v11 = *(_QWORD *)(v10 + 40);
  else
    v11 = 0;
  v51 = 0;
  v52 = 0;
  v12 = *(_QWORD *)(v11 + 256);
  a7 = 0;
  a8 = 0;
  memset(hmf, 0, sizeof(hmf));
  v13 = *(_QWORD *)(v11 + 240);
  if ( !v13 )
    return 2147500037LL;
  p_polesite = &a2->polesite;
  polesite = a2->polesite;
  if ( !*(_QWORD *)(v13 + 24) || !CTxtEdit::GetObjectMgr((CTxtEdit *)v11) )
    return 2147500037LL;
  v14 = *((_DWORD *)this + 8) - 1;
  *((_QWORD *)&v51 + 1) = 0;
  *(_QWORD *)&v52 = 0xFFFFFFFF00000001uLL;
  v15 = 0;
  DWORD2(v52) = 0;
  if ( v14 > 0x3E7 )
    *((_DWORD *)this + 8) = 100;
  if ( (unsigned int)(*((_DWORD *)this + 9) - 1) > 0x3E7 )
    *((_DWORD *)this + 9) = 100;
  if ( !*(_WORD *)this )
  {
    v15 = ObHBuildBitmap;
LABEL_21:
    v16 = CLSID_StaticDib;
    v17 = 16;
    LOWORD(v51) = 2;
    goto LABEL_22;
  }
  if ( *(_WORD *)this == 1 )
  {
    v16 = CLSID_StaticMetafile;
    LOWORD(v51) = 3;
    v15 = ObHBuildMetafilePict;
    v17 = 32;
LABEL_22:
    DWORD2(v52) = v17;
    goto LABEL_23;
  }
  if ( *(_WORD *)this != 2 )
  {
    if ( *(_WORD *)this != 3 && *(_WORD *)this != 4 )
    {
      if ( *(_WORD *)this != 9 )
        goto LABEL_24;
      v16 = CLSID_Picture_EnhMetafile;
      LOWORD(v51) = 14;
      v17 = 64;
      v15 = ObHBuildEnhMetafilePict;
      goto LABEL_22;
    }
    goto LABEL_21;
  }
  v16 = CLSID_StaticDib;
  LOWORD(v51) = 8;
  v15 = ObHBuildDib;
  DWORD2(v52) = 1;
LABEL_23:
  a2->clsid = v16;
LABEL_24:
  a2->dvaspect = 1;
  v18 = CW32System::MulDivFunc(*((__int16 *)this + 20), 127, 72);
  a2->sizel.cx = v18;
  v19 = v18;
  v20 = CW32System::MulDivFunc(*((__int16 *)this + 21), 127, 72);
  a2->sizel.cy = v20;
  v22 = v20;
  v23 = *((_DWORD *)this + 8);
  if ( (unsigned int)(v23 - 1) <= 0x3E7 )
    a2->sizel.cx = CW32System::MulDivFunc(v19, v23, 100);
  v24 = *((_DWORD *)this + 9);
  if ( (unsigned int)(v24 - 1) <= 0x3E7 )
    a2->sizel.cy = CW32System::MulDivFunc(v22, v24, 100);
  LODWORD(hmf[0]) = v21;
  *(_OWORD *)&hmf[1] = 0;
  if ( v12 && v55 )
  {
    *(_BYTE *)(v12 + 143) = *(_BYTE *)this;
    *(_BYTE *)(v12 + 144) = *((_BYTE *)this + 2);
    v25 = *((_DWORD *)this + 5);
    if ( (unsigned int)(v25 + 0x8000) > 0xFFFF )
      goto LABEL_43;
    *(_WORD *)(v12 + 164) = v25;
    v26 = *((_DWORD *)this + 6);
    if ( (unsigned int)(v26 + 0x8000) > 0xFFFF )
      goto LABEL_43;
    *(_WORD *)(v12 + 166) = v26;
    v27 = *((_DWORD *)this + 8);
    if ( (unsigned int)(v27 + 0x8000) > 0xFFFF )
      goto LABEL_43;
    *(_WORD *)(v12 + 168) = v27;
    v28 = *((_DWORD *)this + 9);
    if ( (unsigned int)(v28 + 0x8000) > 0xFFFF
      || (*(_WORD *)(v12 + 170) = v28,
          *(_WORD *)(v12 + 172) = *((_WORD *)this + 20),
          *(_WORD *)(v12 + 174) = *((_WORD *)this + 21),
          v29 = *((_DWORD *)this + 24),
          (unsigned int)(v29 + 0x8000) > 0xFFFF)
      || (*(_WORD *)(v12 + 176) = v29, v30 = *((_DWORD *)this + 25), (unsigned int)(v30 + 0x8000) > 0xFFFF) )
    {
LABEL_43:
      SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow();
    }
    v31 = *(_BYTE *)(v12 + 139) == 3;
    v32 = v54;
    *(_WORD *)(v12 + 178) = v30;
    *(_OWORD *)(v12 + 148) = *(_OWORD *)((char *)this + 52);
    *(_QWORD *)(v12 + 88) = *v32;
    if ( v31 )
    {
      v33 = *(_QWORD *)(v12 + 104);
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      v34 = *(void **)(v12 + 96);
      *(_QWORD *)(v12 + 104) = 0;
      if ( v34 )
        DeleteObject(v34);
      *(_QWORD *)(v12 + 96) = 0;
    }
    *(_BYTE *)(v12 + 139) = 3;
    *(_DWORD *)(v11 + 184) &= ~0x10000000u;
  }
  else
  {
    v32 = v54;
  }
  v35 = -2147467259;
  if ( (unsigned __int16)(*(_WORD *)this - 3) <= 1u )
    goto LABEL_78;
  if ( !v15 )
    goto LABEL_77;
  hmf[1] = (HENHMETAFILE)v15(this, v32);
  if ( hmf[1] )
  {
    v36 = a5;
    if ( a5 )
    {
      if ( !polesite )
        goto LABEL_78;
      lpVtbl = polesite[7].lpVtbl;
      if ( !lpVtbl )
        goto LABEL_78;
      p_poleobj = &a2->poleobj;
      (*(void (__fastcall **)(struct IOleClientSiteVtbl *, GUID *, LPOLEOBJECT *))lpVtbl->QueryInterface)(
        lpVtbl,
        &IID_IOleObject,
        &a2->poleobj);
      v41 = 1;
      LODWORD(v52) = 4;
      if ( !a6 )
        LODWORD(v52) = 1;
    }
    else
    {
      Ole32Procs = CThreadData::GetOle32Procs();
      v38 = (struct COLE32_PROC *)((char *)Ole32Procs + 304);
      if ( !*((_QWORD *)Ole32Procs + 38) )
        SetProcAddr((char *)Ole32Procs + 304, (unsigned int)(v36 + 1), "OleCreateDefaultHandler");
      v39 = *(__int64 (__fastcall **)(CLSID *, _QWORD, GUID *, LPOLEOBJECT *))v38;
      if ( !*(_QWORD *)v38 )
        goto LABEL_78;
      p_poleobj = &a2->poleobj;
      v35 = v39(&a2->clsid, 0, &IID_IOleObject, &a2->poleobj);
      if ( v35 )
        goto LABEL_78;
      v35 = CW32System::WriteClassStg(a2->pstg, &a2->clsid);
      if ( v35 )
        goto LABEL_78;
      v35 = ((__int64 (__fastcall *)(LPOLEOBJECT, GUID *, struct IStream **))(*p_poleobj)->lpVtbl->QueryInterface)(
              *p_poleobj,
              &IID_IPersistStorage,
              &a8);
      if ( v35 )
        goto LABEL_78;
      v35 = (*(__int64 (__fastcall **)(struct IStream *, LPSTORAGE))(*(_QWORD *)a8 + 40LL))(a8, a2->pstg);
      if ( v35 )
        goto LABEL_78;
      v41 = 2;
    }
    if ( !*p_poleobj
      || (v35 = ((__int64 (__fastcall *)(LPOLEOBJECT, GUID *, struct CTxtRange **))(*p_poleobj)->lpVtbl->QueryInterface)(
                  *p_poleobj,
                  &IID_IOleCache,
                  &a7)) == 0 )
    {
      if ( a7 )
      {
        v35 = (*(__int64 (__fastcall **)(struct CTxtRange *, __int128 *, _QWORD, int *))(*(_QWORD *)a7 + 24LL))(
                a7,
                &v51,
                v41,
                &v53);
        if ( v35 < 0 )
          goto LABEL_78;
        v43 = (*(__int64 (__fastcall **)(struct CTxtRange *, __int128 *, HENHMETAFILE *, __int64))(*(_QWORD *)a7 + 56LL))(
                a7,
                &v51,
                hmf,
                1);
        v35 = v43;
        if ( v43 )
        {
          if ( v43 >= 0 )
            hmf[1] = 0;
          goto LABEL_78;
        }
        hmf[1] = 0;
      }
      if ( v36 )
      {
        *(SIZEL *)((char *)polesite + 84) = a2->sizel;
        goto LABEL_77;
      }
      (*(void (__fastcall **)(__int64, LPOLECLIENTSITE *))(*(_QWORD *)(v11 + 8) + 24LL))(v11 + 8, p_polesite);
      if ( !*p_polesite )
        goto LABEL_78;
      if ( *p_poleobj )
      {
        v35 = ((__int64 (__fastcall *)(LPOLEOBJECT))(*p_poleobj)->lpVtbl->SetClientSite)(*p_poleobj);
        if ( v35 )
          goto LABEL_78;
      }
      if ( *p_poleobj )
        goto LABEL_77;
      if ( *(_WORD *)this == 2 )
      {
        v44 = *p_polesite;
        v45 = operator new(0x10u);
        v45[2] = 0;
        *((_WORD *)v45 + 6) = 0;
        v46 = v54;
        *(_QWORD *)v45 = 0;
        v44[14].lpVtbl = (struct IOleClientSiteVtbl *)*v46;
        *v45 = *((_DWORD *)this + 8);
        v45[1] = *((_DWORD *)this + 9);
        *((_WORD *)v45 + 4) = *((_WORD *)this + 20);
        *((_WORD *)v45 + 5) = *((_WORD *)this + 21);
        *((_WORD *)v45 + 6) = *((_WORD *)this + 4);
        v44[16].lpVtbl = (struct IOleClientSiteVtbl *)v45;
        hmf[1] = 0;
LABEL_77:
        v35 = 0;
      }
    }
  }
LABEL_78:
  if ( a7 )
    (*(void (__fastcall **)(struct CTxtRange *))(*(_QWORD *)a7 + 16LL))(a7);
  if ( a8 )
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)a8 + 16LL))(a8);
  if ( hmf[1] )
  {
    if ( *(_WORD *)this )
    {
      if ( *(_WORD *)this == 1 )
      {
        GlobalUnlock(hmf[1]);
        CW32System::GlobalFree(hmf[1]);
      }
      else if ( *(_WORD *)this == 9 )
      {
        DeleteEnhMetaFile(hmf[1]);
      }
    }
    else
    {
      DeleteObject(hmf[1]);
    }
  }
  return (unsigned int)v35;
}

```

## disassembly

```asm
0x18015849c  mov     [rsp-38h+arg_0], rbx
0x1801584a1  mov     [rsp-38h+arg_18], r9d
0x1801584a6  mov     [rsp-38h+arg_10], r8
0x1801584ab  push    rbp
0x1801584ac  push    rsi
0x1801584ad  push    rdi
0x1801584ae  push    r12
0x1801584b0  push    r13
0x1801584b2  push    r14
0x1801584b4  push    r15
0x1801584b6  mov     rbp, rsp
0x1801584b9  sub     rsp, 80h
0x1801584c0  mov     rax, [rbp+arg_30]
0x1801584c4  xor     r12d, r12d
0x1801584c7  mov     rdi, rcx
0x1801584ca  mov     [rbp+arg_8], r12d
0x1801584ce  mov     rsi, rdx
0x1801584d1  mov     rcx, [rax+18h]
0x1801584d5  test    rcx, rcx
0x1801584d8  jz      short loc_1801584E0
0x1801584da  mov     r15, [rcx+28h]
0x1801584de  jmp     short loc_1801584E3
0x1801584e0  mov     r15, r12
0x1801584e3  xorps   xmm0, xmm0
0x1801584e6  xor     eax, eax
0x1801584e8  movups  [rbp+var_28], xmm0
0x1801584ec  movups  [rbp+var_18], xmm0
0x1801584f0  mov     rbx, [r15+100h]
0x1801584f7  mov     [rbp+arg_30], r12
0x1801584fb  mov     [rbp+arg_38], r12
0x1801584ff  movups  xmmword ptr [rbp+hmf], xmm0
0x180158503  mov     [rbp+var_30], rax
0x180158507  mov     rax, [r15+0F0h]
0x18015850e  test    rax, rax
0x180158511  jz      loc_180158AD6
0x180158517  lea     rcx, [rdx+28h]
0x18015851b  mov     [rbp+var_48], rcx
0x18015851f  mov     rcx, [rcx]
0x180158522  mov     [rbp+var_50], rcx
0x180158526  cmp     [rax+18h], r12
0x18015852a  jz      loc_180158AD6
0x180158530  mov     rcx, r15; this
0x180158533  call    ?GetObjectMgr@CTxtEdit@@QEAAPEAVCObjectMgr@@XZ; CTxtEdit::GetObjectMgr(void)
0x180158538  test    rax, rax
0x18015853b  jz      loc_180158AD6
0x180158541  mov     eax, [rdi+20h]
0x180158544  mov     edx, 1
0x180158549  sub     eax, edx
0x18015854b  mov     qword ptr [rbp+var_28+8], r12
0x18015854f  mov     r8d, 3E7h
0x180158555  mov     dword ptr [rbp+var_18], edx
0x180158558  mov     dword ptr [rbp+var_18+4], 0FFFFFFFFh
0x18015855f  mov     r14, r12
0x180158562  mov     dword ptr [rbp+var_18+8], r12d
0x180158566  lea     ecx, [rdx+63h]
0x180158569  mov     r11d, r12d
0x18015856c  cmp     eax, r8d
0x18015856f  jbe     short loc_180158574
0x180158571  mov     [rdi+20h], ecx
0x180158574  mov     eax, [rdi+24h]
0x180158577  sub     eax, edx
0x180158579  cmp     eax, r8d
0x18015857c  jbe     short loc_180158581
0x18015857e  mov     [rdi+24h], ecx
0x180158581  movsx   ecx, word ptr [rdi]
0x180158584  mov     eax, 3
0x180158589  lea     r8d, [rax-1]
0x18015858d  lea     r9d, [rax+5]
0x180158591  test    ecx, ecx
0x180158593  jz      short loc_1801585FA
0x180158595  sub     ecx, edx
0x180158597  jz      short loc_1801585E0
0x180158599  sub     ecx, edx
0x18015859b  jz      short loc_1801585C5
0x18015859d  sub     ecx, edx
0x18015859f  jz      short loc_180158601
0x1801585a1  sub     ecx, edx
0x1801585a3  jz      short loc_180158601
0x1801585a5  cmp     ecx, 5
0x1801585a8  jnz     short loc_18015861C
0x1801585aa  movups  xmm0, xmmword ptr cs:CLSID_Picture_EnhMetafile.Data1
0x1801585b1  lea     eax, [rcx+9]
0x1801585b4  mov     word ptr [rbp+var_28], ax
0x1801585b8  lea     r11d, [r8+3Eh]
0x1801585bc  lea     r14, ?ObHBuildEnhMetafilePict@@YAPEAXPEAVCRTFObject@@AEAPEAX@Z; ObHBuildEnhMetafilePict(CRTFObject *,void * &)
0x1801585c3  jmp     short loc_180158613
0x1801585c5  movups  xmm0, xmmword ptr cs:CLSID_StaticDib.Data1
0x1801585cc  mov     word ptr [rbp+var_28], r9w
0x1801585d1  lea     r14, ?ObHBuildDib@@YAPEAXPEAVCRTFObject@@AEAPEAX@Z; ObHBuildDib(CRTFObject *,void * &)
0x1801585d8  mov     r11d, edx
0x1801585db  mov     dword ptr [rbp+var_18+8], edx
0x1801585de  jmp     short loc_180158617
0x1801585e0  movups  xmm0, xmmword ptr cs:CLSID_StaticMetafile.Data1
0x1801585e7  mov     word ptr [rbp+var_28], ax
0x1801585eb  lea     r14, ?ObHBuildMetafilePict@@YAPEAXPEAVCRTFObject@@AEAPEAX@Z; ObHBuildMetafilePict(CRTFObject *,void * &)
0x1801585f2  mov     r11d, 20h ; ' '
0x1801585f8  jmp     short loc_180158613
0x1801585fa  lea     r14, ?ObHBuildBitmap@@YAPEAXPEAVCRTFObject@@AEAPEAX@Z; ObHBuildBitmap(CRTFObject *,void * &)
0x180158601  movups  xmm0, xmmword ptr cs:CLSID_StaticDib.Data1
0x180158608  mov     r11d, 10h
0x18015860e  mov     word ptr [rbp+var_28], r8w
0x180158613  mov     dword ptr [rbp+var_18+8], r11d
0x180158617  movdqu  xmmword ptr [rsi+8], xmm0
0x18015861c  mov     [rsi+38h], edx
0x18015861f  mov     r8d, 48h ; 'H'; int
0x180158625  movsx   ecx, word ptr [rdi+28h]; int
0x180158629  lea     r13d, [r8+37h]
0x18015862d  mov     edx, r13d; int
0x180158630  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180158635  mov     [rsi+30h], eax
0x180158638  lea     r8d, [r13-37h]; int
0x18015863c  movsx   ecx, word ptr [rdi+2Ah]; int
0x180158640  mov     edx, r13d; int
0x180158643  mov     r12d, eax
0x180158646  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18015864b  mov     [rsi+34h], eax
0x18015864e  mov     r13d, eax
0x180158651  mov     edx, [rdi+20h]; int
0x180158654  lea     ecx, [rdx-1]
0x180158657  cmp     ecx, 3E7h
0x18015865d  ja      short loc_180158670
0x18015865f  mov     r8d, 64h ; 'd'; int
0x180158665  mov     ecx, r12d; int
0x180158668  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18015866d  mov     [rsi+30h], eax
0x180158670  mov     edx, [rdi+24h]; int
0x180158673  lea     eax, [rdx-1]
0x180158676  cmp     eax, 3E7h
0x18015867b  ja      short loc_18015868E
0x18015867d  mov     r8d, 64h ; 'd'; int
0x180158683  mov     ecx, r13d; int
0x180158686  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18015868b  mov     [rsi+34h], eax
0x18015868e  xor     r13d, r13d
0x180158691  mov     dword ptr [rbp+hmf], r11d
0x180158695  xorps   xmm0, xmm0
0x180158698  movdqu  xmmword ptr [rbp+hmf+8], xmm0
0x18015869d  test    rbx, rbx
0x1801586a0  jz      loc_1801587C9
0x1801586a6  cmp     [rbp+arg_18], r13d
0x1801586aa  jz      loc_1801587C9
0x1801586b0  mov     al, [rdi]
0x1801586b2  mov     edx, 0FFFFh
0x1801586b7  mov     [rbx+8Fh], al
0x1801586bd  mov     al, [rdi+2]
0x1801586c0  mov     [rbx+90h], al
0x1801586c6  mov     ecx, [rdi+14h]
0x1801586c9  lea     eax, [rcx+8000h]
0x1801586cf  cmp     eax, edx
0x1801586d1  ja      loc_1801587C3
0x1801586d7  mov     [rbx+0A4h], cx
0x1801586de  mov     ecx, [rdi+18h]
0x1801586e1  lea     eax, [rcx+8000h]
0x1801586e7  cmp     eax, edx
0x1801586e9  ja      loc_1801587C3
0x1801586ef  mov     [rbx+0A6h], cx
0x1801586f6  mov     ecx, [rdi+20h]
0x1801586f9  lea     eax, [rcx+8000h]
0x1801586ff  cmp     eax, edx
0x180158701  ja      loc_1801587C3
0x180158707  mov     [rbx+0A8h], cx
0x18015870e  mov     ecx, [rdi+24h]
0x180158711  lea     eax, [rcx+8000h]
0x180158717  cmp     eax, edx
0x180158719  ja      loc_1801587C3
0x18015871f  mov     [rbx+0AAh], cx
0x180158726  movzx   eax, word ptr [rdi+28h]
0x18015872a  mov     [rbx+0ACh], ax
0x180158731  movzx   eax, word ptr [rdi+2Ah]
0x180158735  mov     [rbx+0AEh], ax
0x18015873c  mov     ecx, [rdi+60h]
0x18015873f  lea     eax, [rcx+8000h]
0x180158745  cmp     eax, edx
0x180158747  ja      short loc_1801587C3
0x180158749  mov     [rbx+0B0h], cx
0x180158750  mov     ecx, [rdi+64h]
0x180158753  lea     eax, [rcx+8000h]
0x180158759  cmp     eax, edx
0x18015875b  ja      short loc_1801587C3
0x18015875d  cmp     byte ptr [rbx+8Bh], 3
0x180158764  mov     r12, [rbp+arg_10]
0x180158768  mov     [rbx+0B2h], cx
0x18015876f  movups  xmm0, xmmword ptr [rdi+34h]
0x180158773  movdqu  xmmword ptr [rbx+94h], xmm0
0x18015877b  mov     rax, [r12]
0x18015877f  mov     [rbx+58h], rax
0x180158783  jnz     short loc_1801587B1
0x180158785  mov     rcx, [rbx+68h]
0x180158789  test    rcx, rcx
0x18015878c  jz      short loc_18015879A
0x18015878e  mov     rax, [rcx]
0x180158791  mov     rax, [rax+10h]
0x180158795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015879a  mov     rcx, [rbx+60h]; ho
0x18015879e  mov     [rbx+68h], r13
0x1801587a2  test    rcx, rcx
0x1801587a5  jz      short loc_1801587AD
0x1801587a7  call    cs:__imp_DeleteObject
0x1801587ad  mov     [rbx+60h], r13
0x1801587b1  mov     byte ptr [rbx+8Bh], 3
0x1801587b8  btr     dword ptr [r15+0B8h], 1Ch
0x1801587c1  jmp     short loc_1801587CD
0x1801587c3  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x1801587c9  mov     r12, [rbp+arg_10]
0x1801587cd  movzx   ecx, word ptr [rdi]
0x1801587d0  mov     eax, 1
0x1801587d5  sub     cx, 3
0x1801587d9  mov     ebx, 80004005h
0x1801587de  cmp     cx, ax
0x1801587e1  jbe     loc_180158A67
0x1801587e7  test    r14, r14
0x1801587ea  jz      loc_180158A65
0x1801587f0  mov     rdx, r12
0x1801587f3  mov     rcx, rdi
0x1801587f6  mov     rax, r14
0x1801587f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801587fe  mov     [rbp+hmf+8], rax
0x180158802  test    rax, rax
0x180158805  jz      loc_180158A67
0x18015880b  mov     r13d, [rbp+arg_20]
0x18015880f  test    r13d, r13d
0x180158812  jnz     loc_1801588CA
0x180158818  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18015881d  lea     r14, [rax+130h]
0x180158824  cmp     qword ptr [r14], 0
0x180158828  jnz     short loc_18015883D
0x18015882a  lea     r8, aOlecreatedefau; "OleCreateDefaultHandler"
0x180158831  mov     rcx, r14
0x180158834  lea     edx, [r13+1]
0x180158838  call    ?SetProcAddr@@YAXAEAPEAXW4DLL_ENUM@@PEBD@Z; SetProcAddr(void * &,DLL_ENUM,char const *)
0x18015883d  mov     rax, [r14]
0x180158840  test    rax, rax
0x180158843  jz      loc_180158A67
0x180158849  lea     r14, [rsi+18h]
0x18015884d  xor     edx, edx
0x18015884f  mov     r9, r14
0x180158852  lea     r8, IID_IOleObject
0x180158859  lea     rcx, [rsi+8]
0x18015885d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158862  mov     ebx, eax
0x180158864  test    eax, eax
0x180158866  jnz     loc_180158A67
0x18015886c  mov     rcx, [rsi+20h]; struct IStorage *
0x180158870  lea     rdx, [rsi+8]; struct _GUID *
0x180158874  call    ?WriteClassStg@CW32System@@SAJPEAUIStorage@@AEBU_GUID@@@Z; CW32System::WriteClassStg(IStorage *,_GUID const &)
0x180158879  mov     ebx, eax
0x18015887b  test    eax, eax
0x18015887d  jnz     loc_180158A67
0x180158883  mov     rcx, [r14]
0x180158886  lea     r8, [rbp+arg_38]
0x18015888a  lea     rdx, IID_IPersistStorage
0x180158891  mov     rax, [rcx]
0x180158894  mov     rax, [rax]
0x180158897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015889c  mov     ebx, eax
0x18015889e  test    eax, eax
0x1801588a0  jnz     loc_180158A67
0x1801588a6  mov     rcx, [rbp+arg_38]
0x1801588aa  mov     rdx, [rsi+20h]
0x1801588ae  mov     rax, [rcx]
0x1801588b1  mov     rax, [rax+28h]
0x1801588b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801588ba  mov     ebx, eax
0x1801588bc  test    eax, eax
0x1801588be  jnz     loc_180158A67
0x1801588c4  lea     r12d, [rax+2]
0x1801588c8  jmp     short loc_180158915
0x1801588ca  mov     rax, [rbp+var_50]
0x1801588ce  test    rax, rax
0x1801588d1  jz      loc_180158A67
0x1801588d7  mov     rcx, [rax+38h]
0x1801588db  test    rcx, rcx
0x1801588de  jz      loc_180158A67
0x1801588e4  mov     rax, [rcx]
0x1801588e7  lea     r14, [rsi+18h]
0x1801588eb  mov     r8, r14
0x1801588ee  lea     rdx, IID_IOleObject
0x1801588f5  mov     rax, [rax]
0x1801588f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801588fd  cmp     [rbp+arg_28], 0
0x180158901  mov     eax, 1
0x180158906  mov     r12d, eax
0x180158909  mov     dword ptr [rbp+var_18], 4
0x180158910  jnz     short loc_180158915
0x180158912  mov     dword ptr [rbp+var_18], eax
0x180158915  mov     rcx, [r14]
0x180158918  test    rcx, rcx
0x18015891b  jz      short loc_18015893D
0x18015891d  mov     rax, [rcx]
0x180158920  lea     r8, [rbp+arg_30]
0x180158924  lea     rdx, IID_IOleCache
0x18015892b  mov     rax, [rax]
0x18015892e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180158933  mov     ebx, eax
0x180158935  test    eax, eax
0x180158937  jnz     loc_180158A67
0x18015893d  mov     rcx, [rbp+arg_30]
0x180158941  test    rcx, rcx
0x180158944  jz      short loc_1801589A6
0x180158946  mov     rax, [rcx]
  ... truncated ...
```
