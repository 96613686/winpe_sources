# Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::Worker(void)

- ea: `0x180017100`
- end: `0x18001732e`
- name: `?Worker@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@EEAAJXZ`
- size: `558`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800045b0`
- `0x1800105f4`
- `0x180013370`
- `0x180014608`
- `0x180014b4c`
- `0x180014c5c`
- `0x1800150b4`
- `0x1800151cc`
- `0x180015ed0`
- `0x180016420`
- `0x180016700`
- `0x180016838`
- `0x180017100`
- `0x180017400`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001713c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001713c`

## string_xrefs

- `0x18001715d`: `AutopilotHardwareDetectionChangeTaskTelemetry`
- `0x18001724a`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`
- `0x1800172a9`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`
- `0x1800172d1`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::Worker(
        Microsoft::Windows::Autopilot::DetectHardwareChangeHandler *this)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 v5; // rdx
  __int64 *v6; // rcx
  __int64 v7; // rax
  char *v8; // rdx
  int v9; // r9d
  int v10; // r8d
  int v11; // eax
  int v12; // eax
  bool v14[4]; // [rsp+20h] [rbp-E0h] BYREF
  int v15; // [rsp+24h] [rbp-DCh] BYREF
  unsigned __int16 *v16; // [rsp+28h] [rbp-D8h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v18[5]; // [rsp+38h] [rbp-C8h] BYREF
  char v19; // [rsp+60h] [rbp-A0h]
  _QWORD v20[42]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v16 = (unsigned __int16 *)*((_QWORD *)this + 1);
  QueryPerformanceCounter(&PerformanceCount);
  if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
    McTemplateU0z_EventWriteTransfer(v2, AutopilotDetectHardwareChangeTaskStarted, v16);
  wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v20,
    "AutopilotHardwareDetectionChangeTaskTelemetry");
  v20[0] = &ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::`vftable';
  ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::StartActivity(
    (ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry *)v20,
    v16);
  v15 = 0;
  v14[0] = 0;
  v18[0] = &v15;
  v18[1] = &v16;
  v18[2] = v20;
  v18[3] = v14;
  v18[4] = &PerformanceCount;
  v19 = 1;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 9, 1, 1) != 1 )
  {
    v6 = &qword_180030320;
    do
    {
      if ( v16 )
      {
        v7 = v6[1];
        v8 = (char *)v16 - v7;
        do
        {
          v9 = *(unsigned __int16 *)&v8[v7];
          v10 = *(unsigned __int16 *)v7 - v9;
          if ( v10 )
            break;
          v7 += 2;
        }
        while ( v9 );
        if ( !v10 )
          break;
      }
      v6 += 2;
    }
    while ( v6 != (__int64 *)&Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonHardwareFilter );
    v3 = -2147024809;
    if ( v6 == (__int64 *)&Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonHardwareFilter )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\detecthardwarechange.cpp",
        (const char *)0x80070057LL,
        *(int *)v14);
LABEL_16:
      v15 = -2147024809;
      v4 = 2147942487LL;
      v5 = 118;
      goto LABEL_22;
    }
    if ( *(_DWORD *)v6 == 1 )
    {
      v11 = Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::EnableSpecifiedTask(
              v6,
              (unsigned int)(*(_DWORD *)v6 - 1));
      v3 = v11;
      v15 = v11;
      if ( v11 < 0 )
      {
        v5 = 102;
        goto LABEL_21;
      }
      v12 = Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::RunSpecifiedTask();
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x6B,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\detecthardwarechange.cpp",
          (const char *)(unsigned int)v12,
          *(int *)v14);
    }
    else
    {
      if ( *(_DWORD *)v6 != 2 )
        goto LABEL_16;
      v11 = Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::RemediateHardwareChange(
              (Microsoft::Windows::Autopilot::DetectHardwareChangeHandler *)v6,
              v14);
      v3 = v11;
      v15 = v11;
      if ( v11 < 0 )
      {
        v5 = 113;
LABEL_21:
        v4 = (unsigned int)v11;
        goto LABEL_22;
      }
    }
    v3 = 0;
    goto LABEL_26;
  }
  v3 = -2147023673;
  v15 = -2147023673;
  v4 = 2147943623LL;
  v5 = 90;
LABEL_22:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\dll\\detecthardwarechange.cpp",
    (const char *)v4,
    *(int *)v14);
LABEL_26:
  wil::details::lambda_call__lambda_5554f4efdf1cc4c6026edded3cbe3d2b___::_lambda_call__lambda_5554f4efdf1cc4c6026edded3cbe3d2b___(v18);
  v20[0] = &ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::`vftable';
  wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v20);
  wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(v20);
  return v3;
}

```

## disassembly

```asm
0x180017100  mov     [rsp-8+arg_8], rbx
0x180017105  mov     [rsp-8+arg_10], rsi
0x18001710a  push    rbp
0x18001710b  lea     rbp, [rsp-0D0h]
0x180017113  sub     rsp, 1D0h
0x18001711a  mov     rax, cs:__security_cookie
0x180017121  xor     rax, rsp
0x180017124  mov     [rbp+0D0h+var_10], rax
0x18001712b  mov     rbx, rcx
0x18001712e  mov     rax, [rcx+8]
0x180017132  mov     [rsp+1D0h+var_1A8], rax
0x180017137  lea     rcx, [rsp+1D0h+PerformanceCount]; lpPerformanceCount
0x18001713c  call    cs:__imp_QueryPerformanceCounter
0x180017142  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180017149  jz      short loc_18001715D
0x18001714b  mov     r8, [rsp+1D0h+var_1A8]
0x180017150  lea     rdx, AutopilotDetectHardwareChangeTaskStarted
0x180017157  call    McTemplateU0z_EventWriteTransfer
0x18001715c  nop
0x18001715d  lea     rdx, aAutopilothardw; "AutopilotHardwareDetectionChangeTaskTel"...
0x180017164  lea     rcx, [rsp+1D0h+var_160]
0x180017169  call    ??0?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001716e  lea     rsi, ??_7AutopilotHardwareDetectionChangeTaskTelemetry@ZeroTouchProvCxhTelemetry@@6B@; const ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::`vftable'
0x180017175  mov     [rsp+1D0h+var_160], rsi
0x18001717a  mov     rdx, [rsp+1D0h+var_1A8]; unsigned __int16 *
0x18001717f  lea     rcx, [rsp+1D0h+var_160]; this
0x180017184  call    ?StartActivity@AutopilotHardwareDetectionChangeTaskTelemetry@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::StartActivity(ushort const *)
0x180017189  nop
0x18001718a  mov     [rsp+1D0h+var_1AC], 0
0x180017192  mov     [rsp+1D0h+var_1B0], 0; int
0x180017197  lea     rax, [rsp+1D0h+var_1AC]
0x18001719c  mov     [rsp+1D0h+var_198], rax
0x1800171a1  lea     rax, [rsp+1D0h+var_1A8]
0x1800171a6  mov     [rsp+1D0h+var_190], rax
0x1800171ab  lea     rax, [rsp+1D0h+var_160]
0x1800171b0  mov     [rsp+1D0h+var_188], rax
0x1800171b5  lea     rax, [rsp+1D0h+var_1B0]
0x1800171ba  mov     [rsp+1D0h+var_180], rax
0x1800171bf  lea     rax, [rsp+1D0h+PerformanceCount]
0x1800171c4  mov     [rsp+1D0h+var_178], rax
0x1800171c9  mov     ecx, 1
0x1800171ce  mov     [rsp+1D0h+var_170], cl
0x1800171d2  mov     eax, ecx
0x1800171d4  lock cmpxchg [rbx+24h], ecx
0x1800171d9  jnz     short loc_1800171EF
0x1800171db  mov     ebx, 800704C7h
0x1800171e0  mov     [rsp+1D0h+var_1AC], ebx
0x1800171e4  mov     r9d, ebx
0x1800171e7  lea     edx, [rcx+59h]
0x1800171ea  jmp     loc_1800172A9
0x1800171ef  mov     r10, [rsp+1D0h+var_1A8]
0x1800171f4  lea     rcx, qword_180030320
0x1800171fb  lea     r11, ?c_remediationResponseJsonHardwareFilter@HardwareInfo@Autopilot@Windows@Microsoft@@2QEBGEB; ushort const * const Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonHardwareFilter
0x180017202  test    r10, r10
0x180017205  jz      short loc_18001722D
0x180017207  mov     rax, [rcx+8]
0x18001720b  mov     rdx, r10
0x18001720e  sub     rdx, rax
0x180017211  movzx   r8d, word ptr [rax]
0x180017215  movzx   r9d, word ptr [rax+rdx]
0x18001721a  sub     r8d, r9d
0x18001721d  jnz     short loc_180017228
0x18001721f  add     rax, 2
0x180017223  test    r9d, r9d
0x180017226  jnz     short loc_180017211
0x180017228  test    r8d, r8d
0x18001722b  jz      short loc_180017236
0x18001722d  add     rcx, 10h; this
0x180017231  cmp     rcx, r11
0x180017234  jnz     short loc_180017202
0x180017236  mov     ebx, 80070057h
0x18001723b  cmp     rcx, r11
0x18001723e  jnz     short loc_18001725D
0x180017240  mov     rcx, [rbp+0D8h]; this
0x180017247  mov     r9d, ebx; char *
0x18001724a  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x180017251  mov     edx, 89h; void *
0x180017256  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001725b  jmp     short loc_180017269
0x18001725d  mov     edx, [rcx]
0x18001725f  sub     edx, 1
0x180017262  jz      short loc_180017292
0x180017264  cmp     edx, 1
0x180017267  jz      short loc_180017277
0x180017269  mov     [rsp+1D0h+var_1AC], ebx
0x18001726d  mov     r9d, ebx
0x180017270  mov     edx, 76h ; 'v'
0x180017275  jmp     short loc_1800172A9
0x180017277  lea     rdx, [rsp+1D0h+var_1B0]; bool *
0x18001727c  call    ?RemediateHardwareChange@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@AEAAJAEA_N@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::RemediateHardwareChange(bool &)
0x180017281  mov     ebx, eax
0x180017283  mov     [rsp+1D0h+var_1AC], eax
0x180017287  test    eax, eax
0x180017289  jns     short loc_1800172E2
0x18001728b  mov     edx, 71h ; 'q'
0x180017290  jmp     short loc_1800172A6
0x180017292  call    ?EnableSpecifiedTask@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@SAJW4TaskHandler@1234@@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::EnableSpecifiedTask(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler)
0x180017297  mov     ebx, eax
0x180017299  mov     [rsp+1D0h+var_1AC], eax
0x18001729d  test    eax, eax
0x18001729f  jns     short loc_1800172BE
0x1800172a1  mov     edx, 66h ; 'f'; void *
0x1800172a6  mov     r9d, eax; char *
0x1800172a9  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800172b0  mov     rcx, [rbp+0D8h]; this
0x1800172b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800172bc  jmp     short loc_1800172E4
0x1800172be  call    ?RunSpecifiedTask@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@SAJW4TaskHandler@1234@_N@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::RunSpecifiedTask(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler,bool)
0x1800172c3  mov     rcx, [rbp+0D8h]; this
0x1800172ca  test    eax, eax
0x1800172cc  jns     short loc_1800172E2
0x1800172ce  mov     r9d, eax; char *
0x1800172d1  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800172d8  mov     edx, 6Bh ; 'k'; void *
0x1800172dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800172e2  xor     ebx, ebx
0x1800172e4  lea     rcx, [rsp+1D0h+var_198]
0x1800172e9  call    wil__details__lambda_call__lambda_5554f4efdf1cc4c6026edded3cbe3d2b______lambda_call__lambda_5554f4efdf1cc4c6026edded3cbe3d2b___
0x1800172ee  nop
0x1800172ef  mov     [rsp+1D0h+var_160], rsi
0x1800172f4  lea     rcx, [rsp+1D0h+var_160]
0x1800172f9  call    ?Destroy@?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800172fe  lea     rcx, [rsp+1D0h+var_160]
0x180017303  call    ??1?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180017308  mov     eax, ebx
0x18001730a  mov     rcx, [rbp+0D0h+var_10]
0x180017311  xor     rcx, rsp; StackCookie
0x180017314  call    __security_check_cookie
0x180017319  lea     r11, [rsp+1D0h+var_s0]
0x180017321  mov     rbx, [r11+18h]
0x180017325  mov     rsi, [r11+20h]
0x180017329  mov     rsp, r11
0x18001732c  pop     rbp
0x18001732d  retn
```
