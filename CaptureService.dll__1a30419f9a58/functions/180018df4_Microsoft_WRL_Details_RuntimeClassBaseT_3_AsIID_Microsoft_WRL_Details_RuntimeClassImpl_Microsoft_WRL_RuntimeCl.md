# Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>> *,_GUID const &,void * *)

- ea: `0x180018df4`
- end: `0x180018edc`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `232`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019dd0`

## callees

- `0x18000ee80`
- `0x18000f010`
- `0x180012290`
- `0x180018df4`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>>(
        __int64 a1,
        const struct _GUID *a2,
        _QWORD *a3)
{
  const struct _GUID *v4; // rcx
  _QWORD *v5; // r8
  __int64 v6; // r11
  const struct _GUID *v7; // rcx
  void **v8; // r8
  __int64 v9; // r11
  int CanCastTo; // ebx
  const struct _GUID *v11; // rcx

  *a3 = 0;
  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_00000000_0000_0000_c000_000000000046)
    || (unsigned int)InlineIsEqualGUID(v4, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90) )
  {
    *v5 = v6;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
    return 0;
  }
  if ( (unsigned int)InlineIsEqualGUID(v7, &GUID_00000036_0000_0000_c000_000000000046) )
  {
LABEL_6:
    *v8 = (void *)v9;
    CanCastTo = 0;
    goto LABEL_9;
  }
  CanCastTo = Microsoft::WRL::FtmBase::CanCastTo((Microsoft::WRL::FtmBase *)(v9 + 80), a2, v8);
  if ( CanCastTo == -2147467262 )
  {
    if ( !(unsigned int)InlineIsEqualGUID(a2, &GUID_00000038_0000_0000_c000_000000000046)
      && !(unsigned int)InlineIsEqualGUID(v11, &GUID_827caf42_5fe6_5b5b_84ce_c44834134d3d) )
    {
      CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::CanCastTo(
                    v9 + 8,
                    a2);
      goto LABEL_9;
    }
    goto LABEL_6;
  }
LABEL_9:
  if ( CanCastTo >= 0 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)*v8 + 8LL))(*v8);
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x180018df4  mov     [rsp+arg_0], rbx
0x180018df9  push    rdi
0x180018dfa  sub     rsp, 20h
0x180018dfe  mov     rdi, rdx
0x180018e01  mov     r11, rcx
0x180018e04  mov     qword ptr [r8], 0
0x180018e0b  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x180018e12  mov     rcx, rdi; struct _GUID *
0x180018e15  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180018e1a  test    eax, eax
0x180018e1c  jnz     loc_180018EBD
0x180018e22  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x180018e29  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180018e2e  test    eax, eax
0x180018e30  jnz     loc_180018EBD
0x180018e36  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046; struct _GUID *
0x180018e3d  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180018e42  test    eax, eax
0x180018e44  jnz     short loc_180018E7D
0x180018e46  lea     rcx, [r11+50h]; this
0x180018e4a  mov     rdx, rdi; struct _GUID *
0x180018e4d  call    ?CanCastTo@FtmBase@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)
0x180018e52  mov     ebx, eax
0x180018e54  mov     eax, 80004002h
0x180018e59  cmp     ebx, eax
0x180018e5b  jnz     short loc_180018EA6
0x180018e5d  mov     ebx, eax
0x180018e5f  cmp     eax, eax
0x180018e61  jnz     short loc_180018EA6
0x180018e63  add     r11, 0A8h
0x180018e6a  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046; struct _GUID *
0x180018e71  mov     rcx, rdi; struct _GUID *
0x180018e74  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180018e79  test    eax, eax
0x180018e7b  jz      short loc_180018E84
0x180018e7d  mov     [r8], r11
0x180018e80  xor     ebx, ebx
0x180018e82  jmp     short loc_180018EA6
0x180018e84  add     r11, 8
0x180018e88  lea     rdx, _GUID_827caf42_5fe6_5b5b_84ce_c44834134d3d; struct _GUID *
0x180018e8f  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x180018e94  test    eax, eax
0x180018e96  jnz     short loc_180018E7D
0x180018e98  lea     rcx, [r11+8]
0x180018e9c  mov     rdx, rdi
0x180018e9f  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAsyncOperationLocal@Internal@Windows@@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::CanCastTo(_GUID const &,void * *,bool *)
0x180018ea4  mov     ebx, eax
0x180018ea6  test    ebx, ebx
0x180018ea8  js      short loc_180018EB9
0x180018eaa  mov     rcx, [r8]
0x180018ead  mov     rdx, [rcx]
0x180018eb0  mov     rax, [rdx+8]
0x180018eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018eb9  mov     eax, ebx
0x180018ebb  jmp     short loc_180018ED1
0x180018ebd  mov     [r8], r11
0x180018ec0  mov     rax, [r11]
0x180018ec3  mov     rcx, r11
0x180018ec6  mov     rax, [rax+8]
0x180018eca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ecf  xor     eax, eax
0x180018ed1  mov     rbx, [rsp+28h+arg_0]
0x180018ed6  add     rsp, 20h
0x180018eda  pop     rdi
0x180018edb  retn
```
