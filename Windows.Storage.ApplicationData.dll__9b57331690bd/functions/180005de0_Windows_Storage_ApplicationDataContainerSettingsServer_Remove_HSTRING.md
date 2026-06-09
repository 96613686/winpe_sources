# Windows::Storage::ApplicationDataContainerSettingsServer::Remove(HSTRING__ *)

- ea: `0x180005de0`
- end: `0x180005ed8`
- name: `?Remove@ApplicationDataContainerSettingsServer@Storage@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `248`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataContainerSettingsServer *this, HSTRING__ *key)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005de0`
- `0x180005ee0`
- `0x180005f40`
- `0x1800092d0`
- `0x180009778`
- `0x18002d0e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e32`
- `ntdll!WinSqmIncrementDWORD` at `0x180005e0c`
- `ntdll!WinSqmIncrementDWORD` at `0x180005e0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005e17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005e67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005e17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180005e67`
- `ext-ms-win-appmodel-state-ext-l1-2-0!DeleteStateContainerValue` at `0x180005e24`
- `ext-ms-win-appmodel-state-ext-l1-2-0!DeleteStateContainerValue` at `0x180005e24`

## string_xrefs

- `0x180005e81`: `DeleteStateContainerValue %ws`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataContainerSettingsServer::Remove(
        Windows::Storage::ApplicationDataContainerSettingsServer *this,
        HSTRING key)
{
  PCWSTR StringRawBuffer; // rax
  signed int LastError; // eax
  signed int v6; // ebx
  Windows::Storage::ApplicationDataCompositeValueServer *v7; // rcx
  PCWSTR v8; // rax
  void *retaddr; // [rsp+38h] [rbp+0h]

  Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_REMOVE_START);
  WinSqmIncrementDWORD(0, 11325, 1);
  StringRawBuffer = WindowsGetStringRawBuffer(key, 0);
  if ( (unsigned int)DeleteStateContainerValue(this->m_containerHandle, StringRawBuffer)
    || (LastError = GetLastError(), v6 = LastError, LastError == 4312) )
  {
    Windows::Storage::ApplicationDataContainerSettingsServer::SignalDataChanged(this);
    v6 = 0;
  }
  else
  {
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    Windows::Storage::StateABIHelpers::ReportError(v6, 0xBu);
    if ( v6 == -2147024809
      || v6 == -2147024882
      || (Windows::Storage::ApplicationDataContainerSettingsServer::SqmWriteSettingError(v7, v6), v6 < 0) )
    {
      v8 = WindowsGetStringRawBuffer(key, 0);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x1F4u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacontainersettings.server.cpp",
        v6,
        "DeleteStateContainerValue %ws",
        v8);
    }
  }
  Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_REMOVE_STOP);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005de0  mov     [rsp+arg_0], rbx
0x180005de5  mov     [rsp+arg_8], rsi
0x180005dea  push    rdi
0x180005deb  sub     rsp, 30h
0x180005def  mov     rdi, this
0x180005df2  mov     rsi, key
0x180005df5  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_REMOVE_START; eventDescriptor
0x180005dfc  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x180005e01  xor     ecx, ecx
0x180005e03  mov     edx, 2C3Dh
0x180005e08  lea     r8d, [this+1]
0x180005e0c  call    cs:__imp_WinSqmIncrementDWORD
0x180005e12  xor     edx, edx; length
0x180005e14  mov     this, rsi; string
0x180005e17  call    cs:__imp_WindowsGetStringRawBuffer
0x180005e1d  mov     this, [rdi+58h]
0x180005e21  mov     key, rax
0x180005e24  call    cs:__imp_DeleteStateContainerValue
0x180005e2a  test    eax, eax
0x180005e2c  jnz     loc_180005EB5
0x180005e32  call    cs:__imp_GetLastError
0x180005e38  mov     ebx, eax
0x180005e3a  cmp     eax, 10D8h
0x180005e3f  jz      short loc_180005EB5
0x180005e41  test    eax, eax
0x180005e43  jle     short loc_180005E4E
0x180005e45  movzx   ebx, ax
0x180005e48  or      ebx, 80070000h
0x180005e4e  mov     edx, 0Bh; idsValue
0x180005e53  mov     ecx, ebx; hr
0x180005e55  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x180005e5a  cmp     ebx, 80070057h
0x180005e60  jnz     short loc_180005ECE
0x180005e62  xor     edx, edx; length
0x180005e64  mov     this, rsi; string
0x180005e67  call    cs:__imp_WindowsGetStringRawBuffer
0x180005e6d  mov     this, [rsp+38h]; callerReturnAddress
0x180005e72  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\statemanage"...
0x180005e79  mov     [rsp+38h+var_10], rax
0x180005e7e  mov     r9d, ebx; hr
0x180005e81  lea     rax, aDeletestatecon_2; "DeleteStateContainerValue %ws"
0x180005e88  mov     edx, 1F4h; lineNumber
0x180005e8d  mov     [rsp+38h+formatString], rax; formatString
0x180005e92  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180005e97  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACONTAINERSETTINGSSERVER_REMOVE_STOP; eventDescriptor
0x180005e9e  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x180005ea3  mov     rsi, [rsp+38h+arg_8]
0x180005ea8  mov     eax, ebx
0x180005eaa  mov     rbx, [rsp+38h+arg_0]
0x180005eaf  add     rsp, 30h
0x180005eb3  pop     rdi
0x180005eb4  retn
0x180005eb5  mov     this, rdi; this
0x180005eb8  call    ?SignalDataChanged@ApplicationDataContainerSettingsServer@Storage@Windows@@IEAAJXZ; Windows::Storage::ApplicationDataContainerSettingsServer::SignalDataChanged(void)
0x180005ebd  xor     ebx, ebx
0x180005ebf  jmp     short loc_180005E97
0x180005ec1  mov     edx, ebx; hr
0x180005ec3  call    ?SqmWriteSettingError@ApplicationDataContainerSettingsServer@Storage@Windows@@AEAAXJ@Z; Windows::Storage::ApplicationDataContainerSettingsServer::SqmWriteSettingError(long)
0x180005ec8  test    ebx, ebx
0x180005eca  jns     short loc_180005E97
0x180005ecc  jmp     short loc_180005E62
0x180005ece  cmp     ebx, 8007000Eh
0x180005ed4  jz      short loc_180005E62
0x180005ed6  jmp     short loc_180005EC1
```
