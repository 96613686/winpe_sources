# SetupAllEnrollmentSchedules(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)

- ea: `0x140010000`
- end: `0x1400101d1`
- name: `?SetupAllEnrollmentSchedules@@YAJPEBGU_FILETIME@@KKKH0@Z`
- size: `465`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _FILETIME, unsigned int, unsigned int, unsigned int, int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x140007f34`

## callees

- `0x1400079c0`
- `0x140008bf4`
- `0x1400090d4`
- `0x1400090fc`
- `0x14000d0fc`
- `0x14000dca0`
- `0x14000e128`
- `0x14000f1f8`
- `0x140010000`
- `0x1400177b0`
- `0x140017c2c`

## import_xrefs

- `DMCmnUtils!DmIsSystemOrAdmin` at `0x14001003a`
- `DMCmnUtils!DmIsSystemOrAdmin` at `0x14001003a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14001007c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14001007c`

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
0x140010000  push    rbp
0x140010002  push    rbx
0x140010003  push    rsi
0x140010004  push    rdi
0x140010005  push    r14
0x140010007  push    r15
0x140010009  mov     rbp, rsp
0x14001000c  sub     rsp, 68h
0x140010010  mov     rbx, rdx
0x140010013  mov     [rbp+var_24], 0
0x14001001a  mov     rdi, rcx
0x14001001d  lea     rsi, aSetupallenroll; "SetupAllEnrollmentSchedules"
0x140010024  mov     rdx, rsi; char *
0x140010027  lea     rcx, [rbp+var_20]; this
0x14001002b  mov     r14d, r9d
0x14001002e  mov     r15d, r8d
0x140010031  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x140010036  lea     rcx, [rbp+var_24]
0x14001003a  call    cs:__imp_?DmIsSystemOrAdmin@@YAJPEAH@Z; DmIsSystemOrAdmin(int *)
0x140010040  lea     rcx, [rbp+Data]
0x140010044  mov     [rbp+var_18], rsi
0x140010048  mov     [rbp+var_10], rcx
0x14001004c  mov     [rbp+Data], eax
0x14001004f  test    eax, eax
0x140010051  jns     short loc_140010087
0x140010053  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x14001005a  lea     rax, [rbp+Data]
0x14001005e  mov     r9d, 4; dwType
0x140010064  lea     r8, aDmissystemorad; "DmIsSystemOrAdmin"
0x14001006b  mov     [rsp+68h+cbData], r9d; cbData
0x140010070  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140010077  mov     [rsp+68h+lpData], rax; lpData
0x14001007c  call    cs:__imp_RegSetKeyValueW
0x140010082  jmp     loc_1400101AD
0x140010087  mov     rsi, [rbp+arg_30]
0x14001008b  mov     rcx, rdi; unsigned __int16 *
0x14001008e  mov     rdx, rsi; unsigned __int16 *
0x140010091  call    ?ScheduleOMADMClientTask@@YAJPEBG0@Z; ScheduleOMADMClientTask(ushort const *,ushort const *)
0x140010096  mov     [rbp+Data], eax
0x140010099  test    eax, eax
0x14001009b  jns     short loc_1400100A7
0x14001009d  cmp     [rbp+var_24], 0
0x1400100a1  jnz     loc_1400101AD
0x1400100a7  mov     rdx, rsi; unsigned __int16 *
0x1400100aa  mov     rcx, rdi; unsigned __int16 *
0x1400100ad  call    ScheduleDeviceEnrollerOnPFW
0x1400100b2  mov     r9d, 800706B5h; char *
0x1400100b8  mov     [rbp+Data], eax
0x1400100bb  cmp     eax, r9d
0x1400100be  jnz     short loc_140010122
0x1400100c0  mov     rcx, [rbp+30h]; this
0x1400100c4  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1400100cb  mov     edx, 0E32h; void *
0x1400100d0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400100d5  mov     [rbp+Data], 1
0x1400100dc  mov     eax, [rbp+arg_28]
0x1400100df  mov     r9d, r14d; unsigned int
0x1400100e2  mov     [rsp+68h+var_38], rsi; unsigned __int16 *
0x1400100e7  mov     r8d, r15d; unsigned int
0x1400100ea  mov     [rsp+68h+cbData], eax; int
0x1400100ee  mov     rdx, rbx; struct _FILETIME
0x1400100f1  mov     eax, [rbp+arg_20]
0x1400100f4  mov     rcx, rdi; unsigned __int16 *
0x1400100f7  mov     dword ptr [rsp+68h+lpData], eax; unsigned int
0x1400100fb  call    ?ScheduleRenewalSession@@YAJPEBGU_FILETIME@@KKKH0@Z; ScheduleRenewalSession(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)
0x140010100  mov     [rbp+Data], eax
0x140010103  test    eax, eax
0x140010105  jns     short loc_14001015B
0x140010107  cmp     [rbp+var_24], 0
0x14001010b  jz      short loc_14001015B
0x14001010d  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140010112  mov     edx, [rbp+Data]; int
0x140010115  mov     rcx, rax; this
0x140010118  call    ?LogEnrollManualCertRenewScheduleFailed@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogEnrollManualCertRenewScheduleFailed(long)
0x14001011d  jmp     loc_1400101AD
0x140010122  test    eax, eax
0x140010124  jns     short loc_1400100DC
0x140010126  cmp     [rbp+var_24], 0
0x14001012a  jz      short loc_1400100DC
0x14001012c  cmp     eax, 8007007Fh
0x140010131  jz      short loc_1400100DC
0x140010133  cmp     eax, 80070032h
0x140010138  jz      short loc_1400100DC
0x14001013a  cmp     eax, 80073A9Fh
0x14001013f  jz      short loc_1400100DC
0x140010141  mov     rcx, [rbp+30h]; this
0x140010145  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14001014c  mov     r9d, eax; char *
0x14001014f  mov     edx, 0E3Ch; void *
0x140010154  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140010159  jmp     short loc_1400101AD
0x14001015b  xor     edx, edx
0x14001015d  mov     rcx, rdi
0x140010160  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x140010165  mov     [rbp+Data], eax
0x140010168  test    eax, eax
0x14001016a  jns     short loc_140010172
0x14001016c  cmp     [rbp+var_24], 0
0x140010170  jnz     short loc_1400101AD
0x140010172  mov     edx, 1
0x140010177  mov     rcx, rdi
0x14001017a  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x14001017f  mov     [rbp+Data], eax
0x140010182  test    eax, eax
0x140010184  jns     short loc_14001018C
0x140010186  cmp     [rbp+var_24], 0
0x14001018a  jnz     short loc_1400101AD
0x14001018c  mov     edx, 2
0x140010191  mov     rcx, rdi
0x140010194  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x140010199  mov     [rbp+Data], eax
0x14001019c  test    eax, eax
0x14001019e  jns     short loc_1400101A6
0x1400101a0  cmp     [rbp+var_24], 0
0x1400101a4  jnz     short loc_1400101AD
0x1400101a6  mov     [rbp+Data], 0
0x1400101ad  mov     ebx, [rbp+Data]
0x1400101b0  lea     rcx, [rbp+var_18]; this
0x1400101b4  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1400101b9  lea     rcx, [rbp+var_20]; this
0x1400101bd  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1400101c2  mov     eax, ebx
0x1400101c4  add     rsp, 68h
0x1400101c8  pop     r15
0x1400101ca  pop     r14
0x1400101cc  pop     rdi
0x1400101cd  pop     rsi
0x1400101ce  pop     rbx
0x1400101cf  pop     rbp
0x1400101d0  retn
```
