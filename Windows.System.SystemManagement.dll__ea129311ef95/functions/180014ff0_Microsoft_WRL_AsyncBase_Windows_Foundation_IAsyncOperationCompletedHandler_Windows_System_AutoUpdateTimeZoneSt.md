# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(void)

- ea: `0x180014ff0`
- end: `0x18001502b`
- name: `?CheckValidStateForDelegateCall@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAJXZ`
- size: `59`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800159e0`
- `0x180015a50`
- `0x180015ac0`
- `0x180016470`
- `0x180016550`
- `0x180016680`
- `0x18001a510`
- `0x18001aed0`

## callees

- `0x180014ff0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180015017`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180015017`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(
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
0x180014ff0  sub     rsp, 28h
0x180014ff4  mov     ecx, [rcx+38h]
0x180014ff7  mov     [rsp+28h+arg_0], 0FFFFFFFEh
0x180014fff  mov     eax, [rsp+28h+arg_0]
0x180015003  lock cmpxchg [rsp+28h+arg_0], ecx
0x180015009  cmp     [rsp+28h+arg_0], 4
0x18001500e  jnz     short loc_180015024
0x180015010  xor     edx, edx
0x180015012  mov     ecx, 8000000Eh
0x180015017  call    cs:__imp_RoOriginateError
0x18001501d  mov     eax, 8000000Eh
0x180015022  jmp     short loc_180015026
0x180015024  xor     eax, eax
0x180015026  add     rsp, 28h
0x18001502a  retn
```
