# DdcTaskSchedulerWrapper::DeleteUpdateStatusRetrySchedule(CommandPrefix *)

- ea: `0x180012538`
- end: `0x180012634`
- name: `?DeleteUpdateStatusRetrySchedule@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(DdcTaskSchedulerWrapper *__hidden this, struct CommandPrefix *)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180005b34`
- `0x180006da4`
- `0x1800118fc`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x1800050b8`
- `0x18000d79c`
- `0x180012380`
- `0x180012538`

## string_xrefs

- `0x18001259a`: `UpdateStatusRetry%lu`
- `0x180012605`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x1800125f1`: `CHR(DeleteTaskIfExists( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName ))`
- `0x1800125bf`: `CHR(StringCchPrintfW( pwszTaskName, 32, TASK_SCHEDULER_UPDATE_STATUS_RETRY_FORMAT, pPrefix->dwRequestId))`

## pseudocode

```c
__int64 __fastcall DdcTaskSchedulerWrapper::DeleteUpdateStatusRetrySchedule(
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
    v6 = StringCchPrintfW(v12, 0x20u, L"UpdateStatusRetry%lu", *(unsigned int *)a2);
    if ( v6 >= 0 )
    {
      v6 = DdcTaskSchedulerWrapper::DeleteTaskIfExists(this, v7, v12);
      if ( v6 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v10,
          v9,
          v6,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
          211,
          "CHR(DeleteTaskIfExists( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName ))");
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v8,
        (_DWORD)v7,
        v6,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        205,
        "CHR(StringCchPrintfW( pwszTaskName, 32, TASK_SCHEDULER_UPDATE_STATUS_RETRY_FORMAT, pPrefix->dwRequestId))");
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
        198,
        "CPR(pPrefix)");
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180012538  mov     [rsp+arg_10], rbx
0x18001253d  push    rdi
0x18001253e  sub     rsp, 80h
0x180012545  mov     rax, cs:__security_cookie
0x18001254c  xor     rax, rsp
0x18001254f  mov     [rsp+88h+var_18], rax
0x180012554  mov     rbx, rdx
0x180012557  mov     rdi, rcx
0x18001255a  xor     edx, edx; Val
0x18001255c  lea     rcx, [rsp+88h+var_58]; void *
0x180012561  lea     r8d, [rdx+40h]; Size
0x180012565  call    memset_0
0x18001256a  test    rbx, rbx
0x18001256d  jnz     short loc_180012597
0x18001256f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012576  mov     ebx, 80070057h
0x18001257b  jz      loc_180012614
0x180012581  lea     rax, aCprPprefix; "CPR(pPrefix)"
0x180012588  mov     [rsp+88h+var_60], rax
0x18001258d  mov     [rsp+88h+var_68], 2C6h
0x180012595  jmp     short loc_180012605
0x180012597  mov     r9d, [rbx]
0x18001259a  lea     r8, aUpdatestatusre; "UpdateStatusRetry%lu"
0x1800125a1  mov     edx, 20h ; ' '; unsigned __int64
0x1800125a6  lea     rcx, [rsp+88h+var_58]; unsigned __int16 *
0x1800125ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800125b0  mov     ebx, eax
0x1800125b2  test    eax, eax
0x1800125b4  jns     short loc_1800125D5
0x1800125b6  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800125bd  jz      short loc_180012614
0x1800125bf  lea     rax, aChrStringcchpr_0; "CHR(StringCchPrintfW( pwszTaskName, 32,"...
0x1800125c6  mov     [rsp+88h+var_60], rax
0x1800125cb  mov     [rsp+88h+var_68], 2CDh
0x1800125d3  jmp     short loc_180012605
0x1800125d5  lea     r8, [rsp+88h+var_58]; unsigned __int16 *
0x1800125da  mov     rcx, rdi; this
0x1800125dd  call    ?DeleteTaskIfExists@DdcTaskSchedulerWrapper@@AEAAJPEBG0@Z; DdcTaskSchedulerWrapper::DeleteTaskIfExists(ushort const *,ushort const *)
0x1800125e2  mov     ebx, eax
0x1800125e4  test    eax, eax
0x1800125e6  jns     short loc_180012614
0x1800125e8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800125ef  jz      short loc_180012614
0x1800125f1  lea     rax, aChrDeletetaski_0; "CHR(DeleteTaskIfExists( TASK_SCHEDULER_"...
0x1800125f8  mov     [rsp+88h+var_60], rax
0x1800125fd  mov     [rsp+88h+var_68], 2D3h
0x180012605  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001260c  mov     r8d, ebx
0x18001260f  call    McTemplateU0dsqs_EventWriteTransfer
0x180012614  mov     eax, ebx
0x180012616  mov     rcx, [rsp+88h+var_18]
0x18001261b  xor     rcx, rsp; StackCookie
0x18001261e  call    __security_check_cookie
0x180012623  mov     rbx, [rsp+88h+arg_10]
0x18001262b  add     rsp, 80h
0x180012632  pop     rdi
0x180012633  retn
```
