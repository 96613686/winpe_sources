# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::get_ErrorCode(long *)

- ea: `0x18000eab0`
- end: `0x18000eb41`
- name: `?get_ErrorCode@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJPEAJ@Z`
- size: `145`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000eab0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000eb2e`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000eb2e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000eae8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000eae8`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::get_ErrorCode(
        __int64 a1,
        volatile signed __int32 *a2)
{
  unsigned int v3; // ebx
  signed __int32 v5; // [rsp+30h] [rbp+8h] BYREF

  v5 = -2;
  _InterlockedCompareExchange(&v5, *(_DWORD *)(a1 + 56), -2);
  if ( v5 == 4 )
  {
    v3 = -2147483634;
    RoOriginateError(2147483662LL, 0);
LABEL_6:
    *a2 = v3;
    return v3;
  }
  if ( v5 == -1 )
  {
    v3 = -2147483623;
    goto LABEL_6;
  }
  v5 = -2;
  v3 = 0;
  _InterlockedCompareExchange(&v5, *(_DWORD *)(a1 + 56), -2);
  if ( v5 != 3 )
    goto LABEL_6;
  _InterlockedCompareExchange(a2, *(_DWORD *)(a1 + 60), *a2);
  if ( *(_QWORD *)(a1 + 48) )
    SetRestrictedErrorInfo();
  return v3;
}

```

## disassembly

```asm
0x18000eab0  mov     [rsp+arg_8], rbx
0x18000eab5  push    rdi
0x18000eab6  sub     rsp, 20h
0x18000eaba  mov     rdi, rdx
0x18000eabd  mov     rdx, rcx
0x18000eac0  mov     ecx, 0FFFFFFFEh
0x18000eac5  mov     [rsp+28h+arg_0], ecx
0x18000eac9  mov     r8d, [rdx+38h]
0x18000eacd  mov     eax, [rsp+28h+arg_0]
0x18000ead1  lock cmpxchg [rsp+28h+arg_0], r8d
0x18000ead8  cmp     [rsp+28h+arg_0], 4
0x18000eadd  jnz     short loc_18000EAF0
0x18000eadf  mov     ebx, 8000000Eh
0x18000eae4  xor     edx, edx
0x18000eae6  mov     ecx, ebx
0x18000eae8  call    cs:__imp_RoOriginateError
0x18000eaee  jmp     short loc_18000EB18
0x18000eaf0  cmp     [rsp+28h+arg_0], 0FFFFFFFFh
0x18000eaf5  jnz     short loc_18000EAFE
0x18000eaf7  mov     ebx, 80000019h
0x18000eafc  jmp     short loc_18000EB18
0x18000eafe  mov     [rsp+28h+arg_0], ecx
0x18000eb02  xor     ebx, ebx
0x18000eb04  mov     ecx, [rdx+38h]
0x18000eb07  mov     eax, [rsp+28h+arg_0]
0x18000eb0b  lock cmpxchg [rsp+28h+arg_0], ecx
0x18000eb11  cmp     [rsp+28h+arg_0], 3
0x18000eb16  jz      short loc_18000EB1C
0x18000eb18  mov     [rdi], ebx
0x18000eb1a  jmp     short loc_18000EB34
0x18000eb1c  mov     eax, [rdi]
0x18000eb1e  mov     ecx, [rdx+3Ch]
0x18000eb21  lock cmpxchg [rdi], ecx
0x18000eb25  mov     rcx, [rdx+30h]
0x18000eb29  test    rcx, rcx
0x18000eb2c  jz      short loc_18000EB34
0x18000eb2e  call    cs:__imp_SetRestrictedErrorInfo
0x18000eb34  mov     eax, ebx
0x18000eb36  mov     rbx, [rsp+28h+arg_8]
0x18000eb3b  add     rsp, 20h
0x18000eb3f  pop     rdi
0x18000eb40  retn
```
