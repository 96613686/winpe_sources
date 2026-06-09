# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(void)

- ea: `0x180016aa0`
- end: `0x180016adb`
- name: `?CheckValidStateForDelegateCall@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAJXZ`
- size: `59`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800182c0`
- `0x180018330`
- `0x1800183a0`
- `0x180018c00`
- `0x180018ce0`
- `0x180018e10`

## callees

- `0x180016aa0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180016ac7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180016ac7`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::CheckValidStateForDelegateCall(
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
0x180016aa0  sub     rsp, 28h
0x180016aa4  mov     ecx, [rcx+38h]
0x180016aa7  mov     [rsp+28h+arg_0], 0FFFFFFFEh
0x180016aaf  mov     eax, [rsp+28h+arg_0]
0x180016ab3  lock cmpxchg [rsp+28h+arg_0], ecx
0x180016ab9  cmp     [rsp+28h+arg_0], 4
0x180016abe  jnz     short loc_180016AD4
0x180016ac0  xor     edx, edx
0x180016ac2  mov     ecx, 8000000Eh
0x180016ac7  call    cs:__imp_RoOriginateError
0x180016acd  mov     eax, 8000000Eh
0x180016ad2  jmp     short loc_180016AD6
0x180016ad4  xor     eax, eax
0x180016ad6  add     rsp, 28h
0x180016ada  retn
```
