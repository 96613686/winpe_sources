# Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,CCoreMFT,Windows::Media::Core::ISceneAnalysisEffect,Windows::Media::Core::ISceneAnalysisEffectInternal,Microsoft::WRL::CloakedIid<Windows::Media::Effects::IPlatformEffect>>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,CCoreMFT,Windows::Media::Core::ISceneAnalysisEffect,Windows::Media::Core::ISceneAnalysisEffectInternal,Microsoft::WRL::CloakedIid<Windows::Media::Effects::IPlatformEffect>> *,ulong *,_GUID * *)

- ea: `0x1800acd34`
- end: `0x1800acdd5`
- name: `??$GetImplementedIIDS@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCCoreMFT@@UISceneAnalysisEffect@Core@Media@Windows@@UISceneAnalysisEffectInternal@678@U?$CloakedIid@UIPlatformEffect@Effects@Media@Windows@@@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$00@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VCCoreMFT@@UISceneAnalysisEffect@Core@Media@Windows@@UISceneAnalysisEffectInternal@678@U?$CloakedIid@UIPlatformEffect@Effects@Media@Windows@@@23@@123@PEAKPEAPEAU_GUID@@@Z`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800addd0`

## callees

- `0x180012348`
- `0x1800acd34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800acd5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800acd5b`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassBaseT<1>::GetImplementedIIDS<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,CCoreMFT,Windows::Media::Core::ISceneAnalysisEffect,Windows::Media::Core::ISceneAnalysisEffectInternal,Microsoft::WRL::CloakedIid<Windows::Media::Effects::IPlatformEffect>>>(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  unsigned int v8; // edx
  __int64 v9; // r8
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = a1;
  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x40u);
  if ( !v6 )
    return 2147942414LL;
  LODWORD(v10) = 0;
  Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFRealTimeClientEx>,Microsoft::WRL::CloakedIid<ICaptureSourceDeviceControllerClient>,Microsoft::WRL::CloakedIid<IMFShutdown>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v10,
    v6);
  v8 = v10 + 1;
  *(GUID *)(v9 + 16LL * (unsigned int)v10) = GUID_00000038_0000_0000_c000_000000000046;
  *(GUID *)(v9 + 16LL * v8) = GUID_c04ba319_ca41_4813_bffd_7b08b0ed2557;
  result = 0;
  *(GUID *)(v9 + 16LL * (v8 + 1)) = GUID_d69b14e5_1e8f_4ff5_9fcb_45b373686c9b;
  *a2 = 4;
  *a3 = v9;
  return result;
}

```

## disassembly

```asm
0x1800acd34  mov     [rsp+arg_8], rbx
0x1800acd39  mov     [rsp+arg_0], rcx
0x1800acd3e  push    rdi
0x1800acd3f  sub     rsp, 20h
0x1800acd43  mov     qword ptr [r8], 0
0x1800acd4a  mov     ecx, 40h ; '@'; cb
0x1800acd4f  mov     dword ptr [rdx], 0
0x1800acd55  mov     rbx, r8
0x1800acd58  mov     rdi, rdx
0x1800acd5b  call    cs:__imp_CoTaskMemAlloc
0x1800acd61  mov     r8, rax
0x1800acd64  test    rax, rax
0x1800acd67  jnz     short loc_1800ACD70
0x1800acd69  mov     eax, 8007000Eh
0x1800acd6e  jmp     short loc_1800ACDCA
0x1800acd70  lea     rdx, [rsp+28h+arg_0]
0x1800acd75  mov     dword ptr [rsp+28h+arg_0], 0
0x1800acd7d  call    ?FillArrayWithIid@?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIMediaExtension@Media@Windows@@U?$CloakedIid@UIMFTransform@@@23@U?$CloakedIid@UIMFRealTimeClientEx@@@23@U?$CloakedIid@UICaptureSourceDeviceControllerClient@@@23@U?$CloakedIid@UIMFShutdown@@@23@VFtmBase@23@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFRealTimeClientEx>,Microsoft::WRL::CloakedIid<ICaptureSourceDeviceControllerClient>,Microsoft::WRL::CloakedIid<IMFShutdown>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800acd82  movups  xmm0, xmmword ptr cs:_GUID_00000038_0000_0000_c000_000000000046.Data1
0x1800acd89  mov     edx, dword ptr [rsp+28h+arg_0]
0x1800acd8d  mov     eax, edx
0x1800acd8f  add     rax, rax
0x1800acd92  inc     edx
0x1800acd94  movdqu  xmmword ptr [r8+rax*8], xmm0
0x1800acd9a  mov     eax, edx
0x1800acd9c  lea     ecx, [rdx+1]
0x1800acd9f  movups  xmm0, xmmword ptr cs:_GUID_c04ba319_ca41_4813_bffd_7b08b0ed2557.Data1
0x1800acda6  add     rax, rax
0x1800acda9  add     rcx, rcx
0x1800acdac  movdqu  xmmword ptr [r8+rax*8], xmm0
0x1800acdb2  xor     eax, eax
0x1800acdb4  movups  xmm0, xmmword ptr cs:_GUID_d69b14e5_1e8f_4ff5_9fcb_45b373686c9b.Data1
0x1800acdbb  movdqu  xmmword ptr [r8+rcx*8], xmm0
0x1800acdc1  mov     dword ptr [rdi], 4
0x1800acdc7  mov     [rbx], r8
0x1800acdca  mov     rbx, [rsp+28h+arg_8]
0x1800acdcf  add     rsp, 20h
0x1800acdd3  pop     rdi
0x1800acdd4  retn
```
