# CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreApps::StartActivity(TraceLoggingCorrelationVector const &,uint)

- ea: `0x180040858`
- end: `0x180040a5c`
- name: `?StartActivity@AppRestoreOrchestratorRestoreApps@CloudRestoreLauncherTelemetry@@QEAAXAEBVTraceLoggingCorrelationVector@@I@Z`
- size: `516`
- prototype: `void(CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreApps *__hidden this, const struct TraceLoggingCorrelationVector *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18003fcd4`

## callees

- `0x180001edc`
- `0x1800032e4`
- `0x1800033cc`
- `0x18000c6e0`
- `0x180015bfc`
- `0x180017a5c`
- `0x1800195cc`
- `0x18001d124`
- `0x180024574`
- `0x180040858`
- `0x180043da0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800408f5`
- `KERNEL32!GetCurrentThreadId` at `0x1800409c2`
- `KERNEL32!GetCurrentThreadId` at `0x1800408f5`
- `KERNEL32!GetCurrentThreadId` at `0x1800409c2`

## pseudocode

```c
void __fastcall CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreApps::StartActivity(
        CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreApps *this,
        const struct TraceLoggingCorrelationVector *a2,
        int a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // edi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // ecx
  const struct _tlgProvider_t *v13; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // edi
  DWORD v17; // eax
  __int64 v18; // r8
  int v19; // ecx
  DWORD v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v22; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v23; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v25[144]; // [rsp+70h] [rbp-90h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry>::GetImpl'::`2'::impl) )
  {
    wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
    v6 = CloudRestoreLauncherTelemetry::Provider();
    v9 = (int)v6;
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x800000000000LL, v7, v8) )
    {
      v21 = a3;
      v22 = (__int64)_TlgCVGetter::_TlgCVGetter((_TlgCVGetter *)v25, a2);
      v23 = CloudRestoreLauncherTelemetry::s_restoredDeviceProfileId;
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      v20 = CurrentThreadId;
      v24 = 0x1000000;
      if ( !*(_BYTE *)(v11 + 4) || _tlgGuidIsZero((const struct _GUID *)(v11 + 24)) )
        v12 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)byte_180150241,
        v11 + 8,
        v12,
        (__int64)&v24,
        (__int64)&v20,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v21);
    }
  }
  else
  {
    wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
    v13 = CloudRestoreLauncherTelemetry::Provider();
    v16 = (int)v13;
    if ( *(_DWORD *)v13 > 5u && (unsigned __int8)tlgKeywordOn(v13, 0x800000000000LL, v14, v15) )
    {
      v24 = (__int64)_TlgCVGetter::_TlgCVGetter((_TlgCVGetter *)v25, a2);
      v23 = CloudRestoreLauncherTelemetry::s_restoredDeviceProfileId;
      v17 = GetCurrentThreadId();
      v18 = *((_QWORD *)this + 34);
      v20 = v17;
      v22 = 0x1000000;
      if ( !*(_BYTE *)(v18 + 4) || _tlgGuidIsZero((const struct _GUID *)(v18 + 24)) )
        v19 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
        v16,
        (unsigned int)byte_1801502CB,
        v18 + 8,
        v19,
        (__int64)&v22,
        (__int64)&v20,
        (__int64)&v23,
        (__int64)&v24);
    }
  }
  wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180040858  mov     [rsp-8+arg_10], rbx
0x18004085d  mov     [rsp-8+arg_18], rsi
0x180040862  push    rbp
0x180040863  push    rdi
0x180040864  push    r14
0x180040866  lea     rbp, [rsp-10h]
0x18004086b  sub     rsp, 110h
0x180040872  mov     rax, cs:__security_cookie
0x180040879  xor     rax, rsp
0x18004087c  mov     [rbp+20h+var_20], rax
0x180040880  mov     r14d, r8d
0x180040883  mov     rsi, rdx
0x180040886  mov     rbx, rcx
0x180040889  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry>::GetImpl(void)'::`2'::impl
0x180040890  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry>::__private_IsEnabled(void)
0x180040895  mov     rcx, rbx
0x180040898  test    al, al
0x18004089a  jz      loc_180040972
0x1800408a0  call    ?zInternalStart@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x1800408a5  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x1800408aa  mov     rdi, rax
0x1800408ad  mov     ecx, [rax]
0x1800408af  cmp     ecx, 5
0x1800408b2  jbe     loc_180040A30
0x1800408b8  mov     rdx, 800000000000h
0x1800408c2  mov     rcx, rax
0x1800408c5  call    _tlgKeywordOn
0x1800408ca  test    al, al
0x1800408cc  jz      loc_180040A30
0x1800408d2  mov     rdx, rsi; struct TraceLoggingCorrelationVector *
0x1800408d5  mov     [rsp+120h+var_CC], r14d
0x1800408da  lea     rcx, [rsp+120h+var_B0]; this
0x1800408df  call    ??0_TlgCVGetter@@QEAA@PEAVTraceLoggingCorrelationVector@@@Z; _TlgCVGetter::_TlgCVGetter(TraceLoggingCorrelationVector *)
0x1800408e4  mov     [rsp+120h+var_C8], rax
0x1800408e9  mov     rax, cs:?s_restoredDeviceProfileId@CloudRestoreLauncherTelemetry@@2V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> CloudRestoreLauncherTelemetry::s_restoredDeviceProfileId
0x1800408f0  mov     [rsp+120h+var_C0], rax
0x1800408f5  call    cs:__imp_GetCurrentThreadId
0x1800408fb  mov     r8, [rbx+110h]
0x180040902  mov     [rsp+120h+var_D0], eax
0x180040906  mov     [rsp+120h+var_B8], 1000000h
0x18004090f  cmp     byte ptr [r8+4], 0
0x180040914  jz      short loc_180040923
0x180040916  lea     rcx, [r8+18h]; struct _GUID *
0x18004091a  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18004091f  test    al, al
0x180040921  jz      short loc_180040925
0x180040923  xor     ecx, ecx
0x180040925  lea     rax, [rsp+120h+var_CC]
0x18004092a  mov     r9, rcx
0x18004092d  mov     [rsp+120h+var_E0], rax
0x180040932  lea     rdx, byte_180150241
0x180040939  lea     rax, [rsp+120h+var_C8]
0x18004093e  add     r8, 8
0x180040942  mov     [rsp+120h+var_E8], rax
0x180040947  mov     rcx, rdi
0x18004094a  lea     rax, [rsp+120h+var_C0]
0x18004094f  mov     [rsp+120h+var_F0], rax
0x180040954  lea     rax, [rsp+120h+var_D0]
0x180040959  mov     [rsp+120h+var_F8], rax
0x18004095e  lea     rax, [rsp+120h+var_B8]
0x180040963  mov     [rsp+120h+var_100], rax
0x180040968  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18004096d  jmp     loc_180040A30
0x180040972  call    ?zInternalStart@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180040977  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x18004097c  mov     rdi, rax
0x18004097f  mov     ecx, [rax]
0x180040981  cmp     ecx, 5
0x180040984  jbe     loc_180040A30
0x18004098a  mov     rdx, 800000000000h
0x180040994  mov     rcx, rax
0x180040997  call    _tlgKeywordOn
0x18004099c  test    al, al
0x18004099e  jz      loc_180040A30
0x1800409a4  mov     rdx, rsi; struct TraceLoggingCorrelationVector *
0x1800409a7  lea     rcx, [rsp+120h+var_B0]; this
0x1800409ac  call    ??0_TlgCVGetter@@QEAA@PEAVTraceLoggingCorrelationVector@@@Z; _TlgCVGetter::_TlgCVGetter(TraceLoggingCorrelationVector *)
0x1800409b1  mov     [rsp+120h+var_B8], rax
0x1800409b6  mov     rax, cs:?s_restoredDeviceProfileId@CloudRestoreLauncherTelemetry@@2V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> CloudRestoreLauncherTelemetry::s_restoredDeviceProfileId
0x1800409bd  mov     [rsp+120h+var_C0], rax
0x1800409c2  call    cs:__imp_GetCurrentThreadId
0x1800409c8  mov     r8, [rbx+110h]
0x1800409cf  mov     [rsp+120h+var_D0], eax
0x1800409d3  mov     [rsp+120h+var_C8], 1000000h
0x1800409dc  cmp     byte ptr [r8+4], 0
0x1800409e1  jz      short loc_1800409F0
0x1800409e3  lea     rcx, [r8+18h]; struct _GUID *
0x1800409e7  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800409ec  test    al, al
0x1800409ee  jz      short loc_1800409F2
0x1800409f0  xor     ecx, ecx
0x1800409f2  lea     rax, [rsp+120h+var_B8]
0x1800409f7  mov     r9, rcx
0x1800409fa  mov     [rsp+120h+var_E8], rax
0x1800409ff  lea     rdx, byte_1801502CB
0x180040a06  lea     rax, [rsp+120h+var_C0]
0x180040a0b  add     r8, 8
0x180040a0f  mov     [rsp+120h+var_F0], rax
0x180040a14  mov     rcx, rdi
0x180040a17  lea     rax, [rsp+120h+var_D0]
0x180040a1c  mov     [rsp+120h+var_F8], rax
0x180040a21  lea     rax, [rsp+120h+var_C8]
0x180040a26  mov     [rsp+120h+var_100], rax
0x180040a2b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
0x180040a30  mov     rcx, rbx
0x180040a33  call    ?EnsureWatchingCurrentThread@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
0x180040a38  mov     rcx, [rbp+20h+var_20]
0x180040a3c  xor     rcx, rsp; StackCookie
0x180040a3f  call    __security_check_cookie
0x180040a44  lea     r11, [rsp+120h+var_10]
0x180040a4c  mov     rbx, [r11+30h]
0x180040a50  mov     rsi, [r11+38h]
0x180040a54  mov     rsp, r11
0x180040a57  pop     r14
0x180040a59  pop     rdi
0x180040a5a  pop     rbp
0x180040a5b  retn
```
