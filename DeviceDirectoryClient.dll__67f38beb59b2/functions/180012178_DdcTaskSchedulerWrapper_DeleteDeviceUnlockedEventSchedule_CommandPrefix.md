# DdcTaskSchedulerWrapper::DeleteDeviceUnlockedEventSchedule(CommandPrefix *)

- ea: `0x180012178`
- end: `0x180012274`
- name: `?DeleteDeviceUnlockedEventSchedule@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(DdcTaskSchedulerWrapper *__hidden this, struct CommandPrefix *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005b34`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x1800050b8`
- `0x18000d79c`
- `0x180012178`
- `0x180012380`

## string_xrefs

- `0x180012245`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x180012231`: `CHR(DeleteTaskIfExists( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName ))`
- `0x1800121ff`: `CHR(StringCchPrintfW( pwszTaskName, 32, TASK_SCHEDULER_DEVICE_UNLOCKED_FORMAT, pPrefix->dwRequestId))`

## pseudocode

```c
__int64 __fastcall DdcTaskSchedulerWrapper::DeleteDeviceUnlockedEventSchedule(
        DdcTaskSchedulerWrapper *this,
        struct CommandPrefix *a2)
{
  int v4; // edx
  int v5; // ecx
  int v6; // ebx
  const unsigned __int16 *v7; // rdx
  int v8; // ecx
  int v9; // edx
  int v10; // ecx
  unsigned __int16 v12[32]; // [rsp+30h] [rbp-58h] BYREF

  memset_0(v12, 0, sizeof(v12));
  if ( a2 )
  {
    v6 = StringCchPrintfW(v12, 0x20u, L"DeviceUnlocked%lu", *(unsigned int *)a2);
    if ( v6 >= 0 )
    {
      v6 = DdcTaskSchedulerWrapper::DeleteTaskIfExists(this, v7, v12);
      if ( v6 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v10,
          v9,
          v6,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
          39,
          "CHR(DeleteTaskIfExists( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName ))");
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v8,
        (_DWORD)v7,
        v6,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        33,
        "CHR(StringCchPrintfW( pwszTaskName, 32, TASK_SCHEDULER_DEVICE_UNLOCKED_FORMAT, pPrefix->dwRequestId))");
    }
  }
  else
  {
    v6 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v5,
        v4,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        26,
        "CPR(pPrefix)");
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012178  mov     [rsp+arg_10], rbx
0x18001217d  push    rdi
0x18001217e  sub     rsp, 80h
0x180012185  mov     rax, cs:__security_cookie
0x18001218c  xor     rax, rsp
0x18001218f  mov     [rsp+88h+var_18], rax
0x180012194  mov     rbx, rdx
0x180012197  mov     rdi, rcx
0x18001219a  xor     edx, edx; Val
0x18001219c  lea     rcx, [rsp+88h+var_58]; void *
0x1800121a1  lea     r8d, [rdx+40h]; Size
0x1800121a5  call    memset_0
0x1800121aa  test    rbx, rbx
0x1800121ad  jnz     short loc_1800121D7
0x1800121af  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800121b6  mov     ebx, 80070057h
0x1800121bb  jz      loc_180012254
0x1800121c1  lea     rax, aCprPprefix; "CPR(pPrefix)"
0x1800121c8  mov     [rsp+88h+var_60], rax
0x1800121cd  mov     [rsp+88h+var_68], 31Ah
0x1800121d5  jmp     short loc_180012245
0x1800121d7  mov     r9d, [rbx]
0x1800121da  lea     r8, aDeviceunlocked; "DeviceUnlocked%lu"
0x1800121e1  mov     edx, 20h ; ' '; unsigned __int64
0x1800121e6  lea     rcx, [rsp+88h+var_58]; unsigned __int16 *
0x1800121eb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800121f0  mov     ebx, eax
0x1800121f2  test    eax, eax
0x1800121f4  jns     short loc_180012215
0x1800121f6  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800121fd  jz      short loc_180012254
0x1800121ff  lea     rax, aChrStringcchpr_6; "CHR(StringCchPrintfW( pwszTaskName, 32,"...
0x180012206  mov     [rsp+88h+var_60], rax
0x18001220b  mov     [rsp+88h+var_68], 321h
0x180012213  jmp     short loc_180012245
0x180012215  lea     r8, [rsp+88h+var_58]; unsigned __int16 *
0x18001221a  mov     rcx, rdi; this
0x18001221d  call    ?DeleteTaskIfExists@DdcTaskSchedulerWrapper@@AEAAJPEBG0@Z; DdcTaskSchedulerWrapper::DeleteTaskIfExists(ushort const *,ushort const *)
0x180012222  mov     ebx, eax
0x180012224  test    eax, eax
0x180012226  jns     short loc_180012254
0x180012228  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001222f  jz      short loc_180012254
0x180012231  lea     rax, aChrDeletetaski_0; "CHR(DeleteTaskIfExists( TASK_SCHEDULER_"...
0x180012238  mov     [rsp+88h+var_60], rax
0x18001223d  mov     [rsp+88h+var_68], 327h
0x180012245  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001224c  mov     r8d, ebx
0x18001224f  call    McTemplateU0dsqs_EventWriteTransfer
0x180012254  mov     eax, ebx
0x180012256  mov     rcx, [rsp+88h+var_18]
0x18001225b  xor     rcx, rsp; StackCookie
0x18001225e  call    __security_check_cookie
0x180012263  mov     rbx, [rsp+88h+arg_10]
0x18001226b  add     rsp, 80h
0x180012272  pop     rdi
0x180012273  retn
```
