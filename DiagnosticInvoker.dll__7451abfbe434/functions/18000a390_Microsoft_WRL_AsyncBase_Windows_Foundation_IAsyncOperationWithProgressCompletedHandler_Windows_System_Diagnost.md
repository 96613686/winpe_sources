# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Close(void)

- ea: `0x18000a390`
- end: `0x18000a40d`
- name: `?Close@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJXZ`
- size: `125`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a390`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000a3ff`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000a3ff`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Close(
        volatile signed __int32 *a1)
{
  signed __int32 v1; // edx
  signed __int32 v2; // eax
  __int64 v3; // rdx
  unsigned int v4; // ebx
  signed __int32 v5; // ecx
  signed __int32 v7; // [rsp+30h] [rbp+8h] BYREF

  v1 = *((_DWORD *)a1 + 14);
  v7 = -2;
  _InterlockedCompareExchange(&v7, v1, -2);
  v2 = v7;
  v3 = (unsigned int)(v7 - 1);
  if ( (unsigned int)v3 <= 3 && v2 == _InterlockedCompareExchange(a1 + 14, 4, v7) )
  {
    v4 = 0;
    (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64))(*(_QWORD *)a1 + 144LL))(a1, v3, 4);
  }
  else
  {
    v5 = *((_DWORD *)a1 + 14);
    v7 = -2;
    _InterlockedCompareExchange(&v7, v5, -2);
    if ( v7 == 4 )
    {
      return 0;
    }
    else
    {
      v4 = -2147483635;
      RoOriginateError(2147483661LL, 0);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000a390  push    rbx
0x18000a392  sub     rsp, 20h
0x18000a396  mov     edx, [rcx+38h]
0x18000a399  mov     r9d, 0FFFFFFFEh
0x18000a39f  mov     [rsp+28h+arg_0], r9d
0x18000a3a4  mov     eax, [rsp+28h+arg_0]
0x18000a3a8  lock cmpxchg [rsp+28h+arg_0], edx
0x18000a3ae  mov     eax, [rsp+28h+arg_0]
0x18000a3b2  lea     r8d, [r9+6]
0x18000a3b6  lea     edx, [rax-1]
0x18000a3b9  cmp     edx, 3
0x18000a3bc  ja      short loc_18000A3D9
0x18000a3be  lock cmpxchg [rcx+38h], r8d
0x18000a3c4  jnz     short loc_18000A3D9
0x18000a3c6  mov     rax, [rcx]
0x18000a3c9  xor     ebx, ebx
0x18000a3cb  mov     rax, [rax+90h]
0x18000a3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d7  jmp     short loc_18000A405
0x18000a3d9  mov     ecx, [rcx+38h]
0x18000a3dc  mov     [rsp+28h+arg_0], r9d
0x18000a3e1  mov     eax, [rsp+28h+arg_0]
0x18000a3e5  lock cmpxchg [rsp+28h+arg_0], ecx
0x18000a3eb  cmp     [rsp+28h+arg_0], r8d
0x18000a3f0  jnz     short loc_18000A3F6
0x18000a3f2  xor     ebx, ebx
0x18000a3f4  jmp     short loc_18000A405
0x18000a3f6  mov     ebx, 8000000Dh
0x18000a3fb  xor     edx, edx
0x18000a3fd  mov     ecx, ebx
0x18000a3ff  call    cs:__imp_RoOriginateError
0x18000a405  mov     eax, ebx
0x18000a407  add     rsp, 20h
0x18000a40b  pop     rbx
0x18000a40c  retn
```
