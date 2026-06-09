# Windows::Storage::ApplicationDataContainerSettingsServer::Insert(HSTRING__ *,IInspectable *,uchar *)

- ea: `0x180009900`
- end: `0x180009bcb`
- name: `?Insert@ApplicationDataContainerSettingsServer@Storage@Windows@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z`
- size: `715`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataContainerSettingsServer *this, HSTRING__ *key, IInspectable *value, unsigned __int8 *replaced)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005ee0`
- `0x180005f40`
- `0x1800092d0`
- `0x180009778`
- `0x180009900`
- `0x18000af34`
- `0x180016fdc`
- `0x180017004`
- `0x18001702c`
- `0x180018794`
- `0x180021efc`
- `0x180025004`
- `0x18002b024`
- `0x18002d0e4`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009977`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009977`
- `ntdll!WinSqmIncrementDWORD` at `0x18000995b`
- `ntdll!WinSqmIncrementDWORD` at `0x18000995b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009b0e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009b0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800099fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009a9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009adb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800099fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009a9f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009adb`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateVersion` at `0x180009b76`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateVersion` at `0x180009b76`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenState` at `0x180009b57`
- `ext-ms-win-appmodel-state-ext-l1-2-0!OpenState` at `0x180009b57`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateContainerDepth` at `0x180009b3f`
- `ext-ms-win-appmodel-state-ext-l1-2-0!GetStateContainerDepth` at `0x180009b3f`
- `api-ms-win-core-psm-app-l1-1-0!PsmQueryCurrentAppState` at `0x180009b80`
- `api-ms-win-core-psm-app-l1-1-0!PsmQueryCurrentAppState` at `0x180009b80`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataContainerSettingsServer::Insert(
        Windows::Storage::ApplicationDataContainerSettingsServer *this,
        HSTRING key,
        IInspectable *value,
        unsigned __int8 *replaced)
{
  HRESULT v7; // eax
  unsigned int v8; // edi
  HRESULT v9; // eax
  Windows::Storage::ApplicationDataCompositeValueServer *v10; // rcx
  HRESULT v11; // edi
  Windows::Storage::ApplicationDataCompositeValueServer *v13; // rcx
  PCWSTR StringRawBuffer; // rax
  unsigned int v15; // ebx
  PCWSTR v16; // rax
  const wchar_t *v17; // rbx
  unsigned int SettingValueBufferBytes; // eax
  unsigned int v19; // edi
  __int64 v20; // rax
  void *v21; // rbx
  unsigned int stateVersion; // [rsp+30h] [rbp-20h] BYREF
  _FILETIME time; // [rsp+38h] [rbp-18h] BYREF
  Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter apiSetValue; // [rsp+40h] [rbp-10h] BYREF
  void *retaddr; // [rsp+68h] [rbp+18h]
  HSTRING string; // [rsp+78h] [rbp+28h] BYREF
  unsigned int containerDepth; // [rsp+88h] [rbp+38h] BYREF

  string = key;
  apiSetValue.value = 0;
  apiSetValue.valueBytes = 0;
  apiSetValue.valueType = STATE_VALUE_LAST;
  time = 0;
  Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_INSERT_START);
  if ( !replaced )
  {
    v15 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x17Bu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
      -2147024809);
LABEL_27:
    Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_INSERT_STOP);
    Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::~SettingPropertyToApiSetValueConverter(&apiSetValue);
    return v15;
  }
  WinSqmIncrementDWORD(0, 11325, 1);
  v7 = Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::Initialize(&apiSetValue, value);
  v8 = v7;
  if ( v7 < 0 )
  {
    Windows::Storage::StateABIHelpers::ReportError(v7, 0x71u);
    if ( v8 != -2147024809 && v8 != -2147024882 )
      Windows::Storage::ApplicationDataContainerSettingsServer::SqmWriteSettingError(v13, v8);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x18Bu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
      v8,
      "Initialize %ws",
      StringRawBuffer);
    Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_INSERT_STOP);
    if ( apiSetValue.value )
      operator delete(apiSetValue.value);
    return v8;
  }
  else
  {
    GetSystemTimeAsFileTime(&time);
    v9 = this->InternalInsertValue(this, &string, &apiSetValue, &time);
    v11 = v9;
    if ( v9 < 0 )
    {
      if ( v9 != -2147024809 && v9 != -2147024882 )
        Windows::Storage::ApplicationDataContainerSettingsServer::SqmWriteSettingError(v10, v9);
      v16 = WindowsGetStringRawBuffer(string, 0);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x19Bu,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
        v11,
        "InternalInsertValue %ws",
        v16);
      v15 = v11;
      goto LABEL_27;
    }
    *replaced = 1;
    Windows::Storage::ApplicationDataContainerSettingsServer::SignalDataChanged(this);
    if ( this->m_containerLocality == ApplicationDataLocality_Roaming )
    {
      v17 = WindowsGetStringRawBuffer(string, 0);
      SettingValueBufferBytes = Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueBufferBytes(&apiSetValue);
      containerDepth = 0;
      v19 = SettingValueBufferBytes;
      if ( CompareStringOrdinal(v17, -1, L"HighPriority", -1, 1) == 2
        && v19 < 0x2000
        && !Windows::Storage::StateABIImplementation::setVersionInProgress
        && (unsigned int)GetStateContainerDepth(this->m_containerHandle, &containerDepth)
        && !containerDepth )
      {
        v20 = OpenState();
        v21 = (void *)v20;
        if ( v20 )
        {
          stateVersion = 0;
          if ( (unsigned int)GetStateVersion(v20, &stateVersion, 0) )
          {
            PsmQueryCurrentAppState();
            Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueBuffer(&apiSetValue);
            Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueType(&apiSetValue);
            State::AutoHandleCloseState(v21);
            v15 = 0;
            goto LABEL_27;
          }
        }
        State::AutoHandleCloseState(v21);
      }
    }
    Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_INSERT_STOP);
    if ( apiSetValue.value )
      operator delete(apiSetValue.value);
    return 0;
  }
}

```

## disassembly

```asm
0x180009900  mov     [rsp-18h+arg_0], rbx
0x180009905  mov     [rsp-18h+string], key
0x18000990a  push    rbp
0x18000990b  push    rsi
0x18000990c  push    rdi
0x18000990d  mov     rbp, rsp
0x180009910  sub     rsp, 50h
0x180009914  mov     rsi, this
0x180009917  mov     [rbp+apiSetValue.value], 0
0x18000991f  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_INSERT_START; eventDescriptor
0x180009926  mov     [rbp+apiSetValue.valueBytes], 0
0x18000992d  mov     rbx, replaced
0x180009930  mov     [rbp+apiSetValue.valueType], 27h ; '''
0x180009937  mov     rdi, value
0x18000993a  mov     qword ptr [rbp+time.dwLowDateTime], 0
0x180009942  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x180009947  test    rbx, rbx
0x18000994a  jz      loc_180009A4B
0x180009950  xor     ecx, ecx
0x180009952  mov     edx, 2C3Dh
0x180009957  lea     r8d, [this+1]
0x18000995b  call    cs:__imp_WinSqmIncrementDWORD
0x180009961  mov     key, rdi; _property
0x180009964  lea     this, [rbp+apiSetValue]; this
0x180009968  call    ?Initialize@SettingPropertyToApiSetValueConverter@StateABIHelpers@Storage@Windows@@QEAAJPEAUIInspectable@@@Z; Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::Initialize(IInspectable *)
0x18000996d  mov     edi, eax
0x18000996f  test    eax, eax
0x180009971  js      short loc_1800099E3
0x180009973  lea     this, [rbp+time]; lpSystemTimeAsFileTime
0x180009977  call    cs:__imp_GetSystemTimeAsFileTime
0x18000997d  mov     rax, [rsi]
0x180009980  lea     replaced, [rbp+time]
0x180009984  lea     value, [rbp+apiSetValue]
0x180009988  mov     this, rsi
0x18000998b  lea     key, [rbp+string]
0x18000998f  mov     rax, [rax+88h]
0x180009996  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000999b  mov     edi, eax
0x18000999d  test    eax, eax
0x18000999f  js      loc_180009A81
0x1800099a5  mov     this, rsi; this
0x1800099a8  mov     byte ptr [rbx], 1
0x1800099ab  call    ?SignalDataChanged@ApplicationDataContainerSettingsServer@Storage@Windows@@IEAAJXZ; Windows::Storage::ApplicationDataContainerSettingsServer::SignalDataChanged(void)
0x1800099b0  cmp     dword ptr [rsi+60h], 1
0x1800099b4  jz      loc_180009AD5
0x1800099ba  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_INSERT_STOP; eventDescriptor
0x1800099c1  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x1800099c6  mov     this, [rbp+apiSetValue.value]; p
0x1800099ca  test    this, this
0x1800099cd  jz      short loc_1800099D4
0x1800099cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800099d4  xor     eax, eax
0x1800099d6  mov     rbx, [rsp+50h+arg_0]
0x1800099db  add     rsp, 50h
0x1800099df  pop     rdi
0x1800099e0  pop     rsi
0x1800099e1  pop     rbp
0x1800099e2  retn
0x1800099e3  mov     edx, 71h ; 'q'; idsValue
0x1800099e8  mov     ecx, edi; hr
0x1800099ea  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x1800099ef  mov     ebx, 80070057h
0x1800099f4  cmp     edi, ebx
0x1800099f6  jnz     short loc_180009A6D
0x1800099f8  mov     this, [rbp+string]; string
0x1800099fc  xor     edx, edx; length
0x1800099fe  call    cs:__imp_WindowsGetStringRawBuffer
0x180009a04  mov     this, [rbp+18h]; callerReturnAddress
0x180009a08  lea     value, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\statemanage"...
0x180009a0f  mov     [rsp+50h+var_28], rax
0x180009a14  mov     r9d, edi; hr
0x180009a17  lea     rax, aInitializeWs; "Initialize %ws"
0x180009a1e  mov     edx, 18Bh; lineNumber
0x180009a23  mov     [rsp+50h+formatString], rax; formatString
0x180009a28  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180009a2d  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_INSERT_STOP; eventDescriptor
0x180009a34  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x180009a39  mov     this, [rbp+apiSetValue.value]; p
0x180009a3d  test    this, this
0x180009a40  jz      short loc_180009A47
0x180009a42  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009a47  mov     eax, edi
0x180009a49  jmp     short loc_1800099D6
0x180009a4b  mov     this, [rbp+18h]; callerReturnAddress
0x180009a4f  lea     value, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\statemanage"...
0x180009a56  mov     ebx, 80070057h
0x180009a5b  mov     edx, 17Bh; lineNumber
0x180009a60  mov     r9d, ebx; hr
0x180009a63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a68  jmp     loc_180009BA2
0x180009a6d  cmp     edi, 8007000Eh
0x180009a73  jz      short loc_1800099F8
0x180009a75  mov     edx, edi; hr
0x180009a77  call    ?SqmWriteSettingError@ApplicationDataContainerSettingsServer@Storage@Windows@@AEAAXJ@Z; Windows::Storage::ApplicationDataContainerSettingsServer::SqmWriteSettingError(long)
0x180009a7c  jmp     loc_1800099F8
0x180009a81  mov     ebx, 80070057h
0x180009a86  cmp     edi, ebx
0x180009a88  jz      short loc_180009A99
0x180009a8a  cmp     edi, 8007000Eh
0x180009a90  jz      short loc_180009A99
0x180009a92  mov     edx, edi; hr
0x180009a94  call    ?SqmWriteSettingError@ApplicationDataContainerSettingsServer@Storage@Windows@@AEAAXJ@Z; Windows::Storage::ApplicationDataContainerSettingsServer::SqmWriteSettingError(long)
0x180009a99  mov     this, [rbp+string]; string
0x180009a9d  xor     edx, edx; length
0x180009a9f  call    cs:__imp_WindowsGetStringRawBuffer
0x180009aa5  mov     this, [rbp+18h]; callerReturnAddress
0x180009aa9  lea     value, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\statemanage"...
0x180009ab0  mov     [rsp+50h+var_28], rax
0x180009ab5  mov     r9d, edi; hr
0x180009ab8  lea     rax, aInternalinsert; "InternalInsertValue %ws"
0x180009abf  mov     edx, 19Bh; lineNumber
0x180009ac4  mov     [rsp+50h+formatString], rax; formatString
0x180009ac9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180009ace  mov     ebx, edi
0x180009ad0  jmp     loc_180009BA2
0x180009ad5  mov     this, [rbp+string]; string
0x180009ad9  xor     edx, edx; length
0x180009adb  call    cs:__imp_WindowsGetStringRawBuffer
0x180009ae1  lea     this, [rbp+apiSetValue]; this
0x180009ae5  mov     rbx, rax
0x180009ae8  call    ?GetSettingValueBufferBytes@SettingPropertyToApiSetValueConverter@StateABIHelpers@Storage@Windows@@QEBA?BIXZ; Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueBufferBytes(void)
0x180009aed  or      edx, 0FFFFFFFFh; cchCount1
0x180009af0  mov     [rbp+containerDepth], 0
0x180009af7  mov     r9d, edx; cchCount2
0x180009afa  mov     dword ptr [rsp+50h+formatString], 1; bIgnoreCase
0x180009b02  lea     value, aHighpriority; "HighPriority"
0x180009b09  mov     this, rbx; lpString1
0x180009b0c  mov     edi, eax
0x180009b0e  call    cs:__imp_CompareStringOrdinal
0x180009b14  cmp     eax, 2
0x180009b17  jnz     loc_1800099BA
0x180009b1d  cmp     edi, 2000h
0x180009b23  jnb     loc_1800099BA
0x180009b29  mov     eax, cs:Windows__Storage__StateABIImplementation__setVersionInProgress
0x180009b2f  test    eax, eax
0x180009b31  jnz     loc_1800099BA
0x180009b37  mov     this, [rsi+58h]
0x180009b3b  lea     key, [rbp+containerDepth]
0x180009b3f  call    cs:__imp_GetStateContainerDepth
0x180009b45  test    eax, eax
0x180009b47  jz      loc_1800099BA
0x180009b4d  cmp     [rbp+containerDepth], 0
0x180009b51  jnz     loc_1800099BA
0x180009b57  call    cs:__imp_OpenState
0x180009b5d  mov     rbx, rax
0x180009b60  test    rax, rax
0x180009b63  jz      short loc_180009BBE
0x180009b65  xor     r8d, r8d
0x180009b68  mov     [rbp+stateVersion], 0
0x180009b6f  lea     key, [rbp+stateVersion]
0x180009b73  mov     this, rax
0x180009b76  call    cs:__imp_GetStateVersion
0x180009b7c  test    eax, eax
0x180009b7e  jz      short loc_180009BBE
0x180009b80  call    cs:__imp_PsmQueryCurrentAppState
0x180009b86  lea     this, [rbp+apiSetValue]; this
0x180009b8a  call    ?GetSettingValueBuffer@SettingPropertyToApiSetValueConverter@StateABIHelpers@Storage@Windows@@QEBAPEAEXZ; Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueBuffer(void)
0x180009b8f  lea     this, [rbp+apiSetValue]; this
0x180009b93  call    ?GetSettingValueType@SettingPropertyToApiSetValueConverter@StateABIHelpers@Storage@Windows@@QEBA?BW4tag_STATE_VALUE_TYPE@@XZ; Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueType(void)
0x180009b98  mov     this, rbx; h
0x180009b9b  call    ?AutoHandleCloseState@State@@YAXPEAX@Z; State::AutoHandleCloseState(void *)
0x180009ba0  xor     ebx, ebx
0x180009ba2  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_INSERT_STOP; eventDescriptor
0x180009ba9  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x180009bae  lea     this, [rbp+apiSetValue]; this
0x180009bb2  call    ??1SettingPropertyToApiSetValueConverter@StateABIHelpers@Storage@Windows@@QEAA@XZ; Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::~SettingPropertyToApiSetValueConverter(void)
0x180009bb7  mov     eax, ebx
0x180009bb9  jmp     loc_1800099D6
0x180009bbe  mov     this, rbx; h
0x180009bc1  call    ?AutoHandleCloseState@State@@YAXPEAX@Z; State::AutoHandleCloseState(void *)
0x180009bc6  jmp     loc_1800099BA
```
