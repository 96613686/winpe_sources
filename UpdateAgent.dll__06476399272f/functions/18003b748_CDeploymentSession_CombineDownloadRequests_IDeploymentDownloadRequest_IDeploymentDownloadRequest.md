# CDeploymentSession::CombineDownloadRequests(IDeploymentDownloadRequest *,IDeploymentDownloadRequest *)

- ea: `0x18003b748`
- end: `0x18003c410`
- name: `?CombineDownloadRequests@CDeploymentSession@@QEAAJPEAUIDeploymentDownloadRequest@@0@Z`
- size: `3272`
- prototype: `__int64 __fastcall(CDeploymentSession *__hidden this, struct IDeploymentDownloadRequest *, struct IDeploymentDownloadRequest *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18002b4b8`

## callees

- `0x1800059d0`
- `0x180034218`
- `0x180035b4c`
- `0x180035bf0`
- `0x180039f90`
- `0x18003b748`
- `0x18003e4a4`
- `0x18003e600`
- `0x180077664`
- `0x180078b9c`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ba2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ba4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ba6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ba90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c2aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c2cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c2ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c30d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ba2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ba4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ba6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ba90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bab1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c289`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c2aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c2cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c2ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c30d`

## string_xrefs

- `0x18003b814`: `CDeploymentSession::CombineDownloadRequests`
- `0x18003b8a9`: `CDeploymentSession::CombineDownloadRequests`
- `0x18003b910`: `CDeploymentSession::CombineDownloadRequests`
- `0x18003b854`: `CombineDownloadRequests: Enter`
- `0x18003bfae`: `CombineDownloadRequests: Adding additional [%llu] to size.`
- `0x18003c002`: `CombineDownloadRequests: Plugin DownloadProgress [%d]`
- `0x18003c03a`: `CombineDownloadRequests: OS Request Size [%llu]`
- `0x18003c0ac`: `CombineDownloadRequests: OS Request with Plugins [%llu] `
- `0x18003c212`: `CombineDownloadRequests: Total DownloadProgress [%llu]`
- `0x18003c260`: `CombineDownloadRequests: Exit`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall CDeploymentSession::CombineDownloadRequests(
        CDeploymentSession *this,
        struct IDeploymentDownloadRequest *a2,
        struct IDeploymentDownloadRequest *a3)
{
  wchar_t *v5; // r12
  struct CDeploymentFileRequest *v6; // r13
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  int updated; // eax
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  unsigned int v16; // r15d
  int v17; // eax
  int v18; // eax
  int v19; // esi
  __int64 v20; // rcx
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  unsigned int v30; // esi
  struct CDeploymentFileRequest *v31; // r12
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  struct CDeploymentFileRange *v36; // rax
  int appended; // eax
  struct CDeploymentFileRequest *v38; // rax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  __int64 v42; // rcx
  unsigned __int64 v43; // rcx
  unsigned __int64 v44; // r15
  __int64 v45; // rcx
  unsigned __int64 v46; // r14
  __int64 v47; // rdx
  unsigned __int64 v48; // r15
  __int64 v49; // rcx
  unsigned __int64 v50; // rax
  unsigned __int64 v51; // rbx
  int v52; // eax
  __int64 v53; // rcx
  const char *v54; // r9
  __int64 result; // rax
  wchar_t *v56; // [rsp+20h] [rbp-108h]
  __int64 v57; // [rsp+28h] [rbp-100h]
  struct CDeploymentFileRequest *v58; // [rsp+40h] [rbp-E8h] BYREF
  struct CDeploymentFileRange *v59; // [rsp+48h] [rbp-E0h] BYREF
  struct CDeploymentFileRange *v60; // [rsp+50h] [rbp-D8h] BYREF
  CDeploymentDownloadRequest *v61; // [rsp+58h] [rbp-D0h]
  __int64 v62; // [rsp+60h] [rbp-C8h]
  wchar_t *v63; // [rsp+68h] [rbp-C0h] BYREF
  unsigned int v64; // [rsp+70h] [rbp-B8h] BYREF
  unsigned int v65; // [rsp+74h] [rbp-B4h] BYREF
  wchar_t *v66; // [rsp+78h] [rbp-B0h] BYREF
  wchar_t *v67; // [rsp+80h] [rbp-A8h] BYREF
  wchar_t *v68; // [rsp+88h] [rbp-A0h] BYREF
  wchar_t *v69; // [rsp+90h] [rbp-98h] BYREF
  wchar_t *v70; // [rsp+98h] [rbp-90h] BYREF
  wchar_t *v71; // [rsp+A0h] [rbp-88h] BYREF
  wchar_t *v72; // [rsp+A8h] [rbp-80h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-78h] BYREF
  unsigned int v74; // [rsp+B8h] [rbp-70h] BYREF
  int v75; // [rsp+BCh] [rbp-6Ch] BYREF
  unsigned __int64 v76; // [rsp+C0h] [rbp-68h] BYREF
  __int64 v77; // [rsp+C8h] [rbp-60h] BYREF
  unsigned __int64 v78; // [rsp+D0h] [rbp-58h] BYREF
  unsigned __int64 v79; // [rsp+D8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v62 = -2;
  try
  {
    v61 = a2;
    v5 = 0;
    v77 = 0;
    v63 = 0;
    v66 = 0;
    v68 = 0;
    v67 = 0;
    v6 = 0;
    v58 = 0;
    v60 = 0;
    v74 = 0;
    v65 = 0;
    v79 = 0;
    v78 = 0;
    v76 = 0;
    v75 = 0;
    pv = 0;
    v72 = 0;
    v71 = 0;
    v70 = 0;
    v69 = 0;
    v64 = 0;
    v7 = *((_QWORD *)this + 75);
    if ( !a2 )
    {
      v8 = -2147024809;
      if ( v7 )
      {
        updated = CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                    v7,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDeploymentSession::CombineDownloadRequests",
                    8564,
                    -2147024809);
        v9 = (unsigned int)updated;
        if ( updated < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)updated);
      }
      else
      {
        v9 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
      goto LABEL_157;
    }
    v64 = 100;
    if ( v7 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v7, 2, L"CombineDownloadRequests: Enter");
    v8 = 0;
    if ( a3 )
    {
      v11 = (*(__int64 (__fastcall **)(struct IDeploymentDownloadRequest *, __int64 *))(*(_QWORD *)a3 + 40LL))(a3, &v77);
      v8 = v11;
      if ( v11 < 0 )
      {
        v12 = *((_QWORD *)this + 75);
        if ( !v12 )
        {
LABEL_13:
          v13 = 0;
LABEL_17:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v13);
LABEL_156:
          v6 = v58;
LABEL_157:
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
          if ( v69 )
          {
            CoTaskMemFree(v69);
            v69 = v5;
          }
          if ( v70 )
          {
            CoTaskMemFree(v70);
            v70 = v5;
          }
          if ( v71 )
          {
            CoTaskMemFree(v71);
            v71 = v5;
          }
          if ( v72 )
          {
            CoTaskMemFree(v72);
            v72 = v5;
          }
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = v5;
          }
          if ( v60 )
            (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v60 + 16LL))(v60);
          if ( v6 )
            (*(void (__fastcall **)(struct CDeploymentFileRequest *))(*(_QWORD *)v6 + 16LL))(v6);
          if ( v67 )
          {
            (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v67 + 16LL))(v67);
            v67 = v5;
          }
          if ( v68 )
          {
            (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v68 + 16LL))(v68);
            v68 = v5;
          }
          if ( v66 )
          {
            (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v66 + 16LL))(v66);
            v66 = v5;
          }
          if ( v63 )
          {
            (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v63 + 16LL))(v63);
            v63 = v5;
          }
          if ( v77 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
          return (unsigned int)v8;
        }
        v13 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              v12,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::CombineDownloadRequests",
                              8577,
                              v11);
LABEL_15:
        if ( (int)v13 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v13);
        goto LABEL_17;
      }
      v14 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v77 + 24LL))(v77, &v74);
      v8 = v14;
      if ( v14 < 0 )
      {
        v15 = *((_QWORD *)this + 75);
        if ( !v15 )
          goto LABEL_13;
        LODWORD(v57) = v14;
        LODWORD(v56) = 8578;
        goto LABEL_21;
      }
      v16 = 0;
      while ( 2 )
      {
        if ( v16 < v74 )
        {
          if ( v63 )
          {
            (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v63 + 16LL))(v63);
            v63 = 0;
          }
          if ( v66 )
          {
            (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v66 + 16LL))(v66);
            v66 = 0;
          }
          v17 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)v77 + 32LL))(v77, v16, &v63);
          v8 = v17;
          if ( v17 < 0 )
          {
            v15 = *((_QWORD *)this + 75);
            if ( !v15 )
              goto LABEL_13;
            LODWORD(v57) = v17;
            LODWORD(v56) = 8585;
            goto LABEL_21;
          }
          v18 = (**(__int64 (__fastcall ***)(wchar_t *, GUID *, wchar_t **))v63)(
                  v63,
                  &GUID_f8293c60_4b0e_4489_ac5d_4eda3a608dd5,
                  &v66);
          v19 = v18;
          if ( v18 < 0 )
          {
            v20 = *((_QWORD *)this + 75);
            if ( !v20 )
            {
              v8 = v18;
LABEL_36:
              v15 = *((_QWORD *)this + 75);
              if ( !v15 )
                goto LABEL_13;
              LODWORD(v57) = v19;
              LODWORD(v56) = 8591;
              goto LABEL_21;
            }
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v20,
              2,
              L"This version of IDeploymentFileRequest is not supported");
          }
          v8 = v19;
          if ( v19 < 0 )
            goto LABEL_36;
          if ( pv )
          {
            CoTaskMemFree(pv);
            pv = 0;
          }
          if ( v72 )
          {
            CoTaskMemFree(v72);
            v72 = 0;
          }
          if ( v71 )
          {
            CoTaskMemFree(v71);
            v71 = 0;
          }
          if ( v70 )
          {
            CoTaskMemFree(v70);
            v70 = 0;
          }
          if ( v69 )
          {
            CoTaskMemFree(v69);
            v69 = 0;
          }
          v21 = (*(__int64 (__fastcall **)(wchar_t *, LPVOID *))(*(_QWORD *)v63 + 24LL))(v63, &pv);
          v8 = v21;
          if ( v21 >= 0 )
          {
            v22 = (*(__int64 (__fastcall **)(wchar_t *, wchar_t **))(*(_QWORD *)v63 + 40LL))(v63, &v72);
            v8 = v22;
            if ( v22 >= 0 )
            {
              v23 = (*(__int64 (__fastcall **)(wchar_t *, wchar_t **))(*(_QWORD *)v66 + 56LL))(v66, &v71);
              v8 = v23;
              if ( v23 >= 0 )
              {
                v24 = (*(__int64 (__fastcall **)(wchar_t *, wchar_t **))(*(_QWORD *)v66 + 64LL))(v66, &v70);
                v8 = v24;
                if ( v24 >= 0 )
                {
                  v25 = (*(__int64 (__fastcall **)(wchar_t *, wchar_t **))(*(_QWORD *)v66 + 72LL))(v66, &v69);
                  v8 = v25;
                  if ( v25 >= 0 )
                  {
                    v26 = (*(__int64 (__fastcall **)(wchar_t *, int *))(*(_QWORD *)v63 + 32LL))(v63, &v75);
                    v8 = v26;
                    if ( v26 >= 0 )
                    {
                      v27 = CDeploymentFileRequest::Create((const wchar_t *)pv, v72, v71, v70, v69, v75, &v58);
                      v8 = v27;
                      if ( v27 >= 0 )
                      {
                        if ( v68 )
                        {
                          (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v68 + 16LL))(v68);
                          v68 = 0;
                        }
                        v28 = (*(__int64 (__fastcall **)(wchar_t *, wchar_t **))(*(_QWORD *)v63 + 48LL))(v63, &v68);
                        v8 = v28;
                        if ( v28 >= 0 )
                        {
                          v29 = (*(__int64 (__fastcall **)(wchar_t *, unsigned int *))(*(_QWORD *)v68 + 24LL))(
                                  v68,
                                  &v65);
                          v8 = v29;
                          if ( v29 >= 0 )
                          {
                            v30 = 0;
                            v31 = v58;
                            while ( v30 < v65 )
                            {
                              if ( v67 )
                              {
                                (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v67 + 16LL))(v67);
                                v67 = 0;
                              }
                              v32 = (*(__int64 (__fastcall **)(wchar_t *, _QWORD, wchar_t **))(*(_QWORD *)v68 + 32LL))(
                                      v68,
                                      v30,
                                      &v67);
                              v8 = v32;
                              if ( v32 < 0 )
                              {
                                v15 = *((_QWORD *)this + 75);
                                v5 = 0;
                                if ( !v15 )
                                  goto LABEL_13;
                                LODWORD(v57) = v32;
                                LODWORD(v56) = 8615;
                                goto LABEL_21;
                              }
                              v33 = (*(__int64 (__fastcall **)(wchar_t *, unsigned __int64 *))(*(_QWORD *)v67 + 24LL))(
                                      v67,
                                      &v79);
                              v8 = v33;
                              if ( v33 < 0 )
                              {
                                v15 = *((_QWORD *)this + 75);
                                v5 = 0;
                                if ( !v15 )
                                  goto LABEL_13;
                                LODWORD(v57) = v33;
                                LODWORD(v56) = 8616;
                                goto LABEL_21;
                              }
                              v34 = (*(__int64 (__fastcall **)(wchar_t *, unsigned __int64 *))(*(_QWORD *)v67 + 32LL))(
                                      v67,
                                      &v78);
                              v8 = v34;
                              if ( v34 < 0 )
                              {
                                v15 = *((_QWORD *)this + 75);
                                v5 = 0;
                                if ( !v15 )
                                  goto LABEL_13;
                                LODWORD(v57) = v34;
                                LODWORD(v56) = 8617;
                                goto LABEL_21;
                              }
                              if ( v60 )
                              {
                                (*(void (__fastcall **)(struct CDeploymentFileRange *))(*(_QWORD *)v60 + 16LL))(v60);
                                v60 = 0;
                              }
                              v35 = CDeploymentFileRange::Create(v79, v78, &v60);
                              v8 = v35;
                              if ( v35 < 0 )
                              {
                                v15 = *((_QWORD *)this + 75);
                                v5 = 0;
                                if ( !v15 )
                                  goto LABEL_13;
                                LODWORD(v57) = v35;
                                LODWORD(v56) = 8620;
                                goto LABEL_21;
                              }
                              v36 = v60;
                              v60 = 0;
                              v59 = v36;
                              appended = CDeploymentFileRequest::AppendFileRange(v31, &v59);
                              v8 = appended;
                              if ( appended < 0 )
                              {
                                v15 = *((_QWORD *)this + 75);
                                v5 = 0;
                                if ( !v15 )
                                  goto LABEL_13;
                                LODWORD(v57) = appended;
                                LODWORD(v56) = 8622;
                                goto LABEL_21;
                              }
                              ++v30;
                            }
                            v38 = v31;
                            v5 = 0;
                            v58 = 0;
                            v59 = v38;
                            v39 = CDeploymentDownloadRequest::AppendFileRequest(v61, &v59);
                            v8 = v39;
                            if ( v39 >= 0 )
                            {
                              ++v16;
                              continue;
                            }
                            v15 = *((_QWORD *)this + 75);
                            if ( !v15 )
                              goto LABEL_13;
                            LODWORD(v57) = v39;
                            LODWORD(v56) = 8625;
                          }
                          else
                          {
                            v15 = *((_QWORD *)this + 75);
                            if ( !v15 )
                              goto LABEL_13;
                            LODWORD(v57) = v29;
                            LODWORD(v56) = 8611;
                          }
                        }
                        else
                        {
                          v15 = *((_QWORD *)this + 75);
                          if ( !v15 )
                            goto LABEL_13;
                          LODWORD(v57) = v28;
                          LODWORD(v56) = 8610;
                        }
                      }
                      else
                      {
                        v15 = *((_QWORD *)this + 75);
                        if ( !v15 )
                          goto LABEL_13;
                        LODWORD(v57) = v27;
                        LODWORD(v56) = 8607;
                      }
                    }
                    else
                    {
                      v15 = *((_QWORD *)this + 75);
                      if ( !v15 )
                        goto LABEL_13;
                      LODWORD(v57) = v26;
                      LODWORD(v56) = 8604;
                    }
                  }
                  else
                  {
                    v15 = *((_QWORD *)this + 75);
                    if ( !v15 )
                      goto LABEL_13;
                    LODWORD(v57) = v25;
                    LODWORD(v56) = 8603;
                  }
                }
                else
                {
                  v15 = *((_QWORD *)this + 75);
                  if ( !v15 )
                    goto LABEL_13;
                  LODWORD(v57) = v24;
                  LODWORD(v56) = 8602;
                }
              }
              else
              {
                v15 = *((_QWORD *)this + 75);
                if ( !v15 )
                  goto LABEL_13;
                LODWORD(v57) = v23;
                LODWORD(v56) = 8601;
              }
            }
            else
            {
              v15 = *((_QWORD *)this + 75);
              if ( !v15 )
                goto LABEL_13;
              LODWORD(v57) = v22;
              LODWORD(v56) = 8600;
            }
          }
          else
          {
            v15 = *((_QWORD *)this + 75);
            if ( !v15 )
              goto LABEL_13;
            LODWORD(v57) = v21;
            LODWORD(v56) = 8599;
          }
LABEL_21:
          v13 = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                v15,
                                4,
                                L"%s(%d): Result = 0x%X",
                                L"CDeploymentSession::CombineDownloadRequests",
                                v56,
                                v57);
          goto LABEL_15;
        }
        break;
      }
      v40 = (*(__int64 (__fastcall **)(struct IDeploymentDownloadRequest *, unsigned __int64 *))(*(_QWORD *)a3 + 56LL))(
              a3,
              &v76);
      v8 = v40;
      v15 = *((_QWORD *)this + 75);
      if ( v40 < 0 )
      {
        if ( !v15 )
          goto LABEL_13;
        LODWORD(v57) = v40;
        LODWORD(v56) = 8628;
        goto LABEL_21;
      }
      if ( v15 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v15,
          2,
          L"CombineDownloadRequests: Adding additional [%llu] to size.",
          v76);
      v41 = (*(__int64 (__fastcall **)(struct IDeploymentDownloadRequest *, unsigned int *))(*(_QWORD *)a3 + 32LL))(
              a3,
              &v64);
      v8 = v41;
      v15 = *((_QWORD *)this + 75);
      if ( v41 < 0 )
      {
        if ( !v15 )
          goto LABEL_13;
        LODWORD(v57) = v41;
        LODWORD(v56) = 8631;
        goto LABEL_21;
      }
      if ( v15 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v15,
          2,
          L"CombineDownloadRequests: Plugin DownloadProgress [%d]",
          v64);
    }
    if ( !*((_QWORD *)this + 47) || *((_DWORD *)this + 71) )
      goto LABEL_154;
    v42 = *((_QWORD *)this + 75);
    if ( v42 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v42, 2, L"CombineDownloadRequests: OS Request Size [%llu]");
    v43 = *((_QWORD *)this + 47);
    v5 = (wchar_t *)(v43 + v76);
    if ( v43 + v76 < v43 )
    {
      v5 = 0;
      v8 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
    }
    else
    {
      v8 = 0;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
    v15 = *((_QWORD *)this + 75);
    if ( v8 < 0 )
    {
      v5 = 0;
      if ( !v15 )
        goto LABEL_13;
      LODWORD(v57) = v8;
      LODWORD(v56) = 8639;
      goto LABEL_21;
    }
    if ( v15 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v15,
        2,
        L"CombineDownloadRequests: OS Request with Plugins [%llu] ",
        v5);
    if ( !v5 )
    {
LABEL_154:
      v53 = *((_QWORD *)this + 75);
      if ( v53 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v53, 2, L"CombineDownloadRequests: Exit");
      goto LABEL_156;
    }
    if ( v64 && v76 )
    {
      v44 = v76 * v64;
      if ( v44 / v76 != v64 )
      {
        v44 = 0;
        v8 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        goto LABEL_132;
      }
    }
    else
    {
      v44 = 0;
    }
    v8 = 0;
LABEL_132:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
    if ( v8 < 0 )
    {
      v15 = *((_QWORD *)this + 75);
      v5 = 0;
      if ( !v15 )
        goto LABEL_13;
      LODWORD(v57) = v8;
      LODWORD(v56) = 8645;
      goto LABEL_21;
    }
    v45 = *((_QWORD *)this + 47);
    if ( v45 )
    {
      v46 = 100 * v45;
      v47 = ((unsigned __int64)(100 * v45) * (unsigned __int128)0x47AE147AE147AE15uLL) >> 64;
      if ( (v47 + ((unsigned __int64)(100 * v45 - v47) >> 1)) >> 6 != v45 )
      {
        v46 = 0;
        v8 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
        goto LABEL_140;
      }
    }
    else
    {
      v46 = 0;
    }
    v8 = 0;
LABEL_140:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
    if ( v8 < 0 )
    {
      v15 = *((_QWORD *)this + 75);
      v5 = 0;
      if ( !v15 )
        goto LABEL_13;
      LODWORD(v57) = v8;
      LODWORD(v56) = 8646;
      goto LABEL_21;
    }
    v48 = v46 + v44;
    if ( v48 < v46 )
    {
      v48 = 0;
      v8 = -2147024362;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
    }
    else
    {
      v8 = 0;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v8);
    if ( v8 < 0 )
    {
      v15 = *((_QWORD *)this + 75);
      v5 = 0;
      if ( !v15 )
        goto LABEL_13;
      LODWORD(v57) = v8;
      LODWORD(v56) = 8647;
      goto LABEL_21;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    v49 = *((_QWORD *)this + 75);
    v50 = v48 / (unsigned __int64)v5;
    v51 = v48 / (unsigned __int64)v5;
    v5 = 0;
    if ( v49 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
        v49,
        2,
        L"CombineDownloadRequests: Total DownloadProgress [%llu]",
        v50);
    v52 = CDeploymentDownloadRequest::AddDownloadProgress(v61, v51);
    v8 = v52;
    if ( v52 < 0 )
    {
      v15 = *((_QWORD *)this + 75);
      if ( !v15 )
        goto LABEL_13;
      LODWORD(v57) = v52;
      LODWORD(v56) = 8652;
      goto LABEL_21;
    }
    goto LABEL_154;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x21D4,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v54);
  }
  return result;
}

```

## disassembly

```asm
0x18003b748  mov     r11, rsp
0x18003b74b  push    rbx
0x18003b74c  push    rsi
0x18003b74d  push    rdi
0x18003b74e  push    r12
0x18003b750  push    r13
0x18003b752  push    r14
0x18003b754  push    r15
0x18003b756  sub     rsp, 0F0h
0x18003b75d  mov     [rsp+128h+var_C8], 0FFFFFFFFFFFFFFFEh
0x18003b766  mov     rax, cs:__security_cookie
0x18003b76d  xor     rax, rsp
0x18003b770  mov     [rsp+128h+var_48], rax
0x18003b778  mov     r14, r8
0x18003b77b  mov     rax, rdx
0x18003b77e  mov     [rsp+128h+var_D0], rdx
0x18003b783  mov     rdi, rcx
0x18003b786  xor     r12d, r12d
0x18003b789  mov     [r11-60h], r12
0x18003b78d  mov     [rsp+128h+var_C0], r12
0x18003b792  mov     [rsp+128h+var_B0], r12
0x18003b797  mov     [r11-0A0h], r12
0x18003b79e  mov     [r11-0A8h], r12
0x18003b7a5  mov     r13d, r12d
0x18003b7a8  mov     [rsp+128h+var_E8], r12
0x18003b7ad  mov     [rsp+128h+var_D8], r12
0x18003b7b2  mov     [r11-70h], r12d
0x18003b7b6  mov     [rsp+128h+var_B4], r12d
0x18003b7bb  mov     [r11-50h], r12
0x18003b7bf  mov     [r11-58h], r12
0x18003b7c3  mov     [r11-68h], r12
0x18003b7c7  mov     [r11-6Ch], r12d
0x18003b7cb  mov     [r11-78h], r12
0x18003b7cf  mov     [r11-80h], r12
0x18003b7d3  mov     [r11-88h], r12
0x18003b7da  mov     [r11-90h], r12
0x18003b7e1  mov     [r11-98h], r12
0x18003b7e8  mov     [rsp+128h+var_B8], r12d
0x18003b7ed  mov     rcx, [rcx+258h]
0x18003b7f4  test    rax, rax
0x18003b7f7  jnz     short loc_18003B841
0x18003b7f9  mov     ebx, 80070057h
0x18003b7fe  test    rcx, rcx
0x18003b801  jnz     short loc_18003B808
0x18003b803  mov     ecx, r12d
0x18003b806  jmp     short loc_18003B837
0x18003b808  mov     dword ptr [rsp+128h+var_100], ebx
0x18003b80c  mov     dword ptr [rsp+128h+var_108], 2174h
0x18003b814  lea     r9, aCdeploymentses_19; "CDeploymentSession::CombineDownloadRequ"...
0x18003b81b  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18003b822  mov     edx, 4
0x18003b827  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003b82c  mov     ecx, eax
0x18003b82e  test    eax, eax
0x18003b830  jns     short loc_18003B837
0x18003b832  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b837  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b83c  jmp     loc_18003C274
0x18003b841  mov     [rsp+128h+var_B8], 64h ; 'd'
0x18003b849  mov     r13d, 2
0x18003b84f  test    rcx, rcx
0x18003b852  jz      short loc_18003B863
0x18003b854  lea     r8, aCombinedownloa_4; "CombineDownloadRequests: Enter"
0x18003b85b  mov     edx, r13d
0x18003b85e  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003b863  mov     ebx, r12d
0x18003b866  test    r14, r14
0x18003b869  jz      loc_18003C011
0x18003b86f  mov     rax, [r14]
0x18003b872  lea     rdx, [rsp+128h+var_60]
0x18003b87a  mov     rcx, r14
0x18003b87d  mov     rax, [rax+28h]
0x18003b881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b886  mov     ebx, eax
0x18003b888  test    eax, eax
0x18003b88a  jns     short loc_18003B8D6
0x18003b88c  mov     rcx, [rdi+258h]
0x18003b893  test    rcx, rcx
0x18003b896  jnz     short loc_18003B89D
0x18003b898  mov     ecx, r12d
0x18003b89b  jmp     short loc_18003B8CC
0x18003b89d  mov     dword ptr [rsp+128h+var_100], eax
0x18003b8a1  mov     dword ptr [rsp+128h+var_108], 2181h
0x18003b8a9  lea     r9, aCdeploymentses_19; "CDeploymentSession::CombineDownloadRequ"...
0x18003b8b0  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18003b8b7  mov     edx, 4
0x18003b8bc  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003b8c1  mov     ecx, eax
0x18003b8c3  test    ecx, ecx
0x18003b8c5  jns     short loc_18003B8CC
0x18003b8c7  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003b8cc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003b8d1  jmp     loc_18003C26F
0x18003b8d6  mov     rcx, [rsp+128h+var_60]
0x18003b8de  mov     rax, [rcx]
0x18003b8e1  lea     rdx, [rsp+128h+var_70]
0x18003b8e9  mov     rax, [rax+18h]
0x18003b8ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8f2  mov     ebx, eax
0x18003b8f4  test    eax, eax
0x18003b8f6  jns     short loc_18003B92C
0x18003b8f8  mov     rcx, [rdi+258h]
0x18003b8ff  test    rcx, rcx
0x18003b902  jz      short loc_18003B898
0x18003b904  mov     dword ptr [rsp+128h+var_100], eax
0x18003b908  mov     dword ptr [rsp+128h+var_108], 2182h
0x18003b910  lea     r9, aCdeploymentses_19; "CDeploymentSession::CombineDownloadRequ"...
0x18003b917  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18003b91e  mov     edx, 4
0x18003b923  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003b928  mov     ecx, eax
0x18003b92a  jmp     short loc_18003B8C3
0x18003b92c  mov     r15d, r12d
0x18003b92f  cmp     r15d, [rsp+128h+var_70]
0x18003b937  jnb     loc_18003BF63
0x18003b93d  mov     rcx, [rsp+128h+var_C0]
0x18003b942  test    rcx, rcx
0x18003b945  jz      short loc_18003B959
0x18003b947  mov     rax, [rcx]
0x18003b94a  mov     rax, [rax+10h]
0x18003b94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b953  nop
0x18003b954  mov     [rsp+128h+var_C0], r12
0x18003b959  mov     rcx, [rsp+128h+var_B0]
0x18003b95e  test    rcx, rcx
0x18003b961  jz      short loc_18003B975
0x18003b963  mov     rax, [rcx]
0x18003b966  mov     rax, [rax+10h]
0x18003b96a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b96f  nop
0x18003b970  mov     [rsp+128h+var_B0], r12
0x18003b975  mov     rcx, [rsp+128h+var_60]
0x18003b97d  mov     rax, [rcx]
0x18003b980  lea     r8, [rsp+128h+var_C0]
0x18003b985  mov     edx, r15d
0x18003b988  mov     rax, [rax+20h]
0x18003b98c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b991  mov     ebx, eax
0x18003b993  test    eax, eax
0x18003b995  jns     short loc_18003B9B8
0x18003b997  mov     rcx, [rdi+258h]
0x18003b99e  test    rcx, rcx
0x18003b9a1  jz      loc_18003B898
0x18003b9a7  mov     dword ptr [rsp+128h+var_100], eax
0x18003b9ab  mov     dword ptr [rsp+128h+var_108], 2189h
0x18003b9b3  jmp     loc_18003B910
0x18003b9b8  mov     rcx, [rsp+128h+var_C0]
0x18003b9bd  mov     rax, [rcx]
0x18003b9c0  lea     r8, [rsp+128h+var_B0]
0x18003b9c5  lea     rdx, _GUID_f8293c60_4b0e_4489_ac5d_4eda3a608dd5
0x18003b9cc  mov     rax, [rax]
0x18003b9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b9d4  mov     esi, eax
0x18003b9d6  test    eax, eax
0x18003b9d8  jns     short loc_18003B9F9
0x18003b9da  mov     rcx, [rdi+258h]
0x18003b9e1  test    rcx, rcx
0x18003b9e4  jnz     short loc_18003B9EA
0x18003b9e6  mov     ebx, eax
0x18003b9e8  jmp     short loc_18003B9FF
0x18003b9ea  lea     r8, aThisVersionOfI; "This version of IDeploymentFileRequest "...
0x18003b9f1  mov     edx, r13d
0x18003b9f4  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18003b9f9  mov     ebx, esi
0x18003b9fb  test    esi, esi
0x18003b9fd  jns     short loc_18003BA20
0x18003b9ff  mov     rcx, [rdi+258h]
0x18003ba06  test    rcx, rcx
0x18003ba09  jz      loc_18003B898
0x18003ba0f  mov     dword ptr [rsp+128h+var_100], esi
0x18003ba13  mov     dword ptr [rsp+128h+var_108], 218Fh
0x18003ba1b  jmp     loc_18003B910
0x18003ba20  mov     rcx, [rsp+128h+pv]; pv
0x18003ba28  test    rcx, rcx
0x18003ba2b  jz      short loc_18003BA41
0x18003ba2d  call    cs:__imp_CoTaskMemFree
0x18003ba34  nop     dword ptr [rax+rax+00h]
0x18003ba39  mov     [rsp+128h+pv], r12
0x18003ba41  mov     rcx, [rsp+128h+var_80]; pv
0x18003ba49  test    rcx, rcx
0x18003ba4c  jz      short loc_18003BA62
0x18003ba4e  call    cs:__imp_CoTaskMemFree
0x18003ba55  nop     dword ptr [rax+rax+00h]
0x18003ba5a  mov     [rsp+128h+var_80], r12
0x18003ba62  mov     rcx, [rsp+128h+var_88]; pv
0x18003ba6a  test    rcx, rcx
0x18003ba6d  jz      short loc_18003BA83
0x18003ba6f  call    cs:__imp_CoTaskMemFree
0x18003ba76  nop     dword ptr [rax+rax+00h]
0x18003ba7b  mov     [rsp+128h+var_88], r12
0x18003ba83  mov     rcx, [rsp+128h+var_90]; pv
0x18003ba8b  test    rcx, rcx
0x18003ba8e  jz      short loc_18003BAA4
0x18003ba90  call    cs:__imp_CoTaskMemFree
0x18003ba97  nop     dword ptr [rax+rax+00h]
0x18003ba9c  mov     [rsp+128h+var_90], r12
0x18003baa4  mov     rcx, [rsp+128h+var_98]; pv
0x18003baac  test    rcx, rcx
0x18003baaf  jz      short loc_18003BAC5
0x18003bab1  call    cs:__imp_CoTaskMemFree
0x18003bab8  nop     dword ptr [rax+rax+00h]
0x18003babd  mov     [rsp+128h+var_98], r12
0x18003bac5  mov     rcx, [rsp+128h+var_C0]
0x18003baca  mov     rax, [rcx]
0x18003bacd  lea     rdx, [rsp+128h+pv]
0x18003bad5  mov     rax, [rax+18h]
0x18003bad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bade  mov     ebx, eax
0x18003bae0  test    eax, eax
0x18003bae2  jns     short loc_18003BB05
0x18003bae4  mov     rcx, [rdi+258h]
0x18003baeb  test    rcx, rcx
0x18003baee  jz      loc_18003B898
0x18003baf4  mov     dword ptr [rsp+128h+var_100], eax
0x18003baf8  mov     dword ptr [rsp+128h+var_108], 2197h
0x18003bb00  jmp     loc_18003B910
0x18003bb05  mov     rcx, [rsp+128h+var_C0]
0x18003bb0a  mov     rax, [rcx]
0x18003bb0d  lea     rdx, [rsp+128h+var_80]
0x18003bb15  mov     rax, [rax+28h]
0x18003bb19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb1e  mov     ebx, eax
0x18003bb20  test    eax, eax
0x18003bb22  jns     short loc_18003BB45
0x18003bb24  mov     rcx, [rdi+258h]
0x18003bb2b  test    rcx, rcx
0x18003bb2e  jz      loc_18003B898
0x18003bb34  mov     dword ptr [rsp+128h+var_100], eax
0x18003bb38  mov     dword ptr [rsp+128h+var_108], 2198h
0x18003bb40  jmp     loc_18003B910
0x18003bb45  mov     rcx, [rsp+128h+var_B0]
0x18003bb4a  mov     rax, [rcx]
0x18003bb4d  lea     rdx, [rsp+128h+var_88]
0x18003bb55  mov     rax, [rax+38h]
0x18003bb59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb5e  mov     ebx, eax
0x18003bb60  test    eax, eax
0x18003bb62  jns     short loc_18003BB85
0x18003bb64  mov     rcx, [rdi+258h]
0x18003bb6b  test    rcx, rcx
0x18003bb6e  jz      loc_18003B898
0x18003bb74  mov     dword ptr [rsp+128h+var_100], eax
0x18003bb78  mov     dword ptr [rsp+128h+var_108], 2199h
0x18003bb80  jmp     loc_18003B910
0x18003bb85  mov     rcx, [rsp+128h+var_B0]
0x18003bb8a  mov     rax, [rcx]
0x18003bb8d  lea     rdx, [rsp+128h+var_90]
0x18003bb95  mov     rax, [rax+40h]
0x18003bb99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb9e  mov     ebx, eax
0x18003bba0  test    eax, eax
0x18003bba2  jns     short loc_18003BBC5
0x18003bba4  mov     rcx, [rdi+258h]
0x18003bbab  test    rcx, rcx
0x18003bbae  jz      loc_18003B898
0x18003bbb4  mov     dword ptr [rsp+128h+var_100], eax
0x18003bbb8  mov     dword ptr [rsp+128h+var_108], 219Ah
0x18003bbc0  jmp     loc_18003B910
0x18003bbc5  mov     rcx, [rsp+128h+var_B0]
0x18003bbca  mov     rax, [rcx]
0x18003bbcd  lea     rdx, [rsp+128h+var_98]
0x18003bbd5  mov     rax, [rax+48h]
0x18003bbd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bbde  mov     ebx, eax
0x18003bbe0  test    eax, eax
0x18003bbe2  jns     short loc_18003BC05
0x18003bbe4  mov     rcx, [rdi+258h]
0x18003bbeb  test    rcx, rcx
0x18003bbee  jz      loc_18003B898
0x18003bbf4  mov     dword ptr [rsp+128h+var_100], eax
0x18003bbf8  mov     dword ptr [rsp+128h+var_108], 219Bh
0x18003bc00  jmp     loc_18003B910
0x18003bc05  mov     rcx, [rsp+128h+var_C0]
0x18003bc0a  mov     rax, [rcx]
0x18003bc0d  lea     rdx, [rsp+128h+var_6C]
0x18003bc15  mov     rax, [rax+20h]
0x18003bc19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bc1e  mov     ebx, eax
0x18003bc20  test    eax, eax
0x18003bc22  jns     short loc_18003BC45
0x18003bc24  mov     rcx, [rdi+258h]
0x18003bc2b  test    rcx, rcx
0x18003bc2e  jz      loc_18003B898
0x18003bc34  mov     dword ptr [rsp+128h+var_100], eax
0x18003bc38  mov     dword ptr [rsp+128h+var_108], 219Ch
0x18003bc40  jmp     loc_18003B910
0x18003bc45  mov     eax, [rsp+128h+var_6C]
0x18003bc4c  mov     r10, [rsp+128h+var_98]
0x18003bc54  lea     rcx, [rsp+128h+var_E8]
0x18003bc59  mov     [rsp+128h+var_F8], rcx; struct CDeploymentFileRequest **
0x18003bc5e  mov     dword ptr [rsp+128h+var_100], eax; int
0x18003bc62  mov     [rsp+128h+var_108], r10; wchar_t *
0x18003bc67  mov     r9, [rsp+128h+var_90]; wchar_t *
0x18003bc6f  mov     r8, [rsp+128h+var_88]; wchar_t *
0x18003bc77  mov     rdx, [rsp+128h+var_80]; wchar_t *
0x18003bc7f  mov     rcx, [rsp+128h+pv]; Src
0x18003bc87  call    ?Create@CDeploymentFileRequest@@SAJPEB_W0000HPEAPEAV1@@Z; CDeploymentFileRequest::Create(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,int,CDeploymentFileRequest * *)
0x18003bc8c  mov     ebx, eax
0x18003bc8e  test    eax, eax
0x18003bc90  jns     short loc_18003BCB3
  ... truncated ...
```
