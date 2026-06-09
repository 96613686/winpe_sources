# SetupAllEnrollmentSchedules(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)

- ea: `0x18000fc24`
- end: `0x18000fded`
- name: `?SetupAllEnrollmentSchedules@@YAJPEBGU_FILETIME@@KKKH0@Z`
- size: `457`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME, unsigned int, unsigned int, unsigned int, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180004168`

## callees

- `0x18000707c`
- `0x180007778`
- `0x1800077a0`
- `0x18000c980`
- `0x18000d590`
- `0x18000da38`
- `0x18000eb90`
- `0x18000fc24`
- `0x180011418`
- `0x180012b80`
- `0x18001b9d8`
- `0x18001be70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000fc9f`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18000fc9f`

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
  int v11; // eax
  unsigned int v12; // r8d
  CEnrollmentLogger *Logger; // rax
  unsigned int v14; // ebx
  int lpData; // [rsp+20h] [rbp-48h]
  int Data; // [rsp+40h] [rbp-28h] BYREF
  WINBOOL IsMember; // [rsp+44h] [rbp-24h] BYREF
  _BYTE v19[8]; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v20[3]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]

  IsMember = 0;
  EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v19, "SetupAllEnrollmentSchedules");
  Data = DmIsSystemOrAdmin(&IsMember);
  v20[1] = &Data;
  v20[0] = "SetupAllEnrollmentSchedules";
  if ( Data >= 0 )
  {
    Data = ScheduleOMADMClientTask(a1, a7);
    if ( Data >= 0 || !IsMember )
    {
      v11 = ScheduleDeviceEnrollerOnPFW(a1, a7);
      Data = v11;
      if ( v11 == -2147023179 )
      {
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xE32, v12, (const char *)0x800706B5LL, lpData);
        Data = 1;
      }
      else if ( v11 < 0 && IsMember && v11 != -2147024769 && v11 != -2147024846 && v11 != -2147009889 )
      {
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xE3C, v12, (const char *)(unsigned int)v11, lpData);
        goto LABEL_23;
      }
      Data = ScheduleRenewalSession(a1, a2, a3, a4, a5, a6, a7);
      if ( Data < 0 && IsMember )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogEnrollManualCertRenewScheduleFailed(Logger, Data);
      }
      else
      {
        Data = ScheduleAlertTask(a1, 0);
        if ( Data >= 0 || !IsMember )
        {
          Data = ScheduleAlertTask(a1, 1);
          if ( Data >= 0 || !IsMember )
          {
            Data = ScheduleAlertTask(a1, 2);
            if ( Data >= 0 || !IsMember )
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
0x18000fc24  push    rbp
0x18000fc26  push    rbx
0x18000fc27  push    rsi
0x18000fc28  push    rdi
0x18000fc29  push    r14
0x18000fc2b  push    r15
0x18000fc2d  mov     rbp, rsp
0x18000fc30  sub     rsp, 68h
0x18000fc34  mov     rbx, rdx
0x18000fc37  mov     [rbp+IsMember], 0
0x18000fc3e  mov     rdi, rcx
0x18000fc41  lea     rsi, aSetupallenroll; "SetupAllEnrollmentSchedules"
0x18000fc48  mov     rdx, rsi; char *
0x18000fc4b  lea     rcx, [rbp+var_20]; this
0x18000fc4f  mov     r14d, r9d
0x18000fc52  mov     r15d, r8d
0x18000fc55  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x18000fc5a  lea     rcx, [rbp+IsMember]; IsMember
0x18000fc5e  call    ?DmIsSystemOrAdmin@@YAJPEAH@Z; DmIsSystemOrAdmin(int *)
0x18000fc63  mov     [rbp+Data], eax
0x18000fc66  lea     rcx, [rbp+Data]
0x18000fc6a  mov     [rbp+var_10], rcx
0x18000fc6e  mov     [rbp+var_18], rsi
0x18000fc72  test    eax, eax
0x18000fc74  jns     short loc_18000FCB0
0x18000fc76  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x18000fc7d  lea     rax, [rbp+Data]
0x18000fc81  mov     r9d, 4; dwType
0x18000fc87  lea     r8, aDmissystemorad; "DmIsSystemOrAdmin"
0x18000fc8e  mov     [rsp+68h+cbData], r9d; cbData
0x18000fc93  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000fc9a  mov     [rsp+68h+lpData], rax; lpData
0x18000fc9f  call    cs:__imp_RegSetKeyValueW
0x18000fca6  nop     dword ptr [rax+rax+00h]
0x18000fcab  jmp     loc_18000FDC8
0x18000fcb0  mov     rsi, [rbp+arg_30]
0x18000fcb4  mov     rcx, rdi; unsigned __int16 *
0x18000fcb7  mov     rdx, rsi; unsigned __int16 *
0x18000fcba  call    ?ScheduleOMADMClientTask@@YAJPEBG0@Z; ScheduleOMADMClientTask(ushort const *,ushort const *)
0x18000fcbf  mov     [rbp+Data], eax
0x18000fcc2  test    eax, eax
0x18000fcc4  jns     short loc_18000FCD0
0x18000fcc6  cmp     [rbp+IsMember], 0
0x18000fcca  jnz     loc_18000FDC8
0x18000fcd0  mov     rdx, rsi
0x18000fcd3  mov     rcx, rdi
0x18000fcd6  call    ScheduleDeviceEnrollerOnPFW
0x18000fcdb  mov     r9d, 800706B5h; char *
0x18000fce1  mov     [rbp+Data], eax
0x18000fce4  cmp     eax, r9d
0x18000fce7  jnz     short loc_18000FD44
0x18000fce9  mov     rcx, [rbp+30h]; this
0x18000fced  mov     edx, 0E32h; void *
0x18000fcf2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000fcf7  mov     [rbp+Data], 1
0x18000fcfe  mov     eax, [rbp+arg_28]
0x18000fd01  mov     r9d, r14d; unsigned int
0x18000fd04  mov     [rsp+68h+var_38], rsi; unsigned __int16 *
0x18000fd09  mov     r8d, r15d; unsigned int
0x18000fd0c  mov     [rsp+68h+cbData], eax; int
0x18000fd10  mov     rdx, rbx; struct _FILETIME
0x18000fd13  mov     eax, [rbp+arg_20]
0x18000fd16  mov     rcx, rdi; unsigned __int16 *
0x18000fd19  mov     dword ptr [rsp+68h+lpData], eax; unsigned int
0x18000fd1d  call    ?ScheduleRenewalSession@@YAJPEBGU_FILETIME@@KKKH0@Z; ScheduleRenewalSession(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)
0x18000fd22  mov     [rbp+Data], eax
0x18000fd25  test    eax, eax
0x18000fd27  jns     short loc_18000FD76
0x18000fd29  cmp     [rbp+IsMember], 0
0x18000fd2d  jz      short loc_18000FD76
0x18000fd2f  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18000fd34  mov     edx, [rbp+Data]; int
0x18000fd37  mov     rcx, rax; this
0x18000fd3a  call    ?LogEnrollManualCertRenewScheduleFailed@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogEnrollManualCertRenewScheduleFailed(long)
0x18000fd3f  jmp     loc_18000FDC8
0x18000fd44  test    eax, eax
0x18000fd46  jns     short loc_18000FCFE
0x18000fd48  cmp     [rbp+IsMember], 0
0x18000fd4c  jz      short loc_18000FCFE
0x18000fd4e  cmp     eax, 8007007Fh
0x18000fd53  jz      short loc_18000FCFE
0x18000fd55  cmp     eax, 80070032h
0x18000fd5a  jz      short loc_18000FCFE
0x18000fd5c  cmp     eax, 80073A9Fh
0x18000fd61  jz      short loc_18000FCFE
0x18000fd63  mov     rcx, [rbp+30h]; this
0x18000fd67  mov     r9d, eax; char *
0x18000fd6a  mov     edx, 0E3Ch; void *
0x18000fd6f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000fd74  jmp     short loc_18000FDC8
0x18000fd76  xor     edx, edx
0x18000fd78  mov     rcx, rdi
0x18000fd7b  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x18000fd80  mov     [rbp+Data], eax
0x18000fd83  test    eax, eax
0x18000fd85  jns     short loc_18000FD8D
0x18000fd87  cmp     [rbp+IsMember], 0
0x18000fd8b  jnz     short loc_18000FDC8
0x18000fd8d  mov     edx, 1
0x18000fd92  mov     rcx, rdi
0x18000fd95  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x18000fd9a  mov     [rbp+Data], eax
0x18000fd9d  test    eax, eax
0x18000fd9f  jns     short loc_18000FDA7
0x18000fda1  cmp     [rbp+IsMember], 0
0x18000fda5  jnz     short loc_18000FDC8
0x18000fda7  mov     edx, 2
0x18000fdac  mov     rcx, rdi
0x18000fdaf  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x18000fdb4  mov     [rbp+Data], eax
0x18000fdb7  test    eax, eax
0x18000fdb9  jns     short loc_18000FDC1
0x18000fdbb  cmp     [rbp+IsMember], 0
0x18000fdbf  jnz     short loc_18000FDC8
0x18000fdc1  mov     [rbp+Data], 0
0x18000fdc8  mov     ebx, [rbp+Data]
0x18000fdcb  lea     rcx, [rbp+var_18]; this
0x18000fdcf  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18000fdd4  lea     rcx, [rbp+var_20]; this
0x18000fdd8  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x18000fddd  mov     eax, ebx
0x18000fddf  add     rsp, 68h
0x18000fde3  pop     r15
0x18000fde5  pop     r14
0x18000fde7  pop     rdi
0x18000fde8  pop     rsi
0x18000fde9  pop     rbx
0x18000fdea  pop     rbp
0x18000fdeb  retn
```
