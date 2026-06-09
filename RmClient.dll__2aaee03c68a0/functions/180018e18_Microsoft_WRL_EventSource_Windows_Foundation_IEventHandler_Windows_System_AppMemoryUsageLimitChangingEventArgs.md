# Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(EventRegistrationToken)

- ea: `0x180018e18`
- end: `0x180018fa0`
- name: `?Remove@?$EventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUEventRegistrationToken@@@Z`
- size: `392`
- prototype: `__int64 __fastcall(Microsoft::WRL::Details::EventTargetArray *, struct IUnknown *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180017c34`
- `0x180019180`

## callees

- `0x18000a474`
- `0x18000a640`
- `0x18000fb40`
- `0x1800105e8`
- `0x180013594`
- `0x180018e18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018e60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018ec2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018f60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018f7d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018e60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018ec2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018f60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018f7d`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Remove(
        Microsoft::WRL::Details::EventTargetArray *a1,
        struct IUnknown *a2)
{
  volatile int *v3; // rdx
  struct IUnknown **v4; // rcx
  __int64 v5; // r14
  RTL_SRWLOCK *v6; // r14
  bool v7; // si
  int v8; // edi
  __int64 v10; // rax
  struct IUnknown **v11; // rdi
  void **v12; // r15
  Microsoft::WRL::Details::EventTargetArray *v13; // [rsp+60h] [rbp+38h] BYREF
  PSRWLOCK SRWLock; // [rsp+68h] [rbp+40h] BYREF
  __int64 v15; // [rsp+70h] [rbp+48h] BYREF
  PSRWLOCK v16; // [rsp+78h] [rbp+50h] BYREF

  v13 = a1;
  v15 = 0;
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &stru_18002ED38);
  if ( !Windows::System::CMemoryManager::s_limitChangeEvent )
  {
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    return 0;
  }
  v4 = *(struct IUnknown ***)(Windows::System::CMemoryManager::s_limitChangeEvent + 16);
  v5 = *(_QWORD *)(Windows::System::CMemoryManager::s_limitChangeEvent + 24) - (_QWORD)v4;
  v13 = 0;
  v6 = (RTL_SRWLOCK *)((v5 >> 3) - 1);
  v16 = v6;
  if ( !v6 )
  {
    v7 = *v4 == a2;
    goto LABEL_19;
  }
  v8 = Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64 &>(
         &v13,
         &v16);
  if ( v8 >= 0 )
  {
    v10 = Windows::System::CMemoryManager::s_limitChangeEvent;
    v7 = 0;
    v11 = *(struct IUnknown ***)(Windows::System::CMemoryManager::s_limitChangeEvent + 16);
    v12 = *(void ***)(Windows::System::CMemoryManager::s_limitChangeEvent + 32);
    if ( v11 == *(struct IUnknown ***)(Windows::System::CMemoryManager::s_limitChangeEvent + 24) )
    {
LABEL_22:
      if ( v13 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(
          (__int64)v13,
          v3);
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
      if ( v15 )
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v15, v3);
      return 0;
    }
    do
    {
      if ( v7 || a2 != *v11 )
      {
        if ( !v6 )
          break;
        Microsoft::WRL::Details::EventTargetArray::AddTail(v13, *v11, *v12);
        v10 = Windows::System::CMemoryManager::s_limitChangeEvent;
        ++v12;
        v6 = (RTL_SRWLOCK *)((char *)v6 - 1);
      }
      else
      {
        v7 = 1;
      }
      ++v11;
    }
    while ( v11 != *(struct IUnknown ***)(v10 + 24) );
LABEL_19:
    if ( v7 )
    {
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v16, &stru_18002ED30);
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(
        &v15,
        (char *)&Windows::System::CMemoryManager::s_limitChangeEvent);
      Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(
        &Windows::System::CMemoryManager::s_limitChangeEvent,
        (char *)&v13);
      if ( v16 )
        ReleaseSRWLockExclusive(v16);
    }
    goto LABEL_22;
  }
  if ( v13 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(
      (__int64)v13,
      v3);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180018e18  mov     [rsp-30h+arg_0], rcx
0x180018e1d  push    rbp
0x180018e1e  push    rbx
0x180018e1f  push    rsi
0x180018e20  push    rdi
0x180018e21  push    r14
0x180018e23  push    r15
0x180018e25  mov     rbp, rsp
0x180018e28  sub     rsp, 28h
0x180018e2c  mov     rbx, rdx
0x180018e2f  mov     [rbp+arg_10], 0
0x180018e37  lea     rdx, stru_18002ED38
0x180018e3e  lea     rcx, [rbp+SRWLock]
0x180018e42  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180018e47  mov     rax, cs:?s_limitChangeEvent@CMemoryManager@System@Windows@@0V?$AgileEventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@A; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> Windows::System::CMemoryManager::s_limitChangeEvent
0x180018e4e  test    rax, rax
0x180018e51  jnz     short loc_180018E6B
0x180018e53  mov     rcx, [rbp+SRWLock]; SRWLock
0x180018e57  test    rcx, rcx
0x180018e5a  jz      loc_180018F91
0x180018e60  call    cs:__imp_ReleaseSRWLockExclusive
0x180018e66  jmp     loc_180018F91
0x180018e6b  mov     rcx, [rax+10h]
0x180018e6f  mov     r14, [rax+18h]
0x180018e73  sub     r14, rcx
0x180018e76  mov     [rbp+arg_0], 0
0x180018e7e  sar     r14, 3
0x180018e82  sub     r14, 1
0x180018e86  mov     [rbp+arg_18], r14
0x180018e8a  jnz     short loc_180018E98
0x180018e8c  cmp     [rcx], rbx
0x180018e8f  setz    sil
0x180018e93  jmp     loc_180018F22
0x180018e98  lea     rdx, [rbp+arg_18]
0x180018e9c  lea     rcx, [rbp+arg_0]
0x180018ea0  call    ??$MakeAndInitialize@VEventTargetArray@Details@WRL@Microsoft@@V1234@AEA_K@Details@WRL@Microsoft@@YAJPEAPEAVEventTargetArray@012@AEA_K@Z; Microsoft::WRL::Details::MakeAndInitialize<Microsoft::WRL::Details::EventTargetArray,Microsoft::WRL::Details::EventTargetArray,unsigned __int64 &>(Microsoft::WRL::Details::EventTargetArray * *,unsigned __int64 &)
0x180018ea5  mov     edi, eax
0x180018ea7  test    eax, eax
0x180018ea9  jns     short loc_180018ECF
0x180018eab  mov     rcx, [rbp+arg_0]
0x180018eaf  test    rcx, rcx
0x180018eb2  jz      short loc_180018EB9
0x180018eb4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180018eb9  mov     rcx, [rbp+SRWLock]; SRWLock
0x180018ebd  test    rcx, rcx
0x180018ec0  jz      short loc_180018EC8
0x180018ec2  call    cs:__imp_ReleaseSRWLockExclusive
0x180018ec8  mov     eax, edi
0x180018eca  jmp     loc_180018F93
0x180018ecf  mov     rax, cs:?s_limitChangeEvent@CMemoryManager@System@Windows@@0V?$AgileEventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@A; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> Windows::System::CMemoryManager::s_limitChangeEvent
0x180018ed6  xor     sil, sil
0x180018ed9  mov     rdi, [rax+10h]
0x180018edd  mov     r15, [rax+20h]
0x180018ee1  cmp     rdi, [rax+18h]
0x180018ee5  jz      short loc_180018F66
0x180018ee7  test    sil, sil
0x180018eea  jnz     short loc_180018EF6
0x180018eec  cmp     rbx, [rdi]
0x180018eef  jnz     short loc_180018EF6
0x180018ef1  mov     sil, 1
0x180018ef4  jmp     short loc_180018F18
0x180018ef6  test    r14, r14
0x180018ef9  jz      short loc_180018F22
0x180018efb  mov     r8, [r15]; void *
0x180018efe  mov     rdx, [rdi]; struct IUnknown *
0x180018f01  mov     rcx, [rbp+arg_0]; this
0x180018f05  call    ?AddTail@EventTargetArray@Details@WRL@Microsoft@@QEAAXPEAUIUnknown@@PEAX@Z; Microsoft::WRL::Details::EventTargetArray::AddTail(IUnknown *,void *)
0x180018f0a  mov     rax, cs:?s_limitChangeEvent@CMemoryManager@System@Windows@@0V?$AgileEventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@A; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> Windows::System::CMemoryManager::s_limitChangeEvent
0x180018f11  add     r15, 8
0x180018f15  dec     r14
0x180018f18  add     rdi, 8
0x180018f1c  cmp     rdi, [rax+18h]
0x180018f20  jnz     short loc_180018EE7
0x180018f22  test    sil, sil
0x180018f25  jz      short loc_180018F66
0x180018f27  lea     rdx, stru_18002ED30
0x180018f2e  lea     rcx, [rbp+arg_18]
0x180018f32  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x180018f37  lea     rdx, ?s_limitChangeEvent@CMemoryManager@System@Windows@@0V?$AgileEventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@A; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> Windows::System::CMemoryManager::s_limitChangeEvent
0x180018f3e  lea     rcx, [rbp+arg_10]
0x180018f42  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x180018f47  lea     rdx, [rbp+arg_0]
0x180018f4b  lea     rcx, ?s_limitChangeEvent@CMemoryManager@System@Windows@@0V?$AgileEventSource@U?$IEventHandler@PEAVAppMemoryUsageLimitChangingEventArgs@System@Windows@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@A; Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<Windows::System::AppMemoryUsageLimitChangingEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> Windows::System::CMemoryManager::s_limitChangeEvent
0x180018f52  call    ??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> &&)
0x180018f57  mov     rcx, [rbp+arg_18]; SRWLock
0x180018f5b  test    rcx, rcx
0x180018f5e  jz      short loc_180018F66
0x180018f60  call    cs:__imp_ReleaseSRWLockExclusive
0x180018f66  mov     rcx, [rbp+arg_0]
0x180018f6a  test    rcx, rcx
0x180018f6d  jz      short loc_180018F74
0x180018f6f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180018f74  mov     rcx, [rbp+SRWLock]; SRWLock
0x180018f78  test    rcx, rcx
0x180018f7b  jz      short loc_180018F83
0x180018f7d  call    cs:__imp_ReleaseSRWLockExclusive
0x180018f83  mov     rcx, [rbp+arg_10]
0x180018f87  test    rcx, rcx
0x180018f8a  jz      short loc_180018F91
0x180018f8c  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x180018f91  xor     eax, eax
0x180018f93  add     rsp, 28h
0x180018f97  pop     r15
0x180018f99  pop     r14
0x180018f9b  pop     rdi
0x180018f9c  pop     rsi
0x180018f9d  pop     rbx
0x180018f9e  pop     rbp
0x180018f9f  retn
```
