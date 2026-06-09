# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CCoreMFT,Windows::Media::Core::IFaceDetectionEffect,Microsoft::WRL::CloakedIid<IFaceDetectionEffectInternal>,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>::GetIids(ulong *,_GUID * *)

- ea: `0x180013880`
- end: `0x1800138e9`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VCCoreMFT@@UIFaceDetectionEffect@Core@Media@Windows@@U?$CloakedIid@UIFaceDetectionEffectInternal@@@23@U?$CloakedIid@UIDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFFaceDetectionTransform@@@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `105`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800138f0`
- `0x180013910`
- `0x180013930`
- `0x180013950`
- `0x180013970`

## callees

- `0x180012348`
- `0x180012394`
- `0x180013880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800138a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800138a2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CCoreMFT,Windows::Media::Core::IFaceDetectionEffect,Microsoft::WRL::CloakedIid<IFaceDetectionEffectInternal>,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>::GetIids(
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
  v6 = CoTaskMemAlloc(0x30u);
  if ( !v6 )
    return 2147942414LL;
  v10 = 0;
  Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFRealTimeClientEx>,Microsoft::WRL::CloakedIid<ICaptureSourceDeviceControllerClient>,Microsoft::WRL::CloakedIid<IMFShutdown>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v10,
    v6);
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Media::Core::IFaceDetectionEffect,Microsoft::WRL::CloakedIid<IFaceDetectionEffectInternal>,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>::FillArrayWithIid(
    v8,
    &v10);
  *a2 = 3;
  result = 0;
  *a3 = v9;
  return result;
}

```

## disassembly

```asm
0x180013880  mov     [rsp+arg_0], rbx
0x180013885  push    rdi
0x180013886  sub     rsp, 20h
0x18001388a  mov     qword ptr [r8], 0
0x180013891  mov     ecx, 30h ; '0'; cb
0x180013896  mov     dword ptr [rdx], 0
0x18001389c  mov     rbx, r8
0x18001389f  mov     rdi, rdx
0x1800138a2  call    cs:__imp_CoTaskMemAlloc
0x1800138a8  mov     r8, rax
0x1800138ab  test    rax, rax
0x1800138ae  jnz     short loc_1800138B7
0x1800138b0  mov     eax, 8007000Eh
0x1800138b5  jmp     short loc_1800138DE
0x1800138b7  lea     rdx, [rsp+28h+arg_8]
0x1800138bc  mov     [rsp+28h+arg_8], 0
0x1800138c4  call    ?FillArrayWithIid@?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIMediaExtension@Media@Windows@@U?$CloakedIid@UIMFTransform@@@23@U?$CloakedIid@UIMFRealTimeClientEx@@@23@U?$CloakedIid@UICaptureSourceDeviceControllerClient@@@23@U?$CloakedIid@UIMFShutdown@@@23@VFtmBase@23@@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,Windows::Media::IMediaExtension,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFRealTimeClientEx>,Microsoft::WRL::CloakedIid<ICaptureSourceDeviceControllerClient>,Microsoft::WRL::CloakedIid<IMFShutdown>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x1800138c9  lea     rdx, [rsp+28h+arg_8]
0x1800138ce  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIFaceDetectionEffect@Core@Media@Windows@@U?$CloakedIid@UIFaceDetectionEffectInternal@@@23@U?$CloakedIid@UIDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFFaceDetectionTransform@@@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::Media::Core::IFaceDetectionEffect,Microsoft::WRL::CloakedIid<IFaceDetectionEffectInternal>,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>::FillArrayWithIid(ulong *,_GUID *)
0x1800138d3  mov     dword ptr [rdi], 3
0x1800138d9  xor     eax, eax
0x1800138db  mov     [rbx], r8
0x1800138de  mov     rbx, [rsp+28h+arg_0]
0x1800138e3  add     rsp, 20h
0x1800138e7  pop     rdi
0x1800138e8  retn
```
