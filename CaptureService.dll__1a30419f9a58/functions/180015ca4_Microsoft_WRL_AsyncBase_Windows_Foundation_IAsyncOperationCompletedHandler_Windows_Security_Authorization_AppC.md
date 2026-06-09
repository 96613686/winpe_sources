# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)

- ea: `0x180015ca4`
- end: `0x180015d06`
- name: `?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z`
- size: `98`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `11`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000f060`
- `0x18000f4d0`
- `0x18000fe60`
- `0x18000ff50`
- `0x180014d10`
- `0x180017768`
- `0x180017974`
- `0x180019720`
- `0x180019810`
- `0x18001a010`
- `0x18001a198`

## callees

- `0x180015ca4`

## pseudocode

```c
bool __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
        __int64 a1,
        signed __int32 a2)
{
  signed __int32 v2; // r8d
  signed __int32 v4; // ecx
  signed __int32 v6; // [rsp+10h] [rbp+10h] BYREF

  v2 = *(_DWORD *)(a1 + 56);
  v6 = -2;
  _InterlockedCompareExchange(&v6, v2, -2);
  switch ( a2 )
  {
    case 0:
      v4 = v6;
      if ( v6 != -1 )
        return 0;
      return v4 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), a2, v4);
    case 1:
    case 2:
    case 3:
      v4 = v6;
      if ( v6 )
        return 0;
      return v4 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), a2, v4);
    case 4:
      v4 = v6;
      if ( (unsigned int)(v6 - 1) <= 3 )
        return v4 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), a2, v4);
      break;
  }
  return 0;
}

```

## disassembly

```asm
0x180015ca4  mov     r8d, [rcx+38h]
0x180015ca8  mov     r9, rcx
0x180015cab  mov     [rsp+arg_8], 0FFFFFFFEh
0x180015cb3  mov     eax, [rsp+arg_8]
0x180015cb7  lock cmpxchg [rsp+arg_8], r8d
0x180015cbe  mov     eax, edx
0x180015cc0  test    edx, edx
0x180015cc2  jz      short loc_180015CFA
0x180015cc4  sub     eax, 1
0x180015cc7  jz      short loc_180015CF0
0x180015cc9  sub     eax, 1
0x180015ccc  jz      short loc_180015CF0
0x180015cce  sub     eax, 1
0x180015cd1  jz      short loc_180015CF0
0x180015cd3  cmp     eax, 1
0x180015cd6  jnz     short loc_180015D03
0x180015cd8  mov     ecx, [rsp+arg_8]
0x180015cdc  lea     eax, [rcx-1]
0x180015cdf  cmp     eax, 3
0x180015ce2  ja      short loc_180015D03
0x180015ce4  mov     eax, ecx
0x180015ce6  lock cmpxchg [r9+38h], edx
0x180015cec  setz    al
0x180015cef  retn
0x180015cf0  mov     ecx, [rsp+arg_8]
0x180015cf4  test    ecx, ecx
0x180015cf6  jnz     short loc_180015D03
0x180015cf8  jmp     short loc_180015CE4
0x180015cfa  mov     ecx, [rsp+arg_8]
0x180015cfe  cmp     ecx, 0FFFFFFFFh
0x180015d01  jz      short loc_180015CE4
0x180015d03  xor     al, al
0x180015d05  retn
```
