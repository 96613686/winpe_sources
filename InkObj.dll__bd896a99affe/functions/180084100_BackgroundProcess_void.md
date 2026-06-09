# BackgroundProcess(void *)

- ea: `0x180084100`
- end: `0x180084d23`
- name: `?BackgroundProcess@@YAIPEAX@Z`
- size: `3107`
- prototype: `unsigned int __stdcall(void *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x180079b1c`
- `0x180079bdc`
- `0x180083d9c`
- `0x180084100`
- `0x1800851f8`
- `0x180085568`
- `0x180085624`
- `0x1800859b8`
- `0x180085a08`
- `0x180089488`
- `0x1800898cc`
- `0x18010c010`

## import_xrefs

- `msvcrt!_endthreadex` at `0x180084140`
- `msvcrt!_endthreadex` at `0x180084cf7`
- `msvcrt!_endthreadex` at `0x180084140`
- `msvcrt!_endthreadex` at `0x180084cf7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008419d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008419d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180084c8f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180084c8f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800844d9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800844d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800844ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800844ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084c98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180084c98`
- `OLEAUT32!__imp_VariantInit` at `0x180084ad7`
- `OLEAUT32!__imp_VariantInit` at `0x180084ad7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180084996`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180084996`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180084924`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180084924`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180084975`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180084975`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180084904`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180084904`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180084cef`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180084cef`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180084132`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180084132`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084ca5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084ce9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084ca5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180084ce9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BackgroundProcess(HANDLE *a1)
{
  unsigned int v2; // r12d
  unsigned int v3; // r14d
  HANDLE *v4; // rbx
  void *v5; // rdx
  HANDLE v6; // rcx
  int v7; // r13d
  struct tagOpLink *v8; // r15
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // eax
  int v15; // ebx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ebx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // ebx
  _DWORD *v26; // rax
  __int64 v27; // rax
  int v28; // ebx
  __int64 v29; // r8
  unsigned int *v30; // rax
  __int64 v31; // rdx
  unsigned int v32; // ebx
  int v33; // ebx
  int v34; // ebx
  __int64 v35; // r13
  HRESULT v36; // ebx
  SAFEARRAY *Vector; // rax
  SAFEARRAY *v38; // r13
  __int64 v39; // rax
  int v40; // ecx
  int v41; // ecx
  int v42; // ecx
  int v43; // ecx
  int v44; // ebx
  __int64 v45; // rbx
  int v46; // r13d
  int v47; // ebx
  int v48; // ebx
  int v49; // ebx
  int v50; // eax
  struct tagOpLink *pv; // [rsp+30h] [rbp-1D8h] BYREF
  HANDLE *v53; // [rsp+38h] [rbp-1D0h]
  int v54; // [rsp+40h] [rbp-1C8h]
  __int64 v55; // [rsp+48h] [rbp-1C0h]
  int v56; // [rsp+50h] [rbp-1B8h]
  VARIANTARG ppvData; // [rsp+58h] [rbp-1B0h] BYREF
  HANDLE *v58; // [rsp+70h] [rbp-198h]
  VARIANTARG v59; // [rsp+80h] [rbp-188h] BYREF
  __int128 v60; // [rsp+A0h] [rbp-168h] BYREF
  _BYTE v61[32]; // [rsp+B0h] [rbp-158h] BYREF
  __int64 (__fastcall *v62)(HANDLE); // [rsp+D0h] [rbp-138h]
  int (__fastcall *v63)(HANDLE, _QWORD, _QWORD, _QWORD, _QWORD); // [rsp+E8h] [rbp-120h]
  int (__fastcall *v64)(HANDLE, __int64, _QWORD); // [rsp+F8h] [rbp-110h]
  int (__fastcall *v65)(HANDLE, _QWORD); // [rsp+110h] [rbp-F8h]
  __int64 (__fastcall *v66)(HANDLE); // [rsp+118h] [rbp-F0h]
  int (__fastcall *v67)(HANDLE); // [rsp+128h] [rbp-E0h]
  __int64 (__fastcall *v68)(HANDLE, int *); // [rsp+130h] [rbp-D8h]
  int (__fastcall *v69)(HANDLE, _QWORD, _QWORD); // [rsp+138h] [rbp-D0h]
  __int64 (__fastcall *v70)(HANDLE, _QWORD, _QWORD); // [rsp+140h] [rbp-C8h]
  int (__fastcall *v71)(HANDLE, _QWORD); // [rsp+148h] [rbp-C0h]
  int (__fastcall *v72)(HANDLE, __int64, __int64); // [rsp+158h] [rbp-B0h]
  int (__fastcall *v73)(HANDLE, _QWORD); // [rsp+170h] [rbp-98h]
  __int64 (__fastcall *v74)(HANDLE, _QWORD, _QWORD); // [rsp+180h] [rbp-88h]
  __int64 (__fastcall *v75)(HANDLE, int *, _QWORD); // [rsp+190h] [rbp-78h]
  __int64 (__fastcall *v76)(HANDLE, _QWORD, _QWORD); // [rsp+198h] [rbp-70h]
  __int64 (__fastcall *v77)(HANDLE, _QWORD, _QWORD, __int128 *, char *); // [rsp+1B8h] [rbp-50h]
  __int64 v78; // [rsp+1C0h] [rbp-48h]
  unsigned int v79; // [rsp+210h] [rbp+8h]
  int v80; // [rsp+218h] [rbp+10h] BYREF
  int v81; // [rsp+220h] [rbp+18h] BYREF
  int v82; // [rsp+228h] [rbp+20h] BYREF

  pv = 0;
  v2 = 1;
  v82 = 1;
  v81 = 0;
  v78 = 0;
  CoInitializeEx(0, 0);
  if ( a1 )
  {
    if ( RecoAPIs::LoadAPI((RecoAPIs *)v61, *((const unsigned __int16 **)*a1 + 45)) < 0 )
      goto LABEL_111;
    v53 = a1;
    v54 = 1;
    v3 = 0;
    v79 = 0;
    v4 = a1 + 4;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !v54 )
        {
LABEL_110:
          EmptyQueue((struct tagWispContext *)a1);
          DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 6));
          CloseHandle(*v4);
          *v4 = 0;
          CoTaskMemFree(a1[5]);
          a1[5] = 0;
          v50 = v62(a1[1]);
          WispTraceInformationIf(v50 < 0, "%s - RecoAPIs::DestroyContext failed.\n", "BackgroundProcess");
          RecoAPIs::UnloadAPI((RecoAPIs *)v61);
          CoTaskMemFree(a1);
          CoUninitialize();
          _endthreadex(0);
          v2 = 0;
          goto LABEL_111;
        }
        v4 = a1 + 4;
        v58 = a1 + 4;
        if ( !WaitForSingleObject(a1[4], 0x2710u) )
          break;
        if ( v81 )
        {
          v49 = v68(a1[1], &v81);
          WispTraceInformationIf(v49 < 0, "%s - RecoAPIs::Process(incremental) failed.\n", "BackgroundProcess");
          if ( v49 == 1 )
            v81 = 0;
        }
LABEL_109:
        v4 = v58;
      }
      v6 = a1[5];
      if ( *((_DWORD *)v6 + 5) )
        goto LABEL_110;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)v6 + 4, 0, 0)
        && (!*((_DWORD *)a1[5] + 6) || (int)CleanInterruptedQueue((struct tagWispContext *)a1, v5) >= 0) )
      {
        v7 = RemoveLastLink((struct tagWispContext *)a1, &pv);
        if ( v7 >= 0 )
          break;
      }
    }
    v8 = pv;
    v9 = *(_DWORD *)pv;
    if ( *(int *)pv <= 12 )
    {
      if ( v9 == 12 )
      {
        v20 = v74(a1[1], *(unsigned int *)(*((_QWORD *)pv + 1) + 16LL), *(_QWORD *)(*((_QWORD *)pv + 1) + 24LL));
        WispTraceInformationIf(v20 < 0, "%s - AsyncRecoBackgroundIsStringSupported failed.\n", "BackgroundProcess");
        try
        {
          (**((void (__fastcall ***)(_QWORD, _QWORD))v8 + 1))((unsigned int)v20, *(_QWORD *)(*((_QWORD *)v8 + 1) + 8LL));
        }
        catch ( ... )
        {
          v3 = v79;
          v8 = pv;
          a1 = v53;
          goto LABEL_105;
        }
        goto LABEL_105;
      }
      if ( v9 > 6 )
      {
        v16 = v9 - 7;
        if ( !v16 )
        {
          if ( v71(a1[1], *((unsigned int *)pv + 2)) >= 0 )
            goto LABEL_105;
          WispTraceInformation("%s - AsyncRecoSetFlags failed.\n", "BackgroundProcess");
          v3 |= 0x40u;
          goto LABEL_26;
        }
        v17 = v16 - 1;
        if ( !v17 )
        {
          if ( v72(
                 a1[1],
                 **((unsigned int **)pv + 1),
                 (*((_QWORD *)pv + 1) + 8LL) & -(__int64)(**((_DWORD **)pv + 1) != 0)) >= 0 )
            goto LABEL_105;
          WispTraceInformation("%s - AsyncRecoSetTextContext failed.\n", "BackgroundProcess");
          v3 |= 0x100u;
          goto LABEL_26;
        }
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( !v19 )
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 6));
            --*((_DWORD *)a1[5] + 6);
            LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 6));
            goto LABEL_105;
          }
          if ( v19 != 1 || v73(a1[1], *((_QWORD *)pv + 1)) >= 0 )
            goto LABEL_105;
          WispTraceInformation("%s - AsyncRecoSetWordList failed.\n", "BackgroundProcess");
          v3 |= 0x200u;
          goto LABEL_26;
        }
        if ( v67(a1[1]) < 0 )
        {
          WispTraceInformation("%s - AsyncRecoReset failed.\n", "BackgroundProcess");
          v3 |= 0x10u;
          goto LABEL_26;
        }
        *((_DWORD *)a1 + 22) = 0;
        goto LABEL_35;
      }
      if ( v9 == 6 )
      {
        if ( v69(a1[1], **((unsigned int **)pv + 1), *(_QWORD *)(*((_QWORD *)pv + 1) + 8LL)) >= 0 )
          goto LABEL_105;
        WispTraceInformation("%s - AsyncRecoSetFactoid failed.\n", "BackgroundProcess");
        v3 |= 0x80u;
        goto LABEL_26;
      }
      if ( !v9 )
      {
        v54 = 0;
        goto LABEL_105;
      }
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( v13 )
            {
              if ( v13 != 1 || v64(a1[1], *((_QWORD *)pv + 1), *(unsigned int *)(*((_QWORD *)pv + 1) + 36LL)) >= 0 )
                goto LABEL_105;
              WispTraceInformation("%s - AsyncRecoSetGuide failed.\n", "BackgroundProcess");
              v3 |= 0x20u;
              goto LABEL_26;
            }
            if ( v65(a1[1], *((unsigned int *)pv + 2)) < 0 )
            {
              WispTraceInformation("%s - AsyncRecoSetCACMode failed.\n", "BackgroundProcess");
              v3 |= 8u;
LABEL_26:
              v79 = v3;
            }
LABEL_105:
            FreeLink(v8);
            goto LABEL_109;
          }
          *(_OWORD *)&ppvData.vt = 0;
          v82 = 0;
          v14 = v68(a1[1], &v82);
          if ( v14 == 1 )
          {
            v3 |= 1u;
          }
          else if ( v14 )
          {
            if ( v14 < 0 )
            {
              WispTraceInformation("%s - AsyncRecoRequestResultAsync failed.\n", "BackgroundProcess");
              v3 |= 2u;
            }
          }
          else
          {
            GetTextPrediction(v61, a1[1], *(_QWORD *)(*((_QWORD *)v8 + 1) + 16LL), &ppvData);
          }
          v79 = v3;
          if ( *((_DWORD *)a1 + 23) && !*((_DWORD *)a1[5] + 5) )
          {
            try
            {
              (**((void (__fastcall ***)(_QWORD, _QWORD))v8 + 1))(v3, *(_QWORD *)(*((_QWORD *)v8 + 1) + 8LL));
              v3 = 0;
              v79 = 0;
            }
            catch ( ... )
            {
              a1 = v53;
              v8 = pv;
              v3 = 0;
            }
          }
LABEL_35:
          a1[12] = HANDLE_FLAG_INHERIT;
          a1[13] = 0;
          goto LABEL_105;
        }
        v15 = v66(a1[1]);
        WispTraceInformationIf(v15 < 0, "%s - AsyncRecoEndInkInput failed.\n", "BackgroundProcess");
        if ( v15 >= 0 )
          *((_DWORD *)a1 + 22) = 1;
      }
      else if ( v63(
                  a1[1],
                  **((_QWORD **)pv + 1),
                  *(unsigned int *)(*((_QWORD *)pv + 1) + 8LL),
                  *(_QWORD *)(*((_QWORD *)pv + 1) + 16LL),
                  *(_QWORD *)(*((_QWORD *)pv + 1) + 24LL)) < 0 )
      {
        WispTraceInformation("%s - AsyncRecoAddStroke failed\n", "BackgroundProcess");
        v3 |= 4u;
        v79 = v3;
      }
      a1[12] = HANDLE_FLAG_INHERIT;
      a1[13] = 0;
      v81 = 1;
      goto LABEL_105;
    }
    if ( v9 > 18 )
    {
      v40 = v9 - 19;
      if ( v40 )
      {
        v41 = v40 - 1;
        if ( v41 )
        {
          v42 = v41 - 1;
          if ( v42 )
          {
            v43 = v42 - 1;
            if ( v43 )
            {
              if ( v43 == 1 )
              {
                v44 = v70(a1[1], *(unsigned int *)(*((_QWORD *)pv + 1) + 16LL), *(_QWORD *)(*((_QWORD *)pv + 1) + 24LL));
                WispTraceInformationIf(v44 < 0, "%s - AsyncRecoBackgroundSetConstraint failed.\n", "BackgroundProcess");
                try
                {
                  (**((void (__fastcall ***)(_QWORD, _QWORD))v8 + 1))(
                    (unsigned int)v44,
                    *(_QWORD *)(*((_QWORD *)v8 + 1) + 8LL));
                }
                catch ( ... )
                {
                  v3 = v79;
                  v8 = pv;
                  a1 = v53;
                  goto LABEL_105;
                }
              }
            }
            else if ( (int)v70(a1[1], **((unsigned int **)pv + 1), *(_QWORD *)(*((_QWORD *)pv + 1) + 8LL)) < 0 )
            {
              WispTraceInformation("%s - AsyncRecoSetConstraint failed.\n", "BackgroundProcess");
            }
          }
          else
          {
            v45 = *((_QWORD *)pv + 1);
            memset(&ppvData, 0, sizeof(ppvData));
            v60 = 0;
            VariantInit(&ppvData);
            v46 = v77(a1[1], *(_QWORD *)(v45 + 16), *(_QWORD *)(v45 + 24), &v60, (char *)&v60 + 8);
            WispTraceInformationIf(v46 < 0, "%s - BackgroundGetPredictionText failed.\n", "BackgroundProcess");
            try
            {
              v59 = ppvData;
              (*(void (__fastcall **)(_QWORD, _QWORD, VARIANTARG *, __int128 *))v45)(
                (unsigned int)v46,
                *(_QWORD *)(v45 + 8),
                &v59,
                &v60);
            }
            catch ( ... )
            {
              v3 = v79;
              v8 = pv;
              a1 = v53;
              goto LABEL_105;
            }
          }
        }
        else
        {
          v47 = v65(a1[1], *(unsigned int *)(*((_QWORD *)pv + 1) + 16LL));
          WispTraceInformationIf(v47 < 0, "%s - AsyncRecoBackgroundSetCACMode failed.\n", "BackgroundProcess");
          try
          {
            (**((void (__fastcall ***)(_QWORD, _QWORD))v8 + 1))(
              (unsigned int)v47,
              *(_QWORD *)(*((_QWORD *)v8 + 1) + 8LL));
          }
          catch ( ... )
          {
            v3 = v79;
            v8 = pv;
            a1 = v53;
            goto LABEL_105;
          }
        }
      }
      else
      {
        v48 = v76(a1[1], *(unsigned int *)(*((_QWORD *)pv + 1) + 16LL), *(_QWORD *)(*((_QWORD *)pv + 1) + 24LL));
        WispTraceInformationIf(v48 < 0, "%s - BackgroundSetEnabledUnicodeRanges failed.\n", "BackgroundProcess");
        try
        {
          (**((void (__fastcall ***)(_QWORD, _QWORD))v8 + 1))((unsigned int)v48, *(_QWORD *)(*((_QWORD *)v8 + 1) + 8LL));
        }
        catch ( ... )
        {
          v3 = v79;
          v8 = pv;
          a1 = v53;
          goto LABEL_105;
        }
      }
      goto LABEL_105;
    }
    if ( v9 != 18 )
    {
      v21 = v9 - 13;
      if ( !v21 )
      {
        v34 = v69(a1[1], *(unsigned int *)(*((_QWORD *)pv + 1) + 16LL), *(_QWORD *)(*((_QWORD *)pv + 1) + 24LL));
        WispTraceInformationIf(v34 < 0, "%s - AsyncRecoBackgroundSetFactoid failed.\n", "BackgroundProcess");
        try
        {
          (**((void (__fastcall ***)(_QWORD, _QWORD))v8 + 1))((unsigned int)v34, *(_QWORD *)(*((_QWORD *)v8 + 1) + 8LL));
        }
        catch ( ... )
        {
          v3 = v79;
          v8 = pv;
          a1 = v53;
          goto LABEL_105;
        }
        goto LABEL_105;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        v33 = v71(a1[1], *(unsigned int *)(*((_QWORD *)pv + 1) + 16LL));
        WispTraceInformationIf(v33 < 0, "%s - AsyncRecoBackgroundSetFlags failed.\n", "BackgroundProcess");
        try
        {
          (**((void (__fastcall ***)(_QWORD, _QWORD))v8 + 1))((unsigned int)v33, *(_QWORD *)(*((_QWORD *)v8 + 1) + 8LL));
        }
        catch ( ... )
        {
          v3 = v79;
          v8 = pv;
          a1 = v53;
          goto LABEL_105;
        }
        goto LABEL_105;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        v29 = 0;
        v30 = (unsigned int *)*((_QWORD *)pv + 1);
        v31 = *v30;
        if ( (_DWORD)v31 )
          v29 = *((_QWORD *)v30 + 3);
        v32 = v72(a1[1], v31, v29);
        WispTraceInformationIf(v7 < 0, "%s - AsyncRecoBackgroundSetTextContext failed.\n", "BackgroundProcess");
        try
        {
          (*(void (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)v8 + 1) + 8LL))(
            v32,
            *(_QWORD *)(*((_QWORD *)v8 + 1) + 16LL));
        }
        catch ( ... )
        {
          v3 = v79;
          v8 = pv;
          a1 = v53;
          goto LABEL_105;
        }
        goto LABEL_105;
      }
      v24 = v23 - 1;
      if ( !v24 )
      {
        v28 = v64(a1[1], *((_QWORD *)pv + 1) + 16LL, *(unsigned int *)(*((_QWORD *)pv + 1) + 52LL));
        WispTraceInformationIf(v28 < 0, "%s - AsyncRecoBackgroundSetGuide failed.\n", "BackgroundProcess");
        try
        {
          (**((void (__fastcall ***)(_QWORD, _QWORD))v8 + 1))((unsigned int)v28, *(_QWORD *)(*((_QWORD *)v8 + 1) + 8LL));
        }
        catch ( ... )
        {
          v3 = v79;
          v8 = pv;
          a1 = v53;
          goto LABEL_105;
        }
        goto LABEL_105;
      }
      if ( v24 != 1 )
        goto LABEL_105;
      *(_OWORD *)&ppvData.vt = 0;
      v82 = 0;
      v25 = v68(a1[1], &v82);
      if ( v25 == 1 )
      {
        v3 |= 1u;
      }
      else if ( v25 < 0 )
      {
        WispTraceInformation("%s - AsyncRecoRequestResultAsyncVariant failed.\n", "BackgroundProcess");
        v3 |= 2u;
      }
      v79 = v3;
      if ( *((_DWORD *)a1 + 23) )
      {
        v26 = a1[5];
        if ( !v26[5] && !v26[6] )
        {
          if ( !v25 )
            GetTextPrediction(v61, a1[1], *(_QWORD *)(*((_QWORD *)v8 + 1) + 40LL), &ppvData);
          try
          {
            v27 = *((_QWORD *)v8 + 1);
            v59 = *(VARIANTARG *)(v27 + 8);
            (*(void (__fastcall **)(_QWORD, _QWORD, VARIANTARG *))v27)(v3, *(_QWORD *)(v27 + 32), &v59);
            v3 = 0;
            v79 = 0;
          }
          catch ( ... )
          {
            a1 = v53;
            v8 = pv;
            v3 = 0;
            goto LABEL_35;
          }
        }
      }
      goto LABEL_35;
    }
    v80 = 0;
    *(_QWORD *)&ppvData.vt = 0;
    v35 = *((_QWORD *)pv + 1);
    v55 = v35;
    v36 = v75(a1[1], &v80, 0);
    if ( v36 >= 0 )
    {
      Vector = SafeArrayCreateVector(0x12u, 0, 2 * v80);
      v38 = Vector;
      if ( Vector )
      {
        v36 = SafeArrayAccessData(Vector, (void **)&ppvData);
        if ( v36 >= 0 )
        {
          v56 = v80;
          v36 = v75(a1[1], &v80, *(_QWORD *)&ppvData.vt);
          if ( v36 >= 0 && v80 != v56 )
            v36 = -2147418113;
          SafeArrayUnaccessData(v38);
          if ( v36 >= 0 )
          {
            v39 = v55;
            *(_WORD *)(v55 + 8) = 8210;
            *(_QWORD *)(v39 + 16) = v38;
            v35 = v39;
            goto LABEL_93;
          }
        }
        SafeArrayDestroy(v38);
      }
      else
      {
        v36 = -2147024882;
      }
      v35 = v55;
    }
LABEL_93:
    WispTraceInformationIf(v36 < 0, "%s - BackgroundGetEnabledUnicodeRanges failed.\n", "BackgroundProcess");
    try
    {
      v59 = *(VARIANTARG *)(v35 + 8);
      (*(void (__fastcall **)(_QWORD, _QWORD, VARIANTARG *, _QWORD))v35)(
        (unsigned int)v36,
        *(_QWORD *)(v35 + 32),
        &v59,
        0);
    }
    catch ( ... )
    {
      v3 = v79;
      v8 = pv;
      a1 = v53;
      goto LABEL_105;
    }
    goto LABEL_105;
  }
  _endthreadex(1u);
LABEL_111:
  RecoAPIs::~RecoAPIs((RecoAPIs *)v61);
  return v2;
}

```

## disassembly

```asm
0x180084100  mov     rax, rsp
0x180084103  push    rbx
0x180084104  push    rsi
0x180084105  push    rdi
0x180084106  push    r12
0x180084108  push    r13
0x18008410a  push    r14
0x18008410c  push    r15
0x18008410e  sub     rsp, 1D0h
0x180084115  mov     rsi, rcx
0x180084118  xor     edi, edi
0x18008411a  mov     [rsp+208h+pv], rdi
0x18008411f  lea     r12d, [rdi+1]
0x180084123  mov     [rax+20h], r12d
0x180084127  mov     [rax+18h], edi
0x18008412a  mov     [rax-48h], rdi
0x18008412e  xor     edx, edx; dwCoInit
0x180084130  xor     ecx, ecx; pvReserved
0x180084132  call    cs:__imp_CoInitializeEx
0x180084138  test    rsi, rsi
0x18008413b  jnz     short loc_18008414B
0x18008413d  mov     ecx, r12d; ReturnCode
0x180084140  call    cs:__imp__endthreadex
0x180084146  jmp     loc_180084D00
0x18008414b  mov     rdx, [rsi]
0x18008414e  mov     rdx, [rdx+168h]; unsigned __int16 *
0x180084155  lea     rcx, [rsp+208h+var_158]; this
0x18008415d  call    ?LoadAPI@RecoAPIs@@QEAAJPEBG@Z; RecoAPIs::LoadAPI(ushort const *)
0x180084162  test    eax, eax
0x180084164  js      loc_180084D00
0x18008416a  mov     [rsp+208h+var_1D0], rsi
0x18008416f  mov     [rsp+208h+var_1C8], r12d
0x180084174  mov     r14d, edi
0x180084177  mov     [rsp+208h+arg_0], edi
0x18008417e  lea     rbx, [rsi+20h]
0x180084182  cmp     [rsp+208h+var_1C8], edi
0x180084186  jz      loc_180084C83
0x18008418c  lea     rbx, [rsi+20h]
0x180084190  mov     [rsp+208h+var_198], rbx
0x180084195  mov     edx, 2710h; dwMilliseconds
0x18008419a  mov     rcx, [rbx]; hHandle
0x18008419d  call    cs:__imp_WaitForSingleObject
0x1800841a3  test    eax, eax
0x1800841a5  jnz     loc_180084C2E
0x1800841ab  mov     rcx, [rsi+28h]
0x1800841af  cmp     [rcx+14h], edi
0x1800841b2  jnz     loc_180084C83
0x1800841b8  lock cmpxchg [rcx+10h], edi
0x1800841bd  jz      short loc_180084182
0x1800841bf  mov     rax, [rsi+28h]
0x1800841c3  cmp     [rax+18h], edi
0x1800841c6  jz      short loc_1800841D4
0x1800841c8  mov     rcx, rsi; struct tagWispContext *
0x1800841cb  call    ?CleanInterruptedQueue@@YAJPEAUtagWispContext@@PEAX@Z; CleanInterruptedQueue(tagWispContext *,void *)
0x1800841d0  test    eax, eax
0x1800841d2  js      short loc_180084182
0x1800841d4  lea     rdx, [rsp+208h+pv]; struct tagOpLink **
0x1800841d9  mov     rcx, rsi; struct tagWispContext *
0x1800841dc  call    ?RemoveLastLink@@YAJPEAUtagWispContext@@PEAPEAUtagOpLink@@@Z; RemoveLastLink(tagWispContext *,tagOpLink * *)
0x1800841e1  mov     r13d, eax
0x1800841e4  test    eax, eax
0x1800841e6  js      short loc_180084182
0x1800841e8  mov     r11, rdi
0x1800841eb  mov     r15, [rsp+208h+pv]
0x1800841f0  mov     ecx, [r15]
0x1800841f3  cmp     ecx, 0Ch
0x1800841f6  jg      loc_180084622
0x1800841fc  jz      loc_1800845CC
0x180084202  cmp     ecx, 6
0x180084205  jg      loc_180084476
0x18008420b  jz      loc_180084436
0x180084211  test    ecx, ecx
0x180084213  jz      loc_18008442D
0x180084219  sub     ecx, 1
0x18008421c  jz      loc_1800843C8
0x180084222  sub     ecx, 1
0x180084225  jz      loc_180084390
0x18008422b  sub     ecx, 1
0x18008422e  jz      loc_1800842BD
0x180084234  sub     ecx, 1
0x180084237  jz      short loc_18008427C
0x180084239  cmp     ecx, 1
0x18008423c  jnz     loc_180084C24
0x180084242  mov     rdx, [r15+8]
0x180084246  mov     r8d, [rdx+24h]
0x18008424a  mov     rcx, [rsi+8]
0x18008424e  mov     rax, [rsp+208h+var_110]
0x180084256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008425b  test    eax, eax
0x18008425d  jns     loc_180084C24
0x180084263  lea     rdx, aBackgroundproc; "BackgroundProcess"
0x18008426a  lea     rcx, aSAsyncrecosetg; "%s - AsyncRecoSetGuide failed.\n"
0x180084271  call    ?WispTraceInformation@@YAXPEBDZZ; WispTraceInformation(char const *,...)
0x180084276  or      r14d, 20h
0x18008427a  jmp     short loc_1800842B0
0x18008427c  mov     edx, [r15+8]
0x180084280  mov     rcx, [rsi+8]
0x180084284  mov     rax, [rsp+208h+var_F8]
0x18008428c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084291  test    eax, eax
0x180084293  jns     loc_180084C24
0x180084299  lea     rdx, aBackgroundproc; "BackgroundProcess"
0x1800842a0  lea     rcx, aSAsyncrecosetc_0; "%s - AsyncRecoSetCACMode failed.\n"
0x1800842a7  call    ?WispTraceInformation@@YAXPEBDZZ; WispTraceInformation(char const *,...)
0x1800842ac  or      r14d, 8
0x1800842b0  mov     [rsp+208h+arg_0], r14d
0x1800842b8  jmp     loc_180084C24
0x1800842bd  xorps   xmm0, xmm0
0x1800842c0  movups  xmmword ptr [rsp+208h+ppvData], xmm0
0x1800842c5  mov     [rsp+208h+arg_18], edi
0x1800842cc  lea     rdx, [rsp+208h+arg_18]
0x1800842d4  mov     rcx, [rsi+8]
0x1800842d8  mov     rax, [rsp+208h+var_D8]
0x1800842e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800842e5  cmp     eax, r12d
0x1800842e8  jnz     short loc_1800842EF
0x1800842ea  or      r14d, r12d
0x1800842ed  jmp     short loc_18008432F
0x1800842ef  test    eax, eax
0x1800842f1  jnz     short loc_180084316
0x1800842f3  mov     r8, [r15+8]
0x1800842f7  lea     r9, [rsp+208h+ppvData]
0x1800842fc  mov     r8, [r8+10h]
0x180084300  mov     rdx, [rsi+8]
0x180084304  lea     rcx, [rsp+208h+var_158]
0x18008430c  call    GetTextPrediction
0x180084311  mov     r8, rax
0x180084314  jmp     short loc_180084332
0x180084316  jns     short loc_18008432F
0x180084318  lea     rdx, aBackgroundproc; "BackgroundProcess"
0x18008431f  lea     rcx, aSAsyncrecorequ; "%s - AsyncRecoRequestResultAsync failed"...
0x180084326  call    ?WispTraceInformation@@YAXPEBDZZ; WispTraceInformation(char const *,...)
0x18008432b  or      r14d, 2
0x18008432f  mov     r8, rdi
0x180084332  mov     [rsp+208h+arg_0], r14d
0x18008433a  cmp     [rsi+5Ch], edi
0x18008433d  jz      short loc_18008437F
0x18008433f  mov     rax, [rsi+28h]
0x180084343  cmp     [rax+14h], edi
0x180084346  jnz     short loc_18008437F
0x180084348  mov     rdx, [r15+8]
0x18008434c  mov     rax, [rdx]
0x18008434f  mov     rdx, [rdx+8]
0x180084353  mov     ecx, r14d
0x180084356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008435b  mov     r14d, edi
0x18008435e  mov     [rsp+208h+arg_0], edi
0x180084365  jmp     short loc_18008437F
0x180084367  xor     edi, edi
0x180084369  lea     r12d, [rdi+1]
0x18008436d  mov     rsi, [rsp+208h+var_1D0]
0x180084372  mov     r15, [rsp+208h+pv]
0x180084377  mov     r14d, [rsp+208h+arg_0]
0x18008437f  mov     qword ptr [rsi+60h], 1
0x180084387  mov     [rsi+68h], rdi
0x18008438b  jmp     loc_180084C24
0x180084390  mov     rcx, [rsi+8]
0x180084394  mov     rax, [rsp+208h+var_F0]
0x18008439c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800843a1  mov     ebx, eax
0x1800843a3  mov     ecx, eax
0x1800843a5  shr     ecx, 1Fh
0x1800843a8  lea     r8, aBackgroundproc; "BackgroundProcess"
0x1800843af  lea     rdx, aSAsyncrecoendi; "%s - AsyncRecoEndInkInput failed.\n"
0x1800843b6  movzx   ecx, cl; bool
0x1800843b9  call    ?WispTraceInformationIf@@YAX_NPEBDZZ; WispTraceInformationIf(bool,char const *,...)
0x1800843be  test    ebx, ebx
0x1800843c0  js      short loc_180084414
0x1800843c2  mov     [rsi+58h], r12d
0x1800843c6  jmp     short loc_180084414
0x1800843c8  mov     rdx, [r15+8]
0x1800843cc  mov     rcx, [rdx+18h]
0x1800843d0  mov     [rsp+208h+var_1E8], rcx
0x1800843d5  mov     r9, [rdx+10h]
0x1800843d9  mov     r8d, [rdx+8]
0x1800843dd  mov     rdx, [rdx]
0x1800843e0  mov     rcx, [rsi+8]
0x1800843e4  mov     rax, [rsp+208h+var_120]
0x1800843ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800843f1  test    eax, eax
0x1800843f3  jns     short loc_180084414
0x1800843f5  lea     rdx, aBackgroundproc; "BackgroundProcess"
0x1800843fc  lea     rcx, aSAsyncrecoadds; "%s - AsyncRecoAddStroke failed\n"
0x180084403  call    ?WispTraceInformation@@YAXPEBDZZ; WispTraceInformation(char const *,...)
0x180084408  or      r14d, 4
0x18008440c  mov     [rsp+208h+arg_0], r14d
0x180084414  mov     qword ptr [rsi+60h], 1
0x18008441c  mov     [rsi+68h], rdi
0x180084420  mov     [rsp+208h+arg_10], r12d
0x180084428  jmp     loc_180084C24
0x18008442d  mov     [rsp+208h+var_1C8], edi
0x180084431  jmp     loc_180084C24
0x180084436  mov     rdx, [r15+8]
0x18008443a  mov     r8, [rdx+8]
0x18008443e  mov     edx, [rdx]
0x180084440  mov     rcx, [rsi+8]
0x180084444  mov     rax, [rsp+208h+var_D0]
0x18008444c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084451  test    eax, eax
0x180084453  jns     loc_180084C24
0x180084459  lea     rdx, aBackgroundproc; "BackgroundProcess"
0x180084460  lea     rcx, aSAsyncrecosetf_0; "%s - AsyncRecoSetFactoid failed.\n"
0x180084467  call    ?WispTraceInformation@@YAXPEBDZZ; WispTraceInformation(char const *,...)
0x18008446c  bts     r14d, 7
0x180084471  jmp     loc_1800842B0
0x180084476  sub     ecx, 7
0x180084479  jz      loc_180084593
0x18008447f  sub     ecx, 1
0x180084482  jz      loc_18008452E
0x180084488  sub     ecx, 1
0x18008448b  jz      short loc_1800844F5
0x18008448d  sub     ecx, 1
0x180084490  jz      short loc_1800844D5
0x180084492  cmp     ecx, 1
0x180084495  jnz     loc_180084C24
0x18008449b  mov     rdx, [r15+8]
0x18008449f  mov     rcx, [rsi+8]
0x1800844a3  mov     rax, [rsp+208h+var_98]
0x1800844ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800844b0  test    eax, eax
0x1800844b2  jns     loc_180084C24
0x1800844b8  lea     rdx, aBackgroundproc; "BackgroundProcess"
0x1800844bf  lea     rcx, aSAsyncrecosetw; "%s - AsyncRecoSetWordList failed.\n"
0x1800844c6  call    ?WispTraceInformation@@YAXPEBDZZ; WispTraceInformation(char const *,...)
0x1800844cb  bts     r14d, 9
0x1800844d0  jmp     loc_1800842B0
0x1800844d5  lea     rcx, [rsi+30h]; lpCriticalSection
0x1800844d9  call    cs:__imp_EnterCriticalSection
0x1800844df  mov     rax, [rsi+28h]
0x1800844e3  dec     dword ptr [rax+18h]
0x1800844e6  lea     rcx, [rsi+30h]; lpCriticalSection
0x1800844ea  call    cs:__imp_LeaveCriticalSection
0x1800844f0  jmp     loc_180084C24
0x1800844f5  mov     rcx, [rsi+8]
0x1800844f9  mov     rax, [rsp+208h+var_E0]
0x180084501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084506  test    eax, eax
0x180084508  jns     short loc_180084526
0x18008450a  lea     rdx, aBackgroundproc; "BackgroundProcess"
0x180084511  lea     rcx, aSAsyncrecorese; "%s - AsyncRecoReset failed.\n"
0x180084518  call    ?WispTraceInformation@@YAXPEBDZZ; WispTraceInformation(char const *,...)
0x18008451d  or      r14d, 10h
0x180084521  jmp     loc_1800842B0
0x180084526  mov     [rsi+58h], edi
0x180084529  jmp     loc_18008437F
0x18008452e  mov     r10, [r15+8]
0x180084532  mov     eax, [r10]
0x180084535  lea     rcx, [r10+8]
0x180084539  neg     eax
0x18008453b  sbb     r8, r8
0x18008453e  and     r8, rcx
0x180084541  mov     r9d, [r10+4]
0x180084545  test    r9d, r9d
0x180084548  jz      short loc_180084555
0x18008454a  mov     r11d, [r10]
0x18008454d  add     r11, 4
0x180084551  lea     r11, [r10+r11*2]
0x180084555  mov     [rsp+208h+var_1E8], r11
0x18008455a  mov     edx, [r10]
0x18008455d  mov     rcx, [rsi+8]
0x180084561  mov     rax, [rsp+208h+var_B0]
0x180084569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008456e  test    eax, eax
0x180084570  jns     loc_180084C24
0x180084576  lea     rdx, aBackgroundproc; "BackgroundProcess"
0x18008457d  lea     rcx, aSAsyncrecosett; "%s - AsyncRecoSetTextContext failed.\n"
0x180084584  call    ?WispTraceInformation@@YAXPEBDZZ; WispTraceInformation(char const *,...)
0x180084589  bts     r14d, 8
0x18008458e  jmp     loc_1800842B0
0x180084593  mov     edx, [r15+8]
0x180084597  mov     rcx, [rsi+8]
0x18008459b  mov     rax, [rsp+208h+var_C0]
0x1800845a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800845a8  test    eax, eax
0x1800845aa  jns     loc_180084C24
0x1800845b0  lea     rdx, aBackgroundproc; "BackgroundProcess"
0x1800845b7  lea     rcx, aSAsyncrecosetf; "%s - AsyncRecoSetFlags failed.\n"
0x1800845be  call    ?WispTraceInformation@@YAXPEBDZZ; WispTraceInformation(char const *,...)
0x1800845c3  or      r14d, 40h
0x1800845c7  jmp     loc_1800842B0
0x1800845cc  mov     rdx, [r15+8]
0x1800845d0  mov     r8, [rdx+18h]
0x1800845d4  mov     edx, [rdx+10h]
0x1800845d7  mov     rcx, [rsi+8]
0x1800845db  mov     rax, [rsp+208h+var_88]
0x1800845e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800845e8  mov     ebx, eax
0x1800845ea  mov     ecx, eax
0x1800845ec  shr     ecx, 1Fh
0x1800845ef  lea     r8, aBackgroundproc; "BackgroundProcess"
0x1800845f6  lea     rdx, aSAsyncrecoback_0; "%s - AsyncRecoBackgroundIsStringSupport"...
0x1800845fd  movzx   ecx, cl; bool
0x180084600  call    ?WispTraceInformationIf@@YAX_NPEBDZZ; WispTraceInformationIf(bool,char const *,...)
0x180084605  nop
0x180084606  mov     rdx, [r15+8]
0x18008460a  mov     rax, [rdx]
0x18008460d  mov     rdx, [rdx+8]
0x180084611  mov     ecx, ebx
0x180084613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084618  jmp     loc_180084C08
  ... truncated ...
```
