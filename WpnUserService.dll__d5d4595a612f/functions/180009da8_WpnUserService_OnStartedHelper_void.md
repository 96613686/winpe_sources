# WpnUserService::OnStartedHelper(void)

- ea: `0x180009da8`
- end: `0x18000a160`
- name: `?OnStartedHelper@WpnUserService@@AEAAJXZ`
- size: `952`
- prototype: `__int64 __fastcall(WpnUserService *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009d40`

## callees

- `0x180001008`
- `0x180006244`
- `0x180009b58`
- `0x180009da8`
- `0x18000a648`
- `0x18000bee8`
- `0x18000e51c`
- `0x180012010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180009dde`
- `ntdll!RtlPublishWnfStateData` at `0x180009e2f`
- `ntdll!RtlPublishWnfStateData` at `0x180009dde`
- `ntdll!RtlPublishWnfStateData` at `0x180009e2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a063`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a063`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a0ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a0ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a097`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a097`
- `combase!__imp_CoCreateInstanceAsUser` at `0x180009ef3`
- `combase!__imp_CoCreateInstanceAsUser` at `0x180009ef3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180009e8b`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180009e8b`

## string_xrefs

- `0x180009e08`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`
- `0x180009f12`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`
- `0x180009fad`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`
- `0x18000a00d`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`
- `0x18000a126`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`
- `0x180009f03`: `Failed CoCreateInstanceAsUser CWindowsPushNotificationPlatform`
- `0x180009e9c`: `onecoreuap\base\diagnosis\platform\notifications\common\wpnusermgrutil.cpp`

## pseudocode

```c
__int64 __fastcall WpnUserService::OnStartedHelper(WpnUserService *this)
{
  char *v2; // r14
  int v3; // eax
  int started; // esi
  __int64 v5; // rdx
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  char *v10; // rcx
  int InstanceAsUser; // esi
  char *v12; // rcx
  unsigned int v13; // eax
  int v14; // eax
  unsigned int v15; // edi
  __int64 v16; // rcx
  unsigned int v17; // eax
  int v18; // eax
  __int64 v19; // rcx
  bool v20; // di
  const struct _tlgProvider_t *v21; // rax
  __int64 v22; // rdx
  int v23; // r9d
  unsigned int v24; // eax
  __int64 v25; // rcx
  GUID *phkResult; // [rsp+20h] [rbp-20h]
  const char *lpcbData; // [rsp+28h] [rbp-18h]
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  char *Data; // [rsp+70h] [rbp+30h] BYREF
  int v31; // [rsp+78h] [rbp+38h] BYREF
  __int64 cbData; // [rsp+80h] [rbp+40h] BYREF
  __int64 v33; // [rsp+88h] [rbp+48h] BYREF

  v31 = 1;
  v2 = (char *)this + 8;
  LODWORD(phkResult) = 0;
  v3 = RtlPublishWnfStateData(WNF_WPN_USER_PLATFORM_READY, 0, &v31, 4);
  started = LogIfStartSrvFailedAndReturnHr(v3 | 0x10000000u, v2, 17);
  if ( started < 0 )
  {
    v5 = 156;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
      (const char *)(unsigned int)started,
      (int)phkResult);
    return (unsigned int)started;
  }
  LODWORD(phkResult) = 0;
  v7 = RtlPublishWnfStateData(WNF_WPN_USER_IN_SESSION_PLATFORM_READY, 0, 0, 0);
  started = LogIfStartSrvFailedAndReturnHr(v7 | 0x10000000u, v2, 18);
  if ( started < 0 )
  {
    v5 = 165;
    goto LABEL_3;
  }
  v8 = *((_QWORD *)this + 28);
  if ( v8 )
  {
    *((_QWORD *)this + 28) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  *((_QWORD *)this + 28) = 0;
  Data = 0;
  cbData = 0;
  v9 = UMgrQueryUserContext(0, &cbData);
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\common\\wpnusermgrutil.cpp",
      (const char *)(unsigned int)v9,
      0);
    cbData = 0;
  }
  v10 = Data;
  if ( Data )
  {
    Data = 0;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  lpcbData = (const char *)&Data;
  phkResult = &GUID_df8e9480_ca73_448e_b8f0_da000f581428;
  InstanceAsUser = CoCreateInstanceAsUser(&GUID_0c9281f9_6da1_4006_8729_de6e6b61581c, 0, 1028, cbData);
  if ( InstanceAsUser >= 0 )
  {
    *((_QWORD *)this + 28) = Data;
    InstanceAsUser = 0;
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1D5,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
      (const char *)(unsigned int)InstanceAsUser,
      (int)"Failed CoCreateInstanceAsUser CWindowsPushNotificationPlatform",
      (const char *)&Data);
    v12 = Data;
    if ( Data )
    {
      Data = 0;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  started = LogIfStartSrvFailedAndReturnHr((unsigned int)InstanceAsUser, v2, 19);
  if ( started < 0 )
  {
    v5 = 169;
    goto LABEL_3;
  }
  v33 = 0;
  v13 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 28))(
          *((_QWORD *)this + 28),
          &GUID_6d8eaf9b_de6c_480d_82b5_d46c3aa90d12,
          &v33);
  v14 = LogIfStartSrvFailedAndReturnHr(v13, v2, 20);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
      (const char *)(unsigned int)v14,
      (int)phkResult);
    v16 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v15;
  }
  v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 32LL))(v33);
  v18 = LogIfStartSrvFailedAndReturnHr(v17, v2, 21);
  v15 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
      (const char *)(unsigned int)v18,
      (int)phkResult);
    v19 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return v15;
  }
  LODWORD(Data) = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
          0,
          0x20019u,
          &hKey) )
  {
    LODWORD(cbData) = 4;
    RegQueryValueExW(hKey, L"InitializePlatformOnStartup", 0, 0, (LPBYTE)&Data, (LPDWORD)&cbData);
  }
  v20 = (_DWORD)Data == 1;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v20 )
  {
    v21 = ServiceHostLogging::Provider();
    if ( *(_DWORD *)v21 > 5u )
    {
      v22 = *((_QWORD *)v21 + 3);
      if ( (*((_QWORD *)v21 + 2) & 0x400000000000LL) != 0 && (v22 & 0x400000000000LL) == v22 )
      {
        Data = v2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (_DWORD)v21,
          (unsigned int)byte_180014ABB,
          0,
          v23,
          (__int64)&Data);
      }
    }
    v24 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v33 + 24LL))(v33, v22);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp",
      (const char *)v24,
      (int)"Failed wpnPlatformInternal InitializePlatform",
      lpcbData);
  }
  v25 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  return 0;
}

```

## disassembly

```asm
0x180009da8  push    rbp
0x180009daa  push    rsi
0x180009dab  push    rdi
0x180009dac  push    r14
0x180009dae  push    r15
0x180009db0  mov     rbp, rsp
0x180009db3  sub     rsp, 40h
0x180009db7  mov     rdi, rcx
0x180009dba  mov     [rbp+arg_8], 1
0x180009dc1  lea     r14, [rcx+8]
0x180009dc5  xor     r15d, r15d
0x180009dc8  mov     [rsp+40h+phkResult], r15; int
0x180009dcd  lea     r9d, [r15+4]
0x180009dd1  lea     r8, [rbp+arg_8]
0x180009dd5  xor     edx, edx
0x180009dd7  mov     rcx, cs:WNF_WPN_USER_PLATFORM_READY
0x180009dde  call    cs:__imp_RtlPublishWnfStateData
0x180009de4  bts     eax, 1Ch
0x180009de8  lea     r8d, [r15+11h]
0x180009dec  mov     rdx, r14
0x180009def  mov     ecx, eax
0x180009df1  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x180009df6  mov     esi, eax
0x180009df8  test    eax, eax
0x180009dfa  jns     short loc_180009E1B
0x180009dfc  mov     edx, 9Ch; void *
0x180009e01  mov     rcx, [rbp+28h]; this
0x180009e05  mov     r9d, esi; char *
0x180009e08  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009e0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e14  mov     eax, esi
0x180009e16  jmp     loc_18000A154
0x180009e1b  mov     [rsp+40h+phkResult], r15; int
0x180009e20  xor     r9d, r9d
0x180009e23  xor     r8d, r8d
0x180009e26  xor     edx, edx
0x180009e28  mov     rcx, cs:WNF_WPN_USER_IN_SESSION_PLATFORM_READY
0x180009e2f  call    cs:__imp_RtlPublishWnfStateData
0x180009e35  bts     eax, 1Ch
0x180009e39  mov     r8d, 12h
0x180009e3f  mov     rdx, r14
0x180009e42  mov     ecx, eax
0x180009e44  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x180009e49  mov     esi, eax
0x180009e4b  test    eax, eax
0x180009e4d  jns     short loc_180009E56
0x180009e4f  mov     edx, 0A5h
0x180009e54  jmp     short loc_180009E01
0x180009e56  mov     rcx, [rdi+0E0h]
0x180009e5d  test    rcx, rcx
0x180009e60  jz      short loc_180009E76
0x180009e62  mov     [rdi+0E0h], r15
0x180009e69  mov     rax, [rcx]
0x180009e6c  mov     rax, [rax+10h]
0x180009e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e75  nop
0x180009e76  mov     [rdi+0E0h], r15
0x180009e7d  mov     [rbp+Data], r15
0x180009e81  mov     [rbp+cbData], r15
0x180009e85  lea     rdx, [rbp+cbData]
0x180009e89  xor     ecx, ecx
0x180009e8b  call    cs:__imp_UMgrQueryUserContext
0x180009e91  test    eax, eax
0x180009e93  jns     short loc_180009EB1
0x180009e95  mov     rcx, [rbp+28h]; this
0x180009e99  mov     r9d, eax; char *
0x180009e9c  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009ea3  mov     edx, 2Dh ; '-'; void *
0x180009ea8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ead  mov     [rbp+cbData], r15
0x180009eb1  mov     rcx, [rbp+Data]
0x180009eb5  test    rcx, rcx
0x180009eb8  jz      short loc_180009ECB
0x180009eba  mov     [rbp+Data], r15
0x180009ebe  mov     rax, [rcx]
0x180009ec1  mov     rax, [rax+10h]
0x180009ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eca  nop
0x180009ecb  lea     rax, [rbp+Data]
0x180009ecf  mov     [rsp+40h+lpcbData], rax; char *
0x180009ed4  lea     rax, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x180009edb  mov     [rsp+40h+phkResult], rax; int
0x180009ee0  mov     r9, [rbp+cbData]
0x180009ee4  xor     edx, edx
0x180009ee6  mov     r8d, 404h
0x180009eec  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c
0x180009ef3  call    cs:__imp_CoCreateInstanceAsUser
0x180009ef9  mov     esi, eax
0x180009efb  test    eax, eax
0x180009efd  jns     short loc_180009F40
0x180009eff  mov     rcx, [rbp+28h]; this
0x180009f03  lea     rax, aFailedCocreate; "Failed CoCreateInstanceAsUser CWindowsP"...
0x180009f0a  mov     [rsp+40h+phkResult], rax; int
0x180009f0f  mov     r9d, esi; char *
0x180009f12  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009f19  mov     edx, 1D5h; void *
0x180009f1e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180009f23  nop
0x180009f24  mov     rcx, [rbp+Data]
0x180009f28  test    rcx, rcx
0x180009f2b  jz      short loc_180009F3E
0x180009f2d  mov     [rbp+Data], r15
0x180009f31  mov     rax, [rcx]
0x180009f34  mov     rax, [rax+10h]
0x180009f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f3d  nop
0x180009f3e  jmp     short loc_180009F4E
0x180009f40  mov     rax, [rbp+Data]
0x180009f44  mov     [rdi+0E0h], rax
0x180009f4b  mov     esi, r15d
0x180009f4e  mov     r8d, 13h
0x180009f54  mov     rdx, r14
0x180009f57  mov     ecx, esi
0x180009f59  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x180009f5e  mov     esi, eax
0x180009f60  test    eax, eax
0x180009f62  jns     short loc_180009F6E
0x180009f64  mov     edx, 0A9h
0x180009f69  jmp     loc_180009E01
0x180009f6e  mov     [rbp+arg_18], r15
0x180009f72  mov     rcx, [rdi+0E0h]
0x180009f79  mov     rax, [rcx]
0x180009f7c  lea     r8, [rbp+arg_18]
0x180009f80  lea     rdx, _GUID_6d8eaf9b_de6c_480d_82b5_d46c3aa90d12
0x180009f87  mov     rax, [rax]
0x180009f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f8f  nop
0x180009f90  mov     r8d, 14h
0x180009f96  mov     rdx, r14
0x180009f99  mov     ecx, eax
0x180009f9b  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x180009fa0  mov     edi, eax
0x180009fa2  test    eax, eax
0x180009fa4  jns     short loc_180009FE0
0x180009fa6  mov     rcx, [rbp+28h]; this
0x180009faa  mov     r9d, eax; char *
0x180009fad  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180009fb4  mov     edx, 0ADh; void *
0x180009fb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009fbe  nop
0x180009fbf  mov     rcx, [rbp+arg_18]
0x180009fc3  test    rcx, rcx
0x180009fc6  jz      short loc_180009FD9
0x180009fc8  mov     [rbp+arg_18], r15
0x180009fcc  mov     rax, [rcx]
0x180009fcf  mov     rax, [rax+10h]
0x180009fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fd8  nop
0x180009fd9  mov     eax, edi
0x180009fdb  jmp     loc_18000A154
0x180009fe0  mov     rcx, [rbp+arg_18]
0x180009fe4  mov     rax, [rcx]
0x180009fe7  mov     rax, [rax+20h]
0x180009feb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ff0  mov     r8d, 15h
0x180009ff6  mov     rdx, r14
0x180009ff9  mov     ecx, eax
0x180009ffb  call    ?LogIfStartSrvFailedAndReturnHr@@YAJJPEBGW4StartServiceFailureReason@@@Z; LogIfStartSrvFailedAndReturnHr(long,ushort const *,StartServiceFailureReason)
0x18000a000  mov     edi, eax
0x18000a002  test    eax, eax
0x18000a004  jns     short loc_18000A03B
0x18000a006  mov     rcx, [rbp+28h]; this
0x18000a00a  mov     r9d, eax; char *
0x18000a00d  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000a014  mov     edx, 0B0h; void *
0x18000a019  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a01e  nop
0x18000a01f  mov     rcx, [rbp+arg_18]
0x18000a023  test    rcx, rcx
0x18000a026  jz      short loc_18000A039
0x18000a028  mov     [rbp+arg_18], r15
0x18000a02c  mov     rax, [rcx]
0x18000a02f  mov     rax, [rax+10h]
0x18000a033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a038  nop
0x18000a039  jmp     short loc_180009FD9
0x18000a03b  mov     dword ptr [rbp+Data], r15d
0x18000a03f  mov     [rbp+hKey], r15
0x18000a043  lea     rax, [rbp+hKey]
0x18000a047  mov     [rsp+40h+phkResult], rax; phkResult
0x18000a04c  mov     r9d, 20019h; samDesired
0x18000a052  xor     r8d, r8d; ulOptions
0x18000a055  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18000a05c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a063  call    cs:__imp_RegOpenKeyExW
0x18000a069  test    eax, eax
0x18000a06b  jnz     short loc_18000A09D
0x18000a06d  mov     dword ptr [rbp+cbData], 4
0x18000a074  lea     rax, [rbp+cbData]
0x18000a078  mov     [rsp+40h+lpcbData], rax; char *
0x18000a07d  lea     rax, [rbp+Data]
0x18000a081  mov     [rsp+40h+phkResult], rax; lpData
0x18000a086  xor     r9d, r9d; lpType
0x18000a089  xor     r8d, r8d; lpReserved
0x18000a08c  lea     rdx, ValueName; "InitializePlatformOnStartup"
0x18000a093  mov     rcx, [rbp+hKey]; hKey
0x18000a097  call    cs:__imp_RegQueryValueExW
0x18000a09d  cmp     dword ptr [rbp+Data], 1
0x18000a0a1  setz    dil
0x18000a0a5  mov     rcx, [rbp+hKey]; hKey
0x18000a0a9  test    rcx, rcx
0x18000a0ac  jz      short loc_18000A0B4
0x18000a0ae  call    cs:__imp_RegCloseKey
0x18000a0b4  test    dil, dil
0x18000a0b7  jz      short loc_18000A138
0x18000a0b9  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000a0be  mov     ecx, [rax]
0x18000a0c0  cmp     ecx, 5
0x18000a0c3  jbe     short loc_18000A103
0x18000a0c5  mov     rdx, [rax+18h]
0x18000a0c9  mov     rcx, [rax+10h]
0x18000a0cd  mov     r8, 400000000000h
0x18000a0d7  test    r8, rcx
0x18000a0da  jz      short loc_18000A103
0x18000a0dc  mov     rcx, rdx
0x18000a0df  and     rcx, r8
0x18000a0e2  cmp     rcx, rdx
0x18000a0e5  jnz     short loc_18000A103
0x18000a0e7  mov     [rbp+Data], r14
0x18000a0eb  lea     rcx, [rbp+Data]
0x18000a0ef  mov     [rsp+40h+phkResult], rcx
0x18000a0f4  lea     rdx, byte_180014ABB
0x18000a0fb  mov     rcx, rax
0x18000a0fe  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000a103  mov     rcx, [rbp+arg_18]
0x18000a107  mov     rax, [rcx]
0x18000a10a  mov     rax, [rax+18h]
0x18000a10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a113  mov     rcx, [rbp+28h]; this
0x18000a117  lea     rdx, aFailedWpnplatf; "Failed wpnPlatformInternal InitializePl"...
0x18000a11e  mov     [rsp+40h+phkResult], rdx; int
0x18000a123  mov     r9d, eax; char *
0x18000a126  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000a12d  mov     edx, 0B6h; void *
0x18000a132  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18000a137  nop
0x18000a138  mov     rcx, [rbp+arg_18]
0x18000a13c  test    rcx, rcx
0x18000a13f  jz      short loc_18000A152
0x18000a141  mov     [rbp+arg_18], r15
0x18000a145  mov     rax, [rcx]
0x18000a148  mov     rax, [rax+10h]
0x18000a14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a151  nop
0x18000a152  xor     eax, eax
0x18000a154  add     rsp, 40h
0x18000a158  pop     r15
0x18000a15a  pop     r14
0x18000a15c  pop     rdi
0x18000a15d  pop     rsi
0x18000a15e  pop     rbp
0x18000a15f  retn
```
