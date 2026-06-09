# OobeEsimTaskManager::Start(IUnknown *,ushort *)

- ea: `0x1800079a0`
- end: `0x180007aa4`
- name: `?Start@OobeEsimTaskManager@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `260`
- prototype: `__int64 __fastcall(OobeEsimTaskManager *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task`

## callees

- `0x180007380`
- `0x180007494`
- `0x1800079a0`
- `0x180007aac`
- `0x180009290`
- `0x18000ad20`
- `0x18001bc44`
- `0x18001bdb8`

## string_xrefs

- `0x1800079b5`: `OobeEsimTaskManager::Start`
- `0x1800079c0`: `OOBE in progress, ignore new instances of the task and call ExecuteEasyConnect`
- `0x180007a29`: `OOBE is NOT in progress, queue new instances of the task and call ExecuteBootstrapProfileDeletion`
- `0x1800079e7`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180007a0b`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180007a50`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`
- `0x180007a74`: `onecoreuap\net\ux\mbmediamanager\lib\oobeesimtaskmanager.cpp`

## pseudocode

```c
__int64 __fastcall OobeEsimTaskManager::Start(OobeEsimTaskManager *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  OobeEsimTaskManager *v5; // rcx
  int v6; // eax
  OobeEsimTaskManager *v7; // rcx
  int v8; // eax
  OobeEsimTaskManager *v9; // rcx
  int v10; // eax
  OobeEsimTaskManager *v11; // rcx
  int v12; // eax
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( OobeEsimTaskManager::IsOobeInProgress(this) )
  {
    MBSettingUXLogging::Info(
      "OobeEsimTaskManager::Start",
      0x1Cu,
      "OOBE in progress, ignore new instances of the task and call ExecuteEasyConnect");
    v6 = OobeEsimTaskManager::SetTaskMultipleInstancesPolicy(v5, TASK_INSTANCES_IGNORE_NEW);
    v7 = retaddr;
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1F,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v6,
        v14);
    v8 = OobeEsimTaskManager::SetTaskCellularStateSnapshotTrigger(v7, 0);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v8,
        v14);
    OobeEsimTaskManager::ExecuteEasyConnect(this, a2);
  }
  else
  {
    MBSettingUXLogging::Info(
      "OobeEsimTaskManager::Start",
      0x25u,
      "OOBE is NOT in progress, queue new instances of the task and call ExecuteBootstrapProfileDeletion");
    v10 = OobeEsimTaskManager::SetTaskMultipleInstancesPolicy(v9, TASK_INSTANCES_QUEUE);
    v11 = retaddr;
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v10,
        v14);
    v12 = OobeEsimTaskManager::SetTaskCellularStateSnapshotTrigger(v11, 1);
    if ( v12 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\lib\\oobeesimtaskmanager.cpp",
        (const char *)(unsigned int)v12,
        v14);
    OobeEsimTaskManager::ExecuteBootstrapProfileDeletion(this, a2);
  }
  return 0;
}

```

## disassembly

```asm
0x1800079a0  mov     [rsp+arg_0], rbx
0x1800079a5  push    rdi; int
0x1800079a6  sub     rsp, 20h
0x1800079aa  mov     rbx, rdx
0x1800079ad  mov     rdi, rcx
0x1800079b0  call    ?IsOobeInProgress@OobeEsimTaskManager@@AEAA_NXZ; OobeEsimTaskManager::IsOobeInProgress(void)
0x1800079b5  lea     rcx, aOobeesimtaskma_4; "OobeEsimTaskManager::Start"
0x1800079bc  test    al, al
0x1800079be  jz      short loc_180007A29
0x1800079c0  lea     r8, aOobeInProgress; "OOBE in progress, ignore new instances "...
0x1800079c7  mov     edx, 1Ch; unsigned int
0x1800079cc  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x1800079d1  mov     edx, 2; enum _TASK_INSTANCES_POLICY
0x1800079d6  call    ?SetTaskMultipleInstancesPolicy@OobeEsimTaskManager@@AEAAJW4_TASK_INSTANCES_POLICY@@@Z; OobeEsimTaskManager::SetTaskMultipleInstancesPolicy(_TASK_INSTANCES_POLICY)
0x1800079db  mov     rcx, [rsp+28h]; this
0x1800079e0  test    eax, eax
0x1800079e2  jns     short loc_1800079F8
0x1800079e4  mov     r9d, eax; char *
0x1800079e7  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x1800079ee  mov     edx, 1Fh; void *
0x1800079f3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800079f8  xor     edx, edx; bool
0x1800079fa  call    ?SetTaskCellularStateSnapshotTrigger@OobeEsimTaskManager@@AEAAJ_N@Z; OobeEsimTaskManager::SetTaskCellularStateSnapshotTrigger(bool)
0x1800079ff  mov     rcx, [rsp+28h]; this
0x180007a04  test    eax, eax
0x180007a06  jns     short loc_180007A1C
0x180007a08  mov     r9d, eax; char *
0x180007a0b  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180007a12  mov     edx, 20h ; ' '; void *
0x180007a17  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007a1c  mov     rdx, rbx; struct IUnknown *
0x180007a1f  mov     rcx, rdi; this
0x180007a22  call    ?ExecuteEasyConnect@OobeEsimTaskManager@@AEAAJPEAUIUnknown@@@Z; OobeEsimTaskManager::ExecuteEasyConnect(IUnknown *)
0x180007a27  jmp     short loc_180007A90
0x180007a29  lea     r8, aOobeIsNotInPro; "OOBE is NOT in progress, queue new inst"...
0x180007a30  mov     edx, 25h ; '%'; unsigned int
0x180007a35  call    ?Info@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Info(char const *,ulong,char const *,...)
0x180007a3a  mov     edx, 1; enum _TASK_INSTANCES_POLICY
0x180007a3f  call    ?SetTaskMultipleInstancesPolicy@OobeEsimTaskManager@@AEAAJW4_TASK_INSTANCES_POLICY@@@Z; OobeEsimTaskManager::SetTaskMultipleInstancesPolicy(_TASK_INSTANCES_POLICY)
0x180007a44  mov     rcx, [rsp+28h]; this
0x180007a49  test    eax, eax
0x180007a4b  jns     short loc_180007A61
0x180007a4d  mov     r9d, eax; char *
0x180007a50  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180007a57  mov     edx, 28h ; '('; void *
0x180007a5c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007a61  mov     dl, 1; bool
0x180007a63  call    ?SetTaskCellularStateSnapshotTrigger@OobeEsimTaskManager@@AEAAJ_N@Z; OobeEsimTaskManager::SetTaskCellularStateSnapshotTrigger(bool)
0x180007a68  mov     rcx, [rsp+28h]; this
0x180007a6d  test    eax, eax
0x180007a6f  jns     short loc_180007A85
0x180007a71  mov     r9d, eax; char *
0x180007a74  lea     r8, aOnecoreuapNetU_11; "onecoreuap\\net\\ux\\mbmediamanager\\li"...
0x180007a7b  mov     edx, 29h ; ')'; void *
0x180007a80  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007a85  mov     rdx, rbx; struct IUnknown *
0x180007a88  mov     rcx, rdi; this
0x180007a8b  call    ?ExecuteBootstrapProfileDeletion@OobeEsimTaskManager@@AEAAJPEAUIUnknown@@@Z; OobeEsimTaskManager::ExecuteBootstrapProfileDeletion(IUnknown *)
0x180007a90  xor     eax, eax
0x180007a92  jmp     short loc_180007A98
0x180007a94  mov     eax, [rsp+28h+arg_18]
0x180007a98  mov     rbx, [rsp+28h+arg_0]
0x180007a9d  add     rsp, 20h
0x180007aa1  pop     rdi
0x180007aa2  retn
```
