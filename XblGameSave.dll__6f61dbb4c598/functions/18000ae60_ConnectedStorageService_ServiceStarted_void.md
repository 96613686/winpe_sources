# ConnectedStorageService::ServiceStarted(void)

- ea: `0x18000ae60`
- end: `0x18000b084`
- name: `?ServiceStarted@ConnectedStorageService@@QEAAJXZ`
- size: `548`
- prototype: `__int64 __fastcall(ConnectedStorageService *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000846c`

## callees

- `0x18000315c`
- `0x180003c70`
- `0x180005fe0`
- `0x180005ff0`
- `0x180006018`
- `0x18000a040`
- `0x18000aae4`
- `0x18000ae60`
- `0x18000c9c0`
- `0x18000ca18`
- `0x18000cd40`
- `0x180013fd0`
- `0x180015f7c`
- `0x180016d28`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000af6b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000af6b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000af26`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000af26`

## string_xrefs

- `0x18000af75`: `CoCreateInstance(CLSID_GlobalOptions, nullptr, CLSCTX_INPROC_SERVER, IID_PPV_ARGS(&globalOptions))`
- `0x18000afa1`: `globalOptions->Set(COMGLB_UNMARSHALING_POLICY, COMGLB_UNMARSHALING_POLICY_STRONG)`
- `0x18000affb`: `ConnectedStorage::Service::Create( [this](HRESULT initHr) { OnServiceCreateComplete(initHr); }, [this]() { OnServiceIdleShutdown(); })`
- `0x18000aec8`: `System\CurrentControlSet\Services\XblGameSave\Parameters`

## pseudocode

```c
__int64 __fastcall ConnectedStorageService::ServiceStarted(ConnectedStorageService *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  HRESULT Instance; // eax
  const unsigned __int16 *v5; // r8
  int v6; // eax
  const unsigned __int16 *v7; // r8
  _lambda_249230bd792972bce8c42ec595a35649_ *v8; // rax
  _lambda_249230bd792972bce8c42ec595a35649_ *v9; // rax
  __int64 v10; // rax
  __int64 v11; // r8
  int v12; // eax
  const unsigned __int16 *v13; // r8
  __int64 v14; // rcx
  DWORD v15; // ebx
  DWORD pcbData; // [rsp+40h] [rbp-108h] BYREF
  DWORD pdwType[2]; // [rsp+48h] [rbp-100h] BYREF
  int pvData; // [rsp+50h] [rbp-F8h] BYREF
  _BYTE v20[64]; // [rsp+58h] [rbp-F0h] BYREF
  _BYTE v21[72]; // [rsp+98h] [rbp-B0h] BYREF
  _DWORD v22[16]; // [rsp+E0h] [rbp-68h] BYREF
  HKEY hkey[2]; // [rsp+120h] [rbp-28h] BYREF

  ConnectedStorage::NtmProvider::Start((ConnectedStorageService *)((char *)this + 56));
  if ( (ConnectedStorageEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v3, ConnectedStorageServiceStarted);
  if ( byte_1800C09B8 || (int)TraceLoggingRegisterEx_EventRegister_EventSetInformation(v3) >= 0 )
    byte_1800C09B8 = 1;
  ConnectedStorage::TryOpenRegistryKey(hkey, v2, L"System\\CurrentControlSet\\Services\\XblGameSave\\Parameters");
  pvData = 0;
  pdwType[0] = 4;
  pcbData = 4;
  RegGetValueW(hkey[0], 0, L"LoggingSetting", 0x10u, pdwType, &pvData, &pcbData);
  ConnectedStorage::HKey::Release((ConnectedStorage::HKey *)hkey);
  *(_QWORD *)pdwType = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(pdwType);
  Instance = CoCreateInstance(
               &CLSID_GlobalOptions,
               0,
               1u,
               &GUID_0000015b_0000_0000_c000_000000000046,
               (LPVOID *)pdwType);
  try
  {
    if ( Instance < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)Instance,
        (int)L"CoCreateInstance(CLSID_GlobalOptions, nullptr, CLSCTX_INPROC_SERVER, IID_PPV_ARGS(&globalOptions))",
        v5);
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)pdwType + 24LL))(*(_QWORD *)pdwType, 5, 1);
    if ( v6 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v6,
        (int)L"globalOptions->Set(COMGLB_UNMARSHALING_POLICY, COMGLB_UNMARSHALING_POLICY_STRONG)",
        v7);
    v8 = _lambda_249230bd792972bce8c42ec595a35649_::_lambda_249230bd792972bce8c42ec595a35649_(
           (_lambda_249230bd792972bce8c42ec595a35649_ *)hkey,
           this);
    std::function<void (void)>::function<void (void)>(v20, v8);
    v9 = _lambda_249230bd792972bce8c42ec595a35649_::_lambda_249230bd792972bce8c42ec595a35649_(
           (_lambda_249230bd792972bce8c42ec595a35649_ *)&pcbData,
           this);
    v10 = std::function<void (long)>::function<void (long)>(v21, v9);
    v12 = ConnectedStorage::Service::Create(v10, v11);
    if ( v12 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v12,
        (int)L"ConnectedStorage::Service::Create( [this](HRESULT initHr) { OnServiceCreateComplete(initHr); }, [this]() { "
              "OnServiceIdleShutdown(); })",
        v13);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(pdwType);
  }
  catch ( ConnectedStorage::ComError v22 )
  {
    pcbData = v22[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v22);
    v15 = pcbData;
    if ( (pcbData & 0x80000000) == 0 )
      goto LABEL_15;
LABEL_18:
    if ( (ConnectedStorageEnableBits & 2) != 0 )
      McTemplateU0d_EventWriteTransfer(v14, ConnectedStorageServiceCreateFailed, v15);
    return v15;
  }
  catch ( std::bad_alloc )
  {
    pcbData = -2147024882;
    v15 = -2147024882;
    goto LABEL_18;
  }
  catch ( ... )
  {
    pcbData = -2147467259;
    v15 = -2147467259;
    goto LABEL_18;
  }
LABEL_15:
  if ( (ConnectedStorageEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v14, ConnectedStorageServiceCreated);
  return 0;
}

```

## disassembly

```asm
0x18000ae60  push    rbx
0x18000ae62  sub     rsp, 140h
0x18000ae69  mov     rax, cs:__security_cookie
0x18000ae70  xor     rax, rsp
0x18000ae73  mov     [rsp+148h+var_18], rax
0x18000ae7b  mov     rbx, rcx
0x18000ae7e  add     rcx, 38h ; '8'; this
0x18000ae82  call    ?Start@NtmProvider@ConnectedStorage@@QEAAJXZ; ConnectedStorage::NtmProvider::Start(void)
0x18000ae87  test    cs:ConnectedStorageEnableBits, 1
0x18000ae8e  jz      short loc_18000AEAF
0x18000ae90  lea     rax, [rsp+148h+hkey]
0x18000ae98  mov     [rsp+148h+pdwType], rax
0x18000ae9d  mov     r9d, 1
0x18000aea3  lea     rdx, ConnectedStorageServiceStarted
0x18000aeaa  call    McGenEventWrite_EventWriteTransfer
0x18000aeaf  cmp     cs:byte_1800C09B8, 0
0x18000aeb6  jnz     short loc_18000AEC1
0x18000aeb8  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000aebd  test    eax, eax
0x18000aebf  js      short loc_18000AEC8
0x18000aec1  mov     cs:byte_1800C09B8, 1
0x18000aec8  lea     r8, SubKey; "System\\CurrentControlSet\\Services\\Xb"...
0x18000aecf  lea     rcx, [rsp+148h+hkey]
0x18000aed7  call    ?TryOpenRegistryKey@ConnectedStorage@@YA?AVHKey@1@PEAUHKEY__@@PEBG@Z; ConnectedStorage::TryOpenRegistryKey(HKEY__ *,ushort const *)
0x18000aedc  mov     [rsp+148h+var_F8], 0
0x18000aee4  mov     eax, 4
0x18000aee9  mov     [rsp+148h+var_100], eax
0x18000aeed  mov     [rsp+148h+var_108], eax
0x18000aef1  lea     rax, [rsp+148h+var_108]
0x18000aef6  mov     [rsp+148h+pcbData], rax; pcbData
0x18000aefb  lea     rax, [rsp+148h+var_F8]
0x18000af00  mov     [rsp+148h+pvData], rax; pvData
0x18000af05  lea     rax, [rsp+148h+var_100]
0x18000af0a  mov     [rsp+148h+pdwType], rax; pdwType
0x18000af0f  mov     r9d, 10h; dwFlags
0x18000af15  lea     r8, Value; "LoggingSetting"
0x18000af1c  xor     edx, edx; lpSubKey
0x18000af1e  mov     rcx, [rsp+148h+hkey]; hkey
0x18000af26  call    cs:__imp_RegGetValueW
0x18000af2c  lea     rcx, [rsp+148h+hkey]; this
0x18000af34  call    ?Release@HKey@ConnectedStorage@@QEAAXXZ; ConnectedStorage::HKey::Release(void)
0x18000af39  nop
0x18000af3a  mov     qword ptr [rsp+148h+var_100], 0
0x18000af43  lea     rcx, [rsp+148h+var_100]
0x18000af48  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000af4d  lea     rax, [rsp+148h+var_100]
0x18000af52  mov     [rsp+148h+pdwType], rax; ppv
0x18000af57  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x18000af5e  xor     edx, edx; pUnkOuter
0x18000af60  lea     r8d, [rdx+1]; dwClsContext
0x18000af64  lea     rcx, CLSID_GlobalOptions; rclsid
0x18000af6b  call    cs:__imp_CoCreateInstance
0x18000af71  test    eax, eax
0x18000af73  jns     short loc_18000AF83
0x18000af75  lea     rdx, aCocreateinstan; "CoCreateInstance(CLSID_GlobalOptions, n"...
0x18000af7c  mov     ecx, eax; this
0x18000af7e  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18000af83  mov     rcx, qword ptr [rsp+148h+var_100]
0x18000af88  mov     rax, [rcx]
0x18000af8b  mov     edx, 5
0x18000af90  lea     r8d, [rdx-4]
0x18000af94  mov     rax, [rax+18h]
0x18000af98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af9d  test    eax, eax
0x18000af9f  jns     short loc_18000AFAF
0x18000afa1  lea     rdx, aGlobaloptionsS; "globalOptions->Set(COMGLB_UNMARSHALING_"...
0x18000afa8  mov     ecx, eax; this
0x18000afaa  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18000afaf  mov     rdx, rbx; struct ConnectedStorageService *
0x18000afb2  lea     rcx, [rsp+148h+hkey]; this
0x18000afba  call    ??0_lambda_249230bd792972bce8c42ec595a35649_@@QEAA@PEAVConnectedStorageService@@@Z; _lambda_249230bd792972bce8c42ec595a35649_::_lambda_249230bd792972bce8c42ec595a35649_(ConnectedStorageService *)
0x18000afbf  mov     rdx, rax
0x18000afc2  lea     rcx, [rsp+148h+var_F0]
0x18000afc7  call    ??$?0V_lambda_34a36cab29ee6cb97c555bb9c037bb23_@@$0A@@?$function@$$A6AXXZ@std@@QEAA@$$QEAV_lambda_34a36cab29ee6cb97c555bb9c037bb23_@@@Z; std::function<void (void)>::function<void (void)>(_lambda_34a36cab29ee6cb97c555bb9c037bb23_ &&)
0x18000afcc  mov     r8, rax
0x18000afcf  mov     rdx, rbx; struct ConnectedStorageService *
0x18000afd2  lea     rcx, [rsp+148h+var_108]; this
0x18000afd7  call    ??0_lambda_249230bd792972bce8c42ec595a35649_@@QEAA@PEAVConnectedStorageService@@@Z; _lambda_249230bd792972bce8c42ec595a35649_::_lambda_249230bd792972bce8c42ec595a35649_(ConnectedStorageService *)
0x18000afdc  mov     rdx, rax
0x18000afdf  lea     rcx, [rsp+148h+var_B0]
0x18000afe7  call    ??$?0V_lambda_249230bd792972bce8c42ec595a35649_@@$0A@@?$function@$$A6AXJ@Z@std@@QEAA@$$QEAV_lambda_249230bd792972bce8c42ec595a35649_@@@Z; std::function<void (long)>::function<void (long)>(_lambda_249230bd792972bce8c42ec595a35649_ &&)
0x18000afec  mov     rdx, r8
0x18000afef  mov     rcx, rax
0x18000aff2  call    ?Create@Service@ConnectedStorage@@SAJV?$function@$$A6AXJ@Z@std@@V?$function@$$A6AXXZ@4@@Z; ConnectedStorage::Service::Create(std::function<void (long)>,std::function<void (void)>)
0x18000aff7  test    eax, eax
0x18000aff9  jns     short loc_18000B00A
0x18000affb  lea     rdx, aConnectedstora_16; "ConnectedStorage::Service::Create( [thi"...
0x18000b002  mov     ecx, eax; this
0x18000b004  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18000b00a  lea     rcx, [rsp+148h+var_100]
0x18000b00f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000b014  nop
0x18000b015  jmp     short loc_18000B01F
0x18000b017  mov     ebx, [rsp+148h+var_108]
0x18000b01b  test    ebx, ebx
0x18000b01d  js      short loc_18000B051
0x18000b01f  test    cs:ConnectedStorageEnableBits, 1
0x18000b026  jz      short loc_18000B047
0x18000b028  lea     rax, [rsp+148h+hkey]
0x18000b030  mov     [rsp+148h+pdwType], rax
0x18000b035  mov     r9d, 1
0x18000b03b  lea     rdx, ConnectedStorageServiceCreated
0x18000b042  call    McGenEventWrite_EventWriteTransfer
0x18000b047  xor     eax, eax
0x18000b049  jmp     short loc_18000B06B
0x18000b04b  jmp     short $+2
0x18000b04d  mov     ebx, [rsp+148h+var_108]
0x18000b051  test    cs:ConnectedStorageEnableBits, 2
0x18000b058  jz      short loc_18000B069
0x18000b05a  mov     r8d, ebx
0x18000b05d  lea     rdx, ConnectedStorageServiceCreateFailed
0x18000b064  call    McTemplateU0d_EventWriteTransfer
0x18000b069  mov     eax, ebx
0x18000b06b  mov     rcx, [rsp+148h+var_18]
0x18000b073  xor     rcx, rsp; StackCookie
0x18000b076  call    __security_check_cookie
0x18000b07b  add     rsp, 140h
0x18000b082  pop     rbx
0x18000b083  retn
```
