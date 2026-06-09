# AVISaveVW

- ea: `0x180001fe0`
- end: `0x180002cf7`
- name: `AVISaveVW`
- size: `3351`
- prototype: `HRESULT __stdcall(LPCWSTR szFile, CLSID *pclsidHandler, AVISAVECALLBACK lpfnCallback, int nStreams, PAVISTREAM *ppavi, LPAVICOMPRESSOPTIONS *plpOptions)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001f40`
- `0x180002d00`

## callees

- `0x180001460`
- `0x180001d0c`
- `0x180001fe0`
- `0x180002eb4`
- `0x180002f68`
- `0x180007af0`
- `0x180007c00`
- `0x180007e50`
- `0x180008300`
- `0x180008350`
- `0x1800086a0`
- `0x180008710`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180002760`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x1800029b3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180002b50`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180002760`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x1800029b3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180002b50`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002745`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002998`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002b35`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002c53`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002745`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002998`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002b35`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002c53`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002298`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002769`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800029bc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002b59`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002298`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002769`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1800029bc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180002b59`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000273c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000274e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000298f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800029a1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002b2c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002b3e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002c4a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002c5c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000273c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000274e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000298f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x1800029a1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002b2c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002b3e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002c4a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002c5c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000228f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18000228f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180002c65`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180002c65`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800022ed`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000284f`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000289a`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180002a3e`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180002a50`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180002bef`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180002c01`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1800022ed`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000284f`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x18000289a`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180002a3e`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180002a50`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180002bef`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180002c01`

## pseudocode

```c
HRESULT __stdcall AVISaveVW(
        LPCWSTR szFile,
        CLSID *pclsidHandler,
        AVISAVECALLBACK lpfnCallback,
        int nStreams,
        PAVISTREAM *ppavi,
        LPAVICOMPRESSOPTIONS *plpOptions)
{
  __int64 v8; // r14
  HRESULT v10; // edi
  DWORD dwInterleaveEvery; // r12d
  int v12; // r15d
  __int64 v13; // rbx
  __int64 v14; // rsi
  LPAVICOMPRESSOPTIONS v15; // rax
  PAVISTREAM *v16; // rbx
  LPAVICOMPRESSOPTIONS v17; // rax
  PAVISTREAM v18; // rcx
  LONG v19; // eax
  __int64 v20; // rdx
  IAVIStream *v21; // rcx
  AVISAVECALLBACK v22; // rcx
  unsigned int v23; // r12d
  HGLOBAL v24; // rax
  const void *v25; // rsi
  unsigned int v26; // eax
  int v27; // r15d
  DWORD v28; // ebx
  IAVIStream *v29; // rcx
  unsigned int v30; // eax
  PAVIFILE v31; // rcx
  PAVISTREAM *v32; // rdx
  PAVISTREAM v33; // rcx
  PAVISTREAM v34; // rcx
  DWORD dwInitialFrames; // eax
  PAVISTREAM v36; // rbx
  unsigned int v37; // eax
  unsigned int v38; // eax
  DWORD v39; // eax
  int v40; // r13d
  int v41; // r15d
  __int64 v42; // rax
  __int64 v43; // r13
  PAVISTREAM *v44; // r13
  DWORD v45; // ecx
  int v46; // r15d
  unsigned int v47; // eax
  LONG v48; // ebx
  LONG v49; // r15d
  unsigned int v50; // ebx
  PAVISTREAM v51; // rcx
  unsigned int v52; // edx
  PAVISTREAM v53; // rcx
  HRESULT v54; // eax
  HGLOBAL v55; // rax
  HGLOBAL v56; // rax
  HGLOBAL v57; // rax
  int v58; // eax
  int v59; // r10d
  unsigned int v60; // eax
  int v61; // r15d
  unsigned int v62; // eax
  __int64 v63; // r13
  DWORD dwStart; // r15d
  PAVISTREAM v65; // rcx
  PAVISTREAM v66; // rcx
  __int64 v67; // r8
  HRESULT v68; // eax
  HGLOBAL v69; // rax
  HGLOBAL v70; // rax
  HGLOBAL v71; // rax
  int v72; // ebx
  int v73; // eax
  PAVISTREAM v74; // rcx
  PAVISTREAM v75; // rcx
  int v76; // edi
  HGLOBAL v77; // rax
  HGLOBAL v78; // rax
  HGLOBAL v79; // rax
  int v80; // eax
  int v81; // r10d
  int v82; // ebx
  int v83; // eax
  HGLOBAL v84; // rax
  HGLOBAL v85; // rax
  PAVIFILE v86; // rcx
  __int64 v87; // rbx
  PAVISTREAM v88; // rcx
  __int64 j; // rbx
  PAVISTREAM v90; // rcx
  __int64 v91; // [rsp+28h] [rbp-D8h]
  __int64 v92; // [rsp+28h] [rbp-D8h]
  __int64 v93; // [rsp+28h] [rbp-D8h]
  int nNumber; // [rsp+50h] [rbp-B0h]
  int nNumbera; // [rsp+50h] [rbp-B0h]
  DWORD v96; // [rsp+54h] [rbp-ACh]
  unsigned int v97; // [rsp+58h] [rbp-A8h]
  DWORD dwLength; // [rsp+5Ch] [rbp-A4h]
  int v99; // [rsp+60h] [rbp-A0h]
  LONG v100; // [rsp+60h] [rbp-A0h]
  DWORD v101; // [rsp+64h] [rbp-9Ch]
  DWORD dwKeyFrameEvery; // [rsp+68h] [rbp-98h]
  unsigned int v103; // [rsp+68h] [rbp-98h]
  unsigned int (__fastcall *v104)(_QWORD); // [rsp+70h] [rbp-90h]
  unsigned int i; // [rsp+80h] [rbp-80h]
  PAVIFILE ppfile; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v108; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v109; // [rsp+94h] [rbp-6Ch] BYREF
  unsigned int v110; // [rsp+98h] [rbp-68h] BYREF
  struct _AVISTREAMINFOW psi; // [rsp+A0h] [rbp-60h] BYREF
  struct _AVIFILEINFOW pfi; // [rsp+170h] [rbp+70h] BYREF
  PAVISTREAM pavi[64]; // [rsp+220h] [rbp+120h] BYREF
  PAVISTREAM v114[96]; // [rsp+420h] [rbp+320h] BYREF

  ppfile = 0;
  v8 = nStreams;
  memset_0(&psi, 0, sizeof(psi));
  memset_0(&pfi, 0, sizeof(pfi));
  v108 = 0;
  v109 = 0;
  v110 = 0;
  memset_0(pavi, 0, sizeof(pavi));
  memset_0(v114, 0, 0x200u);
  if ( (int)v8 > 64 )
    return -2147205016;
  if ( (int)v8 > 0 )
  {
    memset_0(pavi, 0, 8 * v8);
    memset_0(v114, 0, 8 * v8);
  }
  v10 = AVIFileOpenW(&ppfile, szFile, 0x1011u, pclsidHandler);
  if ( !v10 )
  {
    dwInterleaveEvery = 0;
    v96 = 0;
    v12 = -1;
    AVIFileInfoW(ppfile, &pfi, 172);
    v13 = 0;
    v99 = 0;
    if ( (int)v8 <= 0 )
      goto LABEL_29;
    do
    {
      v14 = (unsigned int)v13;
      v10 = AVIStreamInfoW(ppavi[v13], &psi, 204);
      if ( v10 )
        goto LABEL_137;
      if ( psi.fccType == 1935960438 )
      {
        if ( v12 < 0 )
          v12 = v13;
      }
      else if ( !dwInterleaveEvery )
      {
        if ( plpOptions )
        {
          v15 = plpOptions[v13];
          if ( v15 )
          {
            if ( (v15->dwFlags & 1) != 0 )
              dwInterleaveEvery = v15->dwInterleaveEvery;
          }
        }
      }
      v16 = &pavi[(unsigned int)v13];
      pavi[v14] = 0;
      if ( plpOptions )
      {
        v17 = plpOptions[v14];
        if ( v17 )
        {
          if ( v17->fccHandler || v17->lpFormat )
          {
            dwKeyFrameEvery = v17->dwKeyFrameEvery;
            if ( (pfi.dwCaps & 0x10) != 0 )
              v17->dwKeyFrameEvery = 1;
            v10 = AVIMakeCompressedStream(&pavi[v14], ppavi[v14], plpOptions[v14], 0);
            plpOptions[v14]->dwKeyFrameEvery = dwKeyFrameEvery;
            if ( v10 )
              goto LABEL_34;
            v10 = AVIStreamInfoW(*v16, &psi, 204);
            if ( v10 )
            {
              ((void (__fastcall *)(PAVISTREAM))(*v16)->lpVtbl->Release)(*v16);
LABEL_34:
              *v16 = 0;
              goto LABEL_137;
            }
          }
        }
      }
      if ( !*v16 )
      {
        v18 = ppavi[v14];
        *v16 = v18;
        ((void (__fastcall *)(PAVISTREAM))v18->lpVtbl->AddRef)(v18);
      }
      v19 = AVIStreamStart(*v16);
      v13 = (unsigned int)(v99 + 1);
      *((_DWORD *)&v114[64] + v14) = v19;
      v99 = v13;
    }
    while ( (int)v13 < (int)v8 );
    v96 = dwInterleaveEvery;
    if ( v12 > 0 )
    {
      v20 = v12;
      v12 = 0;
      v21 = pavi[v20];
      pavi[v20] = pavi[0];
      pavi[0] = v21;
    }
LABEL_29:
    v22 = (AVISAVECALLBACK)CAVIFile::CPersistFileImpl::GetClassID;
    v23 = 0x8000;
    if ( lpfnCallback )
      v22 = lpfnCallback;
    v104 = (unsigned int (__fastcall *)(_QWORD))v22;
    v24 = GlobalAlloc(2u, 0x8000u);
    v25 = GlobalLock(v24);
    if ( !v25 )
    {
LABEL_32:
      v10 = -2147205017;
      goto LABEL_137;
    }
    AVIStreamInfoW(pavi[0], &psi, 204);
    MulDiv(1000000, psi.dwScale, psi.dwRate);
    dwLength = psi.dwLength;
    v101 = 0;
    if ( v12 < 0 )
    {
      v100 = AVIStreamTimeToSample(pavi[0], 500);
      goto LABEL_41;
    }
    _mm_lfence();
    v108 = 0x8000;
    v26 = AVIStreamStart(pavi[v12]);
    v10 = ((__int64 (__fastcall *)(PAVISTREAM, _QWORD, const void *, unsigned int *))pavi[v12]->lpVtbl->ReadFormat)(
            pavi[v12],
            v26,
            v25,
            &v108);
    if ( (unsigned __int64)(int)v108 < 0x28 )
    {
      v10 = -2147205016;
      goto LABEL_136;
    }
    if ( v10 )
      goto LABEL_136;
    v100 = 1;
LABEL_41:
    v27 = 0;
    if ( (int)v8 <= 0 )
      goto LABEL_136;
    v28 = v96;
    do
    {
      AVIStreamInfoW(pavi[v27], &psi, 204);
      psi.dwInitialFrames = 0;
      if ( v28 && v27 > 0 && psi.fccType != 1935960438 )
        psi.dwInitialFrames = AVIStreamTimeToSample(pavi[0], 750);
      v29 = pavi[v27];
      v108 = 0x8000;
      v30 = AVIStreamStart(v29);
      v10 = ((__int64 (__fastcall *)(PAVISTREAM, _QWORD, const void *, unsigned int *))pavi[v27]->lpVtbl->ReadFormat)(
              pavi[v27],
              v30,
              v25,
              &v108);
      if ( v10 )
        goto LABEL_136;
      v31 = ppfile;
      v32 = &v114[v27];
      *v32 = 0;
      v10 = ((__int64 (__fastcall *)(PAVIFILE, PAVISTREAM *, struct _AVISTREAMINFOW *))v31->lpVtbl->CreateStream)(
              v31,
              v32,
              &psi);
      if ( v10 || (v33 = v114[v27]) == 0 )
      {
        ((void (__fastcall *)(PAVISTREAM))pavi[v27]->lpVtbl->Release)(pavi[v27]);
        if ( v27 + 1 < (int)v8 )
          pavi[v27] = pavi[v27 + 1];
        v40 = dwLength;
        LODWORD(v8) = v8 - 1;
        --v27;
      }
      else
      {
        v10 = ((__int64 (__fastcall *)(PAVISTREAM, _QWORD, const void *, _QWORD))v33->lpVtbl->SetFormat)(
                v33,
                0,
                v25,
                v108);
        if ( v10 )
          goto LABEL_136;
        v34 = pavi[v27];
        v108 = 0x8000;
        v10 = ((__int64 (__fastcall *)(PAVISTREAM, __int64, const void *, unsigned int *))v34->lpVtbl->ReadData)(
                v34,
                1685222515,
                v25,
                &v108);
        if ( !v10 )
        {
          if ( v108 )
          {
            v10 = ((__int64 (__fastcall *)(PAVISTREAM, __int64, const void *))v114[v27]->lpVtbl->WriteData)(
                    v114[v27],
                    1685222515,
                    v25);
            if ( v10 )
              goto LABEL_136;
          }
        }
        dwInitialFrames = v101;
        v36 = pavi[v27];
        if ( psi.dwInitialFrames > v101 )
          dwInitialFrames = psi.dwInitialFrames;
        v101 = dwInitialFrames;
        v37 = AVIStreamLength(pavi[v27]);
        v38 = AVIStreamSampleToTimeNoClip(v36, v37);
        v39 = AVIStreamTimeToSampleNoClip(pavi[0], v38);
        v40 = dwLength;
        v28 = v96;
        v110 = v39;
        if ( v39 > dwLength )
        {
          v40 = v39;
          dwLength = v39;
        }
      }
      ++v27;
    }
    while ( v27 < (int)v8 );
    if ( (int)v8 <= 0 )
      goto LABEL_136;
    if ( v28 )
    {
      if ( v28 == 1 )
        ((void (__fastcall *)(PAVIFILE))ppfile->lpVtbl->EndRecord)(ppfile);
      v41 = -v101;
      nNumber = -v101;
      if ( (signed int)-v101 < v40 )
      {
LABEL_67:
        v42 = 0;
        v97 = 0;
        while ( 1 )
        {
          v43 = (unsigned int)v42;
          v10 = AVIStreamInfoW(v114[v42], &psi, 204);
          if ( v10 )
            goto LABEL_135;
          if ( v41 >= (signed int)-psi.dwInitialFrames )
            break;
LABEL_95:
          v42 = v97 + 1;
          v97 = v42;
          if ( (int)v42 >= (int)v8 )
          {
            if ( v28 != 1 || (v10 = ((__int64 (__fastcall *)(PAVIFILE))ppfile->lpVtbl->EndRecord)(ppfile)) == 0 )
            {
              v60 = MulDiv(v101 + v41, 100, v101 + dwLength);
              if ( v104(v60) )
                goto LABEL_134;
              v41 += v100;
              nNumber = v41;
              v96 = v28;
              if ( v41 < (int)dwLength )
                goto LABEL_67;
            }
            goto LABEL_135;
          }
        }
        if ( v41 >= (int)(dwLength - v100) )
        {
          v44 = &pavi[v43];
          goto LABEL_80;
        }
        v45 = v41 + psi.dwInitialFrames;
        v46 = v41 + psi.dwInitialFrames + v100;
        if ( psi.fccType == 1935960438 )
        {
          if ( !v97 )
            goto LABEL_78;
LABEL_77:
          v47 = AVIStreamSampleToTimeNoClip(pavi[0], (unsigned int)v46);
          v44 = &pavi[v43];
          v46 = AVIStreamTimeToSampleNoClip(*v44, v47);
        }
        else
        {
          if ( v97 )
          {
            if ( !(v45 % v28) )
            {
              v46 = v45 + v28;
              goto LABEL_77;
            }
LABEL_94:
            v41 = nNumber;
            goto LABEL_95;
          }
LABEL_78:
          v44 = &pavi[v43];
        }
        v48 = AVIStreamLength(*v44);
        if ( v46 >= v48 + AVIStreamStart(*v44) )
        {
LABEL_80:
          v49 = AVIStreamLength(*v44);
          v46 = AVIStreamStart(*v44) + v49;
        }
        v50 = *((_DWORD *)&v114[64] + v97);
        *((_DWORD *)&v114[64] + v97) = v46;
        while ( 1 )
        {
          v103 = v50;
          if ( v46 <= (int)v50 )
            break;
          v51 = *v44;
          v108 = v23;
          v10 = ((__int64 (__fastcall *)(PAVISTREAM, _QWORD, const void *, unsigned int *))v51->lpVtbl->ReadFormat)(
                  v51,
                  v50,
                  v25,
                  &v108);
          if ( v10 )
            goto LABEL_135;
          ((void (__fastcall *)(PAVISTREAM, _QWORD, const void *, _QWORD))v114[v97]->lpVtbl->SetFormat)(
            v114[v97],
            v50,
            v25,
            v108);
          v52 = v46 - v50;
          for ( i = v46 - v50; ; v52 = i )
          {
            v53 = *v44;
            v108 = v23;
            v109 = 0;
            v54 = ((__int64 (__fastcall *)(PAVISTREAM, _QWORD, _QWORD, const void *, unsigned int, unsigned int *, unsigned int *))v53->lpVtbl->Read)(
                    v53,
                    v50,
                    v52,
                    v25,
                    v23,
                    &v110,
                    &v109);
            v10 = v54;
            if ( v54 != -2147205004 )
              break;
            v23 *= 2;
            v55 = GlobalHandle(v25);
            GlobalUnlock(v55);
            v56 = GlobalHandle(v25);
            v57 = GlobalReAlloc(v56, v23, 2u);
            v25 = GlobalLock(v57);
            if ( !v25 )
              goto LABEL_32;
            v50 = v103;
          }
          if ( v54 )
            goto LABEL_135;
          v58 = ((__int64 (__fastcall *)(PAVISTREAM, _QWORD, __int64))(*v44)->lpVtbl->FindSample)(*v44, v50, 20);
          v59 = 16;
          if ( v58 != v50 )
            v59 = 0;
          LODWORD(v91) = v59;
          v10 = ((__int64 (__fastcall *)(PAVISTREAM, __int64, _QWORD, const void *, unsigned int, __int64, _QWORD, _QWORD))v114[v97]->lpVtbl->Write)(
                  v114[v97],
                  0xFFFFFFFFLL,
                  v109,
                  v25,
                  v110,
                  v91,
                  0,
                  0);
          if ( v10 )
            goto LABEL_135;
          v50 += v109;
        }
        v28 = v96;
        goto LABEL_94;
      }
      goto LABEL_136;
    }
    v61 = 0;
    nNumbera = 0;
    while ( 1 )
    {
      v62 = MulDiv(v61, 100, v8);
      if ( v104(v62) )
        break;
      v63 = v61;
      AVIStreamInfoW(pavi[v61], &psi, 204);
      dwStart = psi.dwStart;
      if ( psi.dwSampleSize )
      {
        while ( (int)dwStart < (int)psi.dwLength )
        {
          v65 = pavi[v63];
          v108 = v23;
          v10 = ((__int64 (__fastcall *)(PAVISTREAM, _QWORD, const void *, unsigned int *))v65->lpVtbl->ReadFormat)(
                  v65,
                  dwStart,
                  v25,
                  &v108);
          if ( v10 )
            goto LABEL_135;
          ((void (__fastcall *)(PAVISTREAM, _QWORD, const void *, _QWORD))v114[v63]->lpVtbl->SetFormat)(
            v114[v63],
            dwStart,
            v25,
            v108);
          while ( 1 )
          {
            v66 = pavi[v63];
            v110 = v23;
            v109 = 0;
            v67 = v23 / psi.dwSampleSize;
            if ( (unsigned int)v67 >= psi.dwLength - dwStart )
              v67 = psi.dwLength - dwStart;
            v68 = ((__int64 (__fastcall *)(PAVISTREAM, _QWORD, __int64, const void *, unsigned int, unsigned int *, unsigned int *))v66->lpVtbl->Read)(
                    v66,
                    dwStart,
                    v67,
                    v25,
                    v23,
                    &v110,
                    &v109);
            v10 = v68;
            if ( v68 != -2147205004 )
              break;
            v23 *= 2;
            v69 = GlobalHandle(v25);
            GlobalUnlock(v69);
            v70 = GlobalHandle(v25);
            v71 = GlobalReAlloc(v70, v23, 2u);
            v25 = GlobalLock(v71);
            if ( !v25 )
              goto LABEL_137;
          }
          if ( v68 )
            goto LABEL_135;
          if ( !v109 )
          {
            if ( dwStart + 1 == psi.dwLength )
              break;
            goto LABEL_119;
          }
          dwStart += v109;
          LODWORD(v92) = 0;
          v10 = ((__int64 (__fastcall *)(PAVISTREAM, __int64, _QWORD, const void *, unsigned int, __int64, _QWORD, _QWORD))v114[v63]->lpVtbl->Write)(
                  v114[v63],
                  0xFFFFFFFFLL,
                  v109,
                  v25,
                  v110,
                  v92,
                  0,
                  0);
          if ( v10 )
            goto LABEL_135;
          v72 = MulDiv(dwStart, 100, psi.dwLength * v8);
          v73 = MulDiv(nNumbera, 100, v8);
          if ( v104((unsigned int)(v73 + v72)) )
            goto LABEL_134;
        }
      }
      else
      {
        while ( (int)dwStart < (int)psi.dwLength )
        {
          v74 = pavi[v63];
          v108 = v23;
          v10 = ((__int64 (__fastcall *)(PAVISTREAM, _QWORD, const void *, unsigned int *))v74->lpVtbl->ReadFormat)(
                  v74,
                  dwStart,
                  v25,
                  &v108);
          if ( v10 )
            goto LABEL_135;
          ((void (__fastcall *)(PAVISTREAM, _QWORD, const void *, _QWORD))v114[v63]->lpVtbl->SetFormat)(
            v114[v63],
            dwStart,
            v25,
            v108);
          do
          {
            v75 = pavi[v63];
            v110 = v23;
            v109 = 0;
            v76 = ((__int64 (__fastcall *)(PAVISTREAM, _QWORD, __int64, const void *, unsigned int, unsigned int *, unsigned int *))v75->lpVtbl->Read)(
                    v75,
                    dwStart,
                    1,
                    v25,
                    v23,
                    &v110,
                    &v109);
            if ( v76 != -2147205004 )
              break;
            v23 *= 2;
            v77 = GlobalHandle(v25);
            GlobalUnlock(v77);
            v78 = GlobalHandle(v25);
            v79 = GlobalReAlloc(v78, v23, 2u);
            v25 = GlobalLock(v79);
          }
          while ( v25 );
          if ( v109 != 1 || v76 )
          {
LABEL_119:
            v10 = -2147205011;
            goto LABEL_135;
          }
          v80 = ((__int64 (__fastcall *)(PAVISTREAM, _QWORD, __int64))pavi[v63]->lpVtbl->FindSample)(
                  pavi[v63],
                  dwStart,
                  20);
          v81 = 16;
          if ( v80 != dwStart )
            v81 = 0;
          LODWORD(v93) = v81;
          v10 = ((__int64 (__fastcall *)(PAVISTREAM, __int64, _QWORD, const void *, unsigned int, __int64, _QWORD, _QWORD))v114[v63]->lpVtbl->Write)(
                  v114[v63],
                  0xFFFFFFFFLL,
                  v109,
                  v25,
                  v110,
                  v93,
                  0,
                  0);
          if ( v10 )
            goto LABEL_135;
          v82 = MulDiv(dwStart, 100, psi.dwLength * v8);
          v83 = MulDiv(nNumbera, 100, v8);
          if ( v104((unsigned int)(v83 + v82)) )
            goto LABEL_134;
          ++dwStart;
        }
      }
      v61 = nNumbera + 1;
      nNumbera = v61;
      if ( v61 >= (int)v8 )
        goto LABEL_135;
    }
LABEL_134:
    v10 = -2147204922;
LABEL_135:
    if ( v25 )
    {
LABEL_136:
      v84 = GlobalHandle(v25);
      GlobalUnlock(v84);
      v85 = GlobalHandle(v25);
      GlobalFree(v85);
    }
  }
LABEL_137:
  v86 = ppfile;
  if ( ppfile )
  {
    v87 = 0;
    if ( (int)v8 > 0 )
    {
      do
      {
        v88 = v114[v87];
        if ( v88 )
          ((void (__fastcall *)(PAVISTREAM))v88->lpVtbl->Release)(v88);
        v87 = (unsigned int)(v87 + 1);
      }
      while ( (int)v87 < (int)v8 );
      v86 = ppfile;
    }
    ((void (__fastcall *)(PAVIFILE))v86->lpVtbl->Release)(v86);
  }
  for ( j = 0; (int)j < (int)v8; j = (unsigned int)(j + 1) )
  {
    v90 = pavi[j];
    if ( v90 )
      ((void (__fastcall *)(PAVISTREAM))v90->lpVtbl->Release)(v90);
  }
  return v10;
}

```

## disassembly

```asm
0x180001fe0  push    rbp
0x180001fe2  push    rbx
0x180001fe3  push    rsi
0x180001fe4  push    rdi
0x180001fe5  push    r12
0x180001fe7  push    r13
0x180001fe9  push    r14
0x180001feb  push    r15
0x180001fed  lea     rbp, [rsp-638h]
0x180001ff5  sub     rsp, 738h
0x180001ffc  mov     rax, cs:__security_cookie
0x180002003  xor     rax, rsp
0x180002006  mov     [rbp+670h+var_50], rax
0x18000200d  mov     rax, [rbp+670h+ppavi]
0x180002014  mov     rsi, rdx
0x180002017  mov     r13, [rbp+670h+plpOptions]
0x18000201e  mov     rdi, rcx
0x180002021  mov     [rsp+770h+var_6F8], r8
0x180002026  lea     rcx, [rbp+670h+psi]; void *
0x18000202a  xor     ebx, ebx
0x18000202c  mov     [rsp+770h+var_700], rax
0x180002031  xor     edx, edx; Val
0x180002033  mov     [rbp+670h+ppfile], rbx
0x180002037  mov     r8d, 0CCh; Size
0x18000203d  movsxd  r14, r9d
0x180002040  call    memset_0
0x180002045  xor     edx, edx; Val
0x180002047  lea     rcx, [rbp+670h+pfi]; void *
0x18000204b  mov     r8d, 0ACh; Size
0x180002051  call    memset_0
0x180002056  mov     [rbp+670h+var_6E0], ebx
0x180002059  lea     rcx, [rbp+670h+pavi]; void *
0x180002060  mov     [rbp+670h+var_6DC], ebx
0x180002063  xor     edx, edx; Val
0x180002065  mov     [rbp+670h+var_6D8], ebx
0x180002068  mov     ebx, 200h
0x18000206d  mov     r8d, ebx; Size
0x180002070  call    memset_0
0x180002075  mov     r8d, ebx; Size
0x180002078  lea     rcx, [rbp+670h+var_350]; void *
0x18000207f  xor     edx, edx; Val
0x180002081  call    memset_0
0x180002086  cmp     r14d, 40h ; '@'
0x18000208a  jle     short loc_180002096
0x18000208c  mov     eax, 80044068h
0x180002091  jmp     loc_180002CD4
0x180002096  test    r14d, r14d
0x180002099  jle     short loc_1800020CC
0x18000209b  mov     rbx, r14
0x18000209e  lea     rcx, [rbp+670h+pavi]; void *
0x1800020a5  shl     rbx, 3
0x1800020a9  xor     edx, edx; Val
0x1800020ab  mov     r8, rbx
0x1800020ae  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x1800020b2  call    memset_0
0x1800020b7  and     rbx, 0FFFFFFFFFFFFFFF8h
0x1800020bb  lea     rcx, [rbp+670h+var_350]; void *
0x1800020c2  mov     r8, rbx; Size
0x1800020c5  xor     edx, edx; Val
0x1800020c7  call    memset_0
0x1800020cc  mov     r9, rsi; lpHandler
0x1800020cf  lea     rcx, [rbp+670h+ppfile]; ppfile
0x1800020d3  mov     r8d, 1011h; uMode
0x1800020d9  mov     rdx, rdi; szFile
0x1800020dc  call    AVIFileOpenW
0x1800020e1  mov     edi, eax
0x1800020e3  test    eax, eax
0x1800020e5  jnz     loc_180002C6B
0x1800020eb  mov     rcx, [rbp+670h+ppfile]; pfile
0x1800020ef  lea     rdx, [rbp+670h+pfi]; pfi
0x1800020f3  xor     r12d, r12d
0x1800020f6  mov     r8d, 0ACh; lSize
0x1800020fc  mov     [rsp+770h+var_71C], r12d
0x180002101  or      r15d, 0FFFFFFFFh
0x180002105  call    AVIFileInfoW
0x18000210a  xor     ebx, ebx
0x18000210c  mov     [rsp+770h+var_710], ebx
0x180002110  test    r14d, r14d
0x180002113  jle     loc_180002269
0x180002119  mov     rax, [rsp+770h+var_700]
0x18000211e  lea     rdx, [rbp+670h+psi]; psi
0x180002122  mov     r8d, 0CCh; lSize
0x180002128  mov     esi, ebx
0x18000212a  mov     rcx, [rax+rbx*8]; pavi
0x18000212e  call    AVIStreamInfoW
0x180002133  mov     edi, eax
0x180002135  test    eax, eax
0x180002137  jnz     loc_180002C6B
0x18000213d  cmp     [rbp+670h+psi.fccType], 73646976h
0x180002144  jnz     short loc_180002150
0x180002146  test    r15d, r15d
0x180002149  jns     short loc_18000216E
0x18000214b  mov     r15d, ebx
0x18000214e  jmp     short loc_18000216E
0x180002150  test    r12d, r12d
0x180002153  jnz     short loc_18000216E
0x180002155  test    r13, r13
0x180002158  jz      short loc_18000216E
0x18000215a  mov     rax, [r13+rbx*8+0]
0x18000215f  test    rax, rax
0x180002162  jz      short loc_18000216E
0x180002164  test    byte ptr [rax+14h], 1
0x180002168  jz      short loc_18000216E
0x18000216a  mov     r12d, [rax+34h]
0x18000216e  lea     rbx, [rbp+670h+pavi]
0x180002175  lea     rbx, [rbx+rsi*8]
0x180002179  mov     qword ptr [rbx], 0
0x180002180  test    r13, r13
0x180002183  jz      short loc_1800021FB
0x180002185  mov     rax, [r13+rsi*8+0]
0x18000218a  test    rax, rax
0x18000218d  jz      short loc_1800021FB
0x18000218f  cmp     dword ptr [rax+4], 0
0x180002193  jnz     short loc_18000219C
0x180002195  cmp     qword ptr [rax+18h], 0
0x18000219a  jz      short loc_1800021FB
0x18000219c  test    byte ptr [rbp+670h+pfi.dwCaps], 10h
0x1800021a0  mov     ecx, [rax+8]
0x1800021a3  mov     [rsp+770h+var_708], ecx
0x1800021a7  jz      short loc_1800021B0
0x1800021a9  mov     dword ptr [rax+8], 1
0x1800021b0  mov     rax, [rsp+770h+var_700]
0x1800021b5  xor     r9d, r9d; pclsidHandler
0x1800021b8  mov     r8, [r13+rsi*8+0]; lpOptions
0x1800021bd  mov     rcx, rbx; ppsCompressed
0x1800021c0  mov     rdx, [rax+rsi*8]; ppsSource
0x1800021c4  call    AVIMakeCompressedStream
0x1800021c9  mov     ecx, [rsp+770h+var_708]
0x1800021cd  mov     edi, eax
0x1800021cf  mov     rax, [r13+rsi*8+0]
0x1800021d4  mov     [rax+8], ecx
0x1800021d7  test    edi, edi
0x1800021d9  jnz     loc_1800022BF
0x1800021df  mov     rcx, [rbx]; pavi
0x1800021e2  lea     rdx, [rbp+670h+psi]; psi
0x1800021e6  mov     r8d, 0CCh; lSize
0x1800021ec  call    AVIStreamInfoW
0x1800021f1  mov     edi, eax
0x1800021f3  test    eax, eax
0x1800021f5  jnz     loc_1800022B0
0x1800021fb  cmp     qword ptr [rbx], 0
0x1800021ff  jnz     short loc_180002219
0x180002201  mov     rax, [rsp+770h+var_700]
0x180002206  mov     rcx, [rax+rsi*8]
0x18000220a  mov     [rbx], rcx
0x18000220d  mov     rax, [rcx]
0x180002210  mov     rax, [rax+8]
0x180002214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002219  mov     rcx, [rbx]; pavi
0x18000221c  call    AVIStreamStart
0x180002221  mov     ebx, [rsp+770h+var_710]
0x180002225  inc     ebx
0x180002227  mov     [rbp+rsi*4+670h+var_150], eax
0x18000222e  mov     [rsp+770h+var_710], ebx
0x180002232  cmp     ebx, r14d
0x180002235  jl      loc_180002119
0x18000223b  mov     [rsp+770h+var_71C], r12d
0x180002240  test    r15d, r15d
0x180002243  jle     short loc_180002269
0x180002245  mov     rax, [rbp+670h+pavi]
0x18000224c  movsxd  rdx, r15d
0x18000224f  xor     r15d, r15d
0x180002252  mov     rcx, [rbp+rdx*8+670h+pavi]
0x18000225a  mov     [rbp+rdx*8+670h+pavi], rax
0x180002262  mov     [rbp+670h+pavi], rcx
0x180002269  mov     rax, [rsp+770h+var_6F8]
0x18000226e  lea     rcx, ?GetClassID@CPersistFileImpl@CAVIFile@@UEAAJPEAU_GUID@@@Z; CAVIFile::CPersistFileImpl::GetClassID(_GUID *)
0x180002275  test    rax, rax
0x180002278  mov     r12d, 8000h
0x18000227e  mov     edx, r12d; dwBytes
0x180002281  cmovnz  rcx, rax
0x180002285  mov     [rsp+770h+var_700], rcx
0x18000228a  mov     ecx, 2; uFlags
0x18000228f  call    cs:__imp_GlobalAlloc
0x180002295  mov     rcx, rax; hMem
0x180002298  call    cs:__imp_GlobalLock
0x18000229e  mov     rsi, rax
0x1800022a1  test    rax, rax
0x1800022a4  jnz     short loc_1800022CB
0x1800022a6  mov     edi, 80044067h
0x1800022ab  jmp     loc_180002C6B
0x1800022b0  mov     rcx, [rbx]
0x1800022b3  mov     rax, [rcx]
0x1800022b6  mov     rax, [rax+10h]
0x1800022ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022bf  mov     qword ptr [rbx], 0
0x1800022c6  jmp     loc_180002C6B
0x1800022cb  mov     rcx, [rbp+670h+pavi]; pavi
0x1800022d2  lea     rdx, [rbp+670h+psi]; psi
0x1800022d6  mov     r8d, 0CCh; lSize
0x1800022dc  call    AVIStreamInfoW
0x1800022e1  mov     r8d, [rbp+670h+psi.dwRate]; nDenominator
0x1800022e5  mov     ecx, 0F4240h; nNumber
0x1800022ea  mov     edx, [rbp+670h+psi.dwScale]; nNumerator
0x1800022ed  call    cs:__imp_MulDiv
0x1800022f3  mov     eax, [rbp+670h+psi.dwLength]
0x1800022f6  mov     [rsp+770h+var_714], eax
0x1800022fa  xor     eax, eax
0x1800022fc  mov     [rsp+770h+var_70C], eax
0x180002300  test    r15d, r15d
0x180002303  js      short loc_180002365
0x180002305  lfence
0x180002308  movsxd  rbx, r15d
0x18000230b  mov     [rbp+670h+var_6E0], r12d
0x18000230f  mov     rcx, [rbp+rbx*8+670h+pavi]; pavi
0x180002317  call    AVIStreamStart
0x18000231c  mov     rcx, [rbp+rbx*8+670h+pavi]
0x180002324  lea     r9, [rbp+670h+var_6E0]
0x180002328  mov     r10d, eax
0x18000232b  mov     r8, rsi
0x18000232e  mov     rdx, [rcx]
0x180002331  mov     rax, [rdx+30h]
0x180002335  mov     edx, r10d
0x180002338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000233d  mov     edi, eax
0x18000233f  movsxd  rax, [rbp+670h+var_6E0]
0x180002343  cmp     rax, 28h ; '('
0x180002347  jnb     short loc_180002353
0x180002349  mov     edi, 80044068h
0x18000234e  jmp     loc_180002C47
0x180002353  test    edi, edi
0x180002355  jnz     loc_180002C47
0x18000235b  mov     [rsp+770h+var_710], 1
0x180002363  jmp     short loc_18000237A
0x180002365  mov     rcx, [rbp+670h+pavi]; pavi
0x18000236c  mov     edx, 1F4h; lTime
0x180002371  call    AVIStreamTimeToSample
0x180002376  mov     [rsp+770h+var_710], eax
0x18000237a  xor     r15d, r15d
0x18000237d  test    r14d, r14d
0x180002380  jle     loc_180002C47
0x180002386  mov     ebx, [rsp+770h+var_71C]
0x18000238a  movsxd  r13, r15d
0x18000238d  lea     rdx, [rbp+670h+psi]; psi
0x180002391  mov     r8d, 0CCh; lSize
0x180002397  mov     rcx, [rbp+r13*8+670h+pavi]; pavi
0x18000239f  call    AVIStreamInfoW
0x1800023a4  mov     [rbp+670h+psi.dwInitialFrames], 0
0x1800023ab  test    ebx, ebx
0x1800023ad  jz      short loc_1800023D1
0x1800023af  test    r15d, r15d
0x1800023b2  jle     short loc_1800023D1
0x1800023b4  cmp     [rbp+670h+psi.fccType], 73646976h
0x1800023bb  jz      short loc_1800023D1
0x1800023bd  mov     rcx, [rbp+670h+pavi]; pavi
0x1800023c4  mov     edx, 2EEh; lTime
0x1800023c9  call    AVIStreamTimeToSample
0x1800023ce  mov     [rbp+670h+psi.dwInitialFrames], eax
0x1800023d1  mov     rcx, [rbp+r13*8+670h+pavi]; pavi
0x1800023d9  mov     [rbp+670h+var_6E0], r12d
0x1800023dd  call    AVIStreamStart
0x1800023e2  mov     rcx, [rbp+r13*8+670h+pavi]
0x1800023ea  lea     r9, [rbp+670h+var_6E0]
0x1800023ee  mov     r10d, eax
0x1800023f1  mov     r8, rsi
0x1800023f4  mov     rdx, [rcx]
0x1800023f7  mov     rax, [rdx+30h]
0x1800023fb  mov     edx, r10d
0x1800023fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002403  mov     edi, eax
0x180002405  test    eax, eax
0x180002407  jnz     loc_180002C47
0x18000240d  mov     rcx, [rbp+670h+ppfile]
0x180002411  lea     rdx, [rbp+670h+var_350]
0x180002418  lea     rdx, [rdx+r13*8]
0x18000241c  mov     qword ptr [rdx], 0
0x180002423  lea     r8, [rbp+670h+psi]
0x180002427  mov     rax, [rcx]
0x18000242a  mov     rax, [rax+28h]
0x18000242e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002433  mov     edi, eax
0x180002435  test    eax, eax
0x180002437  jnz     loc_180002516
0x18000243d  mov     rcx, [rbp+r13*8+670h+var_350]
0x180002445  test    rcx, rcx
0x180002448  jz      loc_180002516
0x18000244e  mov     rax, [rcx]
0x180002451  mov     r8, rsi
0x180002454  mov     r9d, [rbp+670h+var_6E0]
0x180002458  xor     edx, edx
0x18000245a  mov     rax, [rax+38h]
0x18000245e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002463  mov     edi, eax
0x180002465  test    eax, eax
0x180002467  jnz     loc_180002C47
0x18000246d  mov     rcx, [rbp+r13*8+670h+pavi]
0x180002475  lea     r9, [rbp+670h+var_6E0]
0x180002479  mov     [rbp+670h+var_6E0], r12d
0x18000247d  mov     ebx, 64727473h
0x180002482  mov     r8, rsi
0x180002485  mov     edx, ebx
0x180002487  mov     rax, [rcx]
0x18000248a  mov     rax, [rax+58h]
0x18000248e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002493  mov     edi, eax
0x180002495  test    eax, eax
0x180002497  jnz     short loc_1800024C5
0x180002499  mov     r9d, [rbp+670h+var_6E0]
0x18000249d  test    r9d, r9d
0x1800024a0  jz      short loc_1800024C5
  ... truncated ...
```
