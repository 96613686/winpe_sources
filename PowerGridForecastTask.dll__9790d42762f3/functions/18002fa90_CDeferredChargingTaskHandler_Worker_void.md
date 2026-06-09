# CDeferredChargingTaskHandler::Worker(void)

- ea: `0x18002fa90`
- end: `0x18002fc60`
- name: `?Worker@CDeferredChargingTaskHandler@@EEAAJXZ`
- size: `464`
- prototype: `__int64 __fastcall(CDeferredChargingTaskHandler *this, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `loader_planting, service_task`

## callees

- `0x1800268ef`
- `0x180028468`
- `0x18002da2c`
- `0x18002dcd4`
- `0x18002e574`
- `0x18002e778`
- `0x18002fa90`
- `0x180031200`
- `0x180033344`
- `0x180033834`
- `0x1800350e0`
- `0x180037010`

## string_xrefs

- `0x18002fb91`: `onecore\base\sustainability\tasks\deferredcharging\dll\deferredchargingtask.cpp`
- `0x18002fbd9`: `onecore\base\sustainability\tasks\deferredcharging\dll\deferredchargingtask.cpp`

## pseudocode

```c
__int64 __fastcall CDeferredChargingTaskHandler::Worker(CDeferredChargingTaskHandler *this, __int64 a2)
{
  unsigned int v2; // ebx
  PowerGrid *v3; // rcx
  int v4; // eax
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  __int64 v8; // rcx
  int v10[12]; // [rsp+20h] [rbp-E0h] BYREF
  void **v11; // [rsp+50h] [rbp-B0h] BYREF
  int v12; // [rsp+58h] [rbp-A8h] BYREF
  char v13; // [rsp+5Ch] [rbp-A4h]
  int v14; // [rsp+80h] [rbp-80h] BYREF
  const char *v15; // [rsp+88h] [rbp-78h]
  __int64 v16; // [rsp+90h] [rbp-70h]
  char v17; // [rsp+98h] [rbp-68h]
  int v18; // [rsp+A0h] [rbp-60h]
  _BYTE v19[152]; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v20; // [rsp+140h] [rbp+40h]
  int v21; // [rsp+150h] [rbp+50h]
  __int64 v22; // [rsp+158h] [rbp+58h]
  int *v23; // [rsp+160h] [rbp+60h]
  __int64 v24; // [rsp+168h] [rbp+68h]
  __int64 v25; // [rsp+170h] [rbp+70h]
  void ***v26; // [rsp+178h] [rbp+78h]
  __int64 v27; // [rsp+180h] [rbp+80h]
  int v28; // [rsp+188h] [rbp+88h]
  int *v29; // [rsp+190h] [rbp+90h]
  char v30; // [rsp+198h] [rbp+98h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v2 = 0;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_GreenCharging>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_GreenCharging>::GetImpl'::`2'::impl,
    a2);
  if ( PowerGrid::ShouldSendNewForecast(v3) )
  {
    v12 = 0;
    v13 = 0;
    v17 = 0;
    v14 = 0;
    v15 = "GeneratePowerGridForecastActivity";
    v16 = 0;
    v18 = 0;
    v20 = 0;
    memset_0(v19, 0, sizeof(v19));
    v21 = 1;
    v22 = 0;
    v23 = &v12;
    v24 = 0;
    v25 = 0;
    v26 = &v11;
    v27 = 0;
    v28 = 0;
    v29 = &v14;
    v30 = 0;
    v11 = &PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::`vftable';
    PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::StartActivity((PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity *)&v11);
    *(_QWORD *)v10 = 0;
    v4 = PowerGrid::PowerGridForecastGenerator::Initialize((PowerGrid::PowerGridForecastGenerator *)v10);
    v2 = v4;
    if ( v4 >= 0 )
    {
      v6 = PowerGrid::PowerGridForecastGenerator::WriteForecastOutput((PowerGrid::PowerGridForecastGenerator *)v10);
      v2 = v6;
      if ( v6 >= 0 )
      {
        wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(&v11);
        v8 = *(_QWORD *)v10;
        if ( *(_QWORD *)v10 )
        {
          *(_QWORD *)v10 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x55,
          (unsigned int)"onecore\\base\\sustainability\\tasks\\deferredcharging\\dll\\deferredchargingtask.cpp",
          (const char *)(unsigned int)v6,
          v10[0]);
        v7 = *(_QWORD *)v10;
        if ( *(_QWORD *)v10 )
        {
          *(_QWORD *)v10 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\base\\sustainability\\tasks\\deferredcharging\\dll\\deferredchargingtask.cpp",
        (const char *)(unsigned int)v4,
        v10[0]);
      v5 = *(_QWORD *)v10;
      if ( *(_QWORD *)v10 )
      {
        *(_QWORD *)v10 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      }
    }
    PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::~GeneratePowerGridForecastActivity((PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity *)&v11);
  }
  return v2;
}

```

## disassembly

```asm
0x18002fa90  mov     [rsp-8+arg_0], rbx
0x18002fa95  mov     [rsp-8+arg_8], rdi
0x18002fa9a  push    rbp
0x18002fa9b  lea     rbp, [rsp-0B0h]
0x18002faa3  sub     rsp, 1B0h
0x18002faaa  mov     rax, cs:__security_cookie
0x18002fab1  xor     rax, rsp
0x18002fab4  mov     [rbp+0B0h+var_10], rax
0x18002fabb  xor     edi, edi
0x18002fabd  mov     ebx, edi
0x18002fabf  mov     dl, 1
0x18002fac1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_GreenCharging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_GreenCharging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GreenCharging> `wil::Feature<__WilFeatureTraits_Feature_GreenCharging>::GetImpl(void)'::`2'::impl
0x18002fac8  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_GreenCharging@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GreenCharging>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18002facd  call    ?ShouldSendNewForecast@PowerGrid@@YA_NXZ; PowerGrid::ShouldSendNewForecast(void)
0x18002fad2  test    al, al
0x18002fad4  jz      loc_18002FC3A
0x18002fada  mov     [rsp+1B0h+var_158], edi
0x18002fade  mov     [rsp+1B0h+var_154], dil
0x18002fae3  mov     [rbp+0B0h+var_118], dil
0x18002fae7  mov     [rbp+0B0h+var_130], edi
0x18002faea  lea     rax, aGeneratepowerg; "GeneratePowerGridForecastActivity"
0x18002faf1  mov     [rbp+0B0h+var_128], rax
0x18002faf5  mov     [rbp+0B0h+var_120], rdi
0x18002faf9  mov     [rbp+0B0h+var_110], edi
0x18002fafc  xorps   xmm0, xmm0
0x18002faff  movdqa  [rbp+0B0h+var_70], xmm0
0x18002fb04  xor     edx, edx; Val
0x18002fb06  mov     r8d, 98h; Size
0x18002fb0c  lea     rcx, [rbp+0B0h+var_108]; void *
0x18002fb10  call    memset_0
0x18002fb15  mov     [rbp+0B0h+var_60], 1
0x18002fb1c  xor     eax, eax
0x18002fb1e  mov     [rbp+0B0h+var_58], rax
0x18002fb22  lea     rax, [rsp+1B0h+var_158]
0x18002fb27  mov     [rbp+0B0h+var_50], rax
0x18002fb2b  mov     [rbp+0B0h+var_48], rdi
0x18002fb2f  mov     [rbp+0B0h+var_40], rdi
0x18002fb33  lea     rax, [rsp+1B0h+var_160]
0x18002fb38  mov     [rbp+0B0h+var_38], rax
0x18002fb3c  mov     [rbp+0B0h+var_30], rdi
0x18002fb43  mov     [rbp+0B0h+var_28], edi
0x18002fb49  lea     rax, [rbp+0B0h+var_130]
0x18002fb4d  mov     [rbp+0B0h+var_20], rax
0x18002fb54  mov     [rbp+0B0h+var_18], dil
0x18002fb5b  lea     rax, ??_7GeneratePowerGridForecastActivity@PowerGridForecastTaskTelemetry@@6B@; const PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::`vftable'
0x18002fb62  mov     [rsp+1B0h+var_160], rax
0x18002fb67  lea     rcx, [rsp+1B0h+var_160]; this
0x18002fb6c  call    ?StartActivity@GeneratePowerGridForecastActivity@PowerGridForecastTaskTelemetry@@QEAAXXZ; PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::StartActivity(void)
0x18002fb71  nop
0x18002fb72  mov     qword ptr [rsp+1B0h+var_190], rdi; int
0x18002fb77  lea     rcx, [rsp+1B0h+var_190]; this
0x18002fb7c  call    ?Initialize@PowerGridForecastGenerator@PowerGrid@@QEAAJXZ; PowerGrid::PowerGridForecastGenerator::Initialize(void)
0x18002fb81  mov     ebx, eax
0x18002fb83  test    eax, eax
0x18002fb85  jns     short loc_18002FBBF
0x18002fb87  mov     rcx, [rbp+0B8h]; this
0x18002fb8e  mov     r9d, eax; char *
0x18002fb91  lea     r8, aOnecoreBaseSus_0; "onecore\\base\\sustainability\\tasks\\d"...
0x18002fb98  lea     edx, [rdi+51h]; void *
0x18002fb9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fba0  nop
0x18002fba1  mov     rcx, qword ptr [rsp+1B0h+var_190]
0x18002fba6  test    rcx, rcx
0x18002fba9  jz      short loc_18002FBBD
0x18002fbab  mov     qword ptr [rsp+1B0h+var_190], rdi
0x18002fbb0  mov     rax, [rcx]
0x18002fbb3  mov     rax, [rax+10h]
0x18002fbb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fbbc  nop
0x18002fbbd  jmp     short loc_18002FC30
0x18002fbbf  lea     rcx, [rsp+1B0h+var_190]; this
0x18002fbc4  call    ?WriteForecastOutput@PowerGridForecastGenerator@PowerGrid@@QEAAJXZ; PowerGrid::PowerGridForecastGenerator::WriteForecastOutput(void)
0x18002fbc9  mov     ebx, eax
0x18002fbcb  test    eax, eax
0x18002fbcd  jns     short loc_18002FC09
0x18002fbcf  mov     rcx, [rbp+0B8h]; this
0x18002fbd6  mov     r9d, eax; char *
0x18002fbd9  lea     r8, aOnecoreBaseSus_0; "onecore\\base\\sustainability\\tasks\\d"...
0x18002fbe0  mov     edx, 55h ; 'U'; void *
0x18002fbe5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fbea  nop
0x18002fbeb  mov     rcx, qword ptr [rsp+1B0h+var_190]
0x18002fbf0  test    rcx, rcx
0x18002fbf3  jz      short loc_18002FC07
0x18002fbf5  mov     qword ptr [rsp+1B0h+var_190], rdi
0x18002fbfa  mov     rax, [rcx]
0x18002fbfd  mov     rax, [rax+10h]
0x18002fc01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc06  nop
0x18002fc07  jmp     short loc_18002FC30
0x18002fc09  lea     rcx, [rsp+1B0h+var_160]
0x18002fc0e  call    ?Stop@?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18002fc13  nop
0x18002fc14  mov     rcx, qword ptr [rsp+1B0h+var_190]
0x18002fc19  test    rcx, rcx
0x18002fc1c  jz      short loc_18002FC30
0x18002fc1e  mov     qword ptr [rsp+1B0h+var_190], rdi
0x18002fc23  mov     rax, [rcx]
0x18002fc26  mov     rax, [rax+10h]
0x18002fc2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc2f  nop
0x18002fc30  lea     rcx, [rsp+1B0h+var_160]; this
0x18002fc35  call    ??1GeneratePowerGridForecastActivity@PowerGridForecastTaskTelemetry@@QEAA@XZ; PowerGridForecastTaskTelemetry::GeneratePowerGridForecastActivity::~GeneratePowerGridForecastActivity(void)
0x18002fc3a  mov     eax, ebx
0x18002fc3c  mov     rcx, [rbp+0B0h+var_10]
0x18002fc43  xor     rcx, rsp; StackCookie
0x18002fc46  call    __security_check_cookie
0x18002fc4b  lea     r11, [rsp+1B0h+var_s0]
0x18002fc53  mov     rbx, [r11+10h]
0x18002fc57  mov     rdi, [r11+18h]
0x18002fc5b  mov     rsp, r11
0x18002fc5e  pop     rbp
0x18002fc5f  retn
```
