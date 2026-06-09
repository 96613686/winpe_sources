# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::get_Status(ABI::Windows::Foundation::AsyncStatus *)

- ea: `0x18000ebd0`
- end: `0x18000ec37`
- name: `?get_Status@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJPEAW4AsyncStatus@Foundation@Windows@ABI@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ebd0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000ec18`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000ec18`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::get_Status(
        __int64 a1,
        _DWORD *a2)
{
  signed __int32 v2; // r8d
  signed __int32 v3; // ecx
  unsigned int v4; // ebx
  signed __int32 v6; // [rsp+30h] [rbp+8h] BYREF
  signed __int32 v7; // [rsp+38h] [rbp+10h] BYREF

  v2 = *(_DWORD *)(a1 + 56);
  v7 = -2;
  _InterlockedCompareExchange(&v7, v2, -2);
  *a2 = v7;
  v3 = *(_DWORD *)(a1 + 56);
  v6 = -2;
  _InterlockedCompareExchange(&v6, v3, -2);
  if ( v6 == 4 )
  {
    v4 = -2147483634;
    RoOriginateError(2147483662LL, 0);
  }
  else
  {
    v4 = 0;
    if ( v6 == -1 )
      return (unsigned int)-2147483623;
  }
  return v4;
}

```

## disassembly

```asm
0x18000ebd0  mov     r11, rsp
0x18000ebd3  push    rbx
0x18000ebd4  sub     rsp, 20h
0x18000ebd8  mov     r8d, [rcx+38h]
0x18000ebdc  mov     r9d, 0FFFFFFFEh
0x18000ebe2  mov     [r11+10h], r9d
0x18000ebe6  mov     eax, [rsp+28h+arg_8]
0x18000ebea  lock cmpxchg [r11+10h], r8d
0x18000ebf0  mov     r8d, [r11+10h]
0x18000ebf4  mov     [rdx], r8d
0x18000ebf7  mov     ecx, [rcx+38h]
0x18000ebfa  mov     [r11+8], r9d
0x18000ebfe  mov     eax, [rsp+28h+arg_0]
0x18000ec02  lock cmpxchg [rsp+28h+arg_0], ecx
0x18000ec08  cmp     [rsp+28h+arg_0], 4
0x18000ec0d  jnz     short loc_18000EC20
0x18000ec0f  mov     ebx, 8000000Eh
0x18000ec14  xor     edx, edx
0x18000ec16  mov     ecx, ebx
0x18000ec18  call    cs:__imp_RoOriginateError
0x18000ec1e  jmp     short loc_18000EC2F
0x18000ec20  xor     ebx, ebx
0x18000ec22  mov     eax, 80000019h
0x18000ec27  cmp     [rsp+28h+arg_0], 0FFFFFFFFh
0x18000ec2c  cmovz   ebx, eax
0x18000ec2f  mov     eax, ebx
0x18000ec31  add     rsp, 20h
0x18000ec35  pop     rbx
0x18000ec36  retn
```
