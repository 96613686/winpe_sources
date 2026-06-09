# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&ushort const near * const GeotagBroker_SetGeotagInBrokerInternalAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncAction,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetIids(ulong *,_GUID * *)

- ea: `0x1800470a0`
- end: `0x180047109`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@V?$AsyncBaseWithProgressFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncCausalityOptions@$1?GeotagBroker_SetGeotagInBrokerInternalAsync@@3QBGB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UIAsyncAction@Foundation@6@UIAsyncOperationLocal@56@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180047110`

## callees

- `0x180032f08`
- `0x18004594c`
- `0x1800470a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800470c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800470c2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncCausalityOptions<&unsigned short const near * const GeotagBroker_SetGeotagInBrokerInternalAsync,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>,Windows::Foundation::IAsyncAction,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  int v10; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x40u);
  if ( !v6 )
    return 2147942414LL;
  v10 = 0;
  Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::DisableCausality>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v10,
    v6);
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IAsyncAction,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::FillArrayWithIid(
    v8,
    &v10);
  *a2 = 4;
  result = 0;
  *a3 = v9;
  return result;
}

```

## disassembly

```asm
0x1800470a0  mov     [rsp+arg_0], rbx
0x1800470a5  push    rdi
0x1800470a6  sub     rsp, 20h
0x1800470aa  mov     qword ptr [r8], 0
0x1800470b1  mov     ecx, 40h ; '@'; cb
0x1800470b6  mov     dword ptr [rdx], 0
0x1800470bc  mov     rbx, r8
0x1800470bf  mov     rdi, rdx
0x1800470c2  call    cs:__imp_CoTaskMemAlloc
0x1800470c8  mov     r8, rax
0x1800470cb  test    rax, rax
0x1800470ce  jnz     short loc_1800470D7
0x1800470d0  mov     eax, 8007000Eh
0x1800470d5  jmp     short loc_1800470FE
0x1800470d7  lea     rdx, [rsp+28h+arg_8]
0x1800470dc  mov     [rsp+28h+arg_8], 0
0x1800470e4  call    ?FillArrayWithIid@?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@V?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00UDisableCausality@67@@23@VFtmBase@23@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::DisableCausality>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800470e9  lea     rdx, [rsp+28h+arg_8]
0x1800470ee  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIAsyncAction@Foundation@Windows@@UIAsyncOperationLocal@Internal@7@U?$CloakedIid@UIAsyncDeferral@Internal@Windows@@@23@U?$CloakedIid@UIComPoolTask@Internal@Windows@@@23@U?$CloakedIid@UIAsyncFireCompletion@Internal@Windows@@@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Foundation::IAsyncAction,Windows::Internal::IAsyncOperationLocal,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncDeferral>,Microsoft::WRL::CloakedIid<Windows::Internal::IComPoolTask>,Microsoft::WRL::CloakedIid<Windows::Internal::IAsyncFireCompletion>>::FillArrayWithIid(ulong *,_GUID *)
0x1800470f3  mov     dword ptr [rdi], 4
0x1800470f9  xor     eax, eax
0x1800470fb  mov     [rbx], r8
0x1800470fe  mov     rbx, [rsp+28h+arg_0]
0x180047103  add     rsp, 20h
0x180047107  pop     rdi
0x180047108  retn
```
