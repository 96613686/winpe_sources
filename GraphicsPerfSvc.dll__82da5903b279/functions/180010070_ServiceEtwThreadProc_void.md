# ServiceEtwThreadProc(void)

- ea: `0x180010070`
- end: `0x1800102d8`
- name: `?ServiceEtwThreadProc@@YAXXZ`
- size: `616`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task`

## callers

- `0x18000e8e0`

## callees

- `0x180001108`
- `0x1800018ac`
- `0x180003ab0`
- `0x18000cd2c`
- `0x18000e79c`
- `0x18000fbbc`
- `0x180010070`
- `0x1800107b0`
- `0x180013ad0`
- `0x1800193d4`
- `0x1800196c4`
- `0x18001a850`
- `0x18001c0c0`
- `0x180026b48`
- `0x180026c04`

## string_xrefs

- `0x180010095`: `ServiceEtwThread`
- `0x1800100b9`: `ServiceEtwThread starting`
- `0x18001028f`: `ServiceEtwThread stopping`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void ServiceEtwThreadProc(void)
{
  const struct _tlgProvider_t *v0; // rax
  __int64 v1; // r10
  PresentTraceConsumerCore *v2; // rbx
  __int64 v3; // xmm6_8
  int v4; // esi
  __int64 v5; // rdx
  __int64 v6; // r8
  PresentTraceConsumerCore *v7; // rbx
  __int64 v8; // [rsp+30h] [rbp-118h] BYREF
  __int64 v9; // [rsp+38h] [rbp-110h] BYREF
  _DWORD v10[4]; // [rsp+40h] [rbp-108h] BYREF
  struct _GUID v11; // [rsp+50h] [rbp-F8h] BYREF
  _BYTE v12[80]; // [rsp+60h] [rbp-E8h] BYREF
  _BYTE v13[32]; // [rsp+B0h] [rbp-98h] BYREF
  __int128 v14; // [rsp+D0h] [rbp-78h] BYREF
  char *v15; // [rsp+E0h] [rbp-68h]
  __int64 v16; // [rsp+E8h] [rbp-60h]
  __int64 *v17; // [rsp+F0h] [rbp-58h]
  __int64 v18; // [rsp+F8h] [rbp-50h]
  char *v19; // [rsp+100h] [rbp-48h]
  __int64 v20; // [rsp+108h] [rbp-40h]
  __int64 *v21; // [rsp+110h] [rbp-38h]
  __int64 v22; // [rsp+118h] [rbp-30h]

  gpm::TraceProvider::WatchCurrentThread(v12, "ServiceEtwThread");
  v11 = GUID_NULL;
  TelemetrySink::LogDiagnostic((TelemetrySink *)&g::TelemetrySink, L"ServiceEtwThread starting", &v11);
  v0 = gpm::TraceProvider::Provider();
  if ( *(_DWORD *)v0 > 5u && (unsigned __int8)tlgKeywordOn(v0, 0x400000000000LL) )
  {
    v21 = &v8;
    v22 = 4;
    v19 = (char *)&v8 + 4;
    v20 = 4;
    v17 = &v9;
    v18 = 4;
    v15 = (char *)&v9 + 4;
    v16 = 4;
    *(_QWORD *)&v14 = v10;
    *((_QWORD *)&v14 + 1) = 8;
    tlgWriteTransfer_EventWriteTransfer(
      v1,
      byte_180039DA5,
      0,
      0,
      7,
      v13,
      __PAIR64__(g::config, dword_180042D54),
      0x100000001LL,
      0x1000000);
  }
  v2 = g::spTraceConsumer;
  v3 = *((_QWORD *)g::spTraceConsumer + 36);
  v4 = *((_DWORD *)g::spTraceConsumer + 74);
  try
  {
    v10[0] = GetBufferSizeOverride();
    *(_QWORD *)&v10[1] = v3;
    v10[3] = v4;
    TraceSession::Start((PresentTraceConsumerCore *)((char *)v2 + 16), (struct Properties)v10);
  }
  catch ( ... )
  {
    goto LABEL_8;
  }
  try
  {
    v7 = g::spTraceConsumer;
    if ( !*((_BYTE *)g::spTraceConsumer + 152) )
    {
      v14 = 0;
      v15 = 0;
      LOBYTE(v6) = 3;
      LOBYTE(v5) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetImpl'::`2'::impl,
        v5,
        v6);
      PresentTraceConsumerCore::EnableProviders(v7);
      std::vector<unsigned short>::_Tidy(&v14);
    }
    TraceSession::OpenTrace((PresentTraceConsumerCore *)((char *)v7 + 16), v7);
    *((_DWORD *)v7 + 100) = 1;
  }
  catch ( ... )
  {
    goto LABEL_8;
  }
  try
  {
    PresentTraceConsumerCore::Process(g::spTraceConsumer);
  }
  catch ( ... )
  {
  }
LABEL_8:
  v11 = GUID_NULL;
  TelemetrySink::LogDiagnostic((TelemetrySink *)&g::TelemetrySink, L"ServiceEtwThread stopping", &v11);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v12);
}

```

## disassembly

```asm
0x180010070  mov     rax, rsp
0x180010073  mov     [rax+8], rbx
0x180010077  push    rsi
0x180010078  sub     rsp, 140h
0x18001007f  movaps  xmmword ptr [rax-18h], xmm6
0x180010083  mov     rax, cs:__security_cookie
0x18001008a  xor     rax, rsp
0x18001008d  mov     [rsp+148h+var_28], rax
0x180010095  lea     rdx, aServiceetwthre_0; "ServiceEtwThread"
0x18001009c  lea     rcx, [rsp+148h+var_E8]
0x1800100a1  call    ?WatchCurrentThread@TraceProvider@gpm@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; gpm::TraceProvider::WatchCurrentThread(char const *)
0x1800100a6  nop
0x1800100a7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800100ae  movdqu  xmmword ptr [rsp+148h+var_F8.Data1], xmm0
0x1800100b4  lea     r8, [rsp+148h+var_F8]; struct _GUID
0x1800100b9  lea     rdx, aServiceetwthre_1; "ServiceEtwThread starting"
0x1800100c0  lea     rcx, ?TelemetrySink@g@@3U0@A; this
0x1800100c7  call    ?LogDiagnostic@TelemetrySink@@UEAAXPEBGU_GUID@@@Z; TelemetrySink::LogDiagnostic(ushort const *,_GUID)
0x1800100cc  call    ?Provider@TraceProvider@gpm@@SAPEBU_tlgProvider_t@@XZ; gpm::TraceProvider::Provider(void)
0x1800100d1  mov     r10, rax
0x1800100d4  mov     ecx, [rax]
0x1800100d6  cmp     ecx, 5
0x1800100d9  jbe     loc_1800101CE
0x1800100df  mov     rdx, 400000000000h
0x1800100e9  mov     rcx, rax
0x1800100ec  call    _tlgKeywordOn
0x1800100f1  test    al, al
0x1800100f3  jz      loc_1800101CE
0x1800100f9  mov     ecx, cs:dword_180042D54
0x1800100ff  mov     dword ptr [rsp+148h+var_118], ecx
0x180010103  mov     eax, cs:?config@g@@3UConfig@PresentTraceConsumerCore@@A; PresentTraceConsumerCore::Config g::config
0x180010109  mov     dword ptr [rsp+148h+var_118+4], eax
0x18001010d  mov     dword ptr [rsp+148h+var_110], 1
0x180010115  mov     dword ptr [rsp+148h+var_110+4], 1
0x18001011d  mov     qword ptr [rsp+148h+var_108], 1000000h
0x180010126  lea     rax, [rsp+148h+var_118]
0x18001012b  mov     [rsp+148h+var_38], rax
0x180010133  mov     [rsp+148h+var_30], 4
0x18001013f  lea     rax, [rsp+148h+var_118+4]
0x180010144  mov     [rsp+148h+var_48], rax
0x18001014c  mov     [rsp+148h+var_40], 4
0x180010158  lea     rax, [rsp+148h+var_110]
0x18001015d  mov     [rsp+148h+var_58], rax
0x180010165  mov     [rsp+148h+var_50], 4
0x180010171  lea     rax, [rsp+148h+var_110+4]
0x180010176  mov     [rsp+148h+var_68], rax
0x18001017e  mov     [rsp+148h+var_60], 4
0x18001018a  lea     rax, [rsp+148h+var_108]
0x18001018f  mov     qword ptr [rsp+148h+var_78], rax
0x180010197  mov     qword ptr [rsp+148h+var_78+8], 8
0x1800101a3  lea     rax, [rsp+148h+var_98]
0x1800101ab  mov     [rsp+148h+var_120], rax
0x1800101b0  mov     [rsp+148h+var_128], 7
0x1800101b8  xor     r9d, r9d
0x1800101bb  xor     r8d, r8d
0x1800101be  lea     rdx, byte_180039DA5
0x1800101c5  mov     rcx, r10
0x1800101c8  call    _tlgWriteTransfer_EventWriteTransfer
0x1800101cd  nop
0x1800101ce  mov     rbx, cs:?spTraceConsumer@g@@3V?$shared_ptr@UServiceTraceConsumer@@@std@@A; std::shared_ptr<ServiceTraceConsumer> g::spTraceConsumer
0x1800101d5  movsd   xmm6, qword ptr [rbx+120h]
0x1800101dd  mov     esi, [rbx+128h]
0x1800101e3  mov     ecx, [rbx+11Ch]
0x1800101e9  call    GetBufferSizeOverride
0x1800101ee  mov     dword ptr [rsp+148h+var_108], eax
0x1800101f2  movsd   qword ptr [rsp+148h+var_108+4], xmm6
0x1800101f8  mov     [rsp+148h+var_FC], esi
0x1800101fc  lea     rcx, [rbx+10h]; this
0x180010200  lea     rdx, [rsp+148h+var_108]; struct Properties
0x180010205  call    ?Start@TraceSession@@QEAAXUProperties@1@@Z; TraceSession::Start(TraceSession::Properties)
0x18001020a  nop
0x18001020b  mov     rbx, cs:?spTraceConsumer@g@@3V?$shared_ptr@UServiceTraceConsumer@@@std@@A; std::shared_ptr<ServiceTraceConsumer> g::spTraceConsumer
0x180010212  cmp     byte ptr [rbx+98h], 0
0x180010219  jnz     short loc_18001025A
0x18001021b  xorps   xmm0, xmm0
0x18001021e  movdqu  [rsp+148h+var_78], xmm0
0x180010227  mov     [rsp+148h+var_68], 0
0x180010233  mov     r8b, 3
0x180010236  mov     dl, 1
0x180010238  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking> `wil::Feature<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetImpl(void)'::`2'::impl
0x18001023f  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180010244  mov     rcx, rbx; this
0x180010247  call    ?EnableProviders@PresentTraceConsumerCore@@AEAAXXZ; PresentTraceConsumerCore::EnableProviders(void)
0x18001024c  nop
0x18001024d  lea     rcx, [rsp+148h+var_78]
0x180010255  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18001025a  lea     rcx, [rbx+10h]; this
0x18001025e  mov     rdx, rbx; struct ITraceConsumer *
0x180010261  call    ?OpenTrace@TraceSession@@QEAAXPEAUITraceConsumer@@@Z; TraceSession::OpenTrace(ITraceConsumer *)
0x180010266  mov     dword ptr [rbx+190h], 1
0x180010270  mov     rcx, cs:?spTraceConsumer@g@@3V?$shared_ptr@UServiceTraceConsumer@@@std@@A; this
0x180010277  call    ?Process@PresentTraceConsumerCore@@QEAAXXZ; PresentTraceConsumerCore::Process(void)
0x18001027c  nop
0x18001027d  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180010284  movdqu  xmmword ptr [rsp+148h+var_F8.Data1], xmm0
0x18001028a  lea     r8, [rsp+148h+var_F8]; struct _GUID
0x18001028f  lea     rdx, aServiceetwthre; "ServiceEtwThread stopping"
0x180010296  lea     rcx, ?TelemetrySink@g@@3U0@A; this
0x18001029d  call    ?LogDiagnostic@TelemetrySink@@UEAAXPEBGU_GUID@@@Z; TelemetrySink::LogDiagnostic(ushort const *,_GUID)
0x1800102a2  nop
0x1800102a3  lea     rcx, [rsp+148h+var_E8]; this
0x1800102a8  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800102ad  mov     rcx, [rsp+148h+var_28]
0x1800102b5  xor     rcx, rsp; StackCookie
0x1800102b8  call    __security_check_cookie
0x1800102bd  lea     r11, [rsp+148h+var_8]
0x1800102c5  mov     rbx, [r11+10h]
0x1800102c9  movaps  xmm6, xmmword ptr [r11-10h]
0x1800102ce  mov     rsp, r11
0x1800102d1  pop     rsi
0x1800102d2  retn
0x1800102d3  jmp     short loc_18001027D
0x1800102d5  jmp     short loc_18001027D
```
