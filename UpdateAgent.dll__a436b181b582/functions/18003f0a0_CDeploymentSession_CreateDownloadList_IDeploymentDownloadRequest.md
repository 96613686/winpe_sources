# CDeploymentSession::CreateDownloadList(IDeploymentDownloadRequest *)

- ea: `0x18003f0a0`
- end: `0x18003fdb2`
- name: `?CreateDownloadList@CDeploymentSession@@UEAAJPEAUIDeploymentDownloadRequest@@@Z`
- size: `3346`
- prototype: `__int64 __fastcall(CDeploymentSession *__hidden this, struct IDeploymentDownloadRequest *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b4b8`

## callees

- `0x1800059d0`
- `0x180039f90`
- `0x18003f0a0`
- `0x180077664`
- `0x180078b9c`
- `0x180251fe0`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003f81e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003f81e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f482`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fc07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fc25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fc46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fc67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fc88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f461`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f482`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f4e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fc07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fc25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fc46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fc67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fc88`

## string_xrefs

- `0x18003f721`: `SourcePath`
- `0x18003f150`: `CDeploymentSession::CreateDownloadList`
- `0x18003f1c0`: `CDeploymentSession::CreateDownloadList`
- `0x18003f232`: `CDeploymentSession::CreateDownloadList`
- `0x18003f182`: `CreateDownloadList: Enter`
- `0x18003fbe4`: `CreateDownloadList: Exit`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall CDeploymentSession::CreateDownloadList(
        CDeploymentSession *this,
        struct IDeploymentDownloadRequest *a2)
{
  _QWORD *v4; // r15
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 updated; // rcx
  __int64 v8; // rdx
  int DlpDownloadListXml; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  int v14; // eax
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  unsigned int v20; // r14d
  int v21; // eax
  int v22; // eax
  int v23; // esi
  __int64 v24; // rcx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  unsigned int i; // esi
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  const char *v49; // r9
  __int64 result; // rax
  PCNZWCH lpString2; // [rsp+20h] [rbp-D8h]
  __int64 cchCount2; // [rsp+28h] [rbp-D0h]
  _QWORD v53[2]; // [rsp+30h] [rbp-C8h] BYREF
  _QWORD *v54; // [rsp+40h] [rbp-B8h] BYREF
  unsigned int v55; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v56; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v57; // [rsp+58h] [rbp-A0h] BYREF
  _QWORD *v58; // [rsp+60h] [rbp-98h] BYREF
  unsigned int v59; // [rsp+68h] [rbp-90h] BYREF
  PCNZWCH lpString1; // [rsp+70h] [rbp-88h] BYREF
  __int64 v61; // [rsp+78h] [rbp-80h] BYREF
  __int64 v62; // [rsp+80h] [rbp-78h] BYREF
  LPVOID v63; // [rsp+88h] [rbp-70h] BYREF
  LPVOID v64; // [rsp+90h] [rbp-68h] BYREF
  LPVOID v65; // [rsp+98h] [rbp-60h] BYREF
  LPVOID pv; // [rsp+A0h] [rbp-58h] BYREF
  __int64 v67; // [rsp+A8h] [rbp-50h] BYREF
  __int64 v68; // [rsp+B0h] [rbp-48h] BYREF
  __int64 v69; // [rsp+B8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v53[1] = -2;
  try
  {
    v4 = 0;
    v53[0] = 0;
    v54 = 0;
    v58 = 0;
    v67 = 0;
    v62 = 0;
    v56 = 0;
    v57 = 0;
    v61 = 0;
    pv = 0;
    v65 = 0;
    v64 = 0;
    v63 = 0;
    lpString1 = 0;
    v59 = 0;
    v55 = 0;
    v68 = 0;
    v69 = 0;
    v5 = *((_QWORD *)this + 75);
    if ( !a2 )
    {
      v6 = -2147024809;
      if ( !v5 )
      {
LABEL_4:
        updated = 0;
LABEL_8:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(updated);
LABEL_145:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v6);
        if ( lpString1 )
        {
          CoTaskMemFree((LPVOID)lpString1);
          lpString1 = 0;
        }
        if ( v63 )
        {
          CoTaskMemFree(v63);
          v63 = 0;
        }
        if ( v64 )
        {
          CoTaskMemFree(v64);
          v64 = 0;
        }
        if ( v65 )
        {
          CoTaskMemFree(v65);
          v65 = 0;
        }
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        if ( v61 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
          v61 = 0;
        }
        if ( v57 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
          v57 = 0;
        }
        if ( v56 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
          v56 = 0;
        }
        if ( v62 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
          v62 = 0;
        }
        if ( v67 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
          v67 = 0;
        }
        if ( v58 )
        {
          (*(void (__fastcall **)(_QWORD *))(*v58 + 16LL))(v58);
          v58 = 0;
        }
        if ( v54 )
        {
          (*(void (__fastcall **)(_QWORD *))(*v54 + 16LL))(v54);
          v54 = 0;
        }
        if ( v4 )
          (*(void (__fastcall **)(_QWORD *))(*v4 + 16LL))(v4);
        return v6;
      }
      updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v5,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::CreateDownloadList",
                                9027,
                                -2147024809);
LABEL_6:
      if ( (int)updated < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated, v8);
      goto LABEL_8;
    }
    if ( v5 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v5, 2, L"CreateDownloadList: Enter");
    DlpDownloadListXml = CreateDlpDownloadListXml(v53);
    v6 = DlpDownloadListXml;
    if ( DlpDownloadListXml < 0 )
    {
      v10 = *((_QWORD *)this + 75);
      if ( v10 )
      {
        v12 = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v10,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDeploymentSession::CreateDownloadList",
                9031,
                DlpDownloadListXml);
        v11 = (unsigned int)v12;
        if ( v12 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v12, v13);
      }
      else
      {
        v11 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v11);
      v4 = (_QWORD *)v53[0];
      goto LABEL_145;
    }
    v4 = (_QWORD *)v53[0];
    v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*(_QWORD *)v53[0] + 40LL))(
            v53[0],
            *((_QWORD *)this + 61),
            0);
    v6 = v14;
    if ( v14 < 0 )
    {
      v15 = *((_QWORD *)this + 75);
      if ( !v15 )
        goto LABEL_4;
      LODWORD(cchCount2) = v14;
      LODWORD(lpString2) = 9033;
      goto LABEL_20;
    }
    v16 = (*(__int64 (__fastcall **)(_QWORD *))(*v4 + 48LL))(v4);
    v6 = v16;
    if ( v16 < 0 )
    {
      v15 = *((_QWORD *)this + 75);
      if ( !v15 )
        goto LABEL_4;
      LODWORD(cchCount2) = v16;
      LODWORD(lpString2) = 9034;
      goto LABEL_20;
    }
    v17 = (*(__int64 (__fastcall **)(struct IDeploymentDownloadRequest *, __int64 *))(*(_QWORD *)a2 + 40LL))(a2, &v67);
    v6 = v17;
    if ( v17 < 0 )
    {
      v15 = *((_QWORD *)this + 75);
      if ( !v15 )
        goto LABEL_4;
      LODWORD(cchCount2) = v17;
      LODWORD(lpString2) = 9036;
      goto LABEL_20;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v67 + 24LL))(v67, &v59);
    v6 = v18;
    if ( v18 < 0 )
    {
      v15 = *((_QWORD *)this + 75);
      if ( !v15 )
        goto LABEL_4;
      LODWORD(cchCount2) = v18;
      LODWORD(lpString2) = 9038;
      goto LABEL_20;
    }
    v19 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD))(v4[1] + 24LL))(v4 + 1, L"FileCount", v59);
    v6 = v19;
    if ( v19 < 0 )
    {
      v15 = *((_QWORD *)this + 75);
      if ( !v15 )
        goto LABEL_4;
      LODWORD(cchCount2) = v19;
      LODWORD(lpString2) = 9040;
      goto LABEL_20;
    }
    v20 = 0;
LABEL_34:
    if ( v20 >= v59 )
    {
      v48 = (*(__int64 (__fastcall **)(_QWORD *))(*v4 + 56LL))(v4);
      v6 = v48;
      v15 = *((_QWORD *)this + 75);
      if ( v48 >= 0 )
      {
        if ( v15 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v15, 2, L"CreateDownloadList: Exit");
        goto LABEL_145;
      }
      if ( !v15 )
        goto LABEL_4;
      LODWORD(cchCount2) = v48;
      LODWORD(lpString2) = 9105;
    }
    else
    {
      if ( v56 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
        v56 = 0;
      }
      if ( v57 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
        v57 = 0;
      }
      v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v67 + 32LL))(v67, v20, &v56);
      v6 = v21;
      if ( v21 < 0 )
      {
        v15 = *((_QWORD *)this + 75);
        if ( !v15 )
          goto LABEL_4;
        LODWORD(cchCount2) = v21;
        LODWORD(lpString2) = 9047;
        goto LABEL_20;
      }
      v22 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v56)(
              v56,
              &GUID_f8293c60_4b0e_4489_ac5d_4eda3a608dd5,
              &v57);
      v23 = v22;
      if ( v22 < 0 )
      {
        v24 = *((_QWORD *)this + 75);
        if ( !v24 )
        {
          v6 = v22;
LABEL_47:
          v15 = *((_QWORD *)this + 75);
          if ( !v15 )
            goto LABEL_4;
          LODWORD(cchCount2) = v23;
          LODWORD(lpString2) = 9053;
          goto LABEL_20;
        }
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v24, 2, L"This version of IDeploymentFileRequest is not supported");
      }
      v6 = v23;
      if ( v23 < 0 )
        goto LABEL_47;
      if ( v54 )
      {
        (*(void (__fastcall **)(_QWORD *))(*v54 + 16LL))(v54);
        v54 = 0;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v65 )
      {
        CoTaskMemFree(v65);
        v65 = 0;
      }
      if ( v64 )
      {
        CoTaskMemFree(v64);
        v64 = 0;
      }
      if ( v63 )
      {
        CoTaskMemFree(v63);
        v63 = 0;
      }
      if ( lpString1 )
      {
        CoTaskMemFree((LPVOID)lpString1);
        lpString1 = 0;
      }
      v25 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v56 + 24LL))(v56, &pv);
      v6 = v25;
      if ( v25 >= 0 )
      {
        v26 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v56 + 40LL))(v56, &v65);
        v6 = v26;
        if ( v26 >= 0 )
        {
          v27 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v57 + 56LL))(v57, &v64);
          v6 = v27;
          if ( v27 >= 0 )
          {
            v28 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v57 + 64LL))(v57, &v63);
            v6 = v28;
            if ( v28 >= 0 )
            {
              v29 = (*(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v57 + 72LL))(v57, &lpString1);
              v6 = v29;
              if ( v29 >= 0 )
              {
                v30 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD **))(*v4 + 24LL))(v4, L"File", &v54);
                v6 = v30;
                if ( v30 >= 0 )
                {
                  if ( pv
                    && (v31 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *))(v54[1] + 40LL))(v54 + 1, L"Hash"),
                        v6 = v31,
                        v31 < 0) )
                  {
                    v15 = *((_QWORD *)this + 75);
                    if ( !v15 )
                      goto LABEL_4;
                    LODWORD(cchCount2) = v31;
                    LODWORD(lpString2) = 9072;
                  }
                  else
                  {
                    v32 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, LPVOID))(v54[1] + 40LL))(
                            v54 + 1,
                            L"SourceName",
                            v64);
                    v6 = v32;
                    if ( v32 >= 0 )
                    {
                      v33 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, LPVOID))(v54[1] + 40LL))(
                              v54 + 1,
                              L"SourcePath",
                              v63);
                      v6 = v33;
                      if ( v33 >= 0 )
                      {
                        v34 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, LPVOID))(v54[1] + 40LL))(
                                v54 + 1,
                                L"TargetFileName",
                                v65);
                        v6 = v34;
                        if ( v34 >= 0 )
                        {
                          v35 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, PCNZWCH))(v54[1] + 40LL))(
                                  v54 + 1,
                                  L"PayloadType",
                                  lpString1);
                          v6 = v35;
                          if ( v35 >= 0 )
                          {
                            if ( !*((_QWORD *)this + 69)
                              || CompareStringW(0x409u, 1u, lpString1, -1, L"Canonical", -1) == 2
                              || (v36 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD))(v54[1] + 40LL))(
                                          v54 + 1,
                                          L"SourceBuild",
                                          *((_QWORD *)this + 69)),
                                  v6 = v36,
                                  v36 >= 0) )
                            {
                              if ( v62 )
                              {
                                (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
                                v62 = 0;
                              }
                              v37 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v56 + 48LL))(v56, &v62);
                              v6 = v37;
                              if ( v37 >= 0 )
                              {
                                v38 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v62 + 24LL))(
                                        v62,
                                        &v55);
                                v6 = v38;
                                if ( v38 >= 0 )
                                {
                                  v39 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD))(v54[1] + 24LL))(
                                          v54 + 1,
                                          L"RangeCount",
                                          v55);
                                  v6 = v39;
                                  if ( v39 >= 0 )
                                  {
                                    for ( i = 0; ; ++i )
                                    {
                                      if ( i >= v55 )
                                      {
                                        ++v20;
                                        goto LABEL_34;
                                      }
                                      v68 = 0;
                                      v69 = 0;
                                      if ( v61 )
                                      {
                                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
                                        v61 = 0;
                                      }
                                      v41 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v62 + 32LL))(
                                              v62,
                                              i,
                                              &v61);
                                      v6 = v41;
                                      if ( v41 < 0 )
                                      {
                                        v15 = *((_QWORD *)this + 75);
                                        if ( !v15 )
                                          goto LABEL_4;
                                        LODWORD(cchCount2) = v41;
                                        LODWORD(lpString2) = 9094;
                                        goto LABEL_20;
                                      }
                                      v42 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 24LL))(
                                              v61,
                                              &v68);
                                      v6 = v42;
                                      if ( v42 < 0 )
                                      {
                                        v15 = *((_QWORD *)this + 75);
                                        if ( !v15 )
                                          goto LABEL_4;
                                        LODWORD(cchCount2) = v42;
                                        LODWORD(lpString2) = 9095;
                                        goto LABEL_20;
                                      }
                                      v43 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 32LL))(
                                              v61,
                                              &v69);
                                      v6 = v43;
                                      if ( v43 < 0 )
                                      {
                                        v15 = *((_QWORD *)this + 75);
                                        if ( !v15 )
                                          goto LABEL_4;
                                        LODWORD(cchCount2) = v43;
                                        LODWORD(lpString2) = 9096;
                                        goto LABEL_20;
                                      }
                                      if ( v58 )
                                      {
                                        (*(void (__fastcall **)(_QWORD *))(*v58 + 16LL))(v58);
                                        v58 = 0;
                                      }
                                      v44 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD **))(*v54 + 24LL))(
                                              v54,
                                              L"Range",
                                              &v58);
                                      v6 = v44;
                                      if ( v44 < 0 )
                                      {
                                        v15 = *((_QWORD *)this + 75);
                                        if ( !v15 )
                                          goto LABEL_4;
                                        LODWORD(cchCount2) = v44;
                                        LODWORD(lpString2) = 9099;
                                        goto LABEL_20;
                                      }
                                      v45 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD))(v58[1] + 24LL))(
                                              v58 + 1,
                                              L"RangeCount",
                                              i);
                                      v6 = v45;
                                      if ( v45 < 0 )
                                      {
                                        v15 = *((_QWORD *)this + 75);
                                        if ( !v15 )
                                          goto LABEL_4;
                                        LODWORD(cchCount2) = v45;
                                        LODWORD(lpString2) = 9100;
                                        goto LABEL_20;
                                      }
                                      v46 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD))(v58[1] + 24LL))(
                                              v58 + 1,
                                              L"RangeOffset",
                                              (unsigned int)v68);
                                      v6 = v46;
                                      if ( v46 < 0 )
                                      {
                                        v15 = *((_QWORD *)this + 75);
                                        if ( !v15 )
                                          goto LABEL_4;
                                        LODWORD(cchCount2) = v46;
                                        LODWORD(lpString2) = 9101;
                                        goto LABEL_20;
                                      }
                                      v47 = (*(__int64 (__fastcall **)(_QWORD *, const wchar_t *, _QWORD))(v58[1] + 24LL))(
                                              v58 + 1,
                                              L"RangeLength",
                                              (unsigned int)v69);
                                      v6 = v47;
                                      if ( v47 < 0 )
                                        break;
                                    }
                                    v15 = *((_QWORD *)this + 75);
                                    if ( !v15 )
                                      goto LABEL_4;
                                    LODWORD(cchCount2) = v47;
                                    LODWORD(lpString2) = 9102;
                                  }
                                  else
                                  {
                                    v15 = *((_QWORD *)this + 75);
                                    if ( !v15 )
                                      goto LABEL_4;
                                    LODWORD(cchCount2) = v39;
                                    LODWORD(lpString2) = 9087;
                                  }
                                }
                                else
                                {
                                  v15 = *((_QWORD *)this + 75);
                                  if ( !v15 )
                                    goto LABEL_4;
                                  LODWORD(cchCount2) = v38;
                                  LODWORD(lpString2) = 9086;
                                }
                              }
                              else
                              {
                                v15 = *((_QWORD *)this + 75);
                                if ( !v15 )
                                  goto LABEL_4;
                                LODWORD(cchCount2) = v37;
                                LODWORD(lpString2) = 9085;
                              }
                            }
                            else
                            {
                              v15 = *((_QWORD *)this + 75);
                              if ( !v15 )
                                goto LABEL_4;
                              LODWORD(cchCount2) = v36;
                              LODWORD(lpString2) = 9081;
                            }
                          }
                          else
                          {
                            v15 = *((_QWORD *)this + 75);
                            if ( !v15 )
                              goto LABEL_4;
                            LODWORD(cchCount2) = v35;
                            LODWORD(lpString2) = 9077;
                          }
                        }
                        else
                        {
                          v15 = *((_QWORD *)this + 75);
                          if ( !v15 )
                            goto LABEL_4;
                          LODWORD(cchCount2) = v34;
                          LODWORD(lpString2) = 9076;
                        }
                      }
                      else
                      {
                        v15 = *((_QWORD *)this + 75);
                        if ( !v15 )
                          goto LABEL_4;
                        LODWORD(cchCount2) = v33;
                        LODWORD(lpString2) = 9075;
                      }
                    }
                    else
                    {
                      v15 = *((_QWORD *)this + 75);
                      if ( !v15 )
                        goto LABEL_4;
                      LODWORD(cchCount2) = v32;
                      LODWORD(lpString2) = 9074;
                    }
                  }
                }
                else
                {
                  v15 = *((_QWORD *)this + 75);
                  if ( !v15 )
                    goto LABEL_4;
                  LODWORD(cchCount2) = v30;
                  LODWORD(lpString2) = 9068;
                }
              }
              else
              {
                v15 = *((_QWORD *)this + 75);
                if ( !v15 )
                  goto LABEL_4;
                LODWORD(cchCount2) = v29;
                LODWORD(lpString2) = 9066;
              }
            }
            else
            {
              v15 = *((_QWORD *)this + 75);
              if ( !v15 )
                goto LABEL_4;
              LODWORD(cchCount2) = v28;
              LODWORD(lpString2) = 9065;
            }
          }
          else
          {
            v15 = *((_QWORD *)this + 75);
            if ( !v15 )
              goto LABEL_4;
            LODWORD(cchCount2) = v27;
            LODWORD(lpString2) = 9064;
          }
        }
        else
        {
          v15 = *((_QWORD *)this + 75);
          if ( !v15 )
            goto LABEL_4;
          LODWORD(cchCount2) = v26;
          LODWORD(lpString2) = 9063;
        }
      }
      else
      {
        v15 = *((_QWORD *)this + 75);
        if ( !v15 )
          goto LABEL_4;
        LODWORD(cchCount2) = v25;
        LODWORD(lpString2) = 9062;
      }
    }
LABEL_20:
    updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              v15,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::CreateDownloadList",
                              lpString2,
                              cchCount2);
    goto LABEL_6;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2397,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v49);
  }
  return result;
}

```

## disassembly

```asm
0x18003f0a0  mov     r11, rsp
0x18003f0a3  push    rsi
0x18003f0a4  push    rdi
0x18003f0a5  push    r12
0x18003f0a7  push    r14
0x18003f0a9  push    r15
0x18003f0ab  sub     rsp, 0D0h
0x18003f0b2  mov     [rsp+0F8h+var_C0], 0FFFFFFFFFFFFFFFEh
0x18003f0bb  mov     [r11+18h], rbx
0x18003f0bf  mov     rax, cs:__security_cookie
0x18003f0c6  xor     rax, rsp
0x18003f0c9  mov     [rsp+0F8h+var_38], rax
0x18003f0d1  mov     rsi, rdx
0x18003f0d4  mov     rdi, rcx
0x18003f0d7  xor     r12d, r12d
0x18003f0da  mov     r15d, r12d
0x18003f0dd  mov     [rsp+0F8h+var_C8], r12
0x18003f0e2  mov     [rsp+0F8h+var_B8], r12
0x18003f0e7  mov     [rsp+0F8h+var_98], r12
0x18003f0ec  mov     [r11-50h], r12
0x18003f0f0  mov     [r11-78h], r12
0x18003f0f4  mov     [rsp+0F8h+var_A8], r12
0x18003f0f9  mov     [rsp+0F8h+var_A0], r12
0x18003f0fe  mov     [r11-80h], r12
0x18003f102  mov     [r11-58h], r12
0x18003f106  mov     [r11-60h], r12
0x18003f10a  mov     [r11-68h], r12
0x18003f10e  mov     [r11-70h], r12
0x18003f112  mov     [rsp+0F8h+lpString1], r12
0x18003f117  mov     [rsp+0F8h+var_90], r12d
0x18003f11c  mov     [rsp+0F8h+var_B0], r12d
0x18003f121  mov     [r11-48h], r12
0x18003f125  mov     [r11-40h], r12
0x18003f129  mov     rcx, [rcx+258h]
0x18003f130  test    rdx, rdx
0x18003f133  jnz     short loc_18003F17D
0x18003f135  mov     ebx, 80070057h
0x18003f13a  test    rcx, rcx
0x18003f13d  jnz     short loc_18003F144
0x18003f13f  mov     ecx, r12d
0x18003f142  jmp     short loc_18003F173
0x18003f144  mov     dword ptr [rsp+0F8h+cchCount2], ebx
0x18003f148  mov     dword ptr [rsp+0F8h+lpString2], 2343h
0x18003f150  lea     r9, aCdeploymentses_109; "CDeploymentSession::CreateDownloadList"
0x18003f157  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18003f15e  mov     edx, 4
0x18003f163  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003f168  mov     ecx, eax
0x18003f16a  test    ecx, ecx
0x18003f16c  jns     short loc_18003F173
0x18003f16e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003f173  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003f178  jmp     loc_18003FBF5
0x18003f17d  test    rcx, rcx
0x18003f180  jz      short loc_18003F193
0x18003f182  lea     r8, aCreatedownload; "CreateDownloadList: Enter"
0x18003f189  mov     edx, 2
0x18003f18e  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003f193  lea     rcx, [rsp+0F8h+var_C8]
0x18003f198  call    CreateDlpDownloadListXml
0x18003f19d  mov     ebx, eax
0x18003f19f  test    eax, eax
0x18003f1a1  jns     short loc_18003F1F2
0x18003f1a3  mov     rcx, [rdi+258h]
0x18003f1aa  test    rcx, rcx
0x18003f1ad  jnz     short loc_18003F1B4
0x18003f1af  mov     ecx, r12d
0x18003f1b2  jmp     short loc_18003F1E3
0x18003f1b4  mov     dword ptr [rsp+0F8h+cchCount2], eax
0x18003f1b8  mov     dword ptr [rsp+0F8h+lpString2], 2347h
0x18003f1c0  lea     r9, aCdeploymentses_109; "CDeploymentSession::CreateDownloadList"
0x18003f1c7  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18003f1ce  mov     edx, 4
0x18003f1d3  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003f1d8  mov     ecx, eax
0x18003f1da  test    eax, eax
0x18003f1dc  jns     short loc_18003F1E3
0x18003f1de  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003f1e3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003f1e8  mov     r15, [rsp+0F8h+var_C8]
0x18003f1ed  jmp     loc_18003FBF5
0x18003f1f2  mov     r15, [rsp+0F8h+var_C8]
0x18003f1f7  mov     rax, [r15]
0x18003f1fa  xor     r8d, r8d
0x18003f1fd  mov     rdx, [rdi+1E8h]
0x18003f204  mov     rcx, r15
0x18003f207  mov     rax, [rax+28h]
0x18003f20b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f210  mov     ebx, eax
0x18003f212  test    eax, eax
0x18003f214  jns     short loc_18003F251
0x18003f216  mov     rcx, [rdi+258h]
0x18003f21d  test    rcx, rcx
0x18003f220  jz      loc_18003F13F
0x18003f226  mov     dword ptr [rsp+0F8h+cchCount2], eax
0x18003f22a  mov     dword ptr [rsp+0F8h+lpString2], 2349h
0x18003f232  lea     r9, aCdeploymentses_109; "CDeploymentSession::CreateDownloadList"
0x18003f239  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18003f240  mov     edx, 4
0x18003f245  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003f24a  mov     ecx, eax
0x18003f24c  jmp     loc_18003F16A
0x18003f251  mov     rax, [r15]
0x18003f254  mov     rcx, r15
0x18003f257  mov     rax, [rax+30h]
0x18003f25b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f260  mov     ebx, eax
0x18003f262  test    eax, eax
0x18003f264  jns     short loc_18003F284
0x18003f266  mov     rcx, [rdi+258h]
0x18003f26d  test    rcx, rcx
0x18003f270  jz      loc_18003F13F
0x18003f276  mov     dword ptr [rsp+0F8h+cchCount2], eax
0x18003f27a  mov     dword ptr [rsp+0F8h+lpString2], 234Ah
0x18003f282  jmp     short loc_18003F232
0x18003f284  mov     rax, [rsi]
0x18003f287  lea     rdx, [rsp+0F8h+var_50]
0x18003f28f  mov     rcx, rsi
0x18003f292  mov     rax, [rax+28h]
0x18003f296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f29b  mov     ebx, eax
0x18003f29d  test    eax, eax
0x18003f29f  jns     short loc_18003F2C2
0x18003f2a1  mov     rcx, [rdi+258h]
0x18003f2a8  test    rcx, rcx
0x18003f2ab  jz      loc_18003F13F
0x18003f2b1  mov     dword ptr [rsp+0F8h+cchCount2], eax
0x18003f2b5  mov     dword ptr [rsp+0F8h+lpString2], 234Ch
0x18003f2bd  jmp     loc_18003F232
0x18003f2c2  mov     rcx, [rsp+0F8h+var_50]
0x18003f2ca  mov     rax, [rcx]
0x18003f2cd  lea     rdx, [rsp+0F8h+var_90]
0x18003f2d2  mov     rax, [rax+18h]
0x18003f2d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2db  mov     ebx, eax
0x18003f2dd  test    eax, eax
0x18003f2df  jns     short loc_18003F302
0x18003f2e1  mov     rcx, [rdi+258h]
0x18003f2e8  test    rcx, rcx
0x18003f2eb  jz      loc_18003F13F
0x18003f2f1  mov     dword ptr [rsp+0F8h+cchCount2], eax
0x18003f2f5  mov     dword ptr [rsp+0F8h+lpString2], 234Eh
0x18003f2fd  jmp     loc_18003F232
0x18003f302  lea     rcx, [r15+8]
0x18003f306  mov     rax, [rcx]
0x18003f309  mov     r8d, [rsp+0F8h+var_90]
0x18003f30e  lea     rdx, aFilecount; "FileCount"
0x18003f315  mov     rax, [rax+18h]
0x18003f319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f31e  mov     ebx, eax
0x18003f320  test    eax, eax
0x18003f322  jns     short loc_18003F345
0x18003f324  mov     rcx, [rdi+258h]
0x18003f32b  test    rcx, rcx
0x18003f32e  jz      loc_18003F13F
0x18003f334  mov     dword ptr [rsp+0F8h+cchCount2], eax
0x18003f338  mov     dword ptr [rsp+0F8h+lpString2], 2350h
0x18003f340  jmp     loc_18003F232
0x18003f345  mov     r14d, r12d
0x18003f348  cmp     r14d, [rsp+0F8h+var_90]
0x18003f34d  jnb     loc_18003FBA9
0x18003f353  mov     rcx, [rsp+0F8h+var_A8]
0x18003f358  test    rcx, rcx
0x18003f35b  jz      short loc_18003F36F
0x18003f35d  mov     rax, [rcx]
0x18003f360  mov     rax, [rax+10h]
0x18003f364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f369  nop
0x18003f36a  mov     [rsp+0F8h+var_A8], r12
0x18003f36f  mov     rcx, [rsp+0F8h+var_A0]
0x18003f374  test    rcx, rcx
0x18003f377  jz      short loc_18003F38B
0x18003f379  mov     rax, [rcx]
0x18003f37c  mov     rax, [rax+10h]
0x18003f380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f385  nop
0x18003f386  mov     [rsp+0F8h+var_A0], r12
0x18003f38b  mov     rcx, [rsp+0F8h+var_50]
0x18003f393  mov     rax, [rcx]
0x18003f396  lea     r8, [rsp+0F8h+var_A8]
0x18003f39b  mov     edx, r14d
0x18003f39e  mov     rax, [rax+20h]
0x18003f3a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3a7  mov     ebx, eax
0x18003f3a9  test    eax, eax
0x18003f3ab  jns     short loc_18003F3CE
0x18003f3ad  mov     rcx, [rdi+258h]
0x18003f3b4  test    rcx, rcx
0x18003f3b7  jz      loc_18003F13F
0x18003f3bd  mov     dword ptr [rsp+0F8h+cchCount2], eax
0x18003f3c1  mov     dword ptr [rsp+0F8h+lpString2], 2357h
0x18003f3c9  jmp     loc_18003F232
0x18003f3ce  mov     rcx, [rsp+0F8h+var_A8]
0x18003f3d3  mov     rax, [rcx]
0x18003f3d6  lea     r8, [rsp+0F8h+var_A0]
0x18003f3db  lea     rdx, _GUID_f8293c60_4b0e_4489_ac5d_4eda3a608dd5
0x18003f3e2  mov     rax, [rax]
0x18003f3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3ea  mov     esi, eax
0x18003f3ec  test    eax, eax
0x18003f3ee  jns     short loc_18003F411
0x18003f3f0  mov     rcx, [rdi+258h]
0x18003f3f7  test    rcx, rcx
0x18003f3fa  jnz     short loc_18003F400
0x18003f3fc  mov     ebx, eax
0x18003f3fe  jmp     short loc_18003F417
0x18003f400  lea     r8, aThisVersionOfI; "This version of IDeploymentFileRequest "...
0x18003f407  mov     edx, 2
0x18003f40c  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003f411  mov     ebx, esi
0x18003f413  test    esi, esi
0x18003f415  jns     short loc_18003F438
0x18003f417  mov     rcx, [rdi+258h]
0x18003f41e  test    rcx, rcx
0x18003f421  jz      loc_18003F13F
0x18003f427  mov     dword ptr [rsp+0F8h+cchCount2], esi
0x18003f42b  mov     dword ptr [rsp+0F8h+lpString2], 235Dh
0x18003f433  jmp     loc_18003F232
0x18003f438  mov     rcx, [rsp+0F8h+var_B8]
0x18003f43d  test    rcx, rcx
0x18003f440  jz      short loc_18003F454
0x18003f442  mov     rax, [rcx]
0x18003f445  mov     rax, [rax+10h]
0x18003f449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f44e  nop
0x18003f44f  mov     [rsp+0F8h+var_B8], r12
0x18003f454  mov     rcx, [rsp+0F8h+pv]; pv
0x18003f45c  test    rcx, rcx
0x18003f45f  jz      short loc_18003F475
0x18003f461  call    cs:__imp_CoTaskMemFree
0x18003f468  nop     dword ptr [rax+rax+00h]
0x18003f46d  mov     [rsp+0F8h+pv], r12
0x18003f475  mov     rcx, [rsp+0F8h+var_60]; pv
0x18003f47d  test    rcx, rcx
0x18003f480  jz      short loc_18003F496
0x18003f482  call    cs:__imp_CoTaskMemFree
0x18003f489  nop     dword ptr [rax+rax+00h]
0x18003f48e  mov     [rsp+0F8h+var_60], r12
0x18003f496  mov     rcx, [rsp+0F8h+var_68]; pv
0x18003f49e  test    rcx, rcx
0x18003f4a1  jz      short loc_18003F4B7
0x18003f4a3  call    cs:__imp_CoTaskMemFree
0x18003f4aa  nop     dword ptr [rax+rax+00h]
0x18003f4af  mov     [rsp+0F8h+var_68], r12
0x18003f4b7  mov     rcx, [rsp+0F8h+var_70]; pv
0x18003f4bf  test    rcx, rcx
0x18003f4c2  jz      short loc_18003F4D8
0x18003f4c4  call    cs:__imp_CoTaskMemFree
0x18003f4cb  nop     dword ptr [rax+rax+00h]
0x18003f4d0  mov     [rsp+0F8h+var_70], r12
0x18003f4d8  mov     rcx, [rsp+0F8h+lpString1]; pv
0x18003f4dd  test    rcx, rcx
0x18003f4e0  jz      short loc_18003F4F3
0x18003f4e2  call    cs:__imp_CoTaskMemFree
0x18003f4e9  nop     dword ptr [rax+rax+00h]
0x18003f4ee  mov     [rsp+0F8h+lpString1], r12
0x18003f4f3  mov     rcx, [rsp+0F8h+var_A8]
0x18003f4f8  mov     rax, [rcx]
0x18003f4fb  lea     rdx, [rsp+0F8h+pv]
0x18003f503  mov     rax, [rax+18h]
0x18003f507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f50c  mov     ebx, eax
0x18003f50e  test    eax, eax
0x18003f510  jns     short loc_18003F533
0x18003f512  mov     rcx, [rdi+258h]
0x18003f519  test    rcx, rcx
0x18003f51c  jz      loc_18003F13F
0x18003f522  mov     dword ptr [rsp+0F8h+cchCount2], eax
0x18003f526  mov     dword ptr [rsp+0F8h+lpString2], 2366h
0x18003f52e  jmp     loc_18003F232
0x18003f533  mov     rcx, [rsp+0F8h+var_A8]
0x18003f538  mov     rax, [rcx]
0x18003f53b  lea     rdx, [rsp+0F8h+var_60]
0x18003f543  mov     rax, [rax+28h]
0x18003f547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f54c  mov     ebx, eax
0x18003f54e  test    eax, eax
0x18003f550  jns     short loc_18003F573
0x18003f552  mov     rcx, [rdi+258h]
0x18003f559  test    rcx, rcx
0x18003f55c  jz      loc_18003F13F
0x18003f562  mov     dword ptr [rsp+0F8h+cchCount2], eax
0x18003f566  mov     dword ptr [rsp+0F8h+lpString2], 2367h
0x18003f56e  jmp     loc_18003F232
0x18003f573  mov     rcx, [rsp+0F8h+var_A0]
0x18003f578  mov     rax, [rcx]
0x18003f57b  lea     rdx, [rsp+0F8h+var_68]
0x18003f583  mov     rax, [rax+38h]
0x18003f587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f58c  mov     ebx, eax
0x18003f58e  test    eax, eax
0x18003f590  jns     short loc_18003F5B3
0x18003f592  mov     rcx, [rdi+258h]
0x18003f599  test    rcx, rcx
0x18003f59c  jz      loc_18003F13F
0x18003f5a2  mov     dword ptr [rsp+0F8h+cchCount2], eax
0x18003f5a6  mov     dword ptr [rsp+0F8h+lpString2], 2368h
0x18003f5ae  jmp     loc_18003F232
0x18003f5b3  mov     rcx, [rsp+0F8h+var_A0]
0x18003f5b8  mov     rax, [rcx]
  ... truncated ...
```
