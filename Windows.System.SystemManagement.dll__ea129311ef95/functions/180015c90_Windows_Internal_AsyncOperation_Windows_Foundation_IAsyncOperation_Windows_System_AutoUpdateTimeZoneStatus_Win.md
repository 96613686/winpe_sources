# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::CBasicResult<Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180015c90`
- end: `0x180015cc5`
- name: `?GetRuntimeClassName@?$AsyncOperation@U?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@23@V?$CBasicResult@W4AutoUpdateTimeZoneStatus@System@Windows@@$01@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180015cd0`

## callees

- `0x180015c90`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180015cba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180015cba`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::CBasicResult<enum Windows::System::AutoUpdateTimeZoneStatus,2>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  HRESULT result; // eax
  const WCHAR *v4; // rcx
  __int64 v5; // rdx

  *a2 = 0;
  result = 0;
  v4 = *(const WCHAR **)(a1 + 232);
  if ( v4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( v4[v5] );
    return WindowsCreateString(v4, v5, a2);
  }
  return result;
}

```

## disassembly

```asm
0x180015c90  sub     rsp, 28h
0x180015c94  xor     r9d, r9d
0x180015c97  mov     r8, rdx; string
0x180015c9a  mov     [rdx], r9
0x180015c9d  mov     eax, r9d
0x180015ca0  mov     rcx, [rcx+0E8h]; sourceString
0x180015ca7  test    rcx, rcx
0x180015caa  jz      short loc_180015CC0
0x180015cac  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180015cb0  inc     rdx; length
0x180015cb3  cmp     [rcx+rdx*2], r9w
0x180015cb8  jnz     short loc_180015CB0
0x180015cba  call    cs:__imp_WindowsCreateString
0x180015cc0  add     rsp, 28h
0x180015cc4  retn
```
