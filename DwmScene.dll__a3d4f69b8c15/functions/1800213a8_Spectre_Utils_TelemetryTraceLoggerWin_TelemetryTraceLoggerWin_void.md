# Spectre::Utils::TelemetryTraceLoggerWin::TelemetryTraceLoggerWin(void)

- ea: `0x1800213a8`
- end: `0x1800215b4`
- name: `??0TelemetryTraceLoggerWin@Utils@Spectre@@QEAA@XZ`
- size: `524`
- prototype: `__int64 __fastcall(Spectre::Utils::TelemetryTraceLoggerWin *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180020c2c`

## callees

- `0x1800013e8`
- `0x18000ca90`
- `0x18001128c`
- `0x180011f64`
- `0x18001437c`
- `0x180014530`
- `0x18001c290`
- `0x180021108`
- `0x180021318`
- `0x180021394`
- `0x1800213a8`
- `0x180021760`
- `0x180021810`
- `0x180021df8`
- `0x1800239d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18002144d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18002144d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800214c8`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800214c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
Spectre::Utils::TelemetryTraceLoggerWin *__fastcall Spectre::Utils::TelemetryTraceLoggerWin::TelemetryTraceLoggerWin(
        Spectre::Utils::TelemetryTraceLoggerWin *this)
{
  const char *v2; // rdx
  unsigned __int64 v3; // rcx
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  _DWORD *v6; // rax
  std::_Ref_count_base *v7; // rcx
  GUID v9; // [rsp+20h] [rbp-60h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-50h] BYREF
  GUID pguid; // [rsp+60h] [rbp-20h] BYREF

  *(_QWORD *)&pguid.Data1 = this;
  *(_QWORD *)this = &Spectre::Utils::TelemetryTraceLoggerWin::`vftable';
  Spectre::Utils::TelemetryTraceUid::CreateUid((Spectre::Utils::TelemetryTraceLoggerWin *)((char *)this + 8));
  Spectre::Utils::TelemetryTraceUid::CreateUid((Spectre::Utils::TelemetryTraceLoggerWin *)((char *)this + 16));
  Spectre::Utils::TelemetryTraceUid::CreateUid((Spectre::Utils::TelemetryTraceLoggerWin *)((char *)this + 24));
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  std::string::string((char *)this + 48);
  std::string::string((char *)this + 80, "CanvasDefault");
  *((_QWORD *)this + 14) = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  if ( SystemInfo.wProcessorArchitecture )
  {
    if ( SystemInfo.wProcessorArchitecture == 5 )
    {
      v2 = "ARM";
    }
    else if ( SystemInfo.wProcessorArchitecture == 9 )
    {
      v2 = "x64";
    }
    else
    {
      v2 = "UNKNOWN";
    }
  }
  else
  {
    v2 = "WIN32";
  }
  std::string::_Assign<char>((char *)this + 48, v2);
  v4 = TraceLoggingCorrelationVector::operator new(v3);
  v5 = v4;
  *(_QWORD *)&pguid.Data1 = v4;
  if ( v4 )
  {
    v4[19] = 64;
    pguid = 0;
    CoCreateGuid(&pguid);
    v9 = pguid;
    TraceLoggingCorrelationVector::CreateCvFromGuid<12>(v5, &v9);
  }
  else
  {
    v5 = 0;
  }
  *(_QWORD *)&v9.Data1 = v5;
  std::unique_ptr<TraceLoggingCorrelationVector>::operator=<std::default_delete<TraceLoggingCorrelationVector>,0>(
    (char *)this + 112,
    &v9);
  std::unique_ptr<TraceLoggingCorrelationVector>::~unique_ptr<TraceLoggingCorrelationVector>(&v9);
  TraceLoggingCorrelationVector::ToStringImpl(
    *((TraceLoggingCorrelationVector **)this + 14),
    _InterlockedExchangeAdd64((volatile signed __int64 *)(*((_QWORD *)this + 14) + 144LL), 0),
    (char *)this + 120);
  if ( _InterlockedIncrement64(&qword_180236CC0) == 1 )
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_18022B1C0);
  v6 = operator new(0x28u);
  if ( v6 )
  {
    v6[2] = 1;
    v6[3] = 1;
    *(_QWORD *)v6 = &std::_Ref_count_obj2<Spectre::Utils::TelemTraceLoggerAttributes>::`vftable';
    v6 = (_DWORD *)std::_Construct_in_place<Spectre::Utils::TelemTraceLoggerAttributes,Spectre::Utils::TelemetryTraceUid &,Spectre::Utils::TelemetryTraceUid &,std::string &>(
                     v6 + 4,
                     (char *)this + 8,
                     (char *)this + 16,
                     (char *)this + 48);
  }
  *((_QWORD *)this + 4) = v6 + 4;
  v7 = (std::_Ref_count_base *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = v6;
  if ( v7 )
    std::_Ref_count_base::_Decref(v7);
  return this;
}

```

## disassembly

```asm
0x1800213a8  mov     [rsp-28h+arg_8], rbx
0x1800213ad  mov     [rsp-28h+arg_10], rsi
0x1800213b2  push    rbp
0x1800213b3  push    rdi
0x1800213b4  push    r12
0x1800213b6  push    r14
0x1800213b8  push    r15
0x1800213ba  mov     rbp, rsp
0x1800213bd  sub     rsp, 80h
0x1800213c4  mov     rax, cs:__security_cookie
0x1800213cb  xor     rax, rsp
0x1800213ce  mov     [rbp+var_10], rax
0x1800213d2  mov     rbx, rcx
0x1800213d5  mov     qword ptr [rbp+pguid.Data1], rcx
0x1800213d9  lea     rax, ??_7TelemetryTraceLoggerWin@Utils@Spectre@@6B@; const Spectre::Utils::TelemetryTraceLoggerWin::`vftable'
0x1800213e0  mov     [rcx], rax
0x1800213e3  add     rcx, 8
0x1800213e7  call    ?CreateUid@TelemetryTraceUid@Utils@Spectre@@SA?AV123@XZ; Spectre::Utils::TelemetryTraceUid::CreateUid(void)
0x1800213ec  nop
0x1800213ed  lea     rcx, [rbx+10h]
0x1800213f1  call    ?CreateUid@TelemetryTraceUid@Utils@Spectre@@SA?AV123@XZ; Spectre::Utils::TelemetryTraceUid::CreateUid(void)
0x1800213f6  nop
0x1800213f7  lea     rcx, [rbx+18h]
0x1800213fb  call    ?CreateUid@TelemetryTraceUid@Utils@Spectre@@SA?AV123@XZ; Spectre::Utils::TelemetryTraceUid::CreateUid(void)
0x180021400  nop
0x180021401  mov     qword ptr [rbx+20h], 0
0x180021409  mov     qword ptr [rbx+28h], 0
0x180021411  lea     rsi, [rbx+30h]
0x180021415  mov     rcx, rsi; void *
0x180021418  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18002141d  nop
0x18002141e  lea     rcx, [rbx+50h]
0x180021422  lea     rdx, aCanvasdefault; "CanvasDefault"
0x180021429  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002142e  nop
0x18002142f  lea     r14, [rbx+70h]
0x180021433  mov     qword ptr [r14], 0
0x18002143a  xorps   xmm0, xmm0
0x18002143d  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x180021441  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180021445  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x180021449  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x18002144d  call    cs:__imp_GetSystemInfo
0x180021453  movzx   eax, word ptr [rbp+SystemInfo]
0x180021457  mov     r8d, 5
0x18002145d  test    eax, eax
0x18002145f  jz      short loc_180021492
0x180021461  cmp     eax, r8d
0x180021464  jz      short loc_180021489
0x180021466  cmp     eax, 9
0x180021469  jz      short loc_18002147A
0x18002146b  lea     rdx, aUnknown; "UNKNOWN"
0x180021472  mov     r8d, 7
0x180021478  jmp     short loc_180021499
0x18002147a  lea     rdx, aX64; "x64"
0x180021481  mov     r8d, 3
0x180021487  jmp     short loc_180021499
0x180021489  lea     rdx, aArm; "ARM"
0x180021490  jmp     short loc_180021481
0x180021492  lea     rdx, aWin32; "WIN32"
0x180021499  mov     rcx, rsi
0x18002149c  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x1800214a1  call    ??2TraceLoggingCorrelationVector@@SAPEAX_K@Z; TraceLoggingCorrelationVector::operator new(unsigned __int64)
0x1800214a6  mov     rdi, rax
0x1800214a9  mov     qword ptr [rbp+pguid.Data1], rax
0x1800214ad  test    rax, rax
0x1800214b0  jz      short loc_1800214E5
0x1800214b2  mov     qword ptr [rax+98h], 40h ; '@'
0x1800214bd  xorps   xmm0, xmm0
0x1800214c0  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x1800214c4  lea     rcx, [rbp+pguid]; pguid
0x1800214c8  call    cs:__imp_CoCreateGuid
0x1800214ce  movaps  xmm0, xmmword ptr [rbp+pguid.Data1]
0x1800214d2  movdqa  [rbp+var_60], xmm0
0x1800214d7  lea     rdx, [rbp+var_60]
0x1800214db  mov     rcx, rdi
0x1800214de  call    ??$CreateCvFromGuid@$0M@@TraceLoggingCorrelationVector@@AEAAXU_GUID@@@Z; TraceLoggingCorrelationVector::CreateCvFromGuid<12>(_GUID)
0x1800214e3  jmp     short loc_1800214E7
0x1800214e5  xor     edi, edi
0x1800214e7  mov     qword ptr [rbp+var_60], rdi
0x1800214eb  lea     rdx, [rbp+var_60]
0x1800214ef  mov     rcx, r14
0x1800214f2  call    ??$?4U?$default_delete@VTraceLoggingCorrelationVector@@@std@@$0A@@?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<TraceLoggingCorrelationVector>::operator=<std::default_delete<TraceLoggingCorrelationVector>,0>(std::unique_ptr<TraceLoggingCorrelationVector> &&)
0x1800214f7  lea     rcx, [rbp+var_60]
0x1800214fb  call    ??1?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@std@@@std@@QEAA@XZ; std::unique_ptr<TraceLoggingCorrelationVector>::~unique_ptr<TraceLoggingCorrelationVector>(void)
0x180021500  mov     rcx, [r14]; this
0x180021503  xor     edx, edx
0x180021505  lock xadd [rcx+90h], rdx; unsigned __int64
0x18002150e  lea     r8, [rbx+78h]; char *
0x180021512  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180021517  mov     edi, 1
0x18002151c  mov     eax, edi
0x18002151e  lock xadd cs:qword_180236CC0, rax
0x180021527  add     rax, rdi
0x18002152a  cmp     rax, rdi
0x18002152d  jnz     short loc_18002153B
0x18002152f  lea     rcx, dword_18022B1C0; CallbackContext
0x180021536  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18002153b  mov     ecx, 28h ; '('; unsigned __int64
0x180021540  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021545  test    rax, rax
0x180021548  jz      short loc_18002156E
0x18002154a  mov     [rax+8], edi
0x18002154d  mov     [rax+0Ch], edi
0x180021550  lea     rcx, ??_7?$_Ref_count_obj2@UTelemTraceLoggerAttributes@Utils@Spectre@@@std@@6B@; const std::_Ref_count_obj2<Spectre::Utils::TelemTraceLoggerAttributes>::`vftable'
0x180021557  mov     [rax], rcx
0x18002155a  lea     rcx, [rax+10h]
0x18002155e  mov     r9, rsi
0x180021561  lea     r8, [rbx+10h]
0x180021565  lea     rdx, [rbx+8]
0x180021569  call    ??$_Construct_in_place@UTelemTraceLoggerAttributes@Utils@Spectre@@AEAVTelemetryTraceUid@23@AEAV423@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@YAXAEAUTelemTraceLoggerAttributes@Utils@Spectre@@AEAVTelemetryTraceUid@23@1AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::_Construct_in_place<Spectre::Utils::TelemTraceLoggerAttributes,Spectre::Utils::TelemetryTraceUid &,Spectre::Utils::TelemetryTraceUid &,std::string &>(Spectre::Utils::TelemTraceLoggerAttributes &,Spectre::Utils::TelemetryTraceUid &,Spectre::Utils::TelemetryTraceUid &,std::string &)
0x18002156e  lea     rcx, [rax+10h]
0x180021572  mov     [rbx+20h], rcx
0x180021576  mov     rcx, [rbx+28h]; this
0x18002157a  mov     [rbx+28h], rax
0x18002157e  test    rcx, rcx
0x180021581  jz      short loc_180021589
0x180021583  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180021588  nop
0x180021589  mov     rax, rbx
0x18002158c  mov     rcx, [rbp+var_10]
0x180021590  xor     rcx, rsp; StackCookie
0x180021593  call    __security_check_cookie
0x180021598  lea     r11, [rsp+80h+var_s0]
0x1800215a0  mov     rbx, [r11+38h]
0x1800215a4  mov     rsi, [r11+40h]
0x1800215a8  mov     rsp, r11
0x1800215ab  pop     r15
0x1800215ad  pop     r14
0x1800215af  pop     r12
0x1800215b1  pop     rdi
0x1800215b2  pop     rbp
0x1800215b3  retn
```
