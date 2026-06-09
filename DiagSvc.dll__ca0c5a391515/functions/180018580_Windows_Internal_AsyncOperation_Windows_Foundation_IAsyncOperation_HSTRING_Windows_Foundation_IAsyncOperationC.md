# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180018580`
- end: `0x1800185b5`
- name: `?GetRuntimeClassName@?$AsyncOperation@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@23@VCHSTRINGResult@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800185c0`

## callees

- `0x180018580`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800185aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800185aa`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::CHSTRINGResult,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetRuntimeClassName(
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
0x180018580  sub     rsp, 28h
0x180018584  xor     r9d, r9d
0x180018587  mov     r8, rdx; string
0x18001858a  mov     [rdx], r9
0x18001858d  mov     eax, r9d
0x180018590  mov     rcx, [rcx+0E8h]; sourceString
0x180018597  test    rcx, rcx
0x18001859a  jz      short loc_1800185B0
0x18001859c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800185a0  inc     rdx; length
0x1800185a3  cmp     [rcx+rdx*2], r9w
0x1800185a8  jnz     short loc_1800185A0
0x1800185aa  call    cs:__imp_WindowsCreateString
0x1800185b0  add     rsp, 28h
0x1800185b4  retn
```
