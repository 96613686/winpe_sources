# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800192a0`
- end: `0x180019320`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `128`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180019330`
- `0x180019340`
- `0x180019360`
- `0x180019380`
- `0x1800193a0`
- `0x1800193c0`
- `0x1800193e0`

## callees

- `0x18000d8dc`
- `0x1800167c4`
- `0x1800192a0`
- `0x180027010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::QueryInterface(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  const struct _GUID *v4; // rcx
  __int64 *v5; // r8
  __int64 v6; // r9
  const struct _GUID *v7; // r10
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
    CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,IWeakReferenceSource,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::CanCastTo(
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
0x1800192a0  mov     [rsp+arg_0], rbx
0x1800192a5  push    rdi
0x1800192a6  sub     rsp, 20h
0x1800192aa  mov     rdi, r8
0x1800192ad  mov     r10, rdx
0x1800192b0  mov     r9, rcx
0x1800192b3  mov     qword ptr [r8], 0
0x1800192ba  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x1800192c1  mov     rcx, r10; struct _GUID *
0x1800192c4  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1800192c9  test    eax, eax
0x1800192cb  jnz     short loc_1800192FF
0x1800192cd  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x1800192d4  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1800192d9  test    eax, eax
0x1800192db  jnz     short loc_1800192FF
0x1800192dd  mov     rdx, r10
0x1800192e0  mov     rcx, r9
0x1800192e3  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$0A@U?$ImplementsMarker@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@@Details@23@UIWeakReferenceSource@@U?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@UIAsyncOperationLocal@Internal@9@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,Microsoft::WRL::Details::ImplementsMarker<Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,IWeakReferenceSource,Windows::Foundation::IAsyncOperation<HSTRING__ *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::CanCastTo(_GUID const &,void * *,bool *)
0x1800192e8  mov     ebx, eax
0x1800192ea  test    eax, eax
0x1800192ec  js      short loc_180019313
0x1800192ee  mov     rcx, [rdi]
0x1800192f1  mov     rax, [rcx]
0x1800192f4  mov     rax, [rax+8]
0x1800192f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192fd  jmp     short loc_180019313
0x1800192ff  mov     [r8], r9
0x180019302  mov     rax, [r9]
0x180019305  mov     rcx, r9
0x180019308  mov     rax, [rax+8]
0x18001930c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019311  xor     ebx, ebx
0x180019313  mov     eax, ebx
0x180019315  mov     rbx, [rsp+28h+arg_0]
0x18001931a  add     rsp, 20h
0x18001931e  pop     rdi
0x18001931f  retn
```
