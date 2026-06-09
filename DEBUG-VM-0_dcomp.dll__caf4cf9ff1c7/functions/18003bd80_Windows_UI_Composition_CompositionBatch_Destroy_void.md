# Windows::UI::Composition::CompositionBatch::Destroy(void)

- ea: `0x18003bd80`
- end: `0x18003be31`
- name: `?Destroy@CompositionBatch@Composition@UI@Windows@@UEAAXXZ`
- size: `177`
- prototype: `void __fastcall(Windows::UI::Composition::CompositionBatch *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b1e0`
- `0x18000c924`
- `0x18003a598`
- `0x18003aa74`
- `0x18003bd80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bdb1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bdeb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bdb1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bdeb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003be01`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003be0f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003be01`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003be0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bda0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bda0`

## pseudocode

```c
void __fastcall Windows::UI::Composition::CompositionBatch::Destroy(Windows::UI::Composition::CompositionBatch *this)
{
  Microsoft::WRL2::ContextSession *v1; // r14
  RTL_SRWLOCK *v2; // rdi
  int v4; // ebx
  PVOID Ptr; // rax
  struct IUnknown **i; // rsi
  struct IUnknown *v7; // rdx

  v1 = (Microsoft::WRL2::ContextSession *)*((_QWORD *)this + 3);
  v2 = (RTL_SRWLOCK *)((char *)this + 168);
  v4 = *(_DWORD *)(*((_QWORD *)v1 + 7) + 40LL);
  if ( v4 == GetCurrentThreadId() )
  {
    AcquireSRWLockExclusive(v2 + 2);
    Ptr = v2->Ptr;
    if ( v2->Ptr )
    {
      for ( i = (struct IUnknown **)*((_QWORD *)Ptr + 2); i != *((struct IUnknown ***)Ptr + 3); ++i )
      {
        v7 = *i;
        *i = 0;
        Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker(v1, v7);
        Ptr = v2->Ptr;
      }
      AcquireSRWLockExclusive(v2 + 1);
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::InternalRelease(v2);
      if ( v2 != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(v2 + 1);
    }
    if ( v2 != (RTL_SRWLOCK *)-16LL )
      ReleaseSRWLockExclusive(v2 + 2);
  }
  else
  {
    Microsoft::WRL2::ContextEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::Core::CompositorController *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Destroy_NoLock(v2);
  }
  Windows::UI::Composition::CompositionObject::Destroy(this);
}

```

## disassembly

```asm
0x18003bd80  push    rbx
0x18003bd82  push    rbp
0x18003bd83  push    rsi
0x18003bd84  push    rdi
0x18003bd85  push    r14
0x18003bd87  sub     rsp, 20h
0x18003bd8b  mov     r14, [rcx+18h]
0x18003bd8f  lea     rdi, [rcx+0A8h]
0x18003bd96  mov     rbp, rcx
0x18003bd99  mov     rax, [r14+38h]
0x18003bd9d  mov     ebx, [rax+28h]
0x18003bda0  call    cs:__imp_GetCurrentThreadId
0x18003bda6  cmp     ebx, eax
0x18003bda8  jnz     short loc_18003BE17
0x18003bdaa  lea     rbx, [rdi+10h]
0x18003bdae  mov     rcx, rbx; SRWLock
0x18003bdb1  call    cs:__imp_AcquireSRWLockExclusive
0x18003bdb7  mov     rax, [rdi]
0x18003bdba  test    rax, rax
0x18003bdbd  jz      short loc_18003BE07
0x18003bdbf  mov     rsi, [rax+10h]
0x18003bdc3  jmp     short loc_18003BDDE
0x18003bdc5  mov     rdx, [rsi]; struct IUnknown *
0x18003bdc8  mov     rcx, r14; this
0x18003bdcb  mov     qword ptr [rsi], 0
0x18003bdd2  call    ?EnqueueReleaseAndPassOwnershipWorker@ContextSession@WRL2@Microsoft@@AEAAXPEAUIUnknown@@@Z; Microsoft::WRL2::ContextSession::EnqueueReleaseAndPassOwnershipWorker(IUnknown *)
0x18003bdd7  mov     rax, [rdi]
0x18003bdda  add     rsi, 8
0x18003bdde  cmp     rsi, [rax+18h]
0x18003bde2  jnz     short loc_18003BDC5
0x18003bde4  lea     rsi, [rdi+8]
0x18003bde8  mov     rcx, rsi; SRWLock
0x18003bdeb  call    cs:__imp_AcquireSRWLockExclusive
0x18003bdf1  mov     rcx, rdi
0x18003bdf4  call    ?InternalRelease@?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::InternalRelease(void)
0x18003bdf9  test    rsi, rsi
0x18003bdfc  jz      short loc_18003BE07
0x18003bdfe  mov     rcx, rsi; SRWLock
0x18003be01  call    cs:__imp_ReleaseSRWLockExclusive
0x18003be07  test    rbx, rbx
0x18003be0a  jz      short loc_18003BE1F
0x18003be0c  mov     rcx, rbx; SRWLock
0x18003be0f  call    cs:__imp_ReleaseSRWLockExclusive
0x18003be15  jmp     short loc_18003BE1F
0x18003be17  mov     rcx, rdi
0x18003be1a  call    ?Destroy_NoLock@?$ContextEventSource@U?$ITypedEventHandler@PEAVCompositorController@Core@Composition@UI@Windows@@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL2@Microsoft@@QEAAXXZ; Microsoft::WRL2::ContextEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::Core::CompositorController *,IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Destroy_NoLock(void)
0x18003be1f  mov     rcx, rbp; this
0x18003be22  add     rsp, 20h
0x18003be26  pop     r14
0x18003be28  pop     rdi
0x18003be29  pop     rsi
0x18003be2a  pop     rbp
0x18003be2b  pop     rbx
0x18003be2c  jmp     ?Destroy@CompositionObject@Composition@UI@Windows@@MEAAXXZ; Windows::UI::Composition::CompositionObject::Destroy(void)
```
