# FaceDetectionMFT::~FaceDetectionMFT(void)

- ea: `0x18000ed4c`
- end: `0x18000ef5a`
- name: `??1FaceDetectionMFT@@EEAA@XZ`
- size: `526`
- prototype: `void __fastcall(FaceDetectionMFT *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fb20`

## callees

- `0x180005660`
- `0x18000c0b8`
- `0x18000e780`
- `0x18000e8a4`
- `0x18000eacc`
- `0x18000ed4c`
- `0x180010b68`
- `0x18001c51c`
- `0x18001d3b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ef20`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ef2d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ef3a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ef47`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ef20`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ef2d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ef3a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000ef47`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ee55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ee72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ee55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ee72`

## pseudocode

```c
void __fastcall FaceDetectionMFT::~FaceDetectionMFT(FaceDetectionMFT *this)
{
  void *v2; // rcx
  void *v3; // rcx
  std::_Ref_count_base *v4; // rcx

  *(_QWORD *)this = &FaceDetectionMFT::`vftable'{for `Windows::Media::IMediaExtension'};
  *((_QWORD *)this + 1) = &FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFRealTimeClientEx>,Microsoft::WRL::CloakedIid<ICaptureSourceDeviceControllerClient>,Microsoft::WRL::CloakedIid<IMFShutdown>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMFRealTimeClientEx>'};
  *((_QWORD *)this + 3) = &FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ICaptureSourceDeviceControllerClient>,Microsoft::WRL::CloakedIid<IMFShutdown>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 4) = &FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMFShutdown>'};
  *((_QWORD *)this + 5) = &FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  *((_QWORD *)this + 38) = &FaceDetectionMFT::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 39) = &FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Media::Core::IFaceDetectionEffect,Microsoft::WRL::CloakedIid<IFaceDetectionEffectInternal>,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>'};
  *((_QWORD *)this + 40) = &FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IFaceDetectionEffectInternal>'};
  *((_QWORD *)this + 41) = &FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>'};
  *((_QWORD *)this + 42) = &FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMFDetectedFaceNotifierClient>'};
  *((_QWORD *)this + 43) = &FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>'};
  FaceDetectionMFT::CleanUp(this);
  if ( (unsigned __int8)byte_180160805 >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 13, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 17440);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset((char *)this + 17416);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 992);
  v2 = (void *)*((_QWORD *)this + 123);
  *((_QWORD *)this + 123) = 0;
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 122);
  *((_QWORD *)this + 122) = 0;
  if ( v3 )
    CoTaskMemFree(v3);
  AnalysisParameters::~AnalysisParameters((FaceDetectionMFT *)((char *)this + 760));
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 728);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 720);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 88);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 688);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 680);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 672);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 664);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 656);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 648);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 640);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 632);
  Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::~ComPtr<Microsoft::WRL::Details::EventTargetArray>((char *)this + 600);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 504));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 464));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CCoreMFT,Windows::Media::Core::IFaceDetectionEffect,Microsoft::WRL::CloakedIid<IFaceDetectionEffectInternal>,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CCoreMFT,Windows::Media::Core::IFaceDetectionEffect,Microsoft::WRL::CloakedIid<IFaceDetectionEffectInternal>,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>(this);
}

```

## disassembly

```asm
0x18000ed4c  push    rbx
0x18000ed4e  sub     rsp, 20h
0x18000ed52  mov     rbx, rcx
0x18000ed55  lea     rax, ??_7FaceDetectionMFT@@6BIMediaExtension@Media@Windows@@@; const FaceDetectionMFT::`vftable'{for `Windows::Media::IMediaExtension'}
0x18000ed5c  mov     [rcx], rax
0x18000ed5f  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIMFTransform@@@23@U?$CloakedIid@UIMFRealTimeClientEx@@@23@U?$CloakedIid@UICaptureSourceDeviceControllerClient@@@23@U?$CloakedIid@UIMFShutdown@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFRealTimeClientEx>,Microsoft::WRL::CloakedIid<ICaptureSourceDeviceControllerClient>,Microsoft::WRL::CloakedIid<IMFShutdown>,Microsoft::WRL::FtmBase>'}
0x18000ed66  mov     [rcx+8], rax
0x18000ed6a  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIMFRealTimeClientEx@@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMFRealTimeClientEx>'}
0x18000ed71  mov     [rcx+10h], rax
0x18000ed75  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UICaptureSourceDeviceControllerClient@@@23@U?$CloakedIid@UIMFShutdown@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ICaptureSourceDeviceControllerClient>,Microsoft::WRL::CloakedIid<IMFShutdown>,Microsoft::WRL::FtmBase>'}
0x18000ed7c  mov     [rcx+18h], rax
0x18000ed80  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIMFShutdown@@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMFShutdown>'}
0x18000ed87  mov     [rcx+20h], rax
0x18000ed8b  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000ed92  mov     [rcx+28h], rax
0x18000ed96  lea     rax, ??_7FaceDetectionMFT@@6BIWeakReferenceSource@@@; const FaceDetectionMFT::`vftable'{for `IWeakReferenceSource'}
0x18000ed9d  mov     [rcx+130h], rax
0x18000eda4  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIFaceDetectionEffect@Core@Media@Windows@@U?$CloakedIid@UIFaceDetectionEffectInternal@@@23@U?$CloakedIid@UIDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFFaceDetectionTransform@@@23@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Media::Core::IFaceDetectionEffect,Microsoft::WRL::CloakedIid<IFaceDetectionEffectInternal>,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>'}
0x18000edab  mov     [rcx+138h], rax
0x18000edb2  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIFaceDetectionEffectInternal@@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IFaceDetectionEffectInternal>'}
0x18000edb9  mov     [rcx+140h], rax
0x18000edc0  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFFaceDetectionTransform@@@23@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>'}
0x18000edc7  mov     [rcx+148h], rax
0x18000edce  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIMFDetectedFaceNotifierClient@@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMFDetectedFaceNotifierClient>'}
0x18000edd5  mov     [rcx+150h], rax
0x18000eddc  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIMFFaceDetectionTransform@@@23@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>'}
0x18000ede3  mov     [rcx+158h], rax
0x18000edea  call    ?CleanUp@FaceDetectionMFT@@AEAAXXZ; FaceDetectionMFT::CleanUp(void)
0x18000edef  cmp     cs:byte_180160805, 20h ; ' '
0x18000edf6  jb      short loc_18000EE1A
0x18000edf8  mov     edx, 0Dh
0x18000edfd  mov     r9, rbx
0x18000ee00  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x18000ee07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ee0e  mov     rcx, [rcx+0D8h]
0x18000ee15  call    WPP_SF_q
0x18000ee1a  lea     rcx, [rbx+4420h]
0x18000ee21  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ee26  lea     rcx, [rbx+4408h]
0x18000ee2d  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x18000ee32  lea     rcx, [rbx+3E0h]
0x18000ee39  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ee3e  mov     rcx, [rbx+3D8h]; pv
0x18000ee45  mov     qword ptr [rbx+3D8h], 0
0x18000ee50  test    rcx, rcx
0x18000ee53  jz      short loc_18000EE5B
0x18000ee55  call    cs:__imp_CoTaskMemFree
0x18000ee5b  mov     rcx, [rbx+3D0h]; pv
0x18000ee62  mov     qword ptr [rbx+3D0h], 0
0x18000ee6d  test    rcx, rcx
0x18000ee70  jz      short loc_18000EE78
0x18000ee72  call    cs:__imp_CoTaskMemFree
0x18000ee78  lea     rcx, [rbx+2F8h]; this
0x18000ee7f  call    ??1AnalysisParameters@@QEAA@XZ; AnalysisParameters::~AnalysisParameters(void)
0x18000ee84  lea     rcx, [rbx+2D8h]
0x18000ee8b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ee90  lea     rcx, [rbx+2D0h]
0x18000ee97  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ee9c  mov     rcx, [rbx+2C0h]; this
0x18000eea3  test    rcx, rcx
0x18000eea6  jz      short loc_18000EEAD
0x18000eea8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000eead  lea     rcx, [rbx+2B0h]
0x18000eeb4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000eeb9  lea     rcx, [rbx+2A8h]
0x18000eec0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000eec5  lea     rcx, [rbx+2A0h]
0x18000eecc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000eed1  lea     rcx, [rbx+298h]
0x18000eed8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000eedd  lea     rcx, [rbx+290h]
0x18000eee4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000eee9  lea     rcx, [rbx+288h]
0x18000eef0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000eef5  lea     rcx, [rbx+280h]
0x18000eefc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ef01  lea     rcx, [rbx+278h]
0x18000ef08  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000ef0d  lea     rcx, [rbx+258h]
0x18000ef14  call    ??1?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::~ComPtr<Microsoft::WRL::Details::EventTargetArray>(void)
0x18000ef19  lea     rcx, [rbx+1F8h]; lpCriticalSection
0x18000ef20  call    cs:__imp_DeleteCriticalSection
0x18000ef26  lea     rcx, [rbx+1D0h]; lpCriticalSection
0x18000ef2d  call    cs:__imp_DeleteCriticalSection
0x18000ef33  lea     rcx, [rbx+1A8h]; lpCriticalSection
0x18000ef3a  call    cs:__imp_DeleteCriticalSection
0x18000ef40  lea     rcx, [rbx+180h]; lpCriticalSection
0x18000ef47  call    cs:__imp_DeleteCriticalSection
0x18000ef4d  mov     rcx, rbx; this
0x18000ef50  add     rsp, 20h
0x18000ef54  pop     rbx
0x18000ef55  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VCCoreMFT@@UIFaceDetectionEffect@Core@Media@Windows@@U?$CloakedIid@UIFaceDetectionEffectInternal@@@23@U?$CloakedIid@UIDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFFaceDetectionTransform@@@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CCoreMFT,Windows::Media::Core::IFaceDetectionEffect,Microsoft::WRL::CloakedIid<IFaceDetectionEffectInternal>,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CCoreMFT,Windows::Media::Core::IFaceDetectionEffect,Microsoft::WRL::CloakedIid<IFaceDetectionEffectInternal>,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>(void)
```
