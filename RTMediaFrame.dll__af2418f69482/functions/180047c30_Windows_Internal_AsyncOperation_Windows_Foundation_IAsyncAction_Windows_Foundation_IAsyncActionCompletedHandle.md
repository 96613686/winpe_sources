# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const GeotagBroker_SetGeotagInBrokerInternalAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180047c30`
- end: `0x180047c65`
- name: `?GetRuntimeClassName@?$AsyncOperation@UIAsyncAction@Foundation@Windows@@UIAsyncActionCompletedHandler@23@VCNoResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncCausalityOptions@$1?GeotagBroker_SetGeotagInBrokerInternalAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180047c70`

## callees

- `0x180047c30`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180047c5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180047c5a`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncAction,Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::CNoResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const GeotagBroker_SetGeotagInBrokerInternalAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(
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
0x180047c30  sub     rsp, 28h
0x180047c34  xor     r9d, r9d
0x180047c37  mov     r8, rdx; string
0x180047c3a  mov     [rdx], r9
0x180047c3d  mov     eax, r9d
0x180047c40  mov     rcx, [rcx+0E8h]; sourceString
0x180047c47  test    rcx, rcx
0x180047c4a  jz      short loc_180047C60
0x180047c4c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180047c50  inc     rdx; length
0x180047c53  cmp     [rcx+rdx*2], r9w
0x180047c58  jnz     short loc_180047C50
0x180047c5a  call    cs:__imp_WindowsCreateString
0x180047c60  add     rsp, 28h
0x180047c64  retn
```
