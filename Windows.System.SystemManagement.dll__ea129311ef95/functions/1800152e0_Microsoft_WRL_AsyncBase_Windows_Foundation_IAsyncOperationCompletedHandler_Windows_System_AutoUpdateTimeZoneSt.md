# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x1800152e0`
- end: `0x1800153cb`
- name: `?FireCompletion@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJXZ`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007248`
- `0x1800133b8`
- `0x1800152e0`
- `0x180015600`
- `0x180016054`
- `0x18001702c`
- `0x18001705c`
- `0x180017100`
- `0x180017224`
- `0x18002b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
        __int64 a1)
{
  unsigned int v2; // esi
  signed __int32 v3; // edx
  _QWORD *v4; // rdi
  unsigned int v5; // eax
  unsigned int v7; // [rsp+40h] [rbp+20h] BYREF
  __int64 v8; // [rsp+48h] [rbp+28h] BYREF
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64); // [rsp+50h] [rbp+30h] BYREF

  v2 = 0;
  Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
    a1,
    1);
  v4 = (_QWORD *)(a1 + 24);
  if ( *(_QWORD *)(a1 + 24) && !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 16), v3, 0) )
  {
    v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a1;
    Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef((__int64 *)&v9);
    v8 = 0;
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(a1);
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<enum Windows::System::AutoUpdateTimeZoneStatus>>(
                &v9,
                (__int64)&v8) >= 0 )
    {
      v7 = -2;
      _InterlockedCompareExchange((volatile signed __int32 *)&v7, *(_DWORD *)(a1 + 56), -2);
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(a1);
      v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(*(_QWORD *)*v4 + 24LL))(*v4, v8, v7);
      v2 = Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(
             v5,
             *v4,
             *(_QWORD *)(a1 + 40));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 32), 0xFFFFFFFF) == 1 )
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)(a1 + 24));
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete();
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v8);
    if ( a1 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x1800152e0  mov     [rsp-18h+arg_18], rbx
0x1800152e5  push    rbp
0x1800152e6  push    rsi
0x1800152e7  push    rdi
0x1800152e8  mov     rbp, rsp
0x1800152eb  sub     rsp, 20h
0x1800152ef  mov     rbx, rcx
0x1800152f2  xor     esi, esi
0x1800152f4  lea     edx, [rsi+1]
0x1800152f7  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800152fc  lea     rdi, [rbx+18h]
0x180015300  cmp     [rdi], rsi
0x180015303  jz      loc_1800153BC
0x180015309  xor     eax, eax
0x18001530b  lock cmpxchg [rbx+10h], edx
0x180015310  jnz     loc_1800153BC
0x180015316  mov     [rbp+arg_10], rbx
0x18001531a  lea     rcx, [rbp+arg_10]
0x18001531e  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x180015323  nop
0x180015324  mov     [rbp+arg_8], rsi
0x180015328  mov     rcx, rbx
0x18001532b  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVProcessLauncherResult@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x180015330  lea     rdx, [rbp+arg_8]
0x180015334  lea     rcx, [rbp+arg_10]
0x180015338  call    ??$As@U?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus>>>)
0x18001533d  test    eax, eax
0x18001533f  js      short loc_18001539D
0x180015341  mov     [rbp+arg_0], 0FFFFFFFEh
0x180015348  mov     ecx, [rbx+38h]
0x18001534b  mov     eax, [rbp+arg_0]
0x18001534e  lock cmpxchg [rbp+arg_0], ecx
0x180015353  mov     rcx, rbx
0x180015356  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVProcessLauncherResult@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18001535b  mov     rcx, [rdi]
0x18001535e  mov     rax, [rcx]
0x180015361  mov     r8d, [rbp+arg_0]
0x180015365  mov     rdx, [rbp+arg_8]
0x180015369  mov     rax, [rax+18h]
0x18001536d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015372  mov     r8, [rbx+28h]
0x180015376  mov     rdx, [rdi]
0x180015379  mov     ecx, eax
0x18001537b  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x180015380  mov     esi, eax
0x180015382  or      edx, 0FFFFFFFFh
0x180015385  lock xadd [rbx+20h], edx
0x18001538a  cmp     edx, 1
0x18001538d  jnz     short loc_180015397
0x18001538f  mov     rcx, rdi
0x180015392  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015397  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18001539c  nop
0x18001539d  lea     rcx, [rbp+arg_8]
0x1800153a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800153a6  nop
0x1800153a7  test    rbx, rbx
0x1800153aa  jz      short loc_1800153BC
0x1800153ac  mov     rax, [rbx]
0x1800153af  mov     rcx, rbx
0x1800153b2  mov     rax, [rax+10h]
0x1800153b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153bb  nop
0x1800153bc  mov     eax, esi
0x1800153be  mov     rbx, [rsp+20h+arg_18]
0x1800153c3  add     rsp, 20h
0x1800153c7  pop     rdi
0x1800153c8  pop     rsi
0x1800153c9  pop     rbp
0x1800153ca  retn
```
