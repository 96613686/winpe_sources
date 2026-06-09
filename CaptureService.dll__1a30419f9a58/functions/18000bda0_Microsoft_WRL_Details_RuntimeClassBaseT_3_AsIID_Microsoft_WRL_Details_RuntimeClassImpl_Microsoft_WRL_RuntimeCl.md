# Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>> *,_GUID const &,void * *)

- ea: `0x18000bda0`
- end: `0x18000be88`
- name: `??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@U?$IAsyncOperation@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@123@AEBU_GUID@@PEAPEAX@Z`
- size: `232`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180013720`

## callees

- `0x18000bda0`
- `0x18000ee80`
- `0x18000f010`
- `0x180012290`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>>(
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
      && !(unsigned int)InlineIsEqualGUID(v11, &GUID_a0cd3f1f_d135_5e35_8150_652737c04ec7) )
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
0x18000bda0  mov     [rsp+arg_0], rbx
0x18000bda5  push    rdi
0x18000bda6  sub     rsp, 20h
0x18000bdaa  mov     rdi, rdx
0x18000bdad  mov     r11, rcx
0x18000bdb0  mov     qword ptr [r8], 0
0x18000bdb7  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046; struct _GUID *
0x18000bdbe  mov     rcx, rdi; struct _GUID *
0x18000bdc1  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000bdc6  test    eax, eax
0x18000bdc8  jnz     loc_18000BE69
0x18000bdce  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x18000bdd5  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000bdda  test    eax, eax
0x18000bddc  jnz     loc_18000BE69
0x18000bde2  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046; struct _GUID *
0x18000bde9  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000bdee  test    eax, eax
0x18000bdf0  jnz     short loc_18000BE29
0x18000bdf2  lea     rcx, [r11+50h]; this
0x18000bdf6  mov     rdx, rdi; struct _GUID *
0x18000bdf9  call    ?CanCastTo@FtmBase@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::FtmBase::CanCastTo(_GUID const &,void * *)
0x18000bdfe  mov     ebx, eax
0x18000be00  mov     eax, 80004002h
0x18000be05  cmp     ebx, eax
0x18000be07  jnz     short loc_18000BE52
0x18000be09  mov     ebx, eax
0x18000be0b  cmp     eax, eax
0x18000be0d  jnz     short loc_18000BE52
0x18000be0f  add     r11, 0A8h
0x18000be16  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046; struct _GUID *
0x18000be1d  mov     rcx, rdi; struct _GUID *
0x18000be20  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000be25  test    eax, eax
0x18000be27  jz      short loc_18000BE30
0x18000be29  mov     [r8], r11
0x18000be2c  xor     ebx, ebx
0x18000be2e  jmp     short loc_18000BE52
0x18000be30  add     r11, 8
0x18000be34  lea     rdx, _GUID_a0cd3f1f_d135_5e35_8150_652737c04ec7; struct _GUID *
0x18000be3b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000be40  test    eax, eax
0x18000be42  jnz     short loc_18000BE29
0x18000be44  lea     rcx, [r11+8]
0x18000be48  mov     rdx, rdi
0x18000be4b  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIAsyncOperationLocal@Internal@Windows@@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::CanCastTo(_GUID const &,void * *,bool *)
0x18000be50  mov     ebx, eax
0x18000be52  test    ebx, ebx
0x18000be54  js      short loc_18000BE65
0x18000be56  mov     rcx, [r8]
0x18000be59  mov     rdx, [rcx]
0x18000be5c  mov     rax, [rdx+8]
0x18000be60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be65  mov     eax, ebx
0x18000be67  jmp     short loc_18000BE7D
0x18000be69  mov     [r8], r11
0x18000be6c  mov     rax, [r11]
0x18000be6f  mov     rcx, r11
0x18000be72  mov     rax, [rax+8]
0x18000be76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be7b  xor     eax, eax
0x18000be7d  mov     rbx, [rsp+28h+arg_0]
0x18000be82  add     rsp, 20h
0x18000be86  pop     rdi
0x18000be87  retn
```
