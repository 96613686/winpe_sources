# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(void)

- ea: `0x18000d730`
- end: `0x18000d7c6`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `150`
- prototype: `__int64 __fastcall(volatile signed __int64 *)`
- caller_count: `8`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000d510`
- `0x18000d7d0`
- `0x18000d7e0`
- `0x18000d800`
- `0x18000d820`
- `0x18000d840`
- `0x18000d860`
- `0x18000d880`

## callees

- `0x18000d730`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::Release(
        volatile signed __int64 *a1)
{
  signed __int64 v1; // rdx
  unsigned __int32 v2; // ebx
  bool v3; // zf
  signed __int64 v4; // rax
  signed __int32 v5; // r8d

  v1 = *((_QWORD *)a1 + 28);
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return 2147483646;
    v2 = v1 - 1;
    v4 = _InterlockedCompareExchange64(a1 + 28, v1 - 1, v1);
    v3 = v1 == v4;
    v1 = v4;
    if ( v3 )
      goto LABEL_10;
  }
  do
    v5 = *(_DWORD *)(2 * v1 + 0x10);
  while ( v5 != 0x7FFFFFFF && v5 != _InterlockedCompareExchange((volatile signed __int32 *)(2 * v1 + 16), v5 - 1, v5) );
  v2 = v5 - 1;
LABEL_10:
  if ( !v2 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int64 *, __int64))(*a1 + 88))(a1, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x18000d730  push    rbx
0x18000d732  sub     rsp, 20h
0x18000d736  mov     rdx, [rcx+0E0h]
0x18000d73d  mov     r9, rcx
0x18000d740  mov     r10d, 7FFFFFFFh
0x18000d746  test    rdx, rdx
0x18000d749  js      short loc_18000D77D
0x18000d74b  cmp     edx, r10d
0x18000d74e  jz      short loc_18000D767
0x18000d750  lea     rbx, [rdx-1]
0x18000d754  mov     rax, rdx
0x18000d757  lock cmpxchg [rcx+0E0h], rbx
0x18000d760  mov     rdx, rax
0x18000d763  jnz     short loc_18000D746
0x18000d765  jmp     short loc_18000D78B
0x18000d767  mov     ebx, 7FFFFFFEh
0x18000d76c  jmp     short loc_18000D7BE
0x18000d76e  lea     ecx, [r8-1]
0x18000d772  mov     eax, r8d
0x18000d775  lock cmpxchg [rdx+rdx+10h], ecx
0x18000d77b  jz      short loc_18000D787
0x18000d77d  mov     r8d, [rdx+rdx+10h]
0x18000d782  cmp     r8d, r10d
0x18000d785  jnz     short loc_18000D76E
0x18000d787  lea     ebx, [r8-1]
0x18000d78b  test    ebx, ebx
0x18000d78d  jnz     short loc_18000D7BE
0x18000d78f  test    r9, r9
0x18000d792  jz      short loc_18000D7A6
0x18000d794  mov     rax, [r9]
0x18000d797  lea     edx, [rbx+1]
0x18000d79a  mov     rcx, r9
0x18000d79d  mov     rax, [rax+58h]
0x18000d7a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7a6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000d7ad  test    rcx, rcx
0x18000d7b0  jz      short loc_18000D7BE
0x18000d7b2  mov     rdx, [rcx]
0x18000d7b5  mov     rax, [rdx+10h]
0x18000d7b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7be  mov     eax, ebx
0x18000d7c0  add     rsp, 20h
0x18000d7c4  pop     rbx
0x18000d7c5  retn
```
