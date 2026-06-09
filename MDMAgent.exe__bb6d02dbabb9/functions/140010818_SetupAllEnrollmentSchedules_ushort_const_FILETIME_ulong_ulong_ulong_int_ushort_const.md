# SetupAllEnrollmentSchedules(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)

- ea: `0x140010818`
- end: `0x1400109f6`
- name: `?SetupAllEnrollmentSchedules@@YAJPEBGU_FILETIME@@KKKH0@Z`
- size: `478`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME, unsigned int, unsigned int, unsigned int, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x14000829c`

## callees

- `0x140007ca4`
- `0x140009004`
- `0x1400094bc`
- `0x1400094e4`
- `0x14000d780`
- `0x14000e3a4`
- `0x14000e84c`
- `0x14000f9a4`
- `0x140010818`
- `0x14001848c`
- `0x140018920`

## import_xrefs

- `DMCmnUtils!DmIsSystemOrAdmin` at `0x140010852`
- `DMCmnUtils!DmIsSystemOrAdmin` at `0x140010852`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14001089a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14001089a`

## pseudocode

```c
__int64 __fastcall SetupAllEnrollmentSchedules(
        unsigned __int16 *a1,
        struct _FILETIME a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        unsigned __int16 *a7)
{
  int IsSystemOrAdmin; // eax
  int v12; // eax
  CEnrollmentLogger *Logger; // rax
  unsigned int v14; // ebx
  int lpData; // [rsp+20h] [rbp-48h]
  int Data; // [rsp+40h] [rbp-28h] BYREF
  int v18; // [rsp+44h] [rbp-24h] BYREF
  _BYTE v19[8]; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v20[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  v18 = 0;
  EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v19, "SetupAllEnrollmentSchedules");
  IsSystemOrAdmin = DmIsSystemOrAdmin(&v18);
  v20[0] = "SetupAllEnrollmentSchedules";
  v20[1] = &Data;
  Data = IsSystemOrAdmin;
  if ( IsSystemOrAdmin >= 0 )
  {
    Data = ScheduleOMADMClientTask(a1, a7);
    if ( Data >= 0 || !v18 )
    {
      v12 = ScheduleDeviceEnrollerOnPFW(a1, a7);
      Data = v12;
      if ( v12 == -2147023179 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE32,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
          (const char *)0x800706B5LL,
          lpData);
        Data = 1;
      }
      else if ( v12 < 0 && v18 && v12 != -2147024769 && v12 != -2147024846 && v12 != -2147009889 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE3C,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
          (const char *)(unsigned int)v12,
          lpData);
        goto LABEL_23;
      }
      Data = ScheduleRenewalSession(a1, a2, a3, a4, a5, a6, a7);
      if ( Data < 0 && v18 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogEnrollManualCertRenewScheduleFailed(Logger, Data);
      }
      else
      {
        Data = ScheduleAlertTask(a1, 0);
        if ( Data >= 0 || !v18 )
        {
          Data = ScheduleAlertTask(a1, 1);
          if ( Data >= 0 || !v18 )
          {
            Data = ScheduleAlertTask(a1, 2);
            if ( Data >= 0 || !v18 )
              Data = 0;
          }
        }
      }
    }
  }
  else
  {
    RegSetKeyValueW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, L"DmIsSystemOrAdmin", 4u, &Data, 4u);
  }
LABEL_23:
  v14 = Data;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v20);
  EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v19);
  return v14;
}

```

## disassembly

```asm
0x140010818  push    rbp
0x14001081a  push    rbx
0x14001081b  push    rsi
0x14001081c  push    rdi
0x14001081d  push    r14
0x14001081f  push    r15
0x140010821  mov     rbp, rsp
0x140010824  sub     rsp, 68h
0x140010828  mov     rbx, rdx
0x14001082b  mov     [rbp+var_24], 0
0x140010832  mov     rdi, rcx
0x140010835  lea     rsi, aSetupallenroll; "SetupAllEnrollmentSchedules"
0x14001083c  mov     rdx, rsi; char *
0x14001083f  lea     rcx, [rbp+var_20]; this
0x140010843  mov     r14d, r9d
0x140010846  mov     r15d, r8d
0x140010849  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x14001084e  lea     rcx, [rbp+var_24]
0x140010852  call    cs:__imp_?DmIsSystemOrAdmin@@YAJPEAH@Z; DmIsSystemOrAdmin(int *)
0x140010859  nop     dword ptr [rax+rax+00h]
0x14001085e  lea     rcx, [rbp+Data]
0x140010862  mov     [rbp+var_18], rsi
0x140010866  mov     [rbp+var_10], rcx
0x14001086a  mov     [rbp+Data], eax
0x14001086d  test    eax, eax
0x14001086f  jns     short loc_1400108AB
0x140010871  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x140010878  lea     rax, [rbp+Data]
0x14001087c  mov     r9d, 4; dwType
0x140010882  lea     r8, aDmissystemorad; "DmIsSystemOrAdmin"
0x140010889  mov     [rsp+68h+cbData], r9d; cbData
0x14001088e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140010895  mov     [rsp+68h+lpData], rax; lpData
0x14001089a  call    cs:__imp_RegSetKeyValueW
0x1400108a1  nop     dword ptr [rax+rax+00h]
0x1400108a6  jmp     loc_1400109D1
0x1400108ab  mov     rsi, [rbp+arg_30]
0x1400108af  mov     rcx, rdi; unsigned __int16 *
0x1400108b2  mov     rdx, rsi; unsigned __int16 *
0x1400108b5  call    ?ScheduleOMADMClientTask@@YAJPEBG0@Z; ScheduleOMADMClientTask(ushort const *,ushort const *)
0x1400108ba  mov     [rbp+Data], eax
0x1400108bd  test    eax, eax
0x1400108bf  jns     short loc_1400108CB
0x1400108c1  cmp     [rbp+var_24], 0
0x1400108c5  jnz     loc_1400109D1
0x1400108cb  mov     rdx, rsi; unsigned __int16 *
0x1400108ce  mov     rcx, rdi; unsigned __int16 *
0x1400108d1  call    ScheduleDeviceEnrollerOnPFW
0x1400108d6  mov     r9d, 800706B5h; char *
0x1400108dc  mov     [rbp+Data], eax
0x1400108df  cmp     eax, r9d
0x1400108e2  jnz     short loc_140010946
0x1400108e4  mov     rcx, [rbp+30h]; this
0x1400108e8  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1400108ef  mov     edx, 0E32h; void *
0x1400108f4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400108f9  mov     [rbp+Data], 1
0x140010900  mov     eax, [rbp+arg_28]
0x140010903  mov     r9d, r14d; unsigned int
0x140010906  mov     [rsp+68h+var_38], rsi; unsigned __int16 *
0x14001090b  mov     r8d, r15d; unsigned int
0x14001090e  mov     [rsp+68h+cbData], eax; int
0x140010912  mov     rdx, rbx; struct _FILETIME
0x140010915  mov     eax, [rbp+arg_20]
0x140010918  mov     rcx, rdi; unsigned __int16 *
0x14001091b  mov     dword ptr [rsp+68h+lpData], eax; unsigned int
0x14001091f  call    ?ScheduleRenewalSession@@YAJPEBGU_FILETIME@@KKKH0@Z; ScheduleRenewalSession(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)
0x140010924  mov     [rbp+Data], eax
0x140010927  test    eax, eax
0x140010929  jns     short loc_14001097F
0x14001092b  cmp     [rbp+var_24], 0
0x14001092f  jz      short loc_14001097F
0x140010931  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140010936  mov     edx, [rbp+Data]; int
0x140010939  mov     rcx, rax; this
0x14001093c  call    ?LogEnrollManualCertRenewScheduleFailed@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogEnrollManualCertRenewScheduleFailed(long)
0x140010941  jmp     loc_1400109D1
0x140010946  test    eax, eax
0x140010948  jns     short loc_140010900
0x14001094a  cmp     [rbp+var_24], 0
0x14001094e  jz      short loc_140010900
0x140010950  cmp     eax, 8007007Fh
0x140010955  jz      short loc_140010900
0x140010957  cmp     eax, 80070032h
0x14001095c  jz      short loc_140010900
0x14001095e  cmp     eax, 80073A9Fh
0x140010963  jz      short loc_140010900
0x140010965  mov     rcx, [rbp+30h]; this
0x140010969  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140010970  mov     r9d, eax; char *
0x140010973  mov     edx, 0E3Ch; void *
0x140010978  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001097d  jmp     short loc_1400109D1
0x14001097f  xor     edx, edx
0x140010981  mov     rcx, rdi
0x140010984  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x140010989  mov     [rbp+Data], eax
0x14001098c  test    eax, eax
0x14001098e  jns     short loc_140010996
0x140010990  cmp     [rbp+var_24], 0
0x140010994  jnz     short loc_1400109D1
0x140010996  mov     edx, 1
0x14001099b  mov     rcx, rdi
0x14001099e  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x1400109a3  mov     [rbp+Data], eax
0x1400109a6  test    eax, eax
0x1400109a8  jns     short loc_1400109B0
0x1400109aa  cmp     [rbp+var_24], 0
0x1400109ae  jnz     short loc_1400109D1
0x1400109b0  mov     edx, 2
0x1400109b5  mov     rcx, rdi
0x1400109b8  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x1400109bd  mov     [rbp+Data], eax
0x1400109c0  test    eax, eax
0x1400109c2  jns     short loc_1400109CA
0x1400109c4  cmp     [rbp+var_24], 0
0x1400109c8  jnz     short loc_1400109D1
0x1400109ca  mov     [rbp+Data], 0
0x1400109d1  mov     ebx, [rbp+Data]
0x1400109d4  lea     rcx, [rbp+var_18]; this
0x1400109d8  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1400109dd  lea     rcx, [rbp+var_20]; this
0x1400109e1  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1400109e6  mov     eax, ebx
0x1400109e8  add     rsp, 68h
0x1400109ec  pop     r15
0x1400109ee  pop     r14
0x1400109f0  pop     rdi
0x1400109f1  pop     rsi
0x1400109f2  pop     rbx
0x1400109f3  pop     rbp
0x1400109f4  retn
```
