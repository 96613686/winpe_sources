# WnfEventHandlerForOfflinePcChangeImpl(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x180090be8`
- end: `0x180090e4d`
- name: `?WnfEventHandlerForOfflinePcChangeImpl@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `613`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, BYTE Data)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800842b0`

## callees

- `0x180002540`
- `0x180004644`
- `0x180004738`
- `0x180013b50`
- `0x180046f88`
- `0x180056ca8`
- `0x1800593bc`
- `0x180061e24`
- `0x18006ad98`
- `0x180090be8`
- `0x180090f34`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180090cb4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180090cb4`
- `ntdll!RtlPublishWnfStateData` at `0x180090cec`
- `ntdll!RtlPublishWnfStateData` at `0x180090cec`

## string_xrefs

- `0x180090c27`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180090e3a`: `onecoreuap\enduser\winstore\licensemanager\lib\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 WnfEventHandlerForOfflinePcChangeImpl(
        struct _WNF_STATE_NAME a1,
        int a2,
        struct _WNF_TYPE_ID *a3,
        HKEY a4,
        const char *a5,
        ...)
{
  int v6; // eax
  unsigned int v7; // eax
  DWORD v8; // ebx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  const char *v12; // r9
  int lpData; // [rsp+20h] [rbp-58h]
  unsigned int lpDataa; // [rsp+20h] [rbp-58h]
  DWORD cbData[2]; // [rsp+28h] [rbp-50h]
  const wchar_t *v17; // [rsp+50h] [rbp-28h] BYREF
  _BYTE v18[32]; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  const char *v20; // [rsp+80h] [rbp+8h] BYREF
  struct _WNF_TYPE_ID *v21; // [rsp+90h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+20h] BYREF
  __int64 Data; // [rsp+A8h] [rbp+30h] BYREF
  va_list Dataa; // [rsp+A8h] [rbp+30h]
  va_list va1; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(Dataa, a5);
  Data = va_arg(va1, _QWORD);
  hKey = a4;
  v21 = a3;
  v20 = (const char *)a1;
  ProcessReference(v18);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
    0xA70u,
    "WnfEventHandlerForOfflinePcChangeImpl",
    (wchar_t *)L"Wnf for offline pc received");
  try
  {
    CreateApplicationLicenseManager(&v21);
    v6 = (*(__int64 (__fastcall **)(struct _WNF_TYPE_ID *, __int64))(*(_QWORD *)v21 + 88LL))(v21, 1);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA76,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        (const char *)(unsigned int)v6,
        lpData);
    LODWORD(Data) = a2;
    GetServiceMutableStateKey(&hKey, 0x20006u);
    v7 = RegSetValueExW(hKey, L"LastWnfOfflinePcChangeStamp", 0, 4u, (const BYTE *)Dataa, 4u);
    if ( v7 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xF5,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\registry.cpp",
        (const char *)v7,
        lpDataa);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v8 = RtlPublishWnfStateData(WNF_LM_LICENSE_REFRESHED, 0, 0, 0, 0);
    if ( (v8 & 0xC0000000) == 0xC0000000 )
    {
      if ( _UnitTestWnfCallback )
      {
        _UnitTestWnfCallback((struct _WNF_STATE_NAME)WNF_LM_OPTIONAL_PACKAGE_SUSPEND_REQUIRED, 0, 0, 0, 0, 0);
      }
      else
      {
        cbData[0] = v8;
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
          0xA84u,
          "WnfEventHandlerForOfflinePcChangeImpl",
          (wchar_t *)L"Failed to send WNF_LM_LICENSE_REFRESHED - status = 0x%08x",
          *(_QWORD *)cbData);
        if ( (unsigned int)dword_1800F11D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x400000000000LL) )
        {
          v20 = "WnfEventHandlerForOfflinePcChangeImpl";
          LODWORD(Data) = 2696;
          a5 = "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp";
          LODWORD(hKey) = v8;
          v17 = L"Failed to send WNF_LM_LICENSE_REFRESHED";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v9,
            (unsigned int)byte_1800D6FD5,
            v10,
            v11,
            (__int64)&v17,
            (__int64)&hKey,
            (__int64)&a5,
            (__int64)Dataa,
            (__int64)&v20);
        }
      }
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xA8C,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      v12);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v18);
  return 0;
}

```

## disassembly

```asm
0x180090be8  mov     rax, rsp
0x180090beb  mov     [rax+20h], r9
0x180090bef  mov     [rax+18h], r8
0x180090bf3  mov     [rax+8], rcx
0x180090bf7  push    rbx
0x180090bf8  push    rsi
0x180090bf9  push    r14
0x180090bfb  sub     rsp, 60h
0x180090bff  mov     ebx, edx
0x180090c01  lea     rcx, [rax-20h]
0x180090c05  call    ?ProcessReference@@YA?AV?$ComPtr@UIUnknown@@@WRL@Microsoft@@XZ; ProcessReference(void)
0x180090c0a  nop
0x180090c0b  lea     rax, aWnfForOfflineP; "Wnf for offline pc received"
0x180090c12  mov     [rsp+78h+lpData], rax; int
0x180090c17  lea     r14, aWnfeventhandle_2; "WnfEventHandlerForOfflinePcChangeImpl"
0x180090c1e  mov     r9, r14; char *
0x180090c21  mov     r8d, 0A70h; unsigned int
0x180090c27  lea     rsi, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180090c2e  mov     rdx, rsi; char *
0x180090c31  mov     ecx, 3; unsigned int
0x180090c36  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180090c3b  nop
0x180090c3c  lea     rcx, [rsp+78h+arg_10]
0x180090c44  call    ?CreateApplicationLicenseManager@@YA?AV?$ComPtr@UIApplicationLicenseManager@@@WRL@Microsoft@@XZ; CreateApplicationLicenseManager(void)
0x180090c49  nop
0x180090c4a  mov     rcx, [rsp+78h+arg_10]
0x180090c52  mov     rax, [rcx]
0x180090c55  mov     edx, 1
0x180090c5a  mov     rax, [rax+58h]
0x180090c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090c63  mov     rcx, [rsp+78h]; this
0x180090c68  test    eax, eax
0x180090c6a  js      loc_180090E26
0x180090c70  mov     dword ptr [rsp+78h+Data], ebx
0x180090c77  mov     edx, 20006h; samDesired
0x180090c7c  lea     rcx, [rsp+78h+hKey]; phkResult
0x180090c84  call    ?GetServiceMutableStateKey@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; GetServiceMutableStateKey(ulong)
0x180090c89  nop
0x180090c8a  mov     r9d, 4; dwType
0x180090c90  mov     [rsp+78h+cbData], r9d; cbData
0x180090c95  lea     rax, [rsp+78h+Data]
0x180090c9d  mov     [rsp+78h+lpData], rax; unsigned int
0x180090ca2  xor     r8d, r8d; Reserved
0x180090ca5  lea     rdx, aLastwnfoffline; "LastWnfOfflinePcChangeStamp"
0x180090cac  mov     rcx, [rsp+78h+hKey]; hKey
0x180090cb4  call    cs:__imp_RegSetValueExW
0x180090cba  mov     rcx, [rsp+78h]; this
0x180090cbf  test    eax, eax
0x180090cc1  jnz     loc_180090E37
0x180090cc7  lea     rcx, [rsp+78h+hKey]
0x180090ccf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180090cd4  mov     [rsp+78h+lpData], 0
0x180090cdd  xor     r9d, r9d
0x180090ce0  xor     r8d, r8d
0x180090ce3  xor     edx, edx
0x180090ce5  mov     rcx, cs:WNF_LM_LICENSE_REFRESHED
0x180090cec  call    cs:__imp_RtlPublishWnfStateData
0x180090cf2  mov     ebx, eax
0x180090cf4  mov     ecx, eax
0x180090cf6  mov     eax, 0C0000000h
0x180090cfb  and     ecx, eax
0x180090cfd  cmp     ecx, eax
0x180090cff  jnz     loc_180090E03
0x180090d05  mov     rax, cs:?_UnitTestWnfCallback@@3P6AJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@ZEA; long (*_UnitTestWnfCallback)(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180090d0c  test    rax, rax
0x180090d0f  jz      short loc_180090D3B
0x180090d11  mov     [rsp+78h+cbData], 0
0x180090d19  mov     [rsp+78h+lpData], 0
0x180090d22  xor     r9d, r9d
0x180090d25  xor     r8d, r8d
0x180090d28  xor     edx, edx
0x180090d2a  mov     rcx, cs:WNF_LM_OPTIONAL_PACKAGE_SUSPEND_REQUIRED
0x180090d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090d36  jmp     loc_180090E03
0x180090d3b  mov     [rsp+78h+cbData], ebx
0x180090d3f  lea     rax, aFailedToSendWn_2; "Failed to send WNF_LM_LICENSE_REFRESHED"...
0x180090d46  mov     [rsp+78h+lpData], rax; Format
0x180090d4b  mov     r9, r14; char *
0x180090d4e  mov     r8d, 0A84h; unsigned int
0x180090d54  mov     rdx, rsi; char *
0x180090d57  mov     ecx, 1; unsigned int
0x180090d5c  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180090d61  mov     eax, cs:dword_1800F11D0
0x180090d67  cmp     eax, 2
0x180090d6a  jbe     loc_180090E03
0x180090d70  mov     rdx, 400000000000h
0x180090d7a  lea     rcx, dword_1800F11D0
0x180090d81  call    _tlgKeywordOn
0x180090d86  test    al, al
0x180090d88  jz      short loc_180090E03
0x180090d8a  mov     [rsp+78h+arg_0], r14
0x180090d92  mov     dword ptr [rsp+78h+Data], 0A88h
0x180090d9d  mov     [rsp+78h+arg_20], rsi
0x180090da5  mov     dword ptr [rsp+78h+hKey], ebx
0x180090dac  lea     rax, aFailedToSendWn_1; "Failed to send WNF_LM_LICENSE_REFRESHED"
0x180090db3  mov     [rsp+78h+var_28], rax
0x180090db8  lea     rax, [rsp+78h+arg_0]
0x180090dc0  mov     [rsp+78h+var_38], rax
0x180090dc5  lea     rax, [rsp+78h+Data]
0x180090dcd  mov     [rsp+78h+var_40], rax
0x180090dd2  lea     rax, [rsp+78h+arg_20]
0x180090dda  mov     [rsp+78h+var_48], rax
0x180090ddf  lea     rax, [rsp+78h+hKey]
0x180090de7  mov     qword ptr [rsp+78h+cbData], rax
0x180090dec  lea     rax, [rsp+78h+var_28]
0x180090df1  mov     [rsp+78h+lpData], rax
0x180090df6  lea     rdx, byte_1800D6FD5
0x180090dfd  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180090e02  nop
0x180090e03  lea     rcx, [rsp+78h+arg_10]
0x180090e0b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180090e10  nop
0x180090e11  lea     rcx, [rsp+78h+var_20]
0x180090e16  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180090e1b  xor     eax, eax
0x180090e1d  add     rsp, 60h
0x180090e21  pop     r14
0x180090e23  pop     rsi
0x180090e24  pop     rbx
0x180090e25  retn
0x180090e26  mov     r9d, eax; char *
0x180090e29  mov     r8, rsi; unsigned int
0x180090e2c  mov     edx, 0A76h; void *
0x180090e31  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180090e37  mov     r9d, eax; char *
0x180090e3a  lea     r8, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\licensem"...
0x180090e41  mov     edx, 0F5h; void *
0x180090e46  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
