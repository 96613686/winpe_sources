# Windows::Storage::ApplicationDataCompositeValueServer::Insert(HSTRING__ *,IInspectable *,uchar *)

- ea: `0x18000bc30`
- end: `0x18000bf81`
- name: `?Insert@ApplicationDataCompositeValueServer@Storage@Windows@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@PEAE@Z`
- size: `849`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataCompositeValueServer *this, HSTRING__ *key, IInspectable *value, unsigned __int8 *replaced)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005ee0`
- `0x1800092d0`
- `0x180009778`
- `0x18000aa74`
- `0x18000af34`
- `0x18000bc30`
- `0x180016fdc`
- `0x180018794`
- `0x180021efc`
- `0x180021fc4`
- `0x180025004`
- `0x18002d0e4`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdb7`
- `ntdll!WinSqmIncrementDWORD` at `0x18000bc84`
- `ntdll!WinSqmIncrementDWORD` at `0x18000bc84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bd6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000be04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bf38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bd6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000be04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000bf38`
- `ext-ms-win-appmodel-state-ext-l1-2-0!WriteStateAtomValue` at `0x18000bcfd`
- `ext-ms-win-appmodel-state-ext-l1-2-0!WriteStateAtomValue` at `0x18000bcfd`

## string_xrefs

- `0x18000bd74`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`
- `0x18000be0e`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`
- `0x18000be42`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`
- `0x18000bed1`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`
- `0x18000bf42`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`
- `0x18000bf51`: `Remove %ws`
- `0x18000be26`: `WriteStateAtomValue %ws type %u`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataCompositeValueServer::Insert(
        Windows::Storage::ApplicationDataCompositeValueServer *this,
        HSTRING key,
        IInspectable *value,
        unsigned __int8 *replaced)
{
  HRESULT v8; // eax
  unsigned int v9; // edi
  tag_STATE_VALUE_TYPE valueType; // ebx
  unsigned int valueBytes; // r12d
  unsigned __int8 *v12; // rdi
  PCWSTR v13; // rax
  Windows::Storage::ApplicationDataCompositeValueServer *v15; // rcx
  PCWSTR StringRawBuffer; // rax
  signed int LastError; // eax
  signed int v18; // edi
  Windows::Storage::ApplicationDataCompositeValueServer *v19; // rcx
  tag_STATE_VALUE_TYPE SettingValueType; // ebx
  PCWSTR v21; // rax
  unsigned int v22; // ebx
  HRESULT v23; // eax
  Windows::Storage::ApplicationDataCompositeValueServer *v24; // rcx
  PCWSTR v25; // rax
  Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter apiSetValue; // [rsp+40h] [rbp-10h] BYREF
  void *retaddr; // [rsp+88h] [rbp+38h]

  apiSetValue.value = 0;
  apiSetValue.valueBytes = 0;
  apiSetValue.valueType = STATE_VALUE_LAST;
  Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_INSERT_START);
  if ( !replaced )
  {
    v22 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x175u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
      -2147024809);
LABEL_32:
    Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_INSERT_STOP);
    Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::~SettingPropertyToApiSetValueConverter(&apiSetValue);
    return v22;
  }
  WinSqmIncrementDWORD(0, 11325, 1);
  v8 = Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::Initialize(&apiSetValue, value);
  v9 = v8;
  if ( v8 < 0 )
  {
    Windows::Storage::StateABIHelpers::ReportError(v8, 0x71u);
    if ( v9 != -2147024809 && v9 != -2147024882 )
      Windows::Storage::ApplicationDataContainerSettingsServer::SqmWriteSettingError(v15, v9);
    StringRawBuffer = WindowsGetStringRawBuffer(key, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x185u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
      v9,
      "Initialize %ws",
      StringRawBuffer);
    Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_INSERT_STOP);
    if ( apiSetValue.value )
      operator delete(apiSetValue.value);
    return v9;
  }
  valueType = apiSetValue.valueType;
  if ( apiSetValue.valueType == STATE_VALUE_LAST )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    valueType = apiSetValue.valueType;
  }
  switch ( valueType )
  {
    case STATE_VALUE_UNDEFINED:
      v23 = this->Remove(this, key);
      *replaced = 0;
      v9 = v23;
      if ( v23 < 0 )
      {
        if ( v23 != -2147024809 && v23 != -2147024882 )
          Windows::Storage::ApplicationDataContainerSettingsServer::SqmWriteSettingError(v24, v23);
        v25 = WindowsGetStringRawBuffer(key, 0);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x196u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
          v9,
          "Remove %ws",
          v25);
      }
      Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_INSERT_STOP);
      Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::~SettingPropertyToApiSetValueConverter(&apiSetValue);
      return v9;
    case STATE_VALUE_ATOM:
      Windows::Storage::StateABIHelpers::ReportError(-2147023266, 0x70u);
      v22 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              0x19Cu,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
              0x65Eu,
              "ReportError");
      goto LABEL_32;
    case STATE_VALUE_LAST:
      MicrosoftTelemetryAssertTriggeredNoArgs();
      valueType = apiSetValue.valueType;
      break;
  }
  valueBytes = apiSetValue.valueBytes;
  if ( valueType == STATE_VALUE_LAST )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    valueType = apiSetValue.valueType;
  }
  v12 = apiSetValue.value;
  if ( valueType == STATE_VALUE_LAST )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    valueType = apiSetValue.valueType;
  }
  v13 = WindowsGetStringRawBuffer(key, 0);
  if ( !(unsigned int)WriteStateAtomValue(this->atomHandle, v13, (unsigned int)valueType, v12, valueBytes) )
  {
    LastError = GetLastError();
    v18 = LastError;
    if ( LastError > 0 )
      v18 = (unsigned __int16)LastError | 0x80070000;
    Windows::Storage::StateABIHelpers::ReportError(v18, 0xFu);
    if ( v18 == -2147024809
      || v18 == -2147024882
      || (Windows::Storage::ApplicationDataContainerSettingsServer::SqmWriteSettingError(v19, v18), v18 < 0) )
    {
      SettingValueType = Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueType(&apiSetValue);
      v21 = WindowsGetStringRawBuffer(key, 0);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x1B2u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
        v18,
        "WriteStateAtomValue %ws type %u",
        v21,
        SettingValueType);
    }
    v22 = v18;
    goto LABEL_32;
  }
  *replaced = 1;
  this->SignalDataChanged(this);
  Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_INSERT_STOP);
  if ( apiSetValue.value )
    operator delete(apiSetValue.value);
  return 0;
}

```

## disassembly

```asm
0x18000bc30  push    rbp
0x18000bc32  push    rbx
0x18000bc33  push    rsi
0x18000bc34  push    rdi
0x18000bc35  push    r12
0x18000bc37  push    r14
0x18000bc39  push    r15
0x18000bc3b  mov     rbp, rsp
0x18000bc3e  sub     rsp, 50h
0x18000bc42  mov     rsi, this
0x18000bc45  mov     [rbp+apiSetValue.value], 0
0x18000bc4d  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_INSERT_START; eventDescriptor
0x18000bc54  mov     [rbp+apiSetValue.valueBytes], 0
0x18000bc5b  mov     r15, replaced
0x18000bc5e  mov     [rbp+apiSetValue.valueType], 27h ; '''
0x18000bc65  mov     rbx, value
0x18000bc68  mov     r14, key
0x18000bc6b  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18000bc70  test    r15, r15
0x18000bc73  jz      loc_18000BE3E
0x18000bc79  xor     ecx, ecx
0x18000bc7b  mov     edx, 2C3Dh
0x18000bc80  lea     r8d, [this+1]
0x18000bc84  call    cs:__imp_WinSqmIncrementDWORD
0x18000bc8a  mov     key, rbx; _property
0x18000bc8d  lea     this, [rbp+apiSetValue]; this
0x18000bc91  call    ?Initialize@SettingPropertyToApiSetValueConverter@StateABIHelpers@Storage@Windows@@QEAAJPEAUIInspectable@@@Z; Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::Initialize(IInspectable *)
0x18000bc96  mov     edi, eax
0x18000bc98  test    eax, eax
0x18000bc9a  js      loc_18000BD4C
0x18000bca0  mov     ebx, [rbp+apiSetValue.valueType]
0x18000bca3  cmp     ebx, 27h ; '''
0x18000bca6  jz      loc_18000BE78
0x18000bcac  test    ebx, ebx
0x18000bcae  jz      loc_18000BF00
0x18000bcb4  cmp     ebx, 0Dh
0x18000bcb7  jz      loc_18000BEAC
0x18000bcbd  cmp     ebx, 27h ; '''
0x18000bcc0  jz      loc_18000BE85
0x18000bcc6  mov     r12d, [rbp+apiSetValue.valueBytes]
0x18000bcca  cmp     ebx, 27h ; '''
0x18000bccd  jz      loc_18000BE92
0x18000bcd3  mov     rdi, [rbp+apiSetValue.value]
0x18000bcd7  cmp     ebx, 27h ; '''
0x18000bcda  jz      loc_18000BE9F
0x18000bce0  xor     edx, edx; length
0x18000bce2  mov     this, r14; string
0x18000bce5  call    cs:__imp_WindowsGetStringRawBuffer
0x18000bceb  mov     this, [rsi+60h]
0x18000bcef  mov     replaced, rdi
0x18000bcf2  mov     key, rax
0x18000bcf5  mov     dword ptr [rsp+50h+formatString], r12d
0x18000bcfa  mov     r8d, ebx
0x18000bcfd  call    cs:__imp_WriteStateAtomValue
0x18000bd03  test    eax, eax
0x18000bd05  jz      loc_18000BDB7
0x18000bd0b  mov     byte ptr [r15], 1
0x18000bd0f  mov     this, rsi
0x18000bd12  mov     rax, [rsi]
0x18000bd15  mov     rax, [rax+88h]
0x18000bd1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd21  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_INSERT_STOP; eventDescriptor
0x18000bd28  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18000bd2d  mov     this, [rbp+apiSetValue.value]; p
0x18000bd31  test    this, this
0x18000bd34  jz      short loc_18000BD3B
0x18000bd36  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bd3b  xor     eax, eax
0x18000bd3d  add     rsp, 50h
0x18000bd41  pop     r15
0x18000bd43  pop     r14
0x18000bd45  pop     r12
0x18000bd47  pop     rdi
0x18000bd48  pop     rsi
0x18000bd49  pop     rbx
0x18000bd4a  pop     rbp
0x18000bd4b  retn
0x18000bd4c  mov     edx, 71h ; 'q'; idsValue
0x18000bd51  mov     ecx, edi; hr
0x18000bd53  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x18000bd58  mov     ebx, 80070057h
0x18000bd5d  cmp     edi, ebx
0x18000bd5f  jnz     loc_18000BE60
0x18000bd65  xor     edx, edx; length
0x18000bd67  mov     this, r14; string
0x18000bd6a  call    cs:__imp_WindowsGetStringRawBuffer
0x18000bd70  mov     this, [rbp+38h]; callerReturnAddress
0x18000bd74  lea     value, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000bd7b  mov     [rsp+50h+var_28], rax
0x18000bd80  mov     r9d, edi; hr
0x18000bd83  lea     rax, aInitializeWs; "Initialize %ws"
0x18000bd8a  mov     edx, 185h; lineNumber
0x18000bd8f  mov     [rsp+50h+formatString], rax; formatString
0x18000bd94  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000bd99  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_INSERT_STOP; eventDescriptor
0x18000bda0  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18000bda5  mov     this, [rbp+apiSetValue.value]; p
0x18000bda9  test    this, this
0x18000bdac  jz      short loc_18000BDB3
0x18000bdae  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bdb3  mov     eax, edi
0x18000bdb5  jmp     short loc_18000BD3D
0x18000bdb7  call    cs:__imp_GetLastError
0x18000bdbd  mov     edi, eax
0x18000bdbf  test    eax, eax
0x18000bdc1  jle     short loc_18000BDCC
0x18000bdc3  movzx   edi, ax
0x18000bdc6  or      edi, 80070000h
0x18000bdcc  mov     edx, 0Fh; idsValue
0x18000bdd1  mov     ecx, edi; hr
0x18000bdd3  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x18000bdd8  mov     ebx, 80070057h
0x18000bddd  cmp     edi, ebx
0x18000bddf  jz      short loc_18000BDF4
0x18000bde1  cmp     edi, 8007000Eh
0x18000bde7  jz      short loc_18000BDF4
0x18000bde9  mov     edx, edi; hr
0x18000bdeb  call    ?SqmWriteSettingError@ApplicationDataContainerSettingsServer@Storage@Windows@@AEAAXJ@Z; Windows::Storage::ApplicationDataContainerSettingsServer::SqmWriteSettingError(long)
0x18000bdf0  test    edi, edi
0x18000bdf2  jns     short loc_18000BE37
0x18000bdf4  lea     this, [rbp+apiSetValue]; this
0x18000bdf8  call    ?GetSettingValueType@SettingPropertyToApiSetValueConverter@StateABIHelpers@Storage@Windows@@QEBA?BW4tag_STATE_VALUE_TYPE@@XZ; Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::GetSettingValueType(void)
0x18000bdfd  xor     edx, edx; length
0x18000bdff  mov     this, r14; string
0x18000be02  mov     ebx, eax
0x18000be04  call    cs:__imp_WindowsGetStringRawBuffer
0x18000be0a  mov     this, [rbp+38h]; callerReturnAddress
0x18000be0e  lea     value, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000be15  mov     [rsp+50h+var_20], ebx
0x18000be19  mov     r9d, edi; hr
0x18000be1c  mov     [rsp+50h+var_28], rax
0x18000be21  mov     edx, 1B2h; lineNumber
0x18000be26  lea     rax, aWritestateatom_0; "WriteStateAtomValue %ws type %u"
0x18000be2d  mov     [rsp+50h+formatString], rax; formatString
0x18000be32  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000be37  mov     ebx, edi
0x18000be39  jmp     loc_18000BEE4
0x18000be3e  mov     this, [rbp+38h]; callerReturnAddress
0x18000be42  lea     value, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000be49  mov     ebx, 80070057h
0x18000be4e  mov     edx, 175h; lineNumber
0x18000be53  mov     r9d, ebx; hr
0x18000be56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be5b  jmp     loc_18000BEE4
0x18000be60  cmp     edi, 8007000Eh
0x18000be66  jz      loc_18000BD65
0x18000be6c  mov     edx, edi; hr
0x18000be6e  call    ?SqmWriteSettingError@ApplicationDataContainerSettingsServer@Storage@Windows@@AEAAXJ@Z; Windows::Storage::ApplicationDataContainerSettingsServer::SqmWriteSettingError(long)
0x18000be73  jmp     loc_18000BD65
0x18000be78  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "this->valueType != StateApiSet::STATE_VALUE_TYPE::STATE_VALUE_LAST")
0x18000be7d  mov     ebx, [rbp+apiSetValue.valueType]
0x18000be80  jmp     loc_18000BCAC
0x18000be85  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "this->valueType != StateApiSet::STATE_VALUE_TYPE::STATE_VALUE_LAST")
0x18000be8a  mov     ebx, [rbp+apiSetValue.valueType]
0x18000be8d  jmp     loc_18000BCC6
0x18000be92  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "this->valueType != StateApiSet::STATE_VALUE_TYPE::STATE_VALUE_LAST")
0x18000be97  mov     ebx, [rbp+apiSetValue.valueType]
0x18000be9a  jmp     loc_18000BCD3
0x18000be9f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "this->valueType != StateApiSet::STATE_VALUE_TYPE::STATE_VALUE_LAST")
0x18000bea4  mov     ebx, [rbp+apiSetValue.valueType]
0x18000bea7  jmp     loc_18000BCE0
0x18000beac  mov     edx, 70h ; 'p'; idsValue
0x18000beb1  mov     ecx, 8007065Eh; hr
0x18000beb6  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x18000bebb  mov     this, [rbp+38h]; callerReturnAddress
0x18000bebf  lea     rax, aReporterror; "ReportError"
0x18000bec6  mov     r9d, 65Eh; err
0x18000becc  mov     [rsp+50h+formatString], rax; formatString
0x18000bed1  lea     value, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000bed8  mov     edx, 19Ch; lineNumber
0x18000bedd  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18000bee2  mov     ebx, eax
0x18000bee4  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_INSERT_STOP; eventDescriptor
0x18000beeb  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18000bef0  lea     this, [rbp+apiSetValue]; this
0x18000bef4  call    ??1SettingPropertyToApiSetValueConverter@StateABIHelpers@Storage@Windows@@QEAA@XZ; Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::~SettingPropertyToApiSetValueConverter(void)
0x18000bef9  mov     eax, ebx
0x18000befb  jmp     loc_18000BD3D
0x18000bf00  mov     rax, [rsi]
0x18000bf03  mov     key, r14
0x18000bf06  mov     this, rsi
0x18000bf09  mov     rax, [rax+58h]
0x18000bf0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf12  mov     byte ptr [r15], 0
0x18000bf16  mov     edi, eax
0x18000bf18  test    eax, eax
0x18000bf1a  jns     short loc_18000BF67
0x18000bf1c  mov     ebx, 80070057h
0x18000bf21  cmp     eax, ebx
0x18000bf23  jz      short loc_18000BF33
0x18000bf25  cmp     eax, 8007000Eh
0x18000bf2a  jz      short loc_18000BF33
0x18000bf2c  mov     edx, eax; hr
0x18000bf2e  call    ?SqmWriteSettingError@ApplicationDataContainerSettingsServer@Storage@Windows@@AEAAXJ@Z; Windows::Storage::ApplicationDataContainerSettingsServer::SqmWriteSettingError(long)
0x18000bf33  xor     edx, edx; length
0x18000bf35  mov     this, r14; string
0x18000bf38  call    cs:__imp_WindowsGetStringRawBuffer
0x18000bf3e  mov     this, [rbp+38h]; callerReturnAddress
0x18000bf42  lea     value, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000bf49  mov     [rsp+50h+var_28], rax
0x18000bf4e  mov     r9d, edi; hr
0x18000bf51  lea     rax, aRemoveWs; "Remove %ws"
0x18000bf58  mov     edx, 196h; lineNumber
0x18000bf5d  mov     [rsp+50h+formatString], rax; formatString
0x18000bf62  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000bf67  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_INSERT_STOP; eventDescriptor
0x18000bf6e  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18000bf73  lea     this, [rbp+apiSetValue]; this
0x18000bf77  call    ??1SettingPropertyToApiSetValueConverter@StateABIHelpers@Storage@Windows@@QEAA@XZ; Windows::Storage::StateABIHelpers::SettingPropertyToApiSetValueConverter::~SettingPropertyToApiSetValueConverter(void)
0x18000bf7c  jmp     loc_18000BDB3
```
