# DCEngine::ExecuteRequests(void)

- ea: `0x180112208`
- end: `0x1801126eb`
- name: `?ExecuteRequests@DCEngine@@AEAAJXZ`
- size: `1251`
- prototype: `__int64 __fastcall(DCEngine *__hidden this)`
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801142c4`
- `0x180118540`

## callees

- `0x18000b9e0`
- `0x18000e24c`
- `0x180018744`
- `0x180018b30`
- `0x18001c9a4`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18004b7f4`
- `0x18004d1ac`
- `0x1800aa870`
- `0x1800ced20`
- `0x1800f5c8c`
- `0x1800f6294`
- `0x1800f9c1c`
- `0x1800f9cb4`
- `0x1800f9d70`
- `0x180100418`
- `0x180100ad8`
- `0x18010136c`
- `0x18010e36c`
- `0x18011109c`
- `0x180112208`
- `0x180118964`
- `0x18011cc78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180112328`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180112328`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011257a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011257a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180112287`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180112287`
- `RPCRT4!UuidFromStringW` at `0x180112454`
- `RPCRT4!UuidFromStringW` at `0x180112454`
- `dmEnrollEngine!GetEnrollmentType` at `0x180112480`
- `dmEnrollEngine!GetEnrollmentType` at `0x180112480`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x180112527`
- `omadmapi!__imp_OmaDmInitiateSessionAsDevice` at `0x180112527`

## string_xrefs

- `0x1801124dc`: `com.microsoft:mdm.declaredconfiguration.processdoccomplete`
- `0x18011242e`: `DeclaredConfigurationStore_GetDriftControlStartSyncSessionOnFailure`
- `0x1801125c7`: `DCCDNUtil_SetRegistryString:Set WinDCActiveEnrollmentId to empty`
- `0x1801124f2`: `CompleteProcessing`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DCEngine::ExecuteRequests(DCEngine *this)
{
  CDeclaredConfigurationLogger *Logger; // rax
  int v3; // edi
  BOOL v4; // esi
  HKEY v5; // rbx
  CDeclaredConfigurationLogger *v6; // rax
  CDeclaredConfigurationLogger *v7; // rax
  LSTATUS v8; // edi
  CDeclaredConfigurationLogger *v9; // rax
  unsigned int v10; // ebx
  CDeclaredConfigurationLogger *v11; // rax
  int v13; // eax
  int v14; // ecx
  int RegistryString; // [rsp+40h] [rbp-C0h] BYREF
  char v16; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v17; // [rsp+48h] [rbp-B8h] BYREF
  int v18; // [rsp+4Ch] [rbp-B4h] BYREF
  RPC_WSTR StringUuid; // [rsp+50h] [rbp-B0h] BYREF
  int v20; // [rsp+58h] [rbp-A8h] BYREF
  int v21; // [rsp+5Ch] [rbp-A4h] BYREF
  HKEY phkResult[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v23[2]; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  char *v26; // [rsp+90h] [rbp-70h] BYREF
  ULONGLONG TickCount64; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v28[5]; // [rsp+A0h] [rbp-60h] BYREF
  char v29; // [rsp+C8h] [rbp-38h]
  _DWORD v30[2]; // [rsp+D0h] [rbp-30h] BYREF
  const wchar_t *v31; // [rsp+D8h] [rbp-28h]
  __int64 v32; // [rsp+E0h] [rbp-20h]
  const wchar_t *v33; // [rsp+E8h] [rbp-18h]
  int v34; // [rsp+F0h] [rbp-10h]
  int v35; // [rsp+F4h] [rbp-Ch]
  __int64 v36; // [rsp+F8h] [rbp-8h]
  __int128 v37; // [rsp+100h] [rbp+0h]
  int *v38; // [rsp+110h] [rbp+10h]
  char v39; // [rsp+118h] [rbp+18h]
  UUID Uuid; // [rsp+120h] [rbp+20h] BYREF

  RegistryString = 0;
  Logger = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorEnterFunction(Logger, L"DCEngine::ExecuteRequests");
  v38 = &RegistryString;
  v39 = 1;
  v16 = 0;
  v18 = 0;
  v20 = 0;
  TickCount64 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl) )
    TickCount64 = GetTickCount64();
  v28[0] = &TickCount64;
  v28[1] = &v18;
  v28[2] = &v20;
  v28[3] = &v16;
  v28[4] = &RegistryString;
  v29 = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
    DeclaredConfigurationStore_RegistryTrackingStoreMigrationRequired();
  v21 = 1;
  v3 = 0;
  v4 = 0;
  while ( 1 )
  {
    v23[0] = 0;
    RegistryString = DeclaredConfigurations::RequestQueue::GetRequestAndRemoveFromQueue(
                       (DCEngine *)((char *)this + 8),
                       (struct Request *)phkResult);
    if ( RegistryString >= 0 )
    {
      v17 = 0;
      RegistryString = DCEngine::ExecuteOneRequest(this, (const struct Request *)phkResult, &v21, (int *)&v17);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl) )
      {
        v13 = ++v18;
        if ( v17 )
        {
          ++v20;
        }
        else if ( !v21 )
        {
          v18 = v13 - 1;
        }
      }
      v14 = 0;
      if ( v23[0] )
        v14 = *(_DWORD *)(v23[0] + 584LL);
      if ( !v4 )
        v4 = v14 < 0;
      if ( !v17 && LODWORD(phkResult[0]) != 5 )
        v3 = 1;
      goto LABEL_43;
    }
    if ( (unsigned int)DCEngine::checkNewInstanceData(this) )
      break;
LABEL_43:
    ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(v23);
    if ( !v21 )
      goto LABEL_9;
  }
  ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(v23);
LABEL_9:
  v17 = 0;
  v26 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  ULongLongToULong(0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)this + 9) - *((_QWORD *)this + 8)) >> 3), &v17);
  gate<critical_section>::~gate<critical_section>(&v26);
  if ( !v17 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl'::`2'::impl) )
      v16 = 1;
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    RegistryString = DCCDNUtil_GetHKey(qword_18018A6D0, &hKey, 0);
    if ( RegistryString >= 0 )
    {
      StringUuid = 0;
      phkResult[0] = (HKEY)&StringUuid;
      phkResult[1] = 0;
      LOBYTE(v23[0]) = 1;
      v5 = hKey;
      RegistryString = DCCDNUtil_GetRegistryString(
                         hKey,
                         0,
                         L"WinDCActiveEnrollmentId",
                         (unsigned __int16 **)&phkResult[1]);
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(phkResult);
      if ( RegistryString >= 0 && StringUuid )
      {
        v17 = 0;
        RegistryString = DeclaredConfigurationStore_GetDriftControlStartSyncSessionOnFailure(StringUuid, 0, &v17);
        if ( RegistryString < 0 )
        {
          v6 = CDeclaredConfigurationLogger::GetLogger();
          CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
            v6,
            L"DCEngine::ExecuteRequests",
            L"DeclaredConfigurationStore_GetDriftControlStartSyncSessionOnFailure",
            StringUuid,
            RegistryString);
        }
        Uuid = 0;
        RegistryString = UuidFromStringW(StringUuid, &Uuid);
        if ( RegistryString >= 0 )
        {
          v24 = 63;
          *(UUID *)phkResult = Uuid;
          RegistryString = GetEnrollmentType(phkResult, &v24);
          if ( RegistryString >= 0 && (v3 || v17 && v4) && ((1LL << v24) & 0xD402061) != 0 )
          {
            v32 = 0;
            v36 = 0;
            v37 = 0;
            v30[0] = 64;
            v30[1] = 1226;
            v31 = L"com.microsoft:mdm.declaredconfiguration.processdoccomplete";
            v35 = 5;
            v34 = 1;
            v33 = L"CompleteProcessing";
            RegistryString = OmaDmInitiateSessionAsDevice(StringUuid, 1, 2, v30, 1, 0, v3 != 0 ? 12 : 56);
            v7 = CDeclaredConfigurationLogger::GetLogger();
            CDeclaredConfigurationLogger::LogDCAlertStatus(v7, StringUuid, RegistryString);
          }
        }
        v26 = 0;
        phkResult[0] = (HKEY)&v26;
        phkResult[1] = 0;
        LOBYTE(v23[0]) = 1;
        v8 = RegOpenKeyExW(v5, StringUuid, 0, 0x20119u, &phkResult[1]);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(phkResult);
        if ( !v8 )
        {
          RegistryString = DCCDNUtil_SetRegistryString(v5, 0, L"WinDCActiveEnrollmentId", &word_180142E98, 0);
          if ( RegistryString < 0 )
          {
            v9 = CDeclaredConfigurationLogger::GetLogger();
            CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(
              v9,
              L"DCEngine::ExecuteRequests",
              L"DCCDNUtil_SetRegistryString:Set WinDCActiveEnrollmentId to empty",
              StringUuid,
              RegistryString);
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
      }
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&StringUuid);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  }
  v10 = RegistryString;
  v29 = 0;
  lambda_ea65ec2cb10767b0145523f0506ee583_::operator()(v28);
  v11 = CDeclaredConfigurationLogger::GetLogger();
  CDeclaredConfigurationLogger::LogOrchestratorExitFunction(v11, L"DCEngine::ExecuteRequests", RegistryString);
  return v10;
}

```

## disassembly

```asm
0x180112208  mov     [rsp-8+arg_8], rbx
0x18011220d  mov     [rsp-8+arg_10], rsi
0x180112212  push    rbp
0x180112213  push    rdi
0x180112214  push    r12
0x180112216  push    r14
0x180112218  push    r15
0x18011221a  lea     rbp, [rsp-40h]
0x18011221f  sub     rsp, 140h
0x180112226  mov     rax, cs:__security_cookie
0x18011222d  xor     rax, rsp
0x180112230  mov     [rbp+60h+var_30], rax
0x180112234  mov     rbx, rcx
0x180112237  xor     r15d, r15d
0x18011223a  mov     [rsp+160h+var_120], r15d
0x18011223f  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180112244  lea     rdx, aDcengineExecut; "DCEngine::ExecuteRequests"
0x18011224b  mov     rcx, rax; this
0x18011224e  call    ?LogOrchestratorEnterFunction@CDeclaredConfigurationLogger@@QEAAXPEBG@Z; CDeclaredConfigurationLogger::LogOrchestratorEnterFunction(ushort const *)
0x180112253  lea     rax, [rsp+160h+var_120]
0x180112258  mov     [rbp+60h+var_50], rax
0x18011225c  lea     r12d, [r15+1]
0x180112260  mov     [rbp+60h+var_48], r12b
0x180112264  mov     [rsp+160h+var_11C], r15b
0x180112269  mov     [rsp+160h+var_114], r15d
0x18011226e  mov     [rsp+160h+var_108], r15d
0x180112273  mov     [rbp+60h+var_C8], r15
0x180112277  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl(void)'::`2'::impl
0x18011227e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(void)
0x180112283  test    al, al
0x180112285  jz      short loc_180112291
0x180112287  call    cs:__imp_GetTickCount64
0x18011228d  mov     [rbp+60h+var_C8], rax
0x180112291  lea     rax, [rbp+60h+var_C8]
0x180112295  mov     [rbp+60h+var_C0], rax
0x180112299  lea     rax, [rsp+160h+var_114]
0x18011229e  mov     [rbp+60h+var_B8], rax
0x1801122a2  lea     rax, [rsp+160h+var_108]
0x1801122a7  mov     [rbp+60h+var_B0], rax
0x1801122ab  lea     rax, [rsp+160h+var_11C]
0x1801122b0  mov     [rbp+60h+var_A8], rax
0x1801122b4  lea     rax, [rsp+160h+var_120]
0x1801122b9  mov     [rbp+60h+var_A0], rax
0x1801122bd  mov     [rbp+60h+var_98], r12b
0x1801122c1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1801122c8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1801122cd  test    al, al
0x1801122cf  jz      short loc_1801122D6
0x1801122d1  call    ?DeclaredConfigurationStore_RegistryTrackingStoreMigrationRequired@@YAJXZ; DeclaredConfigurationStore_RegistryTrackingStoreMigrationRequired(void)
0x1801122d6  mov     [rsp+160h+var_104], r12d
0x1801122db  mov     edi, r15d
0x1801122de  mov     esi, r15d
0x1801122e1  mov     [rsp+160h+var_F0], r15
0x1801122e6  lea     rdx, [rsp+160h+var_100]; struct Request *
0x1801122eb  lea     rcx, [rbx+8]; this
0x1801122ef  call    ?GetRequestAndRemoveFromQueue@RequestQueue@DeclaredConfigurations@@QEAAJAEAURequest@2@@Z; DeclaredConfigurations::RequestQueue::GetRequestAndRemoveFromQueue(DeclaredConfigurations::Request &)
0x1801122f4  mov     [rsp+160h+var_120], eax
0x1801122f8  mov     rcx, rbx; this
0x1801122fb  test    eax, eax
0x1801122fd  jns     loc_180112652
0x180112303  call    ?checkNewInstanceData@DCEngine@@AEAAJXZ; DCEngine::checkNewInstanceData(void)
0x180112308  nop
0x180112309  test    eax, eax
0x18011230b  jz      loc_1801126D0
0x180112311  lea     rcx, [rsp+160h+var_F0]
0x180112316  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x18011231b  mov     [rsp+160h+var_118], r15d
0x180112320  lea     rcx, [rbx+10h]; lpCriticalSection
0x180112324  mov     [rbp+60h+var_D0], rcx
0x180112328  call    cs:__imp_EnterCriticalSection
0x18011232e  mov     rcx, [rbx+48h]
0x180112332  sub     rcx, [rbx+40h]
0x180112336  sar     rcx, 3
0x18011233a  mov     rax, 0AAAAAAAAAAAAAAABh
0x180112344  imul    rcx, rax; unsigned __int64
0x180112348  lea     rdx, [rsp+160h+var_118]; unsigned int *
0x18011234d  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180112352  lea     rcx, [rbp+60h+var_D0]
0x180112356  call    ??1?$gate@Vcritical_section@@@@QEAA@XZ; gate<critical_section>::~gate<critical_section>(void)
0x18011235b  cmp     [rsp+160h+var_118], r15d
0x180112360  jnz     loc_1801125FC
0x180112366  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl(void)'::`2'::impl
0x18011236d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(void)
0x180112372  test    al, al
0x180112374  jz      short loc_18011237B
0x180112376  mov     [rsp+160h+var_11C], r12b
0x18011237b  mov     [rbp+60h+hKey], r15
0x18011237f  xor     edx, edx
0x180112381  lea     rcx, [rbp+60h+hKey]
0x180112385  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18011238a  xor     r8d, r8d; int
0x18011238d  lea     rdx, [rbp+60h+hKey]; HKEY *
0x180112391  mov     rcx, cs:qword_18018A6D0; lpSubKey
0x180112398  call    ?DCCDNUtil_GetHKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; DCCDNUtil_GetHKey(ushort const *,HKEY__ * *,int)
0x18011239d  mov     [rsp+160h+var_120], eax
0x1801123a1  test    eax, eax
0x1801123a3  js      loc_1801125F3
0x1801123a9  mov     [rsp+160h+StringUuid], r15
0x1801123ae  lea     rax, [rsp+160h+StringUuid]
0x1801123b3  mov     [rsp+160h+var_100], rax
0x1801123b8  mov     [rsp+160h+var_100+8], r15
0x1801123bd  mov     byte ptr [rsp+160h+var_F0], r12b
0x1801123c2  lea     r9, [rsp+160h+var_100+8]; unsigned __int16 **
0x1801123c7  lea     r8, aWindcactiveenr; "WinDCActiveEnrollmentId"
0x1801123ce  xor     edx, edx; unsigned __int16 *
0x1801123d0  mov     rbx, [rbp+60h+hKey]
0x1801123d4  mov     rcx, rbx; HKEY
0x1801123d7  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1801123dc  mov     [rsp+160h+var_120], eax
0x1801123e0  lea     rcx, [rsp+160h+var_100]
0x1801123e5  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1801123ea  cmp     [rsp+160h+var_120], r15d
0x1801123ef  jl      loc_1801125E8
0x1801123f5  mov     rcx, [rsp+160h+StringUuid]; unsigned __int16 *
0x1801123fa  test    rcx, rcx
0x1801123fd  jz      loc_1801125E8
0x180112403  mov     [rsp+160h+var_118], r15d
0x180112408  lea     r8, [rsp+160h+var_118]; unsigned int *
0x18011240d  xor     edx, edx; unsigned __int16 *
0x18011240f  call    ?DeclaredConfigurationStore_GetDriftControlStartSyncSessionOnFailure@@YAJPEBG0PEAK@Z; DeclaredConfigurationStore_GetDriftControlStartSyncSessionOnFailure(ushort const *,ushort const *,ulong *)
0x180112414  mov     [rsp+160h+var_120], eax
0x180112418  test    eax, eax
0x18011241a  jns     short loc_180112444
0x18011241c  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180112421  mov     ecx, [rsp+160h+var_120]
0x180112425  mov     dword ptr [rsp+160h+phkResult], ecx; int
0x180112429  mov     r9, [rsp+160h+StringUuid]; unsigned __int16 *
0x18011242e  lea     r8, aDeclaredconfig_121; "DeclaredConfigurationStore_GetDriftCont"...
0x180112435  lea     rdx, aDcengineExecut; "DCEngine::ExecuteRequests"
0x18011243c  mov     rcx, rax; this
0x18011243f  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x180112444  xorps   xmm0, xmm0
0x180112447  movups  xmmword ptr [rbp+60h+Uuid.Data1], xmm0
0x18011244b  lea     rdx, [rbp+60h+Uuid]; Uuid
0x18011244f  mov     rcx, [rsp+160h+StringUuid]; StringUuid
0x180112454  call    cs:__imp_UuidFromStringW
0x18011245a  mov     [rsp+160h+var_120], eax
0x18011245e  test    eax, eax
0x180112460  js      loc_180112548
0x180112466  mov     [rbp+60h+var_E0], 3Fh ; '?'
0x18011246d  movaps  xmm0, xmmword ptr [rbp+60h+Uuid.Data1]
0x180112471  movdqa  xmmword ptr [rsp+160h+var_100], xmm0
0x180112477  lea     rdx, [rbp+60h+var_E0]
0x18011247b  lea     rcx, [rsp+160h+var_100]
0x180112480  call    cs:__imp_GetEnrollmentType
0x180112486  mov     [rsp+160h+var_120], eax
0x18011248a  test    eax, eax
0x18011248c  js      loc_180112548
0x180112492  test    edi, edi
0x180112494  jnz     short loc_1801124A9
0x180112496  cmp     [rsp+160h+var_118], r15d
0x18011249b  jz      loc_180112548
0x1801124a1  test    esi, esi
0x1801124a3  jz      loc_180112548
0x1801124a9  mov     ecx, [rbp+60h+var_E0]
0x1801124ac  mov     rax, r12
0x1801124af  shl     rax, cl
0x1801124b2  test    rax, 0D402061h
0x1801124b8  jz      loc_180112548
0x1801124be  mov     [rbp+60h+var_80], r15
0x1801124c2  mov     [rbp+60h+var_68], r15
0x1801124c6  xorps   xmm0, xmm0
0x1801124c9  movdqa  [rbp+60h+var_60], xmm0
0x1801124ce  mov     [rbp+60h+var_90], 40h ; '@'
0x1801124d5  mov     [rbp+60h+var_8C], 4CAh
0x1801124dc  lea     rax, aComMicrosoftMd; "com.microsoft:mdm.declaredconfiguration"...
0x1801124e3  mov     [rbp+60h+var_88], rax
0x1801124e7  mov     [rbp+60h+var_6C], 5
0x1801124ee  mov     [rbp+60h+var_70], r12d
0x1801124f2  lea     rax, aCompleteproces; "CompleteProcessing"
0x1801124f9  mov     [rbp+60h+var_78], rax
0x1801124fd  neg     edi
0x1801124ff  sbb     eax, eax
0x180112501  and     eax, 0FFFFFFD4h
0x180112504  add     eax, 38h ; '8'
0x180112507  mov     [rsp+160h+var_130], eax
0x18011250b  mov     [rsp+160h+var_138], r15
0x180112510  mov     dword ptr [rsp+160h+phkResult], r12d
0x180112515  lea     r9, [rbp+60h+var_90]
0x180112519  mov     r8d, 2
0x18011251f  mov     edx, r12d
0x180112522  mov     rcx, [rsp+160h+StringUuid]
0x180112527  call    cs:__imp_OmaDmInitiateSessionAsDevice
0x18011252d  mov     [rsp+160h+var_120], eax
0x180112531  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180112536  mov     r8d, [rsp+160h+var_120]; int
0x18011253b  mov     rdx, [rsp+160h+StringUuid]; unsigned __int16 *
0x180112540  mov     rcx, rax; this
0x180112543  call    ?LogDCAlertStatus@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogDCAlertStatus(ushort const *,long)
0x180112548  mov     [rbp+60h+var_D0], r15
0x18011254c  lea     rax, [rbp+60h+var_D0]
0x180112550  mov     [rsp+160h+var_100], rax
0x180112555  mov     [rsp+160h+var_100+8], r15
0x18011255a  mov     byte ptr [rsp+160h+var_F0], r12b
0x18011255f  lea     rax, [rsp+160h+var_100+8]
0x180112564  mov     [rsp+160h+phkResult], rax; phkResult
0x180112569  mov     r9d, 20119h; samDesired
0x18011256f  xor     r8d, r8d; ulOptions
0x180112572  mov     rdx, [rsp+160h+StringUuid]; lpSubKey
0x180112577  mov     rcx, rbx; hKey
0x18011257a  call    cs:__imp_RegOpenKeyExW
0x180112580  mov     edi, eax
0x180112582  lea     rcx, [rsp+160h+var_100]
0x180112587  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18011258c  test    edi, edi
0x18011258e  jnz     short loc_1801125DE
0x180112590  mov     byte ptr [rsp+160h+phkResult], r15b; bool
0x180112595  lea     r9, word_180142E98; unsigned __int16 *
0x18011259c  lea     r8, aWindcactiveenr; "WinDCActiveEnrollmentId"
0x1801125a3  xor     edx, edx; unsigned __int16 *
0x1801125a5  mov     rcx, rbx; HKEY
0x1801125a8  call    ?DCCDNUtil_SetRegistryString@@YAJPEAUHKEY__@@PEBG11_N@Z; DCCDNUtil_SetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort const *,bool)
0x1801125ad  mov     [rsp+160h+var_120], eax
0x1801125b1  test    eax, eax
0x1801125b3  jns     short loc_1801125DE
0x1801125b5  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x1801125ba  mov     ecx, [rsp+160h+var_120]
0x1801125be  mov     dword ptr [rsp+160h+phkResult], ecx; int
0x1801125c2  mov     r9, [rsp+160h+StringUuid]; unsigned __int16 *
0x1801125c7  lea     r8, aDccdnutilSetre_3; "DCCDNUtil_SetRegistryString:Set WinDCAc"...
0x1801125ce  lea     rdx, aDcengineExecut; "DCEngine::ExecuteRequests"
0x1801125d5  mov     rcx, rax; this
0x1801125d8  call    ?LogOrchestratorGenericFailure@CDeclaredConfigurationLogger@@QEAAXPEBG00J@Z; CDeclaredConfigurationLogger::LogOrchestratorGenericFailure(ushort const *,ushort const *,ushort const *,long)
0x1801125dd  nop
0x1801125de  lea     rcx, [rbp+60h+var_D0]
0x1801125e2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801125e7  nop
0x1801125e8  lea     rcx, [rsp+160h+StringUuid]
0x1801125ed  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1801125f2  nop
0x1801125f3  lea     rcx, [rbp+60h+hKey]
0x1801125f7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1801125fc  mov     ebx, [rsp+160h+var_120]
0x180112600  mov     [rbp+60h+var_98], r15b
0x180112604  lea     rcx, [rbp+60h+var_C0]
0x180112608  call    _lambda_ea65ec2cb10767b0145523f0506ee583___operator__
0x18011260d  nop
0x18011260e  call    ?GetLogger@CDeclaredConfigurationLogger@@SAPEAV1@XZ; CDeclaredConfigurationLogger::GetLogger(void)
0x180112613  mov     r8d, [rsp+160h+var_120]; int
0x180112618  lea     rdx, aDcengineExecut; "DCEngine::ExecuteRequests"
0x18011261f  mov     rcx, rax; this
0x180112622  call    ?LogOrchestratorExitFunction@CDeclaredConfigurationLogger@@QEAAXPEBGJ@Z; CDeclaredConfigurationLogger::LogOrchestratorExitFunction(ushort const *,long)
0x180112627  nop
0x180112628  mov     eax, ebx
0x18011262a  mov     rcx, [rbp+60h+var_30]
0x18011262e  xor     rcx, rsp; StackCookie
0x180112631  call    __security_check_cookie
0x180112636  lea     r11, [rsp+160h+var_20]
0x18011263e  mov     rbx, [r11+38h]
0x180112642  mov     rsi, [r11+40h]
0x180112646  mov     rsp, r11
0x180112649  pop     r15
0x18011264b  pop     r14
0x18011264d  pop     r12
0x18011264f  pop     rdi
0x180112650  pop     rbp
0x180112651  retn
0x180112652  mov     [rsp+160h+var_118], r15d
0x180112657  lea     r9, [rsp+160h+var_118]; int *
0x18011265c  lea     r8, [rsp+160h+var_104]; int *
0x180112661  lea     rdx, [rsp+160h+var_100]; struct Request *
0x180112666  call    ?ExecuteOneRequest@DCEngine@@AEAAJAEBURequest@DeclaredConfigurations@@PEAH1@Z; DCEngine::ExecuteOneRequest(DeclaredConfigurations::Request const &,int *,int *)
0x18011266b  mov     [rsp+160h+var_120], eax
0x18011266f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior> `wil::Feature<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::GetImpl(void)'::`2'::impl
0x180112676  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeclaredConfiguration_RefreshBehavior>::__private_IsEnabled(void)
0x18011267b  mov     edx, [rsp+160h+var_118]
0x18011267f  test    al, al
0x180112681  jz      short loc_1801126A6
0x180112683  mov     eax, [rsp+160h+var_114]
0x180112687  add     eax, r12d
0x18011268a  mov     [rsp+160h+var_114], eax
0x18011268e  test    edx, edx
0x180112690  jz      short loc_180112699
0x180112692  add     [rsp+160h+var_108], r12d
0x180112697  jmp     short loc_1801126A6
0x180112699  cmp     [rsp+160h+var_104], r15d
0x18011269e  jnz     short loc_1801126A6
0x1801126a0  dec     eax
0x1801126a2  mov     [rsp+160h+var_114], eax
0x1801126a6  mov     ecx, r15d
0x1801126a9  mov     rax, [rsp+160h+var_F0]
0x1801126ae  test    rax, rax
0x1801126b1  jz      short loc_1801126B9
0x1801126b3  mov     ecx, [rax+248h]
0x1801126b9  test    esi, esi
0x1801126bb  jnz     short loc_1801126C3
0x1801126bd  test    ecx, ecx
0x1801126bf  cmovs   esi, r12d
0x1801126c3  test    edx, edx
0x1801126c5  jnz     short loc_1801126D0
0x1801126c7  cmp     dword ptr [rsp+160h+var_100], 5
0x1801126cc  cmovnz  edi, r12d
0x1801126d0  lea     rcx, [rsp+160h+var_F0]
0x1801126d5  call    ??1?$CComPtrBase@UIClientSecurity@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IClientSecurity>::~CComPtrBase<IClientSecurity>(void)
0x1801126da  cmp     [rsp+160h+var_104], r15d
0x1801126df  jnz     loc_1801122E1
0x1801126e5  jmp     loc_18011231B
```
