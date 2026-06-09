# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)

- ea: `0x18001a040`
- end: `0x18001a12b`
- name: `?FireCompletion@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVProcessLauncherResult@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJXZ`
- size: `235`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007248`
- `0x180015600`
- `0x180016054`
- `0x18001702c`
- `0x18001705c`
- `0x180017100`
- `0x180017224`
- `0x18001873c`
- `0x18001a040`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(
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
    if ( (int)Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::System::ProcessLauncherResult *>>(
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
0x18001a040  mov     [rsp-18h+arg_18], rbx
0x18001a045  push    rbp
0x18001a046  push    rsi
0x18001a047  push    rdi
0x18001a048  mov     rbp, rsp
0x18001a04b  sub     rsp, 20h
0x18001a04f  mov     rbx, rcx
0x18001a052  xor     esi, esi
0x18001a054  lea     edx, [rsi+1]
0x18001a057  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18001a05c  lea     rdi, [rbx+18h]
0x18001a060  cmp     [rdi], rsi
0x18001a063  jz      loc_18001A11C
0x18001a069  xor     eax, eax
0x18001a06b  lock cmpxchg [rbx+10h], edx
0x18001a070  jnz     loc_18001A11C
0x18001a076  mov     [rbp+arg_10], rbx
0x18001a07a  lea     rcx, [rbp+arg_10]
0x18001a07e  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18001a083  nop
0x18001a084  mov     [rbp+arg_8], rsi
0x18001a088  mov     rcx, rbx
0x18001a08b  call    ?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVProcessLauncherResult@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)
0x18001a090  lea     rdx, [rbp+arg_8]
0x18001a094  lea     rcx, [rbp+arg_10]
0x18001a098  call    ??$As@U?$IAsyncOperation@PEAVProcessLauncherResult@System@Windows@@@Foundation@Windows@@@?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IAsyncOperation@PEAVProcessLauncherResult@System@Windows@@@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IAsyncInfo>::As<Windows::Foundation::IAsyncOperation<Windows::System::ProcessLauncherResult *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::System::ProcessLauncherResult *>>>)
0x18001a09d  test    eax, eax
0x18001a09f  js      short loc_18001A0FD
0x18001a0a1  mov     [rbp+arg_0], 0FFFFFFFEh
0x18001a0a8  mov     ecx, [rbx+38h]
0x18001a0ab  mov     eax, [rbp+arg_0]
0x18001a0ae  lock cmpxchg [rbp+arg_0], ecx
0x18001a0b3  mov     rcx, rbx
0x18001a0b6  call    ?TraceCompletionNotificationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVProcessLauncherResult@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationStart(void)
0x18001a0bb  mov     rcx, [rdi]
0x18001a0be  mov     rax, [rcx]
0x18001a0c1  mov     r8d, [rbp+arg_0]
0x18001a0c5  mov     rdx, [rbp+arg_8]
0x18001a0c9  mov     rax, [rax+18h]
0x18001a0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0d2  mov     r8, [rbx+28h]
0x18001a0d6  mov     rdx, [rdi]
0x18001a0d9  mov     ecx, eax
0x18001a0db  call    ?FireProgressErrorPropagationPolicyFilter@?$ErrorPropagationPolicyTraits@$0?0@WRL@Microsoft@@SAJJPEAUIUnknown@@PEAX@Z; Microsoft::WRL::ErrorPropagationPolicyTraits<-1>::FireProgressErrorPropagationPolicyFilter(long,IUnknown *,void *)
0x18001a0e0  mov     esi, eax
0x18001a0e2  or      edx, 0FFFFFFFFh
0x18001a0e5  lock xadd [rbx+20h], edx
0x18001a0ea  cmp     edx, 1
0x18001a0ed  jnz     short loc_18001A0F7
0x18001a0ef  mov     rcx, rdi
0x18001a0f2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001a0f7  call    ?TraceCompletionNotificationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceCompletionNotificationComplete(void)
0x18001a0fc  nop
0x18001a0fd  lea     rcx, [rbp+arg_8]
0x18001a101  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001a106  nop
0x18001a107  test    rbx, rbx
0x18001a10a  jz      short loc_18001A11C
0x18001a10c  mov     rax, [rbx]
0x18001a10f  mov     rcx, rbx
0x18001a112  mov     rax, [rax+10h]
0x18001a116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a11b  nop
0x18001a11c  mov     eax, esi
0x18001a11e  mov     rbx, [rsp+20h+arg_18]
0x18001a123  add     rsp, 20h
0x18001a127  pop     rdi
0x18001a128  pop     rsi
0x18001a129  pop     rbp
0x18001a12a  retn
```
