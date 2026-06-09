# FaceDetectionMFT::FaceDetectionMFT(void)

- ea: `0x18000dc9c`
- end: `0x18000e143`
- name: `??0FaceDetectionMFT@@QEAA@XZ`
- size: `1191`
- prototype: `FaceDetectionMFT *__fastcall(FaceDetectionMFT *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007df4`
- `0x180007eac`

## callees

- `0x18000290c`
- `0x18000c0b8`
- `0x18000d64c`
- `0x18000d748`
- `0x18000d800`
- `0x18000dc9c`
- `0x18000fcdc`
- `0x1800151a0`
- `0x180017f8c`
- `0x18001b2c0`
- `0x18001d8f4`
- `0x18001da94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000de0c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000de19`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000de0c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000de19`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dd6f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dd7d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dd8b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dd99`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dd6f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dd7d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dd8b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000dd99`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e01d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e0aa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e01d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e0aa`
- `MFPlat!MFGetSystemTime` at `0x18000dfa0`
- `MFPlat!MFGetSystemTime` at `0x18000dfa0`

## string_xrefs

- `0x18000e095`: `FaceAreaDeltaTolerancePerCent`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
FaceDetectionMFT *__fastcall FaceDetectionMFT::FaceDetectionMFT(FaceDetectionMFT *this)
{
  __int64 v2; // rdi
  CAggregatePhotographyTelemetry *v3; // rax
  CAggregatePhotographyTelemetry *v4; // rax
  CAggregatePhotographyTelemetry *v5; // rsi
  MFTIME v6; // rax
  double v7; // xmm2_8
  LSTATUS ValueW; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  signed int v11; // ecx
  int v12; // ecx
  LSTATUS v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  signed int v16; // ecx
  _BYTE *v17; // rax
  DWORD pcbData; // [rsp+88h] [rbp+38h] BYREF
  int pvData; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v21; // [rsp+98h] [rbp+48h] BYREF

  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,CCoreMFT,Windows::Media::Core::IFaceDetectionEffect,Microsoft::WRL::CloakedIid<IFaceDetectionEffectInternal>,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,CCoreMFT,Windows::Media::Core::IFaceDetectionEffect,Microsoft::WRL::CloakedIid<IFaceDetectionEffectInternal>,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>();
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
  *((_QWORD *)this + 46) = &FaceDetectionMFT::RunAnalysisAsyncCallback::`vftable';
  *((_QWORD *)this + 47) = &FaceDetectionMFT::TriggerHardwareEventCallAsyncCallback::`vftable';
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 384));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 464));
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 504));
  *((_WORD *)this + 272) = 257;
  *((_BYTE *)this + 546) = 1;
  *((_QWORD *)this + 69) = 2000000;
  *((_WORD *)this + 280) = 0;
  *((_BYTE *)this + 562) = 0;
  *((_DWORD *)this + 141) = 0;
  *((_BYTE *)this + 568) = 0;
  *((_DWORD *)this + 143) = 1065353216;
  *((_QWORD *)this + 72) = 800;
  *((_QWORD *)this + 73) = 0;
  *((_BYTE *)this + 592) = 0;
  *((_QWORD *)this + 75) = 0;
  InitializeSRWLock((PSRWLOCK)this + 76);
  InitializeSRWLock((PSRWLOCK)this + 77);
  *((_BYTE *)this + 624) = 0;
  *((_QWORD *)this + 79) = 0;
  *((_QWORD *)this + 80) = 0;
  *((_QWORD *)this + 81) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 88) = 0;
  *((_WORD *)this + 356) = 1;
  *((_QWORD *)this + 90) = 0;
  *((_QWORD *)this + 91) = 0;
  AnalysisParameters::AnalysisParameters((FaceDetectionMFT *)((char *)this + 760));
  *((_QWORD *)this + 122) = 0;
  *((_QWORD *)this + 123) = 0;
  *((_QWORD *)this + 124) = 0;
  *((_QWORD *)this + 125) = 0;
  *((_DWORD *)this + 252) = 2;
  *((_DWORD *)this + 253) = 3;
  *((_DWORD *)this + 254) = 4;
  *((_DWORD *)this + 255) = 3;
  *((_WORD *)this + 512) = 1;
  *((_BYTE *)this + 1026) = 0;
  *((_QWORD *)this + 2177) = 0;
  *((_QWORD *)this + 2178) = 1000000;
  *((_DWORD *)this + 4358) = 5;
  *((_QWORD *)this + 2180) = 0;
  *(GUID *)((char *)this + 17464) = GUID_00000000_0000_0000_0000_000000000000;
  *((_DWORD *)this + 4370) = 0;
  v2 = 10;
  if ( (unsigned __int8)byte_180160805 >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this);
  *((_DWORD *)this + 202) = *((_DWORD *)this + 20);
  *((_DWORD *)this + 203) = *((_DWORD *)this + 21);
  v3 = (CAggregatePhotographyTelemetry *)operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v3 )
    v4 = CAggregatePhotographyTelemetry::CAggregatePhotographyTelemetry(v3, "FaceDetection");
  else
    v4 = 0;
  *((_QWORD *)this + 2181) = v4;
  if ( v4 )
  {
    CAggregatePhotographyTelemetry::Start(v4);
    v5 = (CAggregatePhotographyTelemetry *)*((_QWORD *)this + 2181);
    v6 = MFGetSystemTime();
    if ( v6 < 0 )
      v7 = (double)(int)(v6 & 1 | ((unsigned __int64)v6 >> 1)) + (double)(int)(v6 & 1 | ((unsigned __int64)v6 >> 1));
    else
      v7 = (double)(int)v6;
    CAggregatePhotographyTelemetry::AddData(v5, 0, v7 / 10000.0);
  }
  pvData = 10;
  v21 = 10;
  pcbData = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows Media Foundation\\Platform\\FaceDetection",
             L"FaceCenterDeltaTolerancePerCent",
             0x10u,
             0,
             &pvData,
             &pcbData);
  if ( ValueW > 0 )
    v11 = (unsigned __int16)ValueW | 0x80070000;
  else
    v11 = ValueW;
  if ( v11 >= 0 && pcbData == 4 )
  {
    v12 = pvData;
    *((_DWORD *)this + 241) = pvData;
  }
  else
  {
    *((_DWORD *)this + 241) = 10;
    v12 = 10;
  }
  if ( (unsigned __int8)byte_180160805 >= 0x20u )
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 27), v9, v10, (unsigned int)ValueW, v12);
  pcbData = 4;
  v13 = RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows Media Foundation\\Platform\\FaceDetection",
          L"FaceAreaDeltaTolerancePerCent",
          0x10u,
          0,
          &v21,
          &pcbData);
  if ( v13 > 0 )
    v16 = (unsigned __int16)v13 | 0x80070000;
  else
    v16 = v13;
  if ( v16 >= 0 && pcbData == 4 )
    v2 = v21;
  *((_QWORD *)this + 121) = v2;
  if ( (unsigned __int8)byte_180160805 >= 0x20u )
    WPP_SF_di(*((_QWORD *)WPP_GLOBAL_Control + 27), v14, v15, (unsigned int)v13, v2);
  v17 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v17 )
  {
    *(_QWORD *)v17 = 0;
    v17[8] = 0;
  }
  else
  {
    v17 = 0;
  }
  *((_QWORD *)this + 2182) = v17;
  FaceDetectionMFT::ResetAnalysisState(this);
  FaceDetectionMFT::InitializeStreaming(this);
  return this;
}

```

## disassembly

```asm
0x18000dc9c  mov     [rsp-28h+arg_0], rcx
0x18000dca1  push    rbp
0x18000dca2  push    rbx
0x18000dca3  push    rsi
0x18000dca4  push    rdi
0x18000dca5  push    r14
0x18000dca7  mov     rbp, rsp
0x18000dcaa  sub     rsp, 50h
0x18000dcae  mov     rbx, rcx
0x18000dcb1  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@VCCoreMFT@@UIFaceDetectionEffect@Core@Media@Windows@@U?$CloakedIid@UIFaceDetectionEffectInternal@@@23@U?$CloakedIid@UIDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFFaceDetectionTransform@@@23@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,CCoreMFT,Windows::Media::Core::IFaceDetectionEffect,Microsoft::WRL::CloakedIid<IFaceDetectionEffectInternal>,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,CCoreMFT,Windows::Media::Core::IFaceDetectionEffect,Microsoft::WRL::CloakedIid<IFaceDetectionEffectInternal>,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>(void)
0x18000dcb6  nop
0x18000dcb7  lea     rax, ??_7FaceDetectionMFT@@6BIMediaExtension@Media@Windows@@@; const FaceDetectionMFT::`vftable'{for `Windows::Media::IMediaExtension'}
0x18000dcbe  mov     [rbx], rax
0x18000dcc1  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIMFTransform@@@23@U?$CloakedIid@UIMFRealTimeClientEx@@@23@U?$CloakedIid@UICaptureSourceDeviceControllerClient@@@23@U?$CloakedIid@UIMFShutdown@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMFTransform>,Microsoft::WRL::CloakedIid<IMFRealTimeClientEx>,Microsoft::WRL::CloakedIid<ICaptureSourceDeviceControllerClient>,Microsoft::WRL::CloakedIid<IMFShutdown>,Microsoft::WRL::FtmBase>'}
0x18000dcc8  mov     [rbx+8], rax
0x18000dccc  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIMFRealTimeClientEx@@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMFRealTimeClientEx>'}
0x18000dcd3  mov     [rbx+10h], rax
0x18000dcd7  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UICaptureSourceDeviceControllerClient@@@23@U?$CloakedIid@UIMFShutdown@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ICaptureSourceDeviceControllerClient>,Microsoft::WRL::CloakedIid<IMFShutdown>,Microsoft::WRL::FtmBase>'}
0x18000dcde  mov     [rbx+18h], rax
0x18000dce2  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIMFShutdown@@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMFShutdown>'}
0x18000dce9  mov     [rbx+20h], rax
0x18000dced  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18000dcf4  mov     [rbx+28h], rax
0x18000dcf8  lea     rax, ??_7FaceDetectionMFT@@6BIWeakReferenceSource@@@; const FaceDetectionMFT::`vftable'{for `IWeakReferenceSource'}
0x18000dcff  mov     [rbx+130h], rax
0x18000dd06  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIFaceDetectionEffect@Core@Media@Windows@@U?$CloakedIid@UIFaceDetectionEffectInternal@@@23@U?$CloakedIid@UIDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFFaceDetectionTransform@@@23@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Media::Core::IFaceDetectionEffect,Microsoft::WRL::CloakedIid<IFaceDetectionEffectInternal>,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>'}
0x18000dd0d  mov     [rbx+138h], rax
0x18000dd14  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIFaceDetectionEffectInternal@@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IFaceDetectionEffectInternal>'}
0x18000dd1b  mov     [rbx+140h], rax
0x18000dd22  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFDetectedFaceNotifierClient@@@23@U?$CloakedIid@UIMFFaceDetectionTransform@@@23@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFDetectedFaceNotifierClient>,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>'}
0x18000dd29  mov     [rbx+148h], rax
0x18000dd30  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIMFDetectedFaceNotifierClient@@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IMFDetectedFaceNotifierClient>'}
0x18000dd37  mov     [rbx+150h], rax
0x18000dd3e  lea     rax, ??_7FaceDetectionMFT@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UIMFFaceDetectionTransform@@@23@@Details@WRL@Microsoft@@@; const FaceDetectionMFT::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<IMFFaceDetectionTransform>>'}
0x18000dd45  mov     [rbx+158h], rax
0x18000dd4c  lea     rax, ??_7RunAnalysisAsyncCallback@FaceDetectionMFT@@6B@; const FaceDetectionMFT::RunAnalysisAsyncCallback::`vftable'
0x18000dd53  mov     [rbx+170h], rax
0x18000dd5a  lea     rax, ??_7TriggerHardwareEventCallAsyncCallback@FaceDetectionMFT@@6B@; const FaceDetectionMFT::TriggerHardwareEventCallAsyncCallback::`vftable'
0x18000dd61  mov     [rbx+178h], rax
0x18000dd68  lea     rcx, [rbx+180h]; lpCriticalSection
0x18000dd6f  call    cs:__imp_InitializeCriticalSection
0x18000dd75  nop
0x18000dd76  lea     rcx, [rbx+1A8h]; lpCriticalSection
0x18000dd7d  call    cs:__imp_InitializeCriticalSection
0x18000dd83  nop
0x18000dd84  lea     rcx, [rbx+1D0h]; lpCriticalSection
0x18000dd8b  call    cs:__imp_InitializeCriticalSection
0x18000dd91  nop
0x18000dd92  lea     rcx, [rbx+1F8h]; lpCriticalSection
0x18000dd99  call    cs:__imp_InitializeCriticalSection
0x18000dd9f  nop
0x18000dda0  mov     word ptr [rbx+220h], 101h
0x18000dda9  mov     byte ptr [rbx+222h], 1
0x18000ddb0  mov     qword ptr [rbx+228h], 1E8480h
0x18000ddbb  xor     r14d, r14d
0x18000ddbe  mov     [rbx+230h], r14w
0x18000ddc6  mov     [rbx+232h], r14b
0x18000ddcd  mov     [rbx+234h], r14d
0x18000ddd4  mov     [rbx+238h], r14b
0x18000dddb  mov     dword ptr [rbx+23Ch], 3F800000h
0x18000dde5  mov     qword ptr [rbx+240h], 320h
0x18000ddf0  mov     [rbx+248h], r14
0x18000ddf7  mov     [rbx+250h], r14b
0x18000ddfe  mov     [rbx+258h], r14
0x18000de05  lea     rcx, [rbx+260h]; SRWLock
0x18000de0c  call    cs:__imp_InitializeSRWLock
0x18000de12  lea     rcx, [rbx+268h]; SRWLock
0x18000de19  call    cs:__imp_InitializeSRWLock
0x18000de1f  nop
0x18000de20  mov     [rbx+270h], r14b
0x18000de27  mov     [rbx+278h], r14
0x18000de2e  mov     [rbx+280h], r14
0x18000de35  mov     [rbx+288h], r14
0x18000de3c  mov     [rbx+290h], r14
0x18000de43  mov     [rbx+298h], r14
0x18000de4a  mov     [rbx+2A0h], r14
0x18000de51  mov     [rbx+2A8h], r14
0x18000de58  mov     [rbx+2B0h], r14
0x18000de5f  mov     [rbx+2B8h], r14
0x18000de66  mov     [rbx+2C0h], r14
0x18000de6d  mov     word ptr [rbx+2C8h], 1
0x18000de76  mov     [rbx+2D0h], r14
0x18000de7d  mov     [rbx+2D8h], r14
0x18000de84  lea     rcx, [rbx+2F8h]; this
0x18000de8b  call    ??0AnalysisParameters@@QEAA@XZ; AnalysisParameters::AnalysisParameters(void)
0x18000de90  nop
0x18000de91  mov     [rbx+3D0h], r14
0x18000de98  mov     [rbx+3D8h], r14
0x18000de9f  mov     [rbx+3E0h], r14
0x18000dea6  mov     [rbx+3E8h], r14
0x18000dead  mov     dword ptr [rbx+3F0h], 2
0x18000deb7  lea     eax, [r14+3]
0x18000debb  mov     [rbx+3F4h], eax
0x18000dec1  mov     dword ptr [rbx+3F8h], 4
0x18000decb  mov     [rbx+3FCh], eax
0x18000ded1  mov     word ptr [rbx+400h], 1
0x18000deda  mov     [rbx+402h], r14b
0x18000dee1  mov     [rbx+4408h], r14
0x18000dee8  mov     qword ptr [rbx+4410h], 0F4240h
0x18000def3  mov     dword ptr [rbx+4418h], 5
0x18000defd  mov     [rbx+4420h], r14
0x18000df04  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000df0b  movdqu  xmmword ptr [rbx+4438h], xmm0
0x18000df13  mov     [rbx+4448h], r14d
0x18000df1a  lea     edi, [rax+7]
0x18000df1d  cmp     cs:byte_180160805, 20h ; ' '
0x18000df24  jb      short loc_18000DF45
0x18000df26  mov     edx, edi
0x18000df28  mov     r9, rbx
0x18000df2b  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x18000df32  mov     rcx, cs:WPP_GLOBAL_Control
0x18000df39  mov     rcx, [rcx+0D8h]
0x18000df40  call    WPP_SF_q
0x18000df45  mov     eax, [rbx+50h]
0x18000df48  mov     [rbx+328h], eax
0x18000df4e  mov     eax, [rbx+54h]
0x18000df51  mov     [rbx+32Ch], eax
0x18000df57  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000df5e  mov     ecx, 28h ; '('; unsigned __int64
0x18000df63  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000df68  mov     [rbp+var_10], rax
0x18000df6c  test    rax, rax
0x18000df6f  jz      short loc_18000DF82
0x18000df71  lea     rdx, aFacedetection; "FaceDetection"
0x18000df78  mov     rcx, rax; this
0x18000df7b  call    ??0CAggregatePhotographyTelemetry@@QEAA@PEBD@Z; CAggregatePhotographyTelemetry::CAggregatePhotographyTelemetry(char const *)
0x18000df80  jmp     short loc_18000DF85
0x18000df82  mov     rax, r14
0x18000df85  mov     [rbx+4428h], rax
0x18000df8c  test    rax, rax
0x18000df8f  jz      short loc_18000DFDC
0x18000df91  mov     rcx, rax; this
0x18000df94  call    ?Start@CAggregatePhotographyTelemetry@@QEAAXXZ; CAggregatePhotographyTelemetry::Start(void)
0x18000df99  mov     rsi, [rbx+4428h]
0x18000dfa0  call    cs:__imp_MFGetSystemTime
0x18000dfa6  mov     rcx, rax
0x18000dfa9  xorps   xmm2, xmm2
0x18000dfac  test    rax, rax
0x18000dfaf  js      short loc_18000DFB8
0x18000dfb1  cvtsi2sd xmm2, rax
0x18000dfb6  jmp     short loc_18000DFCA
0x18000dfb8  shr     rax, 1
0x18000dfbb  and     ecx, 1
0x18000dfbe  or      rax, rcx
0x18000dfc1  cvtsi2sd xmm2, rax
0x18000dfc6  addsd   xmm2, xmm2
0x18000dfca  divsd   xmm2, cs:__real@40c3880000000000; double
0x18000dfd2  xor     edx, edx; unsigned int
0x18000dfd4  mov     rcx, rsi; this
0x18000dfd7  call    ?AddData@CAggregatePhotographyTelemetry@@QEAAXKN@Z; CAggregatePhotographyTelemetry::AddData(ulong,double)
0x18000dfdc  mov     [rbp+arg_10], edi
0x18000dfdf  mov     [rbp+arg_18], edi
0x18000dfe2  mov     [rbp+arg_8], 4
0x18000dfe9  lea     rax, [rbp+arg_8]
0x18000dfed  mov     [rsp+50h+pcbData], rax; pcbData
0x18000dff2  lea     rax, [rbp+arg_10]
0x18000dff6  mov     [rsp+50h+pvData], rax; pvData
0x18000dffb  mov     [rsp+50h+pdwType], r14; pdwType
0x18000e000  mov     esi, 10h
0x18000e005  mov     r9d, esi; dwFlags
0x18000e008  lea     r8, Value; "FaceCenterDeltaTolerancePerCent"
0x18000e00f  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows Media Foun"...
0x18000e016  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000e01d  call    cs:__imp_RegGetValueW
0x18000e023  test    eax, eax
0x18000e025  jg      short loc_18000E02B
0x18000e027  mov     ecx, eax
0x18000e029  jmp     short loc_18000E034
0x18000e02b  movzx   ecx, ax
0x18000e02e  or      ecx, 80070000h
0x18000e034  test    ecx, ecx
0x18000e036  js      short loc_18000E049
0x18000e038  cmp     [rbp+arg_8], 4
0x18000e03c  jnz     short loc_18000E049
0x18000e03e  mov     ecx, [rbp+arg_10]
0x18000e041  mov     [rbx+3C4h], ecx
0x18000e047  jmp     short loc_18000E051
0x18000e049  mov     [rbx+3C4h], edi
0x18000e04f  mov     ecx, edi
0x18000e051  cmp     cs:byte_180160805, 20h ; ' '
0x18000e058  jb      short loc_18000E074
0x18000e05a  mov     dword ptr [rsp+50h+pdwType], ecx
0x18000e05e  mov     r9d, eax
0x18000e061  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e068  mov     rcx, [rcx+0D8h]
0x18000e06f  call    WPP_SF_dd
0x18000e074  mov     [rbp+arg_8], 4
0x18000e07b  lea     rax, [rbp+arg_8]
0x18000e07f  mov     [rsp+50h+pcbData], rax; pcbData
0x18000e084  lea     rax, [rbp+arg_18]
0x18000e088  mov     [rsp+50h+pvData], rax; pvData
0x18000e08d  mov     [rsp+50h+pdwType], r14; pdwType
0x18000e092  mov     r9d, esi; dwFlags
0x18000e095  lea     r8, aFaceareadeltat; "FaceAreaDeltaTolerancePerCent"
0x18000e09c  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows Media Foun"...
0x18000e0a3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000e0aa  call    cs:__imp_RegGetValueW
0x18000e0b0  test    eax, eax
0x18000e0b2  jg      short loc_18000E0B8
0x18000e0b4  mov     ecx, eax
0x18000e0b6  jmp     short loc_18000E0C1
0x18000e0b8  movzx   ecx, ax
0x18000e0bb  or      ecx, 80070000h
0x18000e0c1  test    ecx, ecx
0x18000e0c3  js      short loc_18000E0CE
0x18000e0c5  cmp     [rbp+arg_8], 4
0x18000e0c9  jnz     short loc_18000E0CE
0x18000e0cb  mov     edi, [rbp+arg_18]
0x18000e0ce  mov     [rbx+3C8h], rdi
0x18000e0d5  cmp     cs:byte_180160805, 20h ; ' '
0x18000e0dc  jb      short loc_18000E0F9
0x18000e0de  mov     [rsp+50h+pdwType], rdi
0x18000e0e3  mov     r9d, eax
0x18000e0e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e0ed  mov     rcx, [rcx+0D8h]
0x18000e0f4  call    WPP_SF_di
0x18000e0f9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e100  mov     rcx, rsi; unsigned __int64
0x18000e103  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e108  mov     [rbp+var_10], rax
0x18000e10c  test    rax, rax
0x18000e10f  jz      short loc_18000E11A
0x18000e111  mov     [rax], r14
0x18000e114  mov     [rax+8], r14b
0x18000e118  jmp     short loc_18000E11D
0x18000e11a  mov     rax, r14
0x18000e11d  mov     [rbx+4430h], rax
0x18000e124  mov     rcx, rbx; this
0x18000e127  call    ?ResetAnalysisState@FaceDetectionMFT@@AEAAXXZ; FaceDetectionMFT::ResetAnalysisState(void)
0x18000e12c  mov     rcx, rbx; this
0x18000e12f  call    ?InitializeStreaming@FaceDetectionMFT@@EEAAJXZ; FaceDetectionMFT::InitializeStreaming(void)
0x18000e134  nop
0x18000e135  mov     rax, rbx
0x18000e138  add     rsp, 50h
0x18000e13c  pop     r14
0x18000e13e  pop     rdi
0x18000e13f  pop     rsi
0x18000e140  pop     rbx
0x18000e141  pop     rbp
0x18000e142  retn
```
