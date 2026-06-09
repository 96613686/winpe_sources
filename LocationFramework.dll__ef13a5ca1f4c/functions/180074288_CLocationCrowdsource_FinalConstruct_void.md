# CLocationCrowdsource::FinalConstruct(void)

- ea: `0x180074288`
- end: `0x1800745d4`
- name: `?FinalConstruct@CLocationCrowdsource@@QEAAJXZ`
- size: `844`
- prototype: `__int64 __fastcall(CLocationCrowdsource *__hidden this)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18008dc7c`
- `0x1800b590c`

## callees

- `0x18000dc00`
- `0x180012398`
- `0x18001be08`
- `0x180046e50`
- `0x180058328`
- `0x180074288`
- `0x180075090`
- `0x1800905c4`
- `0x180097954`
- `0x1800997b4`
- `0x18009c310`
- `0x18009d35c`
- `0x18009d9b8`
- `0x1800a0a88`
- `0x1800a98c0`
- `0x1800a9e0c`
- `0x1800aa5ac`
- `0x1800b1230`
- `0x1800e4a9c`
- `0x1800e9238`
- `0x1801058a0`
- `0x180107c30`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800743c5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800743c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800743d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800743d7`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18007442c`
- `api-ms-win-power-setting-l1-1-0!PowerSettingRegisterNotification` at `0x18007442c`

## string_xrefs

- `0x1800742f3`: `EtwEncryptOpenForTelemetry(&m_hEncrypt_Obsolete)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLocationCrowdsource::FinalConstruct(CLocationCrowdsource *this)
{
  signed int LocationComponentRegistry; // ebx
  int v3; // eax
  PTP_WORK ThreadpoolWork; // rax
  signed int LastError; // eax
  CLocationOrionTelemetry *v6; // rax
  CLocationOrionTelemetry *v7; // rbx
  __int64 v8; // rdx
  bool v9; // bl
  int v10; // eax
  __int64 v11; // rdx
  wil::details *v13; // [rsp+28h] [rbp-81h]
  CLocationOrionTelemetry *v14; // [rsp+30h] [rbp-79h] BYREF
  _OWORD v15[3]; // [rsp+40h] [rbp-69h] BYREF
  __int128 v16; // [rsp+70h] [rbp-39h]
  __int128 v17; // [rsp+80h] [rbp-29h]
  __int128 v18; // [rsp+90h] [rbp-19h]
  __int128 v19; // [rsp+A0h] [rbp-9h]
  int v20; // [rsp+B0h] [rbp+7h]
  __int128 Recipient; // [rsp+C0h] [rbp+17h] BYREF
  LPVOID ppv; // [rsp+D0h] [rbp+27h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+108h] [rbp+5Fh]

  ppv = 0;
  Recipient = 0;
  LocationComponentRegistry = LocationHelper::GetLocationComponentRegistry(&ppv);
  if ( LocationComponentRegistry >= 0 )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_LocalEncryptCertRemoval>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_LocalEncryptCertRemoval>::GetImpl'::`2'::impl) )
    {
      v3 = EtwEncryptOpenForTelemetry((struct tagETWENCRYPT **)this + 14);
      LocationComponentRegistry = v3;
      if ( v3 < 0 )
      {
        LODWORD(v13) = v3;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x68,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\crowdsource\\locationcrowdsource.cpp",
          "CLocationCrowdsource::FinalConstruct",
          "EtwEncryptOpenForTelemetry(&m_hEncrypt_Obsolete)",
          v13,
          (int)v14);
        goto LABEL_23;
      }
    }
    LocationAdapterHelper::GetWiFiAdapter((struct ILocationAdapterWiFi **)this + 39);
    LocationAdapterHelper::GetBluetoothAdapter((struct ILocationAdapterBluetooth **)this + 40);
    LocationAdapterHelper::GetCellAdapter((struct ILocationAdapterCell **)this + 41);
    LocationRegistryHelper::GetSettingValueDWORD(96, (__int64)L"MinTimeGapBetweenWifiScans", 20000, (_DWORD *)this + 32);
    LocationRegistryHelper::GetSettingValueDWORD(
      96,
      (__int64)L"ThrottleTimeForLowAccuracyGnssFixes",
      20000,
      (_DWORD *)this + 31);
    LocationRegistryHelper::GetSettingValueDWORD(
      96,
      (__int64)L"CrowdsourceLevel",
      *((_DWORD *)this + 26),
      (_DWORD *)this + 34);
    LocationRegistryHelper::GetSettingValueDWORD(
      96,
      (__int64)L"CrowdsourceCollectionType",
      *((_DWORD *)this + 27),
      (_DWORD *)this + 35);
    CLocationCrowdsource::RecomputeWiFiBeaconScanFrequency(this);
    *((_DWORD *)this + 30) = 5000;
    ThreadpoolWork = CreateThreadpoolWork(CLocationCrowdsource::CrowdsourceRawDataHandler, this, 0);
    *((_QWORD *)this + 52) = ThreadpoolWork;
    if ( ThreadpoolWork )
    {
      ResettableTimer::SetWindowLength((CLocationCrowdsource *)((char *)this + 424), 0x3E8u);
      *((_QWORD *)&Recipient + 1) = this;
      *(_QWORD *)&Recipient = CLocationCrowdsource::PowerNotificationCallback;
      PowerSettingRegisterNotification(&GUID_GLOBAL_USER_PRESENCE, 2u, &Recipient, (PHPOWERNOTIFY)this + 36);
      *(_QWORD *)&v15[0] = off_180161908;
      *((_QWORD *)&v15[0] + 1) = this;
      *((_QWORD *)&v16 + 1) = v15;
      LocationWnfSubscribe_Impl::SubscribeToWnfState((char *)this + 232, &WNF_PO_ENERGY_SAVER_STATE, v15);
      v6 = (CLocationOrionTelemetry *)operator new(0xC8u, (const struct std::nothrow_t *)std::nothrow);
      v7 = v6;
      v14 = v6;
      if ( v6 )
      {
        memset_0(v6, 0, 0xC8u);
        v6 = CLocationOrionTelemetry::CLocationOrionTelemetry(v7);
      }
      v14 = 0;
      v8 = *((_QWORD *)this + 42);
      *((_QWORD *)this + 42) = v6;
      if ( v8 )
        std::default_delete<CLocationOrionTelemetry>::operator()();
      v9 = *((_QWORD *)this + 42) == 0;
      std::unique_ptr<CLocationOrionTelemetry>::~unique_ptr<CLocationOrionTelemetry>(&v14);
      if ( v9 )
      {
        LocationComponentRegistry = -2147024882;
        goto LABEL_23;
      }
      v10 = ResettableTimer::SetDueTimeFromNow((PVOID)(*((_QWORD *)this + 42) + 56LL), 0x2932E00u);
      LocationComponentRegistry = 0;
      if ( v10 < 0 )
        LocationComponentRegistry = v10;
      if ( LocationComponentRegistry < 0 )
      {
        LODWORD(v13) = LocationComponentRegistry;
        wil::details::in1diag5::_Log_Hr(
          retaddr,
          (void *)0xBC,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\crowdsource\\locationcrowdsource.cpp",
          "CLocationCrowdsource::FinalConstruct",
          "hr",
          (const char *)v13,
          (int)v14);
      }
      memset_0(v15, 0, 0x74u);
      *(_OWORD *)((char *)this + 616) = v15[0];
      *(_OWORD *)((char *)this + 632) = v15[1];
      *(_OWORD *)((char *)this + 648) = v15[2];
      *(_OWORD *)((char *)this + 664) = v16;
      *(_OWORD *)((char *)this + 680) = v17;
      *(_OWORD *)((char *)this + 696) = v18;
      *(_OWORD *)((char *)this + 712) = v19;
      *((_DWORD *)this + 182) = v20;
    }
    else
    {
      LastError = GetLastError();
      LocationComponentRegistry = LastError;
      if ( LastError > 0 )
        LocationComponentRegistry = (unsigned __int16)LastError | 0x80070000;
    }
    if ( LocationComponentRegistry >= 0 )
      goto LABEL_23;
  }
  v11 = *((_QWORD *)this + 42);
  *((_QWORD *)this + 42) = 0;
  if ( v11 )
    std::default_delete<CLocationOrionTelemetry>::operator()();
  LocationCivicAddrAdapter::FinalRelease(this);
LABEL_23:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return (unsigned int)LocationComponentRegistry;
}

```

## disassembly

```asm
0x180074288  push    rbp
0x18007428a  push    rbx
0x18007428b  push    rsi
0x18007428c  push    rdi
0x18007428d  lea     rbp, [rsp-3Fh]
0x180074292  sub     rsp, 0E8h
0x180074299  mov     rax, cs:__security_cookie
0x1800742a0  xor     rax, rsp
0x1800742a3  mov     [rbp+57h+var_28], rax
0x1800742a7  mov     rdi, rcx
0x1800742aa  mov     [rbp+57h+ppv], 0
0x1800742b2  xorps   xmm0, xmm0
0x1800742b5  movups  [rbp+57h+Recipient], xmm0
0x1800742b9  lea     rcx, [rbp+57h+ppv]; ppv
0x1800742bd  call    ?GetLocationComponentRegistry@LocationHelper@@SAJPEAPEAUILocationComponentRegistry@@@Z; LocationHelper::GetLocationComponentRegistry(ILocationComponentRegistry * *)
0x1800742c2  mov     ebx, eax
0x1800742c4  test    eax, eax
0x1800742c6  js      loc_18007458C
0x1800742cc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_LocalEncryptCertRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_LocalEncryptCertRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LocalEncryptCertRemoval> `wil::Feature<__WilFeatureTraits_Feature_LocalEncryptCertRemoval>::GetImpl(void)'::`2'::impl
0x1800742d3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_LocalEncryptCertRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LocalEncryptCertRemoval>::__private_IsEnabled(void)
0x1800742d8  test    al, al
0x1800742da  jnz     short loc_18007431C
0x1800742dc  lea     rcx, [rdi+70h]; struct tagETWENCRYPT **
0x1800742e0  call    ?EtwEncryptOpenForTelemetry@@YAJPEAPEAUtagETWENCRYPT@@@Z; EtwEncryptOpenForTelemetry(tagETWENCRYPT * *)
0x1800742e5  mov     ebx, eax
0x1800742e7  test    eax, eax
0x1800742e9  jns     short loc_18007431C
0x1800742eb  mov     rcx, [rbp+5Fh]; this
0x1800742ef  mov     dword ptr [rsp+100h+var_D8], eax; wil::details *
0x1800742f3  lea     rax, aEtwencryptopen; "EtwEncryptOpenForTelemetry(&m_hEncrypt_"...
0x1800742fa  mov     [rsp+100h+var_E0], rax; char *
0x1800742ff  lea     r9, aClocationcrowd; "CLocationCrowdsource::FinalConstruct"
0x180074306  lea     r8, aOnecoreuapDriv_24; "onecoreuap\\drivers\\mobilepc\\location"...
0x18007430d  mov     edx, 68h ; 'h'; void *
0x180074312  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180074317  jmp     loc_1800745B1
0x18007431c  lea     rcx, [rdi+138h]; struct ILocationAdapterWiFi **
0x180074323  call    ?GetWiFiAdapter@LocationAdapterHelper@@SAJPEAPEAUILocationAdapterWiFi@@@Z; LocationAdapterHelper::GetWiFiAdapter(ILocationAdapterWiFi * *)
0x180074328  lea     rcx, [rdi+140h]; struct ILocationAdapterBluetooth **
0x18007432f  call    ?GetBluetoothAdapter@LocationAdapterHelper@@SAJPEAPEAUILocationAdapterBluetooth@@@Z; LocationAdapterHelper::GetBluetoothAdapter(ILocationAdapterBluetooth * *)
0x180074334  lea     rcx, [rdi+148h]; struct ILocationAdapterCell **
0x18007433b  call    ?GetCellAdapter@LocationAdapterHelper@@SAJPEAPEAUILocationAdapterCell@@@Z; LocationAdapterHelper::GetCellAdapter(ILocationAdapterCell * *)
0x180074340  lea     r9, [rdi+80h]
0x180074347  mov     ebx, 4E20h
0x18007434c  mov     r8d, ebx
0x18007434f  lea     rdx, aMintimegapbetw; "MinTimeGapBetweenWifiScans"
0x180074356  mov     esi, 60h ; '`'
0x18007435b  mov     ecx, esi
0x18007435d  call    ?GetSettingValueDWORD@LocationRegistryHelper@@SAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@PEBGKPEAK@Z; LocationRegistryHelper::GetSettingValueDWORD(__MIDL___MIDL_itf_locationframework_0000_0000_0001,ushort const *,ulong,ulong *)
0x180074362  lea     r9, [rdi+7Ch]
0x180074366  mov     r8d, ebx
0x180074369  lea     rdx, aThrottletimefo; "ThrottleTimeForLowAccuracyGnssFixes"
0x180074370  mov     ecx, esi
0x180074372  call    ?GetSettingValueDWORD@LocationRegistryHelper@@SAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@PEBGKPEAK@Z; LocationRegistryHelper::GetSettingValueDWORD(__MIDL___MIDL_itf_locationframework_0000_0000_0001,ushort const *,ulong,ulong *)
0x180074377  lea     r9, [rdi+88h]
0x18007437e  mov     r8d, [rdi+68h]
0x180074382  lea     rdx, aCrowdsourcelev; "CrowdsourceLevel"
0x180074389  mov     ecx, esi
0x18007438b  call    ?GetSettingValueDWORD@LocationRegistryHelper@@SAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@PEBGKPEAK@Z; LocationRegistryHelper::GetSettingValueDWORD(__MIDL___MIDL_itf_locationframework_0000_0000_0001,ushort const *,ulong,ulong *)
0x180074390  lea     r9, [rdi+8Ch]
0x180074397  mov     r8d, [rdi+6Ch]
0x18007439b  lea     rdx, aCrowdsourcecol; "CrowdsourceCollectionType"
0x1800743a2  mov     ecx, esi
0x1800743a4  call    ?GetSettingValueDWORD@LocationRegistryHelper@@SAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@PEBGKPEAK@Z; LocationRegistryHelper::GetSettingValueDWORD(__MIDL___MIDL_itf_locationframework_0000_0000_0001,ushort const *,ulong,ulong *)
0x1800743a9  mov     rcx, rdi; this
0x1800743ac  call    ?RecomputeWiFiBeaconScanFrequency@CLocationCrowdsource@@AEAAXXZ; CLocationCrowdsource::RecomputeWiFiBeaconScanFrequency(void)
0x1800743b1  mov     dword ptr [rdi+78h], 1388h
0x1800743b8  xor     r8d, r8d; pcbe
0x1800743bb  mov     rdx, rdi; pv
0x1800743be  lea     rcx, ?CrowdsourceRawDataHandler@CLocationCrowdsource@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800743c5  call    cs:__imp_CreateThreadpoolWork
0x1800743cb  mov     [rdi+1A0h], rax
0x1800743d2  test    rax, rax
0x1800743d5  jnz     short loc_1800743F5
0x1800743d7  call    cs:__imp_GetLastError
0x1800743dd  mov     ebx, eax
0x1800743df  test    eax, eax
0x1800743e1  jle     loc_180074588
0x1800743e7  movzx   ebx, ax
0x1800743ea  or      ebx, 80070000h
0x1800743f0  jmp     loc_180074588
0x1800743f5  lea     rcx, [rdi+1A8h]; this
0x1800743fc  mov     edx, 3E8h; unsigned int
0x180074401  call    ?SetWindowLength@ResettableTimer@@QEAAJK@Z; ResettableTimer::SetWindowLength(ulong)
0x180074406  mov     qword ptr [rbp+57h+Recipient+8], rdi
0x18007440a  lea     rax, ?PowerNotificationCallback@CLocationCrowdsource@@CAKPEAXK0@Z; CLocationCrowdsource::PowerNotificationCallback(void *,ulong,void *)
0x180074411  mov     qword ptr [rbp+57h+Recipient], rax
0x180074415  lea     r9, [rdi+120h]; RegistrationHandle
0x18007441c  lea     r8, [rbp+57h+Recipient]; Recipient
0x180074420  mov     edx, 2; Flags
0x180074425  lea     rcx, GUID_GLOBAL_USER_PRESENCE; SettingGuid
0x18007442c  call    cs:__imp_PowerSettingRegisterNotification
0x180074432  lea     rax, off_180161908
0x180074439  mov     qword ptr [rbp+57h+var_C0], rax
0x18007443d  mov     qword ptr [rbp+57h+var_C0+8], rdi
0x180074441  lea     rax, [rbp+57h+var_C0]
0x180074445  mov     [rbp+57h+var_88], rax
0x180074449  lea     rcx, [rdi+0E8h]
0x180074450  lea     r8, [rbp+57h+var_C0]
0x180074454  lea     rdx, WNF_PO_ENERGY_SAVER_STATE
0x18007445b  call    ?SubscribeToWnfState@LocationWnfSubscribe_Impl@@QEAAJAEBULOC_WNF_STATE_NAME@@V?$function@$$A6AXPEBXK@Z@std@@@Z; LocationWnfSubscribe_Impl::SubscribeToWnfState(LOC_WNF_STATE_NAME const &,std::function<void (void const *,ulong)>)
0x180074460  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180074467  mov     esi, 0C8h
0x18007446c  mov     ecx, esi; unsigned __int64
0x18007446e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180074473  mov     rbx, rax
0x180074476  mov     [rbp+57h+var_D0], rax
0x18007447a  test    rax, rax
0x18007447d  jz      short loc_180074495
0x18007447f  mov     r8d, esi; Size
0x180074482  xor     edx, edx; Val
0x180074484  mov     rcx, rax; void *
0x180074487  call    memset_0
0x18007448c  mov     rcx, rbx; this
0x18007448f  call    ??0CLocationOrionTelemetry@@QEAA@XZ; CLocationOrionTelemetry::CLocationOrionTelemetry(void)
0x180074494  nop
0x180074495  mov     [rbp+57h+var_D0], 0
0x18007449d  mov     rdx, [rdi+150h]
0x1800744a4  mov     [rdi+150h], rax
0x1800744ab  test    rdx, rdx
0x1800744ae  jz      short loc_1800744B5
0x1800744b0  call    ??R?$default_delete@VCLocationOrionTelemetry@@@std@@QEBAXPEAVCLocationOrionTelemetry@@@Z; std::default_delete<CLocationOrionTelemetry>::operator()(CLocationOrionTelemetry *)
0x1800744b5  cmp     qword ptr [rdi+150h], 0
0x1800744bd  setz    bl
0x1800744c0  lea     rcx, [rbp+57h+var_D0]
0x1800744c4  call    ??1?$unique_ptr@VCLocationOrionTelemetry@@U?$default_delete@VCLocationOrionTelemetry@@@std@@@std@@QEAA@XZ; std::unique_ptr<CLocationOrionTelemetry>::~unique_ptr<CLocationOrionTelemetry>(void)
0x1800744c9  test    bl, bl
0x1800744cb  jz      short loc_1800744D7
0x1800744cd  mov     ebx, 8007000Eh
0x1800744d2  jmp     loc_1800745B1
0x1800744d7  mov     rcx, [rdi+150h]
0x1800744de  add     rcx, 38h ; '8'; pv
0x1800744e2  mov     edx, 2932E00h; unsigned int
0x1800744e7  call    ?SetDueTimeFromNow@ResettableTimer@@QEAAJK@Z; ResettableTimer::SetDueTimeFromNow(ulong)
0x1800744ec  xor     ebx, ebx
0x1800744ee  test    eax, eax
0x1800744f0  cmovs   ebx, eax
0x1800744f3  mov     rcx, [rbp+5Fh]; this
0x1800744f7  test    ebx, ebx
0x1800744f9  jns     short loc_180074523
0x1800744fb  mov     dword ptr [rsp+100h+var_D8], ebx; char *
0x1800744ff  lea     rax, aHr; "hr"
0x180074506  mov     [rsp+100h+var_E0], rax; char *
0x18007450b  lea     r9, aClocationcrowd; "CLocationCrowdsource::FinalConstruct"
0x180074512  lea     r8, aOnecoreuapDriv_24; "onecoreuap\\drivers\\mobilepc\\location"...
0x180074519  mov     edx, 0BCh; void *
0x18007451e  call    ?_Log_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::_Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x180074523  xor     edx, edx; Val
0x180074525  lea     r8d, [rdx+74h]; Size
0x180074529  lea     rcx, [rbp+57h+var_C0]; void *
0x18007452d  call    memset_0
0x180074532  movaps  xmm0, [rbp+57h+var_C0]
0x180074536  movups  xmmword ptr [rdi+268h], xmm0
0x18007453d  movaps  xmm1, [rbp+57h+var_B0]
0x180074541  movups  xmmword ptr [rdi+278h], xmm1
0x180074548  movaps  xmm0, [rbp+57h+var_A0]
0x18007454c  movups  xmmword ptr [rdi+288h], xmm0
0x180074553  movaps  xmm1, xmmword ptr [rbp-39h]
0x180074557  movups  xmmword ptr [rdi+298h], xmm1
0x18007455e  movaps  xmm0, [rbp+57h+var_80]
0x180074562  movups  xmmword ptr [rdi+2A8h], xmm0
0x180074569  movaps  xmm1, [rbp+57h+var_70]
0x18007456d  movups  xmmword ptr [rdi+2B8h], xmm1
0x180074574  movaps  xmm0, [rbp+57h+var_60]
0x180074578  movups  xmmword ptr [rdi+2C8h], xmm0
0x18007457f  mov     eax, [rbp+57h+var_50]
0x180074582  mov     [rdi+2D8h], eax
0x180074588  test    ebx, ebx
0x18007458a  jns     short loc_1800745B1
0x18007458c  mov     rdx, [rdi+150h]
0x180074593  mov     qword ptr [rdi+150h], 0
0x18007459e  test    rdx, rdx
0x1800745a1  jz      short loc_1800745A8
0x1800745a3  call    ??R?$default_delete@VCLocationOrionTelemetry@@@std@@QEBAXPEAVCLocationOrionTelemetry@@@Z; std::default_delete<CLocationOrionTelemetry>::operator()(CLocationOrionTelemetry *)
0x1800745a8  mov     rcx, rdi; this
0x1800745ab  call    ?FinalRelease@LocationCivicAddrAdapter@@QEAAXXZ; LocationCivicAddrAdapter::FinalRelease(void)
0x1800745b0  nop
0x1800745b1  lea     rcx, [rbp+57h+ppv]
0x1800745b5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800745ba  mov     eax, ebx
0x1800745bc  mov     rcx, [rbp+57h+var_28]
0x1800745c0  xor     rcx, rsp; StackCookie
0x1800745c3  call    __security_check_cookie
0x1800745c8  add     rsp, 0E8h
0x1800745cf  pop     rdi
0x1800745d0  pop     rsi
0x1800745d1  pop     rbx
0x1800745d2  pop     rbp
0x1800745d3  retn
```
