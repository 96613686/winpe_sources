# UsageAndQualityInsights::Ingestion::MetricEventsFetcher::FetchMetricEvents(unsigned __int64)

- ea: `0x180019f6c`
- end: `0x18001a117`
- name: `?FetchMetricEvents@MetricEventsFetcher@Ingestion@UsageAndQualityInsights@@SA?AU?$pair@V?$vector@UMetricEvent@Utilities@UsageAndQualityInsights@@V?$allocator@UMetricEvent@Utilities@UsageAndQualityInsights@@@std@@@std@@_K@std@@_K@Z`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180015930`

## callees

- `0x18001411c`
- `0x180016628`
- `0x180016d2c`
- `0x180019a58`
- `0x180019cc0`
- `0x180019f6c`
- `0x18001a120`
- `0x1800e42e0`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x18001a04f`
- `RPCRT4!RpcBindingFree` at `0x18001a04f`

## string_xrefs

- `0x18001a0f0`: `onecore\base\usageandqualityinsights\service\lib\ingestion\metriceventsfetcher.cpp`
- `0x18001a105`: `onecore\base\usageandqualityinsights\service\lib\ingestion\metriceventsfetcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall UsageAndQualityInsights::Ingestion::MetricEventsFetcher::FetchMetricEvents(
        _QWORD *a1,
        unsigned __int64 a2)
{
  int Metrics; // eax
  int v5; // eax
  unsigned __int64 v6; // r8
  __int64 i; // rdx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  int v12; // [rsp+20h] [rbp-19h]
  int v13; // [rsp+20h] [rbp-19h]
  void **v14; // [rsp+38h] [rbp-1h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp+7h] BYREF
  __int64 v16; // [rsp+48h] [rbp+Fh] BYREF
  __int64 v17; // [rsp+50h] [rbp+17h]
  __int64 v18; // [rsp+58h] [rbp+1Fh]
  unsigned __int64 v19; // [rsp+60h] [rbp+27h] BYREF
  struct tagMetricsRecord *v20; // [rsp+68h] [rbp+2Fh]
  unsigned int v21; // [rsp+70h] [rbp+37h]
  _QWORD v22[2]; // [rsp+78h] [rbp+3Fh] BYREF
  int v23; // [rsp+88h] [rbp+4Fh]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]
  unsigned int v25; // [rsp+B0h] [rbp+77h] BYREF
  struct tagMetricsRecord *v26; // [rsp+B8h] [rbp+7Fh] BYREF

  Binding = 0;
  v14 = &Microsoft::Diagnostics::UtcMetricsApiWrapper::`vftable';
  Microsoft::Diagnostics::UtcWrapperBase::Initialize((RPC_BINDING_HANDLE *)&v14);
  v26 = 0;
  v25 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl'::`2'::impl) )
  {
    Metrics = Microsoft::Diagnostics::UtcMetricsApiWrapper::GetMetrics(
                (Microsoft::Diagnostics::UtcMetricsApiWrapper *)&v14,
                L"USAGEANDQUALITYINSIGHTSV2",
                a2,
                &v26,
                &v25);
    if ( Metrics < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\ingestion\\metriceventsfetcher.cpp",
        (const char *)(unsigned int)Metrics,
        v12);
  }
  else
  {
    v5 = Microsoft::Diagnostics::UtcMetricsApiWrapper::GetMetrics(
           (Microsoft::Diagnostics::UtcMetricsApiWrapper *)&v14,
           L"USAGEANDQUALITYINSIGHTS",
           a2,
           &v26,
           &v25);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\ingestion\\metriceventsfetcher.cpp",
        (const char *)(unsigned int)v5,
        v13);
  }
  v22[0] = a2;
  v20 = v26;
  v21 = v25;
  v19 = a2;
  v22[1] = 0;
  v23 = 0;
  UsageAndQualityInsights::Ingestion::MetricDataRecords::~MetricDataRecords((UsageAndQualityInsights::Ingestion::MetricDataRecords *)v22);
  v14 = &Microsoft::Diagnostics::UtcMetricsApiWrapper::`vftable';
  if ( Binding )
    RpcBindingFree(&Binding);
  UsageAndQualityInsights::Ingestion::MetricDataRecords::AsMetricEvents(&v19, &v16);
  v6 = v19;
  for ( i = 0; (unsigned int)i < v21; i = (unsigned int)(i + 1) )
  {
    if ( *((_QWORD *)v20 + 3 * i) + 1LL >= v6 )
      v6 = *((_QWORD *)v20 + 3 * i) + 1LL;
  }
  v8 = v18;
  v18 = 0;
  v9 = v17;
  v17 = 0;
  v10 = v16;
  v16 = 0;
  *a1 = v10;
  a1[1] = v9;
  a1[2] = v8;
  a1[3] = v6;
  std::vector<UsageAndQualityInsights::Utilities::MetricEvent>::~vector<UsageAndQualityInsights::Utilities::MetricEvent>(&v16);
  UsageAndQualityInsights::Ingestion::MetricDataRecords::~MetricDataRecords((UsageAndQualityInsights::Ingestion::MetricDataRecords *)&v19);
  return a1;
}

```

## disassembly

```asm
0x180019f6c  mov     [rsp-8+arg_0], rbx
0x180019f71  mov     [rsp-8+arg_8], rdi
0x180019f76  push    rbp
0x180019f77  lea     rbp, [rsp-57h]
0x180019f7c  sub     rsp, 90h
0x180019f83  mov     rdi, rdx
0x180019f86  mov     rbx, rcx
0x180019f89  mov     [rbp+57h+Binding], 0
0x180019f91  lea     rax, ??_7UtcMetricsApiWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcMetricsApiWrapper::`vftable'
0x180019f98  mov     [rbp+57h+var_58], rax
0x180019f9c  lea     rcx, [rbp+57h+var_58]; this
0x180019fa0  call    ?Initialize@UtcWrapperBase@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::UtcWrapperBase::Initialize(void)
0x180019fa5  mov     [rbp+57h+arg_18], 0
0x180019fad  mov     [rbp+57h+arg_10], 0
0x180019fb4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport> `wil::Feature<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::GetImpl(void)'::`2'::impl
0x180019fbb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UtcExtendedMetricsSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UtcExtendedMetricsSupport>::__private_IsEnabled(void)
0x180019fc0  lea     r9, [rbp+57h+arg_18]; struct tagMetricsRecord **
0x180019fc4  mov     r8, rdi; unsigned __int64
0x180019fc7  lea     rcx, [rbp+57h+var_58]; this
0x180019fcb  test    al, al
0x180019fcd  lea     rax, [rbp+57h+arg_10]
0x180019fd1  mov     qword ptr [rsp+90h+var_70], rax; int
0x180019fd6  jz      short loc_180019FF2
0x180019fd8  lea     rdx, aUsageandqualit_0; "USAGEANDQUALITYINSIGHTSV2"
0x180019fdf  call    ?GetMetrics@UtcMetricsApiWrapper@Diagnostics@Microsoft@@QEBAJPEB_W_KPEAPEAUtagMetricsRecord@@PEAK@Z; Microsoft::Diagnostics::UtcMetricsApiWrapper::GetMetrics(wchar_t const *,unsigned __int64,tagMetricsRecord * *,ulong *)
0x180019fe4  mov     rcx, [rbp+5Fh]; this
0x180019fe8  test    eax, eax
0x180019fea  js      loc_18001A102
0x180019ff0  jmp     short loc_18001A00A
0x180019ff2  lea     rdx, aUsageandqualit_2; "USAGEANDQUALITYINSIGHTS"
0x180019ff9  call    ?GetMetrics@UtcMetricsApiWrapper@Diagnostics@Microsoft@@QEBAJPEB_W_KPEAPEAUtagMetricsRecord@@PEAK@Z; Microsoft::Diagnostics::UtcMetricsApiWrapper::GetMetrics(wchar_t const *,unsigned __int64,tagMetricsRecord * *,ulong *)
0x180019ffe  mov     rcx, [rbp+5Fh]; this
0x18001a002  test    eax, eax
0x18001a004  js      loc_18001A0ED
0x18001a00a  mov     [rbp+57h+var_18], rdi
0x18001a00e  mov     rax, [rbp+57h+arg_18]
0x18001a012  mov     [rbp+57h+var_28], rax
0x18001a016  mov     eax, [rbp+57h+arg_10]
0x18001a019  mov     [rbp+57h+var_20], eax
0x18001a01c  mov     [rbp+57h+var_30], rdi
0x18001a020  mov     [rbp+57h+var_10], 0
0x18001a028  mov     [rbp+57h+var_8], 0
0x18001a02f  lea     rcx, [rbp+57h+var_18]; this
0x18001a033  call    ??1MetricDataRecords@Ingestion@UsageAndQualityInsights@@QEAA@XZ; UsageAndQualityInsights::Ingestion::MetricDataRecords::~MetricDataRecords(void)
0x18001a038  nop
0x18001a039  lea     rax, ??_7UtcMetricsApiWrapper@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcMetricsApiWrapper::`vftable'
0x18001a040  mov     [rbp+57h+var_58], rax
0x18001a044  cmp     [rbp+57h+Binding], 0
0x18001a049  jz      short loc_18001A056
0x18001a04b  lea     rcx, [rbp+57h+Binding]; Binding
0x18001a04f  call    cs:__imp_RpcBindingFree
0x18001a055  nop
0x18001a056  lea     rdx, [rbp+57h+var_48]
0x18001a05a  lea     rcx, [rbp+57h+var_30]
0x18001a05e  call    ?AsMetricEvents@MetricDataRecords@Ingestion@UsageAndQualityInsights@@QEBA?AV?$vector@UMetricEvent@Utilities@UsageAndQualityInsights@@V?$allocator@UMetricEvent@Utilities@UsageAndQualityInsights@@@std@@@std@@XZ; UsageAndQualityInsights::Ingestion::MetricDataRecords::AsMetricEvents(void)
0x18001a063  mov     r8, [rbp+57h+var_30]
0x18001a067  xor     edx, edx
0x18001a069  mov     r9d, [rbp+57h+var_20]
0x18001a06d  test    r9d, r9d
0x18001a070  jz      short loc_18001A08F
0x18001a072  mov     r10, [rbp+57h+var_28]
0x18001a076  lea     rcx, [rdx+rdx*2]
0x18001a07a  mov     rax, [r10+rcx*8]
0x18001a07e  inc     rax
0x18001a081  cmp     rax, r8
0x18001a084  cmovnb  r8, rax
0x18001a088  inc     edx
0x18001a08a  cmp     edx, r9d
0x18001a08d  jb      short loc_18001A076
0x18001a08f  mov     rdx, [rbp+57h+var_38]
0x18001a093  mov     [rbp+57h+var_38], 0
0x18001a09b  mov     rcx, [rbp+57h+var_40]
0x18001a09f  mov     [rbp+57h+var_40], 0
0x18001a0a7  mov     rax, [rbp+57h+var_48]
0x18001a0ab  mov     [rbp+57h+var_48], 0
0x18001a0b3  mov     [rbx], rax
0x18001a0b6  mov     [rbx+8], rcx
0x18001a0ba  mov     [rbx+10h], rdx
0x18001a0be  mov     [rbx+18h], r8
0x18001a0c2  lea     rcx, [rbp+57h+var_48]
0x18001a0c6  call    ??1?$vector@UMetricEvent@Utilities@UsageAndQualityInsights@@V?$allocator@UMetricEvent@Utilities@UsageAndQualityInsights@@@std@@@std@@QEAA@XZ; std::vector<UsageAndQualityInsights::Utilities::MetricEvent>::~vector<UsageAndQualityInsights::Utilities::MetricEvent>(void)
0x18001a0cb  nop
0x18001a0cc  lea     rcx, [rbp+57h+var_30]; this
0x18001a0d0  call    ??1MetricDataRecords@Ingestion@UsageAndQualityInsights@@QEAA@XZ; UsageAndQualityInsights::Ingestion::MetricDataRecords::~MetricDataRecords(void)
0x18001a0d5  mov     rax, rbx
0x18001a0d8  lea     r11, [rsp+90h+var_s0]
0x18001a0e0  mov     rbx, [r11+10h]
0x18001a0e4  mov     rdi, [r11+18h]
0x18001a0e8  mov     rsp, r11
0x18001a0eb  pop     rbp
0x18001a0ec  retn
0x18001a0ed  mov     r9d, eax; char *
0x18001a0f0  lea     r8, aOnecoreBaseUsa_6; "onecore\\base\\usageandqualityinsights"...
0x18001a0f7  mov     edx, 65h ; 'e'; void *
0x18001a0fc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a102  mov     r9d, eax; char *
0x18001a105  lea     r8, aOnecoreBaseUsa_6; "onecore\\base\\usageandqualityinsights"...
0x18001a10c  mov     edx, 61h ; 'a'; void *
0x18001a111  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
