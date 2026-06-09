# FaceDetectionMFT::InitializeNUIFaceDetector(void)

- ea: `0x180014ea0`
- end: `0x180014ffc`
- name: `?InitializeNUIFaceDetector@FaceDetectionMFT@@AEAAJXZ`
- size: `348`
- prototype: `__int64 __fastcall(FaceDetectionMFT *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015004`
- `0x180019de0`

## callees

- `0x180005660`
- `0x18000c0b8`
- `0x18000c0f8`
- `0x18000c4b4`
- `0x180014ea0`
- `0x18001c95c`
- `0x18001d3b0`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014f8c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180014f8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FaceDetectionMFT::InitializeNUIFaceDetector(FaceDetectionMFT *this)
{
  _QWORD *v2; // rbp
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64 *); // rbx
  HRESULT Instance; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v9; // [rsp+68h] [rbp+10h] BYREF

  v2 = (_QWORD *)((char *)this + 664);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CameraQI2511>::GetImpl'::`2'::impl)
    || !*v2 )
  {
    *((_DWORD *)this + 144) = 800;
    v9 = 0;
    v3 = *((_QWORD *)this + 2180);
    v4 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
    Instance = v4(v3, &v9);
    v6 = Instance;
    if ( Instance >= 0 )
    {
      Instance = BlockOnCompletionAndGetResults<Windows::Media::FaceAnalysis::FaceTracker *,Windows::Media::FaceAnalysis::IFaceTracker>(
                   v9,
                   v2);
      v6 = Instance;
      if ( Instance < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_14;
        v7 = 285;
        goto LABEL_6;
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 656);
      Instance = CoCreateInstance(
                   &CLSID_VideoFrameNativeFactory,
                   0,
                   1u,
                   &GUID_69e3693e_8e1e_4e63_ac4c_7fdc21d9731d,
                   (LPVOID *)this + 82);
      v6 = Instance;
      if ( Instance >= 0 )
      {
        wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset((char *)this + 17416);
        goto LABEL_14;
      }
      if ( g_wppLevels )
      {
        v7 = 286;
        goto LABEL_6;
      }
    }
    else if ( g_wppLevels )
    {
      v7 = 284;
LABEL_6:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
        this,
        Instance);
    }
LABEL_14:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v9);
    return v6;
  }
  if ( (unsigned __int8)byte_180160805 >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 283, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this);
  return 0;
}

```

## disassembly

```asm
0x180014ea0  push    rbx
0x180014ea2  push    rbp
0x180014ea3  push    rsi
0x180014ea4  push    rdi
0x180014ea5  sub     rsp, 38h
0x180014ea9  mov     rsi, rcx
0x180014eac  lea     rbp, [rcx+298h]
0x180014eb3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CameraQI2511@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CameraQI2511@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511> `wil::Feature<__WilFeatureTraits_Feature_CameraQI2511>::GetImpl(void)'::`2'::impl
0x180014eba  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CameraQI2511@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511>::__private_IsEnabled(void)
0x180014ebf  test    al, al
0x180014ec1  jz      short loc_180014ECE
0x180014ec3  cmp     qword ptr [rbp+0], 0
0x180014ec8  jnz     loc_180014FC6
0x180014ece  mov     dword ptr [rsi+240h], 320h
0x180014ed8  mov     [rsp+58h+arg_8], 0
0x180014ee1  mov     rdi, [rsi+4420h]
0x180014ee8  mov     rax, [rdi]
0x180014eeb  mov     rbx, [rax+30h]
0x180014eef  lea     rcx, [rsp+58h+arg_8]
0x180014ef4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014ef9  lea     rdx, [rsp+58h+arg_8]
0x180014efe  mov     rcx, rdi
0x180014f01  mov     rax, rbx
0x180014f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f09  mov     ebx, eax
0x180014f0b  test    eax, eax
0x180014f0d  jns     short loc_180014F41
0x180014f0f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180014f16  jb      loc_180014FB8
0x180014f1c  mov     edx, 11Ch
0x180014f21  mov     dword ptr [rsp+58h+ppv], eax
0x180014f25  mov     r9, rsi
0x180014f28  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180014f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f36  mov     rcx, [rcx+10h]
0x180014f3a  call    WPP_SF_qD
0x180014f3f  jmp     short loc_180014FB8
0x180014f41  mov     rdx, rbp
0x180014f44  mov     rcx, [rsp+58h+arg_8]
0x180014f49  call    ??$BlockOnCompletionAndGetResults@PEAVFaceTracker@FaceAnalysis@Media@Windows@@UIFaceTracker@234@@@YAJPEAU?$IAsyncOperation@PEAVFaceTracker@FaceAnalysis@Media@Windows@@@Foundation@Windows@@V?$ComPtrRef@V?$ComPtr@UIFaceTracker@FaceAnalysis@Media@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@W4tagCOWAIT_FLAGS@@PEAX@Z; BlockOnCompletionAndGetResults<Windows::Media::FaceAnalysis::FaceTracker *,Windows::Media::FaceAnalysis::IFaceTracker>(Windows::Foundation::IAsyncOperation<Windows::Media::FaceAnalysis::FaceTracker *> *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Media::FaceAnalysis::IFaceTracker>>,tagCOWAIT_FLAGS,void *)
0x180014f4e  mov     ebx, eax
0x180014f50  test    eax, eax
0x180014f52  jns     short loc_180014F64
0x180014f54  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180014f5b  jb      short loc_180014FB8
0x180014f5d  mov     edx, 11Dh
0x180014f62  jmp     short loc_180014F21
0x180014f64  lea     rbx, [rsi+290h]
0x180014f6b  mov     rcx, rbx
0x180014f6e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014f73  mov     [rsp+58h+ppv], rbx; ppv
0x180014f78  lea     r9, _GUID_69e3693e_8e1e_4e63_ac4c_7fdc21d9731d; riid
0x180014f7f  xor     edx, edx; pUnkOuter
0x180014f81  lea     r8d, [rdx+1]; dwClsContext
0x180014f85  lea     rcx, CLSID_VideoFrameNativeFactory; rclsid
0x180014f8c  call    cs:__imp_CoCreateInstance
0x180014f92  mov     ebx, eax
0x180014f94  test    eax, eax
0x180014f96  jns     short loc_180014FAB
0x180014f98  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180014f9f  jb      short loc_180014FB8
0x180014fa1  mov     edx, 11Eh
0x180014fa6  jmp     loc_180014F21
0x180014fab  lea     rcx, [rsi+4408h]
0x180014fb2  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180014fb7  nop
0x180014fb8  lea     rcx, [rsp+58h+arg_8]
0x180014fbd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014fc2  mov     eax, ebx
0x180014fc4  jmp     short loc_180014FF3
0x180014fc6  cmp     cs:byte_180160805, 20h ; ' '
0x180014fcd  jb      short loc_180014FF1
0x180014fcf  mov     edx, 11Bh
0x180014fd4  mov     r9, rsi
0x180014fd7  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180014fde  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fe5  mov     rcx, [rcx+0D8h]
0x180014fec  call    WPP_SF_q
0x180014ff1  xor     eax, eax
0x180014ff3  add     rsp, 38h
0x180014ff7  pop     rdi
0x180014ff8  pop     rsi
0x180014ff9  pop     rbp
0x180014ffa  pop     rbx
0x180014ffb  retn
```
