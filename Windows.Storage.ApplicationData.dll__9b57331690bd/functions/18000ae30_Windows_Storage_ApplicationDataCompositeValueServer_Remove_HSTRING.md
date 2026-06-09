# Windows::Storage::ApplicationDataCompositeValueServer::Remove(HSTRING__ *)

- ea: `0x18000ae30`
- end: `0x18000af2d`
- name: `?Remove@ApplicationDataCompositeValueServer@Storage@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `253`
- prototype: `HRESULT __fastcall(Windows::Storage::ApplicationDataCompositeValueServer *this, HSTRING__ *key)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005ee0`
- `0x1800092d0`
- `0x180009778`
- `0x18000ae30`
- `0x18002d0e4`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aeb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aeb0`
- `ntdll!WinSqmIncrementDWORD` at `0x18000ae5c`
- `ntdll!WinSqmIncrementDWORD` at `0x18000ae5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ae67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000aef8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000ae67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000aef8`
- `ext-ms-win-appmodel-state-ext-l1-2-0!DeleteStateAtomValue` at `0x18000ae74`
- `ext-ms-win-appmodel-state-ext-l1-2-0!DeleteStateAtomValue` at `0x18000ae74`

## string_xrefs

- `0x18000af03`: `onecoreuap\base\appmodel\statemanager\winrt\lib\windows.storage.applicationdatacompositevalue.server.cpp`
- `0x18000af12`: `DeleteStateAtomValue %ws`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataCompositeValueServer::Remove(
        Windows::Storage::ApplicationDataCompositeValueServer *this,
        HSTRING key)
{
  PCWSTR StringRawBuffer; // rax
  signed int v5; // ebx
  signed int LastError; // eax
  Windows::Storage::ApplicationDataCompositeValueServer *v8; // rcx
  PCWSTR v9; // rax
  void *retaddr; // [rsp+38h] [rbp+0h]

  Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_REMOVE_START);
  WinSqmIncrementDWORD(0, 11325, 1);
  StringRawBuffer = WindowsGetStringRawBuffer(key, 0);
  if ( (unsigned int)DeleteStateAtomValue(this->atomHandle, StringRawBuffer)
    || (LastError = GetLastError(), v5 = LastError, LastError == 4312) )
  {
    this->SignalDataChanged(this);
    v5 = 0;
  }
  else
  {
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    Windows::Storage::StateABIHelpers::ReportError(v5, 0x10u);
    if ( v5 < 0 )
    {
      if ( v5 != -2147024809 && v5 != -2147024882 )
        Windows::Storage::ApplicationDataContainerSettingsServer::SqmWriteSettingError(v8, v5);
      v9 = WindowsGetStringRawBuffer(key, 0);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        0x1D7u,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatacompositevalue.server.cpp",
        v5,
        "DeleteStateAtomValue %ws",
        v9);
    }
  }
  Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(&APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_REMOVE_STOP);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000ae30  mov     [rsp+arg_0], rbx
0x18000ae35  mov     [rsp+arg_8], rsi
0x18000ae3a  push    rdi
0x18000ae3b  sub     rsp, 30h
0x18000ae3f  mov     rdi, this
0x18000ae42  mov     rsi, key
0x18000ae45  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_REMOVE_START; eventDescriptor
0x18000ae4c  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18000ae51  xor     ecx, ecx
0x18000ae53  mov     edx, 2C3Dh
0x18000ae58  lea     r8d, [this+1]
0x18000ae5c  call    cs:__imp_WinSqmIncrementDWORD
0x18000ae62  xor     edx, edx; length
0x18000ae64  mov     this, rsi; string
0x18000ae67  call    cs:__imp_WindowsGetStringRawBuffer
0x18000ae6d  mov     this, [rdi+60h]
0x18000ae71  mov     key, rax
0x18000ae74  call    cs:__imp_DeleteStateAtomValue
0x18000ae7a  test    eax, eax
0x18000ae7c  jz      short loc_18000AEB0
0x18000ae7e  mov     rax, [rdi]
0x18000ae81  mov     this, rdi
0x18000ae84  mov     rax, [rax+88h]
0x18000ae8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae90  xor     ebx, ebx
0x18000ae92  lea     this, APPMODELSTATE_WINRT_APPLICATIONDATACOMPOSITEVALUESERVER_REMOVE_STOP; eventDescriptor
0x18000ae99  call    ?SetPerformanceMarker@Logging@StateABIHelpers@Storage@Windows@@SAJPEBU_EVENT_DESCRIPTOR@@@Z; Windows::Storage::StateABIHelpers::Logging::SetPerformanceMarker(_EVENT_DESCRIPTOR const *)
0x18000ae9e  mov     rsi, [rsp+38h+arg_8]
0x18000aea3  mov     eax, ebx
0x18000aea5  mov     rbx, [rsp+38h+arg_0]
0x18000aeaa  add     rsp, 30h
0x18000aeae  pop     rdi
0x18000aeaf  retn
0x18000aeb0  call    cs:__imp_GetLastError
0x18000aeb6  mov     ebx, eax
0x18000aeb8  cmp     eax, 10D8h
0x18000aebd  jz      short loc_18000AE7E
0x18000aebf  test    eax, eax
0x18000aec1  jle     short loc_18000AECC
0x18000aec3  movzx   ebx, ax
0x18000aec6  or      ebx, 80070000h
0x18000aecc  mov     edx, 10h; idsValue
0x18000aed1  mov     ecx, ebx; hr
0x18000aed3  call    ?ReportError@StateABIHelpers@Storage@Windows@@YAXJG@Z; Windows::Storage::StateABIHelpers::ReportError(long,ushort)
0x18000aed8  test    ebx, ebx
0x18000aeda  jns     short loc_18000AE92
0x18000aedc  cmp     ebx, 80070057h
0x18000aee2  jz      short loc_18000AEF3
0x18000aee4  cmp     ebx, 8007000Eh
0x18000aeea  jz      short loc_18000AEF3
0x18000aeec  mov     edx, ebx; hr
0x18000aeee  call    ?SqmWriteSettingError@ApplicationDataContainerSettingsServer@Storage@Windows@@AEAAXJ@Z; Windows::Storage::ApplicationDataContainerSettingsServer::SqmWriteSettingError(long)
0x18000aef3  xor     edx, edx; length
0x18000aef5  mov     this, rsi; string
0x18000aef8  call    cs:__imp_WindowsGetStringRawBuffer
0x18000aefe  mov     this, [rsp+38h]; callerReturnAddress
0x18000af03  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\statemanage"...
0x18000af0a  mov     [rsp+38h+var_10], rax
0x18000af0f  mov     r9d, ebx; hr
0x18000af12  lea     rax, aDeletestateato_0; "DeleteStateAtomValue %ws"
0x18000af19  mov     edx, 1D7h; lineNumber
0x18000af1e  mov     [rsp+38h+formatString], rax; formatString
0x18000af23  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000af28  jmp     loc_18000AE92
```
