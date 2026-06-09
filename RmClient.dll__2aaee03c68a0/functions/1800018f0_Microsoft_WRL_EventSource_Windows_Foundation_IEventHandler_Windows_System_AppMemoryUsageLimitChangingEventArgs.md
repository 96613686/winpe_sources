# Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *> *,void *,EventRegistrationToken *)

- ea: `0x1800018f0`
- end: `0x180001a63`
- name: `?AddInternal@?$EventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details::EventTargetArray *, struct IUnknown *, void *, struct IUnknown **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001780`

## callees

- `0x1800018f0`
- `0x18000a474`
- `0x18000a4b4`
- `0x18000a640`
- `0x18000fb40`
- `0x1800105e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000198d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001a1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001a3c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000198d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001a1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001a3c`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
        Microsoft::WRL::Details::EventTargetArray *a1,
        struct IUnknown *a2,
        void *a3,
        struct IUnknown **a4)
{
  __int64 v7; // rcx
  int v8; // ebx
  __int64 v10; // rax
  void **v11; // rdi
  struct IUnknown **i; // rbx
  Microsoft::WRL::Details::EventTargetArray *v13; // rcx
  __int64 v14; // [rsp+20h] [rbp-10h] BYREF
  PSRWLOCK v15; // [rsp+28h] [rbp-8h] BYREF
  Microsoft::WRL::Details::EventTargetArray *v16; // [rsp+60h] [rbp+30h] BYREF
  PSRWLOCK SRWLock; // [rsp+78h] [rbp+48h] BYREF

  v16 = a1;
  *a4 = 0;
  v14 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &stru_18002ED38);
  v16 = 0;
  if ( Windows::System::CMemoryManager::s_limitChangeEvent )
    v7 = ((__int64)(*(_QWORD *)(Windows::System::CMemoryManager::s_limitChangeEvent + 24)
                  - *(_QWORD *)(Windows::System::CMemoryManager::s_limitChangeEvent + 16)) >> 3)
       + 1;
  else
    v7 = 1;
  v15 = (PSRWLOCK)v7;
  v8 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(
         &v16,
         &v15);
  if ( v8 >= 0 )
  {
    v10 = Windows::System::CMemoryManager::s_limitChangeEvent;
    if ( Windows::System::CMemoryManager::s_limitChangeEvent )
    {
      v11 = *(void ***)(Windows::System::CMemoryManager::s_limitChangeEvent + 32);
      for ( i = *(struct IUnknown ***)(Windows::System::CMemoryManager::s_limitChangeEvent + 16);
            i != *(struct IUnknown ***)(v10 + 24);
            ++i )
      {
        Microsoft::WRL::Details::EventTargetArray::AddTail(v16, *i, *v11);
        v10 = Windows::System::CMemoryManager::s_limitChangeEvent;
        ++v11;
      }
    }
    v13 = v16;
    *a4 = a2;
    Microsoft::WRL::Details::EventTargetArray::AddTail(v13, a2, a3);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v15, &stru_18002ED30);
    Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(
      &v14,
      (char *)&Windows::System::CMemoryManager::s_limitChangeEvent);
    Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(
      &Windows::System::CMemoryManager::s_limitChangeEvent,
      (char *)&v16);
    if ( v15 )
      ReleaseSRWLockExclusive(v15);
    if ( v16 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    if ( v14 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
    return 0;
  }
  else
  {
    if ( v16 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x1800018f0  mov     [rsp-28h+arg_8], rbx
0x1800018f5  mov     [rsp-28h+arg_0], rcx
0x1800018fa  push    rbp
0x1800018fb  push    rsi
0x1800018fc  push    rdi
0x1800018fd  push    r14
0x1800018ff  push    r15
0x180001901  mov     rbp, rsp
0x180001904  sub     rsp, 30h
0x180001908  mov     r14, rdx
0x18000190b  mov     qword ptr [r9], 0
0x180001912  lea     rdx, stru_18002ED38
0x180001919  mov     [rbp+var_10], 0
0x180001921  lea     rcx, [rbp+SRWLock]
0x180001925  mov     rsi, r9
0x180001928  mov     r15, r8
0x18000192b  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180001930  mov     rcx, cs:?s_limitChangeEvent@CMemoryManager@System@Windows@@0V?$AgileEventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@A; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> Windows::System::CMemoryManager::s_limitChangeEvent
0x180001937  mov     [rbp+arg_0], 0
0x18000193f  test    rcx, rcx
0x180001942  jnz     short loc_18000194B
0x180001944  mov     ecx, 1
0x180001949  jmp     short loc_18000195F
0x18000194b  mov     rax, [rcx+18h]
0x18000194f  sub     rax, [rcx+10h]
0x180001953  mov     ecx, 1
0x180001958  sar     rax, 3
0x18000195c  add     rcx, rax
0x18000195f  mov     [rbp+var_8], rcx
0x180001963  lea     rdx, [rbp+var_8]
0x180001967  lea     rcx, [rbp+arg_0]
0x18000196b  call    ??$MakeAndInitialize@VEventTargetArray@Details@WRL@Microsoft@@V1234@_K@Details@WRL@Microsoft@@YAJPEAPEAVEventTargetArray@012@$$QEA_K@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64>(Microsoft::WRL::Details::EventTargetArray * *,unsigned __int64 &&)
0x180001970  mov     ebx, eax
0x180001972  test    eax, eax
0x180001974  jns     short loc_18000199A
0x180001976  mov     rcx, [rbp+arg_0]
0x18000197a  test    rcx, rcx
0x18000197d  jz      short loc_180001984
0x18000197f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180001984  mov     rcx, [rbp+SRWLock]; SRWLock
0x180001988  test    rcx, rcx
0x18000198b  jz      short loc_180001993
0x18000198d  call    cs:__imp_ReleaseSRWLockExclusive
0x180001993  mov     eax, ebx
0x180001995  jmp     loc_180001A52
0x18000199a  mov     rax, cs:?s_limitChangeEvent@CMemoryManager@System@Windows@@0V?$AgileEventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@A; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> Windows::System::CMemoryManager::s_limitChangeEvent
0x1800019a1  test    rax, rax
0x1800019a4  jz      short loc_1800019D4
0x1800019a6  mov     rdi, [rax+20h]
0x1800019aa  mov     rbx, [rax+10h]
0x1800019ae  jmp     short loc_1800019CE
0x1800019b0  mov     r8, [rdi]; void *
0x1800019b3  mov     rdx, [rbx]; struct IUnknown *
0x1800019b6  mov     rcx, [rbp+arg_0]; this
0x1800019ba  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x1800019bf  mov     rax, cs:?s_limitChangeEvent@CMemoryManager@System@Windows@@0V?$AgileEventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@A; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> Windows::System::CMemoryManager::s_limitChangeEvent
0x1800019c6  lea     rdi, [rdi+8]
0x1800019ca  add     rbx, 8
0x1800019ce  cmp     rbx, [rax+18h]
0x1800019d2  jnz     short loc_1800019B0
0x1800019d4  mov     rcx, [rbp+arg_0]; this
0x1800019d8  mov     r8, r15; void *
0x1800019db  mov     rdx, r14; struct IUnknown *
0x1800019de  mov     [rsi], r14
0x1800019e1  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x1800019e6  lea     rdx, stru_18002ED30
0x1800019ed  lea     rcx, [rbp+var_8]
0x1800019f1  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x1800019f6  lea     rdx, ?s_limitChangeEvent@CMemoryManager@System@Windows@@0V?$AgileEventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@A; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> Windows::System::CMemoryManager::s_limitChangeEvent
0x1800019fd  lea     rcx, [rbp+var_10]
0x180001a01  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x180001a06  lea     rdx, [rbp+arg_0]
0x180001a0a  lea     rcx, ?s_limitChangeEvent@CMemoryManager@System@Windows@@0V?$AgileEventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@A; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> Windows::System::CMemoryManager::s_limitChangeEvent
0x180001a11  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x180001a16  mov     rcx, [rbp+var_8]; SRWLock
0x180001a1a  test    rcx, rcx
0x180001a1d  jz      short loc_180001A25
0x180001a1f  call    cs:__imp_ReleaseSRWLockExclusive
0x180001a25  mov     rcx, [rbp+arg_0]
0x180001a29  test    rcx, rcx
0x180001a2c  jz      short loc_180001A33
0x180001a2e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180001a33  mov     rcx, [rbp+SRWLock]; SRWLock
0x180001a37  test    rcx, rcx
0x180001a3a  jz      short loc_180001A42
0x180001a3c  call    cs:__imp_ReleaseSRWLockExclusive
0x180001a42  mov     rcx, [rbp+var_10]
0x180001a46  test    rcx, rcx
0x180001a49  jz      short loc_180001A50
0x180001a4b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180001a50  xor     eax, eax
0x180001a52  mov     rbx, [rsp+30h+arg_8]
0x180001a57  add     rsp, 30h
0x180001a5b  pop     r15
0x180001a5d  pop     r14
0x180001a5f  pop     rdi
0x180001a60  pop     rsi
0x180001a61  pop     rbp
0x180001a62  retn
```
