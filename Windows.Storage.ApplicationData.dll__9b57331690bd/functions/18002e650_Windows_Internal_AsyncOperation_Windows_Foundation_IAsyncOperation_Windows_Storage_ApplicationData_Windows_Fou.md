# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x18002e650`
- end: `0x18002e685`
- name: `?GetRuntimeClassName@?$AsyncOperation@U?$IAsyncOperation@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@23@V?$CMarshaledInterfaceResult@UIApplicationData@Storage@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `53`
- prototype: `HRESULT __fastcall(Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this, HSTRING__ **phstrRuntimeName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e690`

## callees

- `0x18002e650`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002e67a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002e67a`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(
        Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Storage::ApplicationData *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Storage::IApplicationData>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this,
        HSTRING__ **phstrRuntimeName)
{
  HRESULT result; // eax
  const wchar_t *refCount; // rcx
  __int64 v5; // rdx

  *phstrRuntimeName = 0;
  result = 0;
  refCount = (const wchar_t *)this->refCount_.refCount;
  if ( refCount )
  {
    v5 = -1;
    do
      ++v5;
    while ( refCount[v5] );
    return WindowsCreateString(refCount, v5, phstrRuntimeName);
  }
  return result;
}

```

## disassembly

```asm
0x18002e650  sub     rsp, 28h
0x18002e654  xor     r9d, r9d
0x18002e657  mov     r8, phstrRuntimeName; string
0x18002e65a  mov     [phstrRuntimeName], r9
0x18002e65d  mov     eax, r9d
0x18002e660  mov     this, [this+0E8h]; sourceString
0x18002e667  test    this, this
0x18002e66a  jz      short loc_18002E680
0x18002e66c  or      phstrRuntimeName, 0FFFFFFFFFFFFFFFFh
0x18002e670  inc     phstrRuntimeName; length
0x18002e673  cmp     [this+phstrRuntimeName*2], r9w
0x18002e678  jnz     short loc_18002E670
0x18002e67a  call    cs:__imp_WindowsCreateString
0x18002e680  add     rsp, 28h
0x18002e684  retn
```
