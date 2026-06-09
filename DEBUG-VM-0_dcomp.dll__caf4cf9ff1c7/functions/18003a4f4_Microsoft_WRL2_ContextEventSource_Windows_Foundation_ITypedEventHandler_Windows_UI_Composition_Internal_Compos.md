# Microsoft::WRL2::ContextEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::Internal::CompositionAnimationTriggerPartner *,Windows::UI::Composition::Internal::CompositionAnimationTriggerPartnerFiredEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Destroy(Microsoft::WRL2::ContextSession *)

- ea: `0x18003a4f4`
- end: `0x18003a592`
- name: `?Destroy@?$ContextEventSource@U?$ITypedEventHandler@PEAVCompositionAnimationTriggerPartner@Internal@Composition@UI@Windows@@PEAVCompositionAnimationTriggerPartnerFiredEventArgs@2345@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL2@Microsoft@@QEAAXPEAVContextSession@23@@Z`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18015b4f0`

## callees

- `0x18000c924`
- `0x18003a4f4`
- `0x18003a598`
- `0x18003aa74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a51b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a566`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a51b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003a566`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a57c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a58a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a57c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a58a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a50a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a50a`

## pseudocode

```c
void __fastcall Microsoft::WRL2::ContextEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::Internal::CompositionAnimationTriggerPartner *,Windows::UI::Composition::Internal::CompositionAnimationTriggerPartnerFiredEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Destroy(
        RTL_SRWLOCK *a1,
        Microsoft::WRL2::ContextSession *a2)
{
  int v4; // ebx
  PVOID Ptr; // rax
  struct IUnknown **i; // rsi
  struct IUnknown *v7; // rdx

  v4 = *(_DWORD *)(*((_QWORD *)a2 + 7) + 40LL);
  if ( v4 == GetCurrentThreadId() )
  {
    AcquireSRWLockExclusive(a1 + 2);
    Ptr = a1->Ptr;
    if ( a1->Ptr )
    {
      for ( i = (struct IUnknown **)*((_QWORD *)Ptr + 2); i != *((struct IUnknown ***)Ptr + 3); ++i )
      {
        v7 = *i;
        *i = 0;
        Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker(a2, v7);
        Ptr = a1->Ptr;
      }
      AcquireSRWLockExclusive(a1 + 1);
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::InternalRelease(a1);
      if ( a1 != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(a1 + 1);
    }
    if ( a1 != (RTL_SRWLOCK *)-16LL )
      ReleaseSRWLockExclusive(a1 + 2);
  }
  else
  {
    Microsoft::WRL2::ContextEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::Core::CompositorController *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Destroy_NoLock(a1);
  }
}

```

## disassembly

```asm
0x18003a4f4  push    rbx
0x18003a4f6  push    rbp
0x18003a4f7  push    rsi
0x18003a4f8  push    rdi
0x18003a4f9  sub     rsp, 28h
0x18003a4fd  mov     rax, [rdx+38h]
0x18003a501  mov     rbp, rdx
0x18003a504  mov     rdi, rcx
0x18003a507  mov     ebx, [rax+28h]
0x18003a50a  call    cs:__imp_GetCurrentThreadId
0x18003a510  cmp     ebx, eax
0x18003a512  jnz     short loc_18003A52F
0x18003a514  lea     rbx, [rdi+10h]
0x18003a518  mov     rcx, rbx; SRWLock
0x18003a51b  call    cs:__imp_AcquireSRWLockExclusive
0x18003a521  mov     rax, [rdi]
0x18003a524  test    rax, rax
0x18003a527  jz      short loc_18003A582
0x18003a529  mov     rsi, [rax+10h]
0x18003a52d  jmp     short loc_18003A559
0x18003a52f  mov     rcx, rdi
0x18003a532  call    ?Destroy_NoLock@?$ContextEventSource@U?$ITypedEventHandler@PEAVCompositorController@Core@Composition@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::Core::CompositorController *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Destroy_NoLock(void)
0x18003a537  add     rsp, 28h
0x18003a53b  pop     rdi
0x18003a53c  pop     rsi
0x18003a53d  pop     rbp
0x18003a53e  pop     rbx
0x18003a53f  retn
0x18003a540  mov     rdx, [rsi]; struct IUnknown *
0x18003a543  mov     rcx, rbp; this
0x18003a546  mov     qword ptr [rsi], 0
0x18003a54d  call    ?EnqueueReleaseAndPassOwnershipWorker@ContextSession@WRL2@Microsoft@@AEAAXPEAUIUnknown@@@Z; Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker(IUnknown *)
0x18003a552  mov     rax, [rdi]
0x18003a555  add     rsi, 8
0x18003a559  cmp     rsi, [rax+18h]
0x18003a55d  jnz     short loc_18003A540
0x18003a55f  lea     rsi, [rdi+8]
0x18003a563  mov     rcx, rsi; SRWLock
0x18003a566  call    cs:__imp_AcquireSRWLockExclusive
0x18003a56c  mov     rcx, rdi
0x18003a56f  call    ?InternalRelease@?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::InternalRelease(void)
0x18003a574  test    rsi, rsi
0x18003a577  jz      short loc_18003A582
0x18003a579  mov     rcx, rsi; SRWLock
0x18003a57c  call    cs:__imp_ReleaseSRWLockExclusive
0x18003a582  test    rbx, rbx
0x18003a585  jz      short loc_18003A537
0x18003a587  mov     rcx, rbx; SRWLock
0x18003a58a  call    cs:__imp_ReleaseSRWLockExclusive
0x18003a590  jmp     short loc_18003A537
```
