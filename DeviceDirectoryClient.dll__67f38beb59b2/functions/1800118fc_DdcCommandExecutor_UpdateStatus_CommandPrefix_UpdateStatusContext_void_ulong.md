# DdcCommandExecutor::UpdateStatus(CommandPrefix *,UpdateStatusContext *,void *,ulong *)

- ea: `0x1800118fc`
- end: `0x180011be8`
- name: `?UpdateStatus@DdcCommandExecutor@@SAJPEAUCommandPrefix@@PEAUUpdateStatusContext@@PEAXPEAK@Z`
- size: `748`
- prototype: `__int64 __fastcall(struct CommandPrefix *, struct UpdateStatusContext *, void *, unsigned int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180005b34`
- `0x180006da4`

## callees

- `0x180003c2c`
- `0x1800050b8`
- `0x180009164`
- `0x1800115c0`
- `0x1800118fc`
- `0x180011bf0`
- `0x180011e74`
- `0x180012538`
- `0x1800128fc`
- `0x1800132e4`

## string_xrefs

- `0x180011a83`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x180011b01`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x180011b6b`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x180011bb6`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x1800119c5`: `UpdateStatus`
- `0x180011ac2`: `CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, pContext))`
- `0x180011b9f`: `CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, pContext))`
- `0x180011b3d`: `CHR(taskSchedulerWrapper.DeleteUpdateStatusRetrySchedule(pPrefix))`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DdcCommandExecutor::UpdateStatus(
        struct CommandPrefix *a1,
        struct UpdateStatusContext *a2,
        void *a3,
        unsigned int *a4)
{
  int updated; // ebx
  int v8; // edx
  int v9; // ecx
  char v11; // [rsp+20h] [rbp-69h]
  const char *v12; // [rsp+28h] [rbp-61h]
  _QWORD v13[8]; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v14; // [rsp+F0h] [rbp+67h] BYREF

  v13[0] = a3;
  v13[1] = 0;
  v14 = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      if ( a4 )
      {
        if ( DdcPdcActivationWrapper::ActivateClient((DdcPdcActivationWrapper *)v13, L"UpdateStatus") < 0 )
        {
          updated = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v14);
          if ( updated >= 0 )
          {
            updated = DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry((DdcTaskSchedulerWrapper *)&v14, a1, a2);
            if ( updated >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
              goto LABEL_32;
            v12 = "CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, pContext))";
            v11 = 26;
          }
          else
          {
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
              goto LABEL_32;
            v12 = "CHR(taskSchedulerWrapper.Initialize())";
            v11 = 25;
          }
        }
        else
        {
          updated = UpdateStatusWrapper(
                      a4,
                      *(unsigned int *)a1,
                      *((unsigned int *)a2 + 4),
                      *((unsigned int *)a1 + 2),
                      *((_DWORD *)a2 + 6),
                      *((_DWORD *)a2 + 5),
                      *(_QWORD *)((char *)a1 + 12),
                      a2,
                      (char *)a2 + 8,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0,
                      0);
          if ( (unsigned int)ShouldRetry(updated, *a4) )
          {
            updated = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v14);
            if ( updated >= 0 )
            {
              updated = DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry((DdcTaskSchedulerWrapper *)&v14, a1, a2);
              if ( updated >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                goto LABEL_32;
              v12 = "CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, pContext))";
              v11 = 13;
            }
            else
            {
              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                goto LABEL_32;
              v12 = "CHR(taskSchedulerWrapper.Initialize())";
              v11 = 12;
            }
          }
          else
          {
            if ( !*((_DWORD *)a2 + 6) )
              goto LABEL_32;
            updated = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v14);
            if ( updated >= 0 )
            {
              updated = DdcTaskSchedulerWrapper::DeleteUpdateStatusRetrySchedule((DdcTaskSchedulerWrapper *)&v14, a1);
              if ( updated >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                goto LABEL_32;
              v12 = "CHR(taskSchedulerWrapper.DeleteUpdateStatusRetrySchedule(pPrefix))";
              v11 = 19;
            }
            else
            {
              if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
                goto LABEL_32;
              v12 = "CHR(taskSchedulerWrapper.Initialize())";
              v11 = 18;
            }
          }
        }
        McTemplateU0dsqs_EventWriteTransfer(
          v9,
          v8,
          updated,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
          v11,
          v12);
        goto LABEL_32;
      }
      updated = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)a1,
          (_DWORD)a2,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
          250,
          "CPR(pdwHttpStatus)");
    }
    else
    {
      updated = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          (_DWORD)a1,
          0,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
          249,
          "CPR(pContext)");
    }
  }
  else
  {
    updated = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        (_DWORD)a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
        248,
        "CPR(pPrefix)");
  }
LABEL_32:
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(&v14);
  DdcPdcActivationWrapper::DeactivateClient((DdcPdcActivationWrapper *)v13);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800118fc  push    rbp
0x1800118fe  push    rbx
0x1800118ff  push    rsi
0x180011900  push    rdi
0x180011901  push    r14
0x180011903  push    r15
0x180011905  lea     rbp, [rsp-2Fh]
0x18001190a  sub     rsp, 0B8h
0x180011911  mov     r14, r9
0x180011914  mov     rdi, rdx
0x180011917  mov     rsi, rcx
0x18001191a  mov     [rbp+57h+var_40], r8
0x18001191e  xor     r15d, r15d
0x180011921  mov     [rbp+57h+var_38], r15
0x180011925  mov     [rbp+57h+arg_0], r15
0x180011929  test    rcx, rcx
0x18001192c  jnz     short loc_18001195D
0x18001192e  mov     r8d, 80070057h
0x180011934  mov     ebx, r8d
0x180011937  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001193e  jz      loc_180011BC3
0x180011944  lea     rax, aCprPprefix; "CPR(pPrefix)"
0x18001194b  mov     [rsp+0E0h+var_B8], rax
0x180011950  mov     dword ptr [rsp+0E0h+var_C0], 2F8h
0x180011958  jmp     loc_180011BB6
0x18001195d  test    rdi, rdi
0x180011960  jnz     short loc_180011991
0x180011962  mov     r8d, 80070057h
0x180011968  mov     ebx, r8d
0x18001196b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011972  jz      loc_180011BC3
0x180011978  lea     rax, aCprPcontext; "CPR(pContext)"
0x18001197f  mov     [rsp+0E0h+var_B8], rax
0x180011984  mov     dword ptr [rsp+0E0h+var_C0], 2F9h
0x18001198c  jmp     loc_180011BB6
0x180011991  test    r14, r14
0x180011994  jnz     short loc_1800119C5
0x180011996  mov     r8d, 80070057h
0x18001199c  mov     ebx, r8d
0x18001199f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800119a6  jz      loc_180011BC3
0x1800119ac  lea     rax, aCprPdwhttpstat; "CPR(pdwHttpStatus)"
0x1800119b3  mov     [rsp+0E0h+var_B8], rax
0x1800119b8  mov     dword ptr [rsp+0E0h+var_C0], 2FAh
0x1800119c0  jmp     loc_180011BB6
0x1800119c5  lea     rdx, aUpdatestatus; "UpdateStatus"
0x1800119cc  lea     rcx, [rbp+57h+var_40]; this
0x1800119d0  call    ?ActivateClient@DdcPdcActivationWrapper@@QEAAJPEBG@Z; DdcPdcActivationWrapper::ActivateClient(ushort const *)
0x1800119d5  test    eax, eax
0x1800119d7  js      loc_180011B53
0x1800119dd  lea     rax, [rdi+8]
0x1800119e1  mov     [rsp+0E0h+var_48], r15
0x1800119e9  mov     [rsp+0E0h+var_50], r15
0x1800119f1  mov     [rsp+0E0h+var_58], r15
0x1800119f9  mov     [rsp+0E0h+var_60], r15
0x180011a01  mov     [rsp+0E0h+var_68], r15
0x180011a06  mov     [rsp+0E0h+var_70], r15
0x180011a0b  mov     [rsp+0E0h+var_78], r15
0x180011a10  mov     [rsp+0E0h+var_80], r15
0x180011a15  mov     [rsp+0E0h+var_88], r15
0x180011a1a  mov     [rsp+0E0h+var_90], r15
0x180011a1f  mov     [rsp+0E0h+var_98], r15
0x180011a24  mov     [rsp+0E0h+var_A0], rax
0x180011a29  mov     [rsp+0E0h+var_A8], rdi
0x180011a2e  mov     rax, [rsi+0Ch]
0x180011a32  mov     [rsp+0E0h+var_B0], rax
0x180011a37  mov     eax, [rdi+14h]
0x180011a3a  mov     dword ptr [rsp+0E0h+var_B8], eax
0x180011a3e  mov     eax, [rdi+18h]
0x180011a41  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180011a45  mov     r9d, [rsi+8]
0x180011a49  mov     r8d, [rdi+10h]
0x180011a4d  mov     edx, [rsi]
0x180011a4f  mov     rcx, r14
0x180011a52  call    ?UpdateStatusWrapper@@YAJPEAKKW4MdmCommandStatus@@W4MdmCommandChannelType@@KKU_FILETIME@@PEAU3@4PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@6666PEAH777PEAPEAG@Z; UpdateStatusWrapper(ulong *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,ulong,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)
0x180011a57  mov     ebx, eax
0x180011a59  mov     edx, [r14]; unsigned int
0x180011a5c  mov     ecx, eax; int
0x180011a5e  call    ?ShouldRetry@@YAHJK@Z; ShouldRetry(long,ulong)
0x180011a63  test    eax, eax
0x180011a65  jz      short loc_180011ADB
0x180011a67  lea     rcx, [rbp+57h+arg_0]; this
0x180011a6b  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x180011a70  mov     ebx, eax
0x180011a72  test    eax, eax
0x180011a74  jns     short loc_180011A9C
0x180011a76  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011a7d  jz      loc_180011BC3
0x180011a83  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x180011a8a  mov     [rsp+0E0h+var_B8], rax
0x180011a8f  mov     dword ptr [rsp+0E0h+var_C0], 30Ch
0x180011a97  jmp     loc_180011BB3
0x180011a9c  mov     r8, rdi; struct UpdateStatusContext *
0x180011a9f  mov     rdx, rsi; struct CommandPrefix *
0x180011aa2  lea     rcx, [rbp+57h+arg_0]; this
0x180011aa6  call    ?ScheduleUpdateStatusRetry@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@PEAUUpdateStatusContext@@@Z; DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(CommandPrefix *,UpdateStatusContext *)
0x180011aab  mov     ebx, eax
0x180011aad  test    eax, eax
0x180011aaf  jns     loc_180011BC3
0x180011ab5  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011abc  jz      loc_180011BC3
0x180011ac2  lea     rax, aChrTaskschedul_7; "CHR(taskSchedulerWrapper.ScheduleUpdate"...
0x180011ac9  mov     [rsp+0E0h+var_B8], rax
0x180011ace  mov     dword ptr [rsp+0E0h+var_C0], 30Dh
0x180011ad6  jmp     loc_180011BB3
0x180011adb  cmp     [rdi+18h], r15d
0x180011adf  jbe     loc_180011BC3
0x180011ae5  lea     rcx, [rbp+57h+arg_0]; this
0x180011ae9  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x180011aee  mov     ebx, eax
0x180011af0  test    eax, eax
0x180011af2  jns     short loc_180011B1A
0x180011af4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011afb  jz      loc_180011BC3
0x180011b01  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x180011b08  mov     [rsp+0E0h+var_B8], rax
0x180011b0d  mov     dword ptr [rsp+0E0h+var_C0], 312h
0x180011b15  jmp     loc_180011BB3
0x180011b1a  mov     rdx, rsi; struct CommandPrefix *
0x180011b1d  lea     rcx, [rbp+57h+arg_0]; this
0x180011b21  call    ?DeleteUpdateStatusRetrySchedule@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@@Z; DdcTaskSchedulerWrapper::DeleteUpdateStatusRetrySchedule(CommandPrefix *)
0x180011b26  mov     ebx, eax
0x180011b28  test    eax, eax
0x180011b2a  jns     loc_180011BC3
0x180011b30  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011b37  jz      loc_180011BC3
0x180011b3d  lea     rax, aChrTaskschedul_2; "CHR(taskSchedulerWrapper.DeleteUpdateSt"...
0x180011b44  mov     [rsp+0E0h+var_B8], rax
0x180011b49  mov     dword ptr [rsp+0E0h+var_C0], 313h
0x180011b51  jmp     short loc_180011BB3
0x180011b53  lea     rcx, [rbp+57h+arg_0]; this
0x180011b57  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x180011b5c  mov     ebx, eax
0x180011b5e  test    eax, eax
0x180011b60  jns     short loc_180011B81
0x180011b62  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011b69  jz      short loc_180011BC3
0x180011b6b  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x180011b72  mov     [rsp+0E0h+var_B8], rax
0x180011b77  mov     dword ptr [rsp+0E0h+var_C0], 319h
0x180011b7f  jmp     short loc_180011BB3
0x180011b81  mov     r8, rdi; struct UpdateStatusContext *
0x180011b84  mov     rdx, rsi; struct CommandPrefix *
0x180011b87  lea     rcx, [rbp+57h+arg_0]; this
0x180011b8b  call    ?ScheduleUpdateStatusRetry@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@PEAUUpdateStatusContext@@@Z; DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(CommandPrefix *,UpdateStatusContext *)
0x180011b90  mov     ebx, eax
0x180011b92  test    eax, eax
0x180011b94  jns     short loc_180011BC3
0x180011b96  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180011b9d  jz      short loc_180011BC3
0x180011b9f  lea     rax, aChrTaskschedul_7; "CHR(taskSchedulerWrapper.ScheduleUpdate"...
0x180011ba6  mov     [rsp+0E0h+var_B8], rax
0x180011bab  mov     dword ptr [rsp+0E0h+var_C0], 31Ah
0x180011bb3  mov     r8d, ebx
0x180011bb6  lea     r9, aOnecoreuapShel_8; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180011bbd  call    McTemplateU0dsqs_EventWriteTransfer
0x180011bc2  nop
0x180011bc3  lea     rcx, [rbp+57h+arg_0]
0x180011bc7  call    ??1?$CComPtrBase@UIWpnPlatform@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(void)
0x180011bcc  nop
0x180011bcd  lea     rcx, [rbp+57h+var_40]; this
0x180011bd1  call    ?DeactivateClient@DdcPdcActivationWrapper@@QEAAXXZ; DdcPdcActivationWrapper::DeactivateClient(void)
0x180011bd6  mov     eax, ebx
0x180011bd8  add     rsp, 0B8h
0x180011bdf  pop     r15
0x180011be1  pop     r14
0x180011be3  pop     rdi
0x180011be4  pop     rsi
0x180011be5  pop     rbx
0x180011be6  pop     rbp
0x180011be7  retn
```
