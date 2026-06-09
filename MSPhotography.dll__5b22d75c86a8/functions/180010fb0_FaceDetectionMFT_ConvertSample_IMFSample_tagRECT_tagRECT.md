# FaceDetectionMFT::ConvertSample(IMFSample *,tagRECT *,tagRECT *)

- ea: `0x180010fb0`
- end: `0x180011701`
- name: `?ConvertSample@FaceDetectionMFT@@AEAAJPEAUIMFSample@@PEAUtagRECT@@1@Z`
- size: `1873`
- prototype: `__int64 __fastcall(FaceDetectionMFT *__hidden this, struct IMFSample *, struct tagRECT *, struct tagRECT *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800180ec`

## callees

- `0x180005660`
- `0x18000b480`
- `0x18000b490`
- `0x18000c0b8`
- `0x18000c0f8`
- `0x18000d51c`
- `0x18000d638`
- `0x18000f14c`
- `0x180010fb0`
- `0x18001dddc`
- `0x18001dea8`
- `0x180132010`
- `0x180133524`
- `0x1801336c8`
- `0x1801358a8`
- `0x180142010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x18001106a`
- `MFPlat!MFCreateMediaType` at `0x18001106a`
- `MFPlat!MFGetStrideForBitmapInfoHeader` at `0x1800113de`
- `MFPlat!MFGetStrideForBitmapInfoHeader` at `0x1800113de`

## pseudocode

```c
__int64 __fastcall FaceDetectionMFT::ConvertSample(
        FaceDetectionMFT *this,
        struct IMFSample *a2,
        struct tagRECT *a3,
        struct tagRECT *a4)
{
  unsigned int v6; // r13d
  unsigned int v7; // ebx
  HRESULT v8; // esi
  __int64 v9; // rdx
  HRESULT (__stdcall *SetGUID)(IMFMediaType *, const GUID *const, const GUID *const); // rax
  DWORD *v11; // r15
  DWORD *v12; // r13
  __int64 v13; // rbx
  unsigned int v14; // esi
  _lambda_8ee436ab0af8888e284ad311860cc2ae_ *v15; // rax
  unsigned int v16; // eax
  __int64 v17; // r15
  int v18; // r13d
  __int64 v19; // r8
  unsigned int v20; // esi
  __int64 v21; // r8
  int v22; // edx
  unsigned int v23; // eax
  float *v24; // rbx
  float v25; // xmm0_4
  float *v26; // rcx
  float v27; // xmm1_4
  float v28; // xmm2_4
  float v29; // xmm1_4
  int v30; // eax
  float v31; // xmm0_4
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // r8
  int v35; // ecx
  int v36; // ecx
  int v37; // ecx
  DWORD v38; // ecx
  DWORD v39; // ecx
  struct IMFSample *v41; // [rsp+40h] [rbp-20h] BYREF
  __int64 v42; // [rsp+48h] [rbp-18h]
  _BYTE v43[16]; // [rsp+50h] [rbp-10h] BYREF
  IMFMediaType *ppMFType; // [rsp+A0h] [rbp+40h] BYREF
  struct tagRECT *v45; // [rsp+B0h] [rbp+50h] BYREF
  struct tagRECT *v46; // [rsp+B8h] [rbp+58h] BYREF

  v46 = a4;
  v45 = a3;
  v41 = 0;
  ppMFType = 0;
  v6 = *((_DWORD *)this + 202);
  LODWORD(v45) = v6;
  v7 = *((_DWORD *)this + 203);
  LODWORD(v46) = v7;
  if ( CCoreMFT::IsMjpgDecoderInitialized(this) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    v8 = CCoreMFT::MjpgDecodeSample(this, a2, &v41);
    if ( v8 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 69;
LABEL_86:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this, v8);
        goto LABEL_87;
      }
      goto LABEL_87;
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<IMFSample>::operator=(&v41, a2);
  }
  if ( !*((_BYTE *)this + 712) )
  {
LABEL_81:
    if ( *((_BYTE *)this + 852) )
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 640);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 640);
    v8 = CCoreMFT::XVPConvertSample(this, v41, (struct IMFSample **)this + 80, 0, 0);
    if ( v8 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 89;
      goto LABEL_86;
    }
    goto LABEL_87;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFType);
  v8 = MFCreateMediaType(&ppMFType);
  if ( v8 >= 0 )
  {
    v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
           ppMFType,
           &MF_MT_MAJOR_TYPE,
           &MFMediaType_Video);
    if ( v8 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 71;
        goto LABEL_86;
      }
      goto LABEL_87;
    }
    if ( *((_BYTE *)this + 545) )
    {
      SetGUID = ppMFType->lpVtbl->SetGUID;
      if ( *((_BYTE *)this + 592) )
      {
        v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))SetGUID)(
               ppMFType,
               &MF_MT_SUBTYPE,
               &MFVideoFormat_NV12);
        if ( v8 < 0 )
        {
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 72;
            goto LABEL_86;
          }
          goto LABEL_87;
        }
        v11 = (DWORD *)((char *)this + 580);
        *((_DWORD *)this + 145) = v6;
        v12 = (DWORD *)((char *)this + 584);
        *((_DWORD *)this + 146) = v7;
      }
      else
      {
        v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))SetGUID)(
               ppMFType,
               &MF_MT_SUBTYPE,
               &MFVideoFormat_ARGB32);
        if ( v8 < 0 )
        {
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 73;
            goto LABEL_86;
          }
          goto LABEL_87;
        }
        v13 = *(_QWORD *)(*((_QWORD *)this + 87) + 56LL);
        v42 = v13;
        v14 = (unsigned int)v46;
        LODWORD(v45) = v6;
        v15 = _lambda_8ee436ab0af8888e284ad311860cc2ae_::_lambda_8ee436ab0af8888e284ad311860cc2ae_(
                (_lambda_8ee436ab0af8888e284ad311860cc2ae_ *)v43,
                (const unsigned int *)&v45,
                (const unsigned int *)&v46);
        v16 = std::_Select_countr_zero_impl<unsigned int,_lambda_8ee436ab0af8888e284ad311860cc2ae_>(*(_QWORD *)v15);
        v17 = v6 / v16;
        v18 = v14 / v16;
        v8 = (*(__int64 (__fastcall **)(_QWORD, const GUID *, unsigned __int64))(**((_QWORD **)this + 90) + 176LL))(
               *((_QWORD *)this + 90),
               &MF_MT_PIXEL_ASPECT_RATIO,
               v17 | ((unsigned __int64)(v14 / v16) << 32));
        if ( v8 < 0 )
        {
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 74;
            goto LABEL_86;
          }
          goto LABEL_87;
        }
        v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT64)(
               ppMFType,
               &MF_MT_PIXEL_ASPECT_RATIO,
               0x100000001LL);
        if ( v8 < 0 )
        {
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 75;
            goto LABEL_86;
          }
          goto LABEL_87;
        }
        if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
          WPP_SF_qdd(*((_QWORD *)WPP_GLOBAL_Control + 27), 76, v19, this, v18, v17);
        v11 = (DWORD *)((char *)this + 580);
        *((_DWORD *)this + 145) = v13;
        v12 = (DWORD *)((char *)this + 584);
        v20 = HIDWORD(v42);
        *((_DWORD *)this + 146) = HIDWORD(v42);
        v7 = v20;
      }
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
        WPP_SF_qdd(*((_QWORD *)WPP_GLOBAL_Control + 27), 77, v21, this, v21, v7);
    }
    else
    {
      if ( *((_BYTE *)this + 852) && *((_DWORD *)this + 212) == 2 )
        goto LABEL_38;
      v22 = *((_DWORD *)this + 144);
      v23 = v6;
      if ( v6 <= v7 )
        v23 = v7;
      if ( v23 <= v22 )
      {
LABEL_38:
        v11 = (DWORD *)((char *)this + 580);
        *((_DWORD *)this + 145) = v6;
        v12 = (DWORD *)((char *)this + 584);
        *((_DWORD *)this + 146) = v7;
        v24 = (float *)((char *)this + 572);
        *((_DWORD *)this + 143) = 1065353216;
      }
      else
      {
        v12 = (DWORD *)((char *)this + 584);
        v25 = (float)(int)v7;
        v26 = (float *)((char *)this + 572);
        v27 = (float)(int)v45;
        v11 = (DWORD *)((char *)this + 580);
        v28 = (float)v22;
        if ( (unsigned int)v45 <= v7 )
        {
          *v12 = v22;
          v31 = v25 / v28;
          *v26 = v31;
          v32 = (int)(float)(v27 / v31);
          *v11 = v32;
          v24 = (float *)((char *)this + 572);
          if ( (v32 & 1) != 0 )
            *v11 = v32 - 1;
        }
        else
        {
          *v11 = v22;
          v29 = v27 / v28;
          *v26 = v29;
          v30 = (int)(float)(v25 / v29);
          *v12 = v30;
          if ( (v30 & 1) != 0 )
            *v12 = v30 - 1;
          v24 = (float *)((char *)this + 572);
        }
      }
      v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const GUID *))ppMFType->lpVtbl->SetGUID)(
             ppMFType,
             &MF_MT_SUBTYPE,
             &MFVideoFormat_NV12);
      if ( v8 < 0 )
      {
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 78;
          goto LABEL_86;
        }
        goto LABEL_87;
      }
      v8 = MFGetStrideForBitmapInfoHeader(MFVideoFormat_NV12.Data1, *v11, (LONG *)this + 147);
      if ( v8 < 0 )
      {
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 79;
          goto LABEL_86;
        }
        goto LABEL_87;
      }
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
        WPP_SF_qgdd(*((_QWORD *)WPP_GLOBAL_Control + 27), v33, v34, this, *v24, *v11, *v12);
    }
    v35 = *((_DWORD *)this + 253);
    if ( v35 )
    {
      v36 = v35 - 1;
      if ( v36 )
      {
        v37 = v36 - 1;
        if ( v37 )
        {
          if ( v37 == 1 )
          {
            v38 = *v11;
            *v11 = *v12;
            *v12 = v38;
            v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(**((_QWORD **)this + 90) + 168LL))(
                   *((_QWORD *)this + 90),
                   MF_MT_VIDEO_ROTATION,
                   270);
            if ( v8 < 0 )
            {
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v9 = 84;
                goto LABEL_86;
              }
              goto LABEL_87;
            }
          }
          else
          {
            if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x20u )
              WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 85, &WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids, this);
            v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD))(**((_QWORD **)this + 90) + 168LL))(
                   *((_QWORD *)this + 90),
                   MF_MT_VIDEO_ROTATION,
                   0);
            if ( v8 < 0 )
            {
              if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
              {
                v9 = 86;
                goto LABEL_86;
              }
              goto LABEL_87;
            }
          }
        }
        else
        {
          v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(**((_QWORD **)this + 90) + 168LL))(
                 *((_QWORD *)this + 90),
                 MF_MT_VIDEO_ROTATION,
                 180);
          if ( v8 < 0 )
          {
            if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            {
              v9 = 83;
              goto LABEL_86;
            }
            goto LABEL_87;
          }
        }
      }
      else
      {
        v39 = *v11;
        *v11 = *v12;
        *v12 = v39;
        v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(**((_QWORD **)this + 90) + 168LL))(
               *((_QWORD *)this + 90),
               MF_MT_VIDEO_ROTATION,
               90);
        if ( v8 < 0 )
        {
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          {
            v9 = 82;
            goto LABEL_86;
          }
          goto LABEL_87;
        }
      }
    }
    else
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD))(**((_QWORD **)this + 90) + 168LL))(
             *((_QWORD *)this + 90),
             MF_MT_VIDEO_ROTATION,
             0);
      if ( v8 < 0 )
      {
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
          v9 = 81;
          goto LABEL_86;
        }
        goto LABEL_87;
      }
    }
    v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, unsigned __int64))ppMFType->lpVtbl->SetUINT64)(
           ppMFType,
           &MF_MT_FRAME_SIZE,
           *v12 | ((unsigned __int64)*v11 << 32));
    if ( v8 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 87;
        goto LABEL_86;
      }
      goto LABEL_87;
    }
    v8 = CCoreMFT::ConfigureXVP(this, *((struct IMFMediaType **)this + 90), ppMFType, v41);
    if ( v8 < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
        v9 = 88;
        goto LABEL_86;
      }
      goto LABEL_87;
    }
    *((_BYTE *)this + 712) = 0;
    goto LABEL_81;
  }
  if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v9 = 70;
    goto LABEL_86;
  }
LABEL_87:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppMFType);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180010fb0  mov     [rsp-38h+arg_8], rbx
0x180010fb5  mov     [rsp-38h+arg_18], r9
0x180010fba  mov     [rsp-38h+arg_10], r8
0x180010fbf  push    rbp
0x180010fc0  push    rsi
0x180010fc1  push    rdi
0x180010fc2  push    r12
0x180010fc4  push    r13
0x180010fc6  push    r14
0x180010fc8  push    r15
0x180010fca  mov     rbp, rsp
0x180010fcd  sub     rsp, 60h
0x180010fd1  mov     rsi, rdx
0x180010fd4  mov     rdi, rcx
0x180010fd7  xor     r15d, r15d
0x180010fda  mov     [rbp+var_20], r15
0x180010fde  mov     [rbp+ppMFType], r15
0x180010fe2  mov     r13d, [rcx+328h]
0x180010fe9  mov     dword ptr [rbp+arg_10], r13d
0x180010fed  mov     ebx, [rcx+32Ch]
0x180010ff3  mov     dword ptr [rbp+arg_18], ebx
0x180010ff6  call    ?IsMjpgDecoderInitialized@CCoreMFT@@IEAA_NXZ; CCoreMFT::IsMjpgDecoderInitialized(void)
0x180010ffb  lea     rcx, [rbp+var_20]
0x180010fff  test    al, al
0x180011001  jz      short loc_18001103E
0x180011003  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011008  lea     r8, [rbp+var_20]; struct IMFSample **
0x18001100c  mov     rdx, rsi; struct IMFSample *
0x18001100f  mov     rcx, rdi; this
0x180011012  call    ?MjpgDecodeSample@CCoreMFT@@IEAAJPEAUIMFSample@@PEAPEAU2@@Z; CCoreMFT::MjpgDecodeSample(IMFSample *,IMFSample * *)
0x180011017  mov     esi, eax
0x180011019  test    eax, eax
0x18001101b  jns     short loc_180011046
0x18001101d  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180011022  mov     r14b, 1
0x180011025  cmp     al, r14b
0x180011028  jb      loc_1800116D4
0x18001102e  lea     edx, [r15+45h]
0x180011032  lea     r8, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180011039  jmp     loc_1800116BC
0x18001103e  mov     rdx, rsi
0x180011041  call    ??4?$ComPtr@UIMFSample@@@WRL@Microsoft@@QEAAAEAV012@PEAUIMFSample@@@Z; Microsoft::WRL::ComPtr<IMFSample>::operator=(IMFSample *)
0x180011046  mov     r14b, 1
0x180011049  lea     r12, WPP_45b7a7f164d436fa30fa2a10d6f3fbff_Traceguids
0x180011050  cmp     [rdi+2C8h], r15b
0x180011057  jz      loc_18001166D
0x18001105d  lea     rcx, [rbp+ppMFType]
0x180011061  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011066  lea     rcx, [rbp+ppMFType]; ppMFType
0x18001106a  call    cs:__imp_MFCreateMediaType
0x180011070  mov     esi, eax
0x180011072  test    eax, eax
0x180011074  jns     short loc_18001108E
0x180011076  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001107b  cmp     al, r14b
0x18001107e  jb      loc_1800116D4
0x180011084  mov     edx, 46h ; 'F'
0x180011089  jmp     loc_1800116B9
0x18001108e  mov     rcx, [rbp+ppMFType]
0x180011092  mov     rax, [rcx]
0x180011095  lea     r8, MFMediaType_Video
0x18001109c  lea     rdx, MF_MT_MAJOR_TYPE
0x1800110a3  mov     rax, [rax+0C0h]
0x1800110aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110af  mov     esi, eax
0x1800110b1  test    eax, eax
0x1800110b3  jns     short loc_1800110CD
0x1800110b5  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800110ba  cmp     al, r14b
0x1800110bd  jb      loc_1800116D4
0x1800110c3  mov     edx, 47h ; 'G'
0x1800110c8  jmp     loc_1800116B9
0x1800110cd  cmp     [rdi+221h], r15b
0x1800110d4  jz      loc_1800112BC
0x1800110da  mov     rcx, [rbp+ppMFType]
0x1800110de  lea     rdx, MF_MT_SUBTYPE
0x1800110e5  mov     rax, [rcx]
0x1800110e8  mov     rax, [rax+0C0h]
0x1800110ef  cmp     [rdi+250h], r15b
0x1800110f6  jz      short loc_180011140
0x1800110f8  lea     r8, MFVideoFormat_NV12
0x1800110ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011104  mov     esi, eax
0x180011106  test    eax, eax
0x180011108  jns     short loc_180011122
0x18001110a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001110f  cmp     al, r14b
0x180011112  jb      loc_1800116D4
0x180011118  mov     edx, 48h ; 'H'
0x18001111d  jmp     loc_1800116B9
0x180011122  lea     r15, [rdi+244h]
0x180011129  mov     [r15], r13d
0x18001112c  lea     r13, [rdi+248h]
0x180011133  mov     [r13+0], ebx
0x180011137  mov     r8d, dword ptr [rbp+arg_10]
0x18001113b  jmp     loc_180011286
0x180011140  lea     r8, MFVideoFormat_ARGB32
0x180011147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001114c  mov     esi, eax
0x18001114e  test    eax, eax
0x180011150  jns     short loc_18001116A
0x180011152  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180011157  cmp     al, r14b
0x18001115a  jb      loc_1800116D4
0x180011160  mov     edx, 49h ; 'I'
0x180011165  jmp     loc_1800116B9
0x18001116a  mov     rbx, [rdi+2B8h]
0x180011171  mov     rbx, [rbx+38h]
0x180011175  mov     [rbp+var_18], rbx
0x180011179  mov     esi, dword ptr [rbp+arg_18]
0x18001117c  mov     dword ptr [rbp+arg_18], esi
0x18001117f  mov     dword ptr [rbp+arg_10], r13d
0x180011183  lea     r8, [rbp+arg_18]; unsigned int *
0x180011187  lea     rdx, [rbp+arg_10]; unsigned int *
0x18001118b  lea     rcx, [rbp+var_10]; this
0x18001118f  call    ??0_lambda_8ee436ab0af8888e284ad311860cc2ae_@@QEAA@AEBI0@Z; _lambda_8ee436ab0af8888e284ad311860cc2ae_::_lambda_8ee436ab0af8888e284ad311860cc2ae_(uint const &,uint const &)
0x180011194  mov     rcx, [rax]
0x180011197  call    ??$_Select_countr_zero_impl@IV_lambda_8ee436ab0af8888e284ad311860cc2ae_@@@std@@YA?A_TV_lambda_8ee436ab0af8888e284ad311860cc2ae_@@@Z
0x18001119c  mov     r8d, eax
0x18001119f  mov     rcx, [rdi+2D0h]
0x1800111a6  xor     edx, edx
0x1800111a8  mov     eax, r13d
0x1800111ab  div     r8d
0x1800111ae  mov     r15d, eax
0x1800111b1  xor     edx, edx
0x1800111b3  mov     eax, esi
0x1800111b5  div     r8d
0x1800111b8  mov     r13d, eax
0x1800111bb  mov     r9, [rcx]
0x1800111be  mov     r8d, eax
0x1800111c1  shl     r8, 20h
0x1800111c5  or      r8, r15
0x1800111c8  lea     rdx, MF_MT_PIXEL_ASPECT_RATIO
0x1800111cf  mov     rax, [r9+0B0h]
0x1800111d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111db  mov     esi, eax
0x1800111dd  test    eax, eax
0x1800111df  jns     short loc_1800111F9
0x1800111e1  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800111e6  cmp     al, r14b
0x1800111e9  jb      loc_1800116D4
0x1800111ef  mov     edx, 4Ah ; 'J'
0x1800111f4  jmp     loc_1800116B9
0x1800111f9  mov     rcx, [rbp+ppMFType]
0x1800111fd  mov     rax, [rcx]
0x180011200  mov     r8, 100000001h
0x18001120a  lea     rdx, MF_MT_PIXEL_ASPECT_RATIO
0x180011211  mov     rax, [rax+0B0h]
0x180011218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001121d  mov     esi, eax
0x18001121f  test    eax, eax
0x180011221  jns     short loc_18001123B
0x180011223  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180011228  cmp     al, r14b
0x18001122b  jb      loc_1800116D4
0x180011231  mov     edx, 4Bh ; 'K'
0x180011236  jmp     loc_1800116B9
0x18001123b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180011240  cmp     al, 20h ; ' '
0x180011242  jb      short loc_180011269
0x180011244  mov     edx, 4Ch ; 'L'
0x180011249  mov     [rsp+60h+var_38], r15d
0x18001124e  mov     dword ptr [rsp+60h+var_40], r13d
0x180011253  mov     r9, rdi
0x180011256  mov     rcx, cs:WPP_GLOBAL_Control
0x18001125d  mov     rcx, [rcx+0D8h]
0x180011264  call    WPP_SF_qdd
0x180011269  lea     r15, [rdi+244h]
0x180011270  mov     [r15], ebx
0x180011273  lea     r13, [rdi+248h]
0x18001127a  mov     esi, dword ptr [rbp+var_18+4]
0x18001127d  mov     [r13+0], esi
0x180011281  mov     r8d, ebx
0x180011284  mov     ebx, esi
0x180011286  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x18001128b  cmp     al, 20h ; ' '
0x18001128d  jb      loc_18001143D
0x180011293  mov     edx, 4Dh ; 'M'
0x180011298  mov     [rsp+60h+var_38], ebx
0x18001129c  mov     dword ptr [rsp+60h+var_40], r8d
0x1800112a1  mov     r9, rdi
0x1800112a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800112ab  mov     rcx, [rcx+0D8h]
0x1800112b2  call    WPP_SF_qdd
0x1800112b7  jmp     loc_18001143D
0x1800112bc  cmp     [rdi+354h], r15b
0x1800112c3  jz      short loc_1800112CE
0x1800112c5  cmp     dword ptr [rdi+350h], 2
0x1800112cc  jz      short loc_1800112E1
0x1800112ce  mov     edx, [rdi+240h]
0x1800112d4  mov     eax, r13d
0x1800112d7  cmp     r13d, ebx
0x1800112da  cmovbe  eax, ebx
0x1800112dd  cmp     eax, edx
0x1800112df  ja      short loc_180011308
0x1800112e1  lea     r15, [rdi+244h]
0x1800112e8  mov     [r15], r13d
0x1800112eb  lea     r13, [rdi+248h]
0x1800112f2  mov     [r13+0], ebx
0x1800112f6  lea     rbx, [rdi+23Ch]
0x1800112fd  mov     dword ptr [rbx], 3F800000h
0x180011303  jmp     loc_18001138F
0x180011308  lea     r13, [rdi+248h]
0x18001130f  xorps   xmm0, xmm0
0x180011312  cvtsi2ss xmm0, rbx
0x180011317  lea     rcx, [rdi+23Ch]
0x18001131e  mov     r8d, dword ptr [rbp+arg_10]
0x180011322  xorps   xmm1, xmm1
0x180011325  cvtsi2ss xmm1, r8
0x18001132a  lea     r15, [rdi+244h]
0x180011331  xorps   xmm2, xmm2
0x180011334  cvtsi2ss xmm2, rdx
0x180011339  cmp     r8d, ebx
0x18001133c  jbe     short loc_18001136A
0x18001133e  mov     [r15], edx
0x180011341  divss   xmm1, xmm2
0x180011345  movss   dword ptr [rcx], xmm1
0x180011349  divss   xmm0, xmm1
0x18001134d  cvttss2si rax, xmm0
0x180011352  mov     [r13+0], eax
0x180011356  test    r14b, al
0x180011359  jz      short loc_180011361
0x18001135b  dec     eax
0x18001135d  mov     [r13+0], eax
0x180011361  lea     rbx, [rdi+23Ch]
0x180011368  jmp     short loc_18001138F
0x18001136a  mov     [r13+0], edx
0x18001136e  divss   xmm0, xmm2
0x180011372  movss   dword ptr [rcx], xmm0
0x180011376  divss   xmm1, xmm0
0x18001137a  cvttss2si rax, xmm1
0x18001137f  mov     [r15], eax
0x180011382  mov     rbx, rcx
0x180011385  test    r14b, al
0x180011388  jz      short loc_18001138F
0x18001138a  dec     eax
0x18001138c  mov     [r15], eax
0x18001138f  mov     rcx, [rbp+ppMFType]
0x180011393  mov     rax, [rcx]
0x180011396  lea     r8, MFVideoFormat_NV12
0x18001139d  lea     rdx, MF_MT_SUBTYPE
0x1800113a4  mov     rax, [rax+0C0h]
0x1800113ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113b0  mov     esi, eax
0x1800113b2  test    eax, eax
0x1800113b4  jns     short loc_1800113CE
0x1800113b6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800113bb  cmp     al, r14b
0x1800113be  jb      loc_1800116D4
0x1800113c4  mov     edx, 4Eh ; 'N'
0x1800113c9  jmp     loc_1800116B9
0x1800113ce  lea     r8, [rdi+24Ch]; pStride
0x1800113d5  mov     edx, [r15]; dwWidth
0x1800113d8  mov     ecx, cs:MFVideoFormat_NV12.Data1; format
0x1800113de  call    cs:__imp_MFGetStrideForBitmapInfoHeader
0x1800113e4  mov     esi, eax
0x1800113e6  test    eax, eax
0x1800113e8  jns     short loc_180011402
0x1800113ea  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800113ef  cmp     al, r14b
0x1800113f2  jb      loc_1800116D4
0x1800113f8  mov     edx, 4Fh ; 'O'
0x1800113fd  jmp     loc_1800116B9
0x180011402  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180011407  cmp     al, 20h ; ' '
0x180011409  jb      short loc_18001143D
0x18001140b  movss   xmm0, dword ptr [rbx]
0x18001140f  cvtps2pd xmm0, xmm0
0x180011412  mov     eax, [r13+0]
0x180011416  mov     [rsp+60h+var_30], eax
0x18001141a  mov     eax, [r15]
0x18001141d  mov     [rsp+60h+var_38], eax
0x180011421  movsd   [rsp+60h+var_40], xmm0
0x180011427  mov     r9, rdi
0x18001142a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011431  mov     rcx, [rcx+0D8h]
0x180011438  call    WPP_SF_qgdd
0x18001143d  mov     ecx, [rdi+3F4h]
0x180011443  test    ecx, ecx
0x180011445  jz      loc_1800115B2
0x18001144b  sub     ecx, 1
0x18001144e  jz      loc_180011563
0x180011454  sub     ecx, 1
0x180011457  jz      loc_18001151E
0x18001145d  cmp     ecx, 1
0x180011460  jz      short loc_1800114CB
0x180011462  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180011467  cmp     al, 20h ; ' '
0x180011469  jb      short loc_180011489
0x18001146b  mov     edx, 55h ; 'U'
0x180011470  mov     r9, rdi
0x180011473  mov     r8, r12
0x180011476  mov     rcx, cs:WPP_GLOBAL_Control
0x18001147d  mov     rcx, [rcx+0D8h]
0x180011484  call    WPP_SF_q
0x180011489  mov     rcx, [rdi+2D0h]
0x180011490  mov     rax, [rcx]
0x180011493  xor     r8d, r8d
0x180011496  lea     rdx, MF_MT_VIDEO_ROTATION
0x18001149d  mov     rax, [rax+0A8h]
  ... truncated ...
```
