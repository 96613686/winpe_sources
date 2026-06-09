# CIMRequestRAEvent::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x140011fc0`
- end: `0x14001287e`
- name: `?Invoke@CIMRequestRAEvent@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `2238`
- prototype: `__int64 __fastcall(CIMRequestRAEvent *this, unsigned int, const struct _GUID *, __int64, unsigned __int16, struct tagDISPPARAMS *)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1400035c8`
- `0x140004f54`
- `0x14000e664`
- `0x14000e6fc`
- `0x14000e778`
- `0x140011a4c`
- `0x140011b74`
- `0x140011bd8`
- `0x140011fc0`
- `0x140012b4c`
- `0x140013c10`
- `0x140014618`
- `0x140014740`
- `0x140014894`
- `0x140014a90`
- `0x140014ccc`
- `0x140015240`
- `0x140015400`
- `0x1400154b0`
- `0x140015548`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001240d`
- `KERNEL32!GetLastError` at `0x1400125f4`
- `KERNEL32!GetLastError` at `0x14001240d`
- `KERNEL32!GetLastError` at `0x1400125f4`
- `KERNEL32!CloseHandle` at `0x140012430`
- `KERNEL32!CloseHandle` at `0x140012633`
- `KERNEL32!CloseHandle` at `0x140012430`
- `KERNEL32!CloseHandle` at `0x140012633`
- `KERNEL32!HeapAlloc` at `0x14001232a`
- `KERNEL32!HeapAlloc` at `0x14001232a`
- `KERNEL32!GetProcessHeap` at `0x140012318`
- `KERNEL32!GetProcessHeap` at `0x1400123f9`
- `KERNEL32!GetProcessHeap` at `0x140012318`
- `KERNEL32!GetProcessHeap` at `0x1400123f9`
- `KERNEL32!CreateThread` at `0x1400123cc`
- `KERNEL32!CreateThread` at `0x1400125e9`
- `KERNEL32!CreateThread` at `0x1400123cc`
- `KERNEL32!CreateThread` at `0x1400125e9`
- `KERNEL32!HeapFree` at `0x140012407`
- `KERNEL32!HeapFree` at `0x140012407`
- `OLEAUT32!__imp_SysFreeString` at `0x1400120b5`
- `OLEAUT32!__imp_SysFreeString` at `0x1400121bc`
- `OLEAUT32!__imp_SysFreeString` at `0x140012241`
- `OLEAUT32!__imp_SysFreeString` at `0x1400123df`
- `OLEAUT32!__imp_SysFreeString` at `0x1400123f0`
- `OLEAUT32!__imp_SysFreeString` at `0x140012662`
- `OLEAUT32!__imp_SysFreeString` at `0x14001266c`
- `OLEAUT32!__imp_SysFreeString` at `0x140012676`
- `OLEAUT32!__imp_SysFreeString` at `0x14001267e`
- `OLEAUT32!__imp_SysFreeString` at `0x140012687`
- `OLEAUT32!__imp_SysFreeString` at `0x1400120b5`
- `OLEAUT32!__imp_SysFreeString` at `0x1400121bc`
- `OLEAUT32!__imp_SysFreeString` at `0x140012241`
- `OLEAUT32!__imp_SysFreeString` at `0x1400123df`
- `OLEAUT32!__imp_SysFreeString` at `0x1400123f0`
- `OLEAUT32!__imp_SysFreeString` at `0x140012662`
- `OLEAUT32!__imp_SysFreeString` at `0x14001266c`
- `OLEAUT32!__imp_SysFreeString` at `0x140012676`
- `OLEAUT32!__imp_SysFreeString` at `0x14001267e`
- `OLEAUT32!__imp_SysFreeString` at `0x140012687`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400126fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400126fd`

## string_xrefs

- `0x14001200f`: `base\diagnosis\ra\dcom\src\raimrequestevnt.cpp`

## pseudocode

```c
__int64 __fastcall CIMRequestRAEvent::Invoke(
        CIMRequestRAEvent *this,
        unsigned int a2,
        const struct _GUID *a3,
        __int64 a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6)
{
  unsigned __int16 *v8; // rbx
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  const struct _EVENT_DESCRIPTOR *v11; // rdx
  CEventLogger *v12; // rcx
  unsigned int v13; // edi
  unsigned int v14; // edi
  unsigned int v15; // edi
  int Instance; // edi
  unsigned __int16 **v17; // rax
  const struct _EVENT_DESCRIPTOR *v18; // rdx
  CEventLogger *v19; // rcx
  const struct _EVENT_DESCRIPTOR *v20; // rdx
  CEventLogger *v21; // rcx
  unsigned int v22; // r9d
  int v23; // eax
  int v24; // eax
  int v25; // eax
  OLECHAR *v26; // rax
  signed int SalemTicket; // eax
  const struct _EVENT_DESCRIPTOR *v28; // rdx
  unsigned int v29; // r9d
  __int64 v30; // rcx
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rdx
  const struct _EVENT_DESCRIPTOR *v34; // rdx
  CEventLogger *v35; // rcx
  HANDLE ProcessHeap; // rax
  BSTR *v37; // r14
  BSTR v38; // rax
  BSTR *v39; // r15
  int v40; // eax
  HANDLE v41; // rax
  HANDLE v42; // rax
  signed int v43; // eax
  const struct _EVENT_DESCRIPTOR *v44; // rdx
  CEventLogger *v45; // rcx
  unsigned int v46; // r9d
  int v47; // eax
  signed int v48; // eax
  const struct _EVENT_DESCRIPTOR *v49; // rdx
  CEventLogger *v50; // rcx
  CEventLogger *v51; // rcx
  unsigned int v52; // r8d
  int v53; // eax
  int v54; // eax
  int v55; // eax
  HANDLE Thread; // rax
  signed int LastError; // eax
  int v59; // eax
  _QWORD *v60; // r14
  CEventLogger *v61; // rcx
  unsigned __int16 *v62; // r8
  const struct _EVENT_DESCRIPTOR *v63; // rdx
  CEventLogger *v64; // rcx
  int v65; // eax
  int v66; // eax
  unsigned int lpThreadId; // [rsp+28h] [rbp-50h]
  int v68; // [rsp+30h] [rbp-48h] BYREF
  int v69; // [rsp+34h] [rbp-44h] BYREF
  int v70; // [rsp+38h] [rbp-40h] BYREF
  BSTR v71; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v72; // [rsp+48h] [rbp-30h] BYREF
  int v73; // [rsp+4Ch] [rbp-2Ch] BYREF
  BSTR v74; // [rsp+50h] [rbp-28h] BYREF
  BSTR v75; // [rsp+58h] [rbp-20h] BYREF
  BSTR v76; // [rsp+60h] [rbp-18h] BYREF
  BSTR bstrString[2]; // [rsp+68h] [rbp-10h] BYREF
  int v78; // [rsp+C8h] [rbp+50h] BYREF

  v78 = 0;
  v8 = 0;
  v69 = 0;
  v71 = 0;
  v70 = 0;
  v68 = 0;
  v73 = 0;
  v76 = 0;
  v75 = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v74, L"EndRendezvous");
  v78 = 1;
  CEventLogger::LogEvent(v10, v9, L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp", 0x193u, a2);
  v13 = a2 - 5;
  if ( !v13 )
  {
    CEventLogger::LogEvent(
      v12,
      &Enter_Conditional_Block,
      0x198u,
      L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp");
    v21 = (CEventLogger *)*((_QWORD *)this + 1);
    v72 = 0;
    if ( !v21 )
    {
      v22 = 418;
      goto LABEL_115;
    }
    v48 = (*(__int64 (__fastcall **)(CEventLogger *, unsigned int *))(*(_QWORD *)v21 + 72LL))(v21, &v72);
    Instance = v48;
    if ( v48 < 0 )
    {
      CEventLogger::LogError(
        v50,
        v49,
        L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
        0x1A8u,
        L"CIMRequestRAEvent::Invoke",
        v48);
      goto LABEL_117;
    }
    CEventLogger::LogEvent(v50, v49, L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp", 0x1ADu, v72);
    v51 = (CEventLogger *)(v72 - 4);
    if ( v72 == 4 )
    {
      CEventLogger::LogEvent(
        v51,
        &Enter_Conditional_Block,
        0x1C8u,
        L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp");
      v21 = (CEventLogger *)*((_QWORD *)this + 1);
      if ( !v21 )
      {
        v22 = 464;
        goto LABEL_115;
      }
      v53 = (*(__int64 (__fastcall **)(CEventLogger *, int *))(*(_QWORD *)v21 + 40LL))(v21, &v78);
      Instance = v53;
      if ( v53 < 0 )
      {
        lpThreadId = v53;
        v22 = 470;
        goto LABEL_116;
      }
      v54 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 1) + 48LL))(*((_QWORD *)this + 1), &v69);
      Instance = v54;
      if ( v54 < 0 )
      {
        lpThreadId = v54;
        v22 = 477;
        goto LABEL_116;
      }
      if ( v78 )
      {
        v55 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 1) + 96LL))(*((_QWORD *)this + 1), &v68);
        Instance = v55;
        if ( v55 < 0 )
        {
          lpThreadId = v55;
          v22 = 495;
          goto LABEL_116;
        }
        if ( !v68 )
        {
          Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)IMRequestObtainTicket, this, 0, 0);
          if ( !Thread )
          {
            LastError = GetLastError();
            Instance = LastError;
            if ( LastError > 0 )
              Instance = (unsigned __int16)LastError | 0x80070000;
            v46 = 522;
            goto LABEL_82;
          }
          CloseHandle(Thread);
        }
      }
      else if ( v69 )
      {
        v59 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 1) + 88LL))(*((_QWORD *)this + 1), &v70);
        Instance = v59;
        if ( v59 < 0 )
        {
          lpThreadId = v59;
          v22 = 538;
          goto LABEL_116;
        }
        if ( v70 )
        {
          v73 = 0;
          v60 = (_QWORD *)((char *)this + 192);
          Instance = CoCreateInstance(
                       &CLSID_RemoteAssistance,
                       0,
                       4u,
                       &GUID_59308e66_7cde_478a_8eba_4d73fdce3545,
                       (LPVOID *)this + 24);
          if ( Instance < 0 )
          {
            CEventLogger::LogEvent(v61, v20, v62);
            CEventLogger::LogError(
              v64,
              v63,
              L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
              0x232u,
              L"CIMRequestRAEvent::Invoke",
              Instance);
            goto LABEL_113;
          }
          v21 = (CEventLogger *)*((_QWORD *)this + 1);
          if ( !v21 )
          {
            v22 = 579;
            goto LABEL_115;
          }
          v65 = (*(__int64 (__fastcall **)(CEventLogger *, BSTR *))(*(_QWORD *)v21 + 32LL))(v21, &v75);
          Instance = v65;
          if ( v65 < 0 )
          {
            lpThreadId = v65;
            v22 = 570;
            goto LABEL_116;
          }
          v66 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(*(_QWORD *)*v60 + 144LL))(*v60, v75);
          Instance = v66;
          if ( v66 < 0 )
          {
            lpThreadId = v66;
            v22 = 585;
            goto LABEL_116;
          }
          SalemTicket = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v60 + 104LL))(*v60);
          Instance = SalemTicket;
          if ( SalemTicket < 0 )
          {
            v29 = 599;
            goto LABEL_112;
          }
          SalemTicket = (*(__int64 (__fastcall **)(_QWORD, int *, _QWORD))(*(_QWORD *)*v60 + 88LL))(*v60, &v73, 0);
          Instance = SalemTicket;
          if ( SalemTicket < 0 )
          {
            v29 = 610;
            goto LABEL_112;
          }
          if ( !v73 )
          {
            Instance = -2147418113;
            CEventLogger::LogError(
              v21,
              v28,
              L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
              0x26Fu,
              L"CIMRequestRAEvent::Invoke",
              0x8000FFFF);
            goto LABEL_113;
          }
          SalemTicket = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(*(_QWORD *)*v60 + 64LL))(*v60, &v76);
          Instance = SalemTicket;
          if ( SalemTicket < 0 )
          {
            v29 = 634;
            goto LABEL_112;
          }
          SalemTicket = CIMRequestRAEvent::SendExpertRevConnString(this, v76);
          Instance = SalemTicket;
          if ( SalemTicket < 0 )
          {
            v29 = 642;
            goto LABEL_112;
          }
        }
      }
      v52 = 650;
    }
    else
    {
      if ( v72 != 5 )
      {
LABEL_88:
        CEventLogger::LogEvent(
          v51,
          &Exit_Conditional_Block,
          0x2A5u,
          L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp");
        goto LABEL_89;
      }
      CEventLogger::LogEvent(
        v51,
        &Enter_Conditional_Block,
        0x28Fu,
        L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp");
      CIMRequestRAEvent::Unadvise(this);
      CIMRequestRAEvent::CleanupSessionState(this, 0);
      v52 = 664;
    }
    CEventLogger::LogEvent(v21, &Exit_Conditional_Block, v52, L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp");
    goto LABEL_88;
  }
  v14 = v13 - 1;
  if ( !v14 )
  {
    CIMRequestRAEvent::Unadvise(this);
    goto LABEL_89;
  }
  v15 = v14 - 1;
  if ( v15 )
  {
    if ( v15 == 1 )
    {
      CEventLogger::LogError(
        v12,
        v11,
        L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
        0x3B4u,
        L"CIMRequestRAEvent::Invoke",
        0);
      Instance = -2147467259;
LABEL_117:
      CIMRequestRAEvent::CleanupSessionState(this, 1);
      goto LABEL_90;
    }
    goto LABEL_89;
  }
  CEventLogger::LogEvent(v12, &Enter_Conditional_Block, 0x2AEu, L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp");
  v17 = (unsigned __int16 **)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, a6->rgvarg->bstrVal);
  Instance = ATL::CComBSTR::AppendBSTR(&v71, *v17);
  SysFreeString(bstrString[0]);
  if ( Instance < 0 )
  {
    CEventLogger::LogError(
      v19,
      v18,
      L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
      0x2B3u,
      L"CIMRequestRAEvent::Invoke",
      Instance);
    v8 = v71;
    goto LABEL_117;
  }
  v8 = v71;
  CIMRequestRAEvent::ProcessNotify(this, v71);
  v21 = (CEventLogger *)*((_QWORD *)this + 1);
  if ( !v21 )
  {
    v22 = 708;
LABEL_115:
    lpThreadId = -2147418113;
    Instance = -2147418113;
    goto LABEL_116;
  }
  v23 = (*(__int64 (__fastcall **)(CEventLogger *, int *))(*(_QWORD *)v21 + 40LL))(v21, &v78);
  Instance = v23;
  if ( v23 < 0 )
  {
    lpThreadId = v23;
    v22 = 713;
LABEL_116:
    CEventLogger::LogError(
      v21,
      v20,
      L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
      v22,
      L"CIMRequestRAEvent::Invoke",
      lpThreadId);
    goto LABEL_117;
  }
  v24 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 1) + 48LL))(*((_QWORD *)this + 1), &v69);
  Instance = v24;
  if ( v24 < 0 )
  {
    lpThreadId = v24;
    v22 = 718;
    goto LABEL_116;
  }
  if ( !v78 )
  {
    if ( !v69 )
      goto LABEL_89;
    v21 = (CEventLogger *)*((_QWORD *)this + 1);
    if ( !v21 )
    {
      v22 = 825;
      goto LABEL_115;
    }
    v31 = (*(__int64 (__fastcall **)(CEventLogger *, int *))(*(_QWORD *)v21 + 88LL))(v21, &v70);
    Instance = v31;
    if ( v31 < 0 )
    {
      lpThreadId = v31;
      v22 = 832;
      goto LABEL_116;
    }
    if ( v70 )
    {
      SalemTicket = CIMRequestRAEvent::ExtractSalemTicket(this, v8);
      Instance = SalemTicket;
      if ( SalemTicket < 0 )
      {
        v29 = 847;
        goto LABEL_112;
      }
      v32 = *((_QWORD *)this + 24);
      v33 = *((_QWORD *)this + 15);
      bstrString[0] = 0;
      Instance = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 72LL))(v32, v33);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)bstrString);
      if ( Instance >= 0 )
      {
        CIMRequestRAEvent::Notify(this, 1);
        CIMRequestRAEvent::CleanupSessionState(this, 1);
        goto LABEL_89;
      }
      CEventLogger::LogError(
        v35,
        v34,
        L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
        0x358u,
        L"CIMRequestRAEvent::Invoke",
        Instance);
LABEL_113:
      CIMRequestRAEvent::Notify(this, 17);
      goto LABEL_117;
    }
    ATL::CComBSTR::operator=((OLECHAR **)this + 23, (ATL::CComBSTR *)&v71);
    ProcessHeap = GetProcessHeap();
    v37 = (BSTR *)HeapAlloc(ProcessHeap, 8u, 0x10u);
    if ( !v37 )
    {
      Instance = -2147024882;
      lpThreadId = -2147024882;
      v22 = 882;
      goto LABEL_116;
    }
    v38 = ATL::CComBSTR::Copy((LPCSTR *)this + 23);
    *v37 = v38;
    if ( !v38 )
    {
      Instance = -2147024882;
      lpThreadId = -2147024882;
      v22 = 888;
      goto LABEL_116;
    }
    v21 = (CEventLogger *)*((_QWORD *)this + 1);
    if ( !v21 )
    {
      v22 = 895;
      goto LABEL_115;
    }
    v39 = v37 + 1;
    v40 = (*(__int64 (__fastcall **)(CEventLogger *, BSTR *))(*(_QWORD *)v21 + 32LL))(v21, v37 + 1);
    Instance = v40;
    if ( v40 < 0 )
    {
      lpThreadId = v40;
      v22 = 899;
      goto LABEL_116;
    }
    v41 = CreateThread(0, 0, PersistRequestRAObjectUntilConsumed, v37, 0, 0);
    if ( v41 )
    {
      CloseHandle(v41);
      v47 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(**((_QWORD **)this + 1) + 56LL))(*((_QWORD *)this + 1), v74);
      Instance = v47;
      if ( v47 < 0 )
      {
        lpThreadId = v47;
        v22 = 938;
        goto LABEL_116;
      }
      goto LABEL_89;
    }
    if ( *v37 )
    {
      SysFreeString(*v37);
      *v37 = 0;
    }
    if ( *v39 )
    {
      SysFreeString(*v39);
      *v39 = 0;
    }
    v42 = GetProcessHeap();
    HeapFree(v42, 0, v37);
    v43 = GetLastError();
    Instance = v43;
    if ( v43 > 0 )
      Instance = (unsigned __int16)v43 | 0x80070000;
    v46 = 926;
LABEL_82:
    CEventLogger::LogError(
      v45,
      v44,
      L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
      v46,
      L"CIMRequestRAEvent::Invoke",
      Instance);
    goto LABEL_83;
  }
  v25 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 1) + 96LL))(*((_QWORD *)this + 1), &v68);
  Instance = v25;
  if ( v25 < 0 )
  {
    lpThreadId = v25;
    v22 = 730;
    goto LABEL_116;
  }
  if ( v68 )
  {
    if ( *((_DWORD *)this + 50) )
    {
      v26 = ATL::CComBSTR::Copy((LPCSTR *)&v71);
      if ( v8 && !v26 )
        ATL::AtlThrowImpl(-2147024882);
      SysFreeString(v26);
    }
    else
    {
      *((_DWORD *)this + 50) = 1;
    }
    SalemTicket = CIMRequestRAEvent::ParseExpertRevConnString(this, v8);
    Instance = SalemTicket;
    if ( SalemTicket < 0 )
    {
      v29 = 755;
LABEL_112:
      CEventLogger::LogError(
        v21,
        v28,
        L"base\\diagnosis\\ra\\dcom\\src\\raimrequestevnt.cpp",
        v29,
        L"CIMRequestRAEvent::Invoke",
        SalemTicket);
      goto LABEL_113;
    }
    SalemTicket = CIMRequestRAEvent::SendEncryptedNoviceTicket(this);
    Instance = SalemTicket;
    if ( SalemTicket < 0 )
    {
      v29 = 768;
      goto LABEL_112;
    }
LABEL_89:
    Instance = 0;
    goto LABEL_90;
  }
  if ( !ATL::CComBSTR::operator==(&v71, &v74) )
    goto LABEL_89;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v71, L"Termination");
  v30 = *((_QWORD *)this + 1);
  if ( v30 )
    Instance = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR))(*(_QWORD *)v30 + 64LL))(v30, 0, v71);
  SysFreeString(v71);
LABEL_83:
  if ( Instance < 0 )
    goto LABEL_117;
LABEL_90:
  SysFreeString(v74);
  SysFreeString(v75);
  SysFreeString(v76);
  SysFreeString(0);
  SysFreeString(v8);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140011fc0  push    rbp
0x140011fc2  push    rbx
0x140011fc3  push    rsi
0x140011fc4  push    rdi
0x140011fc5  push    r12
0x140011fc7  push    r13
0x140011fc9  push    r14
0x140011fcb  push    r15
0x140011fcd  mov     rbp, rsp
0x140011fd0  sub     rsp, 78h
0x140011fd4  xor     r12d, r12d
0x140011fd7  mov     edi, edx
0x140011fd9  mov     rsi, rcx
0x140011fdc  mov     [rbp+arg_8], r12d
0x140011fe0  mov     ebx, r12d
0x140011fe3  mov     [rbp+var_44], r12d
0x140011fe7  lea     rdx, aEndrendezvous; "EndRendezvous"
0x140011fee  mov     [rbp+var_38], rbx
0x140011ff2  lea     rcx, [rbp+var_28]; this
0x140011ff6  mov     [rbp+var_40], r12d
0x140011ffa  mov     [rbp+var_48], r12d
0x140011ffe  mov     [rbp+var_2C], r12d
0x140012002  mov     [rbp+var_18], r12
0x140012006  mov     [rbp+var_20], r12
0x14001200a  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x14001200f  lea     r13, aBaseDiagnosisR_0; "base\\diagnosis\\ra\\dcom\\src\\raimreq"...
0x140012016  mov     [rsp+78h+dwCreationFlags], edi; unsigned int
0x14001201a  lea     r14d, [r12+1]
0x14001201f  mov     r8, r13; unsigned __int16 *
0x140012022  mov     r9d, 193h; unsigned int
0x140012028  mov     [rbp+arg_8], r14d
0x14001202c  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGII@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *,uint,uint)
0x140012031  sub     edi, 5
0x140012034  jz      loc_140012470
0x14001203a  sub     edi, r14d
0x14001203d  jz      loc_140012463
0x140012043  sub     edi, r14d
0x140012046  jz      short loc_14001207A
0x140012048  cmp     edi, r14d
0x14001204b  jnz     loc_14001265B
0x140012051  lea     rax, aCimrequestraev_5; "CIMRequestRAEvent::Invoke"
0x140012058  mov     dword ptr [rsp+78h+lpThreadId], r12d; unsigned int
0x14001205d  mov     r9d, 3B4h; unsigned int
0x140012063  mov     qword ptr [rsp+78h+dwCreationFlags], rax; unsigned __int16 *
0x140012068  mov     r8, r13; unsigned __int16 *
0x14001206b  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140012070  mov     edi, 80004005h
0x140012075  jmp     loc_140012861
0x14001207a  mov     r9, r13; unsigned __int16 *
0x14001207d  lea     rdx, Enter_Conditional_Block; struct _EVENT_DESCRIPTOR *
0x140012084  mov     r8d, 2AEh; unsigned int
0x14001208a  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@IPEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint,ushort *)
0x14001208f  mov     rax, [rbp+arg_28]
0x140012093  lea     rcx, [rbp+bstrString]; this
0x140012097  mov     rdx, [rax]
0x14001209a  mov     rdx, [rdx+8]; unsigned __int16 *
0x14001209e  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1400120a3  lea     rcx, [rbp+var_38]; this
0x1400120a7  mov     rdx, [rax]; unsigned __int16 *
0x1400120aa  call    ?AppendBSTR@CComBSTR@ATL@@QEAAJPEAG@Z; ATL::CComBSTR::AppendBSTR(ushort *)
0x1400120af  mov     rcx, [rbp+bstrString]; bstrString
0x1400120b3  mov     edi, eax
0x1400120b5  call    cs:__imp_SysFreeString
0x1400120bb  test    edi, edi
0x1400120bd  jns     short loc_1400120E6
0x1400120bf  lea     rax, aCimrequestraev_5; "CIMRequestRAEvent::Invoke"
0x1400120c6  mov     dword ptr [rsp+78h+lpThreadId], edi; unsigned int
0x1400120ca  mov     r9d, 2B3h; unsigned int
0x1400120d0  mov     qword ptr [rsp+78h+dwCreationFlags], rax; unsigned __int16 *
0x1400120d5  mov     r8, r13; unsigned __int16 *
0x1400120d8  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400120dd  mov     rbx, [rbp+var_38]
0x1400120e1  jmp     loc_140012861
0x1400120e6  mov     rbx, [rbp+var_38]
0x1400120ea  mov     rcx, rsi; this
0x1400120ed  mov     rdx, rbx; unsigned __int16 *
0x1400120f0  call    ?ProcessNotify@CIMRequestRAEvent@@QEAAJPEAG@Z; CIMRequestRAEvent::ProcessNotify(ushort *)
0x1400120f5  mov     rcx, [rsi+8]
0x1400120f9  test    rcx, rcx
0x1400120fc  jnz     short loc_140012109
0x1400120fe  mov     r9d, 2C4h
0x140012104  jmp     loc_140012840
0x140012109  mov     rax, [rcx]
0x14001210c  lea     rdx, [rbp+arg_8]
0x140012110  mov     rax, [rax+28h]
0x140012114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012119  mov     edi, eax
0x14001211b  test    eax, eax
0x14001211d  jns     short loc_14001212E
0x14001211f  mov     dword ptr [rsp+78h+lpThreadId], eax
0x140012123  mov     r9d, 2C9h
0x140012129  jmp     loc_14001284D
0x14001212e  mov     rcx, [rsi+8]
0x140012132  lea     rdx, [rbp+var_44]
0x140012136  mov     rax, [rcx]
0x140012139  mov     rax, [rax+30h]
0x14001213d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012142  mov     edi, eax
0x140012144  test    eax, eax
0x140012146  jns     short loc_140012157
0x140012148  mov     dword ptr [rsp+78h+lpThreadId], eax
0x14001214c  mov     r9d, 2CEh
0x140012152  jmp     loc_14001284D
0x140012157  cmp     [rbp+arg_8], r12d
0x14001215b  jz      loc_14001224C
0x140012161  mov     rcx, [rsi+8]
0x140012165  lea     rdx, [rbp+var_48]
0x140012169  mov     rax, [rcx]
0x14001216c  mov     rax, [rax+60h]
0x140012170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012175  mov     edi, eax
0x140012177  test    eax, eax
0x140012179  jns     short loc_14001218A
0x14001217b  mov     dword ptr [rsp+78h+lpThreadId], eax
0x14001217f  mov     r9d, 2DAh
0x140012185  jmp     loc_14001284D
0x14001218a  cmp     [rbp+var_48], r12d
0x14001218e  jz      short loc_1400121FB
0x140012190  cmp     [rsi+0C8h], r12d
0x140012197  jnz     short loc_1400121A2
0x140012199  mov     [rsi+0C8h], r14d
0x1400121a0  jmp     short loc_1400121C2
0x1400121a2  lea     rcx, [rbp+var_38]; this
0x1400121a6  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x1400121ab  test    rbx, rbx
0x1400121ae  jz      short loc_1400121B9
0x1400121b0  test    rax, rax
0x1400121b3  jz      loc_140012873
0x1400121b9  mov     rcx, rax; bstrString
0x1400121bc  call    cs:__imp_SysFreeString
0x1400121c2  mov     rdx, rbx; unsigned __int16 *
0x1400121c5  mov     rcx, rsi; this
0x1400121c8  call    ?ParseExpertRevConnString@CIMRequestRAEvent@@QEAAJPEAG@Z; CIMRequestRAEvent::ParseExpertRevConnString(ushort *)
0x1400121cd  mov     edi, eax
0x1400121cf  test    eax, eax
0x1400121d1  jns     short loc_1400121DE
0x1400121d3  mov     r9d, 2F3h
0x1400121d9  jmp     loc_140012813
0x1400121de  mov     rcx, rsi; this
0x1400121e1  call    ?SendEncryptedNoviceTicket@CIMRequestRAEvent@@QEAAJXZ; CIMRequestRAEvent::SendEncryptedNoviceTicket(void)
0x1400121e6  mov     edi, eax
0x1400121e8  test    eax, eax
0x1400121ea  jns     loc_14001265B
0x1400121f0  mov     r9d, 300h
0x1400121f6  jmp     loc_140012813
0x1400121fb  lea     rdx, [rbp+var_28]
0x1400121ff  lea     rcx, [rbp+var_38]
0x140012203  call    ??8CComBSTR@ATL@@QEBA_NAEBV01@@Z; ATL::CComBSTR::operator==(ATL::CComBSTR const &)
0x140012208  test    al, al
0x14001220a  jz      loc_14001265B
0x140012210  lea     rdx, aTermination; "Termination"
0x140012217  lea     rcx, [rbp+var_38]; this
0x14001221b  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x140012220  mov     rcx, [rsi+8]
0x140012224  test    rcx, rcx
0x140012227  jz      short loc_14001223D
0x140012229  mov     rax, [rcx]
0x14001222c  xor     edx, edx
0x14001222e  mov     r8, [rbp+var_38]
0x140012232  mov     rax, [rax+40h]
0x140012236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001223b  mov     edi, eax
0x14001223d  mov     rcx, [rbp+var_38]; bstrString
0x140012241  call    cs:__imp_SysFreeString
0x140012247  jmp     loc_140012627
0x14001224c  cmp     [rbp+var_44], r12d
0x140012250  jz      loc_14001265B
0x140012256  mov     rcx, [rsi+8]
0x14001225a  test    rcx, rcx
0x14001225d  jnz     short loc_14001226A
0x14001225f  mov     r9d, 339h
0x140012265  jmp     loc_140012840
0x14001226a  mov     rax, [rcx]
0x14001226d  lea     rdx, [rbp+var_40]
0x140012271  mov     rax, [rax+58h]
0x140012275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001227a  mov     edi, eax
0x14001227c  test    eax, eax
0x14001227e  jns     short loc_14001228F
0x140012280  mov     dword ptr [rsp+78h+lpThreadId], eax
0x140012284  mov     r9d, 340h
0x14001228a  jmp     loc_14001284D
0x14001228f  cmp     [rbp+var_40], r12d
0x140012293  jz      short loc_140012305
0x140012295  mov     rdx, rbx; unsigned __int16 *
0x140012298  mov     rcx, rsi; this
0x14001229b  call    ?ExtractSalemTicket@CIMRequestRAEvent@@QEAAJPEAG@Z; CIMRequestRAEvent::ExtractSalemTicket(ushort *)
0x1400122a0  mov     edi, eax
0x1400122a2  test    eax, eax
0x1400122a4  jns     short loc_1400122B1
0x1400122a6  mov     r9d, 34Fh
0x1400122ac  jmp     loc_140012813
0x1400122b1  mov     rcx, [rsi+0C0h]
0x1400122b8  mov     rdx, [rsi+78h]
0x1400122bc  mov     [rbp+bstrString], r12
0x1400122c0  mov     rax, [rcx]
0x1400122c3  mov     rax, [rax+48h]
0x1400122c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400122cc  lea     rcx, [rbp+bstrString]
0x1400122d0  mov     edi, eax
0x1400122d2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400122d7  test    edi, edi
0x1400122d9  jns     short loc_1400122EA
0x1400122db  mov     dword ptr [rsp+78h+lpThreadId], edi
0x1400122df  mov     r9d, 358h
0x1400122e5  jmp     loc_140012817
0x1400122ea  mov     edx, r14d; int
0x1400122ed  mov     rcx, rsi; this
0x1400122f0  call    ?Notify@CIMRequestRAEvent@@QEAAJH@Z; CIMRequestRAEvent::Notify(int)
0x1400122f5  mov     edx, r14d; int
0x1400122f8  mov     rcx, rsi; this
0x1400122fb  call    ?CleanupSessionState@CIMRequestRAEvent@@QEAAXH@Z; CIMRequestRAEvent::CleanupSessionState(int)
0x140012300  jmp     loc_14001265B
0x140012305  lea     rdi, [rsi+0B8h]
0x14001230c  mov     rcx, rdi
0x14001230f  lea     rdx, [rbp+var_38]
0x140012313  call    ??4CComBSTR@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CComBSTR::operator=(ATL::CComBSTR const &)
0x140012318  call    cs:__imp_GetProcessHeap
0x14001231e  mov     edx, 8; dwFlags
0x140012323  mov     rcx, rax; hHeap
0x140012326  lea     r8d, [rdx+8]; dwBytes
0x14001232a  call    cs:__imp_HeapAlloc
0x140012330  mov     r14, rax
0x140012333  test    rax, rax
0x140012336  jnz     short loc_140012350
0x140012338  mov     edi, 8007000Eh
0x14001233d  mov     dword ptr [rsp+78h+lpThreadId], 8007000Eh
0x140012345  mov     r9d, 372h
0x14001234b  jmp     loc_14001284D
0x140012350  mov     rcx, rdi; this
0x140012353  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x140012358  mov     [r14], rax
0x14001235b  test    rax, rax
0x14001235e  jnz     short loc_140012378
0x140012360  mov     edi, 8007000Eh
0x140012365  mov     dword ptr [rsp+78h+lpThreadId], 8007000Eh
0x14001236d  mov     r9d, 378h
0x140012373  jmp     loc_14001284D
0x140012378  mov     rcx, [rsi+8]
0x14001237c  test    rcx, rcx
0x14001237f  jnz     short loc_14001238C
0x140012381  mov     r9d, 37Fh
0x140012387  jmp     loc_140012840
0x14001238c  mov     rax, [rcx]
0x14001238f  lea     r15, [r14+8]
0x140012393  mov     rdx, r15
0x140012396  mov     rax, [rax+20h]
0x14001239a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001239f  mov     edi, eax
0x1400123a1  test    eax, eax
0x1400123a3  jns     short loc_1400123B4
0x1400123a5  mov     dword ptr [rsp+78h+lpThreadId], eax
0x1400123a9  mov     r9d, 383h
0x1400123af  jmp     loc_14001284D
0x1400123b4  mov     [rsp+78h+lpThreadId], r12; lpThreadId
0x1400123b9  lea     r8, ?PersistRequestRAObjectUntilConsumed@@YAKPEAX@Z; lpStartAddress
0x1400123c0  mov     r9, r14; lpParameter
0x1400123c3  mov     [rsp+78h+dwCreationFlags], r12d; dwCreationFlags
0x1400123c8  xor     edx, edx; dwStackSize
0x1400123ca  xor     ecx, ecx; lpThreadAttributes
0x1400123cc  call    cs:__imp_CreateThread
0x1400123d2  test    rax, rax
0x1400123d5  jnz     short loc_14001242D
0x1400123d7  mov     rcx, [r14]; bstrString
0x1400123da  test    rcx, rcx
0x1400123dd  jz      short loc_1400123E8
0x1400123df  call    cs:__imp_SysFreeString
0x1400123e5  mov     [r14], r12
0x1400123e8  mov     rcx, [r15]; bstrString
0x1400123eb  test    rcx, rcx
0x1400123ee  jz      short loc_1400123F9
0x1400123f0  call    cs:__imp_SysFreeString
0x1400123f6  mov     [r15], r12
0x1400123f9  call    cs:__imp_GetProcessHeap
0x1400123ff  mov     r8, r14; lpMem
0x140012402  xor     edx, edx; dwFlags
0x140012404  mov     rcx, rax; hHeap
0x140012407  call    cs:__imp_HeapFree
0x14001240d  call    cs:__imp_GetLastError
0x140012413  mov     edi, eax
0x140012415  test    eax, eax
0x140012417  jle     short loc_140012422
0x140012419  movzx   edi, ax
0x14001241c  or      edi, 80070000h
0x140012422  mov     r9d, 39Eh
0x140012428  jmp     loc_14001260F
0x14001242d  mov     rcx, rax; hObject
0x140012430  call    cs:__imp_CloseHandle
0x140012436  mov     rcx, [rsi+8]
0x14001243a  mov     rdx, [rbp+var_28]
0x14001243e  mov     rax, [rcx]
0x140012441  mov     rax, [rax+38h]
0x140012445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001244a  mov     edi, eax
0x14001244c  test    eax, eax
0x14001244e  jns     loc_14001265B
0x140012454  mov     dword ptr [rsp+78h+lpThreadId], eax
0x140012458  mov     r9d, 3AAh
0x14001245e  jmp     loc_14001284D
0x140012463  mov     rcx, rsi; this
  ... truncated ...
```
