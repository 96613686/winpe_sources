# WxDiagnostics::PowerTelemetry::RecordControlPathWakeInPDCStandby(_WFC_JOB_TYPE)

- ea: `0x1400d76a0`
- end: `0x1400d7969`
- name: `?RecordControlPathWakeInPDCStandby@PowerTelemetry@WxDiagnostics@@QEAAXW4_WFC_JOB_TYPE@@@Z`
- size: `713`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140022eb0`

## callees

- `0x140001008`
- `0x140002120`
- `0x140004d48`
- `0x14000d054`
- `0x14004c0cc`
- `0x1400d50a8`
- `0x1400d5124`
- `0x1400d5420`
- `0x1400d58c8`
- `0x1400d76a0`
- `0x1400d868c`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400d773d`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400d773d`
- `ntoskrnl!DbgPrintEx` at `0x1400d76f2`
- `ntoskrnl!DbgPrintEx` at `0x1400d7759`
- `ntoskrnl!DbgPrintEx` at `0x1400d76f2`
- `ntoskrnl!DbgPrintEx` at `0x1400d7759`

## string_xrefs

- `0x1400d76e8`: `[ToDeveloper]:This debugger break typically because there is a PLDR or Power ref leak issue during sleep session.                    please double check your client driver logic! If it's the known issue, you can 'g' in debugger to continue.\n`
- `0x1400d774f`: `[ToDeveloper]:This debugger break typically because there is a PLDR or Power ref leak issue during sleep session.                    please double check your client driver logic! If it's the known issue, you can 'g' in debugger to continue.\n`

## pseudocode

```c
void __fastcall WxDiagnostics::PowerTelemetry::RecordControlPathWakeInPDCStandby(__int64 a1, unsigned int a2)
{
  __int64 v3; // rcx
  int v5; // edx
  wificx::utils *v6; // rcx
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  const wchar_t *v10; // rax
  int v11; // edx
  int v12; // r8d
  int v13; // ecx
  int v14; // r8d
  __int64 v15; // [rsp+40h] [rbp-10h] BYREF
  __int64 v16; // [rsp+48h] [rbp-8h] BYREF
  __int64 v17; // [rsp+80h] [rbp+30h] BYREF
  const wchar_t *v18; // [rsp+90h] [rbp+40h] BYREF
  __int64 v19; // [rsp+98h] [rbp+48h] BYREF

  v3 = *(unsigned int *)(a1 + 664);
  if ( (unsigned int)(v3 - 2) <= 1 )
  {
    if ( (unsigned int)dword_14010EBA8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14010EBA8, 0x400000000000LL) )
    {
      v17 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 720), 0, 0);
      v18 = MapWificxJobType(a2);
      v19 = *(_QWORD *)(a1 + 432);
      v16 = 2048;
      v15 = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v13,
        (unsigned int)byte_14010501B,
        v14,
        (unsigned int)&v15,
        (__int64)&v16,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v17);
    }
    if ( WxDiagnostics::PowerTelemetry::IsSleepStudyReportEnabled((WxDiagnostics::PowerTelemetry *)a1) )
      WxDiagnostics::PowerTelemetry::LogInfoToPDCStandbyDeviceWakerCollection(a1, 1, a2, 0);
  }
  else if ( (_DWORD)v3 == 1 || (_DWORD)v3 == 4 )
  {
    if ( (unsigned int)dword_14010EBA8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_14010EBA8, 0x400000000000LL) )
    {
      v17 = _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 720), 0, 0);
      v18 = MapWificxJobType(a2);
      v19 = *(_QWORD *)(a1 + 432);
      v15 = 2048;
      v16 = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v8,
        (unsigned int)byte_140104F8B,
        v9,
        (unsigned int)&v16,
        (__int64)&v15,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v17);
    }
    if ( WxDiagnostics::PowerTelemetry::IsSleepStudyReportEnabled((WxDiagnostics::PowerTelemetry *)a1)
      && (int)WxDiagnostics::PowerTelemetry::LogInfoToPDCStandbyDeviceWakerAggregatedCollection(
                a1,
                *(unsigned int *)(a1 + 664),
                1,
                a2) < 0
      && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = MapWificxJobType(a2);
      WPP_RECORDER_SF_Sd(WPP_GLOBAL_Control->DeviceExtension, v11, v12, 36, 0, (__int64)v10, v11);
    }
  }
  else if ( (unsigned int)Feature_55721363__private_IsEnabledDeviceUsageNoInline(v3) )
  {
    DbgPrintEx(
      0x65u,
      0,
      "[ToDeveloper]:This debugger break typically because there is a PLDR or Power ref leak issue during sleep session. "
      "                   please double check your client driver logic! If it's the known issue, you can 'g' in debugger to continue.\n");
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        1,
        38,
        (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids);
    }
    wificx::utils::BreakIfDebuggerIsPresent(v6);
  }
  else if ( KdRefreshDebuggerNotPresent() )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        1,
        39,
        (__int64)WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids);
    }
  }
  else
  {
    DbgPrintEx(
      0x65u,
      0,
      "[ToDeveloper]:This debugger break typically because there is a PLDR or Power ref leak issue during sleep session. "
      "                   please double check your client driver logic! If it's the known issue, you can 'g' in debugger to continue.\n");
    __debugbreak();
  }
}

```

## disassembly

```asm
0x1400d76a0  push    rbp
0x1400d76a2  push    rbx
0x1400d76a3  push    rsi
0x1400d76a4  push    rdi
0x1400d76a5  push    r14
0x1400d76a7  mov     rbp, rsp
0x1400d76aa  sub     rsp, 50h
0x1400d76ae  mov     rdi, rcx
0x1400d76b1  mov     r14d, 1
0x1400d76b7  mov     ecx, [rcx+298h]
0x1400d76bd  mov     esi, edx
0x1400d76bf  lea     eax, [rcx-2]
0x1400d76c2  cmp     eax, r14d
0x1400d76c5  jbe     loc_1400D78AE
0x1400d76cb  cmp     ecx, r14d
0x1400d76ce  jz      loc_1400D77AB
0x1400d76d4  cmp     ecx, 4
0x1400d76d7  jz      loc_1400D77AB
0x1400d76dd  call    Feature_55721363__private_IsEnabledDeviceUsageNoInline
0x1400d76e2  test    eax, eax
0x1400d76e4  jz      short loc_1400D773D
0x1400d76e6  xor     edx, edx; Level
0x1400d76e8  lea     r8, aTodeveloperThi; "[ToDeveloper]:This debugger break typic"...
0x1400d76ef  lea     ecx, [rdx+65h]; ComponentId
0x1400d76f2  call    cs:__imp_DbgPrintEx
0x1400d76f9  nop     dword ptr [rax+rax+00h]
0x1400d76fe  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d7705  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d770c  jz      short loc_1400D7733
0x1400d770e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d7715  lea     rax, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d771c  lea     r9d, [r14+25h]
0x1400d7720  mov     [rsp+50h+var_30], rax
0x1400d7725  mov     r8d, r14d
0x1400d7728  mov     dl, 2
0x1400d772a  mov     rcx, [rcx+40h]
0x1400d772e  call    WPP_RECORDER_SF_
0x1400d7733  call    ?BreakIfDebuggerIsPresent@utils@wificx@@YAXXZ; wificx::utils::BreakIfDebuggerIsPresent(void)
0x1400d7738  jmp     loc_1400D795D
0x1400d773d  call    cs:__imp_KdRefreshDebuggerNotPresent
0x1400d7744  nop     dword ptr [rax+rax+00h]
0x1400d7749  test    al, al
0x1400d774b  jnz     short loc_1400D776B
0x1400d774d  xor     edx, edx; Level
0x1400d774f  lea     r8, aTodeveloperThi; "[ToDeveloper]:This debugger break typic"...
0x1400d7756  lea     ecx, [rdx+65h]; ComponentId
0x1400d7759  call    cs:__imp_DbgPrintEx
0x1400d7760  nop     dword ptr [rax+rax+00h]
0x1400d7765  int     3; Trap to Debugger
0x1400d7766  jmp     loc_1400D795D
0x1400d776b  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d7772  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d7779  jz      loc_1400D795D
0x1400d777f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d7786  lea     rax, WPP_79a4b85c4e0b3b4b75cd37a68e5f6346_Traceguids
0x1400d778d  mov     r9d, 27h ; '''
0x1400d7793  mov     [rsp+50h+var_30], rax
0x1400d7798  mov     r8d, r14d
0x1400d779b  mov     dl, 2
0x1400d779d  mov     rcx, [rcx+40h]
0x1400d77a1  call    WPP_RECORDER_SF_
0x1400d77a6  jmp     loc_1400D795D
0x1400d77ab  mov     eax, cs:dword_14010EBA8
0x1400d77b1  xor     ebx, ebx
0x1400d77b3  cmp     eax, 5
0x1400d77b6  jbe     loc_1400D783D
0x1400d77bc  mov     rdx, 400000000000h
0x1400d77c6  lea     rcx, dword_14010EBA8
0x1400d77cd  call    _tlgKeywordOn
0x1400d77d2  test    al, al
0x1400d77d4  jz      short loc_1400D783D
0x1400d77d6  xor     eax, eax
0x1400d77d8  lock cmpxchg [rdi+2D0h], ebx
0x1400d77e0  movsxd  rcx, eax
0x1400d77e3  mov     [rbp+arg_0], rcx
0x1400d77e7  mov     ecx, esi
0x1400d77e9  call    ?MapWificxJobType@@YAPEBGW4_WFC_JOB_TYPE@@@Z; MapWificxJobType(_WFC_JOB_TYPE)
0x1400d77ee  mov     [rbp+arg_10], rax
0x1400d77f2  lea     r9, [rbp+var_8]
0x1400d77f6  mov     rax, [rdi+1B0h]
0x1400d77fd  lea     rdx, byte_140104F8B
0x1400d7804  mov     [rbp+arg_18], rax
0x1400d7808  lea     rax, [rbp+arg_0]
0x1400d780c  mov     [rsp+50h+var_18], rax
0x1400d7811  lea     rax, [rbp+arg_10]
0x1400d7815  mov     [rsp+50h+var_20], rax
0x1400d781a  lea     rax, [rbp+arg_18]
0x1400d781e  mov     [rsp+50h+var_28], rax
0x1400d7823  lea     rax, [rbp+var_10]
0x1400d7827  mov     [rsp+50h+var_30], rax
0x1400d782c  mov     [rbp+var_10], 800h
0x1400d7834  mov     [rbp+var_8], r14
0x1400d7838  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@G@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@2AEBU?$_tlgWrapSz@G@@32@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1400d783d  mov     rcx, rdi; this
0x1400d7840  call    ?IsSleepStudyReportEnabled@PowerTelemetry@WxDiagnostics@@AEAA_NXZ; WxDiagnostics::PowerTelemetry::IsSleepStudyReportEnabled(void)
0x1400d7845  test    al, al
0x1400d7847  jz      loc_1400D795D
0x1400d784d  mov     edx, [rdi+298h]
0x1400d7853  mov     r9d, esi
0x1400d7856  mov     r8d, r14d
0x1400d7859  mov     dword ptr [rsp+50h+var_30], ebx
0x1400d785d  mov     rcx, rdi
0x1400d7860  call    ?LogInfoToPDCStandbyDeviceWakerAggregatedCollection@PowerTelemetry@WxDiagnostics@@AEAAJW4PowerStateSessionWakeSource@12@W4WIFICX_DATA_OR_IHV_PATH_CONTEXT_TYPE@2@W4_WFC_JOB_TYPE@@W4_NET_WAKE_REASON_TYPE@@@Z; WxDiagnostics::PowerTelemetry::LogInfoToPDCStandbyDeviceWakerAggregatedCollection(WxDiagnostics::PowerTelemetry::PowerStateSessionWakeSource,WxDiagnostics::WIFICX_DATA_OR_IHV_PATH_CONTEXT_TYPE,_WFC_JOB_TYPE,_NET_WAKE_REASON_TYPE)
0x1400d7865  mov     edx, eax
0x1400d7867  test    eax, eax
0x1400d7869  jns     loc_1400D795D
0x1400d786f  lea     rax, WPP_RECORDER_INITIALIZED
0x1400d7876  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d787d  jz      loc_1400D795D
0x1400d7883  mov     ecx, esi
0x1400d7885  call    ?MapWificxJobType@@YAPEBGW4_WFC_JOB_TYPE@@@Z; MapWificxJobType(_WFC_JOB_TYPE)
0x1400d788a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d7891  mov     r9d, 24h ; '$'
0x1400d7897  mov     dword ptr [rsp+50h+var_20], edx
0x1400d789b  mov     [rsp+50h+var_28], rax
0x1400d78a0  mov     rcx, [rcx+40h]
0x1400d78a4  call    WPP_RECORDER_SF_Sd
0x1400d78a9  jmp     loc_1400D795D
0x1400d78ae  mov     eax, cs:dword_14010EBA8
0x1400d78b4  xor     ebx, ebx
0x1400d78b6  cmp     eax, 5
0x1400d78b9  jbe     loc_1400D7940
0x1400d78bf  mov     rdx, 400000000000h
0x1400d78c9  lea     rcx, dword_14010EBA8
0x1400d78d0  call    _tlgKeywordOn
0x1400d78d5  test    al, al
0x1400d78d7  jz      short loc_1400D7940
0x1400d78d9  xor     eax, eax
0x1400d78db  lock cmpxchg [rdi+2D0h], ebx
0x1400d78e3  movsxd  rcx, eax
0x1400d78e6  mov     [rbp+arg_0], rcx
0x1400d78ea  mov     ecx, esi
0x1400d78ec  call    ?MapWificxJobType@@YAPEBGW4_WFC_JOB_TYPE@@@Z; MapWificxJobType(_WFC_JOB_TYPE)
0x1400d78f1  mov     [rbp+arg_10], rax
0x1400d78f5  lea     r9, [rbp+var_10]
0x1400d78f9  mov     rax, [rdi+1B0h]
0x1400d7900  lea     rdx, byte_14010501B
0x1400d7907  mov     [rbp+arg_18], rax
0x1400d790b  lea     rax, [rbp+arg_0]
0x1400d790f  mov     [rsp+50h+var_18], rax
0x1400d7914  lea     rax, [rbp+arg_10]
0x1400d7918  mov     [rsp+50h+var_20], rax
0x1400d791d  lea     rax, [rbp+arg_18]
0x1400d7921  mov     [rsp+50h+var_28], rax
0x1400d7926  lea     rax, [rbp+var_8]
0x1400d792a  mov     [rsp+50h+var_30], rax
0x1400d792f  mov     [rbp+var_8], 800h
0x1400d7937  mov     [rbp+var_10], r14
0x1400d793b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@G@@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@2AEBU?$_tlgWrapSz@G@@32@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1400d7940  mov     rcx, rdi; this
0x1400d7943  call    ?IsSleepStudyReportEnabled@PowerTelemetry@WxDiagnostics@@AEAA_NXZ; WxDiagnostics::PowerTelemetry::IsSleepStudyReportEnabled(void)
0x1400d7948  test    al, al
0x1400d794a  jz      short loc_1400D795D
0x1400d794c  xor     r9d, r9d
0x1400d794f  mov     r8d, esi
0x1400d7952  mov     edx, r14d
0x1400d7955  mov     rcx, rdi
0x1400d7958  call    ?LogInfoToPDCStandbyDeviceWakerCollection@PowerTelemetry@WxDiagnostics@@AEAAJW4WIFICX_CONTROL_PATH_CONTEXT_TYPE@2@W4_WFC_JOB_TYPE@@W4_WIFI_WAKE_REASON_TYPE@@@Z; WxDiagnostics::PowerTelemetry::LogInfoToPDCStandbyDeviceWakerCollection(WxDiagnostics::WIFICX_CONTROL_PATH_CONTEXT_TYPE,_WFC_JOB_TYPE,_WIFI_WAKE_REASON_TYPE)
0x1400d795d  add     rsp, 50h
0x1400d7961  pop     r14
0x1400d7963  pop     rdi
0x1400d7964  pop     rsi
0x1400d7965  pop     rbx
0x1400d7966  pop     rbp
0x1400d7967  retn
```
