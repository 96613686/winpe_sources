# Windows::Storage::ApplicationDataContainerSettingsServer::Lookup(HSTRING__ *,IInspectable * *)

- ea: `0x180008410`
- end: `0x1800089af`
- name: `?Lookup@ApplicationDataContainerSettingsServer@Storage@Windows@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `1439`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataContainerSettingsServer *this, HSTRING__ *key, IInspectable **value)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005ee0`
- `0x180008410`
- `0x1800092d0`
- `0x180009758`
- `0x180009778`
- `0x18001c740`
- `0x180021efc`
- `0x180021fc4`
- `0x180024fc4`
- `0x180025004`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800085d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800086fc`
- `ntdll!WinSqmIncrementDWORD` at `0x180008475`
- `ntdll!WinSqmIncrementDWORD` at `0x180008475`
- `ntdll!WinSqmSetDWORD` at `0x1800087ca`
- `ntdll!WinSqmSetDWORD` at `0x18000885c`
- `ntdll!WinSqmSetDWORD` at `0x1800087ca`
- `ntdll!WinSqmSetDWORD` at `0x18000885c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008485`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008503`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000864f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000874e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800087e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008877`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000890d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000895d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008485`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008503`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000864f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000874e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800087e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008877`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000890d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000895d`
- `ext-ms-win-appmodel-state-ext-l1-2-0!ReadStateContainerValue` at `0x1800084a6`
- `ext-ms-win-appmodel-state-ext-l1-2-0!ReadStateContainerValue` at `0x180008522`
- `ext-ms-win-appmodel-state-ext-l1-2-0!ReadStateContainerValue` at `0x1800084a6`
- `ext-ms-win-appmodel-state-ext-l1-2-0!ReadStateContainerValue` at `0x180008522`

## string_xrefs

- `0x180008674`: `InternalCreatePropertyValue %ws %u`
- `0x180008773`: `InternalCreatePropertyValue %ws %u`
- `0x180008932`: `InternalCreatePropertyValue %ws %u`
- `0x180008982`: `InternalCreatePropertyValue %ws %u`
- `0x180008809`: `ReadStateContainerValue %ws %u`
- `0x18000889c`: `ReadStateContainerValue %ws %u`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataContainerSettingsServer::Lookup(
        Windows::Storage::ApplicationDataContainerSettingsServer *this,
        HSTRING key,
        IInspectable **value)
{
  HSTRING v5; // rcx
  PCWSTR StringRawBuffer; // rax
  HRESULT v7; // edi
  PCWSTR v9; // rax
  unsigned __int8 *v10; // rsi
  HRESULT v11; // edi
  signed int LastError; // eax
  HRESULT v13; // esi
  unsigned __int8 *v14; // rsi
  unsigned int v15; // ebx
  PCWSTR v16; // rax
  signed int v17; // eax
  HRESULT v18; // r14d
  HRESULT v19; // edi
  unsigned int v20; // ebx
  PCWSTR v21; // rax
  unsigned int v22; // ebx
  PCWSTR v23; // rax
  unsigned int v24; // ebx
  PCWSTR v25; // rax
  unsigned int v26; // ebx
  PCWSTR v27; // rax
  unsigned int v28; // ebx
  PCWSTR v29; // rax
  unsigned int settingValueBytesRequired; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  tag_STATE_VALUE_TYPE settingType; // [rsp+50h] [rbp-B0h] BYREF
  wistd::unique_ptr<unsigned char,wistd::default_delete<unsigned char> > tempValue; // [rsp+58h] [rbp-A8h] BYREF
  wistd::unique_ptr<unsigned char,wistd::default_delete<unsigned char> > settingValue; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 stackBuffer[256]; // [rsp+70h] [rbp-90h] BYREF
  void *retaddr; // [rsp+1A8h] [rbp+A8h]

  string = key;
  settingValueBytesRequired = 256;
  settingType = STATE_VALUE_UNDEFINED;
  settingValue.__ptr_.__value_ = 0;
  Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_START);
  if ( value )
  {
    WinSqmIncrementDWORD(0, 11326, 1);
    v5 = string;
    *value = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v5, 0);
    if ( (unsigned int)ReadStateContainerValue(
                         this->m_containerHandle,
                         StringRawBuffer,
                         &settingType,
                         stackBuffer,
                         &settingValueBytesRequired) )
    {
      v7 = this->InternalCreatePropertyValue(this, &string, stackBuffer, settingValueBytesRequired, settingType, value);
      if ( v7 < 0 )
      {
        v26 = settingValueBytesRequired;
        v27 = WindowsGetStringRawBuffer(string, 0);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0x97u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
          v7,
          "InternalCreatePropertyValue %ws %u",
          v27,
          v26);
      }
LABEL_5:
      Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP);
      return (unsigned int)v7;
    }
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError == 122 )
    {
      if ( !settingValueBytesRequired )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      while ( 1 )
      {
        tempValue.__ptr_.__value_ = (unsigned __int8 *)operator new(settingValueBytesRequired);
        v14 = tempValue.__ptr_.__value_;
        if ( !tempValue.__ptr_.__value_ )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            0xBFu,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
            -2147024882);
          Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP);
          return 2147942414LL;
        }
        v9 = WindowsGetStringRawBuffer(string, 0);
        if ( (unsigned int)ReadStateContainerValue(
                             this->m_containerHandle,
                             v9,
                             &settingType,
                             v14,
                             &settingValueBytesRequired) )
        {
          wistd::unique_ptr<unsigned char,wistd::default_delete<unsigned char>>::swap(&settingValue, &tempValue);
          if ( tempValue.__ptr_.__value_ )
            operator delete(tempValue.__ptr_.__value_);
          v10 = settingValue.__ptr_.__value_;
          v11 = this->InternalCreatePropertyValue(
                  this,
                  &string,
                  settingValue.__ptr_.__value_,
                  settingValueBytesRequired,
                  settingType,
                  value);
          if ( v11 < 0 )
          {
            v15 = settingValueBytesRequired;
            v16 = WindowsGetStringRawBuffer(string, 0);
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0xF7u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
              v11,
              "InternalCreatePropertyValue %ws %u",
              v16,
              v15);
            Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP);
            if ( v10 )
              operator delete(v10);
            return (unsigned int)v11;
          }
          else
          {
            Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP);
            if ( v10 )
              operator delete(v10);
            return 0;
          }
        }
        v17 = GetLastError();
        v18 = v17;
        if ( v17 != 122 )
          break;
        operator delete(v14);
      }
      if ( v17 == 4312 )
      {
        v19 = this->InternalCreatePropertyValue(this, &string, 0, 0, STATE_VALUE_UNDEFINED, value);
        if ( v19 < 0 )
        {
          v20 = settingValueBytesRequired;
          v21 = WindowsGetStringRawBuffer(string, 0);
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            0xD7u,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
            v19,
            "InternalCreatePropertyValue %ws %u",
            v21,
            v20);
        }
        operator delete(v14);
        Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP);
        return (unsigned int)v19;
      }
      else
      {
        if ( v17 > 0 )
          v18 = (unsigned __int16)v17 | 0x80070000;
        Windows::Storage::StateABIHelpers::ReportError(v18, 0xCu);
        if ( v18 == -2147024809 || (WinSqmSetDWORD(0, 11333, (unsigned int)v18), SqmPackageFamilyname(), v18 < 0) )
        {
          v24 = settingValueBytesRequired;
          v25 = WindowsGetStringRawBuffer(string, 0);
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            0xE5u,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
            v18,
            "ReadStateContainerValue %ws %u",
            v25,
            v24);
        }
        if ( v14 )
          operator delete(v14);
        Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP);
        return (unsigned int)v18;
      }
    }
    else
    {
      if ( LastError == 4312 )
      {
        if ( settingType )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        v7 = this->InternalCreatePropertyValue(this, &string, 0, 0, STATE_VALUE_UNDEFINED, value);
        if ( v7 < 0 )
        {
          v28 = settingValueBytesRequired;
          v29 = WindowsGetStringRawBuffer(string, 0);
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            0xA6u,
            "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
            v7,
            "InternalCreatePropertyValue %ws %u",
            v29,
            v28);
        }
        goto LABEL_5;
      }
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      Windows::Storage::StateABIHelpers::ReportError(v13, 0xCu);
      if ( v13 == -2147024809 || (WinSqmSetDWORD(0, 11333, (unsigned int)v13), SqmPackageFamilyname(), v13 < 0) )
      {
        v22 = settingValueBytesRequired;
        v23 = WindowsGetStringRawBuffer(string, 0);
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          0xB6u,
          "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
          v13,
          "ReadStateContainerValue %ws %u",
          v23,
          v22);
      }
      Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP);
      return (unsigned int)v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x83u,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
      -2147024809);
    Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180008410  push    rbp
0x180008412  push    rbx
0x180008413  push    rdi
0x180008414  push    r15
0x180008416  lea     rbp, [rsp-88h]
0x18000841e  sub     rsp, 188h
0x180008425  mov     rax, cs:__security_cookie
0x18000842c  xor     rax, rsp
0x18000842f  mov     [rbp+0A0h+var_30], rax
0x180008433  mov     rdi, this
0x180008436  mov     [rsp+1A0h+string], key
0x18000843b  xor     r15d, r15d
0x18000843e  mov     [rsp+1A0h+settingValueBytesRequired], 100h
0x180008446  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_START; eventDescriptor
0x18000844d  mov     [rsp+1A0h+settingType], r15d
0x180008452  mov     [rsp+1A0h+settingValue.__ptr_.__value_], r15
0x180008457  mov     rbx, value
0x18000845a  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18000845f  test    rbx, rbx
0x180008462  jz      loc_1800088CE
0x180008468  mov     edx, 2C3Eh
0x18000846d  xor     ecx, ecx
0x18000846f  mov     r8d, 1
0x180008475  call    cs:__imp_WinSqmIncrementDWORD
0x18000847b  mov     this, [rsp+1A0h+string]; string
0x180008480  xor     edx, edx; length
0x180008482  mov     [rbx], r15
0x180008485  call    cs:__imp_WindowsGetStringRawBuffer
0x18000848b  lea     this, [rsp+1A0h+settingValueBytesRequired]
0x180008490  mov     key, rax
0x180008493  mov     [rsp+1A0h+formatString], this
0x180008498  lea     r9, [rsp+1A0h+stackBuffer]
0x18000849d  mov     this, [rdi+58h]
0x1800084a1  lea     value, [rsp+1A0h+settingType]
0x1800084a6  call    cs:__imp_ReadStateContainerValue
0x1800084ac  test    eax, eax
0x1800084ae  jz      loc_1800085CA
0x1800084b4  mov     edx, [rsp+1A0h+settingType]
0x1800084b8  lea     value, [rsp+1A0h+stackBuffer]
0x1800084bd  mov     rax, [rdi]
0x1800084c0  mov     this, rdi
0x1800084c3  mov     r9d, [rsp+1A0h+settingValueBytesRequired]
0x1800084c8  mov     [rsp+1A0h+var_178], rbx
0x1800084cd  mov     dword ptr [rsp+1A0h+formatString], edx
0x1800084d1  lea     key, [rsp+1A0h+string]
0x1800084d6  mov     rax, [rax+78h]
0x1800084da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084df  mov     edi, eax
0x1800084e1  test    eax, eax
0x1800084e3  js      loc_180008902
0x1800084e9  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP; eventDescriptor
0x1800084f0  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x1800084f5  mov     eax, edi
0x1800084f7  jmp     loc_1800085B1
0x1800084fc  mov     this, [rsp+1A0h+string]; string
0x180008501  xor     edx, edx; length
0x180008503  call    cs:__imp_WindowsGetStringRawBuffer
0x180008509  lea     this, [rsp+1A0h+settingValueBytesRequired]
0x18000850e  mov     r9, rsi
0x180008511  mov     [rsp+1A0h+formatString], this
0x180008516  lea     value, [rsp+1A0h+settingType]
0x18000851b  mov     this, [rdi+58h]
0x18000851f  mov     key, rax
0x180008522  call    cs:__imp_ReadStateContainerValue
0x180008528  test    eax, eax
0x18000852a  jz      loc_1800086FC
0x180008530  lea     key, [rsp+1A0h+tempValue]; __u
0x180008535  lea     this, [rsp+1A0h+settingValue]; this
0x18000853a  call    ?swap@?$unique_ptr@EU?$default_delete@E@wistd@@@wistd@@QEAAXAEAV12@@Z; wistd::unique_ptr<uchar,wistd::default_delete<uchar>>::swap(wistd::unique_ptr<uchar,wistd::default_delete<uchar>> &)
0x18000853f  mov     this, [rsp+1A0h+tempValue.__ptr_.__value_]; p
0x180008544  test    this, this
0x180008547  jz      short loc_18000854E
0x180008549  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000854e  mov     ecx, [rsp+1A0h+settingType]
0x180008552  lea     key, [rsp+1A0h+string]
0x180008557  mov     rax, [rdi]
0x18000855a  mov     rsi, [rsp+1A0h+settingValue.__ptr_.__value_]
0x18000855f  mov     r9d, [rsp+1A0h+settingValueBytesRequired]
0x180008564  mov     value, rsi
0x180008567  mov     [rsp+1A0h+var_178], rbx
0x18000856c  mov     rax, [rax+78h]
0x180008570  mov     dword ptr [rsp+1A0h+formatString], ecx
0x180008574  mov     this, rdi
0x180008577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000857c  mov     edi, eax
0x18000857e  test    eax, eax
0x180008580  js      loc_180008644
0x180008586  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP; eventDescriptor
0x18000858d  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x180008592  test    rsi, rsi
0x180008595  jz      short loc_18000859F
0x180008597  mov     this, rsi; p
0x18000859a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000859f  xor     eax, eax
0x1800085a1  mov     r14, [rsp+1A0h+var_20]
0x1800085a9  mov     rsi, [rsp+1A0h+arg_18]
0x1800085b1  mov     this, [rbp+0A0h+var_30]
0x1800085b5  xor     this, rsp; StackCookie
0x1800085b8  call    __security_check_cookie
0x1800085bd  add     rsp, 188h
0x1800085c4  pop     r15
0x1800085c6  pop     rdi
0x1800085c7  pop     rbx
0x1800085c8  pop     rbp
0x1800085c9  retn
0x1800085ca  mov     [rsp+1A0h+arg_18], rsi
0x1800085d2  call    cs:__imp_GetLastError
0x1800085d8  mov     esi, eax
0x1800085da  cmp     eax, 7Ah ; 'z'
0x1800085dd  jnz     loc_1800086A5
0x1800085e3  cmp     [rsp+1A0h+settingValueBytesRequired], r15d
0x1800085e8  jz      loc_180008998
0x1800085ee  mov     [rsp+1A0h+var_20], r14
0x1800085f6  mov     ecx, [rsp+1A0h+settingValueBytesRequired]; cb
0x1800085fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800085ff  mov     [rsp+1A0h+tempValue.__ptr_.__value_], rax
0x180008604  mov     rsi, rax
0x180008607  test    rax, rax
0x18000860a  jnz     loc_1800084FC
0x180008610  mov     this, [rbp+0A8h]; callerReturnAddress
0x180008617  lea     value, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000861e  mov     r9d, 8007000Eh; hr
0x180008624  mov     edx, 0BFh; lineNumber
0x180008629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000862e  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP; eventDescriptor
0x180008635  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18000863a  mov     eax, 8007000Eh
0x18000863f  jmp     loc_1800085A1
0x180008644  mov     this, [rsp+1A0h+string]; string
0x180008649  xor     edx, edx; length
0x18000864b  mov     ebx, [rsp+1A0h+settingValueBytesRequired]
0x18000864f  call    cs:__imp_WindowsGetStringRawBuffer
0x180008655  mov     this, [rbp+0A8h]; callerReturnAddress
0x18000865c  lea     value, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\statemanage"...
0x180008663  mov     [rsp+1A0h+var_170], ebx
0x180008667  mov     r9d, edi; hr
0x18000866a  mov     [rsp+1A0h+var_178], rax
0x18000866f  mov     edx, 0F7h; lineNumber
0x180008674  lea     rax, aInternalcreate; "InternalCreatePropertyValue %ws %u"
0x18000867b  mov     [rsp+1A0h+formatString], rax; formatString
0x180008680  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180008685  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP; eventDescriptor
0x18000868c  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x180008691  test    rsi, rsi
0x180008694  jz      short loc_18000869E
0x180008696  mov     this, rsi; p
0x180008699  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000869e  mov     eax, edi
0x1800086a0  jmp     loc_1800085A1
0x1800086a5  cmp     eax, 10D8h
0x1800086aa  jnz     loc_18000879F
0x1800086b0  cmp     [rsp+1A0h+settingType], r15d
0x1800086b5  jnz     loc_180008948
0x1800086bb  mov     rax, [rdi]
0x1800086be  lea     key, [rsp+1A0h+string]
0x1800086c3  mov     [rsp+1A0h+var_178], rbx
0x1800086c8  xor     r9d, r9d
0x1800086cb  xor     r8d, r8d
0x1800086ce  mov     dword ptr [rsp+1A0h+formatString], r15d
0x1800086d3  mov     this, rdi
0x1800086d6  mov     rax, [rax+78h]
0x1800086da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086df  mov     edi, eax
0x1800086e1  test    eax, eax
0x1800086e3  js      loc_180008952
0x1800086e9  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP; eventDescriptor
0x1800086f0  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x1800086f5  mov     eax, edi
0x1800086f7  jmp     loc_1800085A9
0x1800086fc  call    cs:__imp_GetLastError
0x180008702  mov     r14d, eax
0x180008705  cmp     eax, 7Ah ; 'z'
0x180008708  jz      loc_1800089A2
0x18000870e  cmp     eax, 10D8h
0x180008713  jnz     loc_18000882D
0x180008719  mov     rax, [rdi]
0x18000871c  lea     key, [rsp+1A0h+string]
0x180008721  mov     [rsp+1A0h+var_178], rbx
0x180008726  xor     r9d, r9d
0x180008729  xor     r8d, r8d
0x18000872c  mov     dword ptr [rsp+1A0h+formatString], r15d
0x180008731  mov     this, rdi
0x180008734  mov     rax, [rax+78h]
0x180008738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000873d  mov     edi, eax
0x18000873f  test    eax, eax
0x180008741  jns     short loc_180008784
0x180008743  mov     this, [rsp+1A0h+string]; string
0x180008748  xor     edx, edx; length
0x18000874a  mov     ebx, [rsp+1A0h+settingValueBytesRequired]
0x18000874e  call    cs:__imp_WindowsGetStringRawBuffer
0x180008754  mov     this, [rbp+0A8h]; callerReturnAddress
0x18000875b  lea     value, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\statemanage"...
0x180008762  mov     [rsp+1A0h+var_170], ebx
0x180008766  mov     r9d, edi; hr
0x180008769  mov     [rsp+1A0h+var_178], rax
0x18000876e  mov     edx, 0D7h; lineNumber
0x180008773  lea     rax, aInternalcreate; "InternalCreatePropertyValue %ws %u"
0x18000877a  mov     [rsp+1A0h+formatString], rax; formatString
0x18000877f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180008784  mov     this, rsi; p
0x180008787  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000878c  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP; eventDescriptor
0x180008793  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x180008798  mov     eax, edi
0x18000879a  jmp     loc_1800085A1
0x18000879f  test    eax, eax
0x1800087a1  jle     short loc_1800087AC
0x1800087a3  movzx   esi, ax
0x1800087a6  or      esi, 80070000h
0x1800087ac  mov     edx, 0Ch; idsValue
0x1800087b1  mov     ecx, esi; hr
0x1800087b3  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x1800087b8  cmp     esi, 80070057h
0x1800087be  jz      short loc_1800087D9
0x1800087c0  mov     r8d, esi
0x1800087c3  mov     edx, 2C45h
0x1800087c8  xor     ecx, ecx
0x1800087ca  call    cs:__imp_WinSqmSetDWORD
0x1800087d0  call    ?SqmPackageFamilyname@@YAXXZ; SqmPackageFamilyname(void)
0x1800087d5  test    esi, esi
0x1800087d7  jns     short loc_18000881A
0x1800087d9  mov     this, [rsp+1A0h+string]; string
0x1800087de  xor     edx, edx; length
0x1800087e0  mov     ebx, [rsp+1A0h+settingValueBytesRequired]
0x1800087e4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800087ea  mov     this, [rbp+0A8h]; callerReturnAddress
0x1800087f1  lea     value, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800087f8  mov     [rsp+1A0h+var_170], ebx
0x1800087fc  mov     r9d, esi; hr
0x1800087ff  mov     [rsp+1A0h+var_178], rax
0x180008804  mov     edx, 0B6h; lineNumber
0x180008809  lea     rax, aReadstateconta_0; "ReadStateContainerValue %ws %u"
0x180008810  mov     [rsp+1A0h+formatString], rax; formatString
0x180008815  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000881a  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP; eventDescriptor
0x180008821  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x180008826  mov     eax, esi
0x180008828  jmp     loc_1800085A9
0x18000882d  test    eax, eax
0x18000882f  jle     short loc_18000883C
0x180008831  movzx   r14d, ax
0x180008835  or      r14d, 80070000h
0x18000883c  mov     edx, 0Ch; idsValue
0x180008841  mov     ecx, r14d; hr
0x180008844  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180008849  cmp     r14d, 80070057h
0x180008850  jz      short loc_18000886C
0x180008852  mov     r8d, r14d
0x180008855  mov     edx, 2C45h
0x18000885a  xor     ecx, ecx
0x18000885c  call    cs:__imp_WinSqmSetDWORD
0x180008862  call    ?SqmPackageFamilyname@@YAXXZ; SqmPackageFamilyname(void)
0x180008867  test    r14d, r14d
0x18000886a  jns     short loc_1800088AD
0x18000886c  mov     this, [rsp+1A0h+string]; string
0x180008871  xor     edx, edx; length
0x180008873  mov     ebx, [rsp+1A0h+settingValueBytesRequired]
0x180008877  call    cs:__imp_WindowsGetStringRawBuffer
0x18000887d  mov     this, [rbp+0A8h]; callerReturnAddress
0x180008884  lea     value, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000888b  mov     [rsp+1A0h+var_170], ebx
0x18000888f  mov     r9d, r14d; hr
0x180008892  mov     [rsp+1A0h+var_178], rax
0x180008897  mov     edx, 0E5h; lineNumber
0x18000889c  lea     rax, aReadstateconta_0; "ReadStateContainerValue %ws %u"
0x1800088a3  mov     [rsp+1A0h+formatString], rax; formatString
0x1800088a8  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800088ad  test    rsi, rsi
0x1800088b0  jz      short loc_1800088BA
0x1800088b2  mov     this, rsi; p
0x1800088b5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800088ba  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP; eventDescriptor
0x1800088c1  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x1800088c6  mov     eax, r14d
0x1800088c9  jmp     loc_1800085A1
0x1800088ce  mov     this, [rbp+0A8h]; callerReturnAddress
0x1800088d5  lea     value, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800088dc  mov     r9d, 80070057h; hr
0x1800088e2  mov     edx, 83h; lineNumber
0x1800088e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800088ec  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_LOOKUP_STOP; eventDescriptor
0x1800088f3  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x1800088f8  mov     eax, 80070057h
0x1800088fd  jmp     loc_1800085B1
0x180008902  mov     this, [rsp+1A0h+string]; string
0x180008907  xor     edx, edx; length
0x180008909  mov     ebx, [rsp+1A0h+settingValueBytesRequired]
0x18000890d  call    cs:__imp_WindowsGetStringRawBuffer
0x180008913  mov     this, [rbp+0A8h]; callerReturnAddress
0x18000891a  lea     value, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\statemanage"...
0x180008921  mov     [rsp+1A0h+var_170], ebx
0x180008925  mov     r9d, edi; hr
0x180008928  mov     [rsp+1A0h+var_178], rax
0x18000892d  mov     edx, 97h; lineNumber
0x180008932  lea     rax, aInternalcreate; "InternalCreatePropertyValue %ws %u"
0x180008939  mov     [rsp+1A0h+formatString], rax; formatString
0x18000893e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180008943  jmp     loc_1800084E9
0x180008948  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "settingType == StateApiSet::STATE_VALUE_UNDEFINED")
  ... truncated ...
```
