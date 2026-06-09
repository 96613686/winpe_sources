# DdcCommandExecutor::ProcessLockCommand(CommandPrefix *,void *,ushort *,ushort *,int,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x1800107e0`
- end: `0x180010dcc`
- name: `?ProcessLockCommand@DdcCommandExecutor@@SAJPEAUCommandPrefix@@PEAXPEAG2HAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1516`
- prototype: `__int64 __fastcall(struct CommandPrefix *, __int64, __int64, __int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180005f5c`

## callees

- `0x1800024c0`
- `0x1800028d4`
- `0x1800036e8`
- `0x180003c2c`
- `0x180004060`
- `0x180004d5c`
- `0x180004db8`
- `0x1800050b8`
- `0x180005310`
- `0x180009164`
- `0x18000fd90`
- `0x18001006c`
- `0x1800107e0`
- `0x1800115c0`
- `0x1800115e0`
- `0x180011bf0`
- `0x180011e74`
- `0x1800128fc`
- `0x180012c94`
- `0x1800132e4`
- `0x18001c8a4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010894`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010a6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010ac9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010894`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010a6f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010ac9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800108bb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800108bb`

## string_xrefs

- `0x180010b24`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x180010c3a`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x180010caa`: `CHR(taskSchedulerWrapper.Initialize())`
- `0x180010cf7`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddccommandexecutor.cpp`
- `0x180010b64`: `CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, &updateStatusContext))`
- `0x180010c76`: `CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, &updateStatusContext))`
- `0x180010955`: `LockUpdateStatus`
- `0x180010af1`: `LockUpdateStatus`
- `0x180010ce3`: `CHR(taskSchedulerWrapper.ScheduleDeviceUnlockedEvent(pPrefix, &updateStatusContext, pCommandHandler.Get()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DdcCommandExecutor::ProcessLockCommand(
        struct CommandPrefix *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  int v9; // edx
  int v10; // ecx
  int updated; // ebx
  int dwHighDateTime; // eax
  int v13; // edx
  int v14; // ecx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // r10
  __int64 v18; // r11
  __int64 dwLowDateTime; // r8
  DWORD v20; // r11d
  int v21; // edx
  int v22; // ecx
  int v23; // edx
  int v24; // ecx
  int v25; // edx
  int v26; // ecx
  int v27; // edx
  int v28; // ecx
  int v29; // edx
  int v30; // ecx
  int v31; // edx
  int v32; // ecx
  struct ICommandHandler *v33; // rcx
  unsigned int *v35; // [rsp+38h] [rbp-E8h]
  unsigned int v36; // [rsp+A0h] [rbp-80h] BYREF
  struct ICommandHandler *ppv; // [rsp+A8h] [rbp-78h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-70h] BYREF
  void *Block; // [rsp+B8h] [rbp-68h] BYREF
  struct Windows::Data::Json::IJsonValue *v40; // [rsp+C0h] [rbp-60h] BYREF
  struct Windows::Data::Json::IJsonValue *v41; // [rsp+C8h] [rbp-58h] BYREF
  struct Windows::Data::Json::IJsonValue *v42; // [rsp+D0h] [rbp-50h] BYREF
  struct Windows::Data::Json::IJsonValue *v43; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v44; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v45; // [rsp+E8h] [rbp-38h]
  struct _FILETIME SystemTimeAsFileTime[4]; // [rsp+F0h] [rbp-30h] BYREF
  _BYTE v47[16]; // [rsp+110h] [rbp-10h] BYREF
  __int64 v48; // [rsp+120h] [rbp+0h]
  _BYTE v49[16]; // [rsp+130h] [rbp+10h] BYREF
  __int64 v50; // [rsp+140h] [rbp+20h]

  memset(SystemTimeAsFileTime, 0, 28);
  v36 = 0;
  v38 = 0;
  v44 = a2;
  v45 = 0;
  Block = 0;
  std::wstring::wstring(v49);
  std::wstring::wstring(v47);
  ppv = 0;
  v43 = 0;
  v42 = 0;
  v41 = 0;
  v40 = 0;
  if ( !a1 )
  {
    updated = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v10,
        v9,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
        230,
        (__int64)"CPR(pPrefix)");
    goto LABEL_51;
  }
  GetSystemTimeAsFileTime(SystemTimeAsFileTime);
  SystemTimeAsFileTime[2].dwHighDateTime = CoCreateInstance(
                                             &CLSID_CommandHandler,
                                             0,
                                             1u,
                                             &IID_ICommandHandler,
                                             (LPVOID *)&ppv);
  if ( (SystemTimeAsFileTime[2].dwHighDateTime & 0x80000000) == 0 )
  {
    dwHighDateTime = (*(__int64 (__fastcall **)(struct ICommandHandler *, __int64, __int64, _QWORD, __int64))(*(_QWORD *)ppv + 32LL))(
                       ppv,
                       a3,
                       a4,
                       a5,
                       a6);
    SystemTimeAsFileTime[2].dwHighDateTime = dwHighDateTime;
    if ( dwHighDateTime == -2147024891 )
    {
      updated = DdcAccountHelper::EnumerateUsers(&v43, &v42, &v41, &v40, 0, 0, 0, v35);
      if ( updated < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v14,
            v13,
            updated,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
            245,
            (__int64)"CHR(DdcAccountHelper::EnumerateUsers(pAdmins.GetAddressOf(), pDeviceOwners.GetAddressOf(), pStandar"
                     "dUsers.GetAddressOf(), pConnectedAdmins.GetAddressOf()))");
        goto LABEL_51;
      }
      dwHighDateTime = SystemTimeAsFileTime[2].dwHighDateTime;
    }
    if ( dwHighDateTime >= 0 )
    {
      if ( (int)DdcPdcActivationWrapper::ActivateClient((DdcPdcActivationWrapper *)&v44, L"LockUpdateStatus") >= 0
        && (int)UpdateStatusWrapper(
                  &v36,
                  *(unsigned int *)a1,
                  4,
                  *((unsigned int *)a1 + 2),
                  0,
                  0,
                  *(_QWORD *)((char *)a1 + 12),
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
                  0,
                  0,
                  &Block) >= 0 )
      {
        if ( Block )
        {
          v15 = -1;
          do
            ++v15;
          while ( *((_WORD *)Block + v15) );
          if ( v15 && (int)TryGetLockMessageFromResponse(Block, v47) < 0 )
          {
            v48 = 0;
            *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47) = 0;
          }
        }
      }
      if ( !v48 && (int)GetDefaultLockMessage(ppv, a4, v47) < 0 )
      {
        v48 = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47) = 0;
      }
      if ( (int)GetLockScreenTitle(ppv, v49) < 0 )
      {
        v50 = 0;
        *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v49) = 0;
      }
      GetSystemTimeAsFileTime(SystemTimeAsFileTime);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
      v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v49);
      SystemTimeAsFileTime[2].dwHighDateTime = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(v17 + 40))(
                                                 v18,
                                                 a3,
                                                 v16);
      if ( a5 )
        (*(void (__fastcall **)(struct ICommandHandler *, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0);
    }
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime[1]);
  dwLowDateTime = 7;
  v20 = SystemTimeAsFileTime[2].dwHighDateTime;
  if ( (SystemTimeAsFileTime[2].dwHighDateTime & 0x80000000) == 0 )
    dwLowDateTime = 5;
  SystemTimeAsFileTime[2].dwLowDateTime = dwLowDateTime;
  if ( !v45 )
  {
    if ( (int)DdcPdcActivationWrapper::ActivateClient((DdcPdcActivationWrapper *)&v44, L"LockUpdateStatus") < 0 )
    {
      updated = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v38);
      if ( updated < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v22,
            v21,
            updated,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
            90,
            (__int64)"CHR(taskSchedulerWrapper.Initialize())");
        goto LABEL_51;
      }
      updated = DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(
                  (DdcTaskSchedulerWrapper *)&v38,
                  a1,
                  (struct UpdateStatusContext *)SystemTimeAsFileTime);
      if ( updated < 0 )
      {
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v24,
            v23,
            updated,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
            91,
            (__int64)"CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, &updateStatusContext))");
        goto LABEL_51;
      }
      goto LABEL_44;
    }
    v20 = SystemTimeAsFileTime[2].dwHighDateTime;
    dwLowDateTime = SystemTimeAsFileTime[2].dwLowDateTime;
  }
  updated = UpdateStatusWrapper(
              &v36,
              *(unsigned int *)a1,
              dwLowDateTime,
              *((unsigned int *)a1 + 2),
              0,
              v20,
              *(_QWORD *)((char *)a1 + 12),
              SystemTimeAsFileTime,
              &SystemTimeAsFileTime[1],
              0,
              0,
              v43,
              v42,
              v41,
              v40,
              0,
              0,
              0,
              0,
              0);
  if ( !(unsigned int)ShouldRetry(updated, v36) )
    goto LABEL_44;
  updated = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v38);
  if ( updated < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v26,
        v25,
        updated,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
        83,
        (__int64)"CHR(taskSchedulerWrapper.Initialize())");
    goto LABEL_51;
  }
  updated = DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(
              (DdcTaskSchedulerWrapper *)&v38,
              a1,
              (struct UpdateStatusContext *)SystemTimeAsFileTime);
  if ( updated >= 0 )
  {
LABEL_44:
    if ( (SystemTimeAsFileTime[2].dwHighDateTime & 0x80000000) == 0 )
    {
      updated = DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v38);
      if ( updated >= 0 )
      {
        updated = DdcTaskSchedulerWrapper::ScheduleDeviceUnlockedEvent(
                    (DdcTaskSchedulerWrapper *)&v38,
                    a1,
                    (struct UpdateStatusContext *)SystemTimeAsFileTime,
                    ppv);
        if ( updated < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v32,
            v31,
            updated,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
            100,
            (__int64)"CHR(taskSchedulerWrapper.ScheduleDeviceUnlockedEvent(pPrefix, &updateStatusContext, pCommandHandler.Get()))");
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v30,
          v29,
          updated,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
          97,
          (__int64)"CHR(taskSchedulerWrapper.Initialize())");
      }
    }
    goto LABEL_51;
  }
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v28,
      v27,
      updated,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddccommandexecutor.cpp",
      84,
      (__int64)"CHR(taskSchedulerWrapper.ScheduleUpdateStatusRetry(pPrefix, &updateStatusContext))");
LABEL_51:
  if ( Block )
    operator delete(Block);
  DdcTraceHelper::TraceCommandResult(
    v45 != 0,
    *(_DWORD *)a1,
    3u,
    *((_DWORD *)a1 + 2),
    SystemTimeAsFileTime[2].dwHighDateTime,
    v36,
    updated);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
  v33 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(struct ICommandHandler *))(*(_QWORD *)v33 + 16LL))(v33);
  }
  std::wstring::_Tidy_deallocate(v47);
  std::wstring::_Tidy_deallocate(v49);
  DdcPdcActivationWrapper::DeactivateClient((DdcPdcActivationWrapper *)&v44);
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(&v38);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800107e0  push    rbp
0x1800107e2  push    rbx
0x1800107e3  push    rsi
0x1800107e4  push    rdi
0x1800107e5  push    r12
0x1800107e7  push    r13
0x1800107e9  push    r14
0x1800107eb  lea     rbp, [rsp-40h]
0x1800107f0  sub     rsp, 160h
0x1800107f7  mov     rax, cs:__security_cookie
0x1800107fe  xor     rax, rsp
0x180010801  mov     [rbp+70h+var_40], rax
0x180010805  mov     r14, r9
0x180010808  mov     r12, r8
0x18001080b  mov     rsi, rcx
0x18001080e  mov     r13, [rbp+70h+arg_28]
0x180010815  xorps   xmm0, xmm0
0x180010818  movups  xmmword ptr [rbp+70h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x18001081c  movups  xmmword ptr [rbp+70h+SystemTimeAsFileTime.dwHighDateTime+8], xmm0
0x180010820  xor     ebx, ebx
0x180010822  mov     [rbp+70h+var_F0], ebx
0x180010825  mov     [rbp+70h+var_E0], rbx
0x180010829  mov     [rbp+70h+var_B0], rdx
0x18001082d  mov     [rbp+70h+var_A8], rbx
0x180010831  mov     [rbp+70h+Block], rbx
0x180010835  lea     rcx, [rbp+70h+var_60]
0x180010839  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001083e  nop
0x18001083f  lea     rcx, [rbp+70h+var_80]
0x180010843  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180010848  nop
0x180010849  mov     [rbp+70h+var_E8], rbx
0x18001084d  mov     [rbp+70h+var_B8], rbx
0x180010851  mov     [rbp+70h+var_C0], rbx
0x180010855  mov     [rbp+70h+var_C8], rbx
0x180010859  mov     [rbp+70h+var_D0], rbx
0x18001085d  test    rsi, rsi
0x180010860  jnz     short loc_180010890
0x180010862  mov     ebx, 80070057h
0x180010867  lea     edi, [rsi+1]
0x18001086a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, dil
0x180010871  jz      loc_180010D06
0x180010877  lea     rax, aCprPprefix; "CPR(pPrefix)"
0x18001087e  mov     [rsp+190h+var_168], rax
0x180010883  mov     dword ptr [rsp+190h+ppv], 1E6h
0x18001088b  jmp     loc_180010CF7
0x180010890  lea     rcx, [rbp+70h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010894  call    cs:__imp_GetSystemTimeAsFileTime
0x18001089a  lea     rax, [rbp+70h+var_E8]
0x18001089e  mov     [rsp+190h+ppv], rax; ppv
0x1800108a3  lea     r9, IID_ICommandHandler; riid
0x1800108aa  mov     edi, 1
0x1800108af  mov     r8d, edi; dwClsContext
0x1800108b2  xor     edx, edx; pUnkOuter
0x1800108b4  lea     rcx, CLSID_CommandHandler; rclsid
0x1800108bb  call    cs:__imp_CoCreateInstance
0x1800108c1  mov     [rbp+70h+var_8C], eax
0x1800108c4  test    eax, eax
0x1800108c6  js      loc_180010AC5
0x1800108cc  mov     rcx, [rbp+70h+var_E8]
0x1800108d0  mov     rax, [rcx]
0x1800108d3  mov     [rsp+190h+ppv], r13
0x1800108d8  mov     r9d, [rbp+70h+arg_20]
0x1800108df  mov     r8, r14
0x1800108e2  mov     rdx, r12
0x1800108e5  mov     rax, [rax+20h]
0x1800108e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108ee  mov     [rbp+70h+var_8C], eax
0x1800108f1  cmp     eax, 80070005h
0x1800108f6  jnz     short loc_18001094D
0x1800108f8  mov     [rsp+190h+var_160], rbx; unsigned int *
0x1800108fd  mov     [rsp+190h+var_168], rbx; unsigned int *
0x180010902  mov     [rsp+190h+ppv], rbx; unsigned int *
0x180010907  lea     r9, [rbp+70h+var_D0]; struct Windows::Data::Json::IJsonValue **
0x18001090b  lea     r8, [rbp+70h+var_C8]; struct Windows::Data::Json::IJsonValue **
0x18001090f  lea     rdx, [rbp+70h+var_C0]; struct Windows::Data::Json::IJsonValue **
0x180010913  lea     rcx, [rbp+70h+var_B8]; struct Windows::Data::Json::IJsonValue **
0x180010917  call    ?EnumerateUsers@DdcAccountHelper@@SAJPEAPEAUIJsonValue@Json@Data@Windows@@000PEAK111@Z; DdcAccountHelper::EnumerateUsers(Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,Windows::Data::Json::IJsonValue * *,ulong *,ulong *,ulong *,ulong *)
0x18001091c  mov     ebx, eax
0x18001091e  test    eax, eax
0x180010920  jns     short loc_180010948
0x180010922  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, dil
0x180010929  jz      loc_180010D06
0x18001092f  lea     rax, aChrDdcaccounth; "CHR(DdcAccountHelper::EnumerateUsers(pA"...
0x180010936  mov     [rsp+190h+var_168], rax
0x18001093b  mov     dword ptr [rsp+190h+ppv], 1F5h
0x180010943  jmp     loc_180010CF7
0x180010948  mov     eax, [rbp+70h+var_8C]
0x18001094b  xor     ebx, ebx
0x18001094d  test    eax, eax
0x18001094f  js      loc_180010AC5
0x180010955  lea     rdx, aLockupdatestat; "LockUpdateStatus"
0x18001095c  lea     rcx, [rbp+70h+var_B0]; this
0x180010960  call    ?ActivateClient@DdcPdcActivationWrapper@@QEAAJPEBG@Z; DdcPdcActivationWrapper::ActivateClient(ushort const *)
0x180010965  test    eax, eax
0x180010967  js      loc_180010A20
0x18001096d  lea     rax, [rbp+70h+Block]
0x180010971  mov     [rsp+190h+var_F8], rax
0x180010979  mov     [rsp+190h+var_100], rbx
0x180010981  mov     [rsp+190h+var_108], rbx
0x180010989  mov     [rsp+190h+var_110], rbx
0x180010991  mov     [rsp+190h+var_118], rbx
0x180010996  mov     [rsp+190h+var_120], rbx
0x18001099b  mov     [rsp+190h+var_128], rbx
0x1800109a0  mov     [rsp+190h+var_130], rbx
0x1800109a5  mov     [rsp+190h+var_138], rbx
0x1800109aa  mov     [rsp+190h+var_140], rbx
0x1800109af  mov     [rsp+190h+var_148], rbx
0x1800109b4  mov     [rsp+190h+var_150], rbx
0x1800109b9  mov     [rsp+190h+var_158], rbx
0x1800109be  mov     rax, [rsi+0Ch]
0x1800109c2  mov     [rsp+190h+var_160], rax
0x1800109c7  mov     dword ptr [rsp+190h+var_168], ebx
0x1800109cb  mov     dword ptr [rsp+190h+ppv], ebx
0x1800109cf  mov     r9d, [rsi+8]
0x1800109d3  mov     r8d, 4
0x1800109d9  mov     edx, [rsi]
0x1800109db  lea     rcx, [rbp+70h+var_F0]
0x1800109df  call    ?UpdateStatusWrapper@@YAJPEAKKW4MdmCommandStatus@@W4MdmCommandChannelType@@KKU_FILETIME@@PEAU3@4PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@6666PEAH777PEAPEAG@Z; UpdateStatusWrapper(ulong *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,ulong,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)
0x1800109e4  test    eax, eax
0x1800109e6  js      short loc_180010A20
0x1800109e8  mov     rcx, [rbp+70h+Block]
0x1800109ec  test    rcx, rcx
0x1800109ef  jz      short loc_180010A20
0x1800109f1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800109f5  inc     rax
0x1800109f8  cmp     [rcx+rax*2], bx
0x1800109fc  jnz     short loc_1800109F5
0x1800109fe  test    rax, rax
0x180010a01  jz      short loc_180010A20
0x180010a03  lea     rdx, [rbp+70h+var_80]
0x180010a07  call    ?TryGetLockMessageFromResponse@@YAJPEAGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; TryGetLockMessageFromResponse(ushort *,std::wstring &)
0x180010a0c  test    eax, eax
0x180010a0e  jns     short loc_180010A20
0x180010a10  mov     [rbp+70h+var_70], rbx
0x180010a14  lea     rcx, [rbp+70h+var_80]
0x180010a18  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180010a1d  mov     [rax], bx
0x180010a20  cmp     [rbp+70h+var_70], rbx
0x180010a24  jnz     short loc_180010A4A
0x180010a26  lea     r8, [rbp+70h+var_80]
0x180010a2a  mov     rdx, r14
0x180010a2d  mov     rcx, [rbp+70h+var_E8]
0x180010a31  call    ?GetDefaultLockMessage@@YAJPEAUICommandHandler@@PEAGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetDefaultLockMessage(ICommandHandler *,ushort *,std::wstring &)
0x180010a36  test    eax, eax
0x180010a38  jns     short loc_180010A4A
0x180010a3a  mov     [rbp+70h+var_70], rbx
0x180010a3e  lea     rcx, [rbp+70h+var_80]
0x180010a42  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180010a47  mov     [rax], bx
0x180010a4a  lea     rdx, [rbp+70h+var_60]
0x180010a4e  mov     rcx, [rbp+70h+var_E8]
0x180010a52  call    ?GetLockScreenTitle@@YAJPEAUICommandHandler@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetLockScreenTitle(ICommandHandler *,std::wstring &)
0x180010a57  test    eax, eax
0x180010a59  jns     short loc_180010A6B
0x180010a5b  mov     [rbp+70h+var_50], rbx
0x180010a5f  lea     rcx, [rbp+70h+var_60]
0x180010a63  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180010a68  mov     [rax], bx
0x180010a6b  lea     rcx, [rbp+70h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010a6f  call    cs:__imp_GetSystemTimeAsFileTime
0x180010a75  mov     r11, [rbp+70h+var_E8]
0x180010a79  mov     r10, [r11]
0x180010a7c  lea     rcx, [rbp+70h+var_80]
0x180010a80  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180010a85  mov     r9, rax
0x180010a88  lea     rcx, [rbp+70h+var_60]
0x180010a8c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180010a91  mov     r8, rax
0x180010a94  mov     [rsp+190h+ppv], r13
0x180010a99  mov     rdx, r12
0x180010a9c  mov     rcx, r11
0x180010a9f  mov     rax, [r10+28h]
0x180010aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aa8  mov     [rbp+70h+var_8C], eax
0x180010aab  cmp     [rbp+70h+arg_20], ebx
0x180010ab1  jz      short loc_180010AC5
0x180010ab3  mov     rcx, [rbp+70h+var_E8]
0x180010ab7  mov     rax, [rcx]
0x180010aba  xor     edx, edx
0x180010abc  mov     rax, [rax+18h]
0x180010ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ac5  lea     rcx, [rbp+70h+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x180010ac9  call    cs:__imp_GetSystemTimeAsFileTime
0x180010acf  mov     eax, 5
0x180010ad4  lea     r8d, [rax+2]
0x180010ad8  mov     r11d, [rbp+70h+var_8C]
0x180010adc  test    r11d, r11d
0x180010adf  cmovns  r8d, eax
0x180010ae3  mov     [rbp+70h+var_90], r8d
0x180010ae7  cmp     [rbp+70h+var_A8], rbx
0x180010aeb  jnz     loc_180010B85
0x180010af1  lea     rdx, aLockupdatestat; "LockUpdateStatus"
0x180010af8  lea     rcx, [rbp+70h+var_B0]; this
0x180010afc  call    ?ActivateClient@DdcPdcActivationWrapper@@QEAAJPEBG@Z; DdcPdcActivationWrapper::ActivateClient(ushort const *)
0x180010b01  test    eax, eax
0x180010b03  jns     short loc_180010B7D
0x180010b05  lea     rcx, [rbp+70h+var_E0]; this
0x180010b09  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x180010b0e  mov     ebx, eax
0x180010b10  xor     r14d, r14d
0x180010b13  test    eax, eax
0x180010b15  jns     short loc_180010B3D
0x180010b17  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, dil
0x180010b1e  jz      loc_180010D06
0x180010b24  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x180010b2b  mov     [rsp+190h+var_168], rax
0x180010b30  mov     dword ptr [rsp+190h+ppv], 25Ah
0x180010b38  jmp     loc_180010CF7
0x180010b3d  lea     r8, [rbp+70h+SystemTimeAsFileTime]; struct UpdateStatusContext *
0x180010b41  mov     rdx, rsi; struct CommandPrefix *
0x180010b44  lea     rcx, [rbp+70h+var_E0]; this
0x180010b48  call    ?ScheduleUpdateStatusRetry@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@PEAUUpdateStatusContext@@@Z; DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(CommandPrefix *,UpdateStatusContext *)
0x180010b4d  mov     ebx, eax
0x180010b4f  test    eax, eax
0x180010b51  jns     loc_180010C8C
0x180010b57  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, dil
0x180010b5e  jz      loc_180010D06
0x180010b64  lea     rax, aChrTaskschedul_8; "CHR(taskSchedulerWrapper.ScheduleUpdate"...
0x180010b6b  mov     [rsp+190h+var_168], rax
0x180010b70  mov     dword ptr [rsp+190h+ppv], 25Bh
0x180010b78  jmp     loc_180010CF7
0x180010b7d  mov     r11d, [rbp+70h+var_8C]
0x180010b81  mov     r8d, [rbp+70h+var_90]
0x180010b85  mov     rcx, [rbp+70h+var_D0]
0x180010b89  mov     rdx, [rbp+70h+var_C8]
0x180010b8d  mov     r9, [rbp+70h+var_C0]
0x180010b91  mov     r10, [rbp+70h+var_B8]
0x180010b95  mov     rax, [rsi+0Ch]
0x180010b99  mov     [rsp+190h+var_F8], rbx
0x180010ba1  mov     [rsp+190h+var_100], rbx
0x180010ba9  mov     [rsp+190h+var_108], rbx
0x180010bb1  mov     [rsp+190h+var_110], rbx
0x180010bb9  mov     [rsp+190h+var_118], rbx
0x180010bbe  mov     [rsp+190h+var_120], rcx
0x180010bc3  mov     [rsp+190h+var_128], rdx
0x180010bc8  mov     [rsp+190h+var_130], r9
0x180010bcd  mov     [rsp+190h+var_138], r10
0x180010bd2  mov     [rsp+190h+var_140], rbx
0x180010bd7  mov     [rsp+190h+var_148], rbx
0x180010bdc  lea     rcx, [rbp+70h+SystemTimeAsFileTime.dwLowDateTime+8]
0x180010be0  mov     [rsp+190h+var_150], rcx
0x180010be5  lea     rcx, [rbp+70h+SystemTimeAsFileTime]
0x180010be9  mov     [rsp+190h+var_158], rcx
0x180010bee  mov     [rsp+190h+var_160], rax
0x180010bf3  mov     dword ptr [rsp+190h+var_168], r11d
0x180010bf8  mov     dword ptr [rsp+190h+ppv], ebx
0x180010bfc  mov     r9d, [rsi+8]
0x180010c00  mov     edx, [rsi]
0x180010c02  lea     rcx, [rbp+70h+var_F0]
0x180010c06  call    ?UpdateStatusWrapper@@YAJPEAKKW4MdmCommandStatus@@W4MdmCommandChannelType@@KKU_FILETIME@@PEAU3@4PEAUMdmLocation@@PEAUIJsonValue@Json@Data@Windows@@6666PEAH777PEAPEAG@Z; UpdateStatusWrapper(ulong *,ulong,MdmCommandStatus,MdmCommandChannelType,ulong,ulong,_FILETIME,_FILETIME *,_FILETIME *,MdmLocation *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,Windows::Data::Json::IJsonValue *,int *,int *,int *,int *,ushort * *)
0x180010c0b  mov     ebx, eax
0x180010c0d  mov     edx, [rbp+70h+var_F0]; unsigned int
0x180010c10  mov     ecx, eax; int
0x180010c12  call    ?ShouldRetry@@YAHJK@Z; ShouldRetry(long,ulong)
0x180010c17  xor     r14d, r14d
0x180010c1a  test    eax, eax
0x180010c1c  jz      short loc_180010C8C
0x180010c1e  lea     rcx, [rbp+70h+var_E0]; this
0x180010c22  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x180010c27  mov     ebx, eax
0x180010c29  test    eax, eax
0x180010c2b  jns     short loc_180010C53
0x180010c2d  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, dil
0x180010c34  jz      loc_180010D06
0x180010c3a  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x180010c41  mov     [rsp+190h+var_168], rax
0x180010c46  mov     dword ptr [rsp+190h+ppv], 253h
0x180010c4e  jmp     loc_180010CF7
0x180010c53  lea     r8, [rbp+70h+SystemTimeAsFileTime]; struct UpdateStatusContext *
0x180010c57  mov     rdx, rsi; struct CommandPrefix *
0x180010c5a  lea     rcx, [rbp+70h+var_E0]; this
0x180010c5e  call    ?ScheduleUpdateStatusRetry@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@PEAUUpdateStatusContext@@@Z; DdcTaskSchedulerWrapper::ScheduleUpdateStatusRetry(CommandPrefix *,UpdateStatusContext *)
0x180010c63  mov     ebx, eax
0x180010c65  test    eax, eax
0x180010c67  jns     short loc_180010C8C
0x180010c69  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, dil
0x180010c70  jz      loc_180010D06
0x180010c76  lea     rax, aChrTaskschedul_8; "CHR(taskSchedulerWrapper.ScheduleUpdate"...
0x180010c7d  mov     [rsp+190h+var_168], rax
0x180010c82  mov     dword ptr [rsp+190h+ppv], 254h
0x180010c8a  jmp     short loc_180010CF7
0x180010c8c  cmp     [rbp+70h+var_8C], r14d
0x180010c90  jl      short loc_180010D06
0x180010c92  lea     rcx, [rbp+70h+var_E0]; this
0x180010c96  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x180010c9b  mov     ebx, eax
0x180010c9d  test    eax, eax
0x180010c9f  jns     short loc_180010CC0
0x180010ca1  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, dil
0x180010ca8  jz      short loc_180010D06
0x180010caa  lea     rax, aChrTaskschedul_0; "CHR(taskSchedulerWrapper.Initialize())"
0x180010cb1  mov     [rsp+190h+var_168], rax
0x180010cb6  mov     dword ptr [rsp+190h+ppv], 261h
0x180010cbe  jmp     short loc_180010CF7
0x180010cc0  mov     r9, [rbp+70h+var_E8]; struct ICommandHandler *
0x180010cc4  lea     r8, [rbp+70h+SystemTimeAsFileTime]; struct UpdateStatusContext *
0x180010cc8  mov     rdx, rsi; struct CommandPrefix *
0x180010ccb  lea     rcx, [rbp+70h+var_E0]; this
0x180010ccf  call    ?ScheduleDeviceUnlockedEvent@DdcTaskSchedulerWrapper@@QEAAJPEAUCommandPrefix@@PEAUUpdateStatusContext@@PEAUICommandHandler@@@Z; DdcTaskSchedulerWrapper::ScheduleDeviceUnlockedEvent(CommandPrefix *,UpdateStatusContext *,ICommandHandler *)
  ... truncated ...
```
