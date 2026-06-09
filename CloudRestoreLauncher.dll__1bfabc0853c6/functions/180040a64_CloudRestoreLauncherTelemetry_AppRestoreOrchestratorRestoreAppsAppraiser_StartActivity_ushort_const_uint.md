# CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreAppsAppraiser::StartActivity(ushort const *,uint)

- ea: `0x180040a64`
- end: `0x180040be9`
- name: `?StartActivity@AppRestoreOrchestratorRestoreAppsAppraiser@CloudRestoreLauncherTelemetry@@QEAAXPEBGI@Z`
- size: `389`
- prototype: `void __fastcall(CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreAppsAppraiser *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180036f74`

## callees

- `0x180001edc`
- `0x180003160`
- `0x180003224`
- `0x180017a5c`
- `0x1800195cc`
- `0x18001d124`
- `0x180024574`
- `0x180040a64`
- `0x180043da0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180040ad3`
- `KERNEL32!GetCurrentThreadId` at `0x180040b6e`
- `KERNEL32!GetCurrentThreadId` at `0x180040ad3`
- `KERNEL32!GetCurrentThreadId` at `0x180040b6e`

## pseudocode

```c
void __fastcall CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreAppsAppraiser::StartActivity(
        CloudRestoreLauncherTelemetry::AppRestoreOrchestratorRestoreAppsAppraiser *this,
        const unsigned __int16 *a2,
        DWORD a3)
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
  DWORD v20; // [rsp+40h] [rbp-20h] BYREF
  __int64 v21; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v22[2]; // [rsp+50h] [rbp-10h] BYREF
  DWORD v23; // [rsp+98h] [rbp+38h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry>::GetImpl'::`2'::impl) )
  {
    wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
    v6 = CloudRestoreLauncherTelemetry::Provider();
    v9 = (int)v6;
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x800000000000LL, v7, v8) )
    {
      v23 = a3;
      v21 = (__int64)a2;
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      v20 = CurrentThreadId;
      v22[0] = 0x1000000;
      if ( !*(_BYTE *)(v11 + 4) || _tlgGuidIsZero((const struct _GUID *)(v11 + 24)) )
        v12 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)byte_1801525FD,
        v11 + 8,
        v12,
        (__int64)v22,
        (__int64)&v20,
        (__int64)&v21,
        (__int64)&v23);
    }
  }
  else
  {
    wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(this);
    v13 = CloudRestoreLauncherTelemetry::Provider();
    v16 = (int)v13;
    if ( *(_DWORD *)v13 > 5u && (unsigned __int8)tlgKeywordOn(v13, 0x800000000000LL, v14, v15) )
    {
      v22[0] = a2;
      v17 = GetCurrentThreadId();
      v18 = *((_QWORD *)this + 34);
      v23 = v17;
      v21 = 0x1000000;
      if ( !*(_BYTE *)(v18 + 4) || _tlgGuidIsZero((const struct _GUID *)(v18 + 24)) )
        v19 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v16,
        (unsigned int)word_180152582,
        v18 + 8,
        v19,
        (__int64)&v21,
        (__int64)&v23,
        (__int64)v22);
    }
  }
  wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(this);
}

```

## disassembly

```asm
0x180040a64  mov     [rsp-18h+arg_0], rbx
0x180040a69  mov     [rsp-18h+arg_8], rsi
0x180040a6e  push    rbp
0x180040a6f  push    rdi
0x180040a70  push    r14
0x180040a72  mov     rbp, rsp
0x180040a75  sub     rsp, 60h
0x180040a79  mov     r14d, r8d
0x180040a7c  mov     rsi, rdx
0x180040a7f  mov     rbx, rcx
0x180040a82  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry> `wil::Feature<__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry>::GetImpl(void)'::`2'::impl
0x180040a89  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommercialCloudAppRestore_AccountTypeTelemetry>::__private_IsEnabled(void)
0x180040a8e  mov     rcx, rbx
0x180040a91  test    al, al
0x180040a93  jz      loc_180040B40
0x180040a99  call    ?zInternalStart@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180040a9e  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x180040aa3  mov     rdi, rax
0x180040aa6  mov     ecx, [rax]
0x180040aa8  cmp     ecx, 5
0x180040aab  jbe     loc_180040BCD
0x180040ab1  mov     rdx, 800000000000h
0x180040abb  mov     rcx, rax
0x180040abe  call    _tlgKeywordOn
0x180040ac3  test    al, al
0x180040ac5  jz      loc_180040BCD
0x180040acb  mov     [rbp+arg_18], r14d
0x180040acf  mov     [rbp+var_18], rsi
0x180040ad3  call    cs:__imp_GetCurrentThreadId
0x180040ad9  mov     r8, [rbx+110h]
0x180040ae0  mov     [rbp+var_20], eax
0x180040ae3  mov     [rbp+var_10], 1000000h
0x180040aeb  cmp     byte ptr [r8+4], 0
0x180040af0  jz      short loc_180040AFF
0x180040af2  lea     rcx, [r8+18h]; struct _GUID *
0x180040af6  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180040afb  test    al, al
0x180040afd  jz      short loc_180040B01
0x180040aff  xor     ecx, ecx
0x180040b01  lea     rax, [rbp+arg_18]
0x180040b05  mov     r9, rcx
0x180040b08  mov     [rsp+60h+var_28], rax
0x180040b0d  lea     rdx, byte_1801525FD
0x180040b14  lea     rax, [rbp+var_18]
0x180040b18  add     r8, 8
0x180040b1c  mov     [rsp+60h+var_30], rax
0x180040b21  mov     rcx, rdi
0x180040b24  lea     rax, [rbp+var_20]
0x180040b28  mov     [rsp+60h+var_38], rax
0x180040b2d  lea     rax, [rbp+var_10]
0x180040b31  mov     [rsp+60h+var_40], rax
0x180040b36  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180040b3b  jmp     loc_180040BCD
0x180040b40  call    ?zInternalStart@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180040b45  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x180040b4a  mov     rdi, rax
0x180040b4d  mov     ecx, [rax]
0x180040b4f  cmp     ecx, 5
0x180040b52  jbe     short loc_180040BCD
0x180040b54  mov     rdx, 800000000000h
0x180040b5e  mov     rcx, rax
0x180040b61  call    _tlgKeywordOn
0x180040b66  test    al, al
0x180040b68  jz      short loc_180040BCD
0x180040b6a  mov     [rbp+var_10], rsi
0x180040b6e  call    cs:__imp_GetCurrentThreadId
0x180040b74  mov     r8, [rbx+110h]
0x180040b7b  mov     [rbp+arg_18], eax
0x180040b7e  mov     [rbp+var_18], 1000000h
0x180040b86  cmp     byte ptr [r8+4], 0
0x180040b8b  jz      short loc_180040B9A
0x180040b8d  lea     rcx, [r8+18h]; struct _GUID *
0x180040b91  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180040b96  test    al, al
0x180040b98  jz      short loc_180040B9C
0x180040b9a  xor     ecx, ecx
0x180040b9c  lea     rax, [rbp+var_10]
0x180040ba0  mov     r9, rcx
0x180040ba3  mov     [rsp+60h+var_30], rax
0x180040ba8  lea     rdx, word_180152582
0x180040baf  lea     rax, [rbp+arg_18]
0x180040bb3  add     r8, 8
0x180040bb7  mov     [rsp+60h+var_38], rax
0x180040bbc  mov     rcx, rdi
0x180040bbf  lea     rax, [rbp+var_18]
0x180040bc3  mov     [rsp+60h+var_40], rax
0x180040bc8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180040bcd  mov     rcx, rbx
0x180040bd0  lea     r11, [rsp+60h+var_s0]
0x180040bd5  mov     rbx, [r11+20h]
0x180040bd9  mov     rsi, [r11+28h]
0x180040bdd  mov     rsp, r11
0x180040be0  pop     r14
0x180040be2  pop     rdi
0x180040be3  pop     rbp
0x180040be4  jmp     ?EnsureWatchingCurrentThread@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::EnsureWatchingCurrentThread(void)
```
