# DiscoverApi::BeginRepairJoinInfo(_DSREG_JOIN_TYPE,ushort const *,ushort const * *,ulong,ushort const *,void (*)(struct_dsreg_server_response,unsigned __int64,long),unsigned __int64)

- ea: `0x180092f6c`
- end: `0x1800937e1`
- name: `?BeginRepairJoinInfo@DiscoverApi@@SAJW4_DSREG_JOIN_TYPE@@PEBGPEAPEBGK1P6AXUstruct_dsreg_server_response@@_KJ@Z4@Z`
- size: `2165`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `file_ops, authz_impersonation, registry_config, installer_update`

## callers

- `0x18009433c`

## callees

- `0x180001cfc`
- `0x180002380`
- `0x1800024bc`
- `0x180003c44`
- `0x180005f24`
- `0x18001a8fc`
- `0x18007cc30`
- `0x180084f3c`
- `0x180085628`
- `0x180085c44`
- `0x1800871b4`
- `0x180087468`
- `0x180088388`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aa9c`
- `0x18008aad8`
- `0x18008ab14`
- `0x18008aba4`
- `0x18008b1b8`
- `0x1800929a0`
- `0x1800929f8`
- `0x180092f6c`
- `0x180093e80`
- `0x180094104`
- `0x18009d31c`
- `0x18009d69c`
- `0x18009e72c`
- `0x18009e8a8`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800930b8`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800930b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009375e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093766`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009375e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180093766`
- `popkeycli!NgcGetSymmetricPopKeyTransportKey` at `0x18009325a`
- `popkeycli!NgcGetSymmetricPopKeyTransportKey` at `0x18009325a`

## string_xrefs

- `0x1800934bd`: `CopyStringNullSafeW`
- `0x180092fbc`: `DiscoverApi::BeginRepairJoinInfo`
- `0x18009319a`: `DiscoverApi::BeginRepairJoinInfo`
- `0x1800931ec`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180093268`: `DiscoverApi::BeginRepairJoinInfo`
- `0x1800932c0`: `DiscoverApi::BeginRepairJoinInfo`
- `0x18009339b`: `DiscoverApi::BeginRepairJoinInfo`
- `0x1800933d6`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180093443`: `DiscoverApi::BeginRepairJoinInfo`
- `0x18009349a`: `DiscoverApi::BeginRepairJoinInfo`
- `0x1800934fa`: `DiscoverApi::BeginRepairJoinInfo`
- `0x18009351b`: `DiscoverApi::BeginRepairJoinInfo`
- `0x18009362d`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180093666`: `DiscoverApi::BeginRepairJoinInfo`
- `0x1800936b6`: `DiscoverApi::BeginRepairJoinInfo`
- `0x180093711`: `DiscoverApi::BeginRepairJoinInfo`
- `0x1800937ac`: `DiscoverApi::BeginRepairJoinInfo`
- `0x1800931f3`: `%s: Multiple (%lu) join certificates found for the given tenant. Only the first one will be repaired. JoinType: %d(%s), TenantId: %s.`
- `0x180093299`: `%s: Cannot get existing transport key. Unable to repair transport key type. NgcGetSymmetricPopKeyTransportKey failed with error code 0x%08x. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Key type: %d, Flags: %lu.`
- `0x1800932c7`: `%s: ConvertKeyStatusToDwordKeyType failed with error code 0x%08x. Unable to repair transport key type.`
- `0x180093475`: `%s: GetAutoJoinDomainConfiguration failed with error code: 0x%08x. Unable to recover DJ++ user email.`
- `0x1800933cc`: `GetAutoJoinDomainConfiguration`
- `0x180093718`: `%s: No need to repair join info. Calling callback function...`
- `0x18009363d`: `%s: Repair join info operation started successfully. Tenant ID: "%s", Device ID: "%s", Join type: %d, UPN: "%s", UPN Count: %lu, Request ID: "%s".`
- `0x1800936c2`: `%s: Failed to start repair join info operation with error code: 0x%08x. Tenant ID: "%s", Join type: %d, UPN: "%s", UPN Count: %lu, Request ID: "%s".`

## pseudocode

```c
__int64 __fastcall DiscoverApi::BeginRepairJoinInfo(
        int a1,
        __int64 a2,
        const unsigned __int16 **a3,
        int a4,
        unsigned int a5,
        const WCHAR *a6,
        __int64 a7)
{
  const WCHAR *JoinTypeName; // rbx
  void *v9; // rdi
  char *v10; // rax
  char *v11; // rsi
  const unsigned __int16 *v12; // r12
  __int64 v13; // r14
  char *v14; // r15
  char v15; // al
  int v16; // r8d
  __int64 v17; // rdx
  __int64 v18; // rcx
  int JoinInfo; // eax
  unsigned int v20; // ebx
  const unsigned __int16 *v21; // r8
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int128 v25; // rcx
  __int64 v26; // r8
  int SymmetricPopKeyTransportKey; // eax
  int v28; // eax
  enum _DSR_INSTANCE *v29; // r9
  __int64 v30; // rax
  __int64 v31; // rcx
  int v32; // r8d
  int AutoJoinDomainConfiguration; // eax
  const wchar_t *v34; // r8
  int v35; // r15d
  int v36; // eax
  unsigned __int16 **v37; // rcx
  enum _DSR_INSTANCE *v38; // r9
  int v39; // eax
  int v40; // eax
  int FakeUserEmail; // eax
  __int64 v42; // r9
  int v43; // r13d
  int v44; // r14d
  const unsigned __int16 *v45; // rax
  __int64 v47; // [rsp+20h] [rbp-E0h]
  __int64 v48; // [rsp+20h] [rbp-E0h]
  __int64 v49; // [rsp+30h] [rbp-D0h]
  __int64 v50; // [rsp+40h] [rbp-C0h]
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v52; // [rsp+68h] [rbp-98h] BYREF
  __int64 v53; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v54; // [rsp+78h] [rbp-88h] BYREF
  int v55; // [rsp+80h] [rbp-80h] BYREF
  int v56; // [rsp+84h] [rbp-7Ch] BYREF
  const WCHAR *v57; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v58; // [rsp+90h] [rbp-70h] BYREF
  const WCHAR *v59; // [rsp+98h] [rbp-68h] BYREF
  HLOCAL hMem; // [rsp+A0h] [rbp-60h] BYREF
  const wchar_t *v61; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v62; // [rsp+B0h] [rbp-50h]
  const WCHAR *v63; // [rsp+C0h] [rbp-40h] BYREF
  const WCHAR *v64; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v65; // [rsp+D0h] [rbp-30h]
  __int128 v66; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v67; // [rsp+F0h] [rbp-10h]
  __int128 v68; // [rsp+100h] [rbp+0h]
  __int64 v69; // [rsp+110h] [rbp+10h]
  __int64 v70; // [rsp+120h] [rbp+20h] BYREF
  __int128 v71; // [rsp+128h] [rbp+28h]
  int v72; // [rsp+190h] [rbp+90h] BYREF
  __int64 v73; // [rsp+198h] [rbp+98h] BYREF
  int v74; // [rsp+1A8h] [rbp+A8h]

  v74 = a4;
  v73 = a2;
  v72 = a1;
  JoinTypeName = (const WCHAR *)GetJoinTypeName(1);
  v57 = JoinTypeName;
  Logger::TraceVerbose(
    L"%s started. joinType: %d(%s), tenantId: %s, clientRequestId: %s.",
    L"DiscoverApi::BeginRepairJoinInfo",
    1,
    JoinTypeName,
    &base,
    &base);
  v70 = 1;
  Block = 0;
  v65 = 0;
  v69 = 0;
  v72 = 1;
  v61 = L"login.windows.net";
  LODWORD(v73) = 0;
  v71 = 0;
  a5 = 0;
  v9 = 0;
  v66 = 0;
  v54 = 0;
  v67 = 0;
  hMem = 0;
  v68 = 0;
  v56 = 0;
  v62 = 0;
  v58 = 0;
  v52 = 0;
  LODWORD(a6) = 0;
  v10 = (char *)operator new[](0x28u, (const struct std::nothrow_t *)std::nothrow);
  v53 = (__int64)v10;
  v11 = v10;
  if ( !v10 )
  {
    v11 = 0;
    v20 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DiscoverApi::BeginRepairJoinInfo");
    goto LABEL_66;
  }
  *(_DWORD *)v10 = 0;
  v10[4] = 0;
  v12 = 0;
  if ( (unsigned int)dword_1800E5118 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800E5118, 0x400000000000LL) )
  {
    v13 = (__int64)(v11 + 8);
    EventActivityIdControl(3u, (LPGUID)(v11 + 8));
  }
  else
  {
    v13 = (__int64)(v11 + 8);
    *(_OWORD *)(v11 + 8) = 0;
  }
  v14 = v11;
  *(_DWORD *)v11 = 1;
  if ( (unsigned int)dword_1800E5118 > 5 )
  {
    v15 = tlgKeywordOn(&dword_1800E5118, 0x400000000000LL);
    v17 = 0;
    if ( v15 )
    {
      v63 = JoinTypeName;
      v55 = v16;
      v64 = 0;
      v59 = 0;
      v53 = 16779264;
      if ( !v11[4] || _tlgGuidIsZero((const struct _GUID *)(v11 + 24)) )
        v18 = v17;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        (__int64)&dword_1800E5118,
        (__int64)&dword_1800D32A4,
        v13,
        v18,
        (__int64)&v53,
        &v59,
        &v64,
        (__int64)&v55,
        &v63);
    }
  }
  JoinInfo = DsrGetJoinInfoEx(3, &v70, &Block);
  v20 = JoinInfo;
  if ( JoinInfo < 0 )
  {
    v21 = L"DsrGetJoinInfoEx";
LABEL_14:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"DiscoverApi::BeginRepairJoinInfo",
      v21,
      (unsigned int)JoinInfo);
LABEL_56:
    *(_DWORD *)v11 = 2;
    if ( (unsigned int)dword_1800E5118 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800E5118, 0x400000000000LL) )
    {
      a6 = v57;
      v72 = 1;
      v53 = 0;
      v59 = 0;
      a5 = v20;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        (__int64)&dword_1800E5118,
        (__int64)&word_1800D3346,
        v13,
        v42,
        (__int64)&a5,
        &v59,
        (const WCHAR **)&v53,
        (__int64)&v72,
        &a6);
    }
    v35 = 1;
    if ( (v20 & 0x80000000) == 0 )
      goto LABEL_60;
LABEL_67:
    v44 = v74;
    Logger::WriteBeginRepairJoinInfoFailureEvent(v20, v22, v24, a3, v74);
    if ( a3 && v44 )
      v45 = *a3;
    else
      v45 = 0;
    LODWORD(v49) = v44;
    LODWORD(v48) = 1;
    Logger::TraceError(
      L"%s: Failed to start repair join info operation with error code: 0x%08x. Tenant ID: \"%s\", Join type: %d, UPN: \"%"
       "s\", UPN Count: %lu, Request ID: \"%s\".",
      L"DiscoverApi::BeginRepairJoinInfo",
      v20,
      0,
      v48,
      v45,
      v49,
      0);
    if ( (v20 & 0x80000000) != 0 )
      goto LABEL_74;
    goto LABEL_72;
  }
  *((_QWORD *)&v25 + 1) = 0;
  if ( !Block || (v26 = *((unsigned int *)Block + 4), !(_DWORD)v26) || !*((_QWORD *)Block + 1) )
  {
    Logger::TraceError(
      L"%s: Device is not joined. TenantID: %s, JoinType: %d(%s).",
      L"DiscoverApi::BeginRepairJoinInfo",
      0,
      1,
      v57);
    v20 = -2145647536;
    goto LABEL_56;
  }
  if ( (unsigned int)v26 > 1 )
    Logger::TraceWarning(
      L"%s: Multiple (%lu) join certificates found for the given tenant. Only the first one will be repaired. JoinType: %d"
       "(%s), TenantId: %s.",
      L"DiscoverApi::BeginRepairJoinInfo",
      v26,
      1,
      v57,
      0);
  *(_QWORD *)&v25 = *((_QWORD *)v61 + 4);
  v62 = v25;
  SymmetricPopKeyTransportKey = NgcGetSymmetricPopKeyTransportKey(&v61, 0, 0, 6, &hMem, &v56, 0, 0, 0, 0, &v73);
  if ( SymmetricPopKeyTransportKey >= 0 )
  {
    v28 = ConvertKeyStatusToDwordKeyType((unsigned int)v73, &a5);
    if ( v28 < 0 )
      Logger::TraceWarning(
        L"%s: ConvertKeyStatusToDwordKeyType failed with error code 0x%08x. Unable to repair transport key type.",
        L"DiscoverApi::BeginRepairJoinInfo",
        (unsigned int)v28);
  }
  else
  {
    LODWORD(v50) = 6;
    Logger::TraceWarning(
      L"%s: Cannot get existing transport key. Unable to repair transport key type. NgcGetSymmetricPopKeyTransportKey fail"
       "ed with error code 0x%08x. SID: %s, IDP domain: %s, Tenant domain: %s, User ID: %s, Key type: %d, Flags: %lu.",
      L"DiscoverApi::BeginRepairJoinInfo",
      (unsigned int)SymmetricPopKeyTransportKey,
      0,
      v61,
      v62,
      0,
      v50);
  }
  if ( a3 && v74 )
    v12 = *a3;
  JoinInfo = StringDup(*(const unsigned __int16 **)(*((_QWORD *)Block + 1) + 16LL), &v54, 0);
  v20 = JoinInfo;
  if ( JoinInfo < 0 )
  {
    v21 = L"StringDup";
    goto LABEL_14;
  }
  v9 = operator new[](0x30u, (const struct std::nothrow_t *)std::nothrow);
  v53 = (__int64)v9;
  if ( !v9 )
  {
    v9 = 0;
    v20 = -2147024882;
    Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"DiscoverApi::BeginRepairJoinInfo");
    goto LABEL_56;
  }
  *(_QWORD *)v9 = 0;
  v11 = 0;
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 2) = 0;
  *((_DWORD *)v9 + 6) = 0;
  *((_QWORD *)v9 + 4) = 0;
  *((_QWORD *)v9 + 5) = 0;
  *(_QWORD *)v9 = RepairJoinInfoCallback;
  *((_QWORD *)v9 + 1) = a7;
  *((_DWORD *)v9 + 6) = a5;
  *((_QWORD *)v9 + 4) = Block;
  Block = 0;
  v30 = *((_QWORD *)v9 + 4);
  *((_QWORD *)v9 + 5) = v14;
  v31 = *(_QWORD *)(v30 + 8);
  v32 = *(_DWORD *)(v31 + 60);
  if ( v32 )
  {
    if ( v32 != 1 )
    {
      Logger::TraceError(L"%s: Unsupported DSR instance %d", L"DiscoverApi::BeginRepairJoinInfo");
      v20 = -2147024809;
LABEL_66:
      v35 = v72;
      goto LABEL_67;
    }
    AutoJoinDomainConfiguration = GetAutoJoinDomainConfiguration((unsigned __int16 **)v31, &v52, &v58, v29);
    v20 = AutoJoinDomainConfiguration;
    if ( AutoJoinDomainConfiguration < 0 )
    {
      v34 = L"GetAutoJoinDomainConfiguration";
LABEL_35:
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"DiscoverApi::BeginRepairJoinInfo",
        v34,
        (unsigned int)AutoJoinDomainConfiguration);
      goto LABEL_66;
    }
    AutoJoinDomainConfiguration = MakeFakeUserEmail(v52, (unsigned __int16 **)v9 + 2);
    v20 = AutoJoinDomainConfiguration;
    if ( AutoJoinDomainConfiguration < 0 )
    {
      v34 = L"MakeFakeUserEmail";
      goto LABEL_35;
    }
    AutoJoinDomainConfiguration = DsrBeginDiscoverEnterprise(v58);
    v20 = AutoJoinDomainConfiguration;
    if ( AutoJoinDomainConfiguration < 0 )
    {
      v34 = L"DsrBeginDiscoverEnterprise";
      goto LABEL_35;
    }
  }
  else
  {
    v36 = IsLocalMachineDomainJoined((int *)&a6, 0);
    if ( v36 >= 0 )
    {
      v39 = (int)a6;
    }
    else
    {
      Logger::TraceWarning(
        L"%s: IsLocalMachineDomainJoined failed with error code: 0x%08x. Assuming the device is not AD domain joined.",
        L"DiscoverApi::BeginRepairJoinInfo",
        (unsigned int)v36);
      v39 = 0;
    }
    if ( v39 )
    {
      v40 = GetAutoJoinDomainConfiguration(v37, &v52, 0, v38);
      if ( v40 >= 0 )
      {
        FakeUserEmail = MakeFakeUserEmail(v52, (unsigned __int16 **)v9 + 2);
        if ( FakeUserEmail < 0 )
          Logger::TraceWarning(
            L"%s: MakeFakeUserEmail failed with error code: 0x%08x. Unable to recover DJ++ user email.",
            L"DiscoverApi::BeginRepairJoinInfo",
            (unsigned int)FakeUserEmail);
      }
      else
      {
        Logger::TraceWarning(
          L"%s: GetAutoJoinDomainConfiguration failed with error code: 0x%08x. Unable to recover DJ++ user email.",
          L"DiscoverApi::BeginRepairJoinInfo",
          (unsigned int)v40);
      }
    }
    if ( !*((_QWORD *)v9 + 2) )
    {
      AutoJoinDomainConfiguration = CopyStringNullSafeW(v12, (unsigned __int16 **)v9 + 2);
      v20 = AutoJoinDomainConfiguration;
      if ( AutoJoinDomainConfiguration < 0 )
      {
        v34 = L"CopyStringNullSafeW";
        goto LABEL_35;
      }
    }
    AutoJoinDomainConfiguration = DsrBeginDiscoverEx(*(unsigned __int16 **)(*(_QWORD *)(*((_QWORD *)v9 + 4) + 8LL) + 32LL));
    v20 = AutoJoinDomainConfiguration;
    if ( AutoJoinDomainConfiguration < 0 )
    {
      v34 = L"DsrBeginDiscover";
      goto LABEL_35;
    }
  }
  v35 = 0;
LABEL_60:
  if ( !v12 && a3 && v74 )
    v12 = *a3;
  v43 = v74;
  Logger::WriteBeginRepairJoinInfoSuccessEvent(v23, v54, v24, v12, v74);
  LODWORD(v49) = v43;
  LODWORD(v47) = 1;
  Logger::TraceVerbose(
    L"%s: Repair join info operation started successfully. Tenant ID: \"%s\", Device ID: \"%s\", Join type: %d, UPN: \"%s\""
     ", UPN Count: %lu, Request ID: \"%s\".",
    L"DiscoverApi::BeginRepairJoinInfo",
    0,
    v54,
    v47,
    v12,
    v49,
    0);
LABEL_72:
  if ( !v35 )
    goto LABEL_76;
  Logger::WriteRepairJoinInfoCallbackSuccessEvent(
    0,
    *(_QWORD *)(*((_QWORD *)Block + 1) + 16LL),
    *(_QWORD *)(*((_QWORD *)Block + 1) + 40LL),
    1,
    &v66);
  Logger::TraceVerbose(
    L"%s: No need to repair join info. Calling callback function...",
    L"DiscoverApi::BeginRepairJoinInfo");
  v69 = v65;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  RepairJoinInfoCallback(&v66, a7, v20);
LABEL_74:
  if ( v9 )
    _JOIN_INFO_REPAIR_CALLBACK_CONTEXT::`scalar deleting destructor'((void **)v9);
LABEL_76:
  LocalFree(hMem);
  LocalFree(0);
  DsrFreeJoinInfoEx(Block);
  if ( v11 )
    TraceLoggingActivity<&_tlgProvider_t const * const g_hcdjTraceLoggingProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>::`scalar deleting destructor'(v11);
  SafeFree(v54);
  operator delete(v52, (const struct std::nothrow_t *)2);
  operator delete(v58, (const struct std::nothrow_t *)2);
  Logger::TraceVerbose(L"%s - hr: 0x%08x", L"DiscoverApi::BeginRepairJoinInfo", v20);
  return v20;
}

```

## disassembly

```asm
0x180092f6c  mov     rax, rsp
0x180092f6f  mov     [rax+18h], rbx
0x180092f73  mov     [rax+20h], r9d
0x180092f77  mov     [rax+10h], rdx
0x180092f7b  mov     [rax+8], ecx
0x180092f7e  push    rbp
0x180092f7f  push    rsi
0x180092f80  push    rdi
0x180092f81  push    r12
0x180092f83  push    r13
0x180092f85  push    r14
0x180092f87  push    r15
0x180092f89  lea     rbp, [rsp-50h]
0x180092f8e  sub     rsp, 150h
0x180092f95  mov     ecx, 1
0x180092f9a  movaps  xmmword ptr [rax-48h], xmm6
0x180092f9e  mov     r13, r8
0x180092fa1  call    ?GetJoinTypeName@@YAPEBGW4_DSREG_JOIN_TYPE@@@Z; GetJoinTypeName(_DSREG_JOIN_TYPE)
0x180092fa6  mov     rbx, rax
0x180092fa9  mov     [rbp+80h+var_F8], rax
0x180092fad  lea     rax, base
0x180092fb4  mov     r9, rbx
0x180092fb7  mov     qword ptr [rsp+180h+var_158], rax
0x180092fbc  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x180092fc3  mov     r8d, 1
0x180092fc9  mov     [rsp+180h+var_160], rax
0x180092fce  lea     rcx, aSStartedJointy; "%s started. joinType: %d(%s), tenantId:"...
0x180092fd5  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180092fda  xor     r14d, r14d
0x180092fdd  mov     [rbp+80h+var_60], 1
0x180092fe5  xor     eax, eax
0x180092fe7  mov     [rsp+180h+Block], r14
0x180092fec  xorps   xmm6, xmm6
0x180092fef  mov     [rbp+80h+var_B0], rax
0x180092ff3  xorps   xmm0, xmm0
0x180092ff6  mov     [rbp+80h+var_70], rax
0x180092ffa  lea     rax, aLoginWindowsNe; "login.windows.net"
0x180093001  mov     [rbp+80h+arg_0], 1
0x18009300b  lea     ecx, [r14+28h]; unsigned __int64
0x18009300f  mov     [rbp+80h+var_D8], rax
0x180093013  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009301a  mov     dword ptr [rbp+80h+arg_8], r14d
0x180093021  movdqu  [rbp+80h+var_58], xmm0
0x180093026  mov     [rbp+80h+arg_20], r14d
0x18009302d  mov     edi, r14d
0x180093030  movups  [rbp+80h+var_A0], xmm6
0x180093034  mov     [rsp+180h+var_108], r14
0x180093039  movups  [rbp+80h+var_90], xmm6
0x18009303d  mov     [rbp+80h+hMem], r14
0x180093041  movups  [rbp+80h+var_80], xmm6
0x180093045  mov     [rbp+80h+var_FC], r14d
0x180093049  movdqu  [rbp+80h+var_D0], xmm0
0x18009304e  mov     [rbp+80h+var_F0], r14
0x180093052  mov     [rsp+180h+var_118], r14
0x180093057  mov     dword ptr [rbp+80h+arg_28], r14d
0x18009305e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180093063  mov     [rsp+180h+var_110], rax
0x180093068  mov     rsi, rax
0x18009306b  test    rax, rax
0x18009306e  jz      loc_180093663
0x180093074  mov     [rax], r14d
0x180093077  mov     [rax+4], r14b
0x18009307b  test    rax, rax
0x18009307e  jz      loc_180093666
0x180093084  mov     eax, cs:dword_1800E5118
0x18009308a  mov     r12d, r14d
0x18009308d  cmp     eax, 5
0x180093090  jbe     short loc_1800930C0
0x180093092  mov     rdx, 400000000000h
0x18009309c  lea     rcx, dword_1800E5118
0x1800930a3  call    _tlgKeywordOn
0x1800930a8  test    al, al
0x1800930aa  jz      short loc_1800930C0
0x1800930ac  lea     r14, [rsi+8]
0x1800930b0  mov     rdx, r14; ActivityId
0x1800930b3  lea     ecx, [r12+3]; ControlCode
0x1800930b8  call    cs:__imp_EventActivityIdControl
0x1800930be  jmp     short loc_1800930CB
0x1800930c0  lea     r14, [rsi+8]
0x1800930c4  xorps   xmm0, xmm0
0x1800930c7  movups  xmmword ptr [r14], xmm0
0x1800930cb  mov     r8d, 1
0x1800930d1  mov     r15, rsi
0x1800930d4  mov     [rsi], r8d
0x1800930d7  mov     eax, cs:dword_1800E5118
0x1800930dd  cmp     eax, 5
0x1800930e0  jbe     loc_180093177
0x1800930e6  mov     rdx, 400000000000h
0x1800930f0  lea     rcx, dword_1800E5118
0x1800930f7  call    _tlgKeywordOn
0x1800930fc  xor     edx, edx
0x1800930fe  test    al, al
0x180093100  jz      short loc_180093177
0x180093102  mov     [rbp+80h+var_C0], rbx
0x180093106  mov     [rbp+80h+var_100], r8d
0x18009310a  mov     [rbp+80h+var_B8], rdx
0x18009310e  mov     [rbp+80h+var_E8], rdx
0x180093112  mov     [rsp+180h+var_110], 1000800h
0x18009311b  cmp     [rsi+4], dl
0x18009311e  jz      short loc_18009312D
0x180093120  lea     rcx, [rsi+18h]; struct _GUID *
0x180093124  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180093129  test    al, al
0x18009312b  jz      short loc_180093130
0x18009312d  mov     rcx, rdx
0x180093130  lea     rax, [rbp+80h+var_C0]
0x180093134  mov     r9, rcx
0x180093137  mov     [rsp+180h+var_140], rax
0x18009313c  lea     rdx, dword_1800D32A4
0x180093143  lea     rax, [rbp+80h+var_100]
0x180093147  mov     r8, r14
0x18009314a  mov     [rsp+180h+var_148], rax
0x18009314f  lea     rcx, dword_1800E5118
0x180093156  lea     rax, [rbp+80h+var_B8]
0x18009315a  mov     qword ptr [rsp+180h+var_158+8], rax
0x18009315f  lea     rax, [rbp+80h+var_E8]
0x180093163  mov     qword ptr [rsp+180h+var_158], rax
0x180093168  lea     rax, [rsp+180h+var_110]
0x18009316d  mov     [rsp+180h+var_160], rax
0x180093172  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180093177  lea     r8, [rsp+180h+Block]
0x18009317c  mov     ecx, 3
0x180093181  lea     rdx, [rbp+80h+var_60]
0x180093185  call    DsrGetJoinInfoEx
0x18009318a  mov     ebx, eax
0x18009318c  test    eax, eax
0x18009318e  jns     short loc_1800931B2
0x180093190  lea     r8, aDsrgetjoininfo; "DsrGetJoinInfoEx"
0x180093197  mov     r9d, eax
0x18009319a  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x1800931a1  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x1800931a8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800931ad  jmp     loc_180093541
0x1800931b2  mov     rax, [rsp+180h+Block]
0x1800931b7  xor     ebx, ebx
0x1800931b9  test    rax, rax
0x1800931bc  jz      loc_180093517
0x1800931c2  mov     r8d, [rax+10h]
0x1800931c6  test    r8d, r8d
0x1800931c9  jz      loc_180093517
0x1800931cf  cmp     [rax+8], rbx
0x1800931d3  jz      loc_180093517
0x1800931d9  cmp     r8d, 1
0x1800931dd  jbe     short loc_180093209
0x1800931df  mov     rax, [rbp+80h+var_F8]
0x1800931e3  lea     r9d, [rbx+1]
0x1800931e7  mov     qword ptr [rsp+180h+var_158], rbx
0x1800931ec  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x1800931f3  lea     rcx, aSMultipleLuJoi; "%s: Multiple (%lu) join certificates fo"...
0x1800931fa  mov     [rsp+180h+var_160], rax
0x1800931ff  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180093204  mov     rax, [rsp+180h+Block]
0x180093209  mov     rax, [rax+8]
0x18009320d  mov     r9d, 6
0x180093213  xor     r8d, r8d
0x180093216  xor     edx, edx
0x180093218  mov     rcx, [rax+20h]
0x18009321c  lea     rax, [rbp+80h+arg_8]
0x180093223  mov     [rsp+180h+var_130], rax
0x180093228  lea     rax, [rbp+80h+var_FC]
0x18009322c  mov     [rsp+180h+var_138], rbx
0x180093231  mov     [rsp+180h+var_140], rbx
0x180093236  mov     [rsp+180h+var_148], rbx
0x18009323b  mov     qword ptr [rsp+180h+var_158+8], rbx
0x180093240  mov     qword ptr [rsp+180h+var_158], rax
0x180093245  lea     rax, [rbp+80h+hMem]
0x180093249  mov     qword ptr [rbp+80h+var_D0], rcx
0x18009324d  lea     rcx, [rbp+80h+var_D8]
0x180093251  mov     [rsp+180h+var_160], rax
0x180093256  mov     qword ptr [rbp+80h+var_D0+8], rbx
0x18009325a  call    cs:__imp_NgcGetSymmetricPopKeyTransportKey
0x180093260  test    eax, eax
0x180093262  jns     short loc_1800932A7
0x180093264  mov     rcx, qword ptr [rbp+80h+var_D0+8]
0x180093268  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x18009326f  mov     dword ptr [rsp+180h+var_140], 6
0x180093277  xor     r9d, r9d
0x18009327a  mov     [rsp+180h+var_148], rbx
0x18009327f  mov     r8d, eax
0x180093282  mov     qword ptr [rsp+180h+var_158+8], rcx
0x180093287  mov     rcx, qword ptr [rbp+80h+var_D0]
0x18009328b  mov     qword ptr [rsp+180h+var_158], rcx
0x180093290  mov     rcx, [rbp+80h+var_D8]
0x180093294  mov     [rsp+180h+var_160], rcx
0x180093299  lea     rcx, aSCannotGetExis; "%s: Cannot get existing transport key. "...
0x1800932a0  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800932a5  jmp     short loc_1800932D3
0x1800932a7  mov     ecx, dword ptr [rbp+80h+arg_8]
0x1800932ad  lea     rdx, [rbp+80h+arg_20]
0x1800932b4  call    ?ConvertKeyStatusToDwordKeyType@@YAJW4_NGC_KEY_STATUS@@PEAK@Z; ConvertKeyStatusToDwordKeyType(_NGC_KEY_STATUS,ulong *)
0x1800932b9  test    eax, eax
0x1800932bb  jns     short loc_1800932D3
0x1800932bd  mov     r8d, eax
0x1800932c0  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x1800932c7  lea     rcx, aSConvertkeysta; "%s: ConvertKeyStatusToDwordKeyType fail"...
0x1800932ce  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800932d3  test    r13, r13
0x1800932d6  jz      short loc_1800932E4
0x1800932d8  cmp     [rbp+80h+arg_18], ebx
0x1800932de  jz      short loc_1800932E4
0x1800932e0  mov     r12, [r13+0]
0x1800932e4  mov     rax, [rsp+180h+Block]
0x1800932e9  lea     rdx, [rsp+180h+var_108]; unsigned __int16 **
0x1800932ee  xor     r8d, r8d; int
0x1800932f1  mov     rcx, [rax+8]
0x1800932f5  mov     rcx, [rcx+10h]; unsigned __int16 *
0x1800932f9  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x1800932fe  mov     ebx, eax
0x180093300  test    eax, eax
0x180093302  jns     short loc_180093310
0x180093304  lea     r8, aStringdup; "StringDup"
0x18009330b  jmp     loc_180093197
0x180093310  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180093317  mov     ecx, 30h ; '0'; unsigned __int64
0x18009331c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180093321  mov     rdi, rax
0x180093324  mov     [rsp+180h+var_110], rax
0x180093329  xor     eax, eax
0x18009332b  test    rdi, rdi
0x18009332e  jz      loc_1800934FA
0x180093334  mov     [rdi], rax
0x180093337  xor     esi, esi
0x180093339  mov     [rdi+8], rax
0x18009333d  mov     [rdi+10h], rax
0x180093341  mov     [rdi+18h], eax
0x180093344  mov     [rdi+20h], rax
0x180093348  mov     [rdi+28h], rax
0x18009334c  lea     rax, ?RepairJoinInfoCallback@@YAXUstruct_dsreg_server_response@@_KJ@Z; RepairJoinInfoCallback(struct_dsreg_server_response,unsigned __int64,long)
0x180093353  mov     [rdi], rax
0x180093356  mov     rax, [rbp+80h+arg_30]
0x18009335d  mov     [rdi+8], rax
0x180093361  mov     eax, [rbp+80h+arg_20]
0x180093367  mov     [rdi+18h], eax
0x18009336a  mov     rax, [rsp+180h+Block]
0x18009336f  mov     [rdi+20h], rax
0x180093373  mov     [rsp+180h+Block], 0
0x18009337c  mov     rax, [rdi+20h]
0x180093380  mov     [rdi+28h], r15
0x180093384  mov     rcx, [rax+8]; unsigned __int16 **
0x180093388  mov     r8d, [rcx+3Ch]
0x18009338c  test    r8d, r8d
0x18009338f  jz      loc_18009342E
0x180093395  cmp     r8d, 1
0x180093399  jz      short loc_1800933B8
0x18009339b  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x1800933a2  lea     rcx, aSUnsupportedDs; "%s: Unsupported DSR instance %d"
0x1800933a9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800933ae  mov     ebx, 80070057h
0x1800933b3  jmp     loc_18009367E
0x1800933b8  lea     r8, [rbp+80h+var_F0]; unsigned __int16 **
0x1800933bc  lea     rdx, [rsp+180h+var_118]; unsigned __int16 **
0x1800933c1  call    ?GetAutoJoinDomainConfiguration@@YAJPEAPEAG00PEAW4_DSR_INSTANCE@@@Z; GetAutoJoinDomainConfiguration(ushort * *,ushort * *,ushort * *,_DSR_INSTANCE *)
0x1800933c6  mov     ebx, eax
0x1800933c8  test    eax, eax
0x1800933ca  jns     short loc_1800933EE
0x1800933cc  lea     r8, aGetautojoindom; "GetAutoJoinDomainConfiguration"
0x1800933d3  mov     r9d, eax
0x1800933d6  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x1800933dd  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x1800933e4  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800933e9  jmp     loc_18009367E
0x1800933ee  mov     rcx, [rsp+180h+var_118]; unsigned __int16 *
0x1800933f3  lea     rdx, [rdi+10h]; unsigned __int16 **
0x1800933f7  call    ?MakeFakeUserEmail@@YAJPEBGPEAPEAG@Z; MakeFakeUserEmail(ushort const *,ushort * *)
0x1800933fc  mov     ebx, eax
0x1800933fe  test    eax, eax
0x180093400  jns     short loc_18009340B
0x180093402  lea     r8, aMakefakeuserem; "MakeFakeUserEmail"
0x180093409  jmp     short loc_1800933D3
0x18009340b  mov     rcx, [rbp+80h+var_F0]; unsigned __int16 *
0x18009340f  mov     r8, rdi
0x180093412  call    DsrBeginDiscoverEnterprise
0x180093417  mov     ebx, eax
0x180093419  test    eax, eax
0x18009341b  jns     short loc_180093426
0x18009341d  lea     r8, aDsrbegindiscov; "DsrBeginDiscoverEnterprise"
0x180093424  jmp     short loc_1800933D3
0x180093426  xor     r15d, r15d
0x180093429  jmp     loc_1800935F8
0x18009342e  xor     edx, edx; unsigned __int16 **
0x180093430  lea     rcx, [rbp+80h+arg_28]; int *
0x180093437  call    ?IsLocalMachineDomainJoined@@YAJPEAHPEAPEAG@Z; IsLocalMachineDomainJoined(int *,ushort * *)
0x18009343c  test    eax, eax
0x18009343e  jns     short loc_18009345A
0x180093440  mov     r8d, eax
0x180093443  lea     rdx, aDiscoverapiBeg; "DiscoverApi::BeginRepairJoinInfo"
0x18009344a  lea     rcx, aSIslocalmachin; "%s: IsLocalMachineDomainJoined failed w"...
0x180093451  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x180093456  xor     eax, eax
0x180093458  jmp     short loc_180093460
0x18009345a  mov     eax, dword ptr [rbp+80h+arg_28]
0x180093460  test    eax, eax
0x180093462  jz      short loc_1800934A6
0x180093464  xor     r8d, r8d; unsigned __int16 **
0x180093467  lea     rdx, [rsp+180h+var_118]; unsigned __int16 **
0x18009346c  call    ?GetAutoJoinDomainConfiguration@@YAJPEAPEAG00PEAW4_DSR_INSTANCE@@@Z; GetAutoJoinDomainConfiguration(ushort * *,ushort * *,ushort * *,_DSR_INSTANCE *)
0x180093471  test    eax, eax
0x180093473  jns     short loc_18009347E
0x180093475  lea     rcx, aSGetautojoindo; "%s: GetAutoJoinDomainConfiguration fail"...
0x18009347c  jmp     short loc_180093497
  ... truncated ...
```
