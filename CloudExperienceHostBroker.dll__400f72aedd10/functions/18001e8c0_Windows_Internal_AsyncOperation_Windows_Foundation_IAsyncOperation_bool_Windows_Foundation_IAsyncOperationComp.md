# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const CloudExperienceHostBroker::Account::VerifyLocalAccountCredsOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18001e8c0`
- end: `0x18001e8f5`
- name: `?GetRuntimeClassName@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncCausalityOptions@$1?VerifyLocalAccountCredsOperationName@Account@CloudExperienceHostBroker@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001e900`

## callees

- `0x18001e8c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001e8ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001e8ea`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const CloudExperienceHostBroker::Account::VerifyLocalAccountCredsOperationName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(
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
0x18001e8c0  sub     rsp, 28h
0x18001e8c4  xor     r9d, r9d
0x18001e8c7  mov     r8, rdx; string
0x18001e8ca  mov     [rdx], r9
0x18001e8cd  mov     eax, r9d
0x18001e8d0  mov     rcx, [rcx+0E8h]; sourceString
0x18001e8d7  test    rcx, rcx
0x18001e8da  jz      short loc_18001E8F0
0x18001e8dc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001e8e0  inc     rdx; length
0x18001e8e3  cmp     [rcx+rdx*2], r9w
0x18001e8e8  jnz     short loc_18001E8E0
0x18001e8ea  call    cs:__imp_WindowsCreateString
0x18001e8f0  add     rsp, 28h
0x18001e8f4  retn
```
