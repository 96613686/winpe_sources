# StartUserPresenceMonitoring(ulong,void *)

- ea: `0x1800153e8`
- end: `0x180015588`
- name: `?StartUserPresenceMonitoring@@YAXKPEAX@Z`
- size: `416`
- prototype: `void __fastcall(unsigned int, PSID Sid)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013d30`

## callees

- `0x1800010b0`
- `0x18000129c`
- `0x18000459c`
- `0x18000a7f8`
- `0x18000cb10`
- `0x1800135c4`
- `0x180013f30`
- `0x180014124`
- `0x1800153e8`
- `0x180015590`
- `0x18001c3b0`
- `0x180021980`

## pseudocode

```c
void __fastcall StartUserPresenceMonitoring(unsigned int a1, PSID Sid)
{
  _BYTE *v4; // rax
  _BYTE *v5; // rdi
  struct _GUID *v6; // rbp
  NaturalAuthTraceLogging *v7; // rcx
  struct _GUID v8; // xmm0
  int v9; // eax
  __int64 v10; // r9
  void *v11; // r8
  _BYTE *v12; // [rsp+60h] [rbp+18h] BYREF
  int v13; // [rsp+68h] [rbp+20h] BYREF

  if ( byte_18005FC30 && a1 == dword_18005CC18 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        &WPP_a55972c0645036c47bb3e826c72e1456_Traceguids,
        (unsigned int)dword_18005CC18);
  }
  else
  {
    if ( byte_18005FC30 )
      StopUserPresenceMonitoring();
    v4 = operator new(0x28u);
    v12 = v4;
    v5 = v4;
    qword_18005FC10 = v4;
    *(_DWORD *)v4 = 0;
    v6 = (struct _GUID *)(v4 + 24);
    v4[4] = 0;
    v8 = *NaturalAuthTraceLogging::GetActivityId(v7);
    v5[4] = 1;
    *v6 = v8;
    _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(v5);
    if ( (unsigned int)dword_18005C570 > 5 )
    {
      if ( !v5[4] || _tlgGuidIsZero(v6) )
        v6 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_18005C570,
        (__int64)byte_18004FA33,
        (__int64)(v5 + 8),
        (__int64)v6);
    }
    if ( (int)ConfigurePolicyBasedDynamicLockRules(a1, Sid) >= 0 || (v9 = ConfigureDefaultDynamicLockRules(a1), v9 >= 0) )
    {
      byte_18005FC30 = 1;
      dword_18005CC18 = a1;
    }
    else
    {
      v11 = qword_18005FC10;
      if ( qword_18005FC10 )
      {
        *(_DWORD *)qword_18005FC10 = 2;
        if ( (unsigned int)dword_18005C570 > 5 )
        {
          v13 = v9;
          LOBYTE(v12) = 1;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
            (__int64)&dword_18005C570,
            (__int64)byte_18004F9AD,
            (__int64)v11 + 8,
            v10,
            (__int64)&v12,
            (__int64)&v13);
        }
        if ( qword_18005FC10 )
          TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::`scalar deleting destructor'(qword_18005FC10);
        qword_18005FC10 = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x1800153e8  mov     [rsp+arg_0], rbx
0x1800153ed  mov     [rsp+arg_8], rbp
0x1800153f2  push    rsi
0x1800153f3  push    rdi
0x1800153f4  push    r14
0x1800153f6  sub     rsp, 30h
0x1800153fa  mov     al, cs:byte_18005FC30
0x180015400  mov     r14, rdx
0x180015403  mov     ebx, ecx
0x180015405  nop
0x180015406  test    al, al
0x180015408  jz      short loc_180015451
0x18001540a  mov     r9d, cs:dword_18005CC18
0x180015411  cmp     ecx, r9d
0x180015414  jnz     short loc_180015451
0x180015416  mov     rcx, cs:WPP_GLOBAL_Control
0x18001541d  lea     rax, WPP_GLOBAL_Control
0x180015424  cmp     rcx, rax
0x180015427  jz      loc_180015575
0x18001542d  test    byte ptr [rcx+1Ch], 4
0x180015431  jz      loc_180015575
0x180015437  mov     rcx, [rcx+10h]
0x18001543b  lea     r8, WPP_a55972c0645036c47bb3e826c72e1456_Traceguids
0x180015442  mov     edx, 18h
0x180015447  call    WPP_SF_d
0x18001544c  jmp     loc_180015575
0x180015451  mov     al, cs:byte_18005FC30
0x180015457  nop
0x180015458  test    al, al
0x18001545a  jz      short loc_180015461
0x18001545c  call    ?StopUserPresenceMonitoring@@YAXXZ; StopUserPresenceMonitoring(void)
0x180015461  mov     ecx, 28h ; '('; Size
0x180015466  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001546b  mov     [rsp+48h+arg_10], rax
0x180015470  mov     rdi, rax
0x180015473  mov     cs:qword_18005FC10, rax
0x18001547a  mov     dword ptr [rax], 0
0x180015480  lea     rbp, [rax+18h]
0x180015484  mov     byte ptr [rax+4], 0
0x180015488  call    ?GetActivityId@NaturalAuthTraceLogging@@YAPEBU_GUID@@XZ; NaturalAuthTraceLogging::GetActivityId(void)
0x18001548d  mov     esi, 1
0x180015492  mov     rcx, rdi
0x180015495  movups  xmm0, xmmword ptr [rax]
0x180015498  mov     [rdi+4], sil
0x18001549c  movdqu  xmmword ptr [rbp+0], xmm0
0x1800154a1  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x1800154a6  mov     eax, cs:dword_18005C570
0x1800154ac  cmp     eax, 5
0x1800154af  jbe     short loc_1800154DF
0x1800154b1  cmp     byte ptr [rdi+4], 0
0x1800154b5  jz      short loc_1800154C3
0x1800154b7  mov     rcx, rbp; struct _GUID *
0x1800154ba  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800154bf  test    al, al
0x1800154c1  jz      short loc_1800154C5
0x1800154c3  xor     ebp, ebp
0x1800154c5  lea     r8, [rdi+8]
0x1800154c9  mov     r9, rbp
0x1800154cc  lea     rdx, byte_18004FA33
0x1800154d3  lea     rcx, dword_18005C570
0x1800154da  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800154df  mov     rdx, r14; Sid
0x1800154e2  mov     ecx, ebx; unsigned int
0x1800154e4  call    ?ConfigurePolicyBasedDynamicLockRules@@YAJKPEAX@Z; ConfigurePolicyBasedDynamicLockRules(ulong,void *)
0x1800154e9  test    eax, eax
0x1800154eb  jns     short loc_180015568
0x1800154ed  mov     ecx, ebx; unsigned int
0x1800154ef  call    ?ConfigureDefaultDynamicLockRules@@YAJK@Z; ConfigureDefaultDynamicLockRules(ulong)
0x1800154f4  test    eax, eax
0x1800154f6  jns     short loc_180015568
0x1800154f8  mov     r8, cs:qword_18005FC10
0x1800154ff  test    r8, r8
0x180015502  jz      short loc_180015575
0x180015504  mov     dword ptr [r8], 2
0x18001550b  mov     edx, cs:dword_18005C570
0x180015511  cmp     edx, 5
0x180015514  jbe     short loc_18001554A
0x180015516  mov     [rsp+48h+arg_18], eax
0x18001551a  lea     rdx, byte_18004F9AD
0x180015521  lea     rax, [rsp+48h+arg_18]
0x180015526  mov     byte ptr [rsp+48h+arg_10], sil
0x18001552b  mov     [rsp+48h+var_20], rax
0x180015530  lea     rcx, dword_18005C570
0x180015537  lea     rax, [rsp+48h+arg_10]
0x18001553c  add     r8, 8
0x180015540  mov     [rsp+48h+var_28], rax
0x180015545  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x18001554a  mov     rcx, cs:qword_18005FC10; void *
0x180015551  test    rcx, rcx
0x180015554  jz      short loc_18001555B
0x180015556  call    ??_G?$TraceLoggingActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@QEAAPEAXI@Z; TraceLoggingActivity<&_tlgProvider_t const * const g_logProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::`scalar deleting destructor'(uint)
0x18001555b  mov     cs:qword_18005FC10, 0
0x180015566  jmp     short loc_180015575
0x180015568  xchg    sil, cs:byte_18005FC30
0x18001556f  mov     cs:dword_18005CC18, ebx
0x180015575  mov     rbx, [rsp+48h+arg_0]
0x18001557a  mov     rbp, [rsp+48h+arg_8]
0x18001557f  add     rsp, 30h
0x180015583  pop     r14
0x180015585  pop     rdi
0x180015586  pop     rsi
0x180015587  retn
```
