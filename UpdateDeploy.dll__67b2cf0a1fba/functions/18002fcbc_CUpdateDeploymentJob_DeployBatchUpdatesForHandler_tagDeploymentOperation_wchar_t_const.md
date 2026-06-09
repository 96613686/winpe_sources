# CUpdateDeploymentJob::DeployBatchUpdatesForHandler(tagDeploymentOperation,wchar_t const *)

- ea: `0x18002fcbc`
- end: `0x180030982`
- name: `?DeployBatchUpdatesForHandler@CUpdateDeploymentJob@@AEAAJW4tagDeploymentOperation@@PEB_W@Z`
- size: `3270`
- prototype: `__int64 __fastcall(__int64, unsigned int, const WCHAR *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002fa40`

## callees

- `0x180003180`
- `0x180007b6c`
- `0x1800110fc`
- `0x180011b44`
- `0x180018bb4`
- `0x18002a280`
- `0x18002b4c0`
- `0x18002bd44`
- `0x18002c18c`
- `0x18002c8ec`
- `0x18002fcbc`
- `0x180030988`
- `0x1800369a8`
- `0x180036f20`
- `0x180037d28`
- `0x1800618f8`
- `0x180061960`
- `0x180061d54`
- `0x180062534`
- `0x180062558`
- `0x180068ea0`
- `0x180068f20`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x1800302fc`
- `RPCRT4!UuidFromStringW` at `0x1800302fc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030831`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030891`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030831`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030891`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030844`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800308a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180030844`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800308a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003093e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003093e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800300ff`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800300ff`

## string_xrefs

- `0x18003070f`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18003075a`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18003080f`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x1800308c3`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x1800307ab`: `Deployment job Id %ws : Other install is in progress, MutexId=%ws.`
- `0x1800301e1`: `Deployment job Id %ws : Update %ws being batched for %ws.%d and handler id = %ws`
- `0x1800306f9`: `CUpdateDeploymentJob::DeployBatchUpdatesForHandler`
- `0x1800301a4`: `Uninstalling`
- `0x1800301ad`: `Installing`
- `0x180030192`: `Commiting`

## pseudocode

```c
__int64 __fastcall CUpdateDeploymentJob::DeployBatchUpdatesForHandler(__int64 a1, unsigned int a2, const WCHAR *a3)
{
  const WCHAR *v3; // r14
  signed int v6; // esi
  HANDLE v7; // rbx
  unsigned int v8; // eax
  unsigned int v9; // edi
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned __int64 v12; // r12
  signed int DeploymentToken; // edi
  __int64 v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  unsigned __int64 v16; // rax
  void *v17; // rax
  void *v18; // r14
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  unsigned int v23; // eax
  bool v24; // zf
  unsigned int v25; // eax
  __int64 v26; // r13
  unsigned int v27; // eax
  int v28; // r14d
  __int64 v29; // rdi
  __int64 v30; // r12
  const WCHAR *v31; // rbx
  const WCHAR *v32; // rax
  int v33; // eax
  int v34; // ecx
  unsigned int v35; // r12d
  unsigned int v36; // r14d
  __int64 v37; // r12
  struct tagSusDeployData *v38; // r13
  __int64 v39; // rdi
  void *v40; // rax
  void *v41; // rax
  RPC_STATUS v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  TraceLoggingCorrelationVector *v47; // rcx
  struct tagSusDeployData *v48; // rax
  _OWORD *v49; // rcx
  __int64 v50; // rdx
  _OWORD *v51; // rdx
  _OWORD *v52; // rax
  __int64 v53; // rcx
  unsigned __int64 v54; // r9
  __int64 v55; // rdx
  int v56; // eax
  void *v57; // rdi
  const struct std::nothrow_t *v58; // rdx
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  int cchCount2; // [rsp+28h] [rbp-D8h]
  bool v62; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v63; // [rsp+74h] [rbp-8Ch] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-88h] BYREF
  int v65; // [rsp+80h] [rbp-80h]
  unsigned int v66; // [rsp+84h] [rbp-7Ch]
  __int64 v67; // [rsp+88h] [rbp-78h]
  PCNZWCH lpString1; // [rsp+90h] [rbp-70h]
  _QWORD v69[13]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v70[296]; // [rsp+108h] [rbp+8h] BYREF
  unsigned int v71; // [rsp+230h] [rbp+130h] BYREF
  char v72; // [rsp+234h] [rbp+134h] BYREF
  struct tagSusDeployData *v73; // [rsp+238h] [rbp+138h] BYREF
  void *v74; // [rsp+240h] [rbp+140h] BYREF
  void *v75; // [rsp+248h] [rbp+148h] BYREF
  void *v76; // [rsp+250h] [rbp+150h] BYREF
  int v77; // [rsp+258h] [rbp+158h] BYREF
  int v78; // [rsp+25Ch] [rbp+15Ch] BYREF
  int v79; // [rsp+260h] [rbp+160h] BYREF
  unsigned int v80; // [rsp+264h] [rbp+164h] BYREF
  void *v81; // [rsp+268h] [rbp+168h] BYREF
  UUID Uuid; // [rsp+270h] [rbp+170h] BYREF
  int v83; // [rsp+280h] [rbp+180h]
  _QWORD v84[84]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t Source[72]; // [rsp+530h] [rbp+430h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+608h] [rbp+508h]

  v3 = a3;
  lpString1 = a3;
  v6 = 0;
  v72 = 0;
  memset(v84, 0, sizeof(v84));
  v81 = 0;
  v71 = 0;
  v7 = 0;
  hObject = 0;
  v63 = 0;
  v76 = 0;
  v8 = *(_DWORD *)(a1 + 688);
  v80 = v8;
  v67 = *(_QWORD *)(a1 + 712);
  v75 = 0;
  v74 = 0;
  v9 = 0;
  if ( v8 )
  {
    v10 = *(_QWORD *)(a1 + 696);
    v11 = v8;
    do
    {
      v9 += *(_DWORD *)(*(_QWORD *)v10 + 544LL);
      v10 += 8;
      --v11;
    }
    while ( v11 );
  }
  v69[12] = 0;
  v79 = 0;
  v62 = 0;
  v77 = 0;
  v78 = 0;
  memset(v69, 0, 0x58u);
  v69[0] = &v71;
  v69[1] = &v79;
  v69[2] = a1;
  v69[3] = &v81;
  v69[4] = &v77;
  v69[5] = &v75;
  v69[6] = &v78;
  v69[7] = &v74;
  v69[8] = &v72;
  v69[9] = &v80;
  LOBYTE(v69[10]) = 1;
  v12 = v9;
  DeploymentToken = WuSmartPtr::XPtrBaseWithArrayAllocation<tagDSFile *,WuSmartPtr::Policies::STArrayZeroAllocPolicy<tagDSFile *>>::ReleaseAndAllocArray(
                      &v75,
                      v9);
  if ( DeploymentToken < 0 )
  {
    v14 = 3408;
    goto LABEL_128;
  }
  DeploymentToken = WuSmartPtr::XPtrBaseWithArrayAllocation<tagDSFile *,WuSmartPtr::Policies::STArrayZeroAllocPolicy<tagDSFile *>>::ReleaseAndAllocArray(
                      &v74,
                      v12);
  if ( DeploymentToken < 0 )
  {
    v14 = 3409;
    goto LABEL_128;
  }
  if ( v81 )
  {
    operator delete(v81, v15);
    v81 = 0;
  }
  if ( v12 )
  {
    v16 = 296 * v12;
    if ( !is_mul_ok(v12, 0x128u) )
      v16 = -1;
    v17 = operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
    v18 = v17;
    if ( v17 )
      memset(v17, 0, 296 * v12);
    v81 = v18;
    DeploymentToken = v18 == 0 ? 0x8007000E : 0;
    if ( !v18 )
    {
      v14 = 3410;
      goto LABEL_128;
    }
    v3 = lpString1;
  }
  if ( a2 == 4 && !(unsigned __int8)CUpdateDeploymentJob::DoesHandlerSupportDeploymentOperation(a1, 4, v3) )
  {
    DeploymentToken = -2145124281;
    v14 = 3416;
    goto LABEL_128;
  }
  DeploymentToken = CUpdateDeploymentJob::GetDeploymentToken(
                      (CUpdateDeploymentJob *)a1,
                      *(_QWORD *)(a1 + 808),
                      &hObject,
                      (int *)&v63);
  if ( DeploymentToken < 0 )
  {
    v14 = 3420;
LABEL_23:
    v7 = hObject;
    goto LABEL_128;
  }
  HIDWORD(v84[2]) = *(_DWORD *)(a1 + 792);
  v84[0] = *(_QWORD *)(a1 + 816);
  if ( (v84[2] & 0x2000000000LL) != 0 )
  {
    DeploymentToken = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)(a1 + 704) + 112LL))(
                        *(_QWORD *)(a1 + 704),
                        &v84[2]);
    if ( DeploymentToken < 0 )
    {
      v14 = 3428;
      goto LABEL_23;
    }
  }
  else
  {
    LODWORD(v84[2]) = -1;
  }
  DeploymentToken = CUpdateDeploymentJob::DoesOperationRequirePayload(a1, a2, v3, &v79);
  if ( DeploymentToken < 0 )
  {
    v14 = 3435;
    goto LABEL_23;
  }
  if ( v76 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v76 + 16LL))(v76);
    v76 = 0;
  }
  v19 = *(_DWORD *)(a1 + 824);
  if ( v19 )
  {
    v20 = v19 - 1;
    if ( v20 )
    {
      v21 = v20 - 1;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( !v22 )
        {
          v23 = 3;
          goto LABEL_42;
        }
        if ( v22 == 1 )
        {
          v23 = 4;
          goto LABEL_42;
        }
      }
      v23 = 2;
    }
    else
    {
      v23 = 1;
    }
  }
  else
  {
    v23 = 0;
  }
LABEL_42:
  v7 = hObject;
  DeploymentToken = CUHHandlerManager::GetRemoteDeploymentHandler(
                      (CUHHandlerManager *)(a1 + 48),
                      v3,
                      (__int64)hObject,
                      v63,
                      v23,
                      cchCount2,
                      &v76);
  if ( DeploymentToken < 0 )
  {
    v14 = 3441;
    goto LABEL_128;
  }
  v72 = 1;
  if ( v7 || (v24 = (*(_BYTE *)(a1 + 792) & 0x20) == 0, v65 = 0, !v24) )
    v65 = 1;
  v25 = 0;
  v63 = 0;
  if ( v80 )
  {
    while ( 1 )
    {
      v26 = v25;
      v73 = (struct tagSusDeployData *)v25;
      v27 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 696) + 8LL * v25) + 544LL);
      v66 = v27;
      v28 = 0;
      if ( v27 )
      {
        v29 = 0;
        v30 = v27;
        v31 = lpString1;
        do
        {
          v32 = *(const WCHAR **)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 696) + 8 * v26) + 552LL) + v29)
                                + 80LL);
          if ( v31 == v32 )
          {
            v33 = 2;
          }
          else if ( v31 )
          {
            if ( v32 )
              v33 = CompareStringW(0x7Fu, 1u, v31, -1, v32, -1);
            else
              v33 = 3;
          }
          else
          {
            v33 = 1;
          }
          v34 = v28 + 1;
          if ( v33 != 2 )
            v34 = v28;
          v28 = v34;
          v29 += 8;
          --v30;
        }
        while ( v30 );
        v7 = hObject;
        if ( v34 )
        {
          v35 = v63;
          DeploymentToken = CUpdateDeploymentJob::TryToCreateDeploymentInProgressMutex(
                              (CUpdateDeploymentJob *)a1,
                              v63,
                              &v62);
          if ( DeploymentToken < 0 )
          {
            v14 = 3476;
            goto LABEL_128;
          }
          if ( v62 )
          {
            Trace::GuidToString::GuidToString(Source, (const struct _GUID *)(a1 + 16));
            WUTrace(0, 0, 0x1000000, 3);
            DeploymentToken = -2145124330;
            goto LABEL_129;
          }
          CUpdateDeploymentJob::OnUpdateStarted((CUpdateDeploymentJob *)a1, v35);
          Trace::GuidToString::GuidToString(Source, (const struct _GUID *)(a1 + 16));
          LODWORD(lpString2) = 0;
          WUTrace(0, 0, 0x1000000, 4);
          if ( v6 >= 0 )
          {
            if ( v66 == v28 )
            {
              v36 = 0;
              v37 = 0;
              v38 = v73;
              while ( 1 )
              {
                v73 = 0;
                memset(Source, 0, 0x81u);
                v39 = *(_QWORD *)(v37 + *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 696) + 8LL * (_QWORD)v38) + 552LL));
                v40 = operator new(0x288u, (const struct std::nothrow_t *)&std::nothrow);
                *((_QWORD *)v75 + v71) = v40;
                if ( !*((_QWORD *)v75 + v71) )
                  break;
                ++v77;
                v41 = operator new(0x288u, (const struct std::nothrow_t *)&std::nothrow);
                *((_QWORD *)v74 + v71) = v41;
                if ( !*((_QWORD *)v74 + v71) )
                {
                  v55 = 3529;
                  goto LABEL_116;
                }
                ++v78;
                Uuid = 0;
                v83 = 0;
                v42 = UuidFromStringW(*(RPC_WSTR *)(v39 + 16), &Uuid);
                v6 = v42;
                if ( v42 >= 1 )
                  v6 = (unsigned __int16)v42 | 0x80010000;
                if ( v6 < 0 )
                {
                  v55 = 3535;
                  goto LABEL_117;
                }
                v83 = *(_DWORD *)(v39 + 24);
                switch ( *(_DWORD *)(v39 + 56) )
                {
                  case 1:
                    v43 = 1;
                    break;
                  case 2:
                    v43 = 2;
                    break;
                  case 4:
                    v43 = 4;
                    break;
                  case 8:
                    v43 = 8;
                    break;
                  default:
                    v43 = 0;
                    break;
                }
                LODWORD(lpString2) = v43;
                v6 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)v67 + 24LL))(
                       v67,
                       2,
                       *(unsigned int *)(a1 + 800),
                       3631);
                if ( v6 < 0 )
                {
                  v55 = 3549;
                  goto LABEL_117;
                }
                switch ( *(_DWORD *)(v39 + 56) )
                {
                  case 1:
                    v44 = 1;
                    break;
                  case 2:
                    v44 = 2;
                    break;
                  case 4:
                    v44 = 4;
                    break;
                  case 8:
                    v44 = 8;
                    break;
                  default:
                    v44 = 0;
                    break;
                }
                LODWORD(lpString2) = v44;
                v45 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v67 + 24LL))(
                        v67,
                        3,
                        *(unsigned int *)(a1 + 800));
                v6 = v45;
                if ( v45 < 0 )
                {
                  v54 = (unsigned int)v45;
                  v55 = 3562;
                  goto LABEL_118;
                }
                if ( v73 )
                {
                  operator delete(v73, (const struct std::nothrow_t *)0x128);
                  v73 = 0;
                }
                v46 = CUpdateDeploymentJob::PrepareDeployData(
                        (CUpdateDeploymentJob *)a1,
                        (const struct FullDeployableUpdate *)v39,
                        *(struct IUpdateDeploymentDataProvider **)(a1 + 712),
                        (struct tagDSUpdateMetadata *)(*((_QWORD *)v75 + v71) + 8LL),
                        (const struct tagDSDeployment *)(*((_QWORD *)v74 + v71) + 8LL),
                        v79,
                        &v73);
                v6 = v46;
                if ( v46 < 0 )
                {
                  *(_DWORD *)(v39 + 92) = v46;
                  if ( v73 )
                    operator delete(v73, (const struct std::nothrow_t *)0x128);
                  goto LABEL_107;
                }
                *(_DWORD *)(v39 + 300) = v65;
                v47 = *(TraceLoggingCorrelationVector **)(*(_QWORD *)(*(_QWORD *)(a1 + 696) + 8LL * (_QWORD)v38) + 584LL);
                LOBYTE(Source[0]) = 0;
                if ( v47 )
                  TraceLoggingCorrelationVector::Increment(v47, (char *)Source);
                strcpy_s((char *)v73 + 112, 0x81u, (const char *)Source);
                v48 = v73;
                v49 = v70;
                v50 = 2;
                do
                {
                  *v49 = *(_OWORD *)v48;
                  v49[1] = *((_OWORD *)v48 + 1);
                  v49[2] = *((_OWORD *)v48 + 2);
                  v49[3] = *((_OWORD *)v48 + 3);
                  v49[4] = *((_OWORD *)v48 + 4);
                  v49[5] = *((_OWORD *)v48 + 5);
                  v49[6] = *((_OWORD *)v48 + 6);
                  v49 += 8;
                  *(v49 - 1) = *((_OWORD *)v48 + 7);
                  v48 = (struct tagSusDeployData *)((char *)v48 + 128);
                  --v50;
                }
                while ( v50 );
                *v49 = *(_OWORD *)v48;
                v49[1] = *((_OWORD *)v48 + 1);
                *((_QWORD *)v49 + 4) = *((_QWORD *)v48 + 4);
                v51 = (char *)v81 + 296 * v71;
                v52 = v70;
                v53 = 2;
                do
                {
                  *v51 = *v52;
                  v51[1] = v52[1];
                  v51[2] = v52[2];
                  v51[3] = v52[3];
                  v51[4] = v52[4];
                  v51[5] = v52[5];
                  v51[6] = v52[6];
                  v51 += 8;
                  *(v51 - 1) = v52[7];
                  v52 += 8;
                  --v53;
                }
                while ( v53 );
                *v51 = *v52;
                v51[1] = v52[1];
                *((_QWORD *)v51 + 4) = *((_QWORD *)v52 + 4);
                ++v71;
                if ( v73 )
                  operator delete(v73, (const struct std::nothrow_t *)0x128);
                ++v36;
                v37 += 8;
                if ( v36 >= v66 )
                  goto LABEL_107;
              }
              v55 = 3525;
LABEL_116:
              v6 = -2147024882;
LABEL_117:
              v54 = (unsigned int)v6;
LABEL_118:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v55,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
                (const char *)v54,
                (int)lpString2);
              if ( v73 )
                operator delete(v73, (const struct std::nothrow_t *)0x128);
LABEL_110:
              DeploymentToken = v6;
              goto LABEL_129;
            }
            v6 = -2145124297;
          }
        }
      }
LABEL_107:
      v25 = v63 + 1;
      v63 = v25;
      if ( v25 >= v80 )
      {
        if ( v6 >= 0 )
          break;
        Trace::GuidToString::GuidToString(Source, (const struct _GUID *)(a1 + 16));
        WUTrace("CUpdateDeploymentJob::DeployBatchUpdatesForHandler", 3598, 0x1000000, 3);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE10,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
          (const char *)(unsigned int)v6,
          v6);
        goto LABEL_110;
      }
    }
  }
  v56 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v76 + 88LL))(v76, *(unsigned int *)(a1 + 824));
  if ( v56 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xE17,
      (int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)v56);
  v57 = v76;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 888));
  *(_QWORD *)(a1 + 840) = v57;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 888));
  lpString2 = (PCNZWCH)((a1 + 8) & -(__int64)(a1 != 0));
  DeploymentToken = (*(__int64 (__fastcall **)(void *, _QWORD *, _QWORD, void *))(*(_QWORD *)v76 + 56LL))(
                      v76,
                      v84,
                      v71,
                      v81);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 888));
  *(_QWORD *)(a1 + 840) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 888));
  if ( DeploymentToken == -2145124341 || DeploymentToken == -2145116152 )
  {
    v14 = 3627;
LABEL_128:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)(unsigned int)DeploymentToken,
      (int)lpString2);
  }
  else
  {
    DeploymentToken = 0;
  }
LABEL_129:
  LOBYTE(v69[10]) = 0;
  lambda_d2a8391457cfcd42b796fa4c93220b16_::operator()(v69);
  if ( v74 )
  {
    operator delete(v74, v58);
    v74 = 0;
  }
  if ( v75 )
  {
    operator delete(v75, v58);
    v75 = 0;
  }
  if ( v76 )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)v76 + 16LL))(v76);
    v76 = 0;
  }
  if ( v7 )
    CloseHandle(v7);
  if ( v81 )
    operator delete(v81, v58);
  return (unsigned int)DeploymentToken;
}

```

## disassembly

```asm
0x18002fcbc  mov     [rsp-8+arg_18], rbx
0x18002fcc1  push    rbp
0x18002fcc2  push    rsi
0x18002fcc3  push    rdi
0x18002fcc4  push    r12
0x18002fcc6  push    r13
0x18002fcc8  push    r14
0x18002fcca  push    r15
0x18002fccc  lea     rbp, [rsp-4D0h]
0x18002fcd4  sub     rsp, 5D0h
0x18002fcdb  mov     rax, cs:__security_cookie
0x18002fce2  xor     rax, rsp
0x18002fce5  mov     [rbp+500h+var_40], rax
0x18002fcec  mov     r14, r8
0x18002fcef  mov     [rbp+500h+lpString1], r8
0x18002fcf3  mov     r13d, edx
0x18002fcf6  mov     r15, rcx
0x18002fcf9  xor     r12d, r12d
0x18002fcfc  mov     esi, r12d
0x18002fcff  mov     [rbp+500h+var_3CC], r12b
0x18002fd06  xor     edx, edx; Val
0x18002fd08  mov     r8d, 2A0h; Size
0x18002fd0e  lea     rcx, [rbp+500h+var_370]; void *
0x18002fd15  call    memset
0x18002fd1a  mov     [rbp+500h+var_398], r12
0x18002fd21  mov     [rbp+500h+var_3D0], r12d
0x18002fd28  mov     ebx, r12d
0x18002fd2b  mov     [rsp+600h+hObject], rbx
0x18002fd30  mov     [rsp+600h+var_58C], r12d
0x18002fd35  mov     [rbp+500h+var_3B0], r12
0x18002fd3c  mov     eax, [r15+2B0h]
0x18002fd43  mov     [rbp+500h+var_39C], eax
0x18002fd49  mov     rcx, [r15+2C8h]
0x18002fd50  mov     [rbp+500h+var_578], rcx
0x18002fd54  mov     [rbp+500h+var_3B8], r12
0x18002fd5b  mov     [rbp+500h+var_3C0], r12
0x18002fd62  mov     edi, r12d
0x18002fd65  test    eax, eax
0x18002fd67  jz      short loc_18002FD85
0x18002fd69  mov     rcx, [r15+2B8h]
0x18002fd70  mov     edx, eax
0x18002fd72  mov     rax, [rcx]
0x18002fd75  add     edi, [rax+220h]
0x18002fd7b  lea     rcx, [rcx+8]
0x18002fd7f  sub     rdx, 1
0x18002fd83  jnz     short loc_18002FD72
0x18002fd85  mov     [rbp+500h+var_500], r12
0x18002fd89  mov     [rbp+500h+var_3A0], r12d
0x18002fd90  mov     [rsp+600h+var_590], r12b
0x18002fd95  mov     [rbp+500h+var_3A8], r12d
0x18002fd9c  mov     [rbp+500h+var_3A4], r12d
0x18002fda3  xor     edx, edx; Val
0x18002fda5  lea     r8d, [rdx+58h]; Size
0x18002fda9  lea     rcx, [rbp+500h+var_560]; void *
0x18002fdad  call    memset
0x18002fdb2  lea     rax, [rbp+500h+var_3D0]
0x18002fdb9  mov     [rbp+500h+var_560], rax
0x18002fdbd  lea     rax, [rbp+500h+var_3A0]
0x18002fdc4  mov     [rbp+500h+var_558], rax
0x18002fdc8  mov     [rbp+500h+var_550], r15
0x18002fdcc  lea     rax, [rbp+500h+var_398]
0x18002fdd3  mov     [rbp+500h+var_548], rax
0x18002fdd7  lea     rax, [rbp+500h+var_3A8]
0x18002fdde  mov     [rbp+500h+var_540], rax
0x18002fde2  lea     rax, [rbp+500h+var_3B8]
0x18002fde9  mov     [rbp+500h+var_538], rax
0x18002fded  lea     rax, [rbp+500h+var_3A4]
0x18002fdf4  mov     [rbp+500h+var_530], rax
0x18002fdf8  lea     rax, [rbp+500h+var_3C0]
0x18002fdff  mov     [rbp+500h+var_528], rax
0x18002fe03  lea     rax, [rbp+500h+var_3CC]
0x18002fe0a  mov     [rbp+500h+var_520], rax
0x18002fe0e  lea     rax, [rbp+500h+var_39C]
0x18002fe15  mov     [rbp+500h+var_518], rax
0x18002fe19  mov     [rbp+500h+var_510], 1
0x18002fe1d  mov     r12d, edi
0x18002fe20  mov     edx, edi
0x18002fe22  lea     rcx, [rbp+500h+var_3B8]
0x18002fe29  call    ?ReleaseAndAllocArray@?$XPtrBaseWithArrayAllocation@PEAUtagDSFile@@U?$STArrayZeroAllocPolicy@PEAUtagDSFile@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJ_K@Z; WuSmartPtr::XPtrBaseWithArrayAllocation<tagDSFile *,WuSmartPtr::Policies::STArrayZeroAllocPolicy<tagDSFile *>>::ReleaseAndAllocArray(unsigned __int64)
0x18002fe2e  mov     edi, eax
0x18002fe30  test    eax, eax
0x18002fe32  jns     short loc_18002FE3E
0x18002fe34  mov     edx, 0D50h
0x18002fe39  jmp     loc_1800308C0
0x18002fe3e  mov     rdx, r12
0x18002fe41  lea     rcx, [rbp+500h+var_3C0]
0x18002fe48  call    ?ReleaseAndAllocArray@?$XPtrBaseWithArrayAllocation@PEAUtagDSFile@@U?$STArrayZeroAllocPolicy@PEAUtagDSFile@@@Policies@WuSmartPtr@@@WuSmartPtr@@QEAAJ_K@Z; WuSmartPtr::XPtrBaseWithArrayAllocation<tagDSFile *,WuSmartPtr::Policies::STArrayZeroAllocPolicy<tagDSFile *>>::ReleaseAndAllocArray(unsigned __int64)
0x18002fe4d  mov     edi, eax
0x18002fe4f  test    eax, eax
0x18002fe51  jns     short loc_18002FE5D
0x18002fe53  mov     edx, 0D51h
0x18002fe58  jmp     loc_1800308C0
0x18002fe5d  mov     rcx, [rbp+500h+var_398]; void *
0x18002fe64  test    rcx, rcx
0x18002fe67  jz      short loc_18002FE79
0x18002fe69  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002fe6e  mov     [rbp+500h+var_398], 0
0x18002fe79  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002fe7d  test    r12, r12
0x18002fe80  jz      short loc_18002FEE0
0x18002fe82  mov     eax, 128h
0x18002fe87  mul     r12
0x18002fe8a  cmovb   rax, rcx
0x18002fe8e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002fe95  mov     rcx, rax; unsigned __int64
0x18002fe98  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002fe9d  mov     r14, rax
0x18002fea0  test    rax, rax
0x18002fea3  jz      short loc_18002FEB6
0x18002fea5  imul    r8, r12, 128h; Size
0x18002feac  xor     edx, edx; Val
0x18002feae  mov     rcx, rax; void *
0x18002feb1  call    memset
0x18002feb6  mov     [rbp+500h+var_398], r14
0x18002febd  mov     rcx, r14
0x18002fec0  neg     rcx
0x18002fec3  sbb     edi, edi
0x18002fec5  not     edi
0x18002fec7  and     edi, 8007000Eh
0x18002fecd  test    r14, r14
0x18002fed0  jnz     short loc_18002FEDC
0x18002fed2  mov     edx, 0D52h
0x18002fed7  jmp     loc_1800308C0
0x18002fedc  mov     r14, [rbp+500h+lpString1]
0x18002fee0  mov     r12d, 4
0x18002fee6  cmp     r13d, r12d
0x18002fee9  jnz     short loc_18002FF0C
0x18002feeb  mov     r8, r14
0x18002feee  mov     edx, r12d
0x18002fef1  mov     rcx, r15
0x18002fef4  call    ?DoesHandlerSupportDeploymentOperation@CUpdateDeploymentJob@@AEAA_NW4tagDeploymentOperation@@PEB_W@Z; CUpdateDeploymentJob::DoesHandlerSupportDeploymentOperation(tagDeploymentOperation,wchar_t const *)
0x18002fef9  test    al, al
0x18002fefb  jnz     short loc_18002FF0C
0x18002fefd  mov     edi, 80240047h
0x18002ff02  mov     edx, 0D58h
0x18002ff07  jmp     loc_1800308C0
0x18002ff0c  lea     r9, [rsp+600h+var_58C]; int *
0x18002ff11  lea     r8, [rsp+600h+hObject]; void **
0x18002ff16  mov     rdx, [r15+328h]; unsigned __int64
0x18002ff1d  mov     rcx, r15; this
0x18002ff20  call    ?GetDeploymentToken@CUpdateDeploymentJob@@AEBAJ_KPEAPEAXPEAH@Z; CUpdateDeploymentJob::GetDeploymentToken(unsigned __int64,void * *,int *)
0x18002ff25  mov     edi, eax
0x18002ff27  test    eax, eax
0x18002ff29  jns     short loc_18002FF3A
0x18002ff2b  mov     edx, 0D5Ch
0x18002ff30  mov     rbx, [rsp+600h+hObject]
0x18002ff35  jmp     loc_1800308C0
0x18002ff3a  mov     ecx, [r15+318h]
0x18002ff41  mov     [rbp+500h+var_35C], ecx
0x18002ff47  mov     rax, [r15+330h]
0x18002ff4e  mov     [rbp+500h+var_370], rax
0x18002ff55  test    cl, 20h
0x18002ff58  jz      short loc_18002FF81
0x18002ff5a  mov     rcx, [r15+2C0h]
0x18002ff61  mov     rax, [rcx]
0x18002ff64  lea     rdx, [rbp+500h+var_360]
0x18002ff6b  mov     rax, [rax+70h]
0x18002ff6f  call    _guard_dispatch_icall
0x18002ff74  mov     edi, eax
0x18002ff76  test    eax, eax
0x18002ff78  jns     short loc_18002FF8B
0x18002ff7a  mov     edx, 0D64h
0x18002ff7f  jmp     short loc_18002FF30
0x18002ff81  mov     [rbp+500h+var_360], 0FFFFFFFFh
0x18002ff8b  lea     r9, [rbp+500h+var_3A0]
0x18002ff92  mov     r8, r14
0x18002ff95  mov     edx, r13d
0x18002ff98  mov     rcx, r15
0x18002ff9b  call    ?DoesOperationRequirePayload@CUpdateDeploymentJob@@AEAAJW4tagDeploymentOperation@@PEB_WPEAH@Z; CUpdateDeploymentJob::DoesOperationRequirePayload(tagDeploymentOperation,wchar_t const *,int *)
0x18002ffa0  mov     edi, eax
0x18002ffa2  test    eax, eax
0x18002ffa4  jns     short loc_18002FFAD
0x18002ffa6  mov     edx, 0D6Bh
0x18002ffab  jmp     short loc_18002FF30
0x18002ffad  mov     rcx, [rbp+500h+var_3B0]
0x18002ffb4  test    rcx, rcx
0x18002ffb7  jz      short loc_18002FFD0
0x18002ffb9  mov     rax, [rcx]
0x18002ffbc  mov     rax, [rax+10h]
0x18002ffc0  call    _guard_dispatch_icall
0x18002ffc5  mov     [rbp+500h+var_3B0], 0
0x18002ffd0  mov     ecx, [r15+338h]
0x18002ffd7  test    ecx, ecx
0x18002ffd9  jz      short loc_180030009
0x18002ffdb  sub     ecx, 1
0x18002ffde  jz      short loc_180030002
0x18002ffe0  sub     ecx, 1
0x18002ffe3  jz      short loc_18002FFFB
0x18002ffe5  sub     ecx, 1
0x18002ffe8  jz      short loc_18002FFF4
0x18002ffea  cmp     ecx, 1
0x18002ffed  jnz     short loc_18002FFFB
0x18002ffef  mov     eax, r12d
0x18002fff2  jmp     short loc_18003000B
0x18002fff4  mov     eax, 3
0x18002fff9  jmp     short loc_18003000B
0x18002fffb  mov     eax, 2
0x180030000  jmp     short loc_18003000B
0x180030002  mov     eax, 1
0x180030007  jmp     short loc_18003000B
0x180030009  xor     eax, eax
0x18003000b  lea     rcx, [rbp+500h+var_3B0]
0x180030012  mov     [rsp+600h+var_5D0], rcx
0x180030017  mov     dword ptr [rsp+600h+lpString2], eax; int
0x18003001b  mov     r9d, [rsp+600h+var_58C]
0x180030020  mov     rbx, [rsp+600h+hObject]
0x180030025  mov     r8, rbx
0x180030028  mov     rdx, r14
0x18003002b  lea     rcx, [r15+30h]
0x18003002f  call    ?GetRemoteDeploymentHandler@CUHHandlerManager@@QEAAJPEB_WPEAXHW4tagDeploymentHandlerPriority@@AEBU_GUID@@PEAPEAX@Z; CUHHandlerManager::GetRemoteDeploymentHandler(wchar_t const *,void *,int,tagDeploymentHandlerPriority,_GUID const &,void * *)
0x180030034  mov     edi, eax
0x180030036  test    eax, eax
0x180030038  jns     short loc_180030044
0x18003003a  mov     edx, 0D71h
0x18003003f  jmp     loc_1800308C0
0x180030044  mov     [rbp+500h+var_3CC], 1
0x18003004b  test    rbx, rbx
0x18003004e  jnz     short loc_18003005D
0x180030050  test    byte ptr [r15+318h], 20h
0x180030058  mov     [rbp+500h+var_580], ebx
0x18003005b  jz      short loc_180030064
0x18003005d  mov     [rbp+500h+var_580], 1
0x180030064  xor     eax, eax
0x180030066  mov     [rsp+600h+var_58C], eax
0x18003006a  cmp     [rbp+500h+var_39C], eax
0x180030070  jbe     loc_1800307E7
0x180030076  mov     r13d, eax
0x180030079  mov     [rbp+500h+var_3C8], r13
0x180030080  mov     rax, [r15+2B8h]
0x180030087  mov     rcx, [rax+r13*8]
0x18003008b  mov     eax, [rcx+220h]
0x180030091  mov     [rbp+500h+var_57C], eax
0x180030094  xor     r14d, r14d
0x180030097  test    eax, eax
0x180030099  jz      loc_1800306A5
0x18003009f  xor     edi, edi
0x1800300a1  mov     r12d, eax
0x1800300a4  mov     rbx, [rbp+500h+lpString1]
0x1800300a8  mov     rax, [r15+2B8h]
0x1800300af  mov     rcx, [rax+r13*8]
0x1800300b3  mov     rax, [rcx+228h]
0x1800300ba  mov     rcx, [rax+rdi]
0x1800300be  mov     rax, [rcx+50h]
0x1800300c2  cmp     rbx, rax
0x1800300c5  jnz     short loc_1800300CE
0x1800300c7  mov     eax, 2
0x1800300cc  jmp     short loc_180030105
0x1800300ce  test    rbx, rbx
0x1800300d1  jnz     short loc_1800300D8
0x1800300d3  lea     eax, [rbx+1]
0x1800300d6  jmp     short loc_180030105
0x1800300d8  test    rax, rax
0x1800300db  jnz     short loc_1800300E4
0x1800300dd  mov     eax, 3
0x1800300e2  jmp     short loc_180030105
0x1800300e4  mov     [rsp+600h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800300ec  mov     [rsp+600h+lpString2], rax; lpString2
0x1800300f1  or      r9d, 0FFFFFFFFh; cchCount1
0x1800300f5  mov     r8, rbx; lpString1
0x1800300f8  lea     edx, [r9+2]; dwCmpFlags
0x1800300fc  lea     ecx, [rdx+7Eh]; Locale
0x1800300ff  call    cs:__imp_CompareStringW
0x180030105  lea     ecx, [r14+1]
0x180030109  cmp     eax, 2
0x18003010c  cmovnz  ecx, r14d
0x180030110  mov     r14d, ecx
0x180030113  add     rdi, 8
0x180030117  sub     r12, 1
0x18003011b  jnz     short loc_1800300A8
0x18003011d  mov     rbx, [rsp+600h+hObject]
0x180030122  test    ecx, ecx
0x180030124  jz      loc_1800306A5
0x18003012a  lea     r8, [rsp+600h+var_590]; bool *
0x18003012f  mov     r12d, [rsp+600h+var_58C]
0x180030134  mov     edx, r12d; unsigned int
0x180030137  mov     rcx, r15; this
0x18003013a  call    ?TryToCreateDeploymentInProgressMutex@CUpdateDeploymentJob@@AEAAJKPEA_N@Z; CUpdateDeploymentJob::TryToCreateDeploymentInProgressMutex(ulong,bool *)
0x18003013f  mov     edi, eax
0x180030141  test    eax, eax
0x180030143  js      loc_1800307DD
0x180030149  cmp     [rsp+600h+var_590], 0
0x18003014e  jnz     loc_18003077F
0x180030154  mov     edx, r12d; unsigned int
0x180030157  mov     rcx, r15; this
0x18003015a  call    ?OnUpdateStarted@CUpdateDeploymentJob@@AEAAJK@Z; CUpdateDeploymentJob::OnUpdateStarted(ulong)
0x18003015f  mov     rax, [r15+2B8h]
0x180030166  mov     rcx, [rax+r13*8]
0x18003016a  mov     r12d, [rcx+18h]
0x18003016e  mov     r13, [rcx+10h]
0x180030172  mov     edx, [rcx+38h]
0x180030175  sub     edx, 1
0x180030178  jz      short loc_1800301AD
0x18003017a  sub     edx, 1
0x18003017d  jz      short loc_1800301A4
0x18003017f  sub     edx, 2
0x180030182  jz      short loc_18003019B
0x180030184  cmp     edx, 4
0x180030187  jz      short loc_180030192
0x180030189  lea     rdi, aUnknown_0; "Unknown"
0x180030190  jmp     short loc_1800301B4
  ... truncated ...
```
