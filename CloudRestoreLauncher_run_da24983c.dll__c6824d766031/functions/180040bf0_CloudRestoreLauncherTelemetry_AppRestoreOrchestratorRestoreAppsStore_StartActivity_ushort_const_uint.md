# CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreAppsStore::StartActivity(ushort const *,uint)

- ea: `0x180040bf0`
- end: `0x180040d75`
- name: `?StartActivity@AppRestoreOrchestratorRestoreAppsStore@CloudRestoreLauncherTelemetry@@QEAAXPEBGI@Z`
- size: `389`
- prototype: `void __fastcall(CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreAppsStore *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800375bc`

## callees

- `0x180001edc`
- `0x180003160`
- `0x180003224`
- `0x180017a5c`
- `0x1800195cc`
- `0x18001d124`
- `0x180024574`
- `0x180040bf0`
- `0x180043da0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180040c5f`
- `KERNEL32!GetCurrentThreadId` at `0x180040cfa`
- `KERNEL32!GetCurrentThreadId` at `0x180040c5f`
- `KERNEL32!GetCurrentThreadId` at `0x180040cfa`

## pseudocode

```c
void __fastcall CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreAppsStore::StartActivity(
        CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreAppsStore *this,
        const unsigned __int16 *a2,
        DWORD a3)
{
  const struct _tlgProvider_t *v6; // rax
  int v7; // edi
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  int v10; // ecx
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  DWORD v13; // eax
  __int64 v14; // r8
  int v15; // ecx
  DWORD v16; // [rsp+40h] [rbp-20h] BYREF
  __int64 v17; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v18[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD v19; // [rsp+98h] [rbp+38h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry>::GetImpl'::`2'::impl) )
  {
    wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
    v6 = CloudRestoreLauncherTelemetry::Provider();
    v7 = (int)v6;
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x800000000000LL) )
    {
      v19 = a3;
      v17 = (__int64)a2;
      CurrentThreadId = GetCurrentThreadId();
      v9 = *((_QWORD *)this + 34);
      v16 = CurrentThreadId;
      v18[0] = 0x1000000;
      if ( !*(_BYTE *)(v9 + 4) || _tlgGuidIsZero((const struct _GUID *)(v9 + 24)) )
        v10 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)&unk_180152A1B,
        v9 + 8,
        v10,
        (__int64)v18,
        (__int64)&v16,
        (__int64)&v17,
        (__int64)&v19);
    }
  }
  else
  {
    wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
    v11 = CloudRestoreLauncherTelemetry::Provider();
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x800000000000LL) )
    {
      v18[0] = a2;
      v13 = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v19 = v13;
      v17 = 0x1000000;
      if ( !*(_BYTE *)(v14 + 4) || _tlgGuidIsZero((const struct _GUID *)(v14 + 24)) )
        v15 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v12,
        (unsigned int)&unk_180152A9F,
        v14 + 8,
        v15,
        (__int64)&v17,
        (__int64)&v19,
        (__int64)v18);
    }
  }
  wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180040bf0  mov     [rsp-18h+arg_0], rbx
0x180040bf5  mov     [rsp-18h+arg_8], rsi
0x180040bfa  push    rbp
0x180040bfb  push    rdi
0x180040bfc  push    r14
0x180040bfe  mov     rbp, rsp
0x180040c01  sub     rsp, 60h
0x180040c05  mov     r14d, r8d
0x180040c08  mov     rsi, rdx
0x180040c0b  mov     rbx, rcx
0x180040c0e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry>::GetImpl(void)'::`2'::impl
0x180040c15  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry>::__private_IsEnabled(void)
0x180040c1a  mov     rcx, rbx
0x180040c1d  test    al, al
0x180040c1f  jz      loc_180040CCC
0x180040c25  call    ?zInternalStart@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180040c2a  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x180040c2f  mov     rdi, rax
0x180040c32  mov     ecx, [rax]
0x180040c34  cmp     ecx, 5
0x180040c37  jbe     loc_180040D59
0x180040c3d  mov     rdx, 800000000000h
0x180040c47  mov     rcx, rax
0x180040c4a  call    _tlgKeywordOn
0x180040c4f  test    al, al
0x180040c51  jz      loc_180040D59
0x180040c57  mov     [rbp+arg_18], r14d
0x180040c5b  mov     [rbp+var_18], rsi
0x180040c5f  call    cs:__imp_GetCurrentThreadId
0x180040c65  mov     r8, [rbx+110h]
0x180040c6c  mov     [rbp+var_20], eax
0x180040c6f  mov     [rbp+var_10], 1000000h
0x180040c77  cmp     byte ptr [r8+4], 0
0x180040c7c  jz      short loc_180040C8B
0x180040c7e  lea     rcx, [r8+18h]; struct _GUID *
0x180040c82  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180040c87  test    al, al
0x180040c89  jz      short loc_180040C8D
0x180040c8b  xor     ecx, ecx
0x180040c8d  lea     rax, [rbp+arg_18]
0x180040c91  mov     r9, rcx
0x180040c94  mov     [rsp+60h+var_28], rax
0x180040c99  lea     rdx, unk_180152A1B
0x180040ca0  lea     rax, [rbp+var_18]
0x180040ca4  add     r8, 8
0x180040ca8  mov     [rsp+60h+var_30], rax
0x180040cad  mov     rcx, rdi
0x180040cb0  lea     rax, [rbp+var_20]
0x180040cb4  mov     [rsp+60h+var_38], rax
0x180040cb9  lea     rax, [rbp+var_10]
0x180040cbd  mov     [rsp+60h+var_40], rax
0x180040cc2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180040cc7  jmp     loc_180040D59
0x180040ccc  call    ?zInternalStart@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180040cd1  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x180040cd6  mov     rdi, rax
0x180040cd9  mov     ecx, [rax]
0x180040cdb  cmp     ecx, 5
0x180040cde  jbe     short loc_180040D59
0x180040ce0  mov     rdx, 800000000000h
0x180040cea  mov     rcx, rax
0x180040ced  call    _tlgKeywordOn
0x180040cf2  test    al, al
0x180040cf4  jz      short loc_180040D59
0x180040cf6  mov     [rbp+var_10], rsi
0x180040cfa  call    cs:__imp_GetCurrentThreadId
0x180040d00  mov     r8, [rbx+110h]
0x180040d07  mov     [rbp+arg_18], eax
0x180040d0a  mov     [rbp+var_18], 1000000h
0x180040d12  cmp     byte ptr [r8+4], 0
0x180040d17  jz      short loc_180040D26
0x180040d19  lea     rcx, [r8+18h]; struct _GUID *
0x180040d1d  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180040d22  test    al, al
0x180040d24  jz      short loc_180040D28
0x180040d26  xor     ecx, ecx
0x180040d28  lea     rax, [rbp+var_10]
0x180040d2c  mov     r9, rcx
0x180040d2f  mov     [rsp+60h+var_30], rax
0x180040d34  lea     rdx, unk_180152A9F
0x180040d3b  lea     rax, [rbp+arg_18]
0x180040d3f  add     r8, 8
0x180040d43  mov     [rsp+60h+var_38], rax
0x180040d48  mov     rcx, rdi
0x180040d4b  lea     rax, [rbp+var_18]
0x180040d4f  mov     [rsp+60h+var_40], rax
0x180040d54  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180040d59  mov     rcx, rbx
0x180040d5c  lea     r11, [rsp+60h+var_s0]
0x180040d61  mov     rbx, [r11+20h]
0x180040d65  mov     rsi, [r11+28h]
0x180040d69  mov     rsp, r11
0x180040d6c  pop     r14
0x180040d6e  pop     rdi
0x180040d6f  pop     rbp
0x180040d70  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
