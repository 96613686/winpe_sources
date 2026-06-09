# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18000b5e0`
- end: `0x18000b615`
- name: `?GetRuntimeClassName@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b620`

## callees

- `0x18000b5e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000b60a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000b60a`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(
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
0x18000b5e0  sub     rsp, 28h
0x18000b5e4  xor     r9d, r9d
0x18000b5e7  mov     r8, rdx; string
0x18000b5ea  mov     [rdx], r9
0x18000b5ed  mov     eax, r9d
0x18000b5f0  mov     rcx, [rcx+0E8h]; sourceString
0x18000b5f7  test    rcx, rcx
0x18000b5fa  jz      short loc_18000B610
0x18000b5fc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000b600  inc     rdx; length
0x18000b603  cmp     [rcx+rdx*2], r9w
0x18000b608  jnz     short loc_18000B600
0x18000b60a  call    cs:__imp_WindowsCreateString
0x18000b610  add     rsp, 28h
0x18000b614  retn
```
