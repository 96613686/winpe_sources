# Windows::System::TimeZoneSettingsImpl::AutoUpdateTimeZoneAsync(Windows::Foundation::TimeSpan,Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus> * *)

- ea: `0x180014b10`
- end: `0x180014b56`
- name: `?AutoUpdateTimeZoneAsync@TimeZoneSettingsImpl@System@Windows@@UEAAJUTimeSpan@Foundation@3@PEAPEAU?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@53@@Z`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800135b8`
- `0x180013690`

## string_xrefs

- `0x180014b37`: `Windows.Foundation.IAsyncOperation`1<Windows.System.AutoUpdateTimeZoneStatus>`

## pseudocode

```c
__int64 __fastcall Windows::System::TimeZoneSettingsImpl::AutoUpdateTimeZoneAsync(__int64 a1, __int64 a2, _QWORD *a3)
{
  void (__fastcall ***updated)(_QWORD, __int64); // rax
  __int64 v5; // r9
  int v7; // [rsp+30h] [rbp-18h] BYREF
  __int64 v8; // [rsp+34h] [rbp-14h]
  __int64 v9; // [rsp+58h] [rbp+10h] BYREF

  v9 = a2;
  v7 = 3;
  v8 = 128;
  updated = (void (__fastcall ***)(_QWORD, __int64))Windows::Internal::MakeOpLambda_0_Windows::Internal::CBasicResult_enum_Windows::System::AutoUpdateTimeZoneStatus_2___lambda_6caab501f5dccccab389402d4aaa089d___(&v9);
  return Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,Windows::Internal::CBasicResult<enum Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(
           a3,
           (__int64)&v7,
           (__int64)L"Windows.Foundation.IAsyncOperation`1<Windows.System.AutoUpdateTimeZoneStatus>",
           v5,
           updated);
}

```

## disassembly

```asm
0x180014b10  mov     rax, rsp
0x180014b13  push    rbx
0x180014b14  sub     rsp, 40h
0x180014b18  lea     rcx, [rax+10h]
0x180014b1c  mov     [rax+10h], rdx
0x180014b20  mov     rbx, r8
0x180014b23  mov     dword ptr [rax-18h], 3
0x180014b2a  mov     qword ptr [rax-14h], 80h
0x180014b32  call    Windows__Internal__MakeOpLambda_0_Windows__Internal__CBasicResult_enum_Windows__System__AutoUpdateTimeZoneStatus_2___lambda_6caab501f5dccccab389402d4aaa089d___
0x180014b37  lea     r8, aWindowsFoundat_0; "Windows.Foundation.IAsyncOperation`1<Wi"...
0x180014b3e  mov     [rsp+48h+var_28], rax
0x180014b43  lea     rdx, [rsp+48h+var_18]
0x180014b48  mov     rcx, rbx
0x180014b4b  call    ??$MakeAsyncHelper@U?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@23@UINilDelegate@Internal@3@V?$CBasicResult@W4AutoUpdateTimeZoneStatus@System@Windows@@$01@63@VComTaskPoolHandler@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@YAJPEAPEAU?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@1@$$QEAVComTaskPoolHandler@01@QEBGW4TrustLevel@@PEAV?$AsyncCallbackBase@V?$CBasicResult@W4AutoUpdateTimeZoneStatus@System@Windows@@$01@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncHelper<Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,Windows::Internal::CBasicResult<Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>(Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus> * *,Windows::Internal::ComTaskPoolHandler &&,ushort const * const,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CBasicResult<Windows::System::AutoUpdateTimeZoneStatus,2>> *)
0x180014b50  add     rsp, 40h
0x180014b54  pop     rbx
0x180014b55  retn
```
