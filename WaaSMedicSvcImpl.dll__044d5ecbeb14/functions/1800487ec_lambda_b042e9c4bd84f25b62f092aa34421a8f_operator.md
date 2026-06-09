# _lambda_b042e9c4bd84f25b62f092aa34421a8f_::operator()

- ea: `0x1800487ec`
- end: `0x180048b91`
- name: `_lambda_b042e9c4bd84f25b62f092aa34421a8f_::operator()`
- size: `933`
- prototype: `__int64 __fastcall(__int64 **)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180055d10`

## callees

- `0x1800050a0`
- `0x1800050c4`
- `0x180008c2c`
- `0x1800098f0`
- `0x180009cd0`
- `0x18000bbd4`
- `0x18000de58`
- `0x18000f9cc`
- `0x18001c554`
- `0x18002a32c`
- `0x18002b42c`
- `0x18002e81c`
- `0x180034658`
- `0x180034708`
- `0x1800347e0`
- `0x1800487ec`
- `0x18005f348`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800488ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800488ea`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180048a71`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180048a71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180048a77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180048a77`

## string_xrefs

- `0x180048863`: `onecore\enduser\waasmedic\servicelib\waasremediationagent.cpp`
- `0x1800488d0`: `WaaSRemediationAgent now starting the task. Waiting for remediation lock...`
- `0x1800488f7`: `WaaSRemediationAgent now starting the task. Remediation lock aquired.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall lambda_b042e9c4bd84f25b62f092aa34421a8f_::operator()(__int64 **a1)
{
  __int64 (__fastcall ****v2)(_QWORD, GUID *, __int64 *); // rdx
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall *v4)(_QWORD, GUID *, __int64 *); // r14
  __int64 *v5; // rbx
  __int64 v6; // rcx
  int v7; // ebx
  __int64 v8; // rdx
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // r14
  __int64 *v12; // rbx
  __int64 v13; // rcx
  char *v14; // r8
  volatile signed __int64 *v15; // rcx
  TraceLoggingCorrelationVector *v16; // rax
  TraceLoggingCorrelationVector *v17; // rcx
  _QWORD *v18; // r14
  __int64 v19; // rax
  const wchar_t *v20; // r15
  const wchar_t *v21; // rax
  __int64 v22; // rsi
  __int64 v23; // r8
  __int64 v24; // rcx
  unsigned int v25; // ebx
  HANDLE CurrentThread; // rax
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  int v30; // [rsp+20h] [rbp-40h]
  __int128 v31; // [rsp+38h] [rbp-28h] BYREF
  __int64 v32; // [rsp+48h] [rbp-18h]
  __int64 v33; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v2 = (__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))**a1;
  v3 = *v2;
  v4 = ***v2;
  v5 = a1[1];
  v6 = *v5;
  if ( *v5 )
  {
    *v5 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v7 = v4(v3, &IID_IUnknown, v5);
  if ( v7 < 0 )
  {
    v8 = 991;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\enduser\\waasmedic\\servicelib\\waasremediationagent.cpp",
      (const char *)(unsigned int)v7,
      v30);
    return (unsigned int)v7;
  }
  v10 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))**a1;
  v11 = **v10;
  v12 = a1[2];
  v13 = *v12;
  if ( *v12 )
  {
    *v12 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v7 = v11(v10, &GUID_4a263f7d_05d5_40d2_8eae_6a351acfb16f, v12);
  if ( v7 < 0 )
  {
    v8 = 992;
    goto LABEL_5;
  }
  *(_BYTE *)a1[3] = 1;
  LogLevelW(4u, L"WaaSRemediationAgent now starting the task. Waiting for remediation lock...");
  EnterCriticalSection(&stru_1800A43C8);
  *(_BYTE *)a1[4] = 1;
  LogLevelW(4u, L"WaaSRemediationAgent now starting the task. Remediation lock aquired.");
  v14 = (char *)a1[6];
  if ( !v14 )
  {
    v7 = -2147467261;
LABEL_19:
    v8 = 1000;
    goto LABEL_5;
  }
  v15 = (volatile signed __int64 *)a1[5][20];
  if ( v15 )
  {
    if ( !TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v15,
            _InterlockedExchangeAdd64(v15 + 17, 0),
            v14) )
    {
      v7 = -2147418113;
      goto LABEL_19;
    }
  }
  else
  {
    *v14 = 0;
  }
  if ( !a1[5][20] )
  {
    v16 = (TraceLoggingCorrelationVector *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v16 )
      v17 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v16);
    else
      v17 = 0;
    a1[5][20] = (__int64)v17;
  }
  v7 = WaasMedic::SafeAllocString(*(WaasMedic **)(**a1 + 24), (const unsigned __int16 *)a1[7], (unsigned __int16 **)v14);
  if ( v7 < 0 )
  {
    v8 = 1007;
    goto LABEL_5;
  }
  LogLevelW(4u, L"LaunchMaintenanceRun called by %s", *a1[7]);
  v18 = operator new(0x10u);
  *v18 = &uus::Session::`vftable';
  v19 = uus::Utility::GetFirstBrainSession<uus::Brain3>(L"waasmedic.engine.launchmaintenancerun", 0);
  v18[1] = v19;
  v20 = L"0.0.0.0";
  if ( v19 )
    v21 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 32LL))(v19);
  else
    v21 = L"0.0.0.0";
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v22 = -1;
  v23 = -1;
  do
    ++v23;
  while ( v21[v23] );
  std::wstring::_Construct<1,unsigned short const *>(&v31, v21);
  WaasMedic::TelemetryProvider::ReportMaintenanceRunStarted(a1[6], *a1[7], &v31);
  std::wstring::~wstring(&v31);
  v24 = **a1;
  v25 = *(_DWORD *)(v24 + 32);
  SetEvent(*(HANDLE *)(v24 + 16));
  CurrentThread = GetCurrentThread();
  WaasMedic::MiscUtil::SetBelowNormalPriorityState(CurrentThread);
  v27 = WaaSRemediationAgent::LaunchRemediationHelper(a1[5], v25, 0, *a1[7], 0);
  *(_DWORD *)a1[8] = v27;
  if ( v27 >= 0 )
  {
    v29 = v18[1];
    if ( v29 )
      v20 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 32LL))(v29);
    v31 = 0;
    v32 = 0;
    v33 = 0;
    do
      ++v22;
    while ( v20[v22] );
    std::wstring::_Construct<1,unsigned short const *>(&v31, v20);
    WaasMedic::TelemetryProvider::ReportMaintenanceRunCompleted(a1[6], &v31);
  }
  else
  {
    v28 = v18[1];
    if ( v28 )
      v20 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 32LL))(v28);
    v31 = 0;
    v32 = 0;
    v33 = 0;
    do
      ++v22;
    while ( v20[v22] );
    std::wstring::_Construct<1,unsigned short const *>(&v31, v20);
    WaasMedic::TelemetryProvider::ReportMaintenanceRunFailed(a1[6], *(unsigned int *)a1[8], &v31);
  }
  std::wstring::~wstring(&v31);
  (*(void (__fastcall **)(_QWORD *, __int64))*v18)(v18, 1);
  return 0;
}

```

## disassembly

```asm
0x1800487ec  mov     [rsp-28h+arg_8], rbx
0x1800487f1  mov     [rsp-28h+arg_10], rsi
0x1800487f6  push    rbp
0x1800487f7  push    rdi
0x1800487f8  push    r12
0x1800487fa  push    r14
0x1800487fc  push    r15
0x1800487fe  mov     rbp, rsp
0x180048801  sub     rsp, 60h
0x180048805  mov     rax, cs:__security_cookie
0x18004880c  xor     rax, rsp
0x18004880f  mov     [rbp+var_8], rax
0x180048813  mov     rdi, rcx
0x180048816  xor     r12d, r12d
0x180048819  mov     rax, [rcx]
0x18004881c  mov     rdx, [rax]
0x18004881f  mov     rsi, [rdx]
0x180048822  mov     rax, [rsi]
0x180048825  mov     r14, [rax]
0x180048828  mov     rbx, [rcx+8]
0x18004882c  mov     rcx, [rbx]
0x18004882f  test    rcx, rcx
0x180048832  jz      short loc_180048843
0x180048834  mov     [rbx], r12
0x180048837  mov     rax, [rcx]
0x18004883a  mov     rax, [rax+10h]
0x18004883e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048843  mov     r8, rbx
0x180048846  lea     rdx, IID_IUnknown
0x18004884d  mov     rcx, rsi
0x180048850  mov     rax, r14
0x180048853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048858  mov     ebx, eax
0x18004885a  test    eax, eax
0x18004885c  jns     short loc_18004887D
0x18004885e  mov     edx, 3DFh; void *
0x180048863  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\servicelib"...
0x18004886a  mov     r9d, ebx; char *
0x18004886d  mov     rcx, [rbp+28h]; this
0x180048871  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048876  mov     eax, ebx
0x180048878  jmp     loc_180048B6C
0x18004887d  mov     rax, [rdi]
0x180048880  mov     rcx, [rax]
0x180048883  mov     rsi, [rcx]
0x180048886  mov     rax, [rsi]
0x180048889  mov     r14, [rax]
0x18004888c  mov     rbx, [rdi+10h]
0x180048890  mov     rcx, [rbx]
0x180048893  test    rcx, rcx
0x180048896  jz      short loc_1800488A7
0x180048898  mov     [rbx], r12
0x18004889b  mov     rdx, [rcx]
0x18004889e  mov     rax, [rdx+10h]
0x1800488a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488a7  mov     r8, rbx
0x1800488aa  lea     rdx, _GUID_4a263f7d_05d5_40d2_8eae_6a351acfb16f
0x1800488b1  mov     rcx, rsi
0x1800488b4  mov     rax, r14
0x1800488b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800488bc  mov     ebx, eax
0x1800488be  test    eax, eax
0x1800488c0  jns     short loc_1800488C9
0x1800488c2  mov     edx, 3E0h
0x1800488c7  jmp     short loc_180048863
0x1800488c9  mov     rax, [rdi+18h]
0x1800488cd  mov     byte ptr [rax], 1
0x1800488d0  lea     rdx, aWaasremediatio_2; "WaaSRemediationAgent now starting the t"...
0x1800488d7  mov     esi, 4
0x1800488dc  mov     ecx, esi; unsigned __int8
0x1800488de  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800488e3  lea     rcx, stru_1800A43C8; lpCriticalSection
0x1800488ea  call    cs:__imp_EnterCriticalSection
0x1800488f0  mov     rax, [rdi+20h]
0x1800488f4  mov     byte ptr [rax], 1
0x1800488f7  lea     rdx, aWaasremediatio_3; "WaaSRemediationAgent now starting the t"...
0x1800488fe  mov     ecx, esi; unsigned __int8
0x180048900  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180048905  mov     r8, [rdi+30h]; char *
0x180048909  test    r8, r8
0x18004890c  jnz     short loc_180048915
0x18004890e  mov     ebx, 80004003h
0x180048913  jmp     short loc_180048976
0x180048915  mov     rax, [rdi+28h]
0x180048919  mov     rcx, [rax+0A0h]; this
0x180048920  test    rcx, rcx
0x180048923  jnz     short loc_18004895C
0x180048925  mov     [r8], r12b
0x180048928  mov     rax, [rdi+28h]
0x18004892c  cmp     [rax+0A0h], r12
0x180048933  jnz     short loc_18004898E
0x180048935  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004893c  mov     ecx, 90h; unsigned __int64
0x180048941  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180048946  mov     [rbp+var_30], rax
0x18004894a  test    rax, rax
0x18004894d  jz      short loc_180048980
0x18004894f  mov     rcx, rax; this
0x180048952  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180048957  mov     rcx, rax
0x18004895a  jmp     short loc_180048983
0x18004895c  mov     rdx, r12
0x18004895f  lock xadd [rcx+88h], rdx; unsigned __int64
0x180048968  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18004896d  test    al, al
0x18004896f  jnz     short loc_180048928
0x180048971  mov     ebx, 8000FFFFh
0x180048976  mov     edx, 3E8h
0x18004897b  jmp     loc_180048863
0x180048980  mov     rcx, r12
0x180048983  mov     rax, [rdi+28h]
0x180048987  mov     [rax+0A0h], rcx
0x18004898e  mov     rax, [rdi]
0x180048991  mov     rcx, [rax]
0x180048994  mov     rdx, [rdi+38h]; unsigned __int16 *
0x180048998  mov     rcx, [rcx+18h]; this
0x18004899c  call    ?SafeAllocString@WaasMedic@@YAJPEBGPEAPEAG@Z; WaasMedic::SafeAllocString(ushort const *,ushort * *)
0x1800489a1  mov     ebx, eax
0x1800489a3  test    eax, eax
0x1800489a5  jns     short loc_1800489B1
0x1800489a7  mov     edx, 3EFh
0x1800489ac  jmp     loc_180048863
0x1800489b1  mov     r8, [rdi+38h]
0x1800489b5  mov     r8, [r8]
0x1800489b8  lea     rdx, aLaunchmaintena_0; "LaunchMaintenanceRun called by %s"
0x1800489bf  mov     ecx, esi; unsigned __int8
0x1800489c1  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800489c6  mov     ecx, 10h; Size
0x1800489cb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800489d0  mov     r14, rax
0x1800489d3  mov     [rbp+var_30], rax
0x1800489d7  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x1800489de  mov     [r14], rax
0x1800489e1  xor     edx, edx
0x1800489e3  lea     rcx, aWaasmedicEngin_4; "waasmedic.engine.launchmaintenancerun"
0x1800489ea  call    ??$GetFirstBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@PEBGI@Z; uus::Utility::GetFirstBrainSession<uus::Brain3>(ushort const *,uint)
0x1800489ef  mov     rdx, rax
0x1800489f2  mov     [r14+8], rax
0x1800489f6  mov     [rbp+var_30], r14
0x1800489fa  lea     r15, a0000; "0.0.0.0"
0x180048a01  test    rax, rax
0x180048a04  jz      short loc_180048A17
0x180048a06  mov     rcx, [rax]
0x180048a09  mov     rax, [rcx+20h]
0x180048a0d  mov     rcx, rdx
0x180048a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048a15  jmp     short loc_180048A1A
0x180048a17  mov     rax, r15
0x180048a1a  xorps   xmm0, xmm0
0x180048a1d  movups  [rbp+var_28], xmm0
0x180048a21  mov     [rbp+var_18], r12
0x180048a25  mov     [rbp+var_10], r12
0x180048a29  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180048a2d  mov     r8, rsi
0x180048a30  inc     r8
0x180048a33  cmp     [rax+r8*2], r12w
0x180048a38  jnz     short loc_180048A30
0x180048a3a  mov     rdx, rax
0x180048a3d  lea     rcx, [rbp+var_28]
0x180048a41  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180048a46  nop
0x180048a47  mov     rdx, [rdi+38h]
0x180048a4b  lea     r8, [rbp+var_28]
0x180048a4f  mov     rdx, [rdx]
0x180048a52  mov     rcx, [rdi+30h]
0x180048a56  call    ?ReportMaintenanceRunStarted@TelemetryProvider@WaasMedic@@SAXPEBDPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaasMedic::TelemetryProvider::ReportMaintenanceRunStarted(char const *,ushort const *,std::wstring const &)
0x180048a5b  lea     rcx, [rbp+var_28]; void *
0x180048a5f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048a64  mov     rax, [rdi]
0x180048a67  mov     rcx, [rax]
0x180048a6a  mov     ebx, [rcx+20h]
0x180048a6d  mov     rcx, [rcx+10h]; hEvent
0x180048a71  call    cs:__imp_SetEvent
0x180048a77  call    cs:__imp_GetCurrentThread
0x180048a7d  mov     rcx, rax; ThreadHandle
0x180048a80  call    ?SetBelowNormalPriorityState@MiscUtil@WaasMedic@@SAJPEAX@Z; WaasMedic::MiscUtil::SetBelowNormalPriorityState(void *)
0x180048a85  mov     r9, [rdi+38h]
0x180048a89  mov     qword ptr [rsp+60h+var_40], r12
0x180048a8e  mov     r9, [r9]
0x180048a91  xor     r8d, r8d
0x180048a94  mov     edx, ebx
0x180048a96  mov     rcx, [rdi+28h]
0x180048a9a  call    ?LaunchRemediationHelper@WaaSRemediationAgent@@AEAAJW4RunMode@WaasMedic@@PEBG1PEAPEAG@Z; WaaSRemediationAgent::LaunchRemediationHelper(WaasMedic::RunMode,ushort const *,ushort const *,ushort * *)
0x180048a9f  mov     rcx, [rdi+40h]
0x180048aa3  mov     [rcx], eax
0x180048aa5  test    eax, eax
0x180048aa7  jns     short loc_180048AFF
0x180048aa9  mov     rcx, [r14+8]
0x180048aad  test    rcx, rcx
0x180048ab0  jz      short loc_180048AC1
0x180048ab2  mov     rax, [rcx]
0x180048ab5  mov     rax, [rax+20h]
0x180048ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048abe  mov     r15, rax
0x180048ac1  xorps   xmm0, xmm0
0x180048ac4  movups  [rbp+var_28], xmm0
0x180048ac8  mov     [rbp+var_18], r12
0x180048acc  mov     [rbp+var_10], r12
0x180048ad0  inc     rsi
0x180048ad3  cmp     [r15+rsi*2], r12w
0x180048ad8  jnz     short loc_180048AD0
0x180048ada  mov     r8, rsi
0x180048add  mov     rdx, r15
0x180048ae0  lea     rcx, [rbp+var_28]
0x180048ae4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180048ae9  nop
0x180048aea  mov     rdx, [rdi+40h]
0x180048aee  lea     r8, [rbp+var_28]
0x180048af2  mov     edx, [rdx]
0x180048af4  mov     rcx, [rdi+30h]
0x180048af8  call    ?ReportMaintenanceRunFailed@TelemetryProvider@WaasMedic@@SAXPEBDJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaasMedic::TelemetryProvider::ReportMaintenanceRunFailed(char const *,long,std::wstring const &)
0x180048afd  jmp     short loc_180048B4D
0x180048aff  mov     rcx, [r14+8]
0x180048b03  test    rcx, rcx
0x180048b06  jz      short loc_180048B17
0x180048b08  mov     rax, [rcx]
0x180048b0b  mov     rax, [rax+20h]
0x180048b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b14  mov     r15, rax
0x180048b17  xorps   xmm0, xmm0
0x180048b1a  movups  [rbp+var_28], xmm0
0x180048b1e  mov     [rbp+var_18], r12
0x180048b22  mov     [rbp+var_10], r12
0x180048b26  inc     rsi
0x180048b29  cmp     [r15+rsi*2], r12w
0x180048b2e  jnz     short loc_180048B26
0x180048b30  mov     r8, rsi
0x180048b33  mov     rdx, r15
0x180048b36  lea     rcx, [rbp+var_28]
0x180048b3a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180048b3f  nop
0x180048b40  lea     rdx, [rbp+var_28]
0x180048b44  mov     rcx, [rdi+30h]
0x180048b48  call    ?ReportMaintenanceRunCompleted@TelemetryProvider@WaasMedic@@SAXPEBDAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WaasMedic::TelemetryProvider::ReportMaintenanceRunCompleted(char const *,std::wstring const &)
0x180048b4d  lea     rcx, [rbp+var_28]; void *
0x180048b51  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180048b56  nop
0x180048b57  mov     rax, [r14]
0x180048b5a  mov     edx, 1
0x180048b5f  mov     rcx, r14
0x180048b62  mov     rax, [rax]
0x180048b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048b6a  xor     eax, eax
0x180048b6c  mov     rcx, [rbp+var_8]
0x180048b70  xor     rcx, rsp; StackCookie
0x180048b73  call    __security_check_cookie
0x180048b78  lea     r11, [rsp+60h+var_s0]
0x180048b7d  mov     rbx, [r11+38h]
0x180048b81  mov     rsi, [r11+40h]
0x180048b85  mov     rsp, r11
0x180048b88  pop     r15
0x180048b8a  pop     r14
0x180048b8c  pop     r12
0x180048b8e  pop     rdi
0x180048b8f  pop     rbp
0x180048b90  retn
```
