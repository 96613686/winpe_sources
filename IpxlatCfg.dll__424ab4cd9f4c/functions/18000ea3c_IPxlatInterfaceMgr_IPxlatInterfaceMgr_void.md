# IPxlatInterfaceMgr::IPxlatInterfaceMgr(void *)

- ea: `0x18000ea3c`
- end: `0x18000ed10`
- name: `??0IPxlatInterfaceMgr@@QEAA@PEAX@Z`
- size: `724`
- prototype: `IPxlatInterfaceMgr *__fastcall(IPxlatInterfaceMgr *__hidden this, void *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ba4c`

## callees

- `0x180001d40`
- `0x18000214c`
- `0x180002a34`
- `0x18000b12c`
- `0x18000c224`
- `0x18000dc28`
- `0x18000ea3c`
- `0x18000f184`
- `0x18000f4f8`
- `0x18000fdf0`
- `0x18001088c`
- `0x180010e6c`
- `0x180011134`
- `0x180011dc0`
- `0x180012290`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec79`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000eb0b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000eb0b`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000eaee`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18000eaee`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000eab0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000eab0`

## string_xrefs

- `0x18000ec53`: `CreateWaitableTimer failed`
- `0x18000ec89`: `CreateEvent failed for no interface event`
- `0x18000ec1e`: `Invalid Configuration. Settings`
- `0x18000ebff`: `Reading Registry Configuration Failed`
- `0x18000eb60`: `Interface manager created successfully`

## pseudocode

```c
IPxlatInterfaceMgr *__fastcall IPxlatInterfaceMgr::IPxlatInterfaceMgr(IPxlatInterfaceMgr *this, void *a2)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  HANDLE WaitableTimer; // rax
  HANDLE EventW; // rax
  int v8; // ebx
  __int64 v9; // rcx
  int v10; // ebx
  __int64 v11; // r8
  int Configuration; // ebx
  const struct std::error_category *v14; // rax
  const struct std::error_category *v15; // rax
  int v16; // edx
  const struct std::error_category *v17; // rax
  int v18; // edx
  const struct std::error_category *v19; // rax
  const struct std::error_category *v20; // rax
  _BYTE pExceptionObject[16]; // [rsp+40h] [rbp-38h] BYREF
  const char *v22; // [rsp+50h] [rbp-28h]
  __int64 v23; // [rsp+58h] [rbp-20h]

  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 15) = 0;
  v4 = (_QWORD *)((char *)this + 128);
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  v5 = operator new(0x30u);
  *v5 = v5;
  v5[1] = v5;
  v5[2] = v5;
  *((_WORD *)v5 + 12) = 257;
  *v4 = v5;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  *((_DWORD *)this + 1) = 1;
  *((_QWORD *)this + 4) = a2;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  IPxlatInterfaceMgr::GetSyntheticIPv4Range(this);
  IPxlatInterfaceMgr::ResetWinNatState(this);
  WaitableTimer = CreateWaitableTimerExW(0, 0, 0, 0x1F0003u);
  *((_QWORD *)this + 6) = WaitableTimer;
  if ( !WaitableTimer )
  {
    IPxlatInterfaceMgr::Cleanup(this);
    GetLastError();
    v15 = std::system_category();
    std::system_error::system_error((std::system_error *)pExceptionObject, v16, v15, "CreateWaitableTimer failed");
    throw (std::system_error *)pExceptionObject;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 5) = EventW;
  if ( !EventW )
  {
    IPxlatInterfaceMgr::Cleanup(this);
    GetLastError();
    v17 = std::system_category();
    std::system_error::system_error(
      (std::system_error *)pExceptionObject,
      v18,
      v17,
      "CreateEvent failed for no interface event");
    throw (std::system_error *)pExceptionObject;
  }
  v8 = IPxlatInterfaceMgr::EnableNsiNotifications(this);
  if ( v8 )
  {
    IPxlatInterfaceMgr::Cleanup(this);
    v19 = std::system_category();
    std::system_error::system_error(
      (std::system_error *)pExceptionObject,
      v8,
      v19,
      "Could not register for Nsi notifications");
    throw (std::system_error *)pExceptionObject;
  }
  *(_BYTE *)this = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetImpl'::`2'::impl) )
  {
    v10 = IPxlatPolicyMgrInitialize();
    if ( v10 )
    {
      IPxlatInterfaceMgr::Cleanup(this);
      v20 = std::system_category();
      std::system_error::system_error(
        (std::system_error *)pExceptionObject,
        v10,
        v20,
        "Initializing IPxlat policy manager failed");
      throw (std::system_error *)pExceptionObject;
    }
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc>::GetImpl'::`2'::impl) )
  {
    *((_DWORD *)this + 36) = 0;
    *((_DWORD *)this + 37) = 1;
    *((_QWORD *)this + 19) = 1;
    Configuration = IPxlatInterfaceMgr::ReadConfiguration(this);
    if ( Configuration )
    {
      IPxlatInterfaceMgr::Cleanup(this);
      v14 = std::system_category();
      if ( Configuration != 87 )
      {
        std::system_error::system_error(
          (std::system_error *)pExceptionObject,
          Configuration,
          v14,
          "Reading Registry Configuration Failed");
        throw (std::system_error *)pExceptionObject;
      }
      std::system_error::system_error((std::system_error *)pExceptionObject, 87, v14, "Invalid Configuration. Settings");
      throw (std::system_error *)pExceptionObject;
    }
  }
  if ( (Microsoft_Windows_IPxlatCfgEnableBits & 2) != 0 )
  {
    v22 = "Interface manager created successfully";
    v23 = 39;
    McGenEventWrite_EventWriteTransfer(v9, IPXLATCFG_INFO_EVENT, v11, 2, pExceptionObject);
  }
  return this;
}

```

## disassembly

```asm
0x18000ea3c  push    rbp
0x18000ea3e  push    rbx
0x18000ea3f  push    rsi
0x18000ea40  push    rdi
0x18000ea41  mov     rbp, rsp
0x18000ea44  sub     rsp, 78h
0x18000ea48  mov     rax, cs:__security_cookie
0x18000ea4f  xor     rax, rsp
0x18000ea52  mov     [rbp+var_10], rax
0x18000ea56  mov     rdi, rdx
0x18000ea59  mov     rsi, rcx
0x18000ea5c  mov     [rbp+var_48], rcx
0x18000ea60  mov     qword ptr [rcx+68h], 0
0x18000ea68  mov     qword ptr [rcx+70h], 0
0x18000ea70  mov     qword ptr [rcx+78h], 0
0x18000ea78  lea     rbx, [rcx+80h]
0x18000ea7f  mov     qword ptr [rbx], 0
0x18000ea86  mov     qword ptr [rbx+8], 0
0x18000ea8e  mov     ecx, 30h ; '0'; Size
0x18000ea93  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ea98  mov     [rax], rax
0x18000ea9b  mov     [rax+8], rax
0x18000ea9f  mov     [rax+10h], rax
0x18000eaa3  mov     word ptr [rax+18h], 101h
0x18000eaa9  mov     [rbx], rax
0x18000eaac  lea     rcx, [rsi+38h]; lpCriticalSection
0x18000eab0  call    cs:__imp_InitializeCriticalSection
0x18000eab6  mov     dword ptr [rsi+4], 1
0x18000eabd  mov     [rsi+20h], rdi
0x18000eac1  mov     qword ptr [rsi+10h], 0
0x18000eac9  mov     qword ptr [rsi+18h], 0
0x18000ead1  mov     rcx, rsi; this
0x18000ead4  call    ?GetSyntheticIPv4Range@IPxlatInterfaceMgr@@AEAAXXZ; IPxlatInterfaceMgr::GetSyntheticIPv4Range(void)
0x18000ead9  mov     rcx, rsi; this
0x18000eadc  call    ?ResetWinNatState@IPxlatInterfaceMgr@@AEAAXXZ; IPxlatInterfaceMgr::ResetWinNatState(void)
0x18000eae1  mov     r9d, 1F0003h; dwDesiredAccess
0x18000eae7  xor     r8d, r8d; dwFlags
0x18000eaea  xor     edx, edx; lpTimerName
0x18000eaec  xor     ecx, ecx; lpTimerAttributes
0x18000eaee  call    cs:__imp_CreateWaitableTimerExW
0x18000eaf4  mov     [rsi+30h], rax
0x18000eaf8  test    rax, rax
0x18000eafb  jz      loc_18000EC3B
0x18000eb01  xor     r9d, r9d; lpName
0x18000eb04  xor     r8d, r8d; bInitialState
0x18000eb07  xor     edx, edx; bManualReset
0x18000eb09  xor     ecx, ecx; lpEventAttributes
0x18000eb0b  call    cs:__imp_CreateEventW
0x18000eb11  mov     [rsi+28h], rax
0x18000eb15  mov     rcx, rsi; this
0x18000eb18  test    rax, rax
0x18000eb1b  jz      loc_18000EC74
0x18000eb21  call    ?EnableNsiNotifications@IPxlatInterfaceMgr@@AEAAKXZ; IPxlatInterfaceMgr::EnableNsiNotifications(void)
0x18000eb26  mov     ebx, eax
0x18000eb28  test    eax, eax
0x18000eb2a  jnz     loc_18000ECAA
0x18000eb30  mov     [rsi], al
0x18000eb32  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::GetImpl(void)'::`2'::impl
0x18000eb39  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_GPO@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_GPO>::__private_IsEnabled(void)
0x18000eb3e  test    al, al
0x18000eb40  jz      short loc_18000EBA1
0x18000eb42  call    IPxlatPolicyMgrInitialize
0x18000eb47  mov     ebx, eax
0x18000eb49  test    eax, eax
0x18000eb4b  jnz     loc_18000ECDD
0x18000eb51  mov     r9d, 2
0x18000eb57  test    byte ptr cs:Microsoft_Windows_IPxlatCfgEnableBits, r9b
0x18000eb5e  jz      short loc_18000EB89
0x18000eb60  lea     rax, aInterfaceManag; "Interface manager created successfully"
0x18000eb67  mov     [rbp+var_28], rax
0x18000eb6b  mov     [rbp+var_20], 27h ; '''
0x18000eb73  lea     rax, [rbp+pExceptionObject]
0x18000eb77  mov     [rsp+78h+var_58], rax
0x18000eb7c  lea     rdx, IPXLATCFG_INFO_EVENT
0x18000eb83  call    McGenEventWrite_EventWriteTransfer
0x18000eb88  nop
0x18000eb89  mov     rax, rsi
0x18000eb8c  mov     rcx, [rbp+var_10]
0x18000eb90  xor     rcx, rsp; StackCookie
0x18000eb93  call    __security_check_cookie
0x18000eb98  add     rsp, 78h
0x18000eb9c  pop     rdi
0x18000eb9d  pop     rsi
0x18000eb9e  pop     rbx
0x18000eb9f  pop     rbp
0x18000eba0  retn
0x18000eba1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc> `wil::Feature<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc>::GetImpl(void)'::`2'::impl
0x18000eba8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_IPXlatCfgSvc>::__private_IsEnabled(void)
0x18000ebad  test    al, al
0x18000ebaf  jz      short loc_18000EB51
0x18000ebb1  mov     dword ptr [rsi+90h], 0
0x18000ebbb  mov     dword ptr [rsi+94h], 1
0x18000ebc5  mov     qword ptr [rsi+98h], 1
0x18000ebd0  mov     rcx, rsi; this
0x18000ebd3  call    ?ReadConfiguration@IPxlatInterfaceMgr@@AEAAKXZ; IPxlatInterfaceMgr::ReadConfiguration(void)
0x18000ebd8  mov     ebx, eax
0x18000ebda  test    eax, eax
0x18000ebdc  jz      loc_18000EB51
0x18000ebe2  mov     rcx, rsi; this
0x18000ebe5  call    ?Cleanup@IPxlatInterfaceMgr@@AEAAXXZ; IPxlatInterfaceMgr::Cleanup(void)
0x18000ebea  call    ?system_category@std@@YAAEBVerror_category@1@XZ; std::system_category(void)
0x18000ebef  mov     edx, 57h ; 'W'; int
0x18000ebf4  mov     r8, rax; struct std::error_category *
0x18000ebf7  lea     rcx, [rbp+pExceptionObject]; this
0x18000ebfb  cmp     ebx, edx
0x18000ebfd  jz      short loc_18000EC1E
0x18000ebff  lea     r9, aReadingRegistr; "Reading Registry Configuration Failed"
0x18000ec06  mov     edx, ebx; int
0x18000ec08  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x18000ec0d  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18000ec14  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ec18  call    _CxxThrowException_0
0x18000ec1e  lea     r9, aInvalidConfigu; "Invalid Configuration. Settings"
0x18000ec25  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x18000ec2a  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18000ec31  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ec35  call    _CxxThrowException_0
0x18000ec3b  mov     rcx, rsi; this
0x18000ec3e  call    ?Cleanup@IPxlatInterfaceMgr@@AEAAXXZ; IPxlatInterfaceMgr::Cleanup(void)
0x18000ec43  call    cs:__imp_GetLastError
0x18000ec49  mov     edx, eax
0x18000ec4b  call    ?system_category@std@@YAAEBVerror_category@1@XZ; std::system_category(void)
0x18000ec50  mov     r8, rax; struct std::error_category *
0x18000ec53  lea     r9, aCreatewaitable_0; "CreateWaitableTimer failed"
0x18000ec5a  lea     rcx, [rbp+pExceptionObject]; this
0x18000ec5e  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x18000ec63  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18000ec6a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ec6e  call    _CxxThrowException_0
0x18000ec74  call    ?Cleanup@IPxlatInterfaceMgr@@AEAAXXZ; IPxlatInterfaceMgr::Cleanup(void)
0x18000ec79  call    cs:__imp_GetLastError
0x18000ec7f  mov     edx, eax
0x18000ec81  call    ?system_category@std@@YAAEBVerror_category@1@XZ; std::system_category(void)
0x18000ec86  mov     r8, rax; struct std::error_category *
0x18000ec89  lea     r9, aCreateeventFai_1; "CreateEvent failed for no interface eve"...
0x18000ec90  lea     rcx, [rbp+pExceptionObject]; this
0x18000ec94  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x18000ec99  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18000eca0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000eca4  call    _CxxThrowException_0
0x18000ecaa  mov     rcx, rsi; this
0x18000ecad  call    ?Cleanup@IPxlatInterfaceMgr@@AEAAXXZ; IPxlatInterfaceMgr::Cleanup(void)
0x18000ecb2  call    ?system_category@std@@YAAEBVerror_category@1@XZ; std::system_category(void)
0x18000ecb7  mov     r8, rax; struct std::error_category *
0x18000ecba  lea     r9, aCouldNotRegist; "Could not register for Nsi notification"...
0x18000ecc1  mov     edx, ebx; int
0x18000ecc3  lea     rcx, [rbp+pExceptionObject]; this
0x18000ecc7  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x18000eccc  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18000ecd3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ecd7  call    _CxxThrowException_0
0x18000ecdd  mov     rcx, rsi; this
0x18000ece0  call    ?Cleanup@IPxlatInterfaceMgr@@AEAAXXZ; IPxlatInterfaceMgr::Cleanup(void)
0x18000ece5  call    ?system_category@std@@YAAEBVerror_category@1@XZ; std::system_category(void)
0x18000ecea  mov     r8, rax; struct std::error_category *
0x18000eced  lea     r9, aInitializingIp; "Initializing IPxlat policy manager fail"...
0x18000ecf4  mov     edx, ebx; int
0x18000ecf6  lea     rcx, [rbp+pExceptionObject]; this
0x18000ecfa  call    ??0system_error@std@@QEAA@HAEBVerror_category@1@PEBD@Z; std::system_error::system_error(int,std::error_category const &,char const *)
0x18000ecff  lea     rdx, _TI4?AVsystem_error@std@@; pThrowInfo
0x18000ed06  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ed0a  call    _CxxThrowException_0
```
