# StorageReserveHelper::DeleteReserveAreaContent(ushort const *,_STORAGE_RESERVE_ID)

- ea: `0x1800262e0`
- end: `0x180026eb1`
- name: `?DeleteReserveAreaContent@StorageReserveHelper@@YAJPEBGW4_STORAGE_RESERVE_ID@@@Z`
- size: `3025`
- prototype: `__int64 __fastcall(StorageReserveHelper *this, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `44`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800133f8`

## callees

- `0x180003870`
- `0x180003894`
- `0x180003c84`
- `0x180003e80`
- `0x180004164`
- `0x180004264`
- `0x18000427c`
- `0x1800042f4`
- `0x1800044e0`
- `0x180008140`
- `0x18000a0cc`
- `0x18000a0f4`
- `0x1800255a4`
- `0x180025630`
- `0x180025b48`
- `0x180025c08`
- `0x180025cdc`
- `0x180025e50`
- `0x180025e7c`
- `0x1800262e0`
- `0x180026eb8`
- `0x180026fd4`
- `0x18002729c`
- `0x1800273a8`
- `0x180027c2c`
- `0x1800280b0`
- `0x180028644`
- `0x1800292fc`
- `0x1800294ac`
- `0x180029570`
- `0x1800295dc`
- `0x1800296f4`
- `0x18002980c`
- `0x180029aa8`
- `0x180029b1c`
- `0x18002a2e4`
- `0x18002ac04`
- `0x18002ce34`
- `0x18002d33c`
- `0x18002d494`
- `0x18002de04`
- `0x180031b80`
- `0x180031bf8`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026cd5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800269c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026b1d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026c62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026cd5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026e50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026e50`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800269a3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800269a3`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800269ba`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800269ba`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180026aff`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180026b75`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180026aff`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180026b75`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180026ccb`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180026ccb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800266ee`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800266ee`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800267de`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800267de`

## string_xrefs

- `0x180026330`: `DeleteReserveAreaContent`

## pseudocode

```c
__int64 __fastcall StorageReserveHelper::DeleteReserveAreaContent(
        StorageReserveHelper *this,
        const unsigned __int16 *a2,
        __int64 a3)
{
  int v3; // r13d
  __int64 v5; // rdi
  __int64 *v6; // rbx
  _QWORD *v7; // r14
  _QWORD *v8; // rsi
  StorageReserveHelper::Internal *v9; // rcx
  int Dependencies; // r15d
  __int64 v11; // rdi
  _QWORD *i; // rsi
  __int64 *v13; // rcx
  __int64 v14; // rdi
  _QWORD *mm; // rsi
  unsigned __int64 v16; // rsi
  unsigned int *v17; // rbx
  unsigned __int64 v18; // rdx
  struct _QUERY_STORAGE_RESERVE_OUTPUT **v19; // r8
  __int64 v20; // rax
  WCHAR *v21; // rcx
  WCHAR v22; // r9
  __int64 *v23; // rsi
  __int64 v24; // rbx
  _QWORD *j; // rdi
  int StorageReserve; // eax
  void *v27; // rdx
  __int64 v28; // rbx
  _QWORD *k; // rdi
  struct _QUERY_STORAGE_RESERVE_OUTPUT *v30; // rdi
  __int64 v31; // rbx
  _QWORD *m; // rdi
  struct StorageReserveTelemetry::Internal::SRProvider *v33; // rax
  StorageReserveTelemetry::Internal::SRProvider *v34; // rcx
  int v35; // eax
  __int64 v36; // rbx
  _QWORD *n; // rdi
  _DWORD *v38; // r12
  unsigned __int64 v39; // rdx
  const char *v40; // r9
  unsigned __int64 v41; // rdx
  __int64 v42; // rbx
  _QWORD *ii; // rdi
  void *v44; // rdi
  DWORD v45; // r13d
  int v46; // eax
  struct StorageReserveTelemetry::Internal::SRProvider *v47; // rax
  StorageReserveTelemetry::Internal::SRProvider *v48; // rcx
  char *v49; // r13
  enum _STORAGE_RESERVE_ID *v50; // r9
  unsigned int v51; // esi
  void **kk; // rbx
  int v53; // eax
  bool v54; // cf
  char *v55; // rcx
  unsigned __int64 v56; // rsi
  void *v57; // r12
  void *v58; // rbx
  int v59; // esi
  _BYTE *v60; // rsi
  DWORD FileAttributesW; // eax
  size_t v62; // rax
  unsigned int v63; // esi
  int v64; // eax
  unsigned __int64 v65; // rsi
  __int64 v66; // rcx
  struct StorageReserveTelemetry::Internal::SRProvider *v67; // rax
  StorageReserveTelemetry::Internal::SRProvider *v68; // rcx
  unsigned __int64 v69; // r8
  StorageReserveHelper::Internal *v70; // rsi
  unsigned __int64 v71; // r8
  struct StorageReserveTelemetry::Internal::SRProvider *v72; // rax
  StorageReserveTelemetry::Internal::SRProvider *v73; // rcx
  struct StorageReserveTelemetry::Internal::SRProvider *v74; // rax
  StorageReserveTelemetry::Internal::SRProvider *v75; // rcx
  signed int LastError; // eax
  unsigned int v77; // esi
  struct StorageReserveTelemetry::Internal::SRProvider *v78; // rax
  StorageReserveTelemetry::Internal::SRProvider *v79; // rcx
  unsigned __int64 v80; // rbx
  unsigned __int64 v81; // r13
  DWORD v82; // esi
  const unsigned __int16 *v83; // r12
  struct StorageReserveTelemetry::Internal::SRProvider *v84; // rax
  StorageReserveTelemetry::Internal::SRProvider *v85; // rcx
  const unsigned __int16 *v86; // rsi
  struct StorageReserveTelemetry::Internal::SRProvider *v87; // rax
  StorageReserveTelemetry::Internal::SRProvider *v88; // rcx
  struct _QUERY_STORAGE_RESERVE_OUTPUT **v89; // r8
  struct StorageReserveTelemetry::Internal::SRProvider *v90; // rax
  StorageReserveTelemetry::Internal::SRProvider *v91; // rcx
  StorageReserveHelper *v92; // r14
  void *v93; // rdx
  struct _QUERY_STORAGE_RESERVE_OUTPUT *v94; // rbx
  struct StorageReserveTelemetry::Internal::SRProvider *v95; // rax
  StorageReserveTelemetry::Internal::SRProvider *v96; // rcx
  unsigned __int64 v97; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v101; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String2; // [rsp+48h] [rbp-B8h] BYREF
  int v103; // [rsp+50h] [rbp-B0h]
  int v104; // [rsp+54h] [rbp-ACh]
  unsigned __int64 v105; // [rsp+58h] [rbp-A8h]
  size_t v106; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v107; // [rsp+68h] [rbp-98h]
  unsigned int v108; // [rsp+70h] [rbp-90h]
  DWORD jj; // [rsp+74h] [rbp-8Ch]
  _DWORD *v110; // [rsp+78h] [rbp-88h]
  char *v111; // [rsp+80h] [rbp-80h]
  __int64 v112; // [rsp+88h] [rbp-78h]
  __int64 v113; // [rsp+90h] [rbp-70h]
  struct _QUERY_STORAGE_RESERVE_OUTPUT *v114; // [rsp+98h] [rbp-68h] BYREF
  HANDLE hDevice; // [rsp+A0h] [rbp-60h]
  unsigned int *v116; // [rsp+A8h] [rbp-58h]
  _OWORD v117[2]; // [rsp+B0h] [rbp-50h] BYREF
  void *v118; // [rsp+D0h] [rbp-30h]
  _DWORD *v119; // [rsp+D8h] [rbp-28h]
  _QWORD v120[2]; // [rsp+E0h] [rbp-20h] BYREF
  StorageReserveHelper *v121; // [rsp+F0h] [rbp-10h]
  __int64 v122; // [rsp+F8h] [rbp-8h]
  DWORD BytesReturned[4]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v124[42]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR FileName[32768]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+102A8h] [rbp+101A8h]

  v122 = -2;
  v3 = (int)a2;
  v104 = (int)a2;
  v121 = this;
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v124,
    "DeleteReserveAreaContent",
    a3);
  v124[0] = &StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent::`vftable';
  StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent::StartActivity((StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent *)v124);
  v5 = 100;
  v120[1] = 100;
  v6 = (__int64 *)operator new(0x328u);
  *v6 = 100;
  v7 = v6 + 1;
  v8 = v6 + 1;
  do
  {
    Windows::AutoNewArrayPtr<unsigned short>::AutoNewArrayPtr<unsigned short>(v8++);
    --v5;
  }
  while ( v5 );
  v120[0] = v6 + 1;
  memset_0(FileName, 0, sizeof(FileName));
  BytesReturned[0] = 0;
  memset(v117, 0, 28);
  Dependencies = StorageReserveHelper::Internal::LoadDependencies(v9);
  if ( Dependencies < 0 )
  {
    if ( v6 != (__int64 *)-8LL )
    {
      v11 = *v6;
      for ( i = &v7[*v6]; v11; --v11 )
        Windows::AutoNewArrayPtr<unsigned short>::~AutoNewArrayPtr<unsigned short>(--i);
LABEL_7:
      v13 = v6;
LABEL_58:
      operator delete(v13);
      goto LABEL_180;
    }
    goto LABEL_180;
  }
  if ( this )
  {
    v16 = -1;
    v17 = 0;
    do
      ++v16;
    while ( *((_WORD *)this + v16) );
    v107 = v16;
    if ( v16 > 0x7FFFFFFE )
    {
      Dependencies = -2147024809;
      FileName[0] = 0;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14F,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereservehelper.cpp",
        (const char *)(unsigned int)Dependencies,
        dwCreationDisposition);
      if ( !v7 )
        goto LABEL_180;
      v23 = v7 - 1;
      v24 = *(v7 - 1);
      for ( j = &v7[v24]; v24; --v24 )
        Windows::AutoNewArrayPtr<unsigned short>::~AutoNewArrayPtr<unsigned short>(--j);
LABEL_57:
      v13 = v23;
      goto LABEL_58;
    }
    v18 = v16;
    v19 = (struct _QUERY_STORAGE_RESERVE_OUTPUT **)this;
    v20 = 0x8000;
    v21 = FileName;
    Dependencies = 0;
    while ( v18 )
    {
      v22 = *(_WORD *)v19;
      if ( *(_WORD *)v19 )
      {
        v19 = (struct _QUERY_STORAGE_RESERVE_OUTPUT **)((char *)v19 + 2);
        *v21++ = v22;
        --v18;
        if ( --v20 )
          continue;
      }
      if ( !v20 )
      {
        --v21;
        Dependencies = -2147024774;
      }
      break;
    }
    *v21 = 0;
    if ( Dependencies < 0 )
      goto LABEL_24;
    if ( *((_WORD *)&v124[41] + v16 + 3) == 92 )
    {
      v107 = --v16;
      if ( 2 * v16 >= 0x10000 )
        _report_rangecheckfailure(2 * v16, v18, v19);
      FileName[v16] = 0;
    }
    v114 = 0;
    StorageReserve = StorageReserveHelper::QueryStorageReserve(this, (const unsigned __int16 *)&v114, v19);
    Dependencies = StorageReserve;
    if ( StorageReserve < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereservehelper.cpp",
        (const char *)(unsigned int)StorageReserve,
        dwCreationDisposition);
      if ( !v7 )
        goto LABEL_180;
      v23 = v7 - 1;
      v28 = *(v7 - 1);
      for ( k = &v7[v28]; v28; --v28 )
        Windows::AutoNewArrayPtr<unsigned short>::~AutoNewArrayPtr<unsigned short>(--k);
      goto LABEL_57;
    }
    v30 = v114;
    if ( !v114 )
    {
      Dependencies = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15C,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereservehelper.cpp",
        (const char *)0x8007000ELL,
        dwCreationDisposition);
      if ( !v7 )
        goto LABEL_180;
      v23 = v7 - 1;
      v31 = *(v7 - 1);
      for ( m = &v7[v31]; v31; --v31 )
        Windows::AutoNewArrayPtr<unsigned short>::~AutoNewArrayPtr<unsigned short>(--m);
      goto LABEL_57;
    }
    if ( *((_DWORD *)v114 + 1) )
    {
      while ( *((_DWORD *)v114 + 6 * (unsigned int)v17 + 2) != v3 )
      {
        LODWORD(v17) = (_DWORD)v17 + 1;
        if ( (unsigned int)v17 >= *((_DWORD *)v114 + 1) )
          goto LABEL_48;
      }
      v33 = StorageReserveTelemetry::Internal::SRProvider::Instance();
      if ( *((_QWORD *)v33 + 1) )
      {
        v27 = (void *)**((unsigned int **)v33 + 1);
        if ( (_DWORD)v27 )
        {
          StorageReserveTelemetry::Internal::SRProvider::Instance();
          StorageReserveTelemetry::Internal::SRProvider::QueryReserveSpaceBeforeDelete_(v34, (unsigned int)v17, v30);
        }
      }
LABEL_48:
      v35 = StorageReserveHelper::FreeOutputBuffer(v30, v27);
      Dependencies = v35;
      v17 = 0;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16C,
          (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereservehelper.cpp",
          (const char *)(unsigned int)v35,
          dwCreationDisposition);
        if ( !v7 )
          goto LABEL_180;
        v23 = v7 - 1;
        v36 = *(v7 - 1);
        for ( n = &v7[v36]; v36; --v36 )
          Windows::AutoNewArrayPtr<unsigned short>::~AutoNewArrayPtr<unsigned short>(--n);
        goto LABEL_57;
      }
    }
    v38 = operator new[](0x14u);
    v119 = v38;
    v38[1] = 103;
    v38[2] = 3;
    *v38 = 1;
    v38[4] = v3;
    hDevice = CreateFileW(FileName, 0x100u, 3u, 0, 3u, 0x2000080u, 0);
    if ( hDevice == (HANDLE)-1LL )
    {
      Dependencies = wil::details::in1diag3::Return_GetLastError(
                       retaddr,
                       (void *)0x189,
                       (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereservehelper.cpp",
                       v40);
      operator delete(v38, v41);
      if ( !v7 )
        goto LABEL_180;
      v23 = v7 - 1;
      v42 = *(v7 - 1);
      for ( ii = &v7[v42]; v42; --v42 )
        Windows::AutoNewArrayPtr<unsigned short>::~AutoNewArrayPtr<unsigned short>(--ii);
      goto LABEL_57;
    }
    v105 = 0;
    v44 = 0;
    v118 = 0;
    v116 = 0;
    v45 = 0x2000000;
    LODWORD(v101) = 0;
    v112 = 0;
    v113 = 0;
    while ( 1 )
    {
      v46 = 1;
      for ( jj = v45; ; v45 = jj )
      {
        if ( v46 )
        {
          if ( v44 )
            operator delete(v44, v39);
          v44 = operator new[](v45);
          v118 = v44;
          v17 = (unsigned int *)v44;
          v116 = (unsigned int *)v44;
        }
        if ( !DeviceIoControl(hDevice, 0x90277u, v38, 0x14u, v17, v45, BytesReturned, 0) )
          break;
        v47 = StorageReserveTelemetry::Internal::SRProvider::Instance();
        if ( *((_QWORD *)v47 + 1) && **((_DWORD **)v47 + 1) )
        {
          StorageReserveTelemetry::Internal::SRProvider::Instance();
          StorageReserveTelemetry::Internal::SRProvider::QueryFileLayoutSuccess_(
            v48,
            (struct _QUERY_FILE_LAYOUT_OUTPUT *)v17);
        }
        v49 = (char *)v17 + v17[1];
        v108 = 0;
        if ( *v17 )
        {
          while ( 1 )
          {
            if ( !*((_DWORD *)v49 + 6) )
            {
              v74 = StorageReserveTelemetry::Internal::SRProvider::Instance();
              if ( *((_QWORD *)v74 + 1) && **((_DWORD **)v74 + 1) )
              {
                StorageReserveTelemetry::Internal::SRProvider::Instance();
                StorageReserveTelemetry::Internal::SRProvider::FirstNameOffsetMissing_(
                  v75,
                  (struct _FILE_LAYOUT_ENTRY *)v49);
              }
LABEL_135:
              Dependencies = -2147024662;
              goto LABEL_136;
            }
            v103 = 0;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::GetImpl'::`2'::impl) )
            {
              v110 = v49 + 12;
              if ( (v49[12] & 0x10) != 0 )
              {
                LODWORD(v101) = 0;
                v110 = v49 + 12;
              }
              else
              {
                v51 = 0;
                for ( kk = (void **)&v49[*((unsigned int *)v49 + 6)]; ; kk = (void **)((char *)kk + *(unsigned int *)kk) )
                {
                  if ( *((_DWORD *)kk + 1) != 2 )
                  {
                    LODWORD(v101) = 0;
                    if ( (int)StorageReserveHelper::Internal::QueryAreaID(
                                (StorageReserveHelper::Internal *)hDevice,
                                kk[1],
                                (unsigned __int64)&v101,
                                v50) >= 0 )
                    {
                      v53 = v101;
                    }
                    else
                    {
                      ++LODWORD(v117[1]);
                      v53 = 0;
                    }
                    if ( ++v51 == 1 )
                      ++HIDWORD(v117[0]);
                    if ( v53 != v104 )
                    {
                      ++DWORD1(v117[1]);
                      LODWORD(v101) = 0;
                      v16 = v107;
                      goto LABEL_88;
                    }
                  }
                  if ( !*(_DWORD *)kk )
                    break;
                }
                LODWORD(v101) = 1;
                v110 = v49 + 12;
                v54 = v51 < 2;
                v16 = v107;
                if ( !v54 )
                  ++DWORD2(v117[1]);
              }
            }
            else
            {
              v110 = v49 + 12;
            }
LABEL_88:
            v55 = &v49[*((unsigned int *)v49 + 6)];
            while ( 1 )
            {
              v111 = v55;
              if ( *((_DWORD *)v55 + 1) == 2 )
                goto LABEL_128;
              v56 = ((unsigned __int64)*((unsigned int *)v55 + 4) >> 1) + 7 + v16;
              v57 = operator new(saturated_mul(v56, 2u));
              v58 = v57;
              memset_0(v57, 0, 2 * v56);
              String2 = (wchar_t *)(v111 + 24);
              memcpy_0(v57, v111 + 24, *((unsigned int *)v111 + 4));
              v59 = ((__int64 (__fastcall *)(void *, unsigned __int64, WCHAR *, void *))StorageReserveHelper::Internal::pfnPathCchCombineEx)(
                      v58,
                      v56,
                      FileName,
                      v58);
              if ( v59 < 0 )
              {
                v72 = StorageReserveTelemetry::Internal::SRProvider::Instance();
                if ( *((_QWORD *)v72 + 1) && **((_DWORD **)v72 + 1) )
                {
                  StorageReserveTelemetry::Internal::SRProvider::Instance();
                  StorageReserveTelemetry::Internal::SRProvider::PathCombineFailure_(v73, v59);
                }
                goto LABEL_125;
              }
              v60 = v110;
              FileAttributesW = *v110;
              if ( *v110 == -1 && (FileAttributesW = GetFileAttributesW((LPCWSTR)v57), FileAttributesW == -1)
                || (FileAttributesW & 1) != 0 && !SetFileAttributesW((LPCWSTR)v57, FileAttributesW & 0xFFFFFFFE) )
              {
                GetLastError();
              }
              if ( (*v60 & 0x10) != 0 )
              {
                if ( (int)StorageReserveHelper::Internal::AutoNewDynamicArrayPtr<Windows::AutoNewArrayPtr<unsigned short>>::EnsureSize(
                            v120,
                            v105) < 0 )
                {
                  v7 = (_QWORD *)v120[0];
                }
                else
                {
                  v62 = (unsigned __int64)*((unsigned int *)v111 + 4) >> 1;
                  v106 = v62;
                  v63 = 0;
                  while ( 1 )
                  {
                    v64 = wcsnicmp(
                            (const wchar_t *)(&StorageReserveHelper::Internal::SoftReservePaths)[v63],
                            String2,
                            v62);
                    v7 = (_QWORD *)v120[0];
                    if ( !v64 && !*((_WORD *)(&StorageReserveHelper::Internal::SoftReservePaths)[v63] + v106) )
                      break;
                    ++v63;
                    v62 = v106;
                    if ( v63 >= 9 )
                    {
                      v65 = v105;
                      if ( v105 )
                      {
                        do
                        {
                          if ( wcsicmp((const wchar_t *)v7[v65 - 1], (const wchar_t *)v57) >= 0 )
                            break;
                          v66 = v7[v65];
                          v7[v65] = v7[v65 - 1];
                          v7[--v65] = v66;
                        }
                        while ( v65 );
                        v44 = v118;
                      }
                      v67 = StorageReserveTelemetry::Internal::SRProvider::Instance();
                      if ( *((_QWORD *)v67 + 1) && **((_DWORD **)v67 + 1) )
                      {
                        StorageReserveTelemetry::Internal::SRProvider::Instance();
                        StorageReserveTelemetry::Internal::SRProvider::DirectoryFound_(
                          v68,
                          (const unsigned __int16 *)v57);
                      }
                      if ( v7[v65] )
                        INTERNAL_ERROR_ACTION(-1073741595);
                      v58 = 0;
                      v7[v65] = v57;
                      ++v105;
                      break;
                    }
                  }
                  v103 = 1;
                }
                goto LABEL_125;
              }
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::GetImpl'::`2'::impl) )
              {
                if ( !(_DWORD)v101 )
                {
                  ++v113;
                  v70 = (StorageReserveHelper::Internal *)hDevice;
                  Dependencies = StorageReserveHelper::Internal::SetAreaID(
                                   (StorageReserveHelper::Internal *)hDevice,
                                   *((void **)v49 + 2),
                                   v69,
                                   StorageReserveIdNone,
                                   3u);
                  if ( Dependencies == -2147024784 )
                    StorageReserveHelper::Internal::SetAreaID(
                      v70,
                      *((void **)v49 + 2),
                      v71,
                      StorageReserveIdSoft,
                      dwCreationDispositiona);
                  goto LABEL_125;
                }
                ++v112;
                if ( !DeleteFileW((LPCWSTR)v57) )
                {
LABEL_117:
                  LODWORD(v106) = GetLastError();
                  String2 = (wchar_t *)v57;
                  StorageReserveTelemetry::Internal::SRProvider::DeleteFileFailure<unsigned short *,unsigned long &>(
                    &String2,
                    &v106);
                  goto LABEL_125;
                }
              }
              else
              {
                if ( !DeleteFileW((LPCWSTR)v57) )
                  goto LABEL_117;
                v103 = 1;
              }
              String2 = (wchar_t *)v57;
              StorageReserveTelemetry::Internal::SRProvider::DeleteFileSuccess<unsigned short *>(&String2);
LABEL_125:
              if ( v58 )
                operator delete(v58);
              v55 = v111;
LABEL_128:
              if ( !*(_DWORD *)v55 )
                break;
              v55 += *(unsigned int *)v55;
              v16 = v107;
            }
            v17 = v116;
            if ( !v103 )
              goto LABEL_135;
LABEL_136:
            v49 += *((unsigned int *)v49 + 1);
            ++v108;
            v16 = v107;
            if ( v108 >= *v17 )
            {
              v38 = v119;
              break;
            }
          }
        }
        v46 = 0;
        v38[1] &= ~1u;
      }
      LastError = GetLastError();
      if ( LastError != 122 )
      {
        v77 = 0;
        if ( LastError != 38 )
        {
          Dependencies = LastError > 0 ? (unsigned __int16)LastError | 0x80070000 : LastError;
          v78 = StorageReserveTelemetry::Internal::SRProvider::Instance();
          if ( *((_QWORD *)v78 + 1) )
          {
            if ( **((_DWORD **)v78 + 1) )
            {
              StorageReserveTelemetry::Internal::SRProvider::Instance();
              StorageReserveTelemetry::Internal::SRProvider::QueryFileLayoutFailure_(v79, Dependencies);
            }
          }
        }
        v80 = 0;
        v81 = v105;
        if ( v105 )
        {
          do
          {
            if ( RemoveDirectoryW((LPCWSTR)v7[v80]) )
            {
              v86 = (const unsigned __int16 *)v7[v80];
              v87 = StorageReserveTelemetry::Internal::SRProvider::Instance();
              if ( *((_QWORD *)v87 + 1) && **((_DWORD **)v87 + 1) )
              {
                StorageReserveTelemetry::Internal::SRProvider::Instance();
                StorageReserveTelemetry::Internal::SRProvider::RemoveDirectorySuccess_(v88, v86);
              }
              v77 = 0;
            }
            else
            {
              v82 = GetLastError();
              v83 = (const unsigned __int16 *)v7[v80];
              v84 = StorageReserveTelemetry::Internal::SRProvider::Instance();
              if ( *((_QWORD *)v84 + 1) && **((_DWORD **)v84 + 1) )
              {
                StorageReserveTelemetry::Internal::SRProvider::Instance();
                StorageReserveTelemetry::Internal::SRProvider::RemoveDirectoryFailure_(v85, v82, v83);
              }
              v77 = 0;
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::GetImpl'::`2'::impl) )
                Dependencies = -2147024662;
            }
            ++v80;
          }
          while ( v80 < v81 );
          v38 = v119;
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_StorageReserve_HelperLib_Hardlink_fix>::GetImpl'::`2'::impl) )
        {
          *(_QWORD *)((char *)v117 + 4) = __PAIR64__(v113, v112);
          LOBYTE(v117[0]) = 1;
          v90 = StorageReserveTelemetry::Internal::SRProvider::Instance();
          if ( *((_QWORD *)v90 + 1) && **((_DWORD **)v90 + 1) )
          {
            StorageReserveTelemetry::Internal::SRProvider::Instance();
            StorageReserveTelemetry::Internal::SRProvider::HardlinkStats_(
              v91,
              (struct StorageReserveHelper::Internal::_STORAGE_RESERVE_HARDLINK_STATS *)v117);
          }
          Dependencies = 0;
        }
        v92 = v121;
        if ( (int)StorageReserveHelper::QueryStorageReserve(v121, (const unsigned __int16 *)&v114, v89) >= 0 )
        {
          v94 = v114;
          if ( v114 )
          {
            if ( *((_DWORD *)v114 + 1) )
            {
              while ( *((_DWORD *)v114 + 6 * v77 + 2) != v104 )
              {
                if ( ++v77 >= *((_DWORD *)v114 + 1) )
                  goto LABEL_175;
              }
              v95 = StorageReserveTelemetry::Internal::SRProvider::Instance();
              if ( *((_QWORD *)v95 + 1) )
              {
                v93 = (void *)**((unsigned int **)v95 + 1);
                if ( (_DWORD)v93 )
                {
                  StorageReserveTelemetry::Internal::SRProvider::Instance();
                  StorageReserveTelemetry::Internal::SRProvider::QueryReserveSpaceAfterDelete_(v96, v94, v77);
                }
              }
LABEL_175:
              StorageReserveHelper::FreeOutputBuffer(v94, v93);
            }
          }
        }
        StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent::Stop(
          (StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent *)v124,
          (const unsigned __int16 *)v92,
          v104,
          Dependencies);
        if ( v44 )
          operator delete(v44, v97);
        operator delete(v38, v97);
        StorageReserveHelper::Internal::AutoNewDynamicArrayPtr<Windows::AutoNewArrayPtr<unsigned short>>::~AutoNewDynamicArrayPtr<Windows::AutoNewArrayPtr<unsigned short>>(v120);
        if ( hDevice )
          CloseHandle(hDevice);
        goto LABEL_180;
      }
      v45 = BytesReturned[0];
    }
  }
  Dependencies = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x14C,
    (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereservehelper.cpp",
    (const char *)0x80070057LL,
    dwCreationDisposition);
  if ( v6 != (__int64 *)-8LL )
  {
    v14 = *v6;
    for ( mm = &v7[*v6]; v14; --v14 )
      Windows::AutoNewArrayPtr<unsigned short>::~AutoNewArrayPtr<unsigned short>(--mm);
    goto LABEL_7;
  }
LABEL_180:
  v124[0] = &StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent::`vftable';
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v124);
  wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v124);
  return (unsigned int)Dependencies;
}

```

## disassembly

```asm
0x1800262e0  push    rbp
0x1800262e2  push    rsi
0x1800262e3  push    rdi
0x1800262e4  push    r12
0x1800262e6  push    r13
0x1800262e8  push    r14
0x1800262ea  push    r15
0x1800262ec  lea     rbp, [rsp-10170h]
0x1800262f4  mov     eax, 10270h
0x1800262f9  call    _alloca_probe
0x1800262fe  sub     rsp, rax
0x180026301  mov     [rbp+101A0h+var_101A8], 0FFFFFFFFFFFFFFFEh
0x180026309  mov     [rsp+102A0h+arg_10], rbx
0x180026311  mov     rax, cs:__security_cookie
0x180026318  xor     rax, rsp
0x18002631b  mov     [rbp+101A0h+var_40], rax
0x180026322  mov     r13d, edx
0x180026325  mov     [rsp+102A0h+var_1024C], edx
0x180026329  mov     r12, rcx
0x18002632c  mov     [rbp+101A0h+var_101B0], rcx
0x180026330  lea     rdx, aDeletereservea; "DeleteReserveAreaContent"
0x180026337  lea     rcx, [rbp+101A0h+var_10190]
0x18002633b  call    ??0?$ActivityBase@VStorageReserveProvider@Internal@StorageReserveTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<StorageReserveTelemetry::Internal::StorageReserveProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180026340  lea     rax, ??_7DeleteReserveAreaContent@SRProvider@Internal@StorageReserveTelemetry@@6B@; const StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent::`vftable'
0x180026347  mov     [rbp+101A0h+var_10190], rax
0x18002634b  lea     rcx, [rbp+101A0h+var_10190]; this
0x18002634f  call    ?StartActivity@DeleteReserveAreaContent@SRProvider@Internal@StorageReserveTelemetry@@QEAAXXZ; StorageReserveTelemetry::Internal::SRProvider::DeleteReserveAreaContent::StartActivity(void)
0x180026354  mov     edi, 64h ; 'd'
0x180026359  mov     [rbp+101A0h+var_101B8], rdi
0x18002635d  mov     ecx, 328h; Size
0x180026362  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026367  mov     rbx, rax
0x18002636a  mov     [rax], rdi
0x18002636d  lea     r14, [rax+8]
0x180026371  mov     rsi, r14
0x180026374  mov     rcx, rsi
0x180026377  call    ??0?$AutoNewArrayPtr@G@Windows@@QEAA@XZ; Windows::AutoNewArrayPtr<ushort>::AutoNewArrayPtr<ushort>(void)
0x18002637c  add     rsi, 8
0x180026380  sub     rdi, 1
0x180026384  jnz     short loc_180026374
0x180026386  mov     [rbp+101A0h+var_101C0], r14
0x18002638a  xor     edx, edx; Val
0x18002638c  mov     r8d, 10000h; Size
0x180026392  lea     rcx, [rbp+101A0h+FileName]; void *
0x180026399  call    memset_0
0x18002639e  mov     [rbp+101A0h+BytesReturned], edi
0x1800263a1  xorps   xmm0, xmm0
0x1800263a4  movups  [rbp+101A0h+var_101F0], xmm0
0x1800263a8  movups  [rbp+101A0h+var_101F0+0Ch], xmm0
0x1800263ac  call    ?LoadDependencies@Internal@StorageReserveHelper@@YAJXZ; StorageReserveHelper::Internal::LoadDependencies(void)
0x1800263b1  mov     r15d, eax
0x1800263b4  test    eax, eax
0x1800263b6  jns     short loc_1800263E7
0x1800263b8  test    r14, r14
0x1800263bb  jz      loc_180026E56
0x1800263c1  mov     rdi, [rbx]
0x1800263c4  lea     rsi, [r14+rdi*8]
0x1800263c8  test    rdi, rdi
0x1800263cb  jz      short loc_1800263DF
0x1800263cd  sub     rsi, 8
0x1800263d1  mov     rcx, rsi
0x1800263d4  call    ??1?$AutoNewArrayPtr@G@Windows@@QEAA@XZ; Windows::AutoNewArrayPtr<ushort>::~AutoNewArrayPtr<ushort>(void)
0x1800263d9  sub     rdi, 1
0x1800263dd  jnz     short loc_1800263CD
0x1800263df  mov     rcx, rbx
0x1800263e2  jmp     loc_180026750
0x1800263e7  test    r12, r12
0x1800263ea  jnz     short loc_180026437
0x1800263ec  mov     rcx, [rbp+101A8h]; this
0x1800263f3  mov     r15d, 80070057h
0x1800263f9  mov     r9d, r15d; char *
0x1800263fc  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180026403  mov     edx, 14Ch; void *
0x180026408  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002640d  nop
0x18002640e  test    r14, r14
0x180026411  jz      loc_180026E56
0x180026417  mov     rdi, [rbx]
0x18002641a  lea     rsi, [r14+rdi*8]
0x18002641e  test    rdi, rdi
0x180026421  jz      short loc_1800263DF
0x180026423  sub     rsi, 8
0x180026427  mov     rcx, rsi
0x18002642a  call    ??1?$AutoNewArrayPtr@G@Windows@@QEAA@XZ; Windows::AutoNewArrayPtr<ushort>::~AutoNewArrayPtr<ushort>(void)
0x18002642f  sub     rdi, 1
0x180026433  jnz     short loc_180026423
0x180026435  jmp     short loc_1800263DF
0x180026437  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002643b  xor     ebx, ebx
0x18002643d  inc     rsi
0x180026440  cmp     [r12+rsi*2], bx
0x180026445  jnz     short loc_18002643D
0x180026447  mov     [rsp+102A0h+var_10238], rsi
0x18002644c  cmp     rsi, 7FFFFFFEh
0x180026453  jbe     short loc_180026464
0x180026455  mov     r15d, 80070057h
0x18002645b  mov     [rbp+101A0h+FileName], bx
0x180026462  jmp     short loc_1800264B4
0x180026464  mov     rdx, rsi
0x180026467  mov     r8, r12
0x18002646a  mov     eax, 8000h
0x18002646f  lea     rcx, [rbp+101A0h+FileName]
0x180026476  mov     r15d, ebx
0x180026479  test    rdx, rdx
0x18002647c  jz      short loc_1800264AC
0x18002647e  movzx   r9d, word ptr [r8]
0x180026482  test    r9w, r9w
0x180026486  jz      short loc_18002649D
0x180026488  add     r8, 2; struct _QUERY_STORAGE_RESERVE_OUTPUT **
0x18002648c  mov     [rcx], r9w
0x180026490  add     rcx, 2
0x180026494  dec     rdx
0x180026497  sub     rax, 1
0x18002649b  jnz     short loc_180026479
0x18002649d  test    rax, rax
0x1800264a0  jnz     short loc_1800264AC
0x1800264a2  sub     rcx, 2
0x1800264a6  mov     r15d, 8007007Ah
0x1800264ac  mov     [rcx], bx
0x1800264af  test    r15d, r15d
0x1800264b2  jns     short loc_180026504
0x1800264b4  mov     rcx, [rbp+101A8h]; this
0x1800264bb  mov     r9d, r15d; char *
0x1800264be  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800264c5  mov     edx, 14Fh; void *
0x1800264ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800264cf  nop
0x1800264d0  test    r14, r14
0x1800264d3  jz      loc_180026E56
0x1800264d9  lea     rsi, [r14-8]
0x1800264dd  mov     rbx, [rsi]
0x1800264e0  lea     rdi, [r14+rbx*8]
0x1800264e4  test    rbx, rbx
0x1800264e7  jz      loc_18002674D
0x1800264ed  sub     rdi, 8
0x1800264f1  mov     rcx, rdi
0x1800264f4  call    ??1?$AutoNewArrayPtr@G@Windows@@QEAA@XZ; Windows::AutoNewArrayPtr<ushort>::~AutoNewArrayPtr<ushort>(void)
0x1800264f9  sub     rbx, 1
0x1800264fd  jnz     short loc_1800264ED
0x1800264ff  jmp     loc_18002674D
0x180026504  cmp     [rbp+rsi*2+101A0h+var_10042], 5Ch ; '\'
0x18002650d  jnz     short loc_180026530
0x18002650f  dec     rsi
0x180026512  mov     [rsp+102A0h+var_10238], rsi
0x180026517  lea     rcx, [rsi+rsi]
0x18002651b  cmp     rcx, 10000h
0x180026522  jnb     loc_180026EAB
0x180026528  mov     [rbp+rcx+101A0h+FileName], bx
0x180026530  mov     [rbp+101A0h+var_10208], rbx
0x180026534  lea     rdx, [rbp+101A0h+var_10208]; unsigned __int16 *
0x180026538  mov     rcx, r12; this
0x18002653b  call    ?QueryStorageReserve@StorageReserveHelper@@YAJPEBGPEAPEAU_QUERY_STORAGE_RESERVE_OUTPUT@@@Z; StorageReserveHelper::QueryStorageReserve(ushort const *,_QUERY_STORAGE_RESERVE_OUTPUT * *)
0x180026540  mov     r15d, eax
0x180026543  test    eax, eax
0x180026545  jns     short loc_180026597
0x180026547  mov     rcx, [rbp+101A8h]; this
0x18002654e  mov     r9d, eax; char *
0x180026551  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180026558  mov     edx, 15Bh; void *
0x18002655d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026562  nop
0x180026563  test    r14, r14
0x180026566  jz      loc_180026E56
0x18002656c  lea     rsi, [r14-8]
0x180026570  mov     rbx, [rsi]
0x180026573  lea     rdi, [r14+rbx*8]
0x180026577  test    rbx, rbx
0x18002657a  jz      loc_18002674D
0x180026580  sub     rdi, 8
0x180026584  mov     rcx, rdi
0x180026587  call    ??1?$AutoNewArrayPtr@G@Windows@@QEAA@XZ; Windows::AutoNewArrayPtr<ushort>::~AutoNewArrayPtr<ushort>(void)
0x18002658c  sub     rbx, 1
0x180026590  jnz     short loc_180026580
0x180026592  jmp     loc_18002674D
0x180026597  mov     rdi, [rbp+101A0h+var_10208]
0x18002659b  test    rdi, rdi
0x18002659e  jnz     short loc_1800265F6
0x1800265a0  mov     rcx, [rbp+101A8h]; this
0x1800265a7  mov     r15d, 8007000Eh
0x1800265ad  mov     r9d, r15d; char *
0x1800265b0  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800265b7  mov     edx, 15Ch; void *
0x1800265bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800265c1  nop
0x1800265c2  test    r14, r14
0x1800265c5  jz      loc_180026E56
0x1800265cb  lea     rsi, [r14-8]
0x1800265cf  mov     rbx, [rsi]
0x1800265d2  lea     rdi, [r14+rbx*8]
0x1800265d6  test    rbx, rbx
0x1800265d9  jz      loc_18002674D
0x1800265df  sub     rdi, 8
0x1800265e3  mov     rcx, rdi
0x1800265e6  call    ??1?$AutoNewArrayPtr@G@Windows@@QEAA@XZ; Windows::AutoNewArrayPtr<ushort>::~AutoNewArrayPtr<ushort>(void)
0x1800265eb  sub     rbx, 1
0x1800265ef  jnz     short loc_1800265DF
0x1800265f1  jmp     loc_18002674D
0x1800265f6  cmp     [rdi+4], ebx
0x1800265f9  jbe     loc_18002669C
0x1800265ff  mov     eax, ebx
0x180026601  lea     rcx, [rax+rax*2]
0x180026605  cmp     [rdi+rcx*8+8], r13d
0x18002660a  jz      short loc_180026615
0x18002660c  inc     ebx
0x18002660e  cmp     ebx, [rdi+4]
0x180026611  jb      short loc_1800265FF
0x180026613  jmp     short loc_18002663B
0x180026615  call    ?Instance@SRProvider@Internal@StorageReserveTelemetry@@KAPEAV123@XZ; StorageReserveTelemetry::Internal::SRProvider::Instance(void)
0x18002661a  xor     ecx, ecx
0x18002661c  cmp     [rax+8], rcx
0x180026620  jz      short loc_18002663B
0x180026622  mov     rax, [rax+8]
0x180026626  mov     edx, [rax]
0x180026628  test    edx, edx
0x18002662a  jz      short loc_18002663B
0x18002662c  call    ?Instance@SRProvider@Internal@StorageReserveTelemetry@@KAPEAV123@XZ; StorageReserveTelemetry::Internal::SRProvider::Instance(void)
0x180026631  mov     r8, rdi; struct _QUERY_STORAGE_RESERVE_OUTPUT *
0x180026634  mov     edx, ebx; unsigned int
0x180026636  call    ?QueryReserveSpaceBeforeDelete_@SRProvider@Internal@StorageReserveTelemetry@@QEAAXKPEAU_QUERY_STORAGE_RESERVE_OUTPUT@@@Z; StorageReserveTelemetry::Internal::SRProvider::QueryReserveSpaceBeforeDelete_(ulong,_QUERY_STORAGE_RESERVE_OUTPUT *)
0x18002663b  mov     rcx, rdi; this
0x18002663e  call    ?FreeOutputBuffer@StorageReserveHelper@@YAJPEAX@Z; StorageReserveHelper::FreeOutputBuffer(void *)
0x180026643  mov     r15d, eax
0x180026646  xor     ebx, ebx
0x180026648  test    eax, eax
0x18002664a  jns     short loc_18002669C
0x18002664c  mov     rcx, [rbp+101A8h]; this
0x180026653  mov     r9d, eax; char *
0x180026656  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002665d  mov     edx, 16Ch; void *
0x180026662  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026667  nop
0x180026668  test    r14, r14
0x18002666b  jz      loc_180026E56
0x180026671  lea     rsi, [r14-8]
0x180026675  mov     rbx, [rsi]
0x180026678  lea     rdi, [r14+rbx*8]
0x18002667c  test    rbx, rbx
0x18002667f  jz      loc_18002674D
0x180026685  sub     rdi, 8
0x180026689  mov     rcx, rdi
0x18002668c  call    ??1?$AutoNewArrayPtr@G@Windows@@QEAA@XZ; Windows::AutoNewArrayPtr<ushort>::~AutoNewArrayPtr<ushort>(void)
0x180026691  sub     rbx, 1
0x180026695  jnz     short loc_180026685
0x180026697  jmp     loc_18002674D
0x18002669c  mov     ecx, 14h; unsigned __int64
0x1800266a1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800266a6  mov     r12, rax
0x1800266a9  mov     [rbp+101A0h+var_101C8], rax
0x1800266ad  mov     dword ptr [rax+4], 67h ; 'g'
0x1800266b4  mov     eax, 3
0x1800266b9  mov     [r12+8], eax
0x1800266be  mov     dword ptr [r12], 1
0x1800266c6  mov     [r12+10h], r13d
0x1800266cb  mov     [rsp+102A0h+hTemplateFile], rbx; hTemplateFile
0x1800266d0  mov     [rsp+102A0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x1800266d8  mov     [rsp+102A0h+dwCreationDisposition], eax; dwCreationDisposition
0x1800266dc  xor     r9d, r9d; lpSecurityAttributes
0x1800266df  mov     r8d, eax; dwShareMode
0x1800266e2  mov     edx, 100h; dwDesiredAccess
0x1800266e7  lea     rcx, [rbp+101A0h+FileName]; lpFileName
0x1800266ee  call    cs:__imp_CreateFileW
0x1800266f4  mov     [rbp+101A0h+hDevice], rax
0x1800266f8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800266fc  jnz     short loc_18002675A
0x1800266fe  mov     rcx, [rbp+101A8h]; this
0x180026705  lea     r8, aOnecoreDrivers_1; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002670c  mov     edx, 189h; void *
0x180026711  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026716  mov     r15d, eax
0x180026719  mov     rcx, r12; void *
0x18002671c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026721  nop
0x180026722  test    r14, r14
0x180026725  jz      loc_180026E56
0x18002672b  lea     rsi, [r14-8]
0x18002672f  mov     rbx, [rsi]
0x180026732  lea     rdi, [r14+rbx*8]
0x180026736  test    rbx, rbx
0x180026739  jz      short loc_18002674D
0x18002673b  sub     rdi, 8
0x18002673f  mov     rcx, rdi
0x180026742  call    ??1?$AutoNewArrayPtr@G@Windows@@QEAA@XZ; Windows::AutoNewArrayPtr<ushort>::~AutoNewArrayPtr<ushort>(void)
0x180026747  sub     rbx, 1
0x18002674b  jnz     short loc_18002673B
0x18002674d  mov     rcx, rsi; Block
0x180026750  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180026755  jmp     loc_180026E56
0x18002675a  mov     [rsp+102A0h+var_10248], rbx
0x18002675f  mov     rdi, rbx
0x180026762  mov     [rbp+101A0h+var_101D0], rbx
0x180026766  mov     [rbp+101A0h+var_101F8], rbx
0x18002676a  mov     r13d, 2000000h
0x180026770  xor     r8d, r8d
0x180026773  mov     dword ptr [rsp+102A0h+var_10260], r8d
0x180026778  mov     [rbp+101A0h+var_10218], r8
0x18002677c  mov     [rbp+101A0h+var_10210], r8
0x180026780  mov     eax, 1
0x180026785  mov     [rsp+102A0h+var_1022C], r13d
0x18002678a  test    eax, eax
0x18002678c  jz      short loc_1800267B4
  ... truncated ...
```
