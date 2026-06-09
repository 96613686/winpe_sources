# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800167d0`
- end: `0x180016850`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `128`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180016860`
- `0x180016870`
- `0x180016890`
- `0x1800168b0`
- `0x1800168d0`
- `0x1800168f0`
- `0x180016910`

## callees

- `0x18000c3a0`
- `0x180014b5c`
- `0x1800167d0`
- `0x18002b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  const struct _GUID *v4; // rcx
  _QWORD *v5; // r8
  __int64 v6; // r9
  __int64 v7; // r10
  int CanCastTo; // ebx

  *a3 = 0;
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046)
    || (unsigned int)InlineIsEqualGUID(v4, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90) )
  {
    *v5 = v6;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    return 0;
  }
  else
  {
    CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,IWeakReferenceSource,Windows::Foundation::IAsyncOperation<enum Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::CanCastTo(
                  v6,
                  v7);
    if ( CanCastTo >= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
  }
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x1800167d0  mov     [rsp+arg_0], rbx
0x1800167d5  push    rdi
0x1800167d6  sub     rsp, 20h
0x1800167da  mov     rdi, r8
0x1800167dd  mov     r10, rdx
0x1800167e0  mov     r9, rcx
0x1800167e3  mov     qword ptr [r8], 0
0x1800167ea  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x1800167f1  mov     rcx, r10; struct _GUID *
0x1800167f4  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1800167f9  test    eax, eax
0x1800167fb  jnz     short loc_18001682F
0x1800167fd  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x180016804  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180016809  test    eax, eax
0x18001680b  jnz     short loc_18001682F
0x18001680d  mov     rdx, r10
0x180016810  mov     rcx, r9
0x180016813  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$0A@U?$ImplementsMarker@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@@Details@23@UIWeakReferenceSource@@U?$IAsyncOperation@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@UIAsyncOperationLocal@Internal@9@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,IWeakReferenceSource,Windows::Foundation::IAsyncOperation<Windows::System::AutoUpdateTimeZoneStatus>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::CanCastTo(_GUID const &,void * *,bool *)
0x180016818  mov     ebx, eax
0x18001681a  test    eax, eax
0x18001681c  js      short loc_180016843
0x18001681e  mov     rcx, [rdi]
0x180016821  mov     rax, [rcx]
0x180016824  mov     rax, [rax+8]
0x180016828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001682d  jmp     short loc_180016843
0x18001682f  mov     [r8], r9
0x180016832  mov     rax, [r9]
0x180016835  mov     rcx, r9
0x180016838  mov     rax, [rax+8]
0x18001683c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016841  xor     ebx, ebx
0x180016843  mov     eax, ebx
0x180016845  mov     rbx, [rsp+28h+arg_0]
0x18001684a  add     rsp, 20h
0x18001684e  pop     rdi
0x18001684f  retn
```
