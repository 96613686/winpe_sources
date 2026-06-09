# CRTFRead::StaticObjectReadFromEditStream(int)

- ea: `0x18007cb94`
- end: `0x18007d366`
- name: `?StaticObjectReadFromEditStream@CRTFRead@@AEAAHH@Z`
- size: `2002`
- prototype: `__int64 __fastcall(CRTFRead *this, unsigned int)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800026c0`

## callees

- `0x180022780`
- `0x180023010`
- `0x180032db0`
- `0x180038bd0`
- `0x180041adc`
- `0x18004a8fc`
- `0x18005bb98`
- `0x18006fe60`
- `0x18007cb94`
- `0x1800907ac`
- `0x18009110a`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x18007cef8`
- `KERNEL32!GlobalAlloc` at `0x18007cef8`
- `KERNEL32!GlobalLock` at `0x18007cf06`
- `KERNEL32!GlobalLock` at `0x18007cf06`
- `KERNEL32!GlobalUnlock` at `0x18007ce15`
- `KERNEL32!GlobalUnlock` at `0x18007ce4e`
- `KERNEL32!GlobalUnlock` at `0x18007cf88`
- `KERNEL32!GlobalUnlock` at `0x18007ce15`
- `KERNEL32!GlobalUnlock` at `0x18007ce4e`
- `KERNEL32!GlobalUnlock` at `0x18007cf88`
- `GDI32!DeleteObject` at `0x18007d323`
- `GDI32!DeleteObject` at `0x18007d323`

## string_xrefs

- `0x18007ce77`: `CreateStreamOnHGlobal`
- `0x18007d03c`: `OleCreateDefaultHandler`

## pseudocode

```c
__int64 __fastcall CRTFRead::StaticObjectReadFromEditStream(CRTFRead *this, unsigned int a2)
{
  SIZE_T v2; // r14
  CTxtEdit *v4; // rcx
  void *(__fastcall *v5)(struct _rtfobject *, void **); // r12
  int v6; // edi
  void *v7; // r15
  __int64 v8; // r13
  __int16 *v9; // rdx
  __int16 v10; // ax
  int v11; // ecx
  int v12; // ecx
  GUID v13; // xmm0
  int v14; // ebx
  int v15; // ecx
  __int64 v16; // rbx
  int v17; // ecx
  _WORD *v18; // rax
  struct COLE32_PROC *Ole32Procs; // rax
  struct COLE32_PROC *v20; // rbx
  _DWORD *v21; // rbx
  int v22; // eax
  __int64 v23; // r8
  __int64 v24; // rbx
  struct COLE32_PROC *v25; // rax
  __int64 (__fastcall **v26)(__int64, HGLOBAL *); // rdi
  void *v27; // rax
  struct COLE32_PROC *v28; // rax
  __int64 (__fastcall **v29)(CLSID *, _QWORD, GUID *, LPOLEOBJECT *); // rbx
  unsigned int v30; // ebx
  __int64 v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, GUID *, LPOLEOBJECT *); // rcx
  int v33; // eax
  LPOLECLIENTSITE polesite; // rbx
  _DWORD *v35; // rax
  LONG *v36; // rcx
  struct IUndoBuilder *v37; // r9
  int inserted; // eax
  __int16 v40; // [rsp+44h] [rbp-BCh] BYREF
  HGLOBAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-A8h] BYREF
  int v44; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+68h] [rbp-98h] BYREF
  HGLOBAL ho[3]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v47; // [rsp+88h] [rbp-78h] BYREF
  __int128 v48; // [rsp+98h] [rbp-68h]
  __int64 v49; // [rsp+A8h] [rbp-58h]
  CObjectMgr *ObjectMgr; // [rsp+B0h] [rbp-50h]
  struct _reobject v51; // [rsp+C0h] [rbp-40h] BYREF

  v2 = a2;
  v44 = 0;
  v4 = (CTxtEdit *)*((_QWORD *)this + 7);
  v40 = -4;
  v5 = 0;
  v47 = 0;
  hMem = 0;
  v6 = -2147467259;
  v48 = 0;
  ObjectMgr = CTxtEdit::GetObjectMgr(v4);
  v45 = 0;
  v42 = 0;
  memset_0(&v51, 0, sizeof(v51));
  v43 = 0;
  v7 = 0;
  memset(ho, 0, sizeof(ho));
  if ( !ObjectMgr )
    goto LABEL_16;
  v8 = *((_QWORD *)ObjectMgr + 4);
  v9 = (__int16 *)*((_QWORD *)this + 79);
  *((_QWORD *)&v47 + 1) = 0;
  v10 = 2;
  LODWORD(v48) = 1;
  *(_QWORD *)((char *)&v48 + 4) = 0xFFFFFFFFLL;
  v11 = *v9;
  v49 = v8;
  if ( !v11 )
  {
    DWORD2(v48) = 16;
    v5 = ObHBuildBitmap;
LABEL_8:
    v13 = CLSID_StaticDib;
    LOWORD(v47) = v10;
    goto LABEL_9;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    if ( v12 != 1 )
      goto LABEL_10;
    v10 = 8;
    DWORD2(v48) = 1;
    v5 = ObHBuildDib;
    goto LABEL_8;
  }
  v13 = CLSID_StaticMetafile;
  LOWORD(v47) = 3;
  v5 = ObHBuildMetafilePict;
  DWORD2(v48) = 32;
LABEL_9:
  v51.clsid = v13;
LABEL_10:
  v14 = *((_DWORD *)v9 + 6);
  v15 = v14 * CW32System::MulDiv(v9[16], 127, 72);
  v16 = *((_QWORD *)this + 79);
  v51.sizel.cx = v15 / 100;
  v17 = *(_DWORD *)(v16 + 28) * CW32System::MulDiv(*(__int16 *)(v16 + 34), 127, 72);
  *(_OWORD *)&ho[1] = 0;
  v51.sizel.cy = v17 / 100;
  LODWORD(ho[0]) = DWORD2(v48);
  if ( v8 )
  {
    if ( (*((_BYTE *)this + 472) & 4) == 0 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, LPSTORAGE *))(*(_QWORD *)v8 + 24LL))(v8, &v51.pstg);
      if ( v6 )
        goto LABEL_13;
    }
    Ole32Procs = CThreadData::GetOle32Procs();
    v20 = (struct COLE32_PROC *)((char *)Ole32Procs + 272);
    if ( !*((_QWORD *)Ole32Procs + 34) )
      SetProcAddr((char *)Ole32Procs + 272, 1, "CreateStreamOnHGlobal");
    if ( *(_QWORD *)v20 )
    {
      v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))v20)(0, 0, &v43);
      if ( !v6 )
      {
        LODWORD(v2) = 0x4000;
        while ( 1 )
        {
          v7 = CW32System::PvAlloc(v2, 0);
          if ( v7 )
            goto LABEL_48;
          LODWORD(v2) = v2 - 1024;
          if ( (int)v2 < 1024 )
            goto LABEL_42;
        }
      }
    }
    else
    {
      v6 = -2147467259;
    }
    LODWORD(v5) = 0;
    goto LABEL_14;
  }
  if ( !(_DWORD)v2 )
    goto LABEL_46;
  hMem = GlobalAlloc(0, v2);
  v7 = GlobalLock(hMem);
  if ( !v7 )
    goto LABEL_13;
LABEL_48:
  v21 = (_DWORD *)((char *)this + 48);
  while ( 1 )
  {
    v22 = (**((__int64 (__fastcall ***)(char *, void *, _QWORD))this + 80))((char *)this + 640, v7, (unsigned int)v2);
    v23 = (unsigned int)v22;
    if ( v22 <= 0 )
      break;
    v21 = (_DWORD *)((char *)this + 48);
    if ( *((_DWORD *)this + 12) )
      break;
    if ( v43 )
    {
      v6 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, _QWORD))(*(_QWORD *)v43 + 32LL))(
             v43,
             v7,
             (unsigned int)v22,
             0);
      if ( v6 )
        goto LABEL_42;
    }
  }
  if ( *v21 )
    goto LABEL_13;
  if ( hMem )
  {
    GlobalUnlock(hMem);
    v7 = 0;
  }
  v24 = v43;
  if ( v43 )
  {
    v25 = CThreadData::GetOle32Procs();
    v26 = (__int64 (__fastcall **)(__int64, HGLOBAL *))((char *)v25 + 280);
    if ( !*((_QWORD *)v25 + 35) )
      SetProcAddr((char *)v25 + 280, 1, "GetHGlobalFromStream");
    if ( !*v26 )
      goto LABEL_73;
    v6 = (*v26)(v24, &hMem);
    if ( v6 )
      goto LABEL_13;
  }
  if ( !v5 )
  {
LABEL_46:
    LODWORD(v5) = 1;
    goto LABEL_14;
  }
  v27 = (void *)((__int64 (__fastcall *)(_QWORD, HGLOBAL *, __int64))v5)(*((_QWORD *)this + 79), &hMem, v23);
  ho[1] = v27;
  if ( !v49 )
    goto LABEL_84;
  if ( !v27 )
    goto LABEL_13;
  if ( (*((_BYTE *)this + 472) & 4) == 0 )
  {
    v28 = CThreadData::GetOle32Procs();
    v29 = (__int64 (__fastcall **)(CLSID *, _QWORD, GUID *, LPOLEOBJECT *))((char *)v28 + 288);
    if ( !*((_QWORD *)v28 + 36) )
      SetProcAddr((char *)v28 + 288, 1, "OleCreateDefaultHandler");
    if ( *v29 )
    {
      v6 = (*v29)(&v51.clsid, 0, &IID_IOleObject, &v51.poleobj);
      if ( !v6 )
      {
        v6 = ((__int64 (__fastcall *)(LPOLEOBJECT, GUID *, __int64 *))v51.poleobj->lpVtbl->QueryInterface)(
               v51.poleobj,
               &IID_IPersistStorage,
               &v45);
        if ( v6 )
          goto LABEL_42;
        v6 = (*(__int64 (__fastcall **)(__int64, LPSTORAGE))(*(_QWORD *)v45 + 40LL))(v45, v51.pstg);
        if ( v6 )
          goto LABEL_42;
        v30 = 2;
        goto LABEL_78;
      }
LABEL_13:
      LODWORD(v5) = 0;
      goto LABEL_14;
    }
LABEL_73:
    v6 = -2147467259;
    goto LABEL_13;
  }
  v31 = *((_QWORD *)this + 58);
  if ( !v31 )
    goto LABEL_73;
  v32 = *(__int64 (__fastcall ****)(_QWORD, GUID *, LPOLEOBJECT *))(v31 + 72);
  if ( !v32 )
    goto LABEL_73;
  v6 = (**v32)(v32, &IID_IOleObject, &v51.poleobj);
  if ( v6 < 0 )
    goto LABEL_13;
  v30 = 1;
  LODWORD(v48) = (*((_BYTE *)this + 472) & 2) != 0 ? 4 : 1;
LABEL_78:
  v6 = ((__int64 (__fastcall *)(LPOLEOBJECT, GUID *, __int64 *))v51.poleobj->lpVtbl->QueryInterface)(
         v51.poleobj,
         &IID_IOleCache,
         &v42);
  if ( v6 )
    goto LABEL_13;
  v6 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, int *))(*(_QWORD *)v42 + 24LL))(v42, &v47, v30, &v44);
  if ( v6 < 0 )
    goto LABEL_13;
  v33 = (*(__int64 (__fastcall **)(__int64, __int128 *, HGLOBAL *, __int64))(*(_QWORD *)v42 + 56LL))(v42, &v47, ho, 1);
  v6 = v33;
  if ( v33 )
  {
    if ( v33 >= 0 )
    {
      ho[1] = 0;
      goto LABEL_13;
    }
    goto LABEL_42;
  }
  ho[1] = 0;
LABEL_84:
  if ( (*((_BYTE *)this + 472) & 4) == 0 )
  {
    (*(void (__fastcall **)(__int64, LPOLECLIENTSITE *))(*(_QWORD *)(*((_QWORD *)this + 7) + 8LL) + 24LL))(
      *((_QWORD *)this + 7) + 8LL,
      &v51.polesite);
    if ( !v51.polesite )
      goto LABEL_13;
    if ( v51.poleobj )
    {
      v6 = ((__int64 (__fastcall *)(LPOLEOBJECT))v51.poleobj->lpVtbl->SetClientSite)(v51.poleobj);
      if ( v6 )
        goto LABEL_42;
      if ( v51.poleobj )
        goto LABEL_92;
    }
    if ( **((_WORD **)this + 79) != 2 )
      goto LABEL_13;
    polesite = v51.polesite;
    v35 = CW32System::PvAlloc(0x10u, 0x40u);
    if ( v35 )
    {
      polesite[15].lpVtbl = (struct IOleClientSiteVtbl *)hMem;
      *v35 = *(_DWORD *)(*((_QWORD *)this + 79) + 24LL);
      v35[1] = *(_DWORD *)(*((_QWORD *)this + 79) + 28LL);
      *((_WORD *)v35 + 4) = *(_WORD *)(*((_QWORD *)this + 79) + 32LL);
      *((_WORD *)v35 + 5) = *(_WORD *)(*((_QWORD *)this + 79) + 34LL);
      *((_WORD *)v35 + 6) = *(_WORD *)(*((_QWORD *)this + 79) + 8LL);
      polesite[17].lpVtbl = (struct IOleClientSiteVtbl *)v35;
      ho[1] = 0;
LABEL_92:
      v36 = (LONG *)*((_QWORD *)this + 8);
      v51.cbStruct = 72;
      v51.cp = v36[10];
      v51.dvaspect = 1;
      v51.dwFlags = 1;
      CTxtRange::Set_iCF((CTxtRange *)v36, -1);
      (*(void (__fastcall **)(_QWORD, __int64, __int16 *, _QWORD, _DWORD, _QWORD, _DWORD))(**((_QWORD **)this + 8)
                                                                                         + 560LL))(
        *((_QWORD *)this + 8),
        1,
        &v40,
        0,
        0,
        0,
        0);
      inserted = CObjectMgr::InsertObject(ObjectMgr, v51.cp, &v51, v37);
      v6 = 0;
      if ( inserted != 1 )
        v6 = inserted;
      goto LABEL_96;
    }
LABEL_42:
    LODWORD(v5) = 0;
    goto LABEL_14;
  }
  *(SIZEL *)(*((_QWORD *)this + 58) + 104LL) = v51.sizel;
LABEL_96:
  LODWORD(v5) = 1;
LABEL_14:
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
LABEL_16:
  if ( v51.pstg )
    ((void (__fastcall *)(LPSTORAGE))v51.pstg->lpVtbl->Release)(v51.pstg);
  if ( v51.polesite )
    ((void (__fastcall *)(LPOLECLIENTSITE))v51.polesite->lpVtbl->Release)(v51.polesite);
  if ( v51.poleobj )
    ((void (__fastcall *)(LPOLEOBJECT))v51.poleobj->lpVtbl->Release)(v51.poleobj);
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    CW32System::FreePv(v7);
    v7 = 0;
  }
  if ( v6 || *((_DWORD *)this + 12) )
  {
    if ( v7 )
      GlobalUnlock(hMem);
    CW32System::GlobalFree(hMem);
  }
  if ( ho[1] )
  {
    v18 = (_WORD *)*((_QWORD *)this + 79);
    if ( *v18 )
    {
      if ( *v18 == 1 )
      {
        GlobalUnlock(ho[1]);
        CW32System::GlobalFree(ho[1]);
      }
    }
    else
    {
      DeleteObject(ho[1]);
    }
  }
  *((_QWORD *)this + 58) = 0;
  *((_WORD *)this + 236) &= 0xFFF9u;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007cb94  mov     [rsp-8+arg_10], rbx
0x18007cb99  push    rbp
0x18007cb9a  push    rsi
0x18007cb9b  push    rdi
0x18007cb9c  push    r12
0x18007cb9e  push    r13
0x18007cba0  push    r14
0x18007cba2  push    r15
0x18007cba4  lea     rbp, [rsp-20h]
0x18007cba9  sub     rsp, 120h
0x18007cbb0  mov     rax, cs:__security_cookie
0x18007cbb7  xor     rax, rsp
0x18007cbba  mov     [rbp+50h+var_40], rax
0x18007cbbe  xor     r13d, r13d
0x18007cbc1  mov     r14d, edx
0x18007cbc4  xorps   xmm0, xmm0
0x18007cbc7  mov     [rsp+150h+var_F0], r13d
0x18007cbcc  mov     rsi, rcx
0x18007cbcf  mov     [rsp+150h+var_110], r13d
0x18007cbd4  mov     rcx, [rcx+38h]; this
0x18007cbd8  mov     eax, 0FFFCh
0x18007cbdd  mov     [rsp+150h+var_10C], ax
0x18007cbe2  mov     r12d, r13d
0x18007cbe5  movups  [rbp+50h+var_C8], xmm0
0x18007cbe9  mov     [rsp+150h+hMem], r13
0x18007cbee  mov     edi, 80004005h
0x18007cbf3  movups  [rbp+50h+var_B8], xmm0
0x18007cbf7  call    ?GetObjectMgr@CTxtEdit@@QEAAPEAVCObjectMgr@@XZ; CTxtEdit::GetObjectMgr(void)
0x18007cbfc  xor     edx, edx; Val
0x18007cbfe  mov     [rbp+50h+var_A0], rax
0x18007cc02  lea     r8d, [r13+48h]; Size
0x18007cc06  mov     [rsp+150h+var_E8], r13
0x18007cc0b  lea     rcx, [rbp+50h+var_90]; void *
0x18007cc0f  mov     [rsp+150h+var_100], r13
0x18007cc14  mov     rbx, rax
0x18007cc17  call    memset_0
0x18007cc1c  xor     eax, eax
0x18007cc1e  mov     [rsp+150h+var_F8], r13
0x18007cc23  mov     [rbp+50h+var_D0], rax
0x18007cc27  xorps   xmm0, xmm0
0x18007cc2a  mov     r15d, r13d
0x18007cc2d  movups  xmmword ptr [rsp+150h+ho], xmm0
0x18007cc32  test    rbx, rbx
0x18007cc35  jz      loc_18007CD85
0x18007cc3b  mov     r13, [rbx+20h]
0x18007cc3f  lea     r8d, [r15+1]
0x18007cc43  mov     rdx, [rsi+278h]
0x18007cc4a  lea     r9d, [r15+3]
0x18007cc4e  mov     qword ptr [rbp+50h+var_C8+8], rax
0x18007cc52  mov     dword ptr [rbp+50h+var_B8+8], eax
0x18007cc55  lea     eax, [r15+2]
0x18007cc59  mov     dword ptr [rbp+50h+var_B8], r8d
0x18007cc5d  mov     dword ptr [rbp+50h+var_B8+4], 0FFFFFFFFh
0x18007cc64  movsx   ecx, word ptr [rdx]
0x18007cc67  mov     [rbp+50h+var_A8], r13
0x18007cc6b  test    ecx, ecx
0x18007cc6d  jz      short loc_18007CCA6
0x18007cc6f  sub     ecx, r8d
0x18007cc72  jz      short loc_18007CC8A
0x18007cc74  cmp     ecx, r8d
0x18007cc77  jnz     short loc_18007CCC4
0x18007cc79  lea     eax, [r15+8]
0x18007cc7d  mov     dword ptr [rbp+50h+var_B8+8], r8d
0x18007cc81  lea     r12, ?ObHBuildDib@@YAPEAXPEAU_rtfobject@@AEAPEAX@Z; ObHBuildDib(_rtfobject *,void * &)
0x18007cc88  jmp     short loc_18007CCB4
0x18007cc8a  movups  xmm0, xmmword ptr cs:CLSID_StaticMetafile.Data1
0x18007cc91  mov     word ptr [rbp+50h+var_C8], r9w
0x18007cc96  lea     r12, ?ObHBuildMetafilePict@@YAPEAXPEAU_rtfobject@@AEAPEAX@Z; ObHBuildMetafilePict(_rtfobject *,void * &)
0x18007cc9d  mov     dword ptr [rbp+50h+var_B8+8], 20h ; ' '
0x18007cca4  jmp     short loc_18007CCBF
0x18007cca6  mov     dword ptr [rbp+50h+var_B8+8], 10h
0x18007ccad  lea     r12, ?ObHBuildBitmap@@YAPEAXPEAU_rtfobject@@AEAPEAX@Z; ObHBuildBitmap(_rtfobject *,void * &)
0x18007ccb4  movups  xmm0, xmmword ptr cs:CLSID_StaticDib.Data1
0x18007ccbb  mov     word ptr [rbp+50h+var_C8], ax
0x18007ccbf  movdqu  xmmword ptr [rbp+50h+var_90.clsid.Data1], xmm0
0x18007ccc4  mov     ebx, [rdx+18h]
0x18007ccc7  movsx   ecx, word ptr [rdx+20h]; int
0x18007cccb  mov     edx, 7Fh; int
0x18007ccd0  lea     r8d, [rdx-37h]; int
0x18007ccd4  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18007ccd9  mov     ecx, eax
0x18007ccdb  mov     eax, 51EB851Fh
0x18007cce0  imul    ecx, ebx
0x18007cce3  mov     rbx, [rsi+278h]
0x18007ccea  imul    ecx
0x18007ccec  sar     edx, 5
0x18007ccef  mov     eax, edx
0x18007ccf1  shr     eax, 1Fh
0x18007ccf4  add     edx, eax
0x18007ccf6  mov     [rbp+50h+var_90.sizel.cx], edx
0x18007ccf9  mov     edx, 7Fh; int
0x18007ccfe  movsx   ecx, word ptr [rbx+22h]; int
0x18007cd02  lea     r8d, [rdx-37h]; int
0x18007cd06  call    ?MulDiv@CW32System@@SAHHHH@Z; CW32System::MulDiv(int,int,int)
0x18007cd0b  mov     ecx, eax
0x18007cd0d  xorps   xmm0, xmm0
0x18007cd10  imul    ecx, [rbx+1Ch]
0x18007cd14  mov     eax, 51EB851Fh
0x18007cd19  movdqu  xmmword ptr [rsp+150h+ho+8], xmm0
0x18007cd1f  imul    ecx
0x18007cd21  sar     edx, 5
0x18007cd24  mov     eax, edx
0x18007cd26  shr     eax, 1Fh
0x18007cd29  add     edx, eax
0x18007cd2b  mov     eax, dword ptr [rbp+50h+var_B8+8]
0x18007cd2e  mov     [rbp+50h+var_90.sizel.cy], edx
0x18007cd31  mov     dword ptr [rsp+150h+ho], eax
0x18007cd35  test    r13, r13
0x18007cd38  jz      loc_18007CEE3
0x18007cd3e  test    byte ptr [rsi+1D8h], 4
0x18007cd45  jnz     loc_18007CE63
0x18007cd4b  mov     rax, [r13+0]
0x18007cd4f  lea     rdx, [rbp+50h+var_90.pstg]
0x18007cd53  mov     rcx, r13
0x18007cd56  mov     rax, [rax+18h]
0x18007cd5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cd5f  xor     r13d, r13d
0x18007cd62  mov     edi, eax
0x18007cd64  test    eax, eax
0x18007cd66  jz      loc_18007CE66
0x18007cd6c  mov     r12d, r13d
0x18007cd6f  mov     rcx, [rsp+150h+var_100]
0x18007cd74  test    rcx, rcx
0x18007cd77  jz      short loc_18007CD85
0x18007cd79  mov     rax, [rcx]
0x18007cd7c  mov     rax, [rax+10h]
0x18007cd80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cd85  mov     rcx, [rbp+50h+var_90.pstg]
0x18007cd89  test    rcx, rcx
0x18007cd8c  jz      short loc_18007CD9A
0x18007cd8e  mov     rax, [rcx]
0x18007cd91  mov     rax, [rax+10h]
0x18007cd95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cd9a  mov     rdx, [rbp+50h+var_90.polesite]
0x18007cd9e  test    rdx, rdx
0x18007cda1  jz      short loc_18007CDB2
0x18007cda3  mov     rax, [rdx]
0x18007cda6  mov     rcx, rdx
0x18007cda9  mov     rax, [rax+10h]
0x18007cdad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cdb2  mov     rcx, [rbp+50h+var_90.poleobj]
0x18007cdb6  test    rcx, rcx
0x18007cdb9  jz      short loc_18007CDC7
0x18007cdbb  mov     rax, [rcx]
0x18007cdbe  mov     rax, [rax+10h]
0x18007cdc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cdc7  mov     rcx, [rsp+150h+var_E8]
0x18007cdcc  test    rcx, rcx
0x18007cdcf  jz      short loc_18007CDDD
0x18007cdd1  mov     rax, [rcx]
0x18007cdd4  mov     rax, [rax+10h]
0x18007cdd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cddd  mov     rbx, [rsp+150h+var_F8]
0x18007cde2  test    rbx, rbx
0x18007cde5  jz      short loc_18007CE01
0x18007cde7  mov     rax, [rbx]
0x18007cdea  mov     rcx, rbx
0x18007cded  mov     rax, [rax+10h]
0x18007cdf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cdf6  mov     rcx, r15; lpMem
0x18007cdf9  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x18007cdfe  mov     r15, r13
0x18007ce01  test    edi, edi
0x18007ce03  jnz     short loc_18007CE0B
0x18007ce05  cmp     [rsi+30h], r13d
0x18007ce09  jz      short loc_18007CE25
0x18007ce0b  test    r15, r15
0x18007ce0e  jz      short loc_18007CE1B
0x18007ce10  mov     rcx, [rsp+150h+hMem]; hMem
0x18007ce15  call    cs:__imp_GlobalUnlock
0x18007ce1b  mov     rcx, [rsp+150h+hMem]; void *
0x18007ce20  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18007ce25  mov     rcx, [rsp+150h+ho+8]; hMem
0x18007ce2a  test    rcx, rcx
0x18007ce2d  jz      loc_18007D329
0x18007ce33  mov     rax, [rsi+278h]
0x18007ce3a  movsx   edx, word ptr [rax]
0x18007ce3d  test    edx, edx
0x18007ce3f  jz      loc_18007D31E
0x18007ce45  cmp     edx, 1
0x18007ce48  jnz     loc_18007D329
0x18007ce4e  call    cs:__imp_GlobalUnlock
0x18007ce54  mov     rcx, [rsp+150h+ho+8]; void *
0x18007ce59  call    ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
0x18007ce5e  jmp     loc_18007D329
0x18007ce63  xor     r13d, r13d
0x18007ce66  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18007ce6b  lea     rbx, [rax+110h]
0x18007ce72  cmp     [rbx], r13
0x18007ce75  jnz     short loc_18007CE8B
0x18007ce77  lea     r8, aCreatestreamon; "CreateStreamOnHGlobal"
0x18007ce7e  mov     edx, 1
0x18007ce83  mov     rcx, rbx
0x18007ce86  call    SetProcAddr
0x18007ce8b  mov     rax, [rbx]
0x18007ce8e  test    rax, rax
0x18007ce91  jz      short loc_18007CED6
0x18007ce93  lea     r8, [rsp+150h+var_F8]
0x18007ce98  xor     edx, edx
0x18007ce9a  xor     ecx, ecx
0x18007ce9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cea1  mov     edi, eax
0x18007cea3  test    eax, eax
0x18007cea5  jnz     short loc_18007CEDB
0x18007cea7  mov     ebx, 400h
0x18007ceac  mov     r14d, 4000h
0x18007ceb2  xor     edx, edx; unsigned int
0x18007ceb4  mov     ecx, r14d; unsigned int
0x18007ceb7  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18007cebc  mov     r15, rax
0x18007cebf  test    rax, rax
0x18007cec2  jnz     short loc_18007CF18
0x18007cec4  sub     r14d, ebx
0x18007cec7  cmp     r14d, ebx
0x18007ceca  jge     short loc_18007CEB2
0x18007cecc  mov     r12d, [rsp+150h+var_110]
0x18007ced1  jmp     loc_18007CD6F
0x18007ced6  mov     edi, 80004005h
0x18007cedb  mov     r12d, r15d
0x18007cede  jmp     loc_18007CD6F
0x18007cee3  test    r14d, r14d
0x18007cee6  jnz     short loc_18007CEF3
0x18007cee8  mov     r12d, 1
0x18007ceee  jmp     loc_18007CD6F
0x18007cef3  mov     rdx, r14; dwBytes
0x18007cef6  xor     ecx, ecx; uFlags
0x18007cef8  call    cs:__imp_GlobalAlloc
0x18007cefe  mov     rcx, rax; hMem
0x18007cf01  mov     [rsp+150h+hMem], rax
0x18007cf06  call    cs:__imp_GlobalLock
0x18007cf0c  mov     r15, rax
0x18007cf0f  test    rax, rax
0x18007cf12  jz      loc_18007CD6C
0x18007cf18  lea     r13, [rsi+280h]
0x18007cf1f  lea     rbx, [rsi+30h]
0x18007cf23  mov     rax, [r13+0]
0x18007cf27  mov     r8d, r14d
0x18007cf2a  mov     rdx, r15
0x18007cf2d  mov     rcx, r13
0x18007cf30  mov     rax, [rax]
0x18007cf33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cf38  mov     r8d, eax
0x18007cf3b  test    eax, eax
0x18007cf3d  jle     short loc_18007CF72
0x18007cf3f  lea     rbx, [rsi+30h]
0x18007cf43  cmp     dword ptr [rbx], 0
0x18007cf46  jnz     short loc_18007CF72
0x18007cf48  mov     rcx, [rsp+150h+var_F8]
0x18007cf4d  test    rcx, rcx
0x18007cf50  jz      short loc_18007CF23
0x18007cf52  mov     rax, [rcx]
0x18007cf55  xor     r9d, r9d
0x18007cf58  mov     rdx, r15
0x18007cf5b  mov     rax, [rax+20h]
0x18007cf5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cf64  mov     edi, eax
0x18007cf66  test    eax, eax
0x18007cf68  jz      short loc_18007CF23
0x18007cf6a  xor     r13d, r13d
0x18007cf6d  jmp     loc_18007CECC
0x18007cf72  xor     r13d, r13d
0x18007cf75  cmp     [rbx], r13d
0x18007cf78  jnz     loc_18007CD6C
0x18007cf7e  mov     rcx, [rsp+150h+hMem]; hMem
0x18007cf83  test    rcx, rcx
0x18007cf86  jz      short loc_18007CF91
0x18007cf88  call    cs:__imp_GlobalUnlock
0x18007cf8e  mov     r15d, r13d
0x18007cf91  mov     rbx, [rsp+150h+var_F8]
0x18007cf96  test    rbx, rbx
0x18007cf99  jz      short loc_18007CFE3
0x18007cf9b  call    ?GetOle32Procs@CThreadData@@SAPEAVCOLE32_PROC@@XZ; CThreadData::GetOle32Procs(void)
0x18007cfa0  lea     rdi, [rax+118h]
0x18007cfa7  cmp     [rdi], r13
0x18007cfaa  jnz     short loc_18007CFC0
0x18007cfac  lea     r8, aGethglobalfrom; "GetHGlobalFromStream"
0x18007cfb3  mov     edx, 1
0x18007cfb8  mov     rcx, rdi
0x18007cfbb  call    SetProcAddr
0x18007cfc0  mov     rax, [rdi]
0x18007cfc3  test    rax, rax
0x18007cfc6  jz      loc_18007D0C3
0x18007cfcc  lea     rdx, [rsp+150h+hMem]
0x18007cfd1  mov     rcx, rbx
0x18007cfd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cfd9  mov     edi, eax
0x18007cfdb  test    eax, eax
0x18007cfdd  jnz     loc_18007CD6C
0x18007cfe3  test    r12, r12
0x18007cfe6  jz      loc_18007CEE8
0x18007cfec  mov     rcx, [rsi+278h]
0x18007cff3  lea     rdx, [rsp+150h+hMem]
0x18007cff8  mov     rax, r12
0x18007cffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d000  mov     [rsp+150h+ho+8], rax
0x18007d005  cmp     [rbp+50h+var_A8], r13
0x18007d009  jz      loc_18007D1AB
0x18007d00f  test    rax, rax
0x18007d012  jz      loc_18007CD6C
0x18007d018  test    byte ptr [rsi+1D8h], 4
  ... truncated ...
```
