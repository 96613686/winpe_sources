# CBinding::StartBinding(IUri *,IBindCtx *,_GUID const &,int,ushort * *,void * *)

- ea: `0x180024bd0`
- end: `0x1800261b9`
- name: `?StartBinding@CBinding@@QEAAJPEAUIUri@@PEAUIBindCtx@@AEBU_GUID@@HPEAPEAGPEAPEAX@Z`
- size: `5609`
- prototype: `__int64 __usercall@<rax>(CBinding *__hidden this@<rcx>, struct IUri *@<rdx>, struct IBindCtx *@<r8>, const struct _GUID *@<r9>, int, unsigned __int16 **, void **)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004e9d4`

## callees

- `0x180008300`
- `0x1800150e0`
- `0x180015f10`
- `0x18001a4d0`
- `0x18001e160`
- `0x180024a3c`
- `0x180024bd0`
- `0x1800261c0`
- `0x1800265e0`
- `0x180026dac`
- `0x180026f54`
- `0x180027034`
- `0x1800271cc`
- `0x180027228`
- `0x180028f0c`
- `0x18004ff60`
- `0x180050420`
- `0x1800504ec`
- `0x180050520`
- `0x1800506a0`
- `0x1800506e4`
- `0x180051b58`
- `0x18005a2f0`
- `0x18007ec94`
- `0x18009ba00`
- `0x1800ebb44`
- `0x18011ba26`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_DSA_InsertItem` at `0x1800256a3`
- `iertutil!__imp_DSA_InsertItem` at `0x1800256a3`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180025084`
- `iertutil!__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ` at `0x180025084`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800256be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025786`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800259cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002609e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800256be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025786`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800259cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b54`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002609e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002500f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002567e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002500f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002567e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800251c0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800251c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024d8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025be1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024d8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025be1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024d31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025097`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800257c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800257e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024d31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025097`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800257c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800257e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025a9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025e50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025e5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800260b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025a9f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025e50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025e5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800260b6`
- `OLEAUT32!__imp_SysFreeString` at `0x180025db3`
- `OLEAUT32!__imp_SysFreeString` at `0x180025db3`
- `OLEAUT32!__imp_SysStringLen` at `0x180025dfc`
- `OLEAUT32!__imp_SysStringLen` at `0x180025dfc`
- `api-ms-win-ole32-ie-l1-1-0!ReleaseStgMedium` at `0x180024ece`
- `api-ms-win-ole32-ie-l1-1-0!ReleaseStgMedium` at `0x180024ece`

## string_xrefs

- `0x180025bb9`: `onecoreuap\inetcore\urlmon\trans\common\ctransaction.cpp`

## pseudocode

```c
__int64 __fastcall CBinding::StartBinding(
        CBinding *this,
        struct IUri *a2,
        struct IBindCtx *a3,
        struct _GUID *a4,
        int a5,
        unsigned __int16 **a6,
        void **a7)
{
  int v7; // r12d
  int COInetSession; // esi
  _QWORD *v14; // r15
  int v15; // esi
  char *v16; // rax
  char *v17; // rdi
  struct IUri *v18; // rcx
  __int64 (__fastcall ***v19)(__int64, GUID *, struct IInternetProtocol **); // rdi
  __int64 (__fastcall ***v20)(__int64, GUID *, struct IInternetProtocol **); // r15
  unsigned int v21; // eax
  OLECHAR *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  void *v25; // rcx
  void *v26; // rcx
  _DWORD *v27; // r15
  __int64 (__fastcall ***v28)(_QWORD, GUID *, struct IInternetProtocol **); // rcx
  int v29; // eax
  char *v30; // r8
  int v31; // r12d
  int v32; // eax
  int v33; // eax
  struct IInternetProtocolVtbl **v34; // rsi
  unsigned int v35; // edi
  bool v36; // cf
  __int64 (__fastcall ***v37)(_QWORD, GUID *, LPVOID *); // r12
  unsigned int v38; // edi
  __int64 (__fastcall **v39)(_QWORD, _QWORD, _QWORD); // rax
  EdgeTransaction *v40; // rax
  const char *v41; // r9
  EdgeTransaction *p_Suspend; // r12
  int v43; // eax
  __int64 v44; // rcx
  int (__fastcall ***v45)(_QWORD, GUID *, struct IInternetProtocol **); // rcx
  __int64 v46; // xmm0_8
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rax
  int v50; // ecx
  int v51; // edx
  struct IUriVtbl *v52; // rax
  int v53; // eax
  __int64 v54; // rcx
  int v55; // ecx
  int v56; // edx
  int v57; // ecx
  unsigned int v58; // edx
  int v59; // ecx
  int v60; // edx
  int v61; // ecx
  int v62; // r15d
  __int64 v63; // rax
  unsigned int v64; // edi
  const OLECHAR *v65; // rdx
  __int16 v66; // r8
  __int64 v67; // rcx
  const OLECHAR *v68; // rdx
  const OLECHAR *v69; // rcx
  int v70; // edx
  EdgeTransaction *v71; // rax
  HDSA *GlobalTransactionManager; // rdi
  int v73; // edi
  int v74; // esi
  _QWORD *v75; // rdi
  EdgeTransaction *v76; // rcx
  CBindCtx *v77; // rdi
  char *v78; // r12
  void *v79; // xmm6_8
  unsigned __int8 *v80; // rax
  unsigned __int8 *v81; // rdi
  CTransData *v82; // rax
  unsigned int v83; // edx
  CTransData *v84; // rsi
  struct CTransaction *v85; // rdx
  unsigned int v86; // r9d
  void *v87; // r9
  struct IInternetProtocol *v88; // rdx
  __int64 v89; // rsi
  __int64 v90; // rdi
  CTransData *v91; // rcx
  __int64 (__fastcall **v92)(__int64, GUID *, struct IInternetProtocol **); // rax
  int v93; // eax
  __int64 v94; // rdx
  void *v95; // rdi
  char *v96; // rax
  char *v97; // rdi
  char *v98; // rcx
  struct IInternetProtocol *v99; // rax
  struct IInternetProtocolVtbl *v100; // rcx
  int v101; // edi
  __int64 v102; // r14
  __int64 v103; // rdi
  __int64 v104; // rcx
  int v105; // ecx
  int (__fastcall ***v106)(_QWORD, GUID *, void **); // rcx
  int v107; // eax
  IID *v108; // rax
  IID v109; // xmm0
  struct IBindCtxVtbl *lpVtbl; // rax
  OLECHAR *v111; // rcx
  const unsigned __int16 *v112; // rdx
  volatile signed __int32 *v113; // rdi
  int v114; // eax
  int v115; // eax
  CBinding *v116; // rcx
  struct IInternetProtocolVtbl *v117; // r12
  __int64 v118; // rcx
  int v119; // ecx
  int v120; // ecx
  int v121; // ecx
  LPCOLESTR lpsz; // [rsp+20h] [rbp-C1h]
  LPCOLESTR lpsza; // [rsp+20h] [rbp-C1h]
  unsigned int v124; // [rsp+40h] [rbp-A1h] BYREF
  int v125; // [rsp+44h] [rbp-9Dh]
  struct IInternetProtocol *pitem; // [rsp+48h] [rbp-99h] BYREF
  __int64 v127; // [rsp+50h] [rbp-91h]
  LPVOID pv; // [rsp+60h] [rbp-81h] BYREF
  int v129; // [rsp+68h] [rbp-79h]
  void *Buf1; // [rsp+70h] [rbp-71h] BYREF
  void *v131; // [rsp+78h] [rbp-69h] BYREF
  unsigned __int16 **v132; // [rsp+80h] [rbp-61h]
  __int128 v133; // [rsp+88h] [rbp-59h] BYREF
  struct IBindCtx *v134; // [rsp+98h] [rbp-49h]
  __int64 v135; // [rsp+A0h] [rbp-41h]
  IID rclsid; // [rsp+B0h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  v7 = 0;
  v132 = a6;
  v131 = a7;
  Buf1 = a4;
  v125 = 0;
  COInetSession = -2147467259;
  pitem = 0;
  if ( !a3
    || (COInetSession = ((__int64 (__fastcall *)(struct IBindCtx *, const wchar_t *, struct IInternetProtocol **))a3->lpVtbl->GetObjectParam)(
                          a3,
                          L"_BSCB_Holder_",
                          &pitem),
        COInetSession < 0)
    || (COInetSession = ((__int64 (__fastcall *)(struct IInternetProtocol *, GUID *, char *))pitem->lpVtbl->QueryInterface)(
                          pitem,
                          &IID_IBindStatusCallback,
                          (char *)this + 128),
        ((void (__fastcall *)(struct IInternetProtocol *))pitem->lpVtbl->Release)(pitem),
        COInetSession < 0) )
  {
    *((_QWORD *)this + 16) = 0;
    goto LABEL_4;
  }
  if ( !*((_QWORD *)this + 16) )
  {
    COInetSession = -2147024809;
    goto LABEL_77;
  }
  *((_DWORD *)this + 68) = a5;
  if ( a5 )
  {
    v108 = (IID *)*((_QWORD *)this + 42);
    *((_DWORD *)this + 82) |= 0x2000000u;
    *((_QWORD *)this + 51) = a4;
    v109 = *v108;
    lpVtbl = a3->lpVtbl;
    rclsid = v109;
    rclsid.Data1 = 16;
    COInetSession = ((__int64 (__fastcall *)(struct IBindCtx *, IID *))lpVtbl->GetBindOptions)(a3, &rclsid);
    if ( COInetSession < 0 )
      goto LABEL_77;
    *(IID *)*((_QWORD *)this + 42) = rclsid;
  }
  v14 = (_QWORD *)((char *)this + 400);
  *((_QWORD *)this + 50) = 0;
  v15 = ((__int64 (__fastcall *)(struct IBindCtx *, GUID *, char *))a3->lpVtbl->QueryInterface)(
          a3,
          &IID_IAsyncBindCtx,
          (char *)this + 400);
  if ( v15 )
  {
    v15 = 0;
    *v14 = 0;
  }
  ((void (__fastcall *)(struct IBindCtx *))a3->lpVtbl->AddRef)(a3);
  if ( !*v14 )
  {
    v16 = (char *)CoTaskMemAlloc(0x48u);
    v17 = v16;
    if ( v16 )
    {
      *(_QWORD *)(v16 + 20) = 0;
      *((_DWORD *)v16 + 7) = 0;
      *((_QWORD *)v16 + 5) = 0;
      *((_QWORD *)v16 + 6) = 0;
      *((_QWORD *)v16 + 7) = 0;
      *((_QWORD *)v16 + 8) = 0;
      *(_QWORD *)v16 = &CBindCtx::`vftable'{for `IBindCtx'};
      *((_QWORD *)v16 + 1) = &CBindCtx::`vftable'{for `IMarshal'};
      *((_DWORD *)v16 + 4) = 1;
      *((_QWORD *)v16 + 4) = a3;
      ((void (__fastcall *)(struct IBindCtx *))a3->lpVtbl->AddRef)(a3);
      *((_QWORD *)v17 + 3) = 0;
      *((_DWORD *)v17 + 14) = GetCurrentThreadId();
      *((_QWORD *)v17 + 5) = 0;
      *((_QWORD *)v17 + 6) = 0;
      *((_QWORD *)v17 + 8) = 0;
      _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
      *v14 = v17;
    }
    else
    {
      *v14 = 0;
      v15 = -2147024882;
    }
  }
  ((void (__fastcall *)(struct IBindCtx *))a3->lpVtbl->Release)(a3);
  if ( v15 < 0 )
  {
    COInetSession = -2147024882;
    goto LABEL_77;
  }
  v18 = (struct IUri *)*((_QWORD *)this + 25);
  COInetSession = 0;
  if ( v18 != a2 )
  {
    if ( v18 )
    {
      ((void (__fastcall *)(struct IUri *))v18->lpVtbl->Release)(v18);
      *((_QWORD *)this + 25) = 0;
    }
    if ( a2 )
    {
      *((_QWORD *)this + 25) = a2;
      ((void (__fastcall *)(struct IUri *))a2->lpVtbl->AddRef)(a2);
    }
    v19 = (__int64 (__fastcall ***)(__int64, GUID *, struct IInternetProtocol **))*((_QWORD *)this + 25);
    COInetSession = 0;
    v20 = (__int64 (__fastcall ***)(__int64, GUID *, struct IInternetProtocol **))*((_QWORD *)this + 27);
    v21 = *((_DWORD *)this + 56);
    v124 = v21;
    if ( v19 != v20 || v21 )
    {
      v22 = (OLECHAR *)*((_QWORD *)this + 29);
      if ( v22 )
      {
        SysFreeString(v22);
        v21 = v124;
        *((_QWORD *)this + 29) = 0;
      }
      *((_QWORD *)this + 30) = 0;
      *((_DWORD *)this + 62) = 0;
      if ( v19 != v20 )
      {
        v23 = *((_QWORD *)this + 27);
        if ( v23 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          v21 = v124;
          *((_QWORD *)this + 27) = 0;
        }
      }
    }
    *((_DWORD *)this + 56) = 0;
    if ( v19 && (v21 || v19 != v20) )
    {
      v92 = *v19;
      pitem = 0;
      v93 = (*v92)((__int64)v19, &GUID_50295b0c_6b79_4935_aed8_05d80ec86a60, &pitem);
      v94 = *((unsigned int *)this + 56);
      if ( v93 < 0 )
      {
        COInetSession = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, struct IInternetProtocol **), __int64, char *, _QWORD))(*v19)[3])(
                          v19,
                          v94,
                          (char *)this + 232,
                          0);
        if ( COInetSession >= 0 )
        {
          v111 = (OLECHAR *)*((_QWORD *)this + 29);
          *((_QWORD *)this + 30) = v111;
          *((_DWORD *)this + 62) = SysStringLen(v111);
        }
      }
      else
      {
        COInetSession = ((__int64 (__fastcall *)(struct IInternetProtocol *, __int64, char *, char *))pitem->lpVtbl[2].Release)(
                          pitem,
                          v94,
                          (char *)this + 240,
                          (char *)this + 248);
        ((void (__fastcall *)(struct IInternetProtocol *))pitem->lpVtbl->Release)(pitem);
      }
      if ( v19 != v20 && COInetSession >= 0 )
      {
        *((_QWORD *)this + 27) = v19;
        ((void (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, struct IInternetProtocol **)))(*v19)[1])(v19);
      }
      if ( COInetSession == 1 )
        COInetSession = CUString::Set(
                          (CBinding *)((char *)this + 208),
                          *((struct IUri **)this + 25),
                          Uri_PROPERTY_RAW_URI);
    }
  }
  if ( !*((_QWORD *)this + 30) )
  {
    if ( COInetSession >= 0 )
    {
      COInetSession = -2147024809;
      goto LABEL_4;
    }
LABEL_77:
    if ( *((_QWORD *)this + 16) && v7 )
    {
      *((_DWORD *)this + 86) = COInetSession;
      CBinding::CallOnStopBinding(this, COInetSession, 0);
    }
    v54 = *((_QWORD *)this + 48);
    if ( v54 )
    {
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v54 + 48LL))(v54, 0);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 16LL))(*((_QWORD *)this + 48));
      *((_QWORD *)this + 48) = 0;
    }
    return (unsigned int)COInetSession;
  }
  if ( COInetSession < 0 )
    goto LABEL_77;
  *((_DWORD *)this + 110) = 128;
  if ( this != (CBinding *)-440LL )
  {
    v24 = *((_QWORD *)this + 69);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    v25 = (void *)*((_QWORD *)this + 56);
    if ( v25 )
      CoTaskMemFree(v25);
    v26 = (void *)*((_QWORD *)this + 61);
    if ( v26 )
      CoTaskMemFree(v26);
    ReleaseStgMedium((LPSTGMEDIUM)this + 19);
    memset_0((char *)this + 444, 0, 0x7Cu);
    *((_DWORD *)this + 110) = 128;
  }
  v27 = (_DWORD *)((char *)this + 176);
  COInetSession = -2147467259;
  *((_QWORD *)this + 22) = 0;
  *((_DWORD *)this + 46) = 0;
  if ( !*((_DWORD *)this + 40) )
  {
    v28 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct IInternetProtocol **))*((_QWORD *)this + 16);
    pitem = 0;
    v29 = (**v28)(v28, &GUID_aaa74ef9_8ee7_4659_88d9_f8c504da73cc, &pitem);
    v30 = (char *)this + 440;
    if ( v29 < 0 )
    {
      COInetSession = (*(__int64 (__fastcall **)(_QWORD, char *, char *))(**((_QWORD **)this + 16) + 64LL))(
                        *((_QWORD *)this + 16),
                        (char *)this + 176,
                        v30);
    }
    else
    {
      COInetSession = ((__int64 (__fastcall *)(struct IInternetProtocol *, char *, char *, char *, char *))pitem->lpVtbl->LockRequest)(
                        pitem,
                        (char *)this + 176,
                        v30,
                        (char *)this + 180,
                        (char *)this + 184);
      ((void (__fastcall *)(struct IInternetProtocol *))pitem->lpVtbl->Release)(pitem);
    }
    *((_DWORD *)this + 40) = 2;
  }
  if ( COInetSession )
  {
    if ( COInetSession < 0 )
    {
LABEL_76:
      v7 = v125;
      goto LABEL_77;
    }
  }
  else if ( !*((_QWORD *)this + 16) || (*(_BYTE *)v27 & 1) == 0 )
  {
    *v27 &= ~2u;
  }
  v31 = *((_DWORD *)this + 125);
  if ( (g_dwSettings & 0x20000000) != 0 )
    *v27 |= 0x20000u;
  if ( (_WORD)v31 )
  {
    if ( a5 )
      goto LABEL_47;
    pv = 0;
    pitem = 0;
    COInetSession = GetCOInetSession((struct COInetSession **)&pv);
    if ( COInetSession )
      goto LABEL_251;
    v112 = (const unsigned __int16 *)*((_QWORD *)this + 30);
    v124 = 0;
    v113 = (volatile signed __int32 *)pv;
    rclsid = GUID_NULL;
    v114 = COInetSession::CreateFirstProtocol(
             (COInetSession *)pv,
             v112,
             0,
             0,
             &pitem,
             &rclsid,
             &v124,
             (unsigned __int16)v31);
    _InterlockedDecrement(v113 + 4);
    COInetSession = v114;
    if ( v114 )
      goto LABEL_251;
    v95 = Buf1;
    v134 = a3;
    v135 = 0;
    pv = 0;
    v133 = *(_OWORD *)Buf1;
    if ( ((__int64 (__fastcall *)(struct IInternetProtocol *, GUID *, LPVOID *))pitem->lpVtbl->QueryInterface)(
           pitem,
           &IID_IInternetProtocolEx,
           &pv) < 0 )
      v115 = ((__int64 (__fastcall *)(struct IInternetProtocol *, _QWORD, _QWORD, _QWORD, _DWORD, __int128 *))pitem->lpVtbl->Start)(
               pitem,
               *((_QWORD *)this + 30),
               0,
               0,
               0,
               &v133);
    else
      v115 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, _DWORD, __int128 *))(*(_QWORD *)pv + 104LL))(
               pv,
               *((_QWORD *)this + 25),
               0,
               0,
               0,
               &v133);
    COInetSession = v115;
    if ( pv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
    ((void (__fastcall *)(struct IInternetProtocol *))pitem->lpVtbl->Release)(pitem);
    if ( !COInetSession )
    {
      if ( !v135 )
        return (unsigned int)COInetSession;
      COInetSession = -2146697193;
      *(_QWORD *)v131 = v135;
      goto LABEL_76;
    }
    if ( COInetSession != -2146697199 )
    {
LABEL_251:
      v7 = v125;
      goto LABEL_4;
    }
  }
  else
  {
    if ( a5 )
      goto LABEL_47;
    v95 = Buf1;
  }
  if ( memcmp_0(v95, &IID_IStream, 0x10u) && memcmp_0(v95, &IID_IStorage, 0x10u) && memcmp_0(v95, &IID_IUnknown, 0x10u) )
  {
    COInetSession = -2147024809;
    goto LABEL_76;
  }
LABEL_47:
  v32 = IsOInetProtocol(a3, *((const unsigned __int16 **)this + 30));
  COInetSession = v32;
  if ( v32 )
  {
    v7 = v125;
    if ( v32 != -2146697202 )
      COInetSession = -2146697203;
    goto LABEL_77;
  }
  v33 = 33554688;
  v34 = (struct IInternetProtocolVtbl **)((char *)this + 376);
  if ( !*((_DWORD *)this + 68) )
    v33 = 256;
  v35 = v33 | 0x20000000;
  v36 = (v31 & 0x400000) != 0;
  v37 = (__int64 (__fastcall ***)(_QWORD, GUID *, LPVOID *))*((_QWORD *)this + 50);
  *(_QWORD *)&rclsid.Data1 = v37;
  if ( !v36 )
    v35 = v33;
  v124 = v35;
  EnterCriticalSection(&g_mxsTransMgr);
  pv = 0;
  if ( v37 )
  {
    v38 = (**v37)(v37, &IID_IAsyncBindCtx, &pv);
    if ( v38 )
    {
LABEL_54:
      if ( v38 <= 1 )
      {
LABEL_56:
        v35 = v124;
        goto LABEL_57;
      }
      goto LABEL_55;
    }
    v97 = (char *)pv;
    pitem = (struct IInternetProtocol *)pv;
    if ( !memcmp_0(&IID_IProxyManager, &IID_IUnknown, 0x10u)
      || !memcmp_0(&IID_IProxyManager, &IID_IBindCtx, 0x10u)
      || !memcmp_0(&IID_IProxyManager, &IID_IAsyncBindCtx, 0x10u) )
    {
      v98 = v97;
    }
    else
    {
      if ( memcmp_0(&IID_IProxyManager, &IID_IMarshal, 0x10u) )
      {
        p_Suspend = (EdgeTransaction *)*((_QWORD *)v97 + 5);
        if ( p_Suspend )
        {
          v38 = 0;
          (*(void (__fastcall **)(EdgeTransaction *, __int64))(*(_QWORD *)p_Suspend + 8LL))(p_Suspend, 2147500034LL);
        }
        else
        {
          v38 = -2147467262;
        }
        v99 = pitem;
        v100 = pitem[6].lpVtbl;
        if ( !v100 || this == (CBinding *)-376LL )
        {
          if ( !pitem[5].lpVtbl )
            v38 = -2147467262;
          if ( this != (CBinding *)-376LL )
            *v34 = 0;
        }
        else
        {
          *v34 = v100;
          _InterlockedIncrement((volatile signed __int32 *)&v99[6].lpVtbl->Release);
        }
        if ( !v38 )
        {
          v101 = *((_DWORD *)p_Suspend + 94);
          if ( v101 != GetCurrentThreadId() )
            CBindCtx::SetTransactionObject((CBindCtx *)pv, 0);
          v74 = 1;
          if ( !p_Suspend )
            goto LABEL_143;
          goto LABEL_263;
        }
        v37 = *(__int64 (__fastcall ****)(_QWORD, GUID *, LPVOID *))&rclsid.Data1;
        goto LABEL_54;
      }
      if ( v97 )
        v98 = v97 + 8;
      else
        v98 = 0;
    }
    _InterlockedIncrement((volatile signed __int32 *)v97 + 4);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v98 + 16LL))(v98);
    CBindCtx::Release((CBindCtx *)pv);
    pv = 0;
LABEL_55:
    v39 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v37;
    pitem = 0;
    ((__int64 (__fastcall **)(_QWORD, const wchar_t *, struct IInternetProtocol **))v39)[10](
      v37,
      L"CBinding Context",
      &pitem);
    if ( !pitem )
      goto LABEL_56;
    v131 = 0;
    if ( !(unsigned int)CBinding::QueryInterface((CBinding *)pitem, &IID_IProxyManager, &v131) )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)v131 + 16LL))(v131);
      v116 = (CBinding *)pitem;
LABEL_259:
      CBinding::Release(v116);
      goto LABEL_56;
    }
    v116 = (CBinding *)pitem;
    v117 = pitem[48].lpVtbl;
    if ( !v117 )
      goto LABEL_259;
    p_Suspend = (EdgeTransaction *)&v117[-1].Suspend;
    if ( !p_Suspend )
      goto LABEL_259;
    (*(void (__fastcall **)(EdgeTransaction *))(*(_QWORD *)p_Suspend + 8LL))(p_Suspend);
    CBinding::Release((CBinding *)pitem);
LABEL_263:
    v74 = 1;
    goto LABEL_143;
  }
LABEL_57:
  if ( !InternalForkingSupport_ShouldUseEdge() )
  {
    v40 = (EdgeTransaction *)CoTaskMemAlloc(0x640u);
    p_Suspend = v40;
    if ( v40 )
    {
      memset_0(v40, 0, 0x640u);
      CTransaction::CTransaction(p_Suspend, v35);
      *(_QWORD *)p_Suspend = &LegacyTransaction::`vftable'{for `IInternetProtocolSink'};
      *((_QWORD *)p_Suspend + 1) = &LegacyTransaction::`vftable'{for `ITransProtocolSink'};
      *((_QWORD *)p_Suspend + 2) = &CTransaction::`vftable'{for `IInternetBindInfoEx'};
      *((_QWORD *)p_Suspend + 3) = &CTransaction::`vftable'{for `IDevToolbarDownloadInitiatorInfo'};
      *((_QWORD *)p_Suspend + 4) = &LegacyTransaction::`vftable'{for `IServiceProvider'};
      *((_QWORD *)p_Suspend + 5) = &LegacyTransaction::`vftable'{for `IAuthenticate'};
      *((_QWORD *)p_Suspend + 6) = &LegacyTransaction::`vftable'{for `IInternetProtocolEx'};
      *((_QWORD *)p_Suspend + 7) = &LegacyTransaction::`vftable'{for `IInternetPriority'};
      *((_QWORD *)p_Suspend + 8) = &CTransaction::`vftable'{for `IInternetPriorityInternal'};
      *((_QWORD *)p_Suspend + 9) = &EdgeTransaction::`vftable'{for `IWrappedProtocol'};
      *((_QWORD *)p_Suspend + 10) = &EdgeTransaction::`vftable'{for `IUriContainer'};
      *((_QWORD *)p_Suspend + 11) = &EdgeTransaction::`vftable'{for `IPreBindingSupport'};
      *((_QWORD *)p_Suspend + 12) = &CTransaction::`vftable'{for `ITransactionInternal'};
      *((_QWORD *)p_Suspend + 13) = &CTransaction::`vftable'{for `IProtocolHandlerValidator'};
      *((_QWORD *)p_Suspend + 14) = &CTransaction::`vftable'{for `IWinInetHttpTimeouts'};
      *((_QWORD *)p_Suspend + 15) = &LegacyTransaction::`vftable'{for `IInternetBindInfoInternal'};
      *((_QWORD *)p_Suspend + 16) = &CTransaction::`vftable'{for `IDownloadModeHandleCallback'};
      *((_QWORD *)p_Suspend + 17) = &LegacyTransaction::`vftable'{for `IInternetPriorityInfoInternal'};
      *((_QWORD *)p_Suspend + 193) = 0;
      *((_QWORD *)p_Suspend + 194) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)p_Suspend + 39);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)p_Suspend + 1544);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)p_Suspend + 1552);
      CTransaction::Init(p_Suspend, v124);
      goto LABEL_133;
    }
LABEL_208:
    wil::details::in1diag3::_FailFast_NullAlloc(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"onecoreuap\\inetcore\\urlmon\\trans\\common\\ctransaction.cpp",
      v41);
  }
  v71 = (EdgeTransaction *)operator new(0x698u);
  if ( !v71 )
    goto LABEL_208;
  p_Suspend = EdgeTransaction::EdgeTransaction(v71, v35);
  if ( !p_Suspend )
    goto LABEL_208;
LABEL_133:
  if ( !(*(__int64 (__fastcall **)(EdgeTransaction *))(*(_QWORD *)p_Suspend + 112LL))(p_Suspend) )
  {
LABEL_205:
    p_Suspend = 0;
    v74 = -2147467259;
    goto LABEL_143;
  }
  GlobalTransactionManager = (HDSA *)GetGlobalTransactionManager();
  if ( !GlobalTransactionManager )
  {
LABEL_204:
    (*(void (__fastcall **)(EdgeTransaction *, __int64))(*(_QWORD *)p_Suspend + 56LL))(p_Suspend, 1);
    goto LABEL_205;
  }
  v127 = 0;
  pitem = (struct IInternetProtocol *)p_Suspend;
  EnterCriticalSection(&g_mxsTransMgr);
  LODWORD(v127) = ++dword_18015E738;
  if ( DSA_InsertItem(*GlobalTransactionManager, 0x7FFFFFFF, &pitem) < 0 )
  {
    LeaveCriticalSection(&g_mxsTransMgr);
    goto LABEL_204;
  }
  v73 = dword_18015E738;
  LeaveCriticalSection(&g_mxsTransMgr);
  *((_DWORD *)p_Suspend + 92) = 1;
  *((_DWORD *)p_Suspend + 377) = v73;
  v74 = (**(__int64 (__fastcall ***)(EdgeTransaction *, GUID *, char *))p_Suspend)(
          p_Suspend,
          &IID_IInternetProtocol,
          (char *)this + 384);
  if ( !v74 )
    (*(void (__fastcall **)(EdgeTransaction *))(*(_QWORD *)p_Suspend + 16LL))(p_Suspend);
  if ( !pv )
  {
    if ( !*(_QWORD *)&rclsid.Data1 )
      goto LABEL_174;
    (***(void (__fastcall ****)(_QWORD, GUID *, LPVOID *))&rclsid.Data1)(
      *(_QWORD *)&rclsid.Data1,
      &IID_IAsyncBindCtx,
      &pv);
    if ( !pv )
      goto LABEL_174;
  }
  v75 = pv;
  v76 = (EdgeTransaction *)*((_QWORD *)pv + 5);
  if ( p_Suspend != v76 )
  {
    if ( v76 )
      (*(void (__fastcall **)(EdgeTransaction *))(*(_QWORD *)v76 + 16LL))(v76);
    v75[5] = p_Suspend;
    (*(void (__fastcall **)(EdgeTransaction *))(*(_QWORD *)p_Suspend + 8LL))(p_Suspend);
  }
LABEL_143:
  v77 = (CBindCtx *)pv;
  if ( pv && _InterlockedExchangeAdd((volatile signed __int32 *)pv + 4, 0xFFFFFFFF) == 1 && v77 )
  {
    CBindCtx::~CBindCtx(v77);
    CoTaskMemFree(v77);
  }
  if ( !p_Suspend )
  {
    *((_QWORD *)this + 48) = 0;
    v78 = (char *)this + 376;
    goto LABEL_147;
  }
LABEL_174:
  v96 = (char *)p_Suspend + 48;
  *((_QWORD *)this + 48) = (char *)p_Suspend + 48;
  v78 = (char *)this + 376;
  if ( !v96 || this == (CBinding *)-376LL || !*(_QWORD *)v78 )
  {
LABEL_147:
    if ( v74 == 1 && v78 && !*(_QWORD *)v78 )
    {
      LeaveCriticalSection(&g_mxsTransMgr);
    }
    else
    {
      LeaveCriticalSection(&g_mxsTransMgr);
      if ( v74 )
      {
        if ( v74 == 1 )
          goto LABEL_61;
LABEL_271:
        COInetSession = -2147024882;
        goto LABEL_76;
      }
    }
    v79 = *(void **)v27;
    v124 = *((_DWORD *)this + 68);
    *(_QWORD *)&rclsid.Data1 = *((_QWORD *)this + 50);
    pitem = (struct IInternetProtocol *)*((_QWORD *)this + 30);
    LODWORD(v131) = *((_DWORD *)this + 46);
    v80 = (unsigned __int8 *)CoTaskMemAlloc(0x2000u);
    v81 = v80;
    if ( v80 )
      memset_0(v80, 0, 0x2000u);
    v82 = (CTransData *)CoTaskMemAlloc(0x4E8u);
    v84 = v82;
    if ( v82 )
    {
      memset_0(v82, 0, 0x4E8u);
      v82 = CTransData::CTransData(v84, v85, v81, v86, v124);
    }
    if ( v81 )
    {
      if ( v82 )
      {
        v87 = Buf1;
        v88 = pitem;
        v129 = (int)v131;
        lpsza = *(LPCOLESTR *)&rclsid.Data1;
        *(_QWORD *)v78 = v82;
        pv = v79;
        CTransData::Initialize(v82, v88, &pv, v87, lpsza, 0);
        v89 = *((_QWORD *)this + 50);
        v90 = *(_QWORD *)v78;
        v91 = *(CTransData **)(v89 + 48);
        if ( *(CTransData **)v78 != v91 )
        {
          if ( v91 )
            CTransData::Release(v91);
          *(_QWORD *)(v89 + 48) = v90;
          if ( v90 )
            _InterlockedIncrement((volatile signed __int32 *)(v90 + 16));
        }
        goto LABEL_70;
      }
      CoTaskMemFree(v81);
    }
    else if ( v82 )
    {
      CTransData::`scalar deleting destructor'(v82, v83);
    }
    *(_QWORD *)v78 = 0;
    goto LABEL_271;
  }
  LeaveCriticalSection(&g_mxsTransMgr);
LABEL_61:
  v43 = 0x10000000;
  if ( !a5 )
    v43 = 0x1000000;
  v44 = *((_QWORD *)this + 48);
  *((_DWORD *)this + 82) |= v43;
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
    v45 = (int (__fastcall ***)(_QWORD, GUID *, struct IInternetProtocol **))*((_QWORD *)this + 48);
    pitem = 0;
    if ( (**v45)(v45, &GUID_c28722e5_bc1a_4c55_a68d_33219f698910, &pitem) >= 0 )
    {
      if ( (*((_BYTE *)this + 180) & 4) != 0 )
        ((void (__fastcall *)(struct IInternetProtocol *))pitem->lpVtbl->Terminate)(pitem);
      ((void (__fastcall *)(struct IInternetProtocol *))pitem->lpVtbl->Release)(pitem);
    }
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 16LL))(*((_QWORD *)this + 48));
  }
  v46 = *(_QWORD *)v27;
  v47 = *((_QWORD *)this + 30);
  v48 = *(_QWORD *)v78;
  *(_DWORD *)rclsid.Data4 = *((_DWORD *)this + 46);
  lpsz = (LPCOLESTR)*((_QWORD *)this + 50);
  *(_QWORD *)&rclsid.Data1 = v46;
  COInetSession = CTransData::Initialize(v48, v47, &rclsid, Buf1, lpsz, a5);
  if ( COInetSession < 0 )
    goto LABEL_76;
LABEL_70:
  *v132 = (unsigned __int16 *)*((_QWORD *)this + 56);
  v49 = *(_QWORD *)v78;
  v50 = *v27;
  v51 = *(_DWORD *)(*(_QWORD *)v78 + 188LL);
  *(_DWORD *)(*(_QWORD *)v78 + 112LL) = *v27;
  if ( v51 == 4 )
  {
    if ( (v50 & 0x82) != 0x82 )
      goto LABEL_74;
    *(_QWORD *)(v49 + 1232) = 0;
    goto LABEL_73;
  }
  if ( v51 )
  {
    if ( v51 == 5 )
    {
      v70 = *(_DWORD *)(v49 + 164);
      if ( v70 && v70 == *(_DWORD *)(v49 + 168) )
      {
        *(_DWORD *)(v49 + 188) = 4;
      }
      else if ( (v50 & 0x82) == 0x82 )
      {
LABEL_73:
        *(_DWORD *)(v49 + 188) = 1;
      }
    }
  }
  else if ( (*(_BYTE *)(v49 + 144) & 1) != 0 )
  {
    *(_DWORD *)(v49 + 188) = 5;
  }
LABEL_74:
  v52 = a2->lpVtbl;
  v124 = 0;
  v53 = ((__int64 (__fastcall *)(struct IUri *, unsigned int *))v52->GetScheme)(a2, &v124);
  COInetSession = v53;
  if ( v53 )
  {
    if ( v53 < 0 )
      goto LABEL_76;
  }
  else
  {
    v55 = *(_DWORD *)(*(_QWORD *)v78 + 188LL);
    if ( v55 == 2 || v55 == 4 || !ProtocolFromScheme(v124) )
      *v27 |= 0x40u;
  }
  *v27 |= 0x100000u;
  *((_DWORD *)this + 45) |= 0x80000000;
  if ( *((_DWORD *)this + 68) )
    *((_DWORD *)this + 125) |= 0x100000u;
  if ( *((_DWORD *)this + 40) == 2 )
  {
    COInetSession = (*(__int64 (__fastcall **)(_QWORD, _QWORD, CBinding *))(**((_QWORD **)this + 16) + 24LL))(
                      *((_QWORD *)this + 16),
                      0,
                      this);
    *((_DWORD *)this + 40) = 1;
  }
  else
  {
    COInetSession = -2147467259;
  }
  v7 = 1;
  if ( *((_QWORD *)this + 16) && (*(_BYTE *)v27 & 1) != 0 )
    v56 = 304;
  else
    v56 = 432;
  if ( COInetSession < 0 )
    goto LABEL_77;
  *(_QWORD *)&rclsid.Data1 = 0;
  v57 = v56 | 0x400000;
  if ( (*v27 & 0x400000) == 0 )
    v57 = v56;
  v58 = v57 & 0xFFFFFEFF;
  if ( (*v27 & 0x10000) == 0 )
    v58 = v57;
  v59 = v58 | 0x40000000;
  if ( (*((_BYTE *)this + 180) & 4) == 0 )
    v59 = v58;
  v60 = v59 | 0x2000200;
  if ( !*((_DWORD *)this + 68) )
    v60 = v59;
  v61 = v60 | 0x10000000;
  if ( (*((_DWORD *)this + 82) & 0x10000000) == 0 )
    v61 = v60;
  v62 = v61 | 0x1000000;
  if ( (*((_DWORD *)this + 82) & 0x1000000) == 0 )
    v62 = v61;
  if ( ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, IID *))a3->lpVtbl->GetObjectParam)(
         a3,
         L"EnablePreBinding",
         &rclsid) >= 0 )
  {
    v118 = *(_QWORD *)&rclsid.Data1;
    *((_DWORD *)this + 145) = 1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
  }
  if ( *((_QWORD *)this + 48) )
  {
    *((_BYTE *)this + 584) |= 0x10u;
    CBinding::SetProtocolPriority(this);
  }
  v63 = *((_QWORD *)this + 47);
  if ( (*(_BYTE *)(v63 + 124) & 5) == 0 && !*(_DWORD *)(v63 + 168) || (*(_BYTE *)(v63 + 144) & 0x10) == 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 8LL))(*((_QWORD *)this + 48));
    v102 = *((_QWORD *)this + 47);
    v103 = *((_QWORD *)this + 48);
    v104 = *(_QWORD *)(v102 + 24);
    if ( v104 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
      *(_QWORD *)(v102 + 24) = 0;
    }
    v105 = *(_DWORD *)(v102 + 188);
    if ( v105 == 4 || (v119 = v105 - 1) == 0 || (v120 = v119 - 1) == 0 || (v121 = v120 - 1) == 0 || v121 == 2 )
    {
      *(_QWORD *)(v102 + 24) = v103;
      if ( v103 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v103 + 8LL))(v103);
    }
    v106 = (int (__fastcall ***)(_QWORD, GUID *, void **))*((_QWORD *)this + 48);
    Buf1 = 0;
    if ( (**v106)(v106, &IID_IInternetProtocolEx, &Buf1) < 0 )
    {
      v107 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *, char *, int, _QWORD))(**((_QWORD **)this + 48) + 24LL))(
               *((_QWORD *)this + 48),
               *((_QWORD *)this + 30),
               (char *)this + 16,
               (char *)this + 24,
               v62,
               0);
    }
    else
    {
      if ( *((_DWORD *)this + 145) == 1 )
        IUnknown_EnablePreBinding((struct IUnknown *)Buf1, 1);
      v107 = (*(__int64 (__fastcall **)(void *, _QWORD, char *, char *, int, _QWORD))(*(_QWORD *)Buf1 + 104LL))(
               Buf1,
               *((_QWORD *)this + 25),
               (char *)this + 16,
               (char *)this + 24,
               v62,
               0);
    }
    COInetSession = v107;
    if ( Buf1 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)Buf1 + 16LL))(Buf1);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 16LL))(*((_QWORD *)this + 48));
LABEL_4:
    if ( COInetSession >= 0 )
      return (unsigned int)COInetSession;
    goto LABEL_77;
  }
  v64 = *(_DWORD *)(v63 + 164);
  v65 = (const OLECHAR *)(v63 + 200);
  v66 = *(_WORD *)(v63 + 200);
  v67 = v63 + 200;
  if ( !v66 )
    v67 = 0;
  if ( v67 )
  {
    if ( !v66 )
      v65 = 0;
    CBinding::OnTransNotification(this, BINDSTATUS_MIMETYPEAVAILABLE, v64, v64, v65, 0);
  }
  v68 = (const OLECHAR *)(*((_QWORD *)this + 47) + 712LL);
  v69 = v68;
  if ( !*v68 )
    v69 = 0;
  if ( v69 )
  {
    if ( !*v68 )
      v68 = 0;
    CBinding::OnTransNotification(this, BINDSTATUS_CACHEFILENAMEAVAILABLE, v64, v64, v68, 0);
  }
  CBinding::OnTransNotification(this, BINDSTATUS_ENDDOWNLOADDATA, v64, v64, 0, 0);
  return (unsigned int)COInetSession;
}

```

## disassembly

```asm
0x180024bd0  push    rbp
0x180024bd2  push    rbx
0x180024bd3  push    rsi
0x180024bd4  push    rdi
0x180024bd5  push    r12
0x180024bd7  push    r13
0x180024bd9  push    r14
0x180024bdb  push    r15
0x180024bdd  lea     rbp, [rsp-7]
0x180024be2  sub     rsp, 0E8h
0x180024be9  movaps  [rsp+120h+var_50], xmm6
0x180024bf1  mov     rax, cs:__security_cookie
0x180024bf8  xor     rax, rsp
0x180024bfb  mov     [rbp+3Fh+var_60], rax
0x180024bff  mov     rax, [rbp+3Fh+arg_28]
0x180024c03  xor     r12d, r12d
0x180024c06  mov     [rbp+3Fh+var_A0], rax
0x180024c0a  mov     r15, r9
0x180024c0d  mov     rax, [rbp+3Fh+arg_30]
0x180024c11  mov     r14, r8
0x180024c14  mov     [rbp+3Fh+var_A8], rax
0x180024c18  mov     r13, rdx
0x180024c1b  mov     [rbp+3Fh+Buf1], r9
0x180024c1f  mov     rbx, rcx
0x180024c22  mov     [rsp+120h+var_DC], r12d
0x180024c27  mov     esi, 80004005h
0x180024c2c  mov     [rsp+120h+pitem], r12
0x180024c31  test    r8, r8
0x180024c34  jz      short loc_180024C57
0x180024c36  mov     rax, [r8]
0x180024c39  lea     rdx, aBscbHolder; "_BSCB_Holder_"
0x180024c40  lea     r8, [rsp+120h+pitem]
0x180024c45  mov     rcx, r14
0x180024c48  mov     rax, [rax+50h]
0x180024c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c51  mov     esi, eax
0x180024c53  test    eax, eax
0x180024c55  jns     short loc_180024C92
0x180024c57  xor     eax, eax
0x180024c59  mov     [rbx+80h], rax
0x180024c60  test    esi, esi
0x180024c62  js      loc_18002533D
0x180024c68  mov     eax, esi
0x180024c6a  mov     rcx, [rbp+3Fh+var_60]
0x180024c6e  xor     rcx, rsp; StackCookie
0x180024c71  call    __security_check_cookie
0x180024c76  movaps  xmm6, [rsp+120h+var_50]
0x180024c7e  add     rsp, 0E8h
0x180024c85  pop     r15
0x180024c87  pop     r14
0x180024c89  pop     r13
0x180024c8b  pop     r12
0x180024c8d  pop     rdi
0x180024c8e  pop     rsi
0x180024c8f  pop     rbx
0x180024c90  pop     rbp
0x180024c91  retn
0x180024c92  mov     rcx, [rsp+120h+pitem]
0x180024c97  lea     r8, [rbx+80h]
0x180024c9e  lea     rdx, IID_IBindStatusCallback
0x180024ca5  mov     rax, [rcx]
0x180024ca8  mov     rax, [rax]
0x180024cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cb0  mov     rcx, [rsp+120h+pitem]
0x180024cb5  mov     esi, eax
0x180024cb7  mov     rax, [rcx]
0x180024cba  mov     rax, [rax+10h]
0x180024cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cc3  test    esi, esi
0x180024cc5  js      short loc_180024C57
0x180024cc7  cmp     [rbx+80h], r12
0x180024cce  jz      loc_180025D49
0x180024cd4  mov     eax, [rbp+3Fh+arg_20]
0x180024cd7  mov     [rbx+110h], eax
0x180024cdd  test    eax, eax
0x180024cdf  jnz     loc_180025D53
0x180024ce5  lea     r15, [rbx+190h]
0x180024cec  xor     edi, edi
0x180024cee  mov     [r15], rdi
0x180024cf1  lea     rdx, IID_IAsyncBindCtx
0x180024cf8  mov     rax, [r14]
0x180024cfb  mov     r8, r15
0x180024cfe  mov     rcx, r14
0x180024d01  mov     rax, [rax]
0x180024d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d09  mov     esi, eax
0x180024d0b  mov     rcx, r14
0x180024d0e  test    eax, eax
0x180024d10  jz      short loc_180024D17
0x180024d12  mov     esi, edi
0x180024d14  mov     [r15], rdi
0x180024d17  mov     rax, [r14]
0x180024d1a  mov     rax, [rax+8]
0x180024d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d23  cmp     [r15], rdi
0x180024d26  jnz     loc_180024DB0
0x180024d2c  mov     ecx, 48h ; 'H'; cb
0x180024d31  call    cs:__imp_CoTaskMemAlloc
0x180024d37  mov     rdi, rax
0x180024d3a  test    rax, rax
0x180024d3d  jz      loc_180025C3D
0x180024d43  xor     eax, eax
0x180024d45  mov     rcx, r14
0x180024d48  mov     [rdi+14h], rax
0x180024d4c  mov     [rdi+1Ch], eax
0x180024d4f  mov     [rdi+28h], rax
0x180024d53  mov     [rdi+30h], rax
0x180024d57  mov     [rdi+38h], rax
0x180024d5b  mov     [rdi+40h], rax
0x180024d5f  lea     rax, ??_7CBindCtx@@6BIBindCtx@@@; const CBindCtx::`vftable'{for `IBindCtx'}
0x180024d66  mov     [rdi], rax
0x180024d69  lea     rax, ??_7CBindCtx@@6BIMarshal@@@; const CBindCtx::`vftable'{for `IMarshal'}
0x180024d70  mov     [rdi+8], rax
0x180024d74  mov     dword ptr [rdi+10h], 1
0x180024d7b  mov     [rdi+20h], r14
0x180024d7f  mov     rax, [r14]
0x180024d82  mov     rax, [rax+8]
0x180024d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d8b  mov     [rdi+18h], r12
0x180024d8f  call    cs:__imp_GetCurrentThreadId
0x180024d95  mov     [rdi+38h], eax
0x180024d98  xor     eax, eax
0x180024d9a  mov     [rdi+28h], rax
0x180024d9e  mov     [rdi+30h], rax
0x180024da2  mov     [rdi+40h], rax
0x180024da6  lock inc cs:?g_cRef@@3VCRefCount@@A; CRefCount g_cRef
0x180024dad  mov     [r15], rdi
0x180024db0  mov     rax, [r14]
0x180024db3  mov     rcx, r14
0x180024db6  mov     rax, [rax+10h]
0x180024dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024dbf  test    esi, esi
0x180024dc1  js      loc_180025DA9
0x180024dc7  mov     rcx, [rbx+0C8h]
0x180024dce  xor     edx, edx
0x180024dd0  mov     esi, edx
0x180024dd2  cmp     rcx, r13
0x180024dd5  jz      loc_180024E7B
0x180024ddb  test    rcx, rcx
0x180024dde  jnz     loc_180025C0A
0x180024de4  test    r13, r13
0x180024de7  jz      short loc_180024E02
0x180024de9  mov     [rbx+0C8h], r13
0x180024df0  mov     rcx, r13
0x180024df3  mov     rax, [r13+0]
0x180024df7  mov     rax, [rax+8]
0x180024dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e00  xor     edx, edx
0x180024e02  mov     rdi, [rbx+0C8h]
0x180024e09  mov     esi, edx
0x180024e0b  mov     r15, [rbx+0D8h]
0x180024e12  mov     eax, [rbx+0E0h]
0x180024e18  mov     [rsp+120h+var_E0], eax
0x180024e1c  cmp     rdi, r15
0x180024e1f  jz      loc_1800259DA
0x180024e25  mov     rcx, [rbx+0E8h]; bstrString
0x180024e2c  test    rcx, rcx
0x180024e2f  jnz     loc_180025DB3
0x180024e35  mov     [rbx+0F0h], rdx
0x180024e3c  mov     [rbx+0F8h], edx
0x180024e42  cmp     rdi, r15
0x180024e45  jz      short loc_180024E6C
0x180024e47  mov     rcx, [rbx+0D8h]
0x180024e4e  test    rcx, rcx
0x180024e51  jz      short loc_180024E6C
0x180024e53  mov     rax, [rcx]
0x180024e56  mov     rax, [rax+10h]
0x180024e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e5f  mov     eax, [rsp+120h+var_E0]
0x180024e63  xor     edx, edx
0x180024e65  mov     [rbx+0D8h], rdx
0x180024e6c  mov     [rbx+0E0h], edx
0x180024e72  test    rdi, rdi
0x180024e75  jnz     loc_18002589A
0x180024e7b  cmp     qword ptr [rbx+0F0h], 0
0x180024e83  jz      loc_180025E2D
0x180024e89  test    esi, esi
0x180024e8b  js      loc_18002533D
0x180024e91  lea     rdi, [rbx+1B8h]
0x180024e98  mov     dword ptr [rdi], 80h
0x180024e9e  test    rdi, rdi
0x180024ea1  jz      short loc_180024EF0
0x180024ea3  mov     rcx, [rdi+70h]
0x180024ea7  test    rcx, rcx
0x180024eaa  jnz     loc_180025E3F
0x180024eb0  mov     rcx, [rdi+8]; pv
0x180024eb4  test    rcx, rcx
0x180024eb7  jnz     loc_180025E50
0x180024ebd  mov     rcx, [rdi+30h]; pv
0x180024ec1  test    rcx, rcx
0x180024ec4  jnz     loc_180025E5B
0x180024eca  lea     rcx, [rdi+10h]; LPSTGMEDIUM
0x180024ece  call    cs:__imp_ReleaseStgMedium
0x180024ed4  lea     rcx, [rbx+1BCh]; void *
0x180024edb  xor     edx, edx; Val
0x180024edd  mov     r8d, 7Ch ; '|'; Size
0x180024ee3  call    memset_0
0x180024ee8  xor     edx, edx
0x180024eea  mov     dword ptr [rdi], 80h
0x180024ef0  lea     r15, [rbx+0B0h]
0x180024ef7  mov     esi, 80004005h
0x180024efc  mov     qword ptr [r15], 0
0x180024f03  mov     [r15+8], edx
0x180024f07  cmp     dword ptr [rbx+0A0h], 0
0x180024f0e  jnz     short loc_180024F7E
0x180024f10  mov     rcx, [rbx+80h]
0x180024f17  lea     r8, [rsp+120h+pitem]
0x180024f1c  mov     [rsp+120h+pitem], rdx
0x180024f21  lea     rdx, _GUID_aaa74ef9_8ee7_4659_88d9_f8c504da73cc
0x180024f28  mov     rax, [rcx]
0x180024f2b  mov     rax, [rax]
0x180024f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f33  mov     r8, rdi
0x180024f36  test    eax, eax
0x180024f38  js      loc_180025B7C
0x180024f3e  mov     rcx, [rsp+120h+pitem]
0x180024f43  lea     rdx, [r15+8]
0x180024f47  mov     [rsp+120h+lpsz], rdx
0x180024f4c  lea     r9, [r15+4]
0x180024f50  mov     rdx, r15
0x180024f53  mov     rax, [rcx]
0x180024f56  mov     rax, [rax+58h]
0x180024f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f5f  mov     rcx, [rsp+120h+pitem]
0x180024f64  mov     esi, eax
0x180024f66  mov     rax, [rcx]
0x180024f69  mov     rax, [rax+10h]
0x180024f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f72  mov     dword ptr [rbx+0A0h], 2
0x180024f7c  xor     edx, edx
0x180024f7e  test    esi, esi
0x180024f80  jz      loc_1800259E7
0x180024f86  js      loc_180025338
0x180024f8c  test    cs:?g_dwSettings@@3KA, 20000000h; ulong g_dwSettings
0x180024f96  mov     r12d, [rbx+1F4h]
0x180024f9d  jnz     loc_180025E66
0x180024fa3  movzx   edi, r12w
0x180024fa7  test    edi, edi
0x180024fa9  jnz     loc_180025E72
0x180024faf  cmp     [rbp+3Fh+arg_20], edi
0x180024fb2  jz      loc_180025933
0x180024fb8  mov     rdx, [rbx+0F0h]; unsigned __int16 *
0x180024fbf  mov     rcx, r14; struct IBindCtx *
0x180024fc2  call    ?IsOInetProtocol@@YAJPEAUIBindCtx@@PEBG@Z; IsOInetProtocol(IBindCtx *,ushort const *)
0x180024fc7  mov     esi, eax
0x180024fc9  test    eax, eax
0x180024fcb  jnz     loc_180025FCD
0x180024fd1  cmp     [rbx+110h], esi
0x180024fd7  mov     eax, 2000100h
0x180024fdc  mov     ecx, 100h
0x180024fe1  lea     rsi, [rbx+178h]
0x180024fe8  cmovz   eax, ecx
0x180024feb  lea     rcx, ?g_mxsTransMgr@@3VCMutexSem@@A; lpCriticalSection
0x180024ff2  mov     edi, eax
0x180024ff4  bts     edi, 1Dh
0x180024ff8  bt      r12d, 16h
0x180024ffd  mov     r12, [rbx+190h]
0x180025004  mov     qword ptr [rbp+3Fh+var_70.Data1], r12
0x180025008  cmovnb  edi, eax
0x18002500b  mov     [rsp+120h+var_E0], edi
0x18002500f  call    cs:__imp_EnterCriticalSection
0x180025015  mov     [rsp+120h+pv], 0
0x18002501e  test    r12, r12
0x180025021  jz      short loc_180025084
0x180025023  mov     rax, [r12]
0x180025027  lea     r8, [rsp+120h+pv]
0x18002502c  lea     rdx, IID_IAsyncBindCtx
0x180025033  mov     rcx, r12
0x180025036  mov     rax, [rax]
0x180025039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002503e  mov     edi, eax
0x180025040  test    eax, eax
0x180025042  jz      loc_180025A04
0x180025048  cmp     edi, 1
0x18002504b  jbe     short loc_180025080
0x18002504d  mov     rax, [r12]
0x180025051  lea     r8, [rsp+120h+pitem]
0x180025056  lea     rdx, aCbindingContex; "CBinding Context"
0x18002505d  mov     [rsp+120h+pitem], 0
0x180025066  mov     rcx, r12
0x180025069  mov     rax, [rax+50h]
0x18002506d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025072  mov     rcx, [rsp+120h+pitem]; this
0x180025077  test    rcx, rcx
0x18002507a  jnz     loc_180025FFC
0x180025080  mov     edi, [rsp+120h+var_E0]
0x180025084  call    cs:__imp_?InternalForkingSupport_ShouldUseEdge@@YA?B_NXZ; InternalForkingSupport_ShouldUseEdge(void)
0x18002508a  test    al, al
0x18002508c  jnz     loc_180025616
0x180025092  mov     ecx, 640h; cb
0x180025097  call    cs:__imp_CoTaskMemAlloc
0x18002509d  mov     r12, rax
0x1800250a0  test    rax, rax
0x1800250a3  jz      loc_180025BB5
0x1800250a9  xor     edx, edx; Val
0x1800250ab  mov     r8d, 640h; Size
0x1800250b1  mov     rcx, rax; void *
0x1800250b4  call    memset_0
0x1800250b9  mov     edx, edi; unsigned int
0x1800250bb  mov     rcx, r12; this
  ... truncated ...
```
