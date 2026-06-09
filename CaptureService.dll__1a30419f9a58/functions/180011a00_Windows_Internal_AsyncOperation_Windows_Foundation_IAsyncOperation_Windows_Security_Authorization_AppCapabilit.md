# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180011a00`
- end: `0x180011a35`
- name: `?GetRuntimeClassName@?$AsyncOperation@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@23@V?$CBasicResult@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@$02@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180011a40`

## callees

- `0x180011a00`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180011a2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180011a2a`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(
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
0x180011a00  sub     rsp, 28h
0x180011a04  xor     r9d, r9d
0x180011a07  mov     r8, rdx; string
0x180011a0a  mov     [rdx], r9
0x180011a0d  mov     eax, r9d
0x180011a10  mov     rcx, [rcx+0E8h]; sourceString
0x180011a17  test    rcx, rcx
0x180011a1a  jz      short loc_180011A30
0x180011a1c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180011a20  inc     rdx; length
0x180011a23  cmp     [rcx+rdx*2], r9w
0x180011a28  jnz     short loc_180011A20
0x180011a2a  call    cs:__imp_WindowsCreateString
0x180011a30  add     rsp, 28h
0x180011a34  retn
```
