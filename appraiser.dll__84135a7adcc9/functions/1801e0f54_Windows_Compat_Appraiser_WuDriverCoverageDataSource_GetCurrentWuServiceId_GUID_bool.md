# Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId(_GUID *,bool *)

- ea: `0x1801e0f54`
- end: `0x1801e16fa`
- name: `?GetCurrentWuServiceId@WuDriverCoverageDataSource@Appraiser@Compat@Windows@@CAJPEAU_GUID@@PEA_N@Z`
- size: `1958`
- prototype: `__int64 __fastcall(UUID *Uuid, bool *)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1801df91c`
- `0x1801e22ac`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800a5d88`
- `0x1801e0f54`
- `0x18021f010`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x1801e15f0`
- `RPCRT4!UuidFromStringW` at `0x1801e15f0`
- `KERNEL32!GetSystemTime` at `0x1801e10b7`
- `KERNEL32!GetSystemTime` at `0x1801e1271`
- `KERNEL32!GetSystemTime` at `0x1801e10b7`
- `KERNEL32!GetSystemTime` at `0x1801e1271`
- `OLE32!CoCreateInstance` at `0x1801e0fd9`
- `OLE32!CoCreateInstance` at `0x1801e0fd9`
- `OLEAUT32!__imp_SysFreeString` at `0x1801e14ff`
- `OLEAUT32!__imp_SysFreeString` at `0x1801e14ff`

## string_xrefs

- `0x1801e1043`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e116f`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e1490`: `Error checking if this service is the default: [0x%x].`
- `0x1801e169f`: `Error checking if this service is the default: [0x%x].`
- `0x1801e1128`: `Error creating IUpdateServiceManager: [0x%x].`
- `0x1801e117a`: `Error creating IUpdateServiceManager: [0x%x].`
- `0x1801e103c`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId`
- `0x1801e1168`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId`
- `0x1801e1347`: `Error getting number of services in collection: [0x%x].`
- `0x1801e137f`: `Error getting number of services in collection: [0x%x].`
- `0x1801e12e1`: `Error getting services collection: [0x%x].`
- `0x1801e1311`: `Error getting services collection: [0x%x].`
- `0x1801e15aa`: `Error getting service id: [0x%x].`
- `0x1801e15ce`: `Error getting service id: [0x%x].`
- `0x1801e1643`: `Error checking if this service is managed by WSUS: [0x%x].`
- `0x1801e166d`: `Error checking if this service is managed by WSUS: [0x%x].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId(UUID *Uuid, bool *a2)
{
  HRESULT v4; // r14d
  volatile signed __int64 *v5; // r9
  void **v6; // rdx
  int v7; // r15d
  int v8; // r8d
  int v9; // r9d
  bool v10; // al
  char v11; // dl
  __int64 v12; // rcx
  int v13; // ebx
  int v14; // ebx
  volatile signed __int64 *v15; // rcx
  void **v16; // rdx
  int v17; // r15d
  int v18; // r8d
  int v19; // r9d
  bool v20; // al
  const char *v21; // r9
  char v22; // dl
  int v23; // r14d
  __int64 v24; // rax
  int v26; // eax
  const char *v27; // rax
  char v28; // dl
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  int v30[2]; // [rsp+28h] [rbp-D8h]
  const char *v31; // [rsp+28h] [rbp-D8h]
  const char *v32; // [rsp+28h] [rbp-D8h]
  char *v33; // [rsp+30h] [rbp-D0h]
  _WORD v34[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v35; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 *v36; // [rsp+68h] [rbp-98h] BYREF
  int v37; // [rsp+70h] [rbp-90h] BYREF
  int v38; // [rsp+74h] [rbp-8Ch] BYREF
  int v39; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+88h] [rbp-78h] BYREF
  BSTR bstrString; // [rsp+90h] [rbp-70h] BYREF
  LPVOID v43; // [rsp+98h] [rbp-68h] BYREF
  char *v44; // [rsp+A0h] [rbp-60h] BYREF
  const char *v45; // [rsp+A8h] [rbp-58h] BYREF
  const char *v46; // [rsp+B0h] [rbp-50h] BYREF
  const char *v47; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v48[2]; // [rsp+C0h] [rbp-40h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+D0h] [rbp-30h] BYREF
  struct _SYSTEMTIME v50; // [rsp+E0h] [rbp-20h] BYREF
  char v51[144]; // [rsp+F0h] [rbp-10h] BYREF
  char v52[144]; // [rsp+180h] [rbp+80h] BYREF

  v37 = 0;
  *Uuid = 0;
  *a2 = 0;
  v43 = 0;
  v41 = 0;
  v40 = 0;
  v36 = 0;
  v34[0] = 0;
  v35 = 0;
  bstrString = 0;
  v4 = CoCreateInstance(
         &GUID_f8d253d9_89a4_4daa_87b6_1168369f0b21,
         0,
         1u,
         &GUID_23857e3c_02ba_44a3_9423_b1c900805f37,
         &v43);
  if ( v4 < 0 )
  {
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v51);
    v5 = (volatile signed __int64 *)v51;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v5 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v5,
      _InterlockedExchangeAdd64(v5 + 17, 0),
      v52);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v6);
    v7 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v38 = v4;
      v44 = v52;
      v45 = "Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId";
      v47 = (const char *)&szValueBuf;
      v46 = "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp";
      v39 = 1101;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v48[0] = &v50;
      v50 = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v7,
        (unsigned int)&unk_1802A5958,
        v8,
        v9,
        (__int64)v48,
        (__int64)&v47,
        (__int64)&v39,
        (__int64)&v46,
        (__int64)&v45,
        (__int64)&v38,
        (__int64)&v44);
    }
    v10 = Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors();
    LODWORD(v33) = v4;
    v31 = "Error creating IUpdateServiceManager: [0x%x].";
    v11 = 77;
    if ( v10 )
    {
      LODWORD(ppv) = v4;
LABEL_12:
      v12 = 1;
LABEL_14:
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)v12,
        v11,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
        "Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId",
        (const char *)ppv,
        (int)v31,
        v33);
      v13 = -2138537983;
      goto LABEL_51;
    }
    goto LABEL_13;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x44Du,
      "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
      "Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId",
      "Error creating IUpdateServiceManager: [0x%x].",
      v4);
  v14 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v43 + 56LL))(v43, &v41);
  if ( v14 < 0 )
  {
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v51);
    v15 = (volatile signed __int64 *)v51;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v15 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v15,
      _InterlockedExchangeAdd64(v15 + 17, 0),
      v52);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v16);
    v17 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v39 = v14;
      v48[0] = v52;
      v47 = "Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId";
      v45 = (const char *)&szValueBuf;
      v46 = "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp";
      v38 = 1104;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v44 = (char *)&v50;
      v50 = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v17,
        (unsigned int)&unk_1802A5A1E,
        v18,
        v19,
        (__int64)&v44,
        (__int64)&v45,
        (__int64)&v38,
        (__int64)&v46,
        (__int64)&v47,
        (__int64)&v39,
        (__int64)v48);
    }
    v20 = Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors();
    LODWORD(v33) = v14;
    v31 = "Error getting services collection: [0x%x].";
    v11 = 80;
    if ( v20 )
    {
      LODWORD(ppv) = v14;
      goto LABEL_12;
    }
LABEL_13:
    ppv = 0;
    v12 = 0;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x450u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
      "Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId",
      "Error getting services collection: [0x%x].",
      v14);
  v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 72LL))(v41, &v37);
  if ( v13 < 0 )
  {
    v21 = "Error getting number of services in collection: [0x%x].";
    v22 = 83;
LABEL_32:
    LODWORD(v33) = v13;
    LODWORD(v32) = (_DWORD)v21;
    goto LABEL_33;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x453u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
      "Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId",
      "Error getting number of services in collection: [0x%x].",
      v13);
  if ( v37 < 0 )
  {
    LODWORD(v33) = v37;
    v13 = -2147024883;
    v22 = 87;
    v32 = "Negative count: %l.";
LABEL_33:
    LODWORD(ppv) = v13;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v22,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
      "Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId",
      (const char *)ppv,
      (int)v32,
      v33);
    goto LABEL_51;
  }
  v23 = 0;
  if ( v37 <= 0 )
  {
LABEL_50:
    v13 = -2147467259;
    goto LABEL_51;
  }
  while ( 1 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v41 + 56LL))(v41, (unsigned int)v23, &v40);
    if ( v13 < 0 )
    {
      v27 = "Error getting item %l: [0x%x].";
      v28 = 93;
      goto LABEL_76;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    {
      v30[0] = v13;
      LODWORD(ppv) = v23;
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x45Du,
        "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
        "Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId",
        "Error getting item %l: [0x%x].",
        ppv,
        *(_QWORD *)v30);
    }
    v13 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v40)(
            v40,
            &GUID_1518b460_6518_4172_940f_c75883b24ceb,
            &v36);
    if ( v13 < 0 )
    {
      v27 = "Error getting V2 object for item %l: [0x%x].";
      v28 = 96;
LABEL_76:
      LODWORD(v33) = v23;
      LODWORD(ppv) = v13;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v28,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
        "Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId",
        (const char *)ppv,
        (int)v27,
        v33,
        v13);
      goto LABEL_51;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    {
      v30[0] = v13;
      LODWORD(ppv) = v23;
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x460u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
        "Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId",
        "Error getting V2 object for item %l: [0x%x].",
        ppv,
        *(_QWORD *)v30);
    }
    v13 = (*(__int64 (__fastcall **)(__int64 *, _WORD *))(*v36 + 160))(v36, v34);
    if ( v13 < 0 )
    {
      LODWORD(v33) = v13;
      v32 = "Error checking if this service is the default: [0x%x].";
      v22 = 99;
      goto LABEL_33;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x463u,
        "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
        "Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId",
        "Error checking if this service is the default: [0x%x].",
        v13);
    v24 = *v36;
    if ( v34[0] == 0xFFFF )
      break;
    (*(void (**)(void))(v24 + 16))();
    v36 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    ++v23;
    v40 = 0;
    if ( v23 >= v37 )
      goto LABEL_50;
  }
  v13 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v24 + 120))(v36, &bstrString);
  if ( v13 < 0 )
  {
    v21 = "Error getting service id: [0x%x].";
    v22 = 104;
    goto LABEL_32;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x468u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
      "Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId",
      "Error getting service id: [0x%x].",
      v13);
  if ( UuidFromStringW(bstrString, Uuid) )
  {
    v13 = -2147024883;
    LODWORD(ppv) = -2147024883;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      108,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
      "Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId",
      (const char *)ppv,
      (int)"Could not convert guid.",
      v33);
    goto LABEL_51;
  }
  v26 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*v36 + 80))(v36, &v35);
  v13 = v26;
  if ( v26 < 0 )
  {
    LODWORD(v33) = v26;
    v32 = "Error checking if this service is managed by WSUS: [0x%x].";
    v22 = 112;
    goto LABEL_33;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x470u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
      "Windows::Compat::Appraiser::WuDriverCoverageDataSource::GetCurrentWuServiceId",
      "Error checking if this service is managed by WSUS: [0x%x].",
      v26);
  v13 = 0;
  *a2 = v35 == -1;
LABEL_51:
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64 *))(*v36 + 16))(v36);
    v36 = 0;
  }
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    v40 = 0;
  }
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
  if ( v43 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v43 + 16LL))(v43);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1801e0f54  mov     [rsp-8+arg_10], rbx
0x1801e0f59  push    rbp
0x1801e0f5a  push    rsi
0x1801e0f5b  push    rdi
0x1801e0f5c  push    r12
0x1801e0f5e  push    r13
0x1801e0f60  push    r14
0x1801e0f62  push    r15
0x1801e0f64  lea     rbp, [rsp-120h]
0x1801e0f6c  sub     rsp, 220h
0x1801e0f73  mov     rax, cs:__security_cookie
0x1801e0f7a  xor     rax, rsp
0x1801e0f7d  mov     [rbp+150h+var_40], rax
0x1801e0f84  xor     r13d, r13d
0x1801e0f87  lea     rax, [rbp+150h+var_1B8]
0x1801e0f8b  xorps   xmm0, xmm0
0x1801e0f8e  mov     [rsp+250h+var_1E0], r13d
0x1801e0f93  movups  xmmword ptr [rcx], xmm0
0x1801e0f96  mov     r12, rdx
0x1801e0f99  mov     [rdx], r13b
0x1801e0f9c  mov     r15, rcx
0x1801e0f9f  mov     [rbp+150h+var_1B8], r13
0x1801e0fa3  lea     r8d, [r13+1]; dwClsContext
0x1801e0fa7  mov     [rbp+150h+var_1C8], r13
0x1801e0fab  lea     r9, _GUID_23857e3c_02ba_44a3_9423_b1c900805f37; riid
0x1801e0fb2  mov     [rbp+150h+var_1D0], r13
0x1801e0fb6  xor     edx, edx; pUnkOuter
0x1801e0fb8  mov     [rsp+250h+var_1E8], r13
0x1801e0fbd  lea     rcx, _GUID_f8d253d9_89a4_4daa_87b6_1168369f0b21; rclsid
0x1801e0fc4  mov     [rsp+250h+var_1F0], r13w
0x1801e0fca  mov     [rsp+250h+var_1EC], r13w
0x1801e0fd0  mov     [rbp+150h+bstrString], r13
0x1801e0fd4  mov     [rsp+250h+ppv], rax; ppv
0x1801e0fd9  call    cs:__imp_CoCreateInstance
0x1801e0fdf  mov     r14d, eax
0x1801e0fe2  test    eax, eax
0x1801e0fe4  jns     loc_1801E1162
0x1801e0fea  lea     rcx, [rbp+150h+var_160]; this
0x1801e0fee  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1801e0ff3  mov     rcx, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1801e0ffa  lea     r9, [rbp+150h+var_160]
0x1801e0ffe  test    rcx, rcx
0x1801e1001  mov     edx, r13d
0x1801e1004  cmovnz  r9, rcx
0x1801e1008  lock xadd [r9+88h], rdx; unsigned __int64
0x1801e1011  lea     r8, [rbp+150h+var_D0]; char *
0x1801e1018  mov     rcx, r9; this
0x1801e101b  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1801e1020  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r13b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1801e1027  jz      short loc_1801E1035
0x1801e1029  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1801e1030  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1801e1035  mov     r15, cs:qword_1802C9628
0x1801e103c  lea     rdi, aWindowsCompatA_75; "Windows::Compat::Appraiser::WuDriverCov"...
0x1801e1043  lea     rsi, aOnecoreBaseApp_99; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801e104a  mov     ebx, 44Dh
0x1801e104f  mov     eax, [r15]
0x1801e1052  cmp     eax, 5
0x1801e1055  jbe     loc_1801E111E
0x1801e105b  mov     rdx, [r15+18h]
0x1801e105f  mov     rcx, 200000000000h
0x1801e1069  mov     rax, [r15+10h]
0x1801e106d  test    rcx, rax
0x1801e1070  jz      loc_1801E111E
0x1801e1076  mov     rax, rdx
0x1801e1079  and     rax, rcx
0x1801e107c  cmp     rax, rdx
0x1801e107f  jnz     loc_1801E111E
0x1801e1085  lea     rax, [rbp+150h+var_D0]
0x1801e108c  mov     [rsp+250h+var_1DC], r14d
0x1801e1091  mov     [rbp+150h+var_1B0], rax
0x1801e1095  lea     rcx, [rbp+150h+SystemTime]; lpSystemTime
0x1801e1099  lea     rax, szValueBuf
0x1801e10a0  mov     [rbp+150h+var_1A8], rdi
0x1801e10a4  xorps   xmm0, xmm0
0x1801e10a7  mov     [rbp+150h+var_198], rax
0x1801e10ab  mov     [rbp+150h+var_1A0], rsi
0x1801e10af  mov     [rsp+250h+var_1D8], ebx
0x1801e10b3  movups  xmmword ptr [rbp+150h+SystemTime.wYear], xmm0
0x1801e10b7  call    cs:__imp_GetSystemTime
0x1801e10bd  movaps  xmm0, xmmword ptr [rbp+150h+SystemTime.wYear]
0x1801e10c1  lea     rax, [rbp+150h+var_170]
0x1801e10c5  mov     [rbp+150h+var_190], rax
0x1801e10c9  lea     rdx, unk_1802A5958
0x1801e10d0  lea     rax, [rbp+150h+var_1B0]
0x1801e10d4  movdqa  [rbp+150h+var_170], xmm0
0x1801e10d9  mov     [rsp+250h+var_200], rax
0x1801e10de  mov     rcx, r15
0x1801e10e1  lea     rax, [rsp+250h+var_1DC]
0x1801e10e6  mov     [rsp+250h+var_208], rax
0x1801e10eb  lea     rax, [rbp+150h+var_1A8]
0x1801e10ef  mov     [rsp+250h+var_210], rax
0x1801e10f4  lea     rax, [rbp+150h+var_1A0]
0x1801e10f8  mov     [rsp+250h+var_218], rax
0x1801e10fd  lea     rax, [rsp+250h+var_1D8]
0x1801e1102  mov     [rsp+250h+var_220], rax
0x1801e1107  lea     rax, [rbp+150h+var_198]
0x1801e110b  mov     qword ptr [rsp+250h+var_228], rax
0x1801e1110  lea     rax, [rbp+150h+var_190]
0x1801e1114  mov     [rsp+250h+ppv], rax
0x1801e1119  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801e111e  call    ?TreatWarningsAsErrors@AppraiserTestHooks@Appraiser@Compat@Windows@@SA_NXZ; Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors(void)
0x1801e1123  mov     dword ptr [rsp+250h+var_220], r14d; char *
0x1801e1128  lea     r9, aErrorCreatingI_1; "Error creating IUpdateServiceManager: ["...
0x1801e112f  mov     qword ptr [rsp+250h+var_228], r9; int
0x1801e1134  mov     r9, rdi; char *
0x1801e1137  mov     r8, rsi; unsigned int
0x1801e113a  mov     edx, ebx; bool
0x1801e113c  test    al, al
0x1801e113e  jz      short loc_1801E114C
0x1801e1140  mov     dword ptr [rsp+250h+ppv], r14d
0x1801e1145  mov     ecx, 1
0x1801e114a  jmp     short loc_1801E1153
0x1801e114c  mov     [rsp+250h+ppv], r13; char *
0x1801e1151  xor     ecx, ecx; this
0x1801e1153  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801e1158  mov     ebx, 80888001h
0x1801e115d  jmp     loc_1801E14F6
0x1801e1162  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801e1168  lea     rdi, aWindowsCompatA_75; "Windows::Compat::Appraiser::WuDriverCov"...
0x1801e116f  lea     rsi, aOnecoreBaseApp_99; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801e1176  test    al, 1
0x1801e1178  jz      short loc_1801E1196
0x1801e117a  lea     r9, aErrorCreatingI_1; "Error creating IUpdateServiceManager: ["...
0x1801e1181  mov     dword ptr [rsp+250h+ppv], r14d
0x1801e1186  mov     r8, rdi; char *
0x1801e1189  mov     rdx, rsi; char *
0x1801e118c  mov     ecx, 44Dh; unsigned int
0x1801e1191  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801e1196  mov     rcx, [rbp+150h+var_1B8]
0x1801e119a  lea     rdx, [rbp+150h+var_1C8]
0x1801e119e  mov     rax, [rcx]
0x1801e11a1  mov     rax, [rax+38h]
0x1801e11a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e11aa  mov     ebx, eax
0x1801e11ac  test    eax, eax
0x1801e11ae  jns     loc_1801E1307
0x1801e11b4  lea     rcx, [rbp+150h+var_160]; this
0x1801e11b8  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1801e11bd  mov     rdx, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1801e11c4  lea     rcx, [rbp+150h+var_160]
0x1801e11c8  test    rdx, rdx
0x1801e11cb  cmovnz  rcx, rdx; this
0x1801e11cf  mov     rdx, r13
0x1801e11d2  lock xadd [rcx+88h], rdx; unsigned __int64
0x1801e11db  lea     r8, [rbp+150h+var_D0]; char *
0x1801e11e2  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1801e11e7  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r13b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1801e11ee  jz      short loc_1801E11FC
0x1801e11f0  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1801e11f7  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1801e11fc  mov     r15, cs:qword_1802C9628
0x1801e1203  mov     r14d, 450h
0x1801e1209  mov     eax, [r15]
0x1801e120c  cmp     eax, 5
0x1801e120f  jbe     loc_1801E12D8
0x1801e1215  mov     rdx, [r15+18h]
0x1801e1219  mov     rcx, 200000000000h
0x1801e1223  mov     rax, [r15+10h]
0x1801e1227  test    rcx, rax
0x1801e122a  jz      loc_1801E12D8
0x1801e1230  mov     rax, rdx
0x1801e1233  and     rax, rcx
0x1801e1236  cmp     rax, rdx
0x1801e1239  jnz     loc_1801E12D8
0x1801e123f  lea     rax, [rbp+150h+var_D0]
0x1801e1246  mov     [rsp+250h+var_1D8], ebx
0x1801e124a  mov     [rbp+150h+var_190], rax
0x1801e124e  lea     rcx, [rbp+150h+SystemTime]; lpSystemTime
0x1801e1252  lea     rax, szValueBuf
0x1801e1259  mov     [rbp+150h+var_198], rdi
0x1801e125d  xorps   xmm0, xmm0
0x1801e1260  mov     [rbp+150h+var_1A8], rax
0x1801e1264  mov     [rbp+150h+var_1A0], rsi
0x1801e1268  mov     [rsp+250h+var_1DC], r14d
0x1801e126d  movups  xmmword ptr [rbp+150h+SystemTime.wYear], xmm0
0x1801e1271  call    cs:__imp_GetSystemTime
0x1801e1277  movaps  xmm0, xmmword ptr [rbp+150h+SystemTime.wYear]
0x1801e127b  lea     rax, [rbp+150h+var_170]
0x1801e127f  mov     [rbp+150h+var_1B0], rax
0x1801e1283  lea     rdx, unk_1802A5A1E
0x1801e128a  lea     rax, [rbp+150h+var_190]
0x1801e128e  movdqa  [rbp+150h+var_170], xmm0
0x1801e1293  mov     [rsp+250h+var_200], rax
0x1801e1298  mov     rcx, r15
0x1801e129b  lea     rax, [rsp+250h+var_1D8]
0x1801e12a0  mov     [rsp+250h+var_208], rax
0x1801e12a5  lea     rax, [rbp+150h+var_198]
0x1801e12a9  mov     [rsp+250h+var_210], rax
0x1801e12ae  lea     rax, [rbp+150h+var_1A0]
0x1801e12b2  mov     [rsp+250h+var_218], rax
0x1801e12b7  lea     rax, [rsp+250h+var_1DC]
0x1801e12bc  mov     [rsp+250h+var_220], rax
0x1801e12c1  lea     rax, [rbp+150h+var_1A8]
0x1801e12c5  mov     qword ptr [rsp+250h+var_228], rax
0x1801e12ca  lea     rax, [rbp+150h+var_1B0]
0x1801e12ce  mov     [rsp+250h+ppv], rax
0x1801e12d3  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801e12d8  call    ?TreatWarningsAsErrors@AppraiserTestHooks@Appraiser@Compat@Windows@@SA_NXZ; Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors(void)
0x1801e12dd  mov     dword ptr [rsp+250h+var_220], ebx
0x1801e12e1  lea     r9, aErrorGettingSe; "Error getting services collection: [0x%"...
0x1801e12e8  mov     qword ptr [rsp+250h+var_228], r9
0x1801e12ed  mov     r9, rdi
0x1801e12f0  mov     r8, rsi
0x1801e12f3  mov     edx, r14d
0x1801e12f6  test    al, al
0x1801e12f8  jz      loc_1801E114C
0x1801e12fe  mov     dword ptr [rsp+250h+ppv], ebx
0x1801e1302  jmp     loc_1801E1145
0x1801e1307  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801e130d  test    al, 1
0x1801e130f  jz      short loc_1801E132C
0x1801e1311  lea     r9, aErrorGettingSe; "Error getting services collection: [0x%"...
0x1801e1318  mov     dword ptr [rsp+250h+ppv], ebx
0x1801e131c  mov     r8, rdi; char *
0x1801e131f  mov     rdx, rsi; char *
0x1801e1322  mov     ecx, 450h; unsigned int
0x1801e1327  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801e132c  mov     rcx, [rbp+150h+var_1C8]
0x1801e1330  lea     rdx, [rsp+250h+var_1E0]
0x1801e1335  mov     rax, [rcx]
0x1801e1338  mov     rax, [rax+48h]
0x1801e133c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e1341  mov     ebx, eax
0x1801e1343  test    eax, eax
0x1801e1345  jns     short loc_1801E1375
0x1801e1347  lea     r9, aErrorGettingNu; "Error getting number of services in col"...
0x1801e134e  mov     edx, 453h; bool
0x1801e1353  mov     dword ptr [rsp+250h+var_220], ebx; char *
0x1801e1357  mov     qword ptr [rsp+250h+var_228], r9; int
0x1801e135c  mov     ecx, 1; this
0x1801e1361  mov     r9, rdi; char *
0x1801e1364  mov     dword ptr [rsp+250h+ppv], ebx; char *
0x1801e1368  mov     r8, rsi; unsigned int
0x1801e136b  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801e1370  jmp     loc_1801E14F6
0x1801e1375  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801e137b  test    al, 1
0x1801e137d  jz      short loc_1801E139A
0x1801e137f  lea     r9, aErrorGettingNu; "Error getting number of services in col"...
0x1801e1386  mov     dword ptr [rsp+250h+ppv], ebx
0x1801e138a  mov     r8, rdi; char *
0x1801e138d  mov     rdx, rsi; char *
0x1801e1390  mov     ecx, 453h; unsigned int
0x1801e1395  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801e139a  mov     eax, [rsp+250h+var_1E0]
0x1801e139e  test    eax, eax
0x1801e13a0  jns     short loc_1801E13BE
0x1801e13a2  mov     dword ptr [rsp+250h+var_220], eax
0x1801e13a6  mov     ebx, 8007000Dh
0x1801e13ab  lea     rax, aNegativeCountL; "Negative count: %l."
0x1801e13b2  mov     edx, 457h
0x1801e13b7  mov     qword ptr [rsp+250h+var_228], rax
0x1801e13bc  jmp     short loc_1801E135C
0x1801e13be  mov     r14d, r13d
0x1801e13c1  test    eax, eax
0x1801e13c3  jle     loc_1801E14F1
0x1801e13c9  mov     rcx, [rbp+150h+var_1C8]
0x1801e13cd  lea     r8, [rbp+150h+var_1D0]
0x1801e13d1  mov     edx, r14d
0x1801e13d4  mov     rax, [rcx]
0x1801e13d7  mov     rax, [rax+38h]
0x1801e13db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e13e0  mov     ebx, eax
0x1801e13e2  test    eax, eax
0x1801e13e4  js      loc_1801E16C7
0x1801e13ea  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801e13f0  test    al, 1
0x1801e13f2  jz      short loc_1801E1414
0x1801e13f4  mov     [rsp+250h+var_228], ebx
0x1801e13f8  lea     r9, aErrorGettingIt; "Error getting item %l: [0x%x]."
0x1801e13ff  mov     r8, rdi; char *
0x1801e1402  mov     dword ptr [rsp+250h+ppv], r14d
0x1801e1407  mov     rdx, rsi; char *
0x1801e140a  mov     ecx, 45Dh; unsigned int
0x1801e140f  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801e1414  mov     rcx, [rbp+150h+var_1D0]
0x1801e1418  lea     r8, [rsp+250h+var_1E8]
0x1801e141d  lea     rdx, _GUID_1518b460_6518_4172_940f_c75883b24ceb
0x1801e1424  mov     rax, [rcx]
0x1801e1427  mov     rax, [rax]
0x1801e142a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e142f  mov     ebx, eax
0x1801e1431  test    eax, eax
0x1801e1433  js      loc_1801E16B9
0x1801e1439  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801e143f  test    al, 1
0x1801e1441  jz      short loc_1801E1463
0x1801e1443  mov     [rsp+250h+var_228], ebx
0x1801e1447  lea     r9, aErrorGettingV2; "Error getting V2 object for item %l: [0"...
0x1801e144e  mov     r8, rdi; char *
0x1801e1451  mov     dword ptr [rsp+250h+ppv], r14d
0x1801e1456  mov     rdx, rsi; char *
0x1801e1459  mov     ecx, 460h; unsigned int
0x1801e145e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801e1463  mov     rcx, [rsp+250h+var_1E8]
0x1801e1468  lea     rdx, [rsp+250h+var_1F0]
0x1801e146d  mov     rax, [rcx]
0x1801e1470  mov     rax, [rax+0A0h]
0x1801e1477  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
