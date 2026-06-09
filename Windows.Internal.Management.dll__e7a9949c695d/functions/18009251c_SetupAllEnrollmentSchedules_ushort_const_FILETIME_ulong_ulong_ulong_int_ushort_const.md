# SetupAllEnrollmentSchedules(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)

- ea: `0x18009251c`
- end: `0x1800926d7`
- name: `?SetupAllEnrollmentSchedules@@YAJPEBGU_FILETIME@@KKKH0@Z`
- size: `443`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct _FILETIME, unsigned int, unsigned int, unsigned int, int, const unsigned __int16 *Data)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180033584`

## callees

- `0x180039990`
- `0x18008e3c4`
- `0x18008e55c`
- `0x18008e584`
- `0x180090484`
- `0x180090edc`
- `0x180091350`
- `0x180091a28`
- `0x18009251c`
- `0x180093684`
- `0x180093fc0`

## import_xrefs

- `DMCmnUtils!DmIsSystemOrAdmin` at `0x18009254a`
- `DMCmnUtils!DmIsSystemOrAdmin` at `0x18009254a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180092593`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180092593`

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
0x18009251c  push    rbp
0x18009251e  push    rbx
0x18009251f  push    rsi
0x180092520  push    rdi
0x180092521  push    r14
0x180092523  mov     rbp, rsp
0x180092526  sub     rsp, 60h
0x18009252a  mov     rdi, rcx
0x18009252d  mov     [rbp+var_20], 0
0x180092534  lea     rcx, [rbp+var_18]; this
0x180092538  mov     esi, r9d
0x18009253b  mov     r14d, r8d
0x18009253e  mov     rbx, rdx
0x180092541  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x180092546  lea     rcx, [rbp+var_20]
0x18009254a  call    cs:__imp_?DmIsSystemOrAdmin@@YAJPEAH@Z; DmIsSystemOrAdmin(int *)
0x180092550  mov     dword ptr [rbp+Data], eax
0x180092553  lea     rcx, aSetupallenroll; "SetupAllEnrollmentSchedules"
0x18009255a  mov     [rbp+var_10], rcx
0x18009255e  lea     rcx, [rbp+Data]
0x180092562  mov     [rbp+var_8], rcx
0x180092566  test    eax, eax
0x180092568  jns     short loc_18009259E
0x18009256a  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x180092571  lea     rax, [rbp+Data]
0x180092575  mov     r9d, 4; dwType
0x18009257b  lea     r8, aDmissystemorad; "DmIsSystemOrAdmin"
0x180092582  mov     [rsp+60h+cbData], r9d; cbData
0x180092587  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009258e  mov     [rsp+60h+lpData], rax; lpData
0x180092593  call    cs:__imp_RegSetKeyValueW
0x180092599  jmp     loc_1800926B5
0x18009259e  mov     rcx, rdi; unsigned __int16 *
0x1800925a1  call    ?ScheduleOMADMClientTask@@YAJPEBG0@Z; ScheduleOMADMClientTask(ushort const *,ushort const *)
0x1800925a6  mov     dword ptr [rbp+Data], eax
0x1800925a9  test    eax, eax
0x1800925ab  jns     short loc_1800925B7
0x1800925ad  cmp     [rbp+var_20], 0
0x1800925b1  jnz     loc_1800926B5
0x1800925b7  mov     rcx, rdi
0x1800925ba  call    ScheduleDeviceEnrollerOnPFW
0x1800925bf  mov     r9d, 800706B5h; char *
0x1800925c5  mov     dword ptr [rbp+Data], eax
0x1800925c8  cmp     eax, r9d
0x1800925cb  jnz     short loc_18009262A
0x1800925cd  mov     rcx, [rbp+28h]; this
0x1800925d1  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800925d8  mov     edx, 0E32h; void *
0x1800925dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800925e2  mov     dword ptr [rbp+Data], 1
0x1800925e9  mov     eax, [rbp+arg_28]
0x1800925ec  mov     r9d, esi; unsigned int
0x1800925ef  mov     [rsp+60h+cbData], eax; int
0x1800925f3  mov     r8d, r14d; unsigned int
0x1800925f6  mov     eax, [rbp+arg_20]
0x1800925f9  mov     rdx, rbx; struct _FILETIME
0x1800925fc  mov     rcx, rdi; unsigned __int16 *
0x1800925ff  mov     dword ptr [rsp+60h+lpData], eax; unsigned int
0x180092603  call    ?ScheduleRenewalSession@@YAJPEBGU_FILETIME@@KKKH0@Z; ScheduleRenewalSession(ushort const *,_FILETIME,ulong,ulong,ulong,int,ushort const *)
0x180092608  mov     dword ptr [rbp+Data], eax
0x18009260b  test    eax, eax
0x18009260d  jns     short loc_180092663
0x18009260f  cmp     [rbp+var_20], 0
0x180092613  jz      short loc_180092663
0x180092615  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18009261a  mov     edx, dword ptr [rbp+Data]; int
0x18009261d  mov     rcx, rax; this
0x180092620  call    ?LogEnrollManualCertRenewScheduleFailed@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogEnrollManualCertRenewScheduleFailed(long)
0x180092625  jmp     loc_1800926B5
0x18009262a  test    eax, eax
0x18009262c  jns     short loc_1800925E9
0x18009262e  cmp     [rbp+var_20], 0
0x180092632  jz      short loc_1800925E9
0x180092634  cmp     eax, 8007007Fh
0x180092639  jz      short loc_1800925E9
0x18009263b  cmp     eax, 80070032h
0x180092640  jz      short loc_1800925E9
0x180092642  cmp     eax, 80073A9Fh
0x180092647  jz      short loc_1800925E9
0x180092649  mov     rcx, [rbp+28h]; this
0x18009264d  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180092654  mov     r9d, eax; char *
0x180092657  mov     edx, 0E3Ch; void *
0x18009265c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180092661  jmp     short loc_1800926B5
0x180092663  xor     edx, edx
0x180092665  mov     rcx, rdi
0x180092668  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x18009266d  mov     dword ptr [rbp+Data], eax
0x180092670  test    eax, eax
0x180092672  jns     short loc_18009267A
0x180092674  cmp     [rbp+var_20], 0
0x180092678  jnz     short loc_1800926B5
0x18009267a  mov     edx, 1
0x18009267f  mov     rcx, rdi
0x180092682  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x180092687  mov     dword ptr [rbp+Data], eax
0x18009268a  test    eax, eax
0x18009268c  jns     short loc_180092694
0x18009268e  cmp     [rbp+var_20], 0
0x180092692  jnz     short loc_1800926B5
0x180092694  mov     edx, 2
0x180092699  mov     rcx, rdi
0x18009269c  call    ?ScheduleAlertTask@@YAJPEBGW4DMAlertType@@@Z; ScheduleAlertTask(ushort const *,DMAlertType)
0x1800926a1  mov     dword ptr [rbp+Data], eax
0x1800926a4  test    eax, eax
0x1800926a6  jns     short loc_1800926AE
0x1800926a8  cmp     [rbp+var_20], 0
0x1800926ac  jnz     short loc_1800926B5
0x1800926ae  mov     dword ptr [rbp+Data], 0
0x1800926b5  mov     ebx, dword ptr [rbp+Data]
0x1800926b8  lea     rcx, [rbp+var_10]; this
0x1800926bc  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x1800926c1  lea     rcx, [rbp+var_18]; this
0x1800926c5  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800926ca  mov     eax, ebx
0x1800926cc  add     rsp, 60h
0x1800926d0  pop     r14
0x1800926d2  pop     rdi
0x1800926d3  pop     rsi
0x1800926d4  pop     rbx
0x1800926d5  pop     rbp
0x1800926d6  retn
```
