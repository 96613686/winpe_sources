# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(void)

- ea: `0x18000f48c`
- end: `0x18000f4c7`
- name: `?CheckValidStateForDelegateCall@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011740`
- `0x1800117b0`
- `0x180011820`
- `0x180013150`
- `0x180013230`
- `0x180013360`
- `0x180019aa0`
- `0x180019ca0`

## callees

- `0x18000f48c`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000f4b3`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000f4b3`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(
        __int64 a1)
{
  signed __int32 v1; // ecx
  signed __int32 v3; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(_DWORD *)(a1 + 56);
  v3 = -2;
  _InterlockedCompareExchange(&v3, v1, -2);
  if ( v3 != 4 )
    return 0;
  RoOriginateError(2147483662LL, 0);
  return 2147483662LL;
}

```

## disassembly

```asm
0x18000f48c  sub     rsp, 28h
0x18000f490  mov     ecx, [rcx+38h]
0x18000f493  mov     [rsp+28h+arg_0], 0FFFFFFFEh
0x18000f49b  mov     eax, [rsp+28h+arg_0]
0x18000f49f  lock cmpxchg [rsp+28h+arg_0], ecx
0x18000f4a5  cmp     [rsp+28h+arg_0], 4
0x18000f4aa  jnz     short loc_18000F4C0
0x18000f4ac  xor     edx, edx
0x18000f4ae  mov     ecx, 8000000Eh
0x18000f4b3  call    cs:__imp_RoOriginateError
0x18000f4b9  mov     eax, 8000000Eh
0x18000f4be  jmp     short loc_18000F4C2
0x18000f4c0  xor     eax, eax
0x18000f4c2  add     rsp, 28h
0x18000f4c6  retn
```
