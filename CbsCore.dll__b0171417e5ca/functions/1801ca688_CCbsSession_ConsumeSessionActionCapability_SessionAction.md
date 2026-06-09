# CCbsSession::ConsumeSessionActionCapability(SessionAction &&)

- ea: `0x1801ca688`
- end: `0x1801cad6b`
- name: `?ConsumeSessionActionCapability@CCbsSession@@AEAAJ$$QEAUSessionAction@@@Z`
- size: `1763`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1801c9aec`

## callees

- `0x180010b60`
- `0x180010cc0`
- `0x1800138b8`
- `0x18001e9c0`
- `0x18001ef60`
- `0x18001f520`
- `0x180042078`
- `0x180042130`
- `0x180093a70`
- `0x180093c4c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x180099700`
- `0x18009cf78`
- `0x1800ad504`
- `0x1800bf55c`
- `0x1800d1f7c`
- `0x1800eb920`
- `0x1801251c8`
- `0x1801aead0`
- `0x1801c9270`
- `0x1801ca688`
- `0x1801cb33c`
- `0x1801d01a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801caafa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801cab20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801cac70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801cac92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801caafa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801cab20`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801cac70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801cac92`

## pseudocode

```c
__int64 __fastcall CCbsSession::ConsumeSessionActionCapability(void **this, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  wchar_t *FastCbsIdentityString; // rax
  CCbsIdentity *v7; // rcx
  signed int Version; // eax
  __int64 v9; // r9
  signed int v10; // eax
  __int64 v11; // rdx
  unsigned __int64 v12; // rbx
  __int64 *v13; // r15
  __int64 v14; // rbx
  __int64 v15; // rbx
  signed int Property; // eax
  __int64 v17; // rdx
  struct CCbsPackage **v18; // rax
  signed int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  int FinalTargetState; // eax
  signed int v24; // eax
  int v25; // edx
  int v26; // r8d
  int v28; // eax
  signed int v29; // eax
  int v30; // [rsp+20h] [rbp-A9h]
  int v31; // [rsp+20h] [rbp-A9h]
  int InitPointer; // [rsp+20h] [rbp-A9h]
  int v33; // [rsp+20h] [rbp-A9h]
  LPVOID v34; // [rsp+60h] [rbp-69h] BYREF
  int v35[2]; // [rsp+68h] [rbp-61h] BYREF
  wchar_t *v36; // [rsp+70h] [rbp-59h] BYREF
  __int64 v37; // [rsp+78h] [rbp-51h] BYREF
  unsigned int v38; // [rsp+80h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+88h] [rbp-41h] BYREF
  int v40[2]; // [rsp+90h] [rbp-39h] BYREF
  _BYTE v41[24]; // [rsp+A0h] [rbp-29h] BYREF
  unsigned __int64 v42; // [rsp+B8h] [rbp-11h]
  __int64 *v43; // [rsp+C8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  if ( *(_DWORD *)a2 == 1 )
  {
    if ( *(_DWORD *)(a2 + 24) == 5 || *(_DWORD *)(a2 + 24) == 48 || *(_DWORD *)(a2 + 24) == 96 )
      LogAdapter::TraceAtLevel<>(1, "Forcing immediate initiation of deferred capability action.");
    FastCbsIdentityString = GetFastCbsIdentityString(*(const struct CCbsIdentity **)(a2 + 8));
    v7 = *(CCbsIdentity **)(a2 + 8);
    v36 = FastCbsIdentityString;
    LODWORD(pv) = 0;
    v38 = 0;
    Version = CCbsIdentity::GetVersion(v7, (unsigned int *)&pv, &v38);
    v4 = Version;
    if ( Version < 0 )
    {
      v38 = Version;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get FOD version");
        *(_QWORD *)v40 = &v38;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v40);
      }
      v5 = 442;
      goto LABEL_3;
    }
    v37 = ExecutionItemActionToString(*(unsigned int *)(a2 + 28));
    CCbsInterfaceArray<CCbsCapability *>::CCbsInterfaceArray<CCbsCapability *>(v41);
    v9 = *(_QWORD *)(a2 + 8);
    v31 = v9 + 584;
    v10 = CCbsCapabilityManager::EnumerateStoreCapabilities(v9 + 584, this, 257, v9 + 30);
    v4 = v10;
    if ( v10 < 0 )
    {
      v38 = v10;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"Unknown feature identifier: {}",
          (__int64)&v36);
        *(_QWORD *)v40 = &v38;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v40);
      }
      v11 = 459;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
        (const char *)v4,
        v31);
LABEL_63:
      CCbsArrayBase<CCbsSession *,CCbsInterfaceArray<CCbsSession *>>::~CCbsArrayBase<CCbsSession *,CCbsInterfaceArray<CCbsSession *>>(v41);
      return v4;
    }
    v12 = v42;
    if ( !v42 )
    {
      if ( LogAdapter::g_Logger )
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (__int64)LogAdapter::g_Logger,
          1,
          1,
          (__int64)"Ignoring {} request for absent capability: {}",
          (__int64)&v37,
          (__int64)&v36);
      v4 = 1;
      goto LABEL_63;
    }
    if ( v42 > 1 )
    {
      v4 = -2146498536;
      LODWORD(pv) = -2146498536;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (__int64)"{} request failed; more than one match found for capability: {}",
          (__int64)&v37,
          (__int64)&v36);
        *(_QWORD *)v40 = &pv;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v40);
      }
      v11 = 468;
      goto LABEL_24;
    }
    if ( *(_DWORD *)(a2 + 28) != 2 && *(_DWORD *)(a2 + 28) != 3 && *(_DWORD *)(a2 + 28) != 6 )
    {
      v4 = -2147024809;
      v38 = -2147024809;
      if ( LogAdapter::g_Logger )
      {
        *(_QWORD *)v40 = CbsStateToString(*(unsigned int *)(a2 + 24));
        LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Invalid target state: {} action: {} for capability: {}",
          (__int64)v40,
          (__int64)&v37,
          (__int64)&v36);
        v34 = &v38;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)&v34);
      }
      v11 = 480;
      goto LABEL_24;
    }
    if ( LogAdapter::g_Logger )
      LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
        (__int64)LogAdapter::g_Logger,
        1,
        1,
        (__int64)"{} capability: {}",
        (__int64)&v37,
        (__int64)&v36);
    v34 = 0;
    if ( !v12 )
      __fastfail(8u);
    v13 = v43;
    v14 = *v43;
    Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&v34);
    if ( (int)CCbsCapability::GetProperty(v14, this, this[141], 45) >= 0 && v34 && *(_WORD *)v34 )
    {
      v15 = *v13;
      *(_QWORD *)v40 = 0;
      pv = 0;
      InitPointer = Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(&pv);
      Property = CCbsCapability::GetProperty(v15, this, this[141], 1);
      v4 = Property;
      if ( Property < 0 )
      {
        v38 = Property;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Unable to determine package identity for capability: {}",
            (__int64)&v36);
          *(_QWORD *)v35 = &v38;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v35);
        }
        v17 = 500;
LABEL_42:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
          (const char *)v4,
          InitPointer);
        if ( pv )
        {
          CoTaskMemFree(pv);
          pv = 0;
        }
        Windows::AutoComPtr<CCbsDriverDeployment>::Close(v40);
LABEL_45:
        if ( v34 )
        {
          CoTaskMemFree(v34);
          v34 = 0;
        }
        goto LABEL_63;
      }
      v18 = (struct CCbsPackage **)Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&void CloseBcdStore(void *)>>::GetInitPointer(v40);
      v19 = CCbsSession::ResolvePackageByFullName((CCbsSession *)this, (const wchar_t *)pv, 1, v18, 1);
      v4 = v19;
      if ( v19 < 0 )
      {
        v38 = v19;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<AutoScz,wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v20,
            v21,
            (unsigned int)"Failed to resolve package identity '{}' for capability: {}",
            (__int64)&pv,
            (__int64)&v36);
          *(_QWORD *)v35 = &v38;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v35);
        }
        v17 = 504;
        goto LABEL_42;
      }
      if ( LogAdapter::g_Logger )
        LogAdapter::Logger::LogNumObjects<Windows::AutoGenericHandle<wchar_t *,0,&void Windows::Detail::CloseWithCoTaskMemFree<wchar_t>(wchar_t *)>>(
          (__int64)LogAdapter::g_Logger,
          v20,
          v21,
          v22,
          (__int64)&pv);
      FinalTargetState = SessionAction::GetFinalTargetState(a2);
      v24 = CCbsPackage::InitiateChanges(*(__int64 *)v40, (__int64)this, this[141], 0, FinalTargetState, 0, 0, 0);
      v4 = v24;
      if ( v24 < 0 )
      {
        v38 = v24;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<AutoScz,wchar_t const *>(
            (_DWORD)LogAdapter::g_Logger,
            v25,
            v26,
            (unsigned int)"Failed to initiate state change of package '{}' for capability: {}",
            (__int64)&pv,
            (__int64)&v36);
          *(_QWORD *)v35 = &v38;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v35);
        }
        v17 = 517;
        goto LABEL_42;
      }
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      Windows::AutoComPtr<CCbsDriverDeployment>::Close(v40);
    }
    else
    {
      v28 = SessionAction::GetFinalTargetState(a2);
      v29 = CCbsCapability::InitiateChanges(*v13, (__int64)this, 0xCu, v28, 0);
      v4 = v29;
      if ( v29 < 0 )
      {
        v38 = v29;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<wchar_t const *>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (__int64)"Failed to initiateChanges for capability: {}",
            (__int64)&v36);
          *(_QWORD *)v35 = &v38;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {}",
            (__int64)v35);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x20E,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
          (const char *)v4,
          v33);
        goto LABEL_45;
      }
    }
    if ( v34 )
      CoTaskMemFree(v34);
    v4 = 0;
    goto LABEL_63;
  }
  v4 = -2147024809;
  v5 = 426;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionoperationplanning.cpp",
    (const char *)v4,
    v30);
  return v4;
}

```

## disassembly

```asm
0x1801ca688  mov     [rsp-8+arg_10], rbx
0x1801ca68d  push    rbp
0x1801ca68e  push    rsi
0x1801ca68f  push    rdi
0x1801ca690  push    r12
0x1801ca692  push    r13
0x1801ca694  push    r14
0x1801ca696  push    r15
0x1801ca698  lea     rbp, [rsp-27h]
0x1801ca69d  sub     rsp, 0F0h
0x1801ca6a4  mov     rax, cs:__security_cookie
0x1801ca6ab  xor     rax, rsp
0x1801ca6ae  mov     [rbp+57h+var_40], rax
0x1801ca6b2  mov     r13d, 1
0x1801ca6b8  mov     rsi, rdx
0x1801ca6bb  mov     r14, rcx
0x1801ca6be  cmp     [rdx], r13d
0x1801ca6c1  jz      short loc_1801CA6E5
0x1801ca6c3  mov     ebx, 80070057h
0x1801ca6c8  mov     edx, 1AAh; void *
0x1801ca6cd  mov     rcx, [rbp+5Fh]; this
0x1801ca6d1  lea     r8, aOnecoreBaseCbs_69; "onecore\\base\\cbs\\core\\cbssessionope"...
0x1801ca6d8  mov     r9d, ebx; char *
0x1801ca6db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ca6e0  jmp     loc_1801CACAA
0x1801ca6e5  cmp     dword ptr [rdx+18h], 5
0x1801ca6e9  jz      short loc_1801CA6F7
0x1801ca6eb  cmp     dword ptr [rdx+18h], 30h ; '0'
0x1801ca6ef  jz      short loc_1801CA6F7
0x1801ca6f1  cmp     dword ptr [rdx+18h], 60h ; '`'
0x1801ca6f5  jnz     short loc_1801CA706
0x1801ca6f7  lea     rdx, aForcingImmedia; "Forcing immediate initiation of deferre"...
0x1801ca6fe  mov     ecx, r13d
0x1801ca701  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x1801ca706  mov     rcx, [rsi+8]; struct CCbsIdentity *
0x1801ca70a  call    ?GetFastCbsIdentityString@@YAPEA_WPEBVCCbsIdentity@@@Z; GetFastCbsIdentityString(CCbsIdentity const *)
0x1801ca70f  mov     rcx, [rsi+8]; this
0x1801ca713  lea     r8, [rbp+57h+var_A0]; unsigned int *
0x1801ca717  xor     r12d, r12d
0x1801ca71a  mov     [rbp+57h+var_B0], rax
0x1801ca71e  lea     rdx, [rbp+57h+pv]; unsigned int *
0x1801ca722  mov     dword ptr [rbp+57h+pv], r12d
0x1801ca726  mov     [rbp+57h+var_A0], r12d
0x1801ca72a  call    ?GetVersion@CCbsIdentity@@QEBAJPEAK0@Z; CCbsIdentity::GetVersion(ulong *,ulong *)
0x1801ca72f  mov     ebx, eax
0x1801ca731  test    eax, eax
0x1801ca733  jns     short loc_1801CA78E
0x1801ca735  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801ca73c  mov     [rbp+57h+var_A0], eax
0x1801ca73f  test    rcx, rcx
0x1801ca742  jz      short loc_1801CA784
0x1801ca744  lea     edi, [r12+3]
0x1801ca749  xor     edx, edx
0x1801ca74b  mov     r8d, edi
0x1801ca74e  lea     r9, aFailedToGetFod_1; "Failed to get FOD version"
0x1801ca755  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1801ca75a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801ca761  lea     rax, [rbp+57h+var_A0]
0x1801ca765  mov     qword ptr [rbp+57h+var_90], rax
0x1801ca769  lea     r9, asc_1802EE7AC; ": {}"
0x1801ca770  lea     rax, [rbp+57h+var_90]
0x1801ca774  mov     r8d, edi
0x1801ca777  mov     dl, r13b
0x1801ca77a  mov     qword ptr [rsp+120h+var_100], rax
0x1801ca77f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801ca784  mov     edx, 1BAh
0x1801ca789  jmp     loc_1801CA6CD
0x1801ca78e  mov     ecx, [rsi+1Ch]
0x1801ca791  call    ?ExecutionItemActionToString@@YAPEB_WW4ExecutionItemAction@@@Z; ExecutionItemActionToString(ExecutionItemAction)
0x1801ca796  lea     rcx, [rbp+57h+var_80]
0x1801ca79a  mov     [rbp+57h+var_A8], rax
0x1801ca79e  call    ??0?$CCbsInterfaceArray@PEAVCCbsCapability@@@@QEAA@XZ; CCbsInterfaceArray<CCbsCapability *>::CCbsInterfaceArray<CCbsCapability *>(void)
0x1801ca7a3  mov     r9, [rsi+8]
0x1801ca7a7  lea     rax, [rbp+57h+var_80]
0x1801ca7ab  mov     [rsp+120h+var_D0], rax
0x1801ca7b0  mov     r8d, 101h
0x1801ca7b6  mov     eax, dword ptr [rbp+57h+pv]
0x1801ca7b9  mov     rdx, r14
0x1801ca7bc  mov     [rsp+120h+var_D8], r12d
0x1801ca7c1  mov     [rsp+120h+var_E0], r13d
0x1801ca7c6  lea     rcx, [r9+248h]
0x1801ca7cd  mov     dword ptr [rsp+120h+var_E8], r13d
0x1801ca7d2  add     r9, 1Eh
0x1801ca7d6  mov     dword ptr [rsp+120h+var_F0], eax
0x1801ca7da  mov     [rsp+120h+var_F8], r12
0x1801ca7df  mov     qword ptr [rsp+120h+var_100], rcx
0x1801ca7e4  call    ?EnumerateStoreCapabilities@CCbsCapabilityManager@@QEBAJPEAVCCbsSession@@KPEB_W11KHHHPEAV?$CCbsInterfaceArray@PEAVCCbsCapability@@@@@Z; CCbsCapabilityManager::EnumerateStoreCapabilities(CCbsSession *,ulong,wchar_t const *,wchar_t const *,wchar_t const *,ulong,int,int,int,CCbsInterfaceArray<CCbsCapability *> *)
0x1801ca7e9  mov     ebx, eax
0x1801ca7eb  test    eax, eax
0x1801ca7ed  jns     short loc_1801CA851
0x1801ca7ef  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801ca7f6  mov     [rbp+57h+var_A0], eax
0x1801ca7f9  test    rcx, rcx
0x1801ca7fc  jz      short loc_1801CA847
0x1801ca7fe  lea     rax, [rbp+57h+var_B0]
0x1801ca802  mov     edi, 3
0x1801ca807  mov     r8d, edi
0x1801ca80a  mov     qword ptr [rsp+120h+var_100], rax
0x1801ca80f  lea     r9, aUnknownFeature; "Unknown feature identifier: {}"
0x1801ca816  xor     edx, edx
0x1801ca818  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1801ca81d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801ca824  lea     rax, [rbp+57h+var_A0]
0x1801ca828  mov     qword ptr [rbp+57h+var_90], rax
0x1801ca82c  lea     r9, asc_1802EE7AC; ": {}"
0x1801ca833  lea     rax, [rbp+57h+var_90]
0x1801ca837  mov     r8d, edi
0x1801ca83a  mov     dl, r13b
0x1801ca83d  mov     qword ptr [rsp+120h+var_100], rax
0x1801ca842  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801ca847  mov     edx, 1CBh
0x1801ca84c  jmp     loc_1801CA906
0x1801ca851  mov     rbx, [rbp+57h+var_68]
0x1801ca855  test    rbx, rbx
0x1801ca858  jnz     short loc_1801CA892
0x1801ca85a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801ca861  test    rcx, rcx
0x1801ca864  jz      short loc_1801CA88A
0x1801ca866  lea     rax, [rbp+57h+var_B0]
0x1801ca86a  mov     r8d, r13d
0x1801ca86d  mov     [rsp+120h+var_F8], rax
0x1801ca872  lea     r9, aIgnoringReques_0; "Ignoring {} request for absent capabili"...
0x1801ca879  lea     rax, [rbp+57h+var_A8]
0x1801ca87d  mov     dl, r13b
0x1801ca880  mov     qword ptr [rsp+120h+var_100], rax
0x1801ca885  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1801ca88a  mov     ebx, r13d
0x1801ca88d  jmp     loc_1801CACA1
0x1801ca892  cmp     rbx, r13
0x1801ca895  jbe     loc_1801CA91E
0x1801ca89b  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801ca8a2  mov     ebx, 800F0818h
0x1801ca8a7  mov     dword ptr [rbp+57h+pv], ebx
0x1801ca8aa  test    rcx, rcx
0x1801ca8ad  jz      short loc_1801CA901
0x1801ca8af  lea     rax, [rbp+57h+var_B0]
0x1801ca8b3  mov     edi, 3
0x1801ca8b8  mov     [rsp+120h+var_F8], rax
0x1801ca8bd  lea     r9, aRequestFailedM; "{} request failed; more than one match "...
0x1801ca8c4  lea     rax, [rbp+57h+var_A8]
0x1801ca8c8  mov     r8d, edi
0x1801ca8cb  xor     edx, edx
0x1801ca8cd  mov     qword ptr [rsp+120h+var_100], rax
0x1801ca8d2  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1801ca8d7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801ca8de  lea     rax, [rbp+57h+pv]
0x1801ca8e2  mov     qword ptr [rbp+57h+var_90], rax
0x1801ca8e6  lea     r9, asc_1802EE7AC; ": {}"
0x1801ca8ed  lea     rax, [rbp+57h+var_90]
0x1801ca8f1  mov     r8d, edi
0x1801ca8f4  mov     dl, r13b
0x1801ca8f7  mov     qword ptr [rsp+120h+var_100], rax; int
0x1801ca8fc  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801ca901  mov     edx, 1D4h; void *
0x1801ca906  mov     rcx, [rbp+5Fh]; this
0x1801ca90a  lea     r8, aOnecoreBaseCbs_69; "onecore\\base\\cbs\\core\\cbssessionope"...
0x1801ca911  mov     r9d, ebx; char *
0x1801ca914  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801ca919  jmp     loc_1801CACA1
0x1801ca91e  mov     ecx, [rsi+1Ch]
0x1801ca921  mov     edi, 3
0x1801ca926  sub     ecx, 2
0x1801ca929  jz      loc_1801CA9C4
0x1801ca92f  sub     ecx, r13d
0x1801ca932  jz      loc_1801CA9C4
0x1801ca938  cmp     ecx, edi
0x1801ca93a  jz      loc_1801CA9C4
0x1801ca940  cmp     cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA, r12; LogAdapter::Logger * LogAdapter::g_Logger
0x1801ca947  mov     ebx, 80070057h
0x1801ca94c  mov     [rbp+57h+var_A0], ebx
0x1801ca94f  jz      short loc_1801CA9BA
0x1801ca951  mov     ecx, [rsi+18h]
0x1801ca954  call    ?CbsStateToString@@YAPEB_WW4CbsState@@@Z; CbsStateToString(CbsState)
0x1801ca959  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801ca960  lea     r9, aInvalidTargetS; "Invalid target state: {} action: {} for"...
0x1801ca967  mov     qword ptr [rbp+57h+var_90], rax
0x1801ca96b  mov     r8d, edi
0x1801ca96e  lea     rax, [rbp+57h+var_B0]
0x1801ca972  xor     edx, edx
0x1801ca974  mov     [rsp+120h+var_F0], rax
0x1801ca979  lea     rax, [rbp+57h+var_A8]
0x1801ca97d  mov     [rsp+120h+var_F8], rax
0x1801ca982  lea     rax, [rbp+57h+var_90]
0x1801ca986  mov     qword ptr [rsp+120h+var_100], rax
0x1801ca98b  call    ??$LogNumObjects@PEB_WVAutoScz@@PEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBVAutoScz@@AEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,AutoScz,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,AutoScz const &,wchar_t * const &)
0x1801ca990  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801ca997  lea     rax, [rbp+57h+var_A0]
0x1801ca99b  mov     [rbp+57h+var_C0], rax
0x1801ca99f  lea     r9, asc_1802EE7AC; ": {}"
0x1801ca9a6  lea     rax, [rbp+57h+var_C0]
0x1801ca9aa  mov     r8d, edi
0x1801ca9ad  mov     dl, r13b
0x1801ca9b0  mov     qword ptr [rsp+120h+var_100], rax
0x1801ca9b5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801ca9ba  mov     edx, 1E0h
0x1801ca9bf  jmp     loc_1801CA906
0x1801ca9c4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801ca9cb  test    rcx, rcx
0x1801ca9ce  jz      short loc_1801CA9F4
0x1801ca9d0  lea     rax, [rbp+57h+var_B0]
0x1801ca9d4  mov     r8d, r13d
0x1801ca9d7  mov     [rsp+120h+var_F8], rax
0x1801ca9dc  lea     r9, aCapability_2; "{} capability: {}"
0x1801ca9e3  lea     rax, [rbp+57h+var_A8]
0x1801ca9e7  mov     dl, r13b
0x1801ca9ea  mov     qword ptr [rsp+120h+var_100], rax
0x1801ca9ef  call    ??$LogNumObjects@PEB_WPEA_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_WAEBQEA_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &,wchar_t * const &)
0x1801ca9f4  mov     [rbp+57h+var_C0], r12
0x1801ca9f8  test    rbx, rbx
0x1801ca9fb  jnz     short loc_1801CAA02
0x1801ca9fd  lea     ecx, [rbx+8]
0x1801caa00  int     29h; Win8: RtlFailFast(ecx)
0x1801caa02  mov     r15, [rbp+57h+var_58]
0x1801caa06  lea     rcx, [rbp+57h+var_C0]
0x1801caa0a  mov     rbx, [r15]
0x1801caa0d  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801caa12  mov     r8, [r14+468h]
0x1801caa19  mov     r9d, 2Dh ; '-'
0x1801caa1f  mov     rdx, r14
0x1801caa22  mov     qword ptr [rsp+120h+var_100], rax
0x1801caa27  mov     rcx, rbx
0x1801caa2a  call    ?GetProperty@CCbsCapability@@QEAAJPEAVCCbsSession@@PEAXW4_CbsPackageProperty@@PEAPEA_W@Z; CCbsCapability::GetProperty(CCbsSession *,void *,_CbsPackageProperty,wchar_t * *)
0x1801caa2f  test    eax, eax
0x1801caa31  js      loc_1801CACD4
0x1801caa37  mov     rax, [rbp+57h+var_C0]
0x1801caa3b  test    rax, rax
0x1801caa3e  jz      loc_1801CACD4
0x1801caa44  cmp     r12w, [rax]
0x1801caa48  jz      loc_1801CACD4
0x1801caa4e  mov     rbx, [r15]
0x1801caa51  lea     rcx, [rbp+57h+pv]
0x1801caa55  mov     qword ptr [rbp+57h+var_90], r12
0x1801caa59  mov     [rbp+57h+pv], r12
0x1801caa5d  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801caa62  mov     r8, [r14+468h]
0x1801caa69  mov     r9d, r13d
0x1801caa6c  mov     rdx, r14
0x1801caa6f  mov     qword ptr [rsp+120h+var_100], rax
0x1801caa74  mov     rcx, rbx
0x1801caa77  call    ?GetProperty@CCbsCapability@@QEAAJPEAVCCbsSession@@PEAXW4_CbsPackageProperty@@PEAPEA_W@Z; CCbsCapability::GetProperty(CCbsSession *,void *,_CbsPackageProperty,wchar_t * *)
0x1801caa7c  mov     ebx, eax
0x1801caa7e  test    eax, eax
0x1801caa80  jns     loc_1801CAB35
0x1801caa86  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801caa8d  mov     [rbp+57h+var_A0], eax
0x1801caa90  test    rcx, rcx
0x1801caa93  jz      short loc_1801CAAD9
0x1801caa95  lea     rax, [rbp+57h+var_B0]
0x1801caa99  mov     r8d, edi
0x1801caa9c  lea     r9, aUnableToDeterm_4; "Unable to determine package identity fo"...
0x1801caaa3  mov     qword ptr [rsp+120h+var_100], rax
0x1801caaa8  xor     edx, edx
0x1801caaaa  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1801caaaf  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801caab6  lea     rax, [rbp+57h+var_A0]
0x1801caaba  mov     qword ptr [rbp+57h+var_B8], rax
0x1801caabe  lea     r9, asc_1802EE7AC; ": {}"
0x1801caac5  lea     rax, [rbp+57h+var_B8]
0x1801caac9  mov     r8d, edi
0x1801caacc  mov     dl, r13b
0x1801caacf  mov     qword ptr [rsp+120h+var_100], rax; int
0x1801caad4  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1801caad9  mov     edx, 1F4h; void *
0x1801caade  mov     rcx, [rbp+5Fh]; this
0x1801caae2  lea     r8, aOnecoreBaseCbs_69; "onecore\\base\\cbs\\core\\cbssessionope"...
0x1801caae9  mov     r9d, ebx; char *
0x1801caaec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801caaf1  mov     rcx, [rbp+57h+pv]; pv
0x1801caaf5  test    rcx, rcx
0x1801caaf8  jz      short loc_1801CAB0A
0x1801caafa  call    cs:__imp_CoTaskMemFree
0x1801cab01  nop     dword ptr [rax+rax+00h]
0x1801cab06  mov     [rbp+57h+pv], r12
0x1801cab0a  lea     rcx, [rbp+57h+var_90]
0x1801cab0e  call    ?Close@?$AutoComPtr@VCCbsDriverDeployment@@@Windows@@QEAAXXZ; Windows::AutoComPtr<CCbsDriverDeployment>::Close(void)
0x1801cab13  mov     rcx, [rbp+57h+var_C0]; pv
0x1801cab17  test    rcx, rcx
0x1801cab1a  jz      loc_1801CACA1
0x1801cab20  call    cs:__imp_CoTaskMemFree
0x1801cab27  nop     dword ptr [rax+rax+00h]
0x1801cab2c  mov     [rbp+57h+var_C0], r12
0x1801cab30  jmp     loc_1801CACA1
0x1801cab35  lea     rcx, [rbp+57h+var_90]
0x1801cab39  call    ?GetInitPointer@?$AutoGenericHandleBase@PEAX$0A@V?$AutoGenericHandle@PEAX$0A@$1?CloseBcdStore@@YAXPEAX@Z@Windows@@@Windows@@QEAAPEAPEAXXZ; Windows::AutoGenericHandleBase<void *,0,Windows::AutoGenericHandle<void *,0,&CloseBcdStore(void *)>>::GetInitPointer(void)
0x1801cab3e  mov     rdx, [rbp+57h+pv]; wchar_t *
0x1801cab42  mov     r9, rax; struct CCbsPackage **
0x1801cab45  mov     r8d, r13d; int
0x1801cab48  mov     [rsp+120h+var_100], r13d; int
0x1801cab4d  mov     rcx, r14; this
0x1801cab50  call    ?ResolvePackageByFullName@CCbsSession@@QEAAJPEB_WHPEAPEAVCCbsPackage@@H@Z; CCbsSession::ResolvePackageByFullName(wchar_t const *,int,CCbsPackage * *,int)
0x1801cab55  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1801cab5c  mov     ebx, eax
0x1801cab5e  test    eax, eax
0x1801cab60  jns     short loc_1801CABBC
0x1801cab62  mov     [rbp+57h+var_A0], eax
0x1801cab65  test    rcx, rcx
0x1801cab68  jz      short loc_1801CABB2
0x1801cab6a  lea     rax, [rbp+57h+var_B0]
0x1801cab6e  mov     [rsp+120h+var_F8], rax
0x1801cab73  lea     r9, aFailedToResolv_1; "Failed to resolve package identity '{}'"...
  ... truncated ...
```
