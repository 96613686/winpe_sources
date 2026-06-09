# DdcStateController::HandleUpgrade(void)

- ea: `0x18000f23c`
- end: `0x18000f355`
- name: `?HandleUpgrade@DdcStateController@@SAJXZ`
- size: `281`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004640`

## callees

- `0x1800024c0`
- `0x180005060`
- `0x1800050b8`
- `0x180005190`
- `0x18000f23c`
- `0x180011e74`
- `0x1800126f8`
- `0x1800128fc`
- `0x180012a60`

## string_xrefs

- `0x18000f29c`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x18000f30e`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcstatecontroller.cpp`
- `0x18000f2cb`: `CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_REGISTER_PHONE_UPGRADE_TASK, 1))`
- `0x18000f2fa`: `CHR(taskSchedulerWrapper.RunTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_REGISTER_PHONE_UPGRADE_TASK))`

## pseudocode

```c
__int64 __fastcall DdcStateController::HandleUpgrade(__int64 a1, __int64 a2, __int64 a3)
{
  const unsigned __int16 *v3; // rdx
  __int64 v4; // rcx
  int v5; // ebx
  const unsigned __int16 *v6; // r8
  const unsigned __int16 *v7; // rdx
  const unsigned __int16 *v8; // r8
  int v9; // edx
  __int64 v11; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v12[16]; // [rsp+38h] [rbp-20h] BYREF

  v11 = 0;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, DEVICE_DIRECTORY_CLIENT_HANDLE_UPGRADE, a3, 1, v12);
  v5 = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v11);
  if ( v5 >= 0 )
  {
    v5 = DdcTaskSchedulerWrapper::EnableTaskIfExists((DdcTaskSchedulerWrapper *)&v11, v3, v6);
    if ( v5 >= 0 )
    {
      v5 = DdcTaskSchedulerWrapper::RunTaskIfExists((DdcTaskSchedulerWrapper *)&v11, v7, v8);
      if ( v5 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v4,
          v9,
          v5,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcstatecontroller.cpp",
          27,
          "CHR(taskSchedulerWrapper.RunTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_REGISTER_PHONE_UPGRADE_TASK))",
          v11);
    }
    else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    {
      McTemplateU0dsqs_EventWriteTransfer(
        v4,
        (_DWORD)v7,
        v5,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcstatecontroller.cpp",
        26,
        "CHR(taskSchedulerWrapper.EnableTaskIfExists(TASK_SCHEDULER_DIRECTORY_NAME, TASK_SCHEDULER_REGISTER_PHONE_UPGRADE_TASK, 1))",
        v11);
    }
  }
  else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    McTemplateU0dsqs_EventWriteTransfer(
      v4,
      (_DWORD)v3,
      v5,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcstatecontroller.cpp",
      25,
      "CHR(taskSchedulerWrapper.Initialize())",
      v11);
  }
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(v4, DEVICE_DIRECTORY_CLIENT_HANDLE_UPGRADE_RESULT, (unsigned int)v5);
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(&v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f23c  push    rbx
0x18000f23e  sub     rsp, 50h
0x18000f242  mov     rax, cs:__security_cookie
0x18000f249  xor     rax, rsp
0x18000f24c  mov     [rsp+58h+var_10], rax
0x18000f251  mov     [rsp+58h+var_28], 0
0x18000f25a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x18000f261  jz      short loc_18000F27F
0x18000f263  lea     rax, [rsp+58h+var_20]
0x18000f268  mov     [rsp+58h+var_38], rax
0x18000f26d  mov     r9d, 1
0x18000f273  lea     rdx, DEVICE_DIRECTORY_CLIENT_HANDLE_UPGRADE
0x18000f27a  call    McGenEventWrite_EventWriteTransfer
0x18000f27f  lea     rcx, [rsp+58h+var_28]; this
0x18000f284  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x18000f289  mov     ebx, eax
0x18000f28b  test    eax, eax
0x18000f28d  jns     short loc_18000F2B2
0x18000f28f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000f296  jz      loc_18000F31D
0x18000f29c  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x18000f2a3  mov     [rsp+58h+var_30], rax
0x18000f2a8  mov     dword ptr [rsp+58h+var_38], 19h
0x18000f2b0  jmp     short loc_18000F30E
0x18000f2b2  lea     rcx, [rsp+58h+var_28]; this
0x18000f2b7  call    ?EnableTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0H@Z; DdcTaskSchedulerWrapper::EnableTaskIfExists(ushort const *,ushort const *,int)
0x18000f2bc  mov     ebx, eax
0x18000f2be  test    eax, eax
0x18000f2c0  jns     short loc_18000F2E1
0x18000f2c2  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000f2c9  jz      short loc_18000F31D
0x18000f2cb  lea     rax, aChrTaskschedul_6; "CHR(taskSchedulerWrapper.EnableTaskIfEx"...
0x18000f2d2  mov     [rsp+58h+var_30], rax
0x18000f2d7  mov     dword ptr [rsp+58h+var_38], 1Ah
0x18000f2df  jmp     short loc_18000F30E
0x18000f2e1  lea     rcx, [rsp+58h+var_28]; this
0x18000f2e6  call    ?RunTaskIfExists@DdcTaskSchedulerWrapper@@QEAAJPEBG0@Z; DdcTaskSchedulerWrapper::RunTaskIfExists(ushort const *,ushort const *)
0x18000f2eb  mov     ebx, eax
0x18000f2ed  test    eax, eax
0x18000f2ef  jns     short loc_18000F31D
0x18000f2f1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000f2f8  jz      short loc_18000F31D
0x18000f2fa  lea     rax, aChrTaskschedul_1; "CHR(taskSchedulerWrapper.RunTaskIfExist"...
0x18000f301  mov     [rsp+58h+var_30], rax
0x18000f306  mov     dword ptr [rsp+58h+var_38], 1Bh
0x18000f30e  lea     r9, aOnecoreuapShel; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000f315  mov     r8d, ebx
0x18000f318  call    McTemplateU0dsqs_EventWriteTransfer
0x18000f31d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x18000f324  jz      short loc_18000F336
0x18000f326  mov     r8d, ebx
0x18000f329  lea     rdx, DEVICE_DIRECTORY_CLIENT_HANDLE_UPGRADE_RESULT
0x18000f330  call    McTemplateU0q_EventWriteTransfer
0x18000f335  nop
0x18000f336  lea     rcx, [rsp+58h+var_28]
0x18000f33b  call    ??1?$CComPtrBase@UIWpnPlatform@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(void)
0x18000f340  mov     eax, ebx
0x18000f342  mov     rcx, [rsp+58h+var_10]
0x18000f347  xor     rcx, rsp; StackCookie
0x18000f34a  call    __security_check_cookie
0x18000f34f  add     rsp, 50h
0x18000f353  pop     rbx
0x18000f354  retn
```
