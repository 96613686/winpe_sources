# Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo(Windows::Compat::Appraiser::WuSessionInfo *)

- ea: `0x1801e22ac`
- end: `0x1801e2c03`
- name: `?InitializeWuSessionInfo@WuDriverCoverageDataSource@Appraiser@Compat@Windows@@CAJPEAUWuSessionInfo@234@@Z`
- size: `2391`
- prototype: `__int64 __fastcall(struct Windows::Compat::Appraiser::WuSessionInfo *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801e3880`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180008ac0`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800a5d88`
- `0x1801e0f54`
- `0x1801e22ac`
- `0x1801e45ec`
- `0x18021f010`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x1801e2a8b`
- `RPCRT4!UuidToStringW` at `0x1801e2a8b`
- `RPCRT4!RpcStringFreeW` at `0x1801e2bc3`
- `RPCRT4!RpcStringFreeW` at `0x1801e2bc3`
- `KERNEL32!GetSystemTime` at `0x1801e243f`
- `KERNEL32!GetSystemTime` at `0x1801e2676`
- `KERNEL32!GetSystemTime` at `0x1801e243f`
- `KERNEL32!GetSystemTime` at `0x1801e2676`
- `OLE32!CoCreateInstance` at `0x1801e25ab`
- `OLE32!CoCreateInstance` at `0x1801e25ab`
- `OLEAUT32!__imp_SysAllocString` at `0x1801e271d`
- `OLEAUT32!__imp_SysAllocString` at `0x1801e271d`
- `OLEAUT32!__imp_SysFreeString` at `0x1801e2b78`
- `OLEAUT32!__imp_SysFreeString` at `0x1801e2b78`
- `OLEAUT32!__imp_VariantInit` at `0x1801e28ee`
- `OLEAUT32!__imp_VariantInit` at `0x1801e28ee`

## string_xrefs

- `0x1801e2316`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e2b9c`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e230c`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo`
- `0x1801e2b90`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo`
- `0x1801e27bf`: `Error creating IUpdateSearcher: [0x%x].`
- `0x1801e27d9`: `Error creating IUpdateSearcher: [0x%x].`
- `0x1801e2898`: `Error QI for IUpdateSearcherInternalConfiguration: [0x%x].`
- `0x1801e28b5`: `Error QI for IUpdateSearcherInternalConfiguration: [0x%x].`
- `0x1801e2828`: `Error QI for IUpdateSearcherInternal: [0x%x].`
- `0x1801e2845`: `Error QI for IUpdateSearcherInternal: [0x%x].`
- `0x1801e24ad`: `Error retrieving current service ID: [0x%x].`
- `0x1801e24f8`: `Error retrieving current service ID: [0x%x].`
- `0x1801e26e3`: `Error creating IUpdateSession: [0x%x].`
- `0x1801e26fb`: `Error creating IUpdateSession: [0x%x].`
- `0x1801e2adf`: `Error putting service id: [0x%x].`
- `0x1801e2afc`: `Error putting service id: [0x%x].`
- `0x1801e299f`: `Error QI for IUpdateSearcherIgnoreInstalledDrivers: [0x%x].`
- `0x1801e29bc`: `Error QI for IUpdateSearcherIgnoreInstalledDrivers: [0x%x].`
- `0x1801e2933`: `Error putting search interactive configuration: [0x%x].`
- `0x1801e2950`: `Error putting search interactive configuration: [0x%x].`
- `0x1801e29f7`: `Error putting ignore installed drivers property: [0x%x].`
- `0x1801e2a14`: `Error putting ignore installed drivers property: [0x%x].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo(UUID *a1)
{
  char *v2; // rax
  HRESULT CurrentWuServiceId; // ebx
  volatile signed __int64 *v4; // r9
  void **v5; // rdx
  __int64 v6; // r13
  char v7; // r12
  __int64 v8; // r8
  __int64 v9; // r9
  bool v10; // al
  const char *v11; // r9
  __int64 v12; // rcx
  int v13; // ebx
  int v14; // eax
  char v15; // dl
  unsigned __int8 *Data4; // r13
  volatile signed __int64 *v17; // r9
  void **v18; // rdx
  __int64 v19; // r13
  __int64 v20; // r8
  __int64 v21; // r9
  const char *v22; // r9
  char v23; // dl
  __int64 v24; // rcx
  UUID *v25; // r13
  UUID *v26; // r12
  __int64 v27; // rbx
  __int64 (__fastcall *v28)(__int64, __int64, struct _SYSTEMTIME *); // rax
  unsigned __int8 *v29; // r12
  __int64 v30; // rcx
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  const char *v33; // [rsp+28h] [rbp-D8h]
  char *v34; // [rsp+30h] [rbp-D0h]
  bool v35; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+64h] [rbp-9Ch] BYREF
  int v37; // [rsp+68h] [rbp-98h] BYREF
  RPC_WSTR StringUuid; // [rsp+70h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  const char *p_pvarg; // [rsp+80h] [rbp-80h] BYREF
  const char *v41; // [rsp+88h] [rbp-78h] BYREF
  const char *v42; // [rsp+90h] [rbp-70h] BYREF
  const char *v43; // [rsp+98h] [rbp-68h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  IRecordInfo *pRecInfo; // [rsp+B0h] [rbp-50h]
  VARIANTARG pvarg; // [rsp+C0h] [rbp-40h] BYREF
  char v47[144]; // [rsp+E0h] [rbp-20h] BYREF
  char v48[144]; // [rsp+170h] [rbp+70h] BYREF

  StringUuid = 0;
  v35 = 0;
  if ( !a1 )
  {
    v13 = -2147467261;
    LODWORD(v34) = -2147467261;
    v33 = "Error creating internal upgrade session: [0x%x].";
    v15 = 9;
    goto LABEL_95;
  }
  v2 = (char *)operator new(0x48u);
  *(_QWORD *)v2 = &WU_UpgradeI::CSession::`vftable';
  v2[8] = 0;
  *((_QWORD *)v2 + 2) = 0;
  *(_OWORD *)(v2 + 24) = 0;
  *(_OWORD *)(v2 + 40) = 0;
  *((_QWORD *)v2 + 7) = 0;
  *((_DWORD *)v2 + 16) = 1;
  *(_QWORD *)&a1->Data1 = v2;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x309u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
      "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
      "Error creating internal upgrade session: [0x%x].",
      0);
  CurrentWuServiceId = Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId(a1 + 3, &v35);
  if ( CurrentWuServiceId < 0 )
  {
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v47);
    v4 = (volatile signed __int64 *)v47;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v4 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v4,
      _InterlockedExchangeAdd64(v4 + 17, 0),
      v48);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v5);
    v6 = qword_1802C9628;
    v7 = 16;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v36 = CurrentWuServiceId;
      p_pvarg = v48;
      v41 = "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo";
      v43 = (const char *)&szValueBuf;
      v42 = "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp";
      v37 = 784;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      bstrString = (BSTR)&pvarg;
      *(struct _SYSTEMTIME *)&pvarg.vt = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v6,
        (__int64)byte_1802A5A81,
        v8,
        v9,
        (__int64 *)&bstrString,
        (const size_t **)&v43,
        (__int64)&v37,
        &v42,
        &v41,
        (__int64)&v36,
        &p_pvarg);
    }
    v10 = Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors();
    v11 = "Error retrieving current service ID: [0x%x].";
LABEL_14:
    LODWORD(v34) = CurrentWuServiceId;
    if ( v10 )
    {
      LODWORD(ppv) = CurrentWuServiceId;
      v12 = 1;
    }
    else
    {
      ppv = 0;
      v12 = 0;
    }
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)v12,
      v7,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
      "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
      (const char *)ppv,
      (int)v11,
      v34);
    v13 = -2138537983;
    goto LABEL_96;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x310u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
      "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
      "Error retrieving current service ID: [0x%x].",
      CurrentWuServiceId);
  v14 = (*(__int64 (__fastcall **)(_QWORD, UUID *, const OLECHAR *, UUID *))(**(_QWORD **)&a1->Data1 + 8LL))(
          *(_QWORD *)&a1->Data1,
          a1 + 3,
          L"Appraiser Driver Scan",
          a1 + 4);
  v13 = v14;
  if ( v14 != -2147467262 )
  {
    if ( v14 < 0 )
    {
      LODWORD(v34) = v14;
      v33 = "Error initiating internal session: [0x%x].";
      v15 = 37;
LABEL_95:
      LODWORD(ppv) = v13;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v15,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
        "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
        (const char *)ppv,
        (int)v33,
        v34);
      goto LABEL_96;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x325u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
        "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
        "Error initiating internal session: [0x%x].",
        v14);
    Data4 = a1->Data4;
    LOBYTE(a1[5].Data1) = 1;
    CurrentWuServiceId = CoCreateInstance(
                           &GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe,
                           0,
                           1u,
                           &GUID_816858a4_260d_4260_933a_2585f1abc76b,
                           (LPVOID *)a1->Data4);
    if ( CurrentWuServiceId < 0 )
    {
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v47);
      v17 = (volatile signed __int64 *)v47;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v17 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v17,
        _InterlockedExchangeAdd64(v17 + 17, 0),
        v48);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v18);
      v19 = qword_1802C9628;
      v7 = 47;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v37 = CurrentWuServiceId;
        bstrString = (BSTR)v48;
        v43 = "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo";
        v41 = (const char *)&szValueBuf;
        v42 = "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp";
        v36 = 815;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        p_pvarg = (const char *)&pvarg;
        *(struct _SYSTEMTIME *)&pvarg.vt = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v19,
          (__int64)byte_1802A5B33,
          v20,
          v21,
          (__int64 *)&p_pvarg,
          (const size_t **)&v41,
          (__int64)&v36,
          &v42,
          &v43,
          (__int64)&v37,
          (const char **)&bstrString);
      }
      v10 = Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors();
      v11 = "Error creating IUpdateSession: [0x%x].";
      goto LABEL_14;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x32Fu,
        "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
        "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
        "Error creating IUpdateSession: [0x%x].",
        CurrentWuServiceId);
    bstrString = SysAllocString(L"Appraiser Driver Scan");
    if ( !bstrString )
    {
      v13 = -2147024882;
      goto LABEL_96;
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(**(_QWORD **)Data4 + 64LL))(*(_QWORD *)Data4, bstrString);
    if ( v13 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x335u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
          "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
          "Error setting ClientApplicationID: [0x%x].",
          v13);
      v24 = *(_QWORD *)Data4;
      v25 = a1 + 1;
      v13 = (*(__int64 (__fastcall **)(__int64, UUID *))(*(_QWORD *)v24 + 96LL))(v24, a1 + 1);
      if ( v13 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x338u,
            "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
            "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
            "Error creating IUpdateSearcher: [0x%x].",
            v13);
        v26 = a1 + 2;
        v13 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))&v25->Data1)(
                *(_QWORD *)&v25->Data1,
                &GUID_f258056c_186d_4fac_929b_c86ebf8f0ad8,
                (char *)&a1[2]);
        if ( v13 == -2147467262 )
        {
          *(_QWORD *)&v26->Data1 = 0;
        }
        else
        {
          if ( v13 < 0 )
          {
            v22 = "Error QI for IUpdateSearcherInternal: [0x%x].";
            v23 = 69;
            goto LABEL_41;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x345u,
              "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
              "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
              "Error QI for IUpdateSearcherInternal: [0x%x].",
              v13);
        }
        if ( *(_QWORD *)&v26->Data1 )
        {
          v13 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))&v25->Data1)(
                  *(_QWORD *)&v25->Data1,
                  &GUID_5455bce5_c1d7_4ff2_a815_8a35697f494b,
                  (char *)a1[2].Data4);
          if ( v13 == -2147467262 )
          {
            *(_QWORD *)a1[2].Data4 = 0;
          }
          else
          {
            if ( v13 < 0 )
            {
              v22 = "Error QI for IUpdateSearcherInternalConfiguration: [0x%x].";
              v23 = 85;
              goto LABEL_41;
            }
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x355u,
                "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
                "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
                "Error QI for IUpdateSearcherInternalConfiguration: [0x%x].",
                v13);
          }
        }
        v27 = *(_QWORD *)a1[2].Data4;
        if ( v27 )
        {
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          pRecInfo = pvarg.pRecInfo;
          pvarg.vt = 11;
          pvarg.iVal = 0;
          v28 = *(__int64 (__fastcall **)(__int64, __int64, struct _SYSTEMTIME *))(*(_QWORD *)v27 + 32LL);
          SystemTime = *(struct _SYSTEMTIME *)&pvarg.vt;
          v13 = v28(v27, 262145, &SystemTime);
          if ( v13 < 0 )
          {
            v22 = "Error putting search interactive configuration: [0x%x].";
            v23 = 92;
            goto LABEL_41;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x35Cu,
              "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
              "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
              "Error putting search interactive configuration: [0x%x].",
              v13);
        }
        v29 = a1[1].Data4;
        v13 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, char *))&v25->Data1)(
                *(_QWORD *)&v25->Data1,
                &GUID_d118bfa1_4217_4647_beef_a4baef1dbc89,
                (char *)a1[1].Data4);
        if ( v13 == -2147467262 )
        {
          *(_QWORD *)v29 = 0;
        }
        else
        {
          if ( v13 < 0 )
          {
            v22 = "Error QI for IUpdateSearcherIgnoreInstalledDrivers: [0x%x].";
            v23 = 110;
            goto LABEL_41;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x36Eu,
              "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
              "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
              "Error QI for IUpdateSearcherIgnoreInstalledDrivers: [0x%x].",
              v13);
        }
        if ( *(_QWORD *)v29 )
        {
          (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v29 + 32LL))(*(_QWORD *)v29, 0xFFFFFFFFLL);
          if ( v13 < 0 )
          {
            v22 = "Error putting ignore installed drivers property: [0x%x].";
            v23 = 116;
            goto LABEL_41;
          }
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x374u,
              "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
              "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
              "Error putting ignore installed drivers property: [0x%x].",
              v13);
        }
        v13 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)&v25->Data1 + 112LL))(*(_QWORD *)&v25->Data1, 3);
        if ( v13 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x37Du,
              "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
              "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
              "Error putting server selection: [0x%x].",
              v13);
          if ( UuidToStringW(a1 + 4, &StringUuid) )
          {
            v13 = -2147024883;
            LODWORD(ppv) = -2147024883;
            Windows::Compat::Appraiser::WriteLog(
              (Windows::Compat::Appraiser *)1,
              133,
              (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
              "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
              (const char *)ppv,
              (int)"Error converting GUID to string.",
              v34);
            goto LABEL_93;
          }
          v13 = (*(__int64 (__fastcall **)(_QWORD, RPC_WSTR))(**(_QWORD **)&v25->Data1 + 192LL))(
                  *(_QWORD *)&v25->Data1,
                  StringUuid);
          if ( v13 >= 0 )
          {
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x389u,
                "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
                "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
                "Error putting service id: [0x%x].",
                v13);
            v30 = *(_QWORD *)&a1[2].Data1;
            if ( v30 )
            {
              v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v30 + 32LL))(v30, 0xFFFFFFFFLL);
              if ( v13 < 0 )
              {
                v22 = "Error putting include driver sets (true): [0x%x].";
                v23 = -110;
                goto LABEL_41;
              }
              if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                  0x392u,
                  "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
                  "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
                  "Error putting include driver sets (true): [0x%x].",
                  v13);
            }
            BYTE1(a1[5].Data1) = 1;
            v13 = 0;
            goto LABEL_93;
          }
          v22 = "Error putting service id: [0x%x].";
          v23 = -119;
        }
        else
        {
          v22 = "Error putting server selection: [0x%x].";
          v23 = 125;
        }
      }
      else
      {
        v22 = "Error creating IUpdateSearcher: [0x%x].";
        v23 = 56;
      }
    }
    else
    {
      v22 = "Error setting ClientApplicationID: [0x%x].";
      v23 = 53;
    }
LABEL_41:
    LODWORD(v34) = v13;
    LODWORD(ppv) = v13;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v23,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
      "Windows::Compat::Appraiser::WuDriverCoverageDataSource::InitializeWuSessionInfo",
      (const char *)ppv,
      (int)v22,
      v34);
LABEL_93:
    SysFreeString(bstrString);
  }
LABEL_96:
  if ( StringUuid )
  {
    RpcStringFreeW(&StringUuid);
    StringUuid = 0;
  }
  if ( v13 < 0 )
    Windows::Compat::Appraiser::WuDriverCoverageDataSource::UnInitializeWuSessionInfo((struct Windows::Compat::Appraiser::WuSessionInfo *)a1);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1801e22ac  push    rbp
0x1801e22ae  push    rbx
0x1801e22af  push    rsi
0x1801e22b0  push    rdi
0x1801e22b1  push    r12
0x1801e22b3  push    r13
0x1801e22b5  push    r14
0x1801e22b7  push    r15
0x1801e22b9  lea     rbp, [rsp-118h]
0x1801e22c1  sub     rsp, 218h
0x1801e22c8  mov     rax, cs:__security_cookie
0x1801e22cf  xor     rax, rsp
0x1801e22d2  mov     [rbp+150h+var_50], rax
0x1801e22d9  mov     [rsp+250h+StringUuid], 0
0x1801e22e2  mov     r15, rcx
0x1801e22e5  mov     [rsp+250h+var_1F0], 0
0x1801e22ea  test    rcx, rcx
0x1801e22ed  jz      loc_1801E2B80
0x1801e22f3  mov     ecx, 48h ; 'H'; Size
0x1801e22f8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801e22fd  mov     edi, 1
0x1801e2302  lea     rcx, ??_7CSession@WU_UpgradeI@@6B@; const WU_UpgradeI::CSession::`vftable'
0x1801e2309  xorps   xmm0, xmm0
0x1801e230c  lea     rsi, aWindowsCompatA_428; "Windows::Compat::Appraiser::WuDriverCov"...
0x1801e2313  xorps   xmm1, xmm1
0x1801e2316  lea     r14, aOnecoreBaseApp_99; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801e231d  mov     [rax], rcx
0x1801e2320  mov     byte ptr [rax+8], 0
0x1801e2324  mov     qword ptr [rax+10h], 0
0x1801e232c  movups  xmmword ptr [rax+18h], xmm0
0x1801e2330  movups  xmmword ptr [rax+28h], xmm1
0x1801e2334  mov     qword ptr [rax+38h], 0
0x1801e233c  mov     [rax+40h], edi
0x1801e233f  mov     [r15], rax
0x1801e2342  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801e2348  and     eax, edi
0x1801e234a  test    al, al
0x1801e234c  jz      short loc_1801E236D
0x1801e234e  lea     r9, aErrorCreatingI; "Error creating internal upgrade session"...
0x1801e2355  mov     dword ptr [rsp+250h+ppv], 0
0x1801e235d  mov     r8, rsi; char *
0x1801e2360  mov     rdx, r14; char *
0x1801e2363  mov     ecx, 309h; unsigned int
0x1801e2368  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801e236d  lea     rdx, [rsp+250h+var_1F0]; bool *
0x1801e2372  lea     rcx, [r15+30h]; Uuid
0x1801e2376  call    ?GetCurrentWuServiceId@WuDriverCoverageDataSource@Appraiser@Compat@Windows@@CAJPEAU_GUID@@PEA_N@Z; Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId(_GUID *,bool *)
0x1801e237b  mov     ebx, eax
0x1801e237d  test    eax, eax
0x1801e237f  jns     loc_1801E24EC
0x1801e2385  lea     rcx, [rbp+150h+var_170]; this
0x1801e2389  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1801e238e  mov     rcx, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1801e2395  lea     r9, [rbp+150h+var_170]
0x1801e2399  test    rcx, rcx
0x1801e239c  cmovnz  r9, rcx
0x1801e23a0  xor     edx, edx
0x1801e23a2  lock xadd [r9+88h], rdx; unsigned __int64
0x1801e23ab  lea     r8, [rbp+150h+var_E0]; char *
0x1801e23af  mov     rcx, r9; this
0x1801e23b2  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1801e23b7  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1801e23be  jz      short loc_1801E23CC
0x1801e23c0  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1801e23c7  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1801e23cc  mov     r13, cs:qword_1802C9628
0x1801e23d3  mov     r12d, 310h
0x1801e23d9  mov     eax, [r13+0]
0x1801e23dd  cmp     eax, 5
0x1801e23e0  jbe     loc_1801E24A8
0x1801e23e6  mov     rdx, [r13+18h]
0x1801e23ea  mov     rcx, 200000000000h
0x1801e23f4  mov     rax, [r13+10h]
0x1801e23f8  test    rcx, rax
0x1801e23fb  jz      loc_1801E24A8
0x1801e2401  mov     rax, rdx
0x1801e2404  and     rax, rcx
0x1801e2407  cmp     rax, rdx
0x1801e240a  jnz     loc_1801E24A8
0x1801e2410  lea     rax, [rbp+150h+var_E0]
0x1801e2414  mov     [rsp+250h+var_1EC], ebx
0x1801e2418  mov     [rbp+150h+var_1D0], rax
0x1801e241c  lea     rcx, [rbp+150h+SystemTime]; lpSystemTime
0x1801e2420  lea     rax, szValueBuf
0x1801e2427  mov     [rbp+150h+var_1C8], rsi
0x1801e242b  xorps   xmm0, xmm0
0x1801e242e  mov     [rbp+150h+var_1B8], rax
0x1801e2432  mov     [rbp+150h+var_1C0], r14
0x1801e2436  mov     [rsp+250h+var_1E8], r12d
0x1801e243b  movups  xmmword ptr [rbp+150h+SystemTime.wYear], xmm0
0x1801e243f  call    cs:__imp_GetSystemTime
0x1801e2445  movaps  xmm0, xmmword ptr [rbp+150h+SystemTime.wYear]
0x1801e2449  lea     rax, [rbp+150h+pvarg]
0x1801e244d  mov     [rsp+250h+bstrString], rax
0x1801e2452  lea     rdx, byte_1802A5A81
0x1801e2459  lea     rax, [rbp+150h+var_1D0]
0x1801e245d  movdqa  xmmword ptr [rbp+150h+pvarg], xmm0
0x1801e2462  mov     [rsp+250h+var_200], rax
0x1801e2467  mov     rcx, r13
0x1801e246a  lea     rax, [rsp+250h+var_1EC]
0x1801e246f  mov     [rsp+250h+var_208], rax
0x1801e2474  lea     rax, [rbp+150h+var_1C8]
0x1801e2478  mov     [rsp+250h+var_210], rax
0x1801e247d  lea     rax, [rbp+150h+var_1C0]
0x1801e2481  mov     [rsp+250h+var_218], rax
0x1801e2486  lea     rax, [rsp+250h+var_1E8]
0x1801e248b  mov     [rsp+250h+var_220], rax
0x1801e2490  lea     rax, [rbp+150h+var_1B8]
0x1801e2494  mov     qword ptr [rsp+250h+var_228], rax
0x1801e2499  lea     rax, [rsp+250h+bstrString]
0x1801e249e  mov     [rsp+250h+ppv], rax
0x1801e24a3  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801e24a8  call    ?TreatWarningsAsErrors@AppraiserTestHooks@Appraiser@Compat@Windows@@SA_NXZ; Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors(void)
0x1801e24ad  lea     r9, aErrorRetrievin_0; "Error retrieving current service ID: [0"...
0x1801e24b4  mov     dword ptr [rsp+250h+var_220], ebx; char *
0x1801e24b8  mov     r8, r14; unsigned int
0x1801e24bb  mov     qword ptr [rsp+250h+var_228], r9; int
0x1801e24c0  mov     r9, rsi; char *
0x1801e24c3  mov     edx, r12d; bool
0x1801e24c6  test    al, al
0x1801e24c8  jz      short loc_1801E24D2
0x1801e24ca  mov     dword ptr [rsp+250h+ppv], ebx
0x1801e24ce  mov     ecx, edi
0x1801e24d0  jmp     short loc_1801E24DD
0x1801e24d2  mov     [rsp+250h+ppv], 0; char *
0x1801e24db  xor     ecx, ecx; this
0x1801e24dd  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801e24e2  mov     ebx, 80888001h
0x1801e24e7  jmp     loc_1801E2BB6
0x1801e24ec  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801e24f2  and     eax, edi
0x1801e24f4  test    al, al
0x1801e24f6  jz      short loc_1801E2513
0x1801e24f8  lea     r9, aErrorRetrievin_0; "Error retrieving current service ID: [0"...
0x1801e24ff  mov     dword ptr [rsp+250h+ppv], ebx
0x1801e2503  mov     r8, rsi; char *
0x1801e2506  mov     rdx, r14; char *
0x1801e2509  mov     ecx, 310h; unsigned int
0x1801e250e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801e2513  mov     rcx, [r15]
0x1801e2516  lea     r9, [r15+40h]
0x1801e251a  lea     r8, aAppraiserDrive; "Appraiser Driver Scan"
0x1801e2521  lea     rdx, [r15+30h]
0x1801e2525  mov     rax, [rcx]
0x1801e2528  mov     rax, [rax+8]
0x1801e252c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2531  mov     ebx, eax
0x1801e2533  cmp     eax, 80004002h
0x1801e2538  jz      loc_1801E2BB6
0x1801e253e  test    eax, eax
0x1801e2540  jns     short loc_1801E2564
0x1801e2542  lea     r9, aErrorInitiatin; "Error initiating internal session: [0x%"...
0x1801e2549  mov     dword ptr [rsp+250h+var_220], eax
0x1801e254d  mov     qword ptr [rsp+250h+var_228], r9
0x1801e2552  mov     r8, r14
0x1801e2555  mov     r9, rsi
0x1801e2558  mov     edx, 325h
0x1801e255d  mov     ecx, edi
0x1801e255f  jmp     loc_1801E2BAD
0x1801e2564  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801e256a  and     eax, edi
0x1801e256c  test    al, al
0x1801e256e  jz      short loc_1801E258B
0x1801e2570  lea     r9, aErrorInitiatin; "Error initiating internal session: [0x%"...
0x1801e2577  mov     dword ptr [rsp+250h+ppv], ebx
0x1801e257b  mov     r8, rsi; char *
0x1801e257e  mov     rdx, r14; char *
0x1801e2581  mov     ecx, 325h; unsigned int
0x1801e2586  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801e258b  lea     r13, [r15+8]
0x1801e258f  mov     [r15+50h], dil
0x1801e2593  lea     r9, _GUID_816858a4_260d_4260_933a_2585f1abc76b; riid
0x1801e259a  mov     [rsp+250h+ppv], r13; ppv
0x1801e259f  mov     r8d, edi; dwClsContext
0x1801e25a2  lea     rcx, _GUID_4cb43d7f_7eee_4906_8698_60da1c38f2fe; rclsid
0x1801e25a9  xor     edx, edx; pUnkOuter
0x1801e25ab  call    cs:__imp_CoCreateInstance
0x1801e25b1  mov     ebx, eax
0x1801e25b3  test    eax, eax
0x1801e25b5  jns     loc_1801E26EF
0x1801e25bb  lea     rcx, [rbp+150h+var_170]; this
0x1801e25bf  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1801e25c4  mov     rcx, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1801e25cb  lea     r9, [rbp+150h+var_170]
0x1801e25cf  test    rcx, rcx
0x1801e25d2  cmovnz  r9, rcx
0x1801e25d6  xor     edx, edx
0x1801e25d8  lock xadd [r9+88h], rdx; unsigned __int64
0x1801e25e1  lea     r8, [rbp+150h+var_E0]; char *
0x1801e25e5  mov     rcx, r9; this
0x1801e25e8  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1801e25ed  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1801e25f4  jz      short loc_1801E2602
0x1801e25f6  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1801e25fd  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1801e2602  mov     r13, cs:qword_1802C9628
0x1801e2609  mov     r12d, 32Fh
0x1801e260f  mov     eax, [r13+0]
0x1801e2613  cmp     eax, 5
0x1801e2616  jbe     loc_1801E26DE
0x1801e261c  mov     rdx, [r13+18h]
0x1801e2620  mov     rcx, 200000000000h
0x1801e262a  mov     rax, [r13+10h]
0x1801e262e  test    rcx, rax
0x1801e2631  jz      loc_1801E26DE
0x1801e2637  mov     rax, rdx
0x1801e263a  and     rax, rcx
0x1801e263d  cmp     rax, rdx
0x1801e2640  jnz     loc_1801E26DE
0x1801e2646  lea     rax, [rbp+150h+var_E0]
0x1801e264a  mov     [rsp+250h+var_1E8], ebx
0x1801e264e  mov     [rsp+250h+bstrString], rax
0x1801e2653  lea     rcx, [rbp+150h+SystemTime]; lpSystemTime
0x1801e2657  lea     rax, szValueBuf
0x1801e265e  mov     [rbp+150h+var_1B8], rsi
0x1801e2662  xorps   xmm0, xmm0
0x1801e2665  mov     [rbp+150h+var_1C8], rax
0x1801e2669  mov     [rbp+150h+var_1C0], r14
0x1801e266d  mov     [rsp+250h+var_1EC], r12d
0x1801e2672  movups  xmmword ptr [rbp+150h+SystemTime.wYear], xmm0
0x1801e2676  call    cs:__imp_GetSystemTime
0x1801e267c  movaps  xmm0, xmmword ptr [rbp+150h+SystemTime.wYear]
0x1801e2680  lea     rax, [rbp+150h+pvarg]
0x1801e2684  mov     [rbp+150h+var_1D0], rax
0x1801e2688  lea     rdx, byte_1802A5B33
0x1801e268f  lea     rax, [rsp+250h+bstrString]
0x1801e2694  movdqa  xmmword ptr [rbp+150h+pvarg], xmm0
0x1801e2699  mov     [rsp+250h+var_200], rax
0x1801e269e  mov     rcx, r13
0x1801e26a1  lea     rax, [rsp+250h+var_1E8]
0x1801e26a6  mov     [rsp+250h+var_208], rax
0x1801e26ab  lea     rax, [rbp+150h+var_1B8]
0x1801e26af  mov     [rsp+250h+var_210], rax
0x1801e26b4  lea     rax, [rbp+150h+var_1C0]
0x1801e26b8  mov     [rsp+250h+var_218], rax
0x1801e26bd  lea     rax, [rsp+250h+var_1EC]
0x1801e26c2  mov     [rsp+250h+var_220], rax
0x1801e26c7  lea     rax, [rbp+150h+var_1C8]
0x1801e26cb  mov     qword ptr [rsp+250h+var_228], rax
0x1801e26d0  lea     rax, [rbp+150h+var_1D0]
0x1801e26d4  mov     [rsp+250h+ppv], rax
0x1801e26d9  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801e26de  call    ?TreatWarningsAsErrors@AppraiserTestHooks@Appraiser@Compat@Windows@@SA_NXZ; Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors(void)
0x1801e26e3  lea     r9, aErrorCreatingI_2; "Error creating IUpdateSession: [0x%x]."
0x1801e26ea  jmp     loc_1801E24B4
0x1801e26ef  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801e26f5  and     eax, edi
0x1801e26f7  test    al, al
0x1801e26f9  jz      short loc_1801E2716
0x1801e26fb  lea     r9, aErrorCreatingI_2; "Error creating IUpdateSession: [0x%x]."
0x1801e2702  mov     dword ptr [rsp+250h+ppv], ebx
0x1801e2706  mov     r8, rsi; char *
0x1801e2709  mov     rdx, r14; char *
0x1801e270c  mov     ecx, 32Fh; unsigned int
0x1801e2711  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801e2716  lea     rcx, aAppraiserDrive; "Appraiser Driver Scan"
0x1801e271d  call    cs:__imp_SysAllocString
0x1801e2723  mov     [rsp+250h+bstrString], rax
0x1801e2728  mov     rdx, rax
0x1801e272b  test    rax, rax
0x1801e272e  jnz     short loc_1801E273A
0x1801e2730  mov     ebx, 8007000Eh
0x1801e2735  jmp     loc_1801E2BB6
0x1801e273a  mov     rcx, [r13+0]
0x1801e273e  mov     rax, [rcx]
0x1801e2741  mov     rax, [rax+40h]
0x1801e2745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e274a  mov     ebx, eax
0x1801e274c  test    eax, eax
0x1801e274e  jns     short loc_1801E277B
0x1801e2750  lea     r9, aErrorSettingCl; "Error setting ClientApplicationID: [0x%"...
0x1801e2757  mov     edx, 335h; bool
0x1801e275c  mov     dword ptr [rsp+250h+var_220], ebx; char *
0x1801e2760  mov     r8, r14; unsigned int
0x1801e2763  mov     qword ptr [rsp+250h+var_228], r9; int
0x1801e2768  mov     ecx, edi; this
0x1801e276a  mov     r9, rsi; char *
0x1801e276d  mov     dword ptr [rsp+250h+ppv], ebx; char *
0x1801e2771  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801e2776  jmp     loc_1801E2B73
0x1801e277b  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801e2781  and     eax, edi
0x1801e2783  test    al, al
0x1801e2785  jz      short loc_1801E27A2
0x1801e2787  lea     r9, aErrorSettingCl; "Error setting ClientApplicationID: [0x%"...
0x1801e278e  mov     dword ptr [rsp+250h+ppv], ebx
0x1801e2792  mov     r8, rsi; char *
0x1801e2795  mov     rdx, r14; char *
0x1801e2798  mov     ecx, 335h; unsigned int
0x1801e279d  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801e27a2  mov     rcx, [r13+0]
0x1801e27a6  lea     r13, [r15+10h]
0x1801e27aa  mov     rdx, r13
0x1801e27ad  mov     rax, [rcx]
0x1801e27b0  mov     rax, [rax+60h]
0x1801e27b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e27b9  mov     ebx, eax
0x1801e27bb  test    eax, eax
0x1801e27bd  jns     short loc_1801E27CD
0x1801e27bf  lea     r9, aErrorCreatingI_0; "Error creating IUpdateSearcher: [0x%x]."
  ... truncated ...
```
