# FaceDetectionMFT::HandleHardwareMetadataEvent(IMFSample *)

- ea: `0x180013ff4`
- end: `0x1800146de`
- name: `?HandleHardwareMetadataEvent@FaceDetectionMFT@@AEAAJPEAUIMFSample@@@Z`
- size: `1770`
- prototype: `__int64 __fastcall(FaceDetectionMFT *__hidden this, struct IMFSample *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180014c4c`

## callees

- `0x180005660`
- `0x18000b480`
- `0x18000b490`
- `0x18000c0f8`
- `0x18000c4fc`
- `0x18000cee0`
- `0x18000d434`
- `0x180013ff4`
- `0x180015ff8`
- `0x18001c310`
- `0x18001cbd8`
- `0x18001dc58`
- `0x1800293f4`
- `0x180134abc`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001467b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014689`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001467b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180014689`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001411d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014412`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001411d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180014412`
- `MFPlat!MFCreateAsyncResult` at `0x180014621`
- `MFPlat!MFCreateAsyncResult` at `0x180014621`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FaceDetectionMFT::HandleHardwareMetadataEvent(FaceDetectionMFT *this, struct IMFSample *a2)
{
  __int64 *v4; // r15
  char *v5; // r14
  __int64 v6; // rcx
  HRESULT v7; // ebx
  __int64 v8; // rdx
  HRESULT (__stdcall *GetUnknown)(IMFSample *, const GUID *const, const IID *const, LPVOID *); // rbx
  _DWORD *v10; // r13
  int v11; // ecx
  __int64 v12; // rdx
  __int64 i; // r12
  int v14; // ebx
  __m128 v15; // xmm6
  __int64 v16; // rcx
  char v17; // al
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 *, unsigned __int64 *); // rbx
  __int64 v20; // rdx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, _QWORD *); // rbx
  int v23; // ecx
  struct IMFSample *v24; // rbx
  _QWORD *v25; // rdi
  __int64 v26; // rbx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v30; // [rsp+38h] [rbp-99h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+40h] [rbp-91h] BYREF
  _QWORD v32[2]; // [rsp+48h] [rbp-89h] BYREF
  __int64 v33; // [rsp+58h] [rbp-79h] BYREF
  int v34; // [rsp+60h] [rbp-71h]
  int v35; // [rsp+64h] [rbp-6Dh]
  __int64 v36; // [rsp+68h] [rbp-69h] BYREF
  IUnknown *punkObject; // [rsp+70h] [rbp-61h] BYREF
  __int64 v38; // [rsp+78h] [rbp-59h] BYREF
  __int64 v39[2]; // [rsp+80h] [rbp-51h] BYREF
  __int64 v40; // [rsp+90h] [rbp-41h] BYREF
  struct tagRECT v41; // [rsp+98h] [rbp-39h] BYREF
  unsigned __int64 v42; // [rsp+A8h] [rbp-29h] BYREF
  float v43; // [rsp+B0h] [rbp-21h]
  _BYTE v44[56]; // [rsp+B8h] [rbp-19h] BYREF
  unsigned __int64 v45; // [rsp+138h] [rbp+67h] BYREF
  struct IMFSample *v46; // [rsp+140h] [rbp+6Fh]
  unsigned __int64 v47; // [rsp+148h] [rbp+77h]
  SIZE_T cb; // [rsp+150h] [rbp+7Fh] BYREF

  v46 = a2;
  v4 = 0;
  v32[0] = 0;
  punkObject = 0;
  ppAsyncResult = 0;
  v30 = 0;
  LODWORD(cb) = 0;
  v5 = (char *)this + 760;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 760);
  v7 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Media::FaceAnalysis::DetectedFace,Windows::Foundation::Collections::Internal::AgileVector<Windows::Media::FaceAnalysis::DetectedFace *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::FaceAnalysis::DetectedFace *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::FaceAnalysis::DetectedFace *>,0>>(
         v6,
         v5);
  if ( v7 >= 0 )
  {
    utl::_HashTable<Windows::Media::FaceAnalysis::IDetectedFace *,utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>,utl::hash<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::equal_to<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::allocator<utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>>,0>::clear(v5 + 8);
    GetUnknown = a2->lpVtbl->GetUnknown;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
    v7 = ((__int64 (__fastcall *)(struct IMFSample *, const GUID *, GUID *, __int64 *))GetUnknown)(
           a2,
           &MFSampleExtension_CaptureMetadata,
           &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3,
           &v30);
    if ( v7 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_75;
      v8 = 164;
      goto LABEL_4;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, const GUID *, SIZE_T *))(*(_QWORD *)v30 + 112LL))(
           v30,
           &MF_CAPTURE_METADATA_FACEROIS,
           &cb);
    if ( v7 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_75;
      v8 = 165;
      goto LABEL_4;
    }
    v10 = CoTaskMemAlloc((unsigned int)cb);
    if ( !v10 )
    {
      v7 = -2147024882;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 166, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v11);
      goto LABEL_75;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, const GUID *, _DWORD *, _QWORD, _QWORD))(*(_QWORD *)v30 + 120LL))(
           v30,
           &MF_CAPTURE_METADATA_FACEROIS,
           v10,
           (unsigned int)cb,
           0);
    if ( v7 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_73;
      v12 = 167;
      goto LABEL_72;
    }
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        168,
        &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
        this,
        v10[1]);
    for ( i = 0; (unsigned int)i < v10[1]; i = (unsigned int)(i + 1) )
    {
      v45 = 0;
      *(_OWORD *)v39 = 0;
      v41 = *(struct tagRECT *)&v10[5 * i + 2];
      v14 = ConvertQ31RectToBounds(
              &v41,
              *((_DWORD *)this + 20),
              *((_DWORD *)this + 21),
              (struct Windows::Foundation::Rect *)v39);
      v15 = *(__m128 *)v39;
      v41 = *(struct tagRECT *)v39;
      v17 = FaceDetectionMFT::ValidateRect(v16, &v41, *((unsigned int *)this + 20), *((unsigned int *)this + 21));
      if ( v14 || !v17 )
      {
        if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            171,
            &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
            this,
            i);
      }
      else
      {
        v18 = *((_QWORD *)this + 81);
        v19 = *(__int64 (__fastcall **)(__int64, __int64 *, unsigned __int64 *))(*(_QWORD *)v18 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
        LODWORD(v33) = (int)(v15.m128_f32[0] + 0.5);
        HIDWORD(v33) = (int)(_mm_shuffle_ps(v15, v15, 85).m128_f32[0] + 0.5);
        v34 = (int)(_mm_shuffle_ps(v15, v15, 170).m128_f32[0] + 0.5);
        v35 = (int)(_mm_shuffle_ps(v15, v15, 255).m128_f32[0] + 0.5);
        v7 = v19(v18, &v33, &v45);
        if ( v7 < 0 )
        {
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v20 = 169;
LABEL_33:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v20,
              &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
              this,
              v7);
          }
LABEL_34:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
          goto LABEL_73;
        }
        v7 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64))(**((_QWORD **)this + 95) + 104LL))(
               *((_QWORD *)this + 95),
               v45);
        if ( v7 < 0 )
        {
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v20 = 170;
            goto LABEL_33;
          }
          goto LABEL_34;
        }
        v42 = v45;
        v43 = (float)(int)v10[5 * i + 6] / 100.0;
        utl::_HashTable<Windows::Media::FaceAnalysis::IDetectedFace *,utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>,utl::hash<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::equal_to<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::allocator<utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>>,0>::_InsertImpl<utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float> const &>(
          (char *)this + 768,
          v44,
          &v42);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
    }
    v21 = *((_QWORD *)this + 95);
    v22 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v21 + 64LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v32);
    v7 = v22(v21, v32);
    if ( v7 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_73;
      v12 = 172;
      goto LABEL_72;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 760);
    v36 = 0;
    v40 = 0;
    v38 = 0;
    v4 = (__int64 *)CoTaskMemAlloc(0x18u);
    if ( !v4 )
    {
      v7 = -2147024882;
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v23);
      goto LABEL_73;
    }
    LOBYTE(v45) = 0;
    LOBYTE(v47) = 0;
    if ( (*(int (__fastcall **)(__int64, const GUID *, __int64 *, __int64, _QWORD))(*(_QWORD *)v30 + 120LL))(
           v30,
           &MF_CAPTURE_METADATA_FACEROITIMESTAMPS,
           v4,
           24,
           0) < 0 )
      goto LABEL_63;
    v24 = v46;
    if ( (*(_BYTE *)v4 & 1) != 0 )
    {
      LOBYTE(v45) = 1;
      v40 = v4[1];
      if ( *((_DWORD *)this + 212) <= 1u
        && ((int (__fastcall *)(struct IMFSample *, const IID *, __int64 *))v46->lpVtbl->GetUINT64)(
             v46,
             &MFSampleExtension_DeviceTimestamp,
             &v38) >= 0 )
      {
        *((_QWORD *)this + 107) = v38;
      }
    }
    if ( (*(_BYTE *)v4 & 2) == 0 || (LOBYTE(v47) = 1, v36 = v4[2], *((__int64 *)this + 69) <= 1000000) )
    {
LABEL_63:
      v33 = v32[0];
      v45 = (unsigned __int64)&v40 & -(__int64)((_BYTE)v45 != 0);
      v47 = (unsigned __int64)&v36 & -(__int64)((_BYTE)v47 != 0);
      v7 = Microsoft::WRL::Details::MakeAndInitialize<FaceDetectedEventArgsImpl,Windows::Media::Core::IFaceDetectedEventArgs,Windows::Foundation::TimeSpan *,Windows::Foundation::TimeSpan *,Windows::Foundation::Collections::IVectorView<Windows::Media::FaceAnalysis::DetectedFace *> *>((void **)&punkObject);
      if ( v7 >= 0 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppAsyncResult);
        v7 = MFCreateAsyncResult(punkObject, (IMFAsyncCallback *)this + 47, 0, &ppAsyncResult);
        if ( v7 >= 0 )
        {
          v7 = CCoreMFT::PutWorkItem(this, ppAsyncResult);
          if ( v7 >= 0 || !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
LABEL_73:
            CoTaskMemFree(v10);
            if ( v4 )
              CoTaskMemFree(v4);
            goto LABEL_75;
          }
          v12 = 178;
        }
        else
        {
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_73;
          v12 = 177;
        }
      }
      else
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_73;
        v12 = 176;
      }
LABEL_72:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v7);
      goto LABEL_73;
    }
    v39[0] = 0;
    v7 = ((__int64 (__fastcall *)(struct IMFSample *, __int64 *))v24->lpVtbl->GetSampleTime)(v24, v39);
    if ( v7 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_73;
      v12 = 174;
      goto LABEL_72;
    }
    v33 = 0;
    if ( v36 >= v39[0] )
    {
      v25 = (_QWORD *)((char *)this + 552);
    }
    else
    {
      if ( (int)LongLongSub(v39[0], v36, &v33) >= 0 )
      {
        v25 = (_QWORD *)((char *)this + 552);
        v26 = v33;
        goto LABEL_57;
      }
      v25 = (_QWORD *)((char *)this + 552);
    }
    v26 = 0;
LABEL_57:
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() < 0x20u )
      v25 = (_QWORD *)((char *)this + 552);
    else
      WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 27), v27, v28, v26);
    if ( v26 > *v25 / 2LL && v26 < *v25 + 2LL * *((_QWORD *)this + 94) )
      *((_QWORD *)this + 93) = v26;
    goto LABEL_63;
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v8 = 163;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v7);
  }
LABEL_75:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppAsyncResult);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&punkObject);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v32);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180013ff4  mov     rax, rsp
0x180013ff7  mov     [rax+10h], rdx
0x180013ffb  push    rbp
0x180013ffc  push    rbx
0x180013ffd  push    rsi
0x180013ffe  push    rdi
0x180013fff  push    r12
0x180014001  push    r13
0x180014003  push    r14
0x180014005  push    r15
0x180014007  lea     rbp, [rax-5Fh]
0x18001400b  sub     rsp, 0E8h
0x180014012  movaps  xmmword ptr [rax-58h], xmm6
0x180014016  movaps  xmmword ptr [rax-68h], xmm7
0x18001401a  mov     rdi, rdx
0x18001401d  mov     rsi, rcx
0x180014020  xor     r15d, r15d
0x180014023  mov     [rsp+120h+var_E0], r15
0x180014028  mov     [rbp+57h+punkObject], r15
0x18001402c  mov     [rsp+120h+ppAsyncResult], r15
0x180014031  mov     [rsp+120h+var_F0], r15
0x180014036  mov     dword ptr [rbp+57h+cb], r15d
0x18001403a  lea     r14, [rcx+2F8h]
0x180014041  mov     rcx, r14
0x180014044  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014049  mov     rdx, r14
0x18001404c  call    ??$CreateExternalObjectVector@VDetectedFace@FaceAnalysis@Media@Windows@@V?$AgileVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@U?$DefaultEqualityPredicate@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@6784@$0A@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@U?$DefaultEqualityPredicate@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@6784@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Media::FaceAnalysis::DetectedFace,Windows::Foundation::Collections::Internal::AgileVector<Windows::Media::FaceAnalysis::DetectedFace *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::FaceAnalysis::DetectedFace *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::FaceAnalysis::DetectedFace *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Media::FaceAnalysis::DetectedFace *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::FaceAnalysis::DetectedFace *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::FaceAnalysis::DetectedFace *>,0> * *)
0x180014051  mov     ebx, eax
0x180014053  test    eax, eax
0x180014055  jns     short loc_18001408C
0x180014057  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001405c  cmp     al, 1
0x18001405e  jb      loc_180014690
0x180014064  mov     edx, 0A3h
0x180014069  mov     dword ptr [rsp+120h+var_100], ebx
0x18001406d  mov     r9, rsi
0x180014070  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180014077  mov     rcx, cs:WPP_GLOBAL_Control
0x18001407e  mov     rcx, [rcx+10h]
0x180014082  call    WPP_SF_qD
0x180014087  jmp     loc_180014690
0x18001408c  lea     rcx, [r14+8]
0x180014090  call    ?clear@?$_HashTable@PEAUIDetectedFace@FaceAnalysis@Media@Windows@@U?$pair@QEAUIDetectedFace@FaceAnalysis@Media@Windows@@M@utl@@U?$hash@PEAUIDetectedFace@FaceAnalysis@Media@Windows@@@6@U?$equal_to@PEAUIDetectedFace@FaceAnalysis@Media@Windows@@@6@V?$allocator@U?$pair@QEAUIDetectedFace@FaceAnalysis@Media@Windows@@M@utl@@@6@$0A@@utl@@QEAAXXZ; utl::_HashTable<Windows::Media::FaceAnalysis::IDetectedFace *,utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>,utl::hash<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::equal_to<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::allocator<utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>>,0>::clear(void)
0x180014095  mov     rax, [rdi]
0x180014098  mov     rbx, [rax+88h]
0x18001409f  lea     rcx, [rsp+120h+var_F0]
0x1800140a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800140a9  lea     r9, [rsp+120h+var_F0]
0x1800140ae  lea     r8, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x1800140b5  lea     rdx, MFSampleExtension_CaptureMetadata
0x1800140bc  mov     rcx, rdi
0x1800140bf  mov     rax, rbx
0x1800140c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140c7  mov     ebx, eax
0x1800140c9  test    eax, eax
0x1800140cb  jns     short loc_1800140E1
0x1800140cd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800140d2  cmp     al, 1
0x1800140d4  jb      loc_180014690
0x1800140da  mov     edx, 0A4h
0x1800140df  jmp     short loc_180014069
0x1800140e1  mov     rcx, [rsp+120h+var_F0]
0x1800140e6  mov     rax, [rcx]
0x1800140e9  lea     r8, [rbp+57h+cb]
0x1800140ed  lea     rdx, MF_CAPTURE_METADATA_FACEROIS
0x1800140f4  mov     rax, [rax+70h]
0x1800140f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140fd  mov     ebx, eax
0x1800140ff  test    eax, eax
0x180014101  jns     short loc_18001411A
0x180014103  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180014108  cmp     al, 1
0x18001410a  jb      loc_180014690
0x180014110  mov     edx, 0A5h
0x180014115  jmp     loc_180014069
0x18001411a  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18001411d  call    cs:__imp_CoTaskMemAlloc
0x180014123  mov     r13, rax
0x180014126  test    rax, rax
0x180014129  jnz     short loc_18001414D
0x18001412b  mov     ecx, 8007000Eh
0x180014130  mov     ebx, ecx
0x180014132  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180014137  cmp     al, 1
0x180014139  jb      loc_180014690
0x18001413f  mov     edx, 0A6h
0x180014144  mov     dword ptr [rsp+120h+var_100], ecx
0x180014148  jmp     loc_18001406D
0x18001414d  mov     rcx, [rsp+120h+var_F0]
0x180014152  mov     rax, [rcx]
0x180014155  mov     [rsp+120h+var_100], 0
0x18001415e  mov     r9d, dword ptr [rbp+57h+cb]
0x180014162  mov     r8, r13
0x180014165  lea     rdx, MF_CAPTURE_METADATA_FACEROIS
0x18001416c  mov     rax, [rax+78h]
0x180014170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014175  mov     ebx, eax
0x180014177  test    eax, eax
0x180014179  jns     short loc_180014199
0x18001417b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180014180  cmp     al, 1
0x180014182  jb      loc_180014678
0x180014188  mov     edx, 0A7h
0x18001418d  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180014194  jmp     loc_180014661
0x180014199  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001419e  lea     r14, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x1800141a5  cmp     al, 20h ; ' '
0x1800141a7  jb      short loc_1800141CF
0x1800141a9  mov     edx, 0A8h
0x1800141ae  mov     eax, [r13+4]
0x1800141b2  mov     dword ptr [rsp+120h+var_100], eax
0x1800141b6  mov     r9, rsi
0x1800141b9  mov     r8, r14
0x1800141bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141c3  mov     rcx, [rcx+0D8h]
0x1800141ca  call    WPP_SF_qD
0x1800141cf  xor     r12d, r12d
0x1800141d2  movsd   xmm7, cs:__real@3fe0000000000000
0x1800141da  cmp     r12d, [r13+4]
0x1800141de  jnb     loc_1800143AE
0x1800141e4  mov     [rbp+57h+arg_0], 0
0x1800141ec  xorps   xmm0, xmm0
0x1800141ef  movups  xmmword ptr [rbp+57h+var_A8], xmm0
0x1800141f3  lea     rax, [r12+r12*4]
0x1800141f7  movups  xmm0, xmmword ptr [r13+rax*4+8]
0x1800141fd  movdqu  xmmword ptr [rbp+57h+var_90.left], xmm0
0x180014202  lea     r9, [rbp+57h+var_A8]; struct Windows::Foundation::Rect *
0x180014206  mov     r8d, [rsi+54h]; unsigned int
0x18001420a  mov     edx, [rsi+50h]; unsigned int
0x18001420d  lea     rcx, [rbp+57h+var_90]; struct tagRECT
0x180014211  call    ?ConvertQ31RectToBounds@@YAJUtagRECT@@IIPEAURect@Foundation@Windows@@@Z; ConvertQ31RectToBounds(tagRECT,uint,uint,Windows::Foundation::Rect *)
0x180014216  mov     ebx, eax
0x180014218  movups  xmm6, xmmword ptr [rbp+57h+var_A8]
0x18001421c  movups  xmmword ptr [rbp+57h+var_90.left], xmm6
0x180014220  mov     r9d, [rsi+54h]
0x180014224  mov     r8d, [rsi+50h]
0x180014228  lea     rdx, [rbp+57h+var_90]
0x18001422c  call    ?ValidateRect@FaceDetectionMFT@@AEAA_NURect@Foundation@Windows@@II@Z; FaceDetectionMFT::ValidateRect(Windows::Foundation::Rect,uint,uint)
0x180014231  test    ebx, ebx
0x180014233  jnz     loc_180014329
0x180014239  test    al, al
0x18001423b  jz      loc_180014329
0x180014241  mov     rdi, [rsi+288h]
0x180014248  mov     rax, [rdi]
0x18001424b  mov     rbx, [rax+30h]
0x18001424f  lea     rcx, [rbp+57h+arg_0]
0x180014253  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180014258  xorps   xmm0, xmm0
0x18001425b  cvtss2sd xmm0, xmm6
0x18001425f  addsd   xmm0, xmm7
0x180014263  cvttsd2si rax, xmm0
0x180014268  mov     dword ptr [rbp+57h+var_D0], eax
0x18001426b  movaps  xmm1, xmm6
0x18001426e  shufps  xmm1, xmm6, 55h ; 'U'
0x180014272  xorps   xmm0, xmm0
0x180014275  cvtss2sd xmm0, xmm1
0x180014279  addsd   xmm0, xmm7
0x18001427d  cvttsd2si rax, xmm0
0x180014282  mov     dword ptr [rbp+57h+var_D0+4], eax
0x180014285  movaps  xmm1, xmm6
0x180014288  shufps  xmm1, xmm6, 0AAh
0x18001428c  xorps   xmm0, xmm0
0x18001428f  cvtss2sd xmm0, xmm1
0x180014293  addsd   xmm0, xmm7
0x180014297  cvttsd2si rdx, xmm0
0x18001429c  mov     [rbp+57h+var_C8], edx
0x18001429f  shufps  xmm6, xmm6, 0FFh
0x1800142a3  xorps   xmm0, xmm0
0x1800142a6  cvtss2sd xmm0, xmm6
0x1800142aa  addsd   xmm0, xmm7
0x1800142ae  cvttsd2si rdx, xmm0
0x1800142b3  mov     [rbp+57h+var_C4], edx
0x1800142b6  lea     r8, [rbp+57h+arg_0]
0x1800142ba  lea     rdx, [rbp+57h+var_D0]
0x1800142be  mov     rcx, rdi
0x1800142c1  mov     rax, rbx
0x1800142c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142c9  mov     ebx, eax
0x1800142cb  test    eax, eax
0x1800142cd  js      loc_180014377
0x1800142d3  mov     rcx, [rsi+2F8h]
0x1800142da  mov     rax, [rcx]
0x1800142dd  mov     rdx, [rbp+57h+arg_0]
0x1800142e1  mov     rax, [rax+68h]
0x1800142e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142ea  mov     ebx, eax
0x1800142ec  test    eax, eax
0x1800142ee  js      short loc_180014367
0x1800142f0  mov     rax, [rbp+57h+arg_0]
0x1800142f4  mov     [rbp+57h+var_80], rax
0x1800142f8  lea     rax, [r12+r12*4]
0x1800142fc  movd    xmm0, dword ptr [r13+rax*4+18h]
0x180014303  cvtdq2ps xmm0, xmm0
0x180014306  divss   xmm0, cs:__real@42c80000
0x18001430e  movss   [rbp+57h+var_78], xmm0
0x180014313  lea     rcx, [rsi+300h]
0x18001431a  lea     r8, [rbp+57h+var_80]
0x18001431e  lea     rdx, [rbp+57h+var_70]
0x180014322  call    ??$_InsertImpl@AEBU?$pair@QEAUIDetectedFace@FaceAnalysis@Media@Windows@@M@utl@@@?$_HashTable@PEAUIDetectedFace@FaceAnalysis@Media@Windows@@U?$pair@QEAUIDetectedFace@FaceAnalysis@Media@Windows@@M@utl@@U?$hash@PEAUIDetectedFace@FaceAnalysis@Media@Windows@@@6@U?$equal_to@PEAUIDetectedFace@FaceAnalysis@Media@Windows@@@6@V?$allocator@U?$pair@QEAUIDetectedFace@FaceAnalysis@Media@Windows@@M@utl@@@6@$0A@@utl@@AEAA?AU?$pair@V?$_DlistIt@U?$_HashNode@U?$pair@QEAUIDetectedFace@FaceAnalysis@Media@Windows@@M@utl@@@utl@@U?$pair@QEAUIDetectedFace@FaceAnalysis@Media@Windows@@M@2@@utl@@_N@1@AEBU?$pair@QEAUIDetectedFace@FaceAnalysis@Media@Windows@@M@1@@Z; utl::_HashTable<Windows::Media::FaceAnalysis::IDetectedFace *,utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>,utl::hash<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::equal_to<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::allocator<utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>>,0>::_InsertImpl<utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float> const &>(utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float> const &)
0x180014327  jmp     short loc_180014356
0x180014329  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001432e  cmp     al, 20h ; ' '
0x180014330  jb      short loc_180014356
0x180014332  mov     edx, 0ABh
0x180014337  mov     dword ptr [rsp+120h+var_100], r12d
0x18001433c  mov     r9, rsi
0x18001433f  mov     r8, r14
0x180014342  mov     rcx, cs:WPP_GLOBAL_Control
0x180014349  mov     rcx, [rcx+0D8h]
0x180014350  call    WPP_SF_qD
0x180014355  nop
0x180014356  lea     rcx, [rbp+57h+arg_0]
0x18001435a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001435f  inc     r12d
0x180014362  jmp     loc_1800141DA
0x180014367  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001436c  cmp     al, 1
0x18001436e  jb      short loc_1800143A0
0x180014370  mov     edx, 0AAh
0x180014375  jmp     short loc_180014385
0x180014377  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001437c  cmp     al, 1
0x18001437e  jb      short loc_1800143A0
0x180014380  mov     edx, 0A9h
0x180014385  mov     dword ptr [rsp+120h+var_100], ebx
0x180014389  mov     r9, rsi
0x18001438c  mov     r8, r14
0x18001438f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014396  mov     rcx, [rcx+10h]
0x18001439a  call    WPP_SF_qD
0x18001439f  nop
0x1800143a0  lea     rcx, [rbp+57h+arg_0]
0x1800143a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800143a9  jmp     loc_180014678
0x1800143ae  mov     rdi, [rsi+2F8h]
0x1800143b5  mov     rax, [rdi]
0x1800143b8  mov     rbx, [rax+40h]
0x1800143bc  lea     rcx, [rsp+120h+var_E0]
0x1800143c1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800143c6  lea     rdx, [rsp+120h+var_E0]
0x1800143cb  mov     rcx, rdi
0x1800143ce  mov     rax, rbx
0x1800143d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143d6  mov     ebx, eax
0x1800143d8  test    eax, eax
0x1800143da  jns     short loc_1800143F3
0x1800143dc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800143e1  cmp     al, 1
0x1800143e3  jb      loc_180014678
0x1800143e9  mov     edx, 0ACh
0x1800143ee  jmp     loc_18001465E
0x1800143f3  lea     rcx, [rsi+2F8h]
0x1800143fa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800143ff  xor     ebx, ebx
0x180014401  mov     [rbp+57h+var_C0], rbx
0x180014405  mov     [rbp+57h+var_98], rbx
0x180014409  mov     [rbp+57h+var_B0], rbx
0x18001440d  lea     edi, [rbx+18h]
0x180014410  mov     ecx, edi; cb
0x180014412  call    cs:__imp_CoTaskMemAlloc
0x180014418  mov     r15, rax
0x18001441b  test    rax, rax
0x18001441e  jnz     short loc_180014445
0x180014420  mov     ecx, 8007000Eh
0x180014425  mov     ebx, ecx
0x180014427  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001442c  cmp     al, 1
0x18001442e  jb      loc_180014678
0x180014434  mov     edx, 0ADh
0x180014439  mov     dword ptr [rsp+120h+var_100], ecx
0x18001443d  mov     r8, r14
0x180014440  jmp     loc_180014665
0x180014445  mov     byte ptr [rbp+57h+arg_0], bl
0x180014448  mov     byte ptr [rbp+57h+arg_10], bl
0x18001444b  mov     rcx, [rsp+120h+var_F0]
0x180014450  mov     rax, [rcx]
0x180014453  mov     [rsp+120h+var_100], rbx
0x180014458  mov     r9d, edi
0x18001445b  mov     r8, r15
0x18001445e  lea     rdx, MF_CAPTURE_METADATA_FACEROITIMESTAMPS
0x180014465  mov     rax, [rax+78h]
0x180014469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001446e  test    eax, eax
0x180014470  js      loc_1800145AE
0x180014476  mov     rbx, [rbp+57h+arg_8]
0x18001447a  test    byte ptr [r15], 1
0x18001447e  jz      short loc_1800144BE
0x180014480  mov     byte ptr [rbp+57h+arg_0], 1
0x180014484  mov     rax, [r15+8]
0x180014488  mov     [rbp+57h+var_98], rax
0x18001448c  cmp     dword ptr [rsi+350h], 1
0x180014493  ja      short loc_1800144BE
0x180014495  mov     rax, [rbx]
0x180014498  lea     r8, [rbp+57h+var_B0]
0x18001449c  lea     rdx, MFSampleExtension_DeviceTimestamp
0x1800144a3  mov     rcx, rbx
0x1800144a6  mov     rax, [rax+40h]
0x1800144aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144af  test    eax, eax
  ... truncated ...
```
