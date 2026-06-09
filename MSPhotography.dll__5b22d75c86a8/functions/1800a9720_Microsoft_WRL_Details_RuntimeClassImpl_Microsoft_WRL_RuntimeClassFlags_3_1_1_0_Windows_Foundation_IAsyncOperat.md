# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::CloakedIid<Windows::System::Threading::IWorkItemHandler>,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Media::Core::LowLightFusionResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::GetIids(ulong *,_GUID * *)

- ea: `0x1800a9720`
- end: `0x1800a978a`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IAsyncOperationWithProgress@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@U?$CloakedIid@UIWorkItemHandler@Threading@System@Windows@@@23@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVLowLightFusionResult@Core@Media@Windows@@N@23@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@6@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800a9790`

## callees

- `0x18002d81c`
- `0x1800a9720`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a9742`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800a9742`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncOperationWithProgress<Windows::Media::Core::LowLightFusionResult *,double>,Microsoft::WRL::CloakedIid<Windows::System::Threading::IWorkItemHandler>,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Media::Core::LowLightFusionResult *,double>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Media::Core::LowLightFusionResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_a2302c2d_66b5_59c7_ab97_3f5793e21d43;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::System::Threading::IWorkItemHandler>,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x1800a9720  mov     [rsp+arg_0], rbx
0x1800a9725  push    rdi
0x1800a9726  sub     rsp, 20h
0x1800a972a  mov     qword ptr [r8], 0
0x1800a9731  mov     ecx, 30h ; '0'; cb
0x1800a9736  mov     dword ptr [rdx], 0
0x1800a973c  mov     rbx, r8
0x1800a973f  mov     rdi, rdx
0x1800a9742  call    cs:__imp_CoTaskMemAlloc
0x1800a9748  mov     r8, rax
0x1800a974b  test    rax, rax
0x1800a974e  jnz     short loc_1800A9757
0x1800a9750  mov     eax, 8007000Eh
0x1800a9755  jmp     short loc_1800A977F
0x1800a9757  movups  xmm0, xmmword ptr cs:_GUID_a2302c2d_66b5_59c7_ab97_3f5793e21d43.Data1
0x1800a975e  lea     rdx, [rsp+28h+arg_8]
0x1800a9763  mov     [rsp+28h+arg_8], 1
0x1800a976b  movdqu  xmmword ptr [rax], xmm0
0x1800a976f  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIWorkItemHandler@Threading@System@Windows@@@23@V?$AsyncBaseWithProgressFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@Foundation@Windows@@U?$IAsyncOperationProgressHandler@PEAVHighDynamicRangeResult@Internal@Imaging@Graphics@Windows@@N@23@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::System::Threading::IWorkItemHandler>,Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,Windows::Foundation::IAsyncOperationProgressHandler<Windows::Graphics::Imaging::Internal::HighDynamicRangeResult *,double>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>::FillArrayWithIid(ulong *,_GUID *)
0x1800a9774  mov     dword ptr [rdi], 3
0x1800a977a  xor     eax, eax
0x1800a977c  mov     [rbx], r8
0x1800a977f  mov     rbx, [rsp+28h+arg_0]
0x1800a9784  add     rsp, 20h
0x1800a9788  pop     rdi
0x1800a9789  retn
```
