# Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::Worker(void)

- ea: `0x180017620`
- end: `0x180017855`
- name: `?Worker@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@EEAAJXZ`
- size: `565`
- prototype: `__int64 __fastcall(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800045d0`
- `0x180010764`
- `0x180013618`
- `0x1800149bc`
- `0x180014f38`
- `0x180015054`
- `0x1800154b4`
- `0x1800155d4`
- `0x180016350`
- `0x1800168c0`
- `0x180016ba8`
- `0x180016ce4`
- `0x180017620`
- `0x18001792c`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001765c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001765c`

## string_xrefs

- `0x180017683`: `AutopilotHardwareDetectionChangeTaskTelemetry`
- `0x180017770`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`
- `0x1800177cf`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`
- `0x1800177f7`: `onecoreuap\admin\moderndeployment\autopilot\dll\detecthardwarechange.cpp`

## pseudocode

```c
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
    v6 = &qword_180031320;
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
      v11 = Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::EnableSpecifiedTask();
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
0x180017620  mov     [rsp-8+arg_8], rbx
0x180017625  mov     [rsp-8+arg_10], rsi
0x18001762a  push    rbp
0x18001762b  lea     rbp, [rsp-0D0h]
0x180017633  sub     rsp, 1D0h
0x18001763a  mov     rax, cs:__security_cookie
0x180017641  xor     rax, rsp
0x180017644  mov     [rbp+0D0h+var_10], rax
0x18001764b  mov     rbx, rcx
0x18001764e  mov     rax, [rcx+8]
0x180017652  mov     [rsp+1D0h+var_1A8], rax
0x180017657  lea     rcx, [rsp+1D0h+PerformanceCount]; lpPerformanceCount
0x18001765c  call    cs:__imp_QueryPerformanceCounter
0x180017663  nop     dword ptr [rax+rax+00h]
0x180017668  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x18001766f  jz      short loc_180017683
0x180017671  mov     r8, [rsp+1D0h+var_1A8]
0x180017676  lea     rdx, AutopilotDetectHardwareChangeTaskStarted
0x18001767d  call    McTemplateU0z_EventWriteTransfer
0x180017682  nop
0x180017683  lea     rdx, aAutopilothardw; "AutopilotHardwareDetectionChangeTaskTel"...
0x18001768a  lea     rcx, [rsp+1D0h+var_160]
0x18001768f  call    ??0?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180017694  lea     rsi, ??_7AutopilotHardwareDetectionChangeTaskTelemetry@ZeroTouchProvCxhTelemetry@@6B@; const ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::`vftable'
0x18001769b  mov     [rsp+1D0h+var_160], rsi
0x1800176a0  mov     rdx, [rsp+1D0h+var_1A8]; unsigned __int16 *
0x1800176a5  lea     rcx, [rsp+1D0h+var_160]; this
0x1800176aa  call    ?StartActivity@AutopilotHardwareDetectionChangeTaskTelemetry@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::StartActivity(ushort const *)
0x1800176af  nop
0x1800176b0  mov     [rsp+1D0h+var_1AC], 0
0x1800176b8  mov     [rsp+1D0h+var_1B0], 0; int
0x1800176bd  lea     rax, [rsp+1D0h+var_1AC]
0x1800176c2  mov     [rsp+1D0h+var_198], rax
0x1800176c7  lea     rax, [rsp+1D0h+var_1A8]
0x1800176cc  mov     [rsp+1D0h+var_190], rax
0x1800176d1  lea     rax, [rsp+1D0h+var_160]
0x1800176d6  mov     [rsp+1D0h+var_188], rax
0x1800176db  lea     rax, [rsp+1D0h+var_1B0]
0x1800176e0  mov     [rsp+1D0h+var_180], rax
0x1800176e5  lea     rax, [rsp+1D0h+PerformanceCount]
0x1800176ea  mov     [rsp+1D0h+var_178], rax
0x1800176ef  mov     ecx, 1
0x1800176f4  mov     [rsp+1D0h+var_170], cl
0x1800176f8  mov     eax, ecx
0x1800176fa  lock cmpxchg [rbx+24h], ecx
0x1800176ff  jnz     short loc_180017715
0x180017701  mov     ebx, 800704C7h
0x180017706  mov     [rsp+1D0h+var_1AC], ebx
0x18001770a  mov     r9d, ebx
0x18001770d  lea     edx, [rcx+59h]
0x180017710  jmp     loc_1800177CF
0x180017715  mov     r10, [rsp+1D0h+var_1A8]
0x18001771a  lea     rcx, qword_180031320
0x180017721  lea     r11, ?c_remediationResponseJsonHardwareFilter@HardwareInfo@Autopilot@Windows@Microsoft@@2QEBGEB; ushort const * const Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonHardwareFilter
0x180017728  test    r10, r10
0x18001772b  jz      short loc_180017753
0x18001772d  mov     rax, [rcx+8]
0x180017731  mov     rdx, r10
0x180017734  sub     rdx, rax
0x180017737  movzx   r8d, word ptr [rax]
0x18001773b  movzx   r9d, word ptr [rax+rdx]
0x180017740  sub     r8d, r9d
0x180017743  jnz     short loc_18001774E
0x180017745  add     rax, 2
0x180017749  test    r9d, r9d
0x18001774c  jnz     short loc_180017737
0x18001774e  test    r8d, r8d
0x180017751  jz      short loc_18001775C
0x180017753  add     rcx, 10h; this
0x180017757  cmp     rcx, r11
0x18001775a  jnz     short loc_180017728
0x18001775c  mov     ebx, 80070057h
0x180017761  cmp     rcx, r11
0x180017764  jnz     short loc_180017783
0x180017766  mov     rcx, [rbp+0D8h]; this
0x18001776d  mov     r9d, ebx; char *
0x180017770  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x180017777  mov     edx, 89h; void *
0x18001777c  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180017781  jmp     short loc_18001778F
0x180017783  mov     edx, [rcx]
0x180017785  sub     edx, 1
0x180017788  jz      short loc_1800177B8
0x18001778a  cmp     edx, 1
0x18001778d  jz      short loc_18001779D
0x18001778f  mov     [rsp+1D0h+var_1AC], ebx
0x180017793  mov     r9d, ebx
0x180017796  mov     edx, 76h ; 'v'
0x18001779b  jmp     short loc_1800177CF
0x18001779d  lea     rdx, [rsp+1D0h+var_1B0]; bool *
0x1800177a2  call    ?RemediateHardwareChange@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@AEAAJAEA_N@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::RemediateHardwareChange(bool &)
0x1800177a7  mov     ebx, eax
0x1800177a9  mov     [rsp+1D0h+var_1AC], eax
0x1800177ad  test    eax, eax
0x1800177af  jns     short loc_180017808
0x1800177b1  mov     edx, 71h ; 'q'
0x1800177b6  jmp     short loc_1800177CC
0x1800177b8  call    ?EnableSpecifiedTask@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@SAJW4TaskHandler@1234@@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::EnableSpecifiedTask(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler)
0x1800177bd  mov     ebx, eax
0x1800177bf  mov     [rsp+1D0h+var_1AC], eax
0x1800177c3  test    eax, eax
0x1800177c5  jns     short loc_1800177E4
0x1800177c7  mov     edx, 66h ; 'f'; void *
0x1800177cc  mov     r9d, eax; char *
0x1800177cf  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800177d6  mov     rcx, [rbp+0D8h]; this
0x1800177dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800177e2  jmp     short loc_18001780A
0x1800177e4  call    ?RunSpecifiedTask@DetectHardwareChangeHandler@Autopilot@Windows@Microsoft@@SAJW4TaskHandler@1234@_N@Z; Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::RunSpecifiedTask(Microsoft::Windows::Autopilot::DetectHardwareChangeHandler::TaskHandler,bool)
0x1800177e9  mov     rcx, [rbp+0D8h]; this
0x1800177f0  test    eax, eax
0x1800177f2  jns     short loc_180017808
0x1800177f4  mov     r9d, eax; char *
0x1800177f7  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800177fe  mov     edx, 6Bh ; 'k'; void *
0x180017803  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180017808  xor     ebx, ebx
0x18001780a  lea     rcx, [rsp+1D0h+var_198]
0x18001780f  call    wil__details__lambda_call__lambda_5554f4efdf1cc4c6026edded3cbe3d2b______lambda_call__lambda_5554f4efdf1cc4c6026edded3cbe3d2b___
0x180017814  nop
0x180017815  mov     [rsp+1D0h+var_160], rsi
0x18001781a  lea     rcx, [rsp+1D0h+var_160]
0x18001781f  call    ?Destroy@?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180017824  lea     rcx, [rsp+1D0h+var_160]
0x180017829  call    ??1?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x18001782e  mov     eax, ebx
0x180017830  mov     rcx, [rbp+0D0h+var_10]
0x180017837  xor     rcx, rsp; StackCookie
0x18001783a  call    __security_check_cookie
0x18001783f  lea     r11, [rsp+1D0h+var_s0]
0x180017847  mov     rbx, [r11+18h]
0x18001784b  mov     rsi, [r11+20h]
0x18001784f  mov     rsp, r11
0x180017852  pop     rbp
0x180017853  retn
```
