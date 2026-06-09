# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetWeakReference(IWeakReference * *)

- ea: `0x18000c650`
- end: `0x18000c750`
- name: `?GetWeakReference@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJPEAPEAUIWeakReference@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(__int64, struct IUnknown *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800022c0`
- `0x18000a4f8`
- `0x18000c650`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetWeakReference(
        __int64 a1,
        struct IUnknown *a2)
{
  signed __int64 v2; // rsi
  __int64 v5; // r8
  signed __int32 v6; // eax
  __int64 WeakReference; // rax
  struct IUnknownVtbl *v8; // r8
  unsigned __int64 v10; // rdx
  bool i; // zf
  signed __int64 v12; // rax
  signed __int64 v13; // rsi
  __int64 v14; // rdx
  signed __int32 v15; // eax

  v2 = *(_QWORD *)(a1 + 56);
  a2->lpVtbl = 0;
  if ( v2 >= 0 )
  {
    WeakReference = (__int64)Microsoft::WRL::Details::CreateWeakReference((Microsoft::WRL::Details *)(a1 - 168), a2);
    v8 = (struct IUnknownVtbl *)WeakReference;
    if ( !WeakReference )
      return 2147942414LL;
    *(_DWORD *)(WeakReference + 16) = v2;
    v10 = (WeakReference >> 1) | 0x8000000000000000uLL;
    v12 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 56), v10, v2);
    for ( i = v2 == v12; ; i = v12 == v13 )
    {
      v13 = v12;
      if ( i )
      {
        a2->lpVtbl = v8;
        return 0;
      }
      if ( v12 < 0 )
        break;
      LODWORD(v8->Release) = v12;
      v12 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 56), v10, v12);
    }
    v8->QueryInterface = (HRESULT (__stdcall *)(IUnknown *, const IID *const, void **))&Microsoft::WRL::Details::WeakReferenceImpl::`vftable';
    LODWORD(v8->Release) = -1073741823;
    HIDWORD(v8->AddRef) = -1073741823;
    operator delete(v8, (const struct std::nothrow_t *)0x20);
    v14 = 2 * v13;
    do
      v15 = *(_DWORD *)(2 * v13 + 0xC);
    while ( v15 != 0x7FFFFFFF && v15 != _InterlockedCompareExchange((volatile signed __int32 *)(v14 + 12), v15 + 1, v15) );
    a2->lpVtbl = (struct IUnknownVtbl *)v14;
  }
  else
  {
    v5 = 2 * v2;
    do
      v6 = *(_DWORD *)(2 * v2 + 0xC);
    while ( v6 != 0x7FFFFFFF && v6 != _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 12), v6 + 1, v6) );
    a2->lpVtbl = (struct IUnknownVtbl *)v5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c650  mov     [rsp+arg_0], rbx
0x18000c655  mov     [rsp+arg_8], rsi
0x18000c65a  push    rdi
0x18000c65b  sub     rsp, 20h
0x18000c65f  mov     rsi, [rcx+38h]
0x18000c663  mov     rbx, rdx
0x18000c666  mov     qword ptr [rdx], 0
0x18000c66d  mov     rdi, rcx
0x18000c670  test    rsi, rsi
0x18000c673  jns     short loc_18000C69A
0x18000c675  lea     r8, [rsi+rsi]
0x18000c679  mov     r9d, 7FFFFFFFh
0x18000c67f  jmp     short loc_18000C68C
0x18000c681  lea     ecx, [rax+1]
0x18000c684  lock cmpxchg [r8+0Ch], ecx
0x18000c68a  jz      short loc_18000C695
0x18000c68c  mov     eax, [r8+0Ch]
0x18000c690  cmp     eax, r9d
0x18000c693  jnz     short loc_18000C681
0x18000c695  mov     [rdx], r8
0x18000c698  jmp     short loc_18000C6F7
0x18000c69a  add     rcx, 0FFFFFFFFFFFFFF58h; this
0x18000c6a1  call    ?CreateWeakReference@Details@WRL@Microsoft@@YAPEAVWeakReferenceImpl@123@PEAUIUnknown@@@Z; Microsoft::WRL::Details::CreateWeakReference(IUnknown *)
0x18000c6a6  mov     r8, rax
0x18000c6a9  test    rax, rax
0x18000c6ac  jnz     short loc_18000C6B5
0x18000c6ae  mov     eax, 8007000Eh
0x18000c6b3  jmp     short loc_18000C6F9
0x18000c6b5  mov     rax, 8000000000000000h
0x18000c6bf  mov     [r8+10h], esi
0x18000c6c3  mov     rdx, r8
0x18000c6c6  sar     rdx, 1
0x18000c6c9  or      rdx, rax
0x18000c6cc  mov     rax, rsi
0x18000c6cf  lock cmpxchg [rdi+38h], rdx
0x18000c6d5  jmp     short loc_18000C6EF
0x18000c6d7  test    rsi, rsi
0x18000c6da  js      short loc_18000C709
0x18000c6dc  mov     rcx, rsi
0x18000c6df  mov     [r8+10h], esi
0x18000c6e3  mov     rax, rsi
0x18000c6e6  lock cmpxchg [rdi+38h], rdx
0x18000c6ec  cmp     rax, rcx
0x18000c6ef  mov     rsi, rax
0x18000c6f2  jnz     short loc_18000C6D7
0x18000c6f4  mov     [rbx], r8
0x18000c6f7  xor     eax, eax
0x18000c6f9  mov     rbx, [rsp+28h+arg_0]
0x18000c6fe  mov     rsi, [rsp+28h+arg_8]
0x18000c703  add     rsp, 20h
0x18000c707  pop     rdi
0x18000c708  retn
0x18000c709  lea     rax, ??_7WeakReferenceImpl@Details@WRL@Microsoft@@6B@; const Microsoft::WRL::Details::WeakReferenceImpl::`vftable'
0x18000c710  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18000c715  mov     [r8], rax
0x18000c718  mov     rcx, r8; void *
0x18000c71b  mov     eax, 0C0000001h
0x18000c720  mov     [r8+10h], eax
0x18000c724  mov     [r8+0Ch], eax
0x18000c728  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c72d  lea     rdx, [rsi+rsi]
0x18000c731  mov     r9d, 7FFFFFFFh
0x18000c737  jmp     short loc_18000C743
0x18000c739  lea     ecx, [rax+1]
0x18000c73c  lock cmpxchg [rdx+0Ch], ecx
0x18000c741  jz      short loc_18000C74B
0x18000c743  mov     eax, [rdx+0Ch]
0x18000c746  cmp     eax, r9d
0x18000c749  jnz     short loc_18000C739
0x18000c74b  mov     [rbx], rdx
0x18000c74e  jmp     short loc_18000C6F7
```
