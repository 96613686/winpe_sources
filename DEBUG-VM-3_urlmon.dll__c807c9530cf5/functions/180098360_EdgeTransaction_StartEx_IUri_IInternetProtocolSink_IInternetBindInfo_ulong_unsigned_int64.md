# EdgeTransaction::StartEx(IUri *,IInternetProtocolSink *,IInternetBindInfo *,ulong,unsigned __int64)

- ea: `0x180098360`
- end: `0x1800990b8`
- name: `?StartEx@EdgeTransaction@@UEAAJPEAUIUri@@PEAUIInternetProtocolSink@@PEAUIInternetBindInfo@@K_K@Z`
- size: `3416`
- prototype: `__int64 __usercall@<rax>(EdgeTransaction *__hidden this@<rcx>, struct IUri *@<rdx>, struct IInternetProtocolSink *@<r8>, struct IInternetBindInfo *@<r9>, unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ee8b0`

## callees

- `0x18001a4d0`
- `0x180024260`
- `0x180024ac8`
- `0x180054ad8`
- `0x180057860`
- `0x18005feac`
- `0x180066970`
- `0x1800677f0`
- `0x180068238`
- `0x18006b710`
- `0x18006ef90`
- `0x1800809c0`
- `0x1800978a0`
- `0x180098360`
- `0x180099280`
- `0x18009b9dc`
- `0x1800e826c`
- `0x1800ebb44`
- `0x1800ee4f0`
- `0x1800ee71c`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180098e72`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180098e72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098444`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098457`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098462`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800984a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800984b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009850e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098517`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800985ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098612`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009863d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800986c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800986f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098809`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800989e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098a07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098b6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098b85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098c5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098cf5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098444`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098457`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098462`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800984a9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800984b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009850e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098517`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800985ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098612`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009863d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800986c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800986f1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098809`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800989e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098a07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098b6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098b85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098c5c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180098cf5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009842b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098434`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098491`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009849a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800984f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800984ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009852d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800985e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009861f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098685`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800987dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009886d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098b54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098b61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098c48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098ce1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009842b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098434`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098491`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009849a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800984f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800984ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009852d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800985e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009861f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098685`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800987dd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009886d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098b54`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098b61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098c48`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098ce1`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800988ee`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180098914`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180098961`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800988ee`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180098914`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180098961`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800987a3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800987a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180098888`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180098888`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180098b47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180098b47`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180098b20`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180098b20`

## string_xrefs

- `0x1800990a3`: `onecoreuap\inetcore\urlmon\trans\common\ctransaction.cpp`

## pseudocode

```c
__int64 __fastcall EdgeTransaction::StartEx(
        EdgeTransaction *this,
        struct IUri *a2,
        struct IInternetProtocolSink *a3,
        struct IInternetBindInfo *a4,
        unsigned int a5)
{
  char *v9; // r13
  int v11; // ebx
  struct _RTL_CRITICAL_SECTION *v12; // rcx
  int v13; // esi
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // ebx
  unsigned int v17; // r12d
  int v18; // ebx
  _DWORD *v19; // rax
  struct IInternetProtocolSink *v20; // rdx
  struct IUri *v21; // rdx
  struct IInternetBindInfo *v22; // r8
  void (__fastcall ***v23)(_QWORD, GUID *, struct IInternetProtocolSink **); // rcx
  struct IInternetProtocolSink *v24; // rcx
  __int64 v25; // rcx
  const WCHAR *v26; // r8
  __int64 v27; // rcx
  _WORD *v28; // rax
  unsigned __int64 v29; // r9
  __int64 v30; // rcx
  const WCHAR *v31; // rax
  unsigned __int64 v32; // rdx
  struct IInternetProtocolSink *v33; // rcx
  void (__fastcall ***v34)(_QWORD, GUID *, struct IInternetProtocolSink **); // rcx
  struct IInternetProtocol **v35; // r15
  IID *v36; // rbx
  struct IUnknown **v37; // r14
  COInetSession *v38; // rbx
  unsigned int v39; // ecx
  __int64 v40; // rax
  int v41; // eax
  COInetSession *v42; // rbx
  const unsigned __int16 *v43; // rdx
  int v44; // eax
  struct IUnknown *v45; // rcx
  struct IInternetProtocol *v46; // rcx
  const OLECHAR *v47; // rcx
  struct IServiceProvider *v48; // r8
  _QWORD *v49; // rbx
  __int64 v50; // rbx
  __int64 v51; // rcx
  struct IInternetProtocol *v52; // r12
  struct IUnknownVtbl *lpVtbl; // rax
  struct IInternetProtocol *v54; // rcx
  int v55; // eax
  char *v56; // r9
  char *v57; // r8
  int v58; // eax
  __int64 v59; // rcx
  struct IUnknown *v60; // rcx
  struct IUnknown *v61; // rcx
  struct IUnknown *v62; // r8
  const unsigned __int16 *v63; // rdx
  int v64; // eax
  struct IUnknown *v65; // rbx
  struct IInternetProtocolSink *v66; // rcx
  __int64 v67; // rax
  int v68; // eax
  unsigned int *v70; // r8
  char v71; // al
  int v72; // eax
  struct IInternetProtocolSink *v73; // rcx
  struct IUnknown *lpString2; // [rsp+20h] [rbp-A9h]
  unsigned __int64 cchCount2; // [rsp+28h] [rbp-A1h]
  char v76; // [rsp+40h] [rbp-89h] BYREF
  int v77; // [rsp+44h] [rbp-85h] BYREF
  struct IInternetProtocolSink *v78; // [rsp+48h] [rbp-81h] BYREF
  struct IUnknown *v79; // [rsp+50h] [rbp-79h]
  COInetSession *v80; // [rsp+58h] [rbp-71h]
  int v81; // [rsp+60h] [rbp-69h]
  unsigned int v82; // [rsp+64h] [rbp-65h] BYREF
  IID *rclsid; // [rsp+68h] [rbp-61h]
  LPOLESTR lpsz; // [rsp+70h] [rbp-59h] BYREF
  const OLECHAR *v85; // [rsp+78h] [rbp-51h] BYREF
  struct IInternetProtocolSink *v86; // [rsp+80h] [rbp-49h]
  __int64 v87; // [rsp+88h] [rbp-41h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v88; // [rsp+90h] [rbp-39h] BYREF
  const OLECHAR **v89; // [rsp+B0h] [rbp-19h]
  __int64 v90; // [rsp+B8h] [rbp-11h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+4Fh]

  v86 = a3;
  if ( (unsigned int)dword_180159000 > 5 && (qword_180159010 & 0x20) != 0 && (qword_180159018 & 0x20) == qword_180159018 )
  {
    v90 = 8;
    v85 = (const OLECHAR *)((char *)this - 48);
    v89 = &v85;
    tlgWriteTransfer_BrowserWriteTransfer((__int64)&dword_180159000, byte_180145D00, 0, 0, 3u, &v88);
  }
  v9 = (char *)this - 48;
  if ( this == (EdgeTransaction *)48 )
    return 2147942487LL;
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 1552));
  EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 1552));
  v11 = *((_DWORD *)v9 + 92);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 1552));
  v12 = (struct _RTL_CRITICAL_SECTION *)(v9 + 1552);
  if ( v11 != 4 )
  {
    LeaveCriticalSection(v12);
    v82 = 0;
    _InterlockedIncrement((volatile signed __int32 *)this + 26);
    if ( !a2 || !a4 || !a3 )
    {
      v13 = -2147024809;
LABEL_153:
      if ( (unsigned int)dword_180159000 > 5
        && (qword_180159010 & 0x20) != 0
        && (qword_180159018 & 0x20) == qword_180159018 )
      {
        v85 = (const OLECHAR *)*((_QWORD *)this + 26);
        v77 = v13;
        lpsz = (LPOLESTR)((char *)this - 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          qword_180159018,
          byte_180145CAD,
          v14,
          v15,
          (__int64)&lpsz,
          (__int64)&v77,
          &v85);
      }
      CTransaction::Release((EdgeTransaction *)((char *)this - 48));
      return (unsigned int)v13;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 1552));
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 1552));
    v16 = *((_DWORD *)this + 80);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 1552));
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 1552));
    if ( v16 == 4 )
    {
      v13 = -2147467259;
      goto LABEL_153;
    }
    v17 = a5;
    *((_BYTE *)this + 394) = *((_BYTE *)this + 394) & 0xFB | (a5 >> 20) & 4;
    if ( (a5 & 0x40000000) != 0 )
      *((_DWORD *)this + 93) |= 1u;
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 1552));
    EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 1552));
    v18 = *((_DWORD *)this + 80);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 1552));
    LeaveCriticalSection((LPCRITICAL_SECTION)(v9 + 1552));
    if ( v18 == 2 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
      v19 = (_DWORD *)((char *)this + 368);
      if ( (a5 & 0x2000000) != 0 )
        *v19 |= 0x2000000u;
      if ( (a5 & 0x1000000) != 0 )
      {
        *((_DWORD *)this + 92) &= ~0x10000000u;
        *((_DWORD *)this + 92) |= 0x1000000u;
      }
      else if ( (a5 & 0x10000000) != 0 )
      {
        *v19 |= 0x10000000u;
        COInetProt::InitAttachedBindToObject((EdgeTransaction *)((char *)this + 736));
      }
      v20 = v86;
      *((_DWORD *)this + 177) = a5 & 0xFFFFFDCF;
      EdgeTransaction::SetClientSink((EdgeTransaction *)((char *)this - 48), v20, 0);
      EdgeTransaction::SetClientBindInfo((EdgeTransaction *)((char *)this - 48), a4);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
      v13 = CTransaction::OnAttach(
              (EdgeTransaction *)((char *)this - 48),
              v21,
              v22,
              v86,
              (unsigned int)lpString2,
              cchCount2);
      goto LABEL_153;
    }
    if ( (a5 & 0x8000) != 0 )
      *((_BYTE *)this + 393) &= ~0x20u;
    v78 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1584));
    v23 = (void (__fastcall ***)(_QWORD, GUID *, struct IInternetProtocolSink **))*((_QWORD *)this + 203);
    if ( v23 )
      (**v23)(v23, &GUID_79eac9e5_baf9_11ce_8c82_00aa004ba90b, &v78);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1584));
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
    v13 = CTransaction::SetIUri((EdgeTransaction *)((char *)this - 48), a2);
    if ( v13 < 0 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
      v24 = v78;
      if ( v78 )
      {
        v78 = 0;
        ((void (__fastcall *)(struct IInternetProtocolSink *))v24->lpVtbl->Release)(v24);
      }
      goto LABEL_153;
    }
    v80 = 0;
    EdgeTransaction::SetClientSink((EdgeTransaction *)((char *)this - 48), v86, 0);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1584));
    if ( *((struct IInternetBindInfo **)this + 204) != a4 )
    {
      ((void (__fastcall *)(struct IInternetBindInfo *))a4->lpVtbl->AddRef)(a4);
      v25 = *((_QWORD *)this + 204);
      *((_QWORD *)this + 204) = a4;
      if ( v25 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1584));
    if ( (a5 & 0x2000000) != 0 )
      *((_DWORD *)this + 92) |= 0x2000000u;
    *((_DWORD *)this + 177) = a5 & 0xFFFFFDCF;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
    if ( *((_DWORD *)this + 54) > 6u )
    {
      v26 = (const WCHAR *)*((_QWORD *)this + 26);
      if ( v26 )
      {
        v27 = 6;
        v28 = (_WORD *)*((_QWORD *)this + 26);
        do
        {
          if ( !*v28 )
            break;
          ++v28;
          --v27;
        }
        while ( v27 );
        v29 = 6 - v27;
        if ( !v27 || v29 > 0xFFFFFFFF )
          LODWORD(v29) = 6;
        v30 = 6;
        v31 = L"mhtml:";
        do
        {
          if ( !*v31 )
            break;
          ++v31;
          --v30;
        }
        while ( v30 );
        v32 = 6 - v30;
        if ( !v30 || v32 > 0xFFFFFFFF )
          LODWORD(v32) = 6;
        if ( CompareStringW(0x7Fu, 0x1001u, v26, v29, L"mhtml:", v32) == 2 )
          *((_BYTE *)this + 394) |= 2u;
      }
    }
    v33 = v78;
    if ( v78 )
    {
      v78 = 0;
      ((void (__fastcall *)(struct IInternetProtocolSink *))v33->lpVtbl->Release)(v33);
    }
    v78 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1584));
    v34 = (void (__fastcall ***)(_QWORD, GUID *, struct IInternetProtocolSink **))*((_QWORD *)this + 203);
    if ( v34 )
      (**v34)(v34, &GUID_79eac9e5_baf9_11ce_8c82_00aa004ba90b, &v78);
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1584));
    v35 = (struct IInternetProtocol **)((char *)this + 264);
    if ( !EdgeTransaction::QueryService(
            (EdgeTransaction *)((char *)this - 16),
            &IID_IInternetProtocol,
            &IID_IInternetProtocol,
            (void **)this + 33)
      && *v35 )
    {
      v36 = (IID *)((char *)this + 288);
      v81 = 0;
      rclsid = (IID *)((char *)this + 288);
      *((GUID *)this + 18) = CLSID_FtpProtocol;
      v37 = (struct IUnknown **)((char *)this + 96);
      v79 = 0;
      v77 = 0;
      while ( 1 )
      {
LABEL_76:
        v46 = *v35;
        v85 = 0;
        if ( ((__int64 (__fastcall *)(struct IInternetProtocol *, GUID *, const OLECHAR **))v46->lpVtbl->QueryInterface)(
               v46,
               &IID_ICrossApartmentProtocolHandler,
               &v85) >= 0
          && (v47 = v85) != 0 )
        {
          *((_BYTE *)this + 395) |= 2u;
          (*(void (__fastcall **)(const OLECHAR *))(*(_QWORD *)v47 + 16LL))(v47);
        }
        else
        {
          *((_BYTE *)this + 395) &= ~2u;
        }
        lpsz = 0;
        if ( StringFromCLSID(v36, &lpsz) >= 0 )
        {
          ((void (__fastcall *)(struct IInternetProtocolSink *, __int64, LPOLESTR))v86->lpVtbl->ReportProgress)(
            v86,
            20,
            lpsz);
          CoTaskMemFree(lpsz);
        }
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
        *((_DWORD *)this + 80) = 2;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1504));
        if ( v77 )
        {
          v50 = *((_QWORD *)v9 + 39);
          if ( v50 )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v50 + 8LL))(*((_QWORD *)v9 + 39));
          v51 = *((_QWORD *)this + 106);
          if ( v51 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
          *((_QWORD *)this + 106) = v50;
          v49 = (_QWORD *)((char *)this + 168);
        }
        else
        {
          v49 = (_QWORD *)((char *)this + 168);
          COInetProt::Initialize(
            (EdgeTransaction *)((char *)this + 736),
            (EdgeTransaction *)((char *)this - 48),
            v48,
            v17,
            lpString2,
            *v35,
            v86,
            *((struct IUri **)this + 21));
          EdgeTransaction::SetClientSink((EdgeTransaction *)((char *)this - 48), v86, 0);
          v77 = 1;
        }
        v52 = *v35;
        if ( *v37 )
        {
          lpVtbl = (*v37)->lpVtbl;
          v79 = *v37;
          ((void (*)(void))lpVtbl->AddRef)();
        }
        *((_BYTE *)this + 395) |= 0x20u;
        *v35 = (struct IInternetProtocol *)((char *)this + 736);
        CTransaction::SetProtocolPriority((EdgeTransaction *)((char *)this - 48));
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
        *((_BYTE *)this + 394) |= 0x10u;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
        v54 = *v35;
        v87 = 0;
        v55 = ((__int64 (__fastcall *)(struct IInternetProtocol *, GUID *, __int64 *))v54->lpVtbl->QueryInterface)(
                v54,
                &IID_IInternetProtocolEx,
                &v87);
        v56 = (char *)this - 32;
        v57 = (char *)this - 48;
        if ( v55 < 0 )
          v58 = ((__int64 (__fastcall *)(struct IInternetProtocol *, _QWORD, char *, char *, _DWORD, _QWORD))(*v35)->lpVtbl->Start)(
                  *v35,
                  *((_QWORD *)this + 26),
                  v57,
                  v56,
                  0,
                  0);
        else
          v58 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *, char *, _DWORD, _QWORD))(*(_QWORD *)v87 + 104LL))(
                  v87,
                  *v49,
                  v57,
                  v56,
                  0,
                  0);
        v13 = v58;
        if ( v87 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v87 + 16LL))(v87);
          v87 = 0;
        }
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
        *((_BYTE *)this + 394) &= ~0x10u;
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 576));
        if ( (*((_BYTE *)this + 394) & 0x20) != 0 )
          break;
        if ( v13 == -2147483638 )
        {
          v13 = 0;
          goto LABEL_133;
        }
        if ( v13 != -2146697199 )
        {
          if ( v13 )
          {
            *((_BYTE *)this + 392) |= 4u;
            if ( *v35 )
            {
              if ( (*((_BYTE *)this + 393) & 2) == 0 )
              {
                v66 = v78;
                if ( v78 )
                {
                  v78 = 0;
                  ((void (__fastcall *)(struct IInternetProtocolSink *))v66->lpVtbl->Release)(v66);
                }
                EdgeTransaction::GetClientSink((EdgeTransaction *)((char *)this - 48), &v78);
                *((_BYTE *)this + 393) |= 1u;
                if ( !*((_DWORD *)this + 103) && (v13 == -2146697190 || IsDualEngineProcess() && v13 == -2146697182) )
                  goto LABEL_126;
                v77 = 1;
                lpsz = (LPOLESTR)&v76;
                v67 = *((_QWORD *)this + 9);
                v76 = 0;
                v68 = (*(__int64 (__fastcall **)(char *, __int64, LPOLESTR *, int *))(v67 + 32))(
                        (char *)this + 72,
                        3,
                        &lpsz,
                        &v77);
                if ( !v68 && v77 != 1 )
                  wil::details::in1diag3::_FailFast_Unexpected(
                    retaddr,
                    (void *)0xD6B,
                    (unsigned int)"onecoreuap\\inetcore\\urlmon\\trans\\common\\ctransaction.cpp",
                    (const char *)retaddr);
                if ( !v68 && v76 )
                {
LABEL_126:
                  v70 = (unsigned int *)((char *)this + 416);
                  *((_DWORD *)this + 103) = v13;
                  *((_DWORD *)this + 104) = 12017;
                }
                else
                {
                  v70 = (unsigned int *)((char *)this + 416);
                }
                ((void (__fastcall *)(struct IInternetProtocolSink *, _QWORD, _QWORD, _QWORD))v78->lpVtbl->ReportResult)(
                  v78,
                  *((unsigned int *)this + 103),
                  *v70,
                  0);
                EdgeTransaction::Terminate(this, 0);
              }
            }
          }
          goto LABEL_133;
        }
        v59 = *((_QWORD *)this + 106);
        if ( v59 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
        *((_QWORD *)this + 106) = 0;
        if ( v52 )
        {
          ((void (__fastcall *)(struct IInternetProtocol *))v52->lpVtbl->Release)(v52);
          v52 = 0;
        }
        v60 = *v37;
        *v35 = 0;
        if ( v60 )
        {
          ((void (__fastcall *)(struct IUnknown *))v60->lpVtbl->Release)(v60);
          v61 = v79;
          *v37 = 0;
          ((void (__fastcall *)(struct IUnknown *))v61->lpVtbl->Release)(v61);
          v79 = 0;
        }
        v62 = (struct IUnknown *)((char *)this - 32);
        v36 = rclsid;
        v63 = (const unsigned __int16 *)*((_QWORD *)this + 26);
        if ( v81 )
        {
          v64 = COInetSession::CreateNextProtocol(
                  v80,
                  v63,
                  v62,
                  v37,
                  (struct IInternetProtocol **)this + 33,
                  rclsid,
                  &v82);
        }
        else
        {
          v64 = COInetSession::CreateFirstProtocol(
                  v80,
                  v63,
                  v62,
                  v37,
                  (struct IInternetProtocol **)this + 33,
                  rclsid,
                  &v82,
                  (unsigned __int8)(*((_BYTE *)this + 394) & 4) << 20);
          v81 = 1;
        }
        v13 = v64;
        if ( v64 )
        {
          *v35 = 0;
          v65 = 0;
          *v37 = 0;
          goto LABEL_134;
        }
        v17 = a5;
      }
      if ( v13 || *((char *)this + 392) >= 0 )
        v13 = EdgeTransaction::Abort(this, *((_DWORD *)this + 100), *((_DWORD *)this + 101));
LABEL_133:
      v65 = v79;
LABEL_134:
      if ( v52 )
        ((void (__fastcall *)(struct IInternetProtocol *))v52->lpVtbl->Release)(v52);
      if ( v65 )
        ((void (__fastcall *)(struct IUnknown *))v65->lpVtbl->Release)(v65);
      if ( (a5 & 0x80u) != 0 && v13 >= 0 )
      {
        v71 = *((_BYTE *)this + 394);
        if ( (v71 & 1) == 0 )
        {
          *((_BYTE *)this + 394) = v71 | 1;
          v72 = EdgeTransaction::CompleteOperation((EdgeTransaction *)((char *)this - 48), a5 & 0x11000000);
          *((_BYTE *)this + 394) &= ~1u;
          v13 = v72;
        }
      }
      v73 = v78;
      if ( !v78 )
        goto LABEL_150;
      v78 = 0;
      goto LABEL_149;
    }
    EnterCriticalSection(&g_mxsOInet);
    v38 = g_pCOInetSession;
    if ( g_pCOInetSession )
    {
      v13 = 0;
    }
    else
    {
      v38 = (COInetSession *)CoTaskMemAlloc(0x180u);
      v13 = -2147024882;
      if ( v38 )
      {
        *((_DWORD *)v38 + 5) = 0;
        memset_0((char *)v38 + 40, 0, 0x158u);
        *(_QWORD *)v38 = &COInetSession::`vftable'{for `IInternetSession'};
        *((_DWORD *)v38 + 4) = 1;
        *((_QWORD *)v38 + 1) = &COInetSession::`vftable'{for `IInternetProtocolInfo'};
        *((_QWORD *)v38 + 3) = &CProtMgr::`vftable';
        *((_DWORD *)v38 + 8) = 1;
        *((_DWORD *)v38 + 9) = -1;
        InitializeCriticalSection((LPCRITICAL_SECTION)v38 + 1);
        *((_QWORD *)v38 + 11) = 0;
        *((_QWORD *)v38 + 10) = 0;
        *((_QWORD *)v38 + 12) = &CProtMgr::`vftable';
        *((_DWORD *)v38 + 26) = 1;
        *((_DWORD *)v38 + 27) = -1;
        InitializeCriticalSection((LPCRITICAL_SECTION)((char *)v38 + 112));
        *((_QWORD *)v38 + 20) = 0;
        *((_QWORD *)v38 + 19) = 0;
        *((_QWORD *)v38 + 21) = 0;
        *((_DWORD *)v38 + 27) = 0;
        *((_QWORD *)v38 + 12) = &CProtMgrNameSpace::`vftable';
        *((_QWORD *)v38 + 22) = &CProtMgr::`vftable';
        *((_DWORD *)v38 + 46) = 1;
        *((_DWORD *)v38 + 47) = -1;
        InitializeCriticalSection((LPCRITICAL_SECTION)((char *)v38 + 192));
        *((_QWORD *)v38 + 30) = 0;
        v39 = 0;
        *((_QWORD *)v38 + 29) = 0;
        *((_QWORD *)v38 + 22) = &CProtMgrMimeHandler::`vftable';
        *((_DWORD *)v38 + 62) = 8;
        do
        {
          v40 = v39++;
          *((_QWORD *)v38 + 2 * v40 + 33) = 0;
        }
        while ( v39 < *((_DWORD *)v38 + 62) );
        _InterlockedIncrement((volatile signed __int32 *)&g_cRef);
        v41 = 0;
        g_pCOInetSession = v38;
      }
      else
      {
        v38 = g_pCOInetSession;
        v41 = -2147024882;
      }
      if ( !v38 )
      {
        LeaveCriticalSection(&g_mxsOInet);
        goto LABEL_146;
      }
      v13 = v41;
    }
    _InterlockedIncrement((volatile signed __int32 *)v38 + 4);
    v42 = g_pCOInetSession;
    v80 = g_pCOInetSession;
    LeaveCriticalSection(&g_mxsOInet);
    if ( !v13 )
    {
      v43 = (const unsigned __int16 *)*((_QWORD *)this + 26);
      v37 = (struct IUnknown **)((char *)this + 96);
      v44 = *((_BYTE *)this + 394) & 4;
      rclsid = (IID *)((char *)this + 288);
      v13 = COInetSession::CreateFirstProtocol(
              v42,
              v43,
              (struct IUnknown *)this - 4,
              (struct IUnknown **)this + 12,
              (struct IInternetProtocol **)this + 33,
              (IID *)this + 18,
              &v82,
              v44 << 20);
      if ( !v13 )
      {
        v45 = *v37;
        v81 = 1;
        if ( v45 && *((_DWORD *)this + 364) == 1 )
        {
          IUnknown_EnablePreBinding(v45, 1);
          v36 = (IID *)((char *)this + 288);
          v79 = 0;
          v77 = 0;
        }
        else
        {
          v80 = v42;
          v36 = (IID *)((char *)this + 288);
          rclsid = (IID *)((char *)this + 288);
          v79 = 0;
          v77 = 0;
        }
        goto LABEL_76;
      }
      v80 = v42;
      goto LABEL_147;
    }
    v80 = v42;
LABEL_146:
    v37 = (struct IUnknown **)((char *)this + 96);
LABEL_147:
    v73 = v78;
    *v35 = 0;
    *v37 = 0;
    if ( !v73 )
      goto LABEL_150;
    v78 = 0;
LABEL_149:
    ((void (__fastcall *)(struct IInternetProtocolSink *))v73->lpVtbl->Release)(v73);
LABEL_150:
    if ( v80 )
      _InterlockedDecrement((volatile signed __int32 *)v80 + 4);
    goto LABEL_153;
  }
  v13 = -2147467259;
  LeaveCriticalSection(v12);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180098360  push    rbp
0x180098362  push    rsi
0x180098363  push    rdi
0x180098364  push    r12
0x180098366  push    r13
0x180098368  push    r15
0x18009836a  lea     rbp, [rsp-1Fh]
0x18009836f  sub     rsp, 0E8h
0x180098376  mov     rax, cs:__security_cookie
0x18009837d  xor     rax, rsp
0x180098380  mov     [rbp+47h+var_50], rax
0x180098384  mov     eax, cs:dword_180159000
0x18009838a  mov     r15, r9
0x18009838d  mov     [rbp+47h+var_90], r8
0x180098391  mov     r12, r8
0x180098394  mov     rsi, rdx
0x180098397  mov     rdi, rcx
0x18009839a  cmp     eax, 5
0x18009839d  jbe     short loc_1800983FE
0x18009839f  mov     rcx, cs:qword_180159018
0x1800983a6  mov     rax, cs:qword_180159010
0x1800983ad  test    al, 20h
0x1800983af  jz      short loc_1800983FE
0x1800983b1  mov     rax, rcx
0x1800983b4  and     eax, 20h
0x1800983b7  cmp     rax, rcx
0x1800983ba  jnz     short loc_1800983FE
0x1800983bc  lea     rax, [rdi-30h]
0x1800983c0  mov     [rbp+47h+var_58], 8
0x1800983c8  mov     [rbp+47h+var_98], rax
0x1800983cc  lea     rdx, byte_180145D00
0x1800983d3  lea     rax, [rbp+47h+var_98]
0x1800983d7  xor     r9d, r9d
0x1800983da  mov     [rbp+47h+var_60], rax
0x1800983de  lea     rcx, dword_180159000
0x1800983e5  lea     rax, [rbp+47h+var_80]
0x1800983e9  xor     r8d, r8d
0x1800983ec  mov     qword ptr [rsp+110h+cchCount2], rax; unsigned __int64
0x1800983f1  mov     dword ptr [rsp+110h+lpString2], 3; unsigned int
0x1800983f9  call    _tlgWriteTransfer_BrowserWriteTransfer
0x1800983fe  lea     r13, [rdi-30h]
0x180098402  test    r13, r13
0x180098405  jnz     short loc_180098411
0x180098407  mov     eax, 80070057h
0x18009840c  jmp     loc_180099086
0x180098411  mov     [rsp+110h+var_30], rbx
0x180098419  mov     [rsp+110h+var_38], r14
0x180098421  lea     r14, [r13+610h]
0x180098428  mov     rcx, r14; lpCriticalSection
0x18009842b  call    cs:__imp_EnterCriticalSection
0x180098431  mov     rcx, r14; lpCriticalSection
0x180098434  call    cs:__imp_EnterCriticalSection
0x18009843a  mov     ebx, [r13+170h]
0x180098441  mov     rcx, r14; lpCriticalSection
0x180098444  call    cs:__imp_LeaveCriticalSection
0x18009844a  mov     rcx, r14; lpCriticalSection
0x18009844d  cmp     ebx, 4
0x180098450  jnz     short loc_180098462
0x180098452  mov     esi, 80004005h
0x180098457  call    cs:__imp_LeaveCriticalSection
0x18009845d  jmp     loc_180099074
0x180098462  call    cs:__imp_LeaveCriticalSection
0x180098468  mov     [rbp+47h+var_AC], 0
0x18009846f  lock inc dword ptr [rdi+68h]
0x180098473  test    rsi, rsi
0x180098476  jz      loc_180099004
0x18009847c  test    r15, r15
0x18009847f  jz      loc_180099004
0x180098485  test    r12, r12
0x180098488  jz      loc_180099004
0x18009848e  mov     rcx, r14; lpCriticalSection
0x180098491  call    cs:__imp_EnterCriticalSection
0x180098497  mov     rcx, r14; lpCriticalSection
0x18009849a  call    cs:__imp_EnterCriticalSection
0x1800984a0  mov     ebx, [rdi+140h]
0x1800984a6  mov     rcx, r14; lpCriticalSection
0x1800984a9  call    cs:__imp_LeaveCriticalSection
0x1800984af  mov     rcx, r14; lpCriticalSection
0x1800984b2  call    cs:__imp_LeaveCriticalSection
0x1800984b8  cmp     ebx, 4
0x1800984bb  jnz     short loc_1800984C7
0x1800984bd  mov     esi, 80004005h
0x1800984c2  jmp     loc_180099009
0x1800984c7  mov     r12d, [rbp+47h+arg_20]
0x1800984cb  mov     ecx, r12d
0x1800984ce  movzx   eax, byte ptr [rdi+18Ah]
0x1800984d5  shr     ecx, 14h
0x1800984d8  and     al, 0FBh
0x1800984da  and     cl, 4
0x1800984dd  or      cl, al
0x1800984df  mov     [rdi+18Ah], cl
0x1800984e5  bt      r12d, 1Eh
0x1800984ea  jnb     short loc_1800984F3
0x1800984ec  or      dword ptr [rdi+174h], 1
0x1800984f3  mov     rcx, r14; lpCriticalSection
0x1800984f6  call    cs:__imp_EnterCriticalSection
0x1800984fc  mov     rcx, r14; lpCriticalSection
0x1800984ff  call    cs:__imp_EnterCriticalSection
0x180098505  mov     ebx, [rdi+140h]
0x18009850b  mov     rcx, r14; lpCriticalSection
0x18009850e  call    cs:__imp_LeaveCriticalSection
0x180098514  mov     rcx, r14; lpCriticalSection
0x180098517  call    cs:__imp_LeaveCriticalSection
0x18009851d  cmp     ebx, 2
0x180098520  jnz     loc_1800985C5
0x180098526  lea     rcx, [rdi+240h]; lpCriticalSection
0x18009852d  call    cs:__imp_EnterCriticalSection
0x180098533  lea     rax, [rdi+170h]
0x18009853a  bt      r12d, 19h
0x18009853f  jnb     short loc_180098547
0x180098541  or      dword ptr [rax], 2000000h
0x180098547  bt      r12d, 18h
0x18009854c  jnb     short loc_180098564
0x18009854e  and     dword ptr [rdi+170h], 0EFFFFFFFh
0x180098558  or      dword ptr [rdi+170h], 1000000h
0x180098562  jmp     short loc_18009857D
0x180098564  bt      r12d, 1Ch
0x180098569  jnb     short loc_18009857D
0x18009856b  or      dword ptr [rax], 10000000h
0x180098571  lea     rcx, [rdi+2E0h]; this
0x180098578  call    ?InitAttachedBindToObject@COInetProt@@QEAAXXZ; COInetProt::InitAttachedBindToObject(void)
0x18009857d  mov     rdx, [rbp+47h+var_90]; struct IInternetProtocolSink *
0x180098581  and     r12d, 0FFFFFDCFh
0x180098588  xor     r8d, r8d; bool
0x18009858b  mov     [rdi+2C4h], r12d
0x180098592  mov     rcx, r13; this
0x180098595  call    ?SetClientSink@EdgeTransaction@@MEAAXPEAUIInternetProtocolSink@@_N@Z; EdgeTransaction::SetClientSink(IInternetProtocolSink *,bool)
0x18009859a  mov     rdx, r15; struct IInternetBindInfo *
0x18009859d  mov     rcx, r13; this
0x1800985a0  call    ?SetClientBindInfo@EdgeTransaction@@MEAAXPEAUIInternetBindInfo@@@Z; EdgeTransaction::SetClientBindInfo(IInternetBindInfo *)
0x1800985a5  lea     rcx, [rdi+240h]; lpCriticalSection
0x1800985ac  call    cs:__imp_LeaveCriticalSection
0x1800985b2  mov     r9, [rbp+47h+var_90]; struct IInternetProtocolSink *
0x1800985b6  mov     rcx, r13; this
0x1800985b9  call    ?OnAttach@CTransaction@@QEAAJPEAUIUri@@PEAUIInternetBindInfo@@PEAUIInternetProtocolSink@@K_K@Z; CTransaction::OnAttach(IUri *,IInternetBindInfo *,IInternetProtocolSink *,ulong,unsigned __int64)
0x1800985be  mov     esi, eax
0x1800985c0  jmp     loc_180099009
0x1800985c5  bt      r12d, 0Fh
0x1800985ca  jnb     short loc_1800985D3
0x1800985cc  and     byte ptr [rdi+189h], 0DFh
0x1800985d3  lea     rbx, [rdi+630h]
0x1800985da  mov     [rsp+110h+var_C8], 0
0x1800985e3  mov     rcx, rbx; lpCriticalSection
0x1800985e6  call    cs:__imp_EnterCriticalSection
0x1800985ec  mov     rcx, [rdi+658h]
0x1800985f3  test    rcx, rcx
0x1800985f6  jz      short loc_18009860F
0x1800985f8  mov     rax, [rcx]
0x1800985fb  lea     r8, [rsp+110h+var_C8]
0x180098600  lea     rdx, _GUID_79eac9e5_baf9_11ce_8c82_00aa004ba90b
0x180098607  mov     rax, [rax]
0x18009860a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009860f  mov     rcx, rbx; lpCriticalSection
0x180098612  call    cs:__imp_LeaveCriticalSection
0x180098618  lea     rcx, [rdi+240h]; lpCriticalSection
0x18009861f  call    cs:__imp_EnterCriticalSection
0x180098625  mov     rdx, rsi; struct IUri *
0x180098628  mov     rcx, r13; this
0x18009862b  call    ?SetIUri@CTransaction@@QEAAJPEAUIUri@@@Z; CTransaction::SetIUri(IUri *)
0x180098630  mov     esi, eax
0x180098632  test    eax, eax
0x180098634  jns     short loc_18009866B
0x180098636  lea     rcx, [rdi+240h]; lpCriticalSection
0x18009863d  call    cs:__imp_LeaveCriticalSection
0x180098643  mov     rcx, [rsp+110h+var_C8]
0x180098648  test    rcx, rcx
0x18009864b  jz      loc_180099009
0x180098651  mov     [rsp+110h+var_C8], 0
0x18009865a  mov     rax, [rcx]
0x18009865d  mov     rax, [rax+10h]
0x180098661  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098666  jmp     loc_180099009
0x18009866b  mov     rdx, [rbp+47h+var_90]; struct IInternetProtocolSink *
0x18009866f  xor     r8d, r8d; bool
0x180098672  mov     rcx, r13; this
0x180098675  mov     [rbp+47h+var_B8], 0
0x18009867d  call    ?SetClientSink@EdgeTransaction@@MEAAXPEAUIInternetProtocolSink@@_N@Z; EdgeTransaction::SetClientSink(IInternetProtocolSink *,bool)
0x180098682  mov     rcx, rbx; lpCriticalSection
0x180098685  call    cs:__imp_EnterCriticalSection
0x18009868b  cmp     [rdi+660h], r15
0x180098692  jz      short loc_1800986C2
0x180098694  mov     rax, [r15]
0x180098697  mov     rcx, r15
0x18009869a  mov     rax, [rax+8]
0x18009869e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800986a3  mov     rcx, [rdi+660h]
0x1800986aa  mov     [rdi+660h], r15
0x1800986b1  test    rcx, rcx
0x1800986b4  jz      short loc_1800986C2
0x1800986b6  mov     rax, [rcx]
0x1800986b9  mov     rax, [rax+10h]
0x1800986bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800986c2  mov     rcx, rbx; lpCriticalSection
0x1800986c5  call    cs:__imp_LeaveCriticalSection
0x1800986cb  bt      r12d, 19h
0x1800986d0  jnb     short loc_1800986DC
0x1800986d2  or      dword ptr [rdi+170h], 2000000h
0x1800986dc  mov     eax, r12d
0x1800986df  lea     rcx, [rdi+240h]; lpCriticalSection
0x1800986e6  and     eax, 0FFFFFDCFh
0x1800986eb  mov     [rdi+2C4h], eax
0x1800986f1  call    cs:__imp_LeaveCriticalSection
0x1800986f7  cmp     dword ptr [rdi+0D8h], 6
0x1800986fe  jbe     loc_1800987B7
0x180098704  mov     r8, [rdi+0D0h]; lpString1
0x18009870b  test    r8, r8
0x18009870e  jz      loc_1800987B7
0x180098714  mov     ecx, 6
0x180098719  mov     rax, r8
0x18009871c  nop     dword ptr [rax+00h]
0x180098720  cmp     word ptr [rax], 0
0x180098724  jz      short loc_180098730
0x180098726  add     rax, 2
0x18009872a  sub     rcx, 1
0x18009872e  jnz     short loc_180098720
0x180098730  xor     r14d, r14d
0x180098733  mov     r9d, 6
0x180098739  sub     r9, rcx
0x18009873c  mov     r10d, 0FFFFFFFFh
0x180098742  test    rcx, rcx
0x180098745  cmovz   r9, r14
0x180098749  jz      short loc_180098750
0x18009874b  cmp     r9, r10
0x18009874e  jbe     short loc_180098756
0x180098750  mov     r9d, 6; cchCount1
0x180098756  lea     r11, aMhtml_1; "mhtml:"
0x18009875d  mov     ecx, 6
0x180098762  mov     rax, r11
0x180098765  cmp     [rax], r14w
0x180098769  jz      short loc_180098775
0x18009876b  add     rax, 2
0x18009876f  sub     rcx, 1
0x180098773  jnz     short loc_180098765
0x180098775  mov     edx, 6
0x18009877a  sub     rdx, rcx
0x18009877d  test    rcx, rcx
0x180098780  cmovz   rdx, r14
0x180098784  jz      short loc_18009878B
0x180098786  cmp     rdx, r10
0x180098789  jbe     short loc_180098790
0x18009878b  mov     edx, 6
0x180098790  mov     [rsp+110h+cchCount2], edx; cchCount2
0x180098794  mov     ecx, 7Fh; Locale
0x180098799  mov     edx, 1001h; dwCmpFlags
0x18009879e  mov     [rsp+110h+lpString2], r11; lpString2
0x1800987a3  call    cs:__imp_CompareStringW
0x1800987a9  add     eax, 0FFFFFFFEh
0x1800987ac  jnz     short loc_1800987BA
0x1800987ae  or      byte ptr [rdi+18Ah], 2
0x1800987b5  jmp     short loc_1800987BA
0x1800987b7  xor     r14d, r14d
0x1800987ba  mov     rcx, [rsp+110h+var_C8]
0x1800987bf  test    rcx, rcx
0x1800987c2  jz      short loc_1800987D5
0x1800987c4  mov     [rsp+110h+var_C8], r14
0x1800987c9  mov     rax, [rcx]
0x1800987cc  mov     rax, [rax+10h]
0x1800987d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800987d5  mov     rcx, rbx; lpCriticalSection
0x1800987d8  mov     [rsp+110h+var_C8], r14
0x1800987dd  call    cs:__imp_EnterCriticalSection
0x1800987e3  mov     rcx, [rdi+658h]
0x1800987ea  test    rcx, rcx
0x1800987ed  jz      short loc_180098806
0x1800987ef  mov     rax, [rcx]
0x1800987f2  lea     r8, [rsp+110h+var_C8]
0x1800987f7  lea     rdx, _GUID_79eac9e5_baf9_11ce_8c82_00aa004ba90b
0x1800987fe  mov     rax, [rax]
0x180098801  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098806  mov     rcx, rbx; lpCriticalSection
0x180098809  call    cs:__imp_LeaveCriticalSection
0x18009880f  lea     r15, [rdi+108h]
0x180098816  mov     r9, r15; void **
0x180098819  lea     rcx, [rdi-10h]; this
0x18009881d  lea     r8, IID_IInternetProtocol; struct _GUID *
0x180098824  lea     rdx, IID_IInternetProtocol; struct _GUID *
0x18009882b  call    ?QueryService@EdgeTransaction@@UEAAJAEBU_GUID@@0PEAPEAX@Z; EdgeTransaction::QueryService(_GUID const &,_GUID const &,void * *)
0x180098830  test    eax, eax
0x180098832  jnz     short loc_180098866
0x180098834  cmp     qword ptr [r15], 0
0x180098838  jz      short loc_180098866
0x18009883a  movups  xmm0, xmmword ptr cs:CLSID_FtpProtocol.Data1
0x180098841  lea     rbx, [rdi+120h]
0x180098848  mov     [rbp+47h+var_B0], r14d
0x18009884c  xor     eax, eax
0x18009884e  mov     [rbp+47h+rclsid], rbx
0x180098852  movups  xmmword ptr [rbx], xmm0
0x180098855  lea     r14, [rdi+60h]
0x180098859  mov     [rbp+47h+var_C0], rax
0x18009885d  mov     [rsp+110h+var_CC], eax
0x180098861  jmp     loc_180098AC4
0x180098866  lea     rcx, ?g_mxsOInet@@3VCMutexSem@@A; lpCriticalSection
0x18009886d  call    cs:__imp_EnterCriticalSection
0x180098873  mov     rbx, cs:?g_pCOInetSession@@3PEAVCOInetSession@@EA; COInetSession * g_pCOInetSession
0x18009887a  test    rbx, rbx
0x18009887d  jnz     loc_1800989EE
0x180098883  mov     ecx, 180h; cb
0x180098888  call    cs:__imp_CoTaskMemAlloc
0x18009888e  mov     rbx, rax
0x180098891  mov     esi, 8007000Eh
  ... truncated ...
```
