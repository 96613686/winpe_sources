# SetupAllEnrollmentSchedules(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)

- ea: `0x180094c70`
- end: `0x180094e38`
- name: `?SetupAllEnrollmentSchedules@@YAJPEBGU_FILETIME@@KKKH0@Z`
- size: `456`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME, unsigned int, unsigned int, unsigned int, int, const unsigned __int16 *Data)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800323e8`

## callees

- `0x180038c94`
- `0x1800908d4`
- `0x180090a88`
- `0x180090ab0`
- `0x180092abc`
- `0x180093578`
- `0x180093a0c`
- `0x180094120`
- `0x180094c70`
- `0x180095efc`
- `0x18009685c`

## import_xrefs

- `DMCmnUtils!DmIsSystemOrAdmin` at `0x180094c9e`
- `DMCmnUtils!DmIsSystemOrAdmin` at `0x180094c9e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180094ced`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180094ced`

## pseudocode

```c
__int64 __fastcall SetupAllEnrollmentSchedules(
        unsigned __int16 *a1,
        struct _FILETIME a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        int a6,
        const unsigned __int16 *Data)
{
  const unsigned __int16 *v11; // rdx
  int v12; // eax
  CEnrollmentLogger *Logger; // rax
  unsigned int v14; // ebx
  int lpData; // [rsp+20h] [rbp-40h]
  const unsigned __int16 *v17; // [rsp+30h] [rbp-30h]
  int v18; // [rsp+40h] [rbp-20h] BYREF
  _BYTE v19[8]; // [rsp+48h] [rbp-18h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v18 = 0;
  EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v19, *(const char **)&a2);
  LODWORD(Data) = DmIsSystemOrAdmin(&v18);
  v20[0] = "SetupAllEnrollmentSchedules";
  v20[1] = &Data;
  if ( (int)Data >= 0 )
  {
    LODWORD(Data) = ScheduleOMADMClientTask(a1, v11);
    if ( (int)Data >= 0 || !v18 )
    {
      v12 = ScheduleDeviceEnrollerOnPFW(a1);
      LODWORD(Data) = v12;
      if ( v12 == -2147023179 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xE32,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
          (const char *)0x800706B5LL,
          lpData);
        LODWORD(Data) = 1;
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
      LODWORD(Data) = ScheduleRenewalSession(a1, a2, a3, a4, a5, a6, v17);
      if ( (int)Data < 0 && v18 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogEnrollManualCertRenewScheduleFailed(Logger, (int)Data);
      }
      else
      {
        LODWORD(Data) = ScheduleAlertTask(a1, 0);
        if ( (int)Data >= 0 || !v18 )
        {
          LODWORD(Data) = ScheduleAlertTask(a1, 1);
          if ( (int)Data >= 0 || !v18 )
          {
            LODWORD(Data) = ScheduleAlertTask(a1, 2);
            if ( (int)Data >= 0 || !v18 )
              LODWORD(Data) = 0;
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
  v14 = (unsigned int)Data;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v20);
  EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v19);
  return v14;
}

```

## disassembly

```asm
0x180094c70  push    rbp
0x180094c72  push    rbx
0x180094c73  push    rsi
0x180094c74  push    rdi
0x180094c75  push    r14
0x180094c77  mov     rbp, rsp
0x180094c7a  sub     rsp, 60h
0x180094c7e  mov     rdi, rcx
0x180094c81  mov     [rbp+var_20], 0
0x180094c88  lea     rcx, [rbp+var_18]; this
0x180094c8c  mov     esi, r9d
0x180094c8f  mov     r14d, r8d
0x180094c92  mov     rbx, rdx
0x180094c95  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x180094c9a  lea     rcx, [rbp+var_20]
0x180094c9e  call    cs:__imp_?DmIsSystemOrAdmin@@YAJPEAH@Z; DmIsSystemOrAdmin(int *)
0x180094ca5  nop     dword ptr [rax+rax+00h]
0x180094caa  mov     dword ptr [rbp+Data], eax
0x180094cad  lea     rcx, aSetupallenroll; "SetupAllEnrollmentSchedules"
0x180094cb4  mov     [rbp+var_10], rcx
0x180094cb8  lea     rcx, [rbp+Data]
0x180094cbc  mov     [rbp+var_8], rcx
0x180094cc0  test    eax, eax
0x180094cc2  jns     short loc_180094CFE
0x180094cc4  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x180094ccb  lea     rax, [rbp+Data]
0x180094ccf  mov     r9d, 4; dwType
0x180094cd5  lea     r8, aDmissystemorad; "DmIsSystemOrAdmin"
0x180094cdc  mov     [rsp+60h+cbData], r9d; cbData
0x180094ce1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180094ce8  mov     [rsp+60h+lpData], rax; lpData
0x180094ced  call    cs:__imp_RegSetKeyValueW
0x180094cf4  nop     dword ptr [rax+rax+00h]
0x180094cf9  jmp     loc_180094E15
0x180094cfe  mov     rcx, rdi; unsigned __int16 *
0x180094d01  call    ?ScheduleOMADMClientTask@@YAJPEBG0@Z; ScheduleOMADMClientTask(ushort const *,ushort const *)
0x180094d06  mov     dword ptr [rbp+Data], eax
0x180094d09  test    eax, eax
0x180094d0b  jns     short loc_180094D17
0x180094d0d  cmp     [rbp+var_20], 0
0x180094d11  jnz     loc_180094E15
0x180094d17  mov     rcx, rdi
0x180094d1a  call    ScheduleDeviceEnrollerOnPFW
0x180094d1f  mov     r9d, 800706B5h; char *
0x180094d25  mov     dword ptr [rbp+Data], eax
0x180094d28  cmp     eax, r9d
0x180094d2b  jnz     short loc_180094D8A
0x180094d2d  mov     rcx, [rbp+28h]; this
0x180094d31  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180094d38  mov     edx, 0E32h; void *
0x180094d3d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180094d42  mov     dword ptr [rbp+Data], 1
0x180094d49  mov     eax, [rbp+arg_28]
0x180094d4c  mov     r9d, esi; unsigned int
0x180094d4f  mov     [rsp+60h+cbData], eax; int
0x180094d53  mov     r8d, r14d; unsigned int
0x180094d56  mov     eax, [rbp+arg_20]
0x180094d59  mov     rdx, rbx; struct _FILETIME
0x180094d5c  mov     rcx, rdi; unsigned __int16 *
0x180094d5f  mov     dword ptr [rsp+60h+lpData], eax; unsigned int
0x180094d63  call    ?ScheduleRenewalSession@@YAJPEBGU_FILETIME@@KKKH0@Z; ScheduleRenewalSession(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)
0x180094d68  mov     dword ptr [rbp+Data], eax
0x180094d6b  test    eax, eax
0x180094d6d  jns     short loc_180094DC3
0x180094d6f  cmp     [rbp+var_20], 0
0x180094d73  jz      short loc_180094DC3
0x180094d75  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x180094d7a  mov     edx, dword ptr [rbp+Data]; int
0x180094d7d  mov     rcx, rax; this
0x180094d80  call    ?LogEnrollManualCertRenewScheduleFailed@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogEnrollManualCertRenewScheduleFailed(long)
0x180094d85  jmp     loc_180094E15
0x180094d8a  test    eax, eax
0x180094d8c  jns     short loc_180094D49
0x180094d8e  cmp     [rbp+var_20], 0
0x180094d92  jz      short loc_180094D49
0x180094d94  cmp     eax, 8007007Fh
0x180094d99  jz      short loc_180094D49
0x180094d9b  cmp     eax, 80070032h
0x180094da0  jz      short loc_180094D49
0x180094da2  cmp     eax, 80073A9Fh
0x180094da7  jz      short loc_180094D49
0x180094da9  mov     rcx, [rbp+28h]; this
0x180094dad  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180094db4  mov     r9d, eax; char *
0x180094db7  mov     edx, 0E3Ch; void *
0x180094dbc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180094dc1  jmp     short loc_180094E15
0x180094dc3  xor     edx, edx
0x180094dc5  mov     rcx, rdi
0x180094dc8  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x180094dcd  mov     dword ptr [rbp+Data], eax
0x180094dd0  test    eax, eax
0x180094dd2  jns     short loc_180094DDA
0x180094dd4  cmp     [rbp+var_20], 0
0x180094dd8  jnz     short loc_180094E15
0x180094dda  mov     edx, 1
0x180094ddf  mov     rcx, rdi
0x180094de2  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x180094de7  mov     dword ptr [rbp+Data], eax
0x180094dea  test    eax, eax
0x180094dec  jns     short loc_180094DF4
0x180094dee  cmp     [rbp+var_20], 0
0x180094df2  jnz     short loc_180094E15
0x180094df4  mov     edx, 2
0x180094df9  mov     rcx, rdi
0x180094dfc  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x180094e01  mov     dword ptr [rbp+Data], eax
0x180094e04  test    eax, eax
0x180094e06  jns     short loc_180094E0E
0x180094e08  cmp     [rbp+var_20], 0
0x180094e0c  jnz     short loc_180094E15
0x180094e0e  mov     dword ptr [rbp+Data], 0
0x180094e15  mov     ebx, dword ptr [rbp+Data]
0x180094e18  lea     rcx, [rbp+var_10]; this
0x180094e1c  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x180094e21  lea     rcx, [rbp+var_18]; this
0x180094e25  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x180094e2a  mov     eax, ebx
0x180094e2c  add     rsp, 60h
0x180094e30  pop     r14
0x180094e32  pop     rdi
0x180094e33  pop     rsi
0x180094e34  pop     rbx
0x180094e35  pop     rbp
0x180094e36  retn
```
