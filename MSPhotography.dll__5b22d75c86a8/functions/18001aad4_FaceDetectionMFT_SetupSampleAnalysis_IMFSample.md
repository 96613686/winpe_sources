# FaceDetectionMFT::SetupSampleAnalysis(IMFSample *)

- ea: `0x18001aad4`
- end: `0x18001aeee`
- name: `?SetupSampleAnalysis@FaceDetectionMFT@@AEAAJPEAUIMFSample@@@Z`
- size: `1050`
- prototype: `__int64 __fastcall(FaceDetectionMFT *__hidden this, struct IMFSample *)`
- caller_count: `2`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001aef4`
- `0x18001b024`

## callees

- `0x1800016b0`
- `0x180001784`
- `0x180005660`
- `0x18000c0f8`
- `0x18000c4fc`
- `0x18000f14c`
- `0x18000fcdc`
- `0x180012290`
- `0x180013b30`
- `0x180015004`
- `0x180015fb8`
- `0x180017f8c`
- `0x1800180ec`
- `0x18001aad4`
- `0x18001c95c`
- `0x18001c99c`
- `0x18001cbd8`
- `0x18001d7d8`
- `0x180134abc`
- `0x1801357e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aafa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ac2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001aafa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ac2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ab0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ac70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ac7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ab0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ac70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ac7e`
- `MFPlat!MFCreateAsyncResult` at `0x18001ad13`
- `MFPlat!MFCreateAsyncResult` at `0x18001ad13`

## pseudocode

```c
__int64 __fastcall FaceDetectionMFT::SetupSampleAnalysis(FaceDetectionMFT *this, struct IMFSample *a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  int SampleRotation; // eax
  int v6; // ebx
  __int64 v7; // rcx
  HRESULT NecessaryAttributes; // eax
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // r10
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // r10
  __int64 v15; // rcx
  CAggregatePhotographyTelemetry *v16; // rcx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  __int64 *v20; // rax
  int *v21; // rdx
  CAggregatePhotographyTelemetry *v22; // rcx
  __int64 *v24; // [rsp+38h] [rbp-38h]
  __int64 v25; // [rsp+50h] [rbp-20h] BYREF
  const char *v26; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v27[2]; // [rsp+60h] [rbp-10h] BYREF
  __int64 v28; // [rsp+A0h] [rbp+30h] BYREF
  int v29; // [rsp+B0h] [rbp+40h] BYREF
  IMFAsyncResult *ppAsyncResult; // [rsp+B8h] [rbp+48h] BYREF

  ppAsyncResult = 0;
  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 424);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 424));
  *((_BYTE *)this + 624) = 1;
  LeaveCriticalSection(v4);
  *((_DWORD *)this + 252) = *((_DWORD *)this + 253);
  SampleRotation = FaceDetectionMFT::GetSampleRotation(this);
  *((_DWORD *)this + 253) = SampleRotation;
  if ( SampleRotation != *((_DWORD *)this + 252) )
    *((_BYTE *)this + 712) = 1;
  if ( !*((_BYTE *)this + 852) || *((_DWORD *)this + 212) != 2 || (v6 = 0, !SampleRotation) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 760);
    NecessaryAttributes = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Media::FaceAnalysis::DetectedFace,Windows::Foundation::Collections::Internal::AgileVector<Windows::Media::FaceAnalysis::DetectedFace *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::FaceAnalysis::DetectedFace *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::FaceAnalysis::DetectedFace *>,0>>(
                            v7,
                            (char *)this + 760);
    v6 = NecessaryAttributes;
    if ( NecessaryAttributes < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_39;
      v9 = 62;
LABEL_38:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids,
        this,
        NecessaryAttributes);
      goto LABEL_39;
    }
    utl::_HashTable<Windows::Media::FaceAnalysis::IDetectedFace *,utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>,utl::hash<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::equal_to<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::allocator<utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>>,0>::clear((char *)this + 768);
    NecessaryAttributes = FaceDetectionMFT::ExtractNecessaryAttributes(this, a2);
    v6 = NecessaryAttributes;
    if ( NecessaryAttributes < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_39;
      v9 = 63;
      goto LABEL_38;
    }
  }
  Microsoft::WRL::ComPtr<IMFSample>::operator=((char *)this + 632, a2);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MediaQI2505>::GetImpl'::`2'::impl)
    && !*((_QWORD *)this + 87)
    && !*((_QWORD *)this + 83) )
  {
    if ( (unsigned __int8)byte_180160805 >= 0x20u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 64, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids);
    v28 = (__int64)this + 504;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 504));
    v10 = FaceDetectionMFT::InitializeSoftwareFaceDector(this);
    v6 = v10;
    if ( v10 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v10);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 504));
LABEL_39:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CameraQI2511>::GetImpl'::`2'::impl) )
      {
        if ( v6 == -2140143607 )
        {
          v6 = 0;
LABEL_51:
          FaceDetectionMFT::ResetAnalysisState(this);
          goto LABEL_52;
        }
        v16 = (CAggregatePhotographyTelemetry *)*((_QWORD *)this + 2181);
        if ( !v16 )
          goto LABEL_51;
        CAggregatePhotographyTelemetry::AddData(v16, 4u, 0.0);
        if ( (unsigned int)dword_18015F0D0 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_18015F0D0, 0x400000000000LL) )
          goto LABEL_51;
        v25 = (__int64)this + 17464;
        v26 = "FaceDetection";
        v27[0] = 0x1000000;
        v24 = &v25;
        v20 = v27;
        v21 = (int *)&byte_180151117;
      }
      else
      {
        v22 = (CAggregatePhotographyTelemetry *)*((_QWORD *)this + 2181);
        if ( !v22 )
          goto LABEL_51;
        CAggregatePhotographyTelemetry::AddData(v22, 4u, 0.0);
        if ( (unsigned int)dword_18015F0D0 <= 5 || !(unsigned __int8)tlgKeywordOn(&dword_18015F0D0, 0x400000000000LL) )
          goto LABEL_51;
        v27[0] = (char *)this + 17464;
        v26 = "FaceDetection";
        v25 = 0x1000000;
        v24 = v27;
        v20 = &v25;
        v21 = &dword_18015108C;
      }
      LODWORD(v28) = v6;
      v29 = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        v17,
        (_DWORD)v21,
        v18,
        v19,
        (__int64)v20,
        (__int64)&v26,
        (__int64)&v29,
        (__int64)v24,
        (__int64)&v28);
      goto LABEL_51;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 504));
  }
  if ( *((_BYTE *)this + 852) )
  {
    FaceDetectionMFT::RunAnalysis(this, 0);
    if ( v6 < 0 )
      goto LABEL_39;
  }
  else
  {
    v11 = *((_QWORD *)this + 119);
    v28 = v11;
    v12 = *((_QWORD *)this + 69);
    if ( v12 > *((_QWORD *)this + 12) )
    {
      v13 = LongLongAdd(v11, v12 - *((_QWORD *)this + 12), &v28);
      v15 = v28;
      if ( v13 < 0 )
        v15 = v14;
      v11 = v15;
    }
    NecessaryAttributes = CCoreMFT::UpdateDeadline(this, v11);
    v6 = NecessaryAttributes;
    if ( NecessaryAttributes < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_39;
      v9 = 66;
      goto LABEL_38;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppAsyncResult);
    NecessaryAttributes = MFCreateAsyncResult(0, (IMFAsyncCallback *)this + 46, 0, &ppAsyncResult);
    v6 = NecessaryAttributes;
    if ( NecessaryAttributes < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_39;
      v9 = 67;
      goto LABEL_38;
    }
    NecessaryAttributes = CCoreMFT::PutWorkItem(this, ppAsyncResult);
    v6 = NecessaryAttributes;
    if ( NecessaryAttributes < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_39;
      v9 = 68;
      goto LABEL_38;
    }
  }
LABEL_52:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppAsyncResult);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001aad4  push    rbp
0x18001aad6  push    rbx
0x18001aad7  push    rsi
0x18001aad8  push    rdi
0x18001aad9  push    r14
0x18001aadb  mov     rbp, rsp
0x18001aade  sub     rsp, 70h
0x18001aae2  mov     r14, rdx
0x18001aae5  mov     rdi, rcx
0x18001aae8  mov     [rbp+ppAsyncResult], 0
0x18001aaf0  lea     rbx, [rcx+1A8h]
0x18001aaf7  mov     rcx, rbx; lpCriticalSection
0x18001aafa  call    cs:__imp_EnterCriticalSection
0x18001ab00  mov     byte ptr [rdi+270h], 1
0x18001ab07  mov     rcx, rbx; lpCriticalSection
0x18001ab0a  call    cs:__imp_LeaveCriticalSection
0x18001ab10  mov     eax, [rdi+3F4h]
0x18001ab16  mov     [rdi+3F0h], eax
0x18001ab1c  mov     rcx, rdi
0x18001ab1f  call    ?GetSampleRotation@FaceDetectionMFT@@AEAA?AW4SampleRotation@@XZ; FaceDetectionMFT::GetSampleRotation(void)
0x18001ab24  mov     [rdi+3F4h], eax
0x18001ab2a  cmp     eax, [rdi+3F0h]
0x18001ab30  jz      short loc_18001AB39
0x18001ab32  mov     byte ptr [rdi+2C8h], 1
0x18001ab39  lea     rsi, [rdi+2F8h]
0x18001ab40  cmp     byte ptr [rsi+5Ch], 0
0x18001ab44  jz      short loc_18001AB55
0x18001ab46  cmp     dword ptr [rdi+350h], 2
0x18001ab4d  jnz     short loc_18001AB55
0x18001ab4f  xor     ebx, ebx
0x18001ab51  test    eax, eax
0x18001ab53  jnz     short loc_18001ABB7
0x18001ab55  mov     rcx, rsi
0x18001ab58  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ab5d  mov     rdx, rsi
0x18001ab60  call    ??$CreateExternalObjectVector@VDetectedFace@FaceAnalysis@Media@Windows@@V?$AgileVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@U?$DefaultEqualityPredicate@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@6784@$0A@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVDetectedFace@FaceAnalysis@Media@Windows@@U?$DefaultEqualityPredicate@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVDetectedFace@FaceAnalysis@Media@Windows@@@6784@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Media::FaceAnalysis::DetectedFace,Windows::Foundation::Collections::Internal::AgileVector<Windows::Media::FaceAnalysis::DetectedFace *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::FaceAnalysis::DetectedFace *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::FaceAnalysis::DetectedFace *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Media::FaceAnalysis::DetectedFace *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Media::FaceAnalysis::DetectedFace *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Media::FaceAnalysis::DetectedFace *>,0> * *)
0x18001ab65  mov     ebx, eax
0x18001ab67  test    eax, eax
0x18001ab69  jns     short loc_18001AB89
0x18001ab6b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ab72  jb      loc_18001AD6D
0x18001ab78  mov     edx, 3Eh ; '>'
0x18001ab7d  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x18001ab84  jmp     loc_18001AD56
0x18001ab89  lea     rcx, [rsi+8]
0x18001ab8d  call    ?clear@?$_HashTable@PEAUIDetectedFace@FaceAnalysis@Media@Windows@@U?$pair@QEAUIDetectedFace@FaceAnalysis@Media@Windows@@M@utl@@U?$hash@PEAUIDetectedFace@FaceAnalysis@Media@Windows@@@6@U?$equal_to@PEAUIDetectedFace@FaceAnalysis@Media@Windows@@@6@V?$allocator@U?$pair@QEAUIDetectedFace@FaceAnalysis@Media@Windows@@M@utl@@@6@$0A@@utl@@QEAAXXZ; utl::_HashTable<Windows::Media::FaceAnalysis::IDetectedFace *,utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>,utl::hash<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::equal_to<Windows::Media::FaceAnalysis::IDetectedFace *>,utl::allocator<utl::pair<Windows::Media::FaceAnalysis::IDetectedFace * const,float>>,0>::clear(void)
0x18001ab92  mov     rdx, r14; struct IMFSample *
0x18001ab95  mov     rcx, rdi; this
0x18001ab98  call    ?ExtractNecessaryAttributes@FaceDetectionMFT@@AEAAJPEAUIMFSample@@@Z; FaceDetectionMFT::ExtractNecessaryAttributes(IMFSample *)
0x18001ab9d  mov     ebx, eax
0x18001ab9f  test    eax, eax
0x18001aba1  jns     short loc_18001ABB7
0x18001aba3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001abaa  jb      loc_18001AD6D
0x18001abb0  mov     edx, 3Fh ; '?'
0x18001abb5  jmp     short loc_18001AB7D
0x18001abb7  lea     rcx, [rdi+278h]
0x18001abbe  mov     rdx, r14
0x18001abc1  call    ??4?$ComPtr@UIMFSample@@@WRL@Microsoft@@QEAAAEAV012@PEAUIMFSample@@@Z; Microsoft::WRL::ComPtr<IMFSample>::operator=(IMFSample *)
0x18001abc6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_MediaQI2505@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2505@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505> `wil::Feature<__WilFeatureTraits_Feature_MediaQI2505>::GetImpl(void)'::`2'::impl
0x18001abcd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2505@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505>::__private_IsEnabled(void)
0x18001abd2  lea     rsi, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x18001abd9  test    al, al
0x18001abdb  jz      loc_18001AC84
0x18001abe1  cmp     qword ptr [rdi+2B8h], 0
0x18001abe9  jnz     loc_18001AC84
0x18001abef  cmp     qword ptr [rdi+298h], 0
0x18001abf7  jnz     loc_18001AC84
0x18001abfd  cmp     cs:byte_180160805, 20h ; ' '
0x18001ac04  jb      short loc_18001AC21
0x18001ac06  mov     edx, 40h ; '@'
0x18001ac0b  mov     r8, rsi
0x18001ac0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac15  mov     rcx, [rcx+0D8h]
0x18001ac1c  call    WPP_SF_
0x18001ac21  lea     r14, [rdi+1F8h]
0x18001ac28  mov     [rbp+arg_0], r14
0x18001ac2c  mov     rcx, r14; lpCriticalSection
0x18001ac2f  call    cs:__imp_EnterCriticalSection
0x18001ac35  nop
0x18001ac36  mov     rcx, rdi; this
0x18001ac39  call    ?InitializeSoftwareFaceDector@FaceDetectionMFT@@AEAAJXZ; FaceDetectionMFT::InitializeSoftwareFaceDector(void)
0x18001ac3e  mov     ebx, eax
0x18001ac40  test    eax, eax
0x18001ac42  jns     short loc_18001AC7B
0x18001ac44  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ac4b  jb      short loc_18001AC6D
0x18001ac4d  mov     edx, 41h ; 'A'
0x18001ac52  mov     dword ptr [rsp+70h+var_50], eax
0x18001ac56  mov     r9, rdi
0x18001ac59  mov     r8, rsi
0x18001ac5c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac63  mov     rcx, [rcx+10h]
0x18001ac67  call    WPP_SF_qD
0x18001ac6c  nop
0x18001ac6d  mov     rcx, r14; lpCriticalSection
0x18001ac70  call    cs:__imp_LeaveCriticalSection
0x18001ac76  jmp     loc_18001AD6D
0x18001ac7b  mov     rcx, r14; lpCriticalSection
0x18001ac7e  call    cs:__imp_LeaveCriticalSection
0x18001ac84  cmp     byte ptr [rdi+354h], 0
0x18001ac8b  jz      short loc_18001ACA4
0x18001ac8d  xor     edx, edx; struct IMFAsyncResult *
0x18001ac8f  mov     rcx, rdi; this
0x18001ac92  call    ?RunAnalysis@FaceDetectionMFT@@AEAAXPEAUIMFAsyncResult@@@Z; FaceDetectionMFT::RunAnalysis(IMFAsyncResult *)
0x18001ac97  test    ebx, ebx
0x18001ac99  jns     loc_18001AED8
0x18001ac9f  jmp     loc_18001AD6D
0x18001aca4  mov     r10, [rdi+3B8h]
0x18001acab  mov     [rbp+arg_0], r10
0x18001acaf  mov     rdx, [rdi+228h]
0x18001acb6  cmp     rdx, [rdi+60h]
0x18001acba  jle     short loc_18001ACD9
0x18001acbc  sub     rdx, [rdi+60h]; __int64
0x18001acc0  lea     r8, [rbp+arg_0]; __int64 *
0x18001acc4  mov     rcx, r10; __int64
0x18001acc7  call    ?LongLongAdd@@YAJ_J0PEA_J@Z; LongLongAdd(__int64,__int64,__int64 *)
0x18001accc  mov     rcx, [rbp+arg_0]
0x18001acd0  test    eax, eax
0x18001acd2  cmovs   rcx, r10
0x18001acd6  mov     r10, rcx
0x18001acd9  mov     rdx, r10; __int64
0x18001acdc  mov     rcx, rdi; this
0x18001acdf  call    ?UpdateDeadline@CCoreMFT@@IEAAJ_J@Z; CCoreMFT::UpdateDeadline(__int64)
0x18001ace4  mov     ebx, eax
0x18001ace6  test    eax, eax
0x18001ace8  jns     short loc_18001ACFA
0x18001acea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001acf1  jb      short loc_18001AD6D
0x18001acf3  mov     edx, 42h ; 'B'
0x18001acf8  jmp     short loc_18001AD53
0x18001acfa  lea     rcx, [rbp+ppAsyncResult]
0x18001acfe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ad03  lea     rdx, [rdi+170h]; pCallback
0x18001ad0a  lea     r9, [rbp+ppAsyncResult]; ppAsyncResult
0x18001ad0e  xor     r8d, r8d; punkState
0x18001ad11  xor     ecx, ecx; punkObject
0x18001ad13  call    cs:__imp_MFCreateAsyncResult
0x18001ad19  mov     ebx, eax
0x18001ad1b  test    eax, eax
0x18001ad1d  jns     short loc_18001AD2F
0x18001ad1f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ad26  jb      short loc_18001AD6D
0x18001ad28  mov     edx, 43h ; 'C'
0x18001ad2d  jmp     short loc_18001AD53
0x18001ad2f  mov     rdx, [rbp+ppAsyncResult]; struct IMFAsyncResult *
0x18001ad33  mov     rcx, rdi; this
0x18001ad36  call    ?PutWorkItem@CCoreMFT@@IEAAJPEAUIMFAsyncResult@@@Z; CCoreMFT::PutWorkItem(IMFAsyncResult *)
0x18001ad3b  mov     ebx, eax
0x18001ad3d  test    eax, eax
0x18001ad3f  jns     loc_18001AED8
0x18001ad45  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ad4c  jb      short loc_18001AD6D
0x18001ad4e  mov     edx, 44h ; 'D'
0x18001ad53  mov     r8, rsi
0x18001ad56  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad5d  mov     dword ptr [rsp+70h+var_50], eax
0x18001ad61  mov     r9, rdi
0x18001ad64  mov     rcx, [rcx+10h]
0x18001ad68  call    WPP_SF_qD
0x18001ad6d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CameraQI2511@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CameraQI2511@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511> `wil::Feature<__WilFeatureTraits_Feature_CameraQI2511>::GetImpl(void)'::`2'::impl
0x18001ad74  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CameraQI2511@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraQI2511>::__private_IsEnabled(void)
0x18001ad79  test    al, al
0x18001ad7b  jz      loc_18001AE2C
0x18001ad81  cmp     ebx, 80700009h
0x18001ad87  jnz     short loc_18001AD90
0x18001ad89  xor     ebx, ebx
0x18001ad8b  jmp     loc_18001AECF
0x18001ad90  mov     rcx, [rdi+4428h]; this
0x18001ad97  test    rcx, rcx
0x18001ad9a  jz      loc_18001AECF
0x18001ada0  xorps   xmm2, xmm2; double
0x18001ada3  mov     edx, 4; unsigned int
0x18001ada8  call    ?AddData@CAggregatePhotographyTelemetry@@QEAAXKN@Z; CAggregatePhotographyTelemetry::AddData(ulong,double)
0x18001adad  mov     eax, cs:dword_18015F0D0
0x18001adb3  cmp     eax, 5
0x18001adb6  jbe     loc_18001AECF
0x18001adbc  mov     rdx, 400000000000h
0x18001adc6  lea     rcx, dword_18015F0D0
0x18001adcd  call    _tlgKeywordOn
0x18001add2  test    al, al
0x18001add4  jz      loc_18001AECF
0x18001adda  lea     rax, [rdi+4438h]
0x18001ade1  mov     [rbp+var_20], rax
0x18001ade5  lea     rax, aFacedetection; "FaceDetection"
0x18001adec  mov     [rbp+var_18], rax
0x18001adf0  mov     [rbp+var_10], 1000000h
0x18001adf8  lea     rax, [rbp+arg_0]
0x18001adfc  mov     [rsp+70h+var_30], rax
0x18001ae01  lea     rax, [rbp+var_20]
0x18001ae05  mov     [rsp+70h+var_38], rax
0x18001ae0a  lea     rax, [rbp+arg_10]
0x18001ae0e  mov     [rsp+70h+var_40], rax
0x18001ae13  lea     rax, [rbp+var_18]
0x18001ae17  mov     [rsp+70h+var_48], rax
0x18001ae1c  lea     rax, [rbp+var_10]
0x18001ae20  lea     rdx, byte_180151117
0x18001ae27  jmp     loc_18001AEBB
0x18001ae2c  mov     rcx, [rdi+4428h]; this
0x18001ae33  test    rcx, rcx
0x18001ae36  jz      loc_18001AECF
0x18001ae3c  xorps   xmm2, xmm2; double
0x18001ae3f  mov     edx, 4; unsigned int
0x18001ae44  call    ?AddData@CAggregatePhotographyTelemetry@@QEAAXKN@Z; CAggregatePhotographyTelemetry::AddData(ulong,double)
0x18001ae49  mov     eax, cs:dword_18015F0D0
0x18001ae4f  cmp     eax, 5
0x18001ae52  jbe     short loc_18001AECF
0x18001ae54  mov     rdx, 400000000000h
0x18001ae5e  lea     rcx, dword_18015F0D0
0x18001ae65  call    _tlgKeywordOn
0x18001ae6a  test    al, al
0x18001ae6c  jz      short loc_18001AECF
0x18001ae6e  lea     rax, [rdi+4438h]
0x18001ae75  mov     [rbp+var_10], rax
0x18001ae79  lea     rax, aFacedetection; "FaceDetection"
0x18001ae80  mov     [rbp+var_18], rax
0x18001ae84  mov     [rbp+var_20], 1000000h
0x18001ae8c  lea     rax, [rbp+arg_0]
0x18001ae90  mov     [rsp+70h+var_30], rax
0x18001ae95  lea     rax, [rbp+var_10]
0x18001ae99  mov     [rsp+70h+var_38], rax
0x18001ae9e  lea     rax, [rbp+arg_10]
0x18001aea2  mov     [rsp+70h+var_40], rax
0x18001aea7  lea     rax, [rbp+var_18]
0x18001aeab  mov     [rsp+70h+var_48], rax
0x18001aeb0  lea     rax, [rbp+var_20]
0x18001aeb4  lea     rdx, dword_18015108C
0x18001aebb  mov     [rsp+70h+var_50], rax
0x18001aec0  mov     dword ptr [rbp+arg_0], ebx
0x18001aec3  mov     [rbp+arg_10], 1
0x18001aeca  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18001aecf  mov     rcx, rdi; this
0x18001aed2  call    ?ResetAnalysisState@FaceDetectionMFT@@AEAAXXZ; FaceDetectionMFT::ResetAnalysisState(void)
0x18001aed7  nop
0x18001aed8  lea     rcx, [rbp+ppAsyncResult]
0x18001aedc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001aee1  mov     eax, ebx
0x18001aee3  add     rsp, 70h
0x18001aee7  pop     r14
0x18001aee9  pop     rdi
0x18001aeea  pop     rsi
0x18001aeeb  pop     rbx
0x18001aeec  pop     rbp
0x18001aeed  retn
```
