# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::get_Id(uint *)

- ea: `0x18000eb50`
- end: `0x18000eb9f`
- name: `?get_Id@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJPEAI@Z`
- size: `79`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000eb50`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000eb80`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000eb80`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::get_Id(
        __int64 a1,
        _DWORD *a2)
{
  signed __int32 v2; // ecx
  unsigned int v3; // ebx
  signed __int32 v5; // [rsp+30h] [rbp+8h] BYREF

  *a2 = *(_DWORD *)(a1 + 64);
  v2 = *(_DWORD *)(a1 + 56);
  v5 = -2;
  _InterlockedCompareExchange(&v5, v2, -2);
  if ( v5 == 4 )
  {
    v3 = -2147483634;
    RoOriginateError(2147483662LL, 0);
  }
  else
  {
    v3 = 0;
    if ( v5 == -1 )
      return (unsigned int)-2147483623;
  }
  return v3;
}

```

## disassembly

```asm
0x18000eb50  push    rbx
0x18000eb52  sub     rsp, 20h
0x18000eb56  mov     eax, [rcx+40h]
0x18000eb59  mov     [rdx], eax
0x18000eb5b  mov     ecx, [rcx+38h]
0x18000eb5e  mov     [rsp+28h+arg_0], 0FFFFFFFEh
0x18000eb66  mov     eax, [rsp+28h+arg_0]
0x18000eb6a  lock cmpxchg [rsp+28h+arg_0], ecx
0x18000eb70  cmp     [rsp+28h+arg_0], 4
0x18000eb75  jnz     short loc_18000EB88
0x18000eb77  mov     ebx, 8000000Eh
0x18000eb7c  xor     edx, edx
0x18000eb7e  mov     ecx, ebx
0x18000eb80  call    cs:__imp_RoOriginateError
0x18000eb86  jmp     short loc_18000EB97
0x18000eb88  xor     ebx, ebx
0x18000eb8a  mov     eax, 80000019h
0x18000eb8f  cmp     [rsp+28h+arg_0], 0FFFFFFFFh
0x18000eb94  cmovz   ebx, eax
0x18000eb97  mov     eax, ebx
0x18000eb99  add     rsp, 20h
0x18000eb9d  pop     rbx
0x18000eb9e  retn
```
