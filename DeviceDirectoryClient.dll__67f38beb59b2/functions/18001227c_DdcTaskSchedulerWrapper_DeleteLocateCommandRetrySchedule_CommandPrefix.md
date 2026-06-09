# DdcTaskSchedulerWrapper::DeleteLocateCommandRetrySchedule(CommandPrefix *)

- ea: `0x18001227c`
- end: `0x180012378`
- name: `?DeleteLocateCommandRetrySchedule@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@@Z`
- size: `252`
- prototype: `__int64 __fastcall(DdcTaskSchedulerWrapper *__hidden this, struct CommandPrefix *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800063f4`
- `0x1800101f0`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x1800050b8`
- `0x18000d79c`
- `0x18001227c`
- `0x180012380`

## string_xrefs

- `0x1800122de`: `LocateCommandRetry%lu`
- `0x180012349`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddctaskschedulerwrapper.cpp`
- `0x180012303`: `CHR(StringCchPrintfW( pwszTaskName, 32, TASK_SCHEDULER_LOCATE_COMMAND_RETRY_FORMAT, pPrefix->dwRequestId))`
- `0x180012335`: `CHR(DeleteTaskIfExists( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName ))`

## pseudocode

```c
__int64 __fastcall DdcTaskSchedulerWrapper::DeleteLocateCommandRetrySchedule(
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
    v6 = StringCchPrintfW(v12, 0x20u, L"LocateCommandRetry%lu", *(unsigned int *)a2);
    if ( v6 >= 0 )
    {
      v6 = DdcTaskSchedulerWrapper::DeleteTaskIfExists(this, v7, v12);
      if ( v6 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v10,
          v9,
          v6,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
          116,
          "CHR(DeleteTaskIfExists( TASK_SCHEDULER_DIRECTORY_NAME, pwszTaskName ))");
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v8,
        (_DWORD)v7,
        v6,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddctaskschedulerwrapper.cpp",
        110,
        "CHR(StringCchPrintfW( pwszTaskName, 32, TASK_SCHEDULER_LOCATE_COMMAND_RETRY_FORMAT, pPrefix->dwRequestId))");
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
        103,
        "CPR(pPrefix)");
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001227c  mov     [rsp+arg_10], rbx
0x180012281  push    rdi
0x180012282  sub     rsp, 80h
0x180012289  mov     rax, cs:__security_cookie
0x180012290  xor     rax, rsp
0x180012293  mov     [rsp+88h+var_18], rax
0x180012298  mov     rbx, rdx
0x18001229b  mov     rdi, rcx
0x18001229e  xor     edx, edx; Val
0x1800122a0  lea     rcx, [rsp+88h+var_58]; void *
0x1800122a5  lea     r8d, [rdx+40h]; Size
0x1800122a9  call    memset_0
0x1800122ae  test    rbx, rbx
0x1800122b1  jnz     short loc_1800122DB
0x1800122b3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x1800122ba  mov     ebx, 80070057h
0x1800122bf  jz      loc_180012358
0x1800122c5  lea     rax, aCprPprefix; "CPR(pPrefix)"
0x1800122cc  mov     [rsp+88h+var_60], rax
0x1800122d1  mov     [rsp+88h+var_68], 267h
0x1800122d9  jmp     short loc_180012349
0x1800122db  mov     r9d, [rbx]
0x1800122de  lea     r8, aLocatecommandr_0; "LocateCommandRetry%lu"
0x1800122e5  mov     edx, 20h ; ' '; unsigned __int64
0x1800122ea  lea     rcx, [rsp+88h+var_58]; unsigned __int16 *
0x1800122ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800122f4  mov     ebx, eax
0x1800122f6  test    eax, eax
0x1800122f8  jns     short loc_180012319
0x1800122fa  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012301  jz      short loc_180012358
0x180012303  lea     rax, aChrStringcchpr_2; "CHR(StringCchPrintfW( pwszTaskName, 32,"...
0x18001230a  mov     [rsp+88h+var_60], rax
0x18001230f  mov     [rsp+88h+var_68], 26Eh
0x180012317  jmp     short loc_180012349
0x180012319  lea     r8, [rsp+88h+var_58]; unsigned __int16 *
0x18001231e  mov     rcx, rdi; this
0x180012321  call    ?DeleteTaskIfExists@DdcTaskSchedulerWrapper@@AEAAJPEBG0@Z; DdcTaskSchedulerWrapper::DeleteTaskIfExists(ushort const *,ushort const *)
0x180012326  mov     ebx, eax
0x180012328  test    eax, eax
0x18001232a  jns     short loc_180012358
0x18001232c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180012333  jz      short loc_180012358
0x180012335  lea     rax, aChrDeletetaski_0; "CHR(DeleteTaskIfExists( TASK_SCHEDULER_"...
0x18001233c  mov     [rsp+88h+var_60], rax
0x180012341  mov     [rsp+88h+var_68], 274h
0x180012349  lea     r9, aOnecoreuapShel_12; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180012350  mov     r8d, ebx
0x180012353  call    McTemplateU0dsqs_EventWriteTransfer
0x180012358  mov     eax, ebx
0x18001235a  mov     rcx, [rsp+88h+var_18]
0x18001235f  xor     rcx, rsp; StackCookie
0x180012362  call    __security_check_cookie
0x180012367  mov     rbx, [rsp+88h+arg_10]
0x18001236f  add     rsp, 80h
0x180012376  pop     rdi
0x180012377  retn
```
