# CDeviceDirectoryClientHandler::Worker(void)

- ea: `0x180004640`
- end: `0x180004c7e`
- name: `?Worker@CDeviceDirectoryClientHandler@@EEAAJXZ`
- size: `1598`
- prototype: `__int64 __fastcall(CDeviceDirectoryClientHandler *__hidden this)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800024c0`
- `0x1800036e8`
- `0x180003974`
- `0x1800040ec`
- `0x180004214`
- `0x1800042c0`
- `0x180004640`
- `0x180004db8`
- `0x180004e10`
- `0x180004ff8`
- `0x180005030`
- `0x180005060`
- `0x1800050b8`
- `0x180005190`
- `0x180005b34`
- `0x180005f5c`
- `0x1800063f4`
- `0x180006c00`
- `0x180006da4`
- `0x1800071d0`
- `0x180007838`
- `0x18000f23c`
- `0x18000f35c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800047d9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800047d9`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180004c10`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180004c10`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180004728`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180004728`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800047df`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800047df`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800047e9`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800047e9`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x180004c20`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x180004c20`
- `UMPDC!Pdcv2ActivationClientRegister` at `0x18000471f`
- `UMPDC!Pdcv2ActivationClientRegister` at `0x18000471f`

## string_xrefs

- `0x1800049a4`: `-WnsCommand`
- `0x1800049f4`: `-SmsCommand`
- `0x180004a44`: `-HandleCommand`
- `0x180004a99`: `-LocateCommandRetry`
- `0x180004b3e`: `-UpdateStatusRetry`
- `0x180004af3`: `-UserSessionCommand`
- `0x180004755`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\dll\devicedirectoryclient.cpp`
- `0x180004798`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\dll\devicedirectoryclient.cpp`
- `0x180004741`: `CHR(Windows::Foundation::Initialize(RO_INIT_MULTITHREADED))`
- `0x180004784`: `CPR(pwszConfiguration)`
- `0x180004833`: `CHR(ProcessRegisterDevice(wstrConfiguration, pdcHandle))`
- `0x180004893`: `CHR(ProcessRegisterUserDevice(wstrConfiguration, pdcHandle))`
- `0x1800048e5`: `CHR(ProcessRegisterPhone(wstrConfiguration, pdcHandle))`
- `0x1800049d5`: `CHR(DdcCommandController::HandleWnsCommand())`
- `0x180004a25`: `CHR(DdcCommandController::HandleSmsCommands())`
- `0x180004a7a`: `CHR(DdcCommandController::HandleCommand(pdcHandle))`
- `0x180004ad4`: `CHR(DdcCommandController::HandleLocateCommandRetry(wstrConfiguration, pdcHandle))`
- `0x180004b1f`: `CHR(DdcCommandController::UserSessionCommand())`
- `0x180004b79`: `CHR(DdcCommandController::HandleUpdateStatusRetry(wstrConfiguration, pdcHandle))`
- `0x180004bc6`: `CHR(DdcCommandController::DeviceUnlocked(wstrConfiguration, pdcHandle))`

## pseudocode

```c
__int64 __fastcall CDeviceDirectoryClientHandler::Worker(CDeviceDirectoryClientHandler *this)
{
  const wchar_t *v2; // rsi
  __int64 v3; // r8
  const wchar_t *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // eax
  int v8; // edx
  int v9; // ecx
  int CommandRetry; // ebx
  int v11; // r8d
  BOOL v12; // eax
  int v13; // ecx
  __int64 v14; // rcx
  void *v15; // rcx
  __int64 v17; // [rsp+0h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+20h] [rbp-98h]
  const char *v19; // [rsp+28h] [rbp-90h]
  void *v20; // [rsp+30h] [rbp-88h] BYREF
  int v21; // [rsp+38h] [rbp-80h]
  _QWORD v22[3]; // [rsp+40h] [rbp-78h] BYREF
  _BYTE v23[32]; // [rsp+58h] [rbp-60h] BYREF
  _BYTE v24[16]; // [rsp+78h] [rbp-40h] BYREF
  const wchar_t *v25; // [rsp+88h] [rbp-30h]
  int v26; // [rsp+90h] [rbp-28h]
  int v27; // [rsp+94h] [rbp-24h]

  v20 = 0;
  v2 = (const wchar_t *)*((_QWORD *)this + 1);
  std::wstring::wstring((__int64)v23);
  v22[0] = 1;
  v22[1] = &PdcTimerActivatorCallback;
  v22[2] = this;
  McGenEventRegister_EventRegister();
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
  {
    v4 = L"null";
    if ( v2 )
      v4 = v2;
    if ( v4 )
    {
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v6 = (unsigned int)(2 * v5 + 2);
    }
    else
    {
      v4 = L"NULL";
      v6 = 10;
    }
    v25 = v4;
    v26 = v6;
    v27 = 0;
    McGenEventWrite_EventWriteTransfer(v6, DEVICE_DIRECTORY_CLIENT_CALLED, v3, 2, v24);
  }
  Pdcv2ActivationClientRegister(89, v22, &v20);
  v7 = RoInitialize(1);
  CommandRetry = v7;
  if ( v7 >= 0 )
  {
    if ( v2 )
    {
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        ((void (__fastcall *)(_BYTE *, const wchar_t *))std::wstring::assign)(v23, v2);
        if ( ConfigurationArgumentPresent((__int64)v23, (__int64)L"-DebugBreak", 0, 0) )
        {
          while ( !IsDebuggerPresent() )
            Sleep(0x5DCu);
          DebugBreak();
        }
        v12 = ConfigurationArgumentPresent((__int64)v23, (__int64)L"-RegisterDevice", 1, 0);
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          v21 = -2147024882;
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v13,
              (unsigned int)&v17,
              -2147024882,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
              248,
              "CHR(((HRESULT)0x8007000EL))");
          CommandRetry = v21;
          __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180004C0A);
          goto LABEL_74;
        }
      }
      if ( v12 )
      {
        CommandRetry = CDeviceDirectoryClientHandler::ProcessRegisterDevice((__int64)this, (__int64)v23, (__int64)v20);
        if ( CommandRetry >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_74;
        v19 = "CHR(ProcessRegisterDevice(wstrConfiguration, pdcHandle))";
        LODWORD(v18) = 259;
      }
      else if ( ConfigurationArgumentPresent((__int64)v23, (__int64)L"-RegisterUserDevice", 1, 0) )
      {
        CommandRetry = CDeviceDirectoryClientHandler::ProcessRegisterUserDevice(
                         (__int64)this,
                         (__int64)v23,
                         (__int64)v20);
        if ( CommandRetry >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_74;
        v19 = "CHR(ProcessRegisterUserDevice(wstrConfiguration, pdcHandle))";
        LODWORD(v18) = 263;
      }
      else if ( ConfigurationArgumentPresent((__int64)v23, (__int64)L"-RegisterPhone", 1, 0) )
      {
        CommandRetry = ((__int64 (__fastcall *)(__int64, _BYTE *))CDeviceDirectoryClientHandler::ProcessRegisterPhone)(
                         v14,
                         v23);
        if ( CommandRetry >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_74;
        v19 = "CHR(ProcessRegisterPhone(wstrConfiguration, pdcHandle))";
        LODWORD(v18) = 267;
      }
      else if ( ConfigurationArgumentPresent((__int64)v23, (__int64)L"-IntegrityCheck", 1, 0) )
      {
        CommandRetry = ((__int64 (*)(void))DdcStateController::IntegrityCheck)();
        if ( CommandRetry >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_74;
        v19 = "CHR(DdcStateController::IntegrityCheck())";
        LODWORD(v18) = 271;
      }
      else if ( ConfigurationArgumentPresent((__int64)v23, (__int64)L"-HandleUpgrade", 1, 0) )
      {
        CommandRetry = ((__int64 (*)(void))DdcStateController::HandleUpgrade)();
        if ( CommandRetry >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_74;
        v19 = "CHR(DdcStateController::HandleUpgrade())";
        LODWORD(v18) = 275;
      }
      else if ( ConfigurationArgumentPresent((__int64)v23, (__int64)L"-WnsCommand", 1, 0) )
      {
        CommandRetry = ((__int64 (*)(void))DdcCommandController::HandleWnsCommand)();
        if ( CommandRetry >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_74;
        v19 = "CHR(DdcCommandController::HandleWnsCommand())";
        LODWORD(v18) = 279;
      }
      else if ( ConfigurationArgumentPresent((__int64)v23, (__int64)L"-SmsCommand", 1, 0) )
      {
        CommandRetry = ((__int64 (*)(void))DdcCommandController::HandleSmsCommands)();
        if ( CommandRetry >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_74;
        v19 = "CHR(DdcCommandController::HandleSmsCommands())";
        LODWORD(v18) = 283;
      }
      else if ( ConfigurationArgumentPresent((__int64)v23, (__int64)L"-HandleCommand", 1, 0) )
      {
        CommandRetry = DdcCommandController::HandleCommand(v20);
        if ( CommandRetry >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_74;
        v19 = "CHR(DdcCommandController::HandleCommand(pdcHandle))";
        LODWORD(v18) = 287;
      }
      else if ( ConfigurationArgumentPresent((__int64)v23, (__int64)L"-LocateCommandRetry", 1, 0) )
      {
        CommandRetry = DdcCommandController::HandleLocateCommandRetry((__int64)v23, v20);
        if ( CommandRetry >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_74;
        v19 = "CHR(DdcCommandController::HandleLocateCommandRetry(wstrConfiguration, pdcHandle))";
        LODWORD(v18) = 291;
      }
      else if ( ConfigurationArgumentPresent((__int64)v23, (__int64)L"-UserSessionCommand", 1, 0) )
      {
        CommandRetry = DdcCommandController::UserSessionCommand();
        if ( CommandRetry >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_74;
        v19 = "CHR(DdcCommandController::UserSessionCommand())";
        LODWORD(v18) = 295;
      }
      else if ( ConfigurationArgumentPresent((__int64)v23, (__int64)L"-UpdateStatusRetry", 1, 0) )
      {
        CommandRetry = DdcCommandController::HandleUpdateStatusRetry((__int64)v23, v20);
        if ( CommandRetry >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_74;
        v19 = "CHR(DdcCommandController::HandleUpdateStatusRetry(wstrConfiguration, pdcHandle))";
        LODWORD(v18) = 299;
      }
      else
      {
        if ( !ConfigurationArgumentPresent((__int64)v23, (__int64)L"-DeviceUnlocked", 1, 0) )
        {
          v11 = -2147024809;
          CommandRetry = -2147024809;
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
            goto LABEL_74;
          v19 = "CHR(((HRESULT)0x80070057L))";
          LODWORD(v18) = 308;
          goto LABEL_16;
        }
        CommandRetry = DdcCommandController::DeviceUnlocked((__int64)v23, v20);
        if ( CommandRetry >= 0 || (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
          goto LABEL_74;
        v19 = "CHR(DdcCommandController::DeviceUnlocked(wstrConfiguration, pdcHandle))";
        LODWORD(v18) = 303;
      }
      v11 = CommandRetry;
    }
    else
    {
      v11 = -2147024809;
      CommandRetry = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      {
LABEL_74:
        RoUninitialize();
        goto LABEL_75;
      }
      v19 = "CPR(pwszConfiguration)";
      LODWORD(v18) = 240;
    }
LABEL_16:
    McTemplateU0dsqs_EventWriteTransfer(
      v9,
      v8,
      v11,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
      v18,
      v19);
    goto LABEL_74;
  }
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v9,
      v8,
      v7,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\dll\\devicedirectoryclient.cpp",
      237,
      "CHR(Windows::Foundation::Initialize(RO_INIT_MULTITHREADED))");
LABEL_75:
  v15 = v20;
  if ( v20 )
  {
    Pdcv2ActivationClientUnregister();
    v20 = 0;
  }
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(v15, DEVICE_DIRECTORY_CLIENT_CALLED_RESULT, (unsigned int)CommandRetry);
  McGenEventUnregister_EventUnregister();
  std::wstring::_Tidy_deallocate((__int64)v23);
  return (unsigned int)CommandRetry;
}

```

## disassembly

```asm
0x180004640  mov     [rsp+arg_8], rbx
0x180004645  mov     [rsp+arg_10], rsi
0x18000464a  push    rdi
0x18000464b  push    r14
0x18000464d  push    r15
0x18000464f  sub     rsp, 0A0h
0x180004656  mov     rax, cs:__security_cookie
0x18000465d  xor     rax, rsp
0x180004660  mov     [rsp+0B8h+var_20], rax
0x180004668  mov     r14, rcx
0x18000466b  xor     edi, edi
0x18000466d  mov     [rsp+0B8h+var_88], rdi
0x180004672  mov     rsi, [rcx+8]
0x180004676  lea     rcx, [rsp+0B8h+var_60]
0x18000467b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180004680  nop
0x180004681  lea     r15d, [rdi+1]
0x180004685  mov     [rsp+0B8h+var_78], r15
0x18000468a  lea     rax, ?PdcTimerActivatorCallback@@YAXPEAXW4_PDC_ACTIVATOR_ERROR_DETAIL@@00@Z; PdcTimerActivatorCallback(void *,_PDC_ACTIVATOR_ERROR_DETAIL,void *,void *)
0x180004691  mov     [rsp+0B8h+var_70], rax
0x180004696  mov     [rsp+0B8h+var_68], r14
0x18000469b  call    McGenEventRegister_EventRegister
0x1800046a0  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x1800046a7  jz      short loc_180004710
0x1800046a9  lea     rax, aNull; "null"
0x1800046b0  test    rsi, rsi
0x1800046b3  cmovnz  rax, rsi
0x1800046b7  test    rax, rax
0x1800046ba  jz      short loc_1800046D2
0x1800046bc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800046c0  inc     rcx
0x1800046c3  cmp     [rax+rcx*2], di
0x1800046c7  jnz     short loc_1800046C0
0x1800046c9  lea     ecx, ds:2[rcx*2]
0x1800046d0  jmp     short loc_1800046DE
0x1800046d2  lea     rax, aNull_1; "NULL"
0x1800046d9  mov     ecx, 0Ah
0x1800046de  mov     [rsp+0B8h+var_30], rax
0x1800046e6  mov     [rsp+0B8h+var_28], ecx
0x1800046ed  mov     [rsp+0B8h+var_24], edi
0x1800046f4  lea     rax, [rsp+0B8h+var_40]
0x1800046f9  mov     [rsp+0B8h+var_98], rax
0x1800046fe  mov     r9d, 2
0x180004704  lea     rdx, DEVICE_DIRECTORY_CLIENT_CALLED
0x18000470b  call    McGenEventWrite_EventWriteTransfer
0x180004710  lea     r8, [rsp+0B8h+var_88]
0x180004715  lea     rdx, [rsp+0B8h+var_78]
0x18000471a  mov     ecx, 59h ; 'Y'
0x18000471f  call    cs:__imp_Pdcv2ActivationClientRegister
0x180004725  mov     ecx, r15d
0x180004728  call    cs:__imp_RoInitialize
0x18000472e  mov     ebx, eax
0x180004730  test    eax, eax
0x180004732  jns     short loc_180004769
0x180004734  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x18000473b  jz      loc_180004C16
0x180004741  lea     rax, aChrWindowsFoun; "CHR(Windows::Foundation::Initialize(RO_"...
0x180004748  mov     [rsp+0B8h+var_90], rax
0x18000474d  mov     dword ptr [rsp+0B8h+var_98], 0EDh
0x180004755  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000475c  mov     r8d, ebx
0x18000475f  call    McTemplateU0dsqs_EventWriteTransfer
0x180004764  jmp     loc_180004C16
0x180004769  test    rsi, rsi
0x18000476c  jnz     short loc_1800047A9
0x18000476e  mov     r8d, 80070057h
0x180004774  mov     ebx, r8d
0x180004777  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x18000477e  jz      loc_180004C10
0x180004784  lea     rax, aCprPwszconfigu; "CPR(pwszConfiguration)"
0x18000478b  mov     [rsp+0B8h+var_90], rax
0x180004790  mov     dword ptr [rsp+0B8h+var_98], 0F0h
0x180004798  lea     r9, aOnecoreuapShel_9; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000479f  call    McTemplateU0dsqs_EventWriteTransfer
0x1800047a4  jmp     loc_180004C10
0x1800047a9  mov     rdx, rsi
0x1800047ac  lea     rcx, [rsp+0B8h+var_60]
0x1800047b1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800047b6  nop
0x1800047b7  xor     r9d, r9d
0x1800047ba  xor     r8d, r8d
0x1800047bd  lea     rdx, aDebugbreak; "-DebugBreak"
0x1800047c4  lea     rcx, [rsp+0B8h+var_60]
0x1800047c9  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x1800047ce  test    eax, eax
0x1800047d0  jz      short loc_1800047EF
0x1800047d2  jmp     short loc_1800047DF
0x1800047d4  mov     ecx, 5DCh; dwMilliseconds
0x1800047d9  call    cs:__imp_Sleep
0x1800047df  call    cs:__imp_IsDebuggerPresent
0x1800047e5  test    eax, eax
0x1800047e7  jz      short loc_1800047D4
0x1800047e9  call    cs:__imp_DebugBreak
0x1800047ef  xor     r9d, r9d
0x1800047f2  mov     r8d, r15d
0x1800047f5  lea     rdx, aRegisterdevice_1; "-RegisterDevice"
0x1800047fc  lea     rcx, [rsp+0B8h+var_60]
0x180004801  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004806  test    eax, eax
0x180004808  jz      short loc_18000484F
0x18000480a  mov     r8, [rsp+0B8h+var_88]
0x18000480f  lea     rdx, [rsp+0B8h+var_60]
0x180004814  mov     rcx, r14
0x180004817  call    ?ProcessRegisterDevice@CDeviceDirectoryClientHandler@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; CDeviceDirectoryClientHandler::ProcessRegisterDevice(std::wstring &,void *)
0x18000481c  mov     ebx, eax
0x18000481e  test    eax, eax
0x180004820  jns     loc_180004C10
0x180004826  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x18000482d  jz      loc_180004C10
0x180004833  lea     rax, aChrProcessregi; "CHR(ProcessRegisterDevice(wstrConfigura"...
0x18000483a  mov     [rsp+0B8h+var_90], rax
0x18000483f  mov     dword ptr [rsp+0B8h+var_98], 103h
0x180004847  mov     r8d, ebx
0x18000484a  jmp     loc_180004798
0x18000484f  xor     r9d, r9d
0x180004852  mov     r8d, r15d
0x180004855  lea     rdx, aRegisteruserde_0; "-RegisterUserDevice"
0x18000485c  lea     rcx, [rsp+0B8h+var_60]
0x180004861  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004866  test    eax, eax
0x180004868  jz      short loc_1800048A9
0x18000486a  mov     r8, [rsp+0B8h+var_88]
0x18000486f  lea     rdx, [rsp+0B8h+var_60]
0x180004874  mov     rcx, r14
0x180004877  call    ?ProcessRegisterUserDevice@CDeviceDirectoryClientHandler@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; CDeviceDirectoryClientHandler::ProcessRegisterUserDevice(std::wstring &,void *)
0x18000487c  mov     ebx, eax
0x18000487e  test    eax, eax
0x180004880  jns     loc_180004C10
0x180004886  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x18000488d  jz      loc_180004C10
0x180004893  lea     rax, aChrProcessregi_1; "CHR(ProcessRegisterUserDevice(wstrConfi"...
0x18000489a  mov     [rsp+0B8h+var_90], rax
0x18000489f  mov     dword ptr [rsp+0B8h+var_98], 107h
0x1800048a7  jmp     short loc_180004847
0x1800048a9  xor     r9d, r9d
0x1800048ac  mov     r8d, r15d
0x1800048af  lea     rdx, aRegisterphone; "-RegisterPhone"
0x1800048b6  lea     rcx, [rsp+0B8h+var_60]
0x1800048bb  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x1800048c0  test    eax, eax
0x1800048c2  jz      short loc_1800048FE
0x1800048c4  lea     rdx, [rsp+0B8h+var_60]
0x1800048c9  call    ?ProcessRegisterPhone@CDeviceDirectoryClientHandler@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; CDeviceDirectoryClientHandler::ProcessRegisterPhone(std::wstring &,void *)
0x1800048ce  mov     ebx, eax
0x1800048d0  test    eax, eax
0x1800048d2  jns     loc_180004C10
0x1800048d8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x1800048df  jz      loc_180004C10
0x1800048e5  lea     rax, aChrProcessregi_0; "CHR(ProcessRegisterPhone(wstrConfigurat"...
0x1800048ec  mov     [rsp+0B8h+var_90], rax
0x1800048f1  mov     dword ptr [rsp+0B8h+var_98], 10Bh
0x1800048f9  jmp     loc_180004847
0x1800048fe  xor     r9d, r9d
0x180004901  mov     r8d, r15d
0x180004904  lea     rdx, aIntegritycheck; "-IntegrityCheck"
0x18000490b  lea     rcx, [rsp+0B8h+var_60]
0x180004910  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004915  test    eax, eax
0x180004917  jz      short loc_18000494E
0x180004919  call    ?IntegrityCheck@DdcStateController@@SAJXZ; DdcStateController::IntegrityCheck(void)
0x18000491e  mov     ebx, eax
0x180004920  test    eax, eax
0x180004922  jns     loc_180004C10
0x180004928  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x18000492f  jz      loc_180004C10
0x180004935  lea     rax, aChrDdcstatecon_0; "CHR(DdcStateController::IntegrityCheck("...
0x18000493c  mov     [rsp+0B8h+var_90], rax
0x180004941  mov     dword ptr [rsp+0B8h+var_98], 10Fh
0x180004949  jmp     loc_180004847
0x18000494e  xor     r9d, r9d
0x180004951  mov     r8d, r15d
0x180004954  lea     rdx, aHandleupgrade; "-HandleUpgrade"
0x18000495b  lea     rcx, [rsp+0B8h+var_60]
0x180004960  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004965  test    eax, eax
0x180004967  jz      short loc_18000499E
0x180004969  call    ?HandleUpgrade@DdcStateController@@SAJXZ; DdcStateController::HandleUpgrade(void)
0x18000496e  mov     ebx, eax
0x180004970  test    eax, eax
0x180004972  jns     loc_180004C10
0x180004978  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x18000497f  jz      loc_180004C10
0x180004985  lea     rax, aChrDdcstatecon; "CHR(DdcStateController::HandleUpgrade()"...
0x18000498c  mov     [rsp+0B8h+var_90], rax
0x180004991  mov     dword ptr [rsp+0B8h+var_98], 113h
0x180004999  jmp     loc_180004847
0x18000499e  xor     r9d, r9d
0x1800049a1  mov     r8d, r15d
0x1800049a4  lea     rdx, aWnscommand; "-WnsCommand"
0x1800049ab  lea     rcx, [rsp+0B8h+var_60]
0x1800049b0  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x1800049b5  test    eax, eax
0x1800049b7  jz      short loc_1800049EE
0x1800049b9  call    ?HandleWnsCommand@DdcCommandController@@SAJXZ; DdcCommandController::HandleWnsCommand(void)
0x1800049be  mov     ebx, eax
0x1800049c0  test    eax, eax
0x1800049c2  jns     loc_180004C10
0x1800049c8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x1800049cf  jz      loc_180004C10
0x1800049d5  lea     rax, aChrDdccommandc_6; "CHR(DdcCommandController::HandleWnsComm"...
0x1800049dc  mov     [rsp+0B8h+var_90], rax
0x1800049e1  mov     dword ptr [rsp+0B8h+var_98], 117h
0x1800049e9  jmp     loc_180004847
0x1800049ee  xor     r9d, r9d
0x1800049f1  mov     r8d, r15d
0x1800049f4  lea     rdx, aSmscommand; "-SmsCommand"
0x1800049fb  lea     rcx, [rsp+0B8h+var_60]
0x180004a00  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004a05  test    eax, eax
0x180004a07  jz      short loc_180004A3E
0x180004a09  call    ?HandleSmsCommands@DdcCommandController@@SAJXZ; DdcCommandController::HandleSmsCommands(void)
0x180004a0e  mov     ebx, eax
0x180004a10  test    eax, eax
0x180004a12  jns     loc_180004C10
0x180004a18  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x180004a1f  jz      loc_180004C10
0x180004a25  lea     rax, aChrDdccommandc_4; "CHR(DdcCommandController::HandleSmsComm"...
0x180004a2c  mov     [rsp+0B8h+var_90], rax
0x180004a31  mov     dword ptr [rsp+0B8h+var_98], 11Bh
0x180004a39  jmp     loc_180004847
0x180004a3e  xor     r9d, r9d
0x180004a41  mov     r8d, r15d
0x180004a44  lea     rdx, aHandlecommand; "-HandleCommand"
0x180004a4b  lea     rcx, [rsp+0B8h+var_60]
0x180004a50  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004a55  test    eax, eax
0x180004a57  jz      short loc_180004A93
0x180004a59  mov     rcx, [rsp+0B8h+var_88]; void *
0x180004a5e  call    ?HandleCommand@DdcCommandController@@SAJPEAX@Z; DdcCommandController::HandleCommand(void *)
0x180004a63  mov     ebx, eax
0x180004a65  test    eax, eax
0x180004a67  jns     loc_180004C10
0x180004a6d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x180004a74  jz      loc_180004C10
0x180004a7a  lea     rax, aChrDdccommandc_1; "CHR(DdcCommandController::HandleCommand"...
0x180004a81  mov     [rsp+0B8h+var_90], rax
0x180004a86  mov     dword ptr [rsp+0B8h+var_98], 11Fh
0x180004a8e  jmp     loc_180004847
0x180004a93  xor     r9d, r9d
0x180004a96  mov     r8d, r15d
0x180004a99  lea     rdx, aLocatecommandr; "-LocateCommandRetry"
0x180004aa0  lea     rcx, [rsp+0B8h+var_60]
0x180004aa5  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004aaa  lea     rcx, [rsp+0B8h+var_60]
0x180004aaf  test    eax, eax
0x180004ab1  jz      short loc_180004AED
0x180004ab3  mov     rdx, [rsp+0B8h+var_88]
0x180004ab8  call    ?HandleLocateCommandRetry@DdcCommandController@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; DdcCommandController::HandleLocateCommandRetry(std::wstring &,void *)
0x180004abd  mov     ebx, eax
0x180004abf  test    eax, eax
0x180004ac1  jns     loc_180004C10
0x180004ac7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x180004ace  jz      loc_180004C10
0x180004ad4  lea     rax, aChrDdccommandc_3; "CHR(DdcCommandController::HandleLocateC"...
0x180004adb  mov     [rsp+0B8h+var_90], rax
0x180004ae0  mov     dword ptr [rsp+0B8h+var_98], 123h
0x180004ae8  jmp     loc_180004847
0x180004aed  xor     r9d, r9d
0x180004af0  mov     r8d, r15d
0x180004af3  lea     rdx, aUsersessioncom; "-UserSessionCommand"
0x180004afa  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004aff  test    eax, eax
0x180004b01  jz      short loc_180004B38
0x180004b03  call    ?UserSessionCommand@DdcCommandController@@SAJXZ; DdcCommandController::UserSessionCommand(void)
0x180004b08  mov     ebx, eax
0x180004b0a  test    eax, eax
0x180004b0c  jns     loc_180004C10
0x180004b12  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x180004b19  jz      loc_180004C10
0x180004b1f  lea     rax, aChrDdccommandc_2; "CHR(DdcCommandController::UserSessionCo"...
0x180004b26  mov     [rsp+0B8h+var_90], rax
0x180004b2b  mov     dword ptr [rsp+0B8h+var_98], 127h
0x180004b33  jmp     loc_180004847
0x180004b38  xor     r9d, r9d
0x180004b3b  mov     r8d, r15d
0x180004b3e  lea     rdx, aUpdatestatusre_0; "-UpdateStatusRetry"
0x180004b45  lea     rcx, [rsp+0B8h+var_60]
0x180004b4a  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004b4f  lea     rcx, [rsp+0B8h+var_60]
0x180004b54  test    eax, eax
0x180004b56  jz      short loc_180004B92
0x180004b58  mov     rdx, [rsp+0B8h+var_88]
0x180004b5d  call    ?HandleUpdateStatusRetry@DdcCommandController@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; DdcCommandController::HandleUpdateStatusRetry(std::wstring &,void *)
0x180004b62  mov     ebx, eax
0x180004b64  test    eax, eax
0x180004b66  jns     loc_180004C10
0x180004b6c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, r15b
0x180004b73  jz      loc_180004C10
0x180004b79  lea     rax, aChrDdccommandc_5; "CHR(DdcCommandController::HandleUpdateS"...
0x180004b80  mov     [rsp+0B8h+var_90], rax
0x180004b85  mov     dword ptr [rsp+0B8h+var_98], 12Bh
0x180004b8d  jmp     loc_180004847
0x180004b92  xor     r9d, r9d
0x180004b95  mov     r8d, r15d
0x180004b98  lea     rdx, aDeviceunlocked_0; "-DeviceUnlocked"
0x180004b9f  call    ?ConfigurationArgumentPresent@@YAHAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGHH@Z; ConfigurationArgumentPresent(std::wstring &,ushort const *,int,int)
0x180004ba4  test    eax, eax
0x180004ba6  jz      short loc_180004BDF
0x180004ba8  mov     rdx, [rsp+0B8h+var_88]
0x180004bad  lea     rcx, [rsp+0B8h+var_60]
  ... truncated ...
```
