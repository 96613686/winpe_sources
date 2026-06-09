# GEL::WICImageResource::CropImageAndResample(_GUID const &,_GUID const &,bool,bool,Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &,bool,Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &,Math::TVector2<Math::TUnits<int,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>> const &,GEL::ImageFormat,Ofc::TOwnerPtr<GEL::IImageResource> &)

- ea: `0x180105a00`
- end: `0x180105ebc`
- name: `?CropImageAndResample@WICImageResource@GEL@@AEBAXAEBU_GUID@@0_N1AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@1AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@5@AEBU?$TVector2@V?$TUnits@HU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@5@W4ImageFormat@2@AEAV?$TOwnerPtr@UIImageResource@GEL@@@Ofc@@@Z`
- size: `1212`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180105410`

## callees

- `0x180018ad0`
- `0x18001f490`
- `0x180020c30`
- `0x18004e9d0`
- `0x1800573f0`
- `0x1800786fc`
- `0x1800a0638`
- `0x1800d33a4`
- `0x1800d8288`
- `0x180105a00`
- `0x180105ec0`
- `0x180106880`

## import_xrefs

- `mso40uiWin32Client!__imp_?ConvertFrameToValidPixelFormat@WIC@ARC@@YA?AV?$TCntPtr@UIWICBitmapSource@@@Mso@@AEAUIWICImagingFactory@@AEBU_GUID@@AEAUIWICBitmapSource@@@Z` at `0x180105c67`
- `mso40uiWin32Client!__imp_?ConvertFrameToValidPixelFormat@WIC@ARC@@YA?AV?$TCntPtr@UIWICBitmapSource@@@Mso@@AEAUIWICImagingFactory@@AEBU_GUID@@AEAUIWICBitmapSource@@@Z` at `0x180105c67`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x180105af5`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x180105af5`
- `mso40uiWin32Client!__imp_?GetWICImagingFactory@WIC@ARC@@YA?AV?$TCntPtr@UIWICImagingFactory@@@Mso@@XZ` at `0x180105c4c`
- `mso40uiWin32Client!__imp_?GetWICImagingFactory@WIC@ARC@@YA?AV?$TCntPtr@UIWICImagingFactory@@@Mso@@XZ` at `0x180105c4c`
- `mso40uiWin32Client!__imp_?Create@IWICPlatformBitmap@WIC@ARC@@SA?AV?$TCntPtr@UIWICPlatformBitmap@WIC@ARC@@@Mso@@AEBUIWICBitmapSource@@W4ImageFormat@3@AEBU_GUID@@@Z` at `0x180105e3f`
- `mso40uiWin32Client!__imp_?Create@IWICPlatformBitmap@WIC@ARC@@SA?AV?$TCntPtr@UIWICPlatformBitmap@WIC@ARC@@@Mso@@AEBUIWICBitmapSource@@W4ImageFormat@3@AEBU_GUID@@@Z` at `0x180105e3f`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z` at `0x180105b3b`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z` at `0x180105b3b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180105ba3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180105c03`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180105cba`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180105ba3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180105c03`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180105cba`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall GEL::WICImageResource::CropImageAndResample(
        __int64 a1,
        ARC::WIC *a2,
        ARC::WIC *a3,
        char a4,
        int a5,
        __int128 *a6,
        char a7,
        int *a8,
        __int64 a9,
        unsigned int a10,
        void (__fastcall ****a11)(_QWORD, __int64))
{
  char v13; // r13
  void (__fastcall ****v14)(_QWORD, _QWORD); // rbx
  void (__fastcall ***v15)(_QWORD, __int64); // rcx
  unsigned int *Size; // rax
  unsigned int v17; // ecx
  unsigned int v18; // edx
  char v19; // r15
  char v20; // si
  unsigned int v21; // ebx
  unsigned __int64 v22; // rdi
  __int64 result; // rax
  void (__fastcall ***v24)(_QWORD); // rcx
  __int64 *v25; // rax
  __int64 v26; // rcx
  void (__fastcall ***v27)(_QWORD); // rbx
  void (__fastcall ***v28)(_QWORD); // rcx
  unsigned __int64 v29; // r9
  unsigned __int64 v30; // r9
  unsigned __int64 v31; // rdi
  __int64 v32; // rax
  __int64 v33; // rsi
  __int64 v34; // rdi
  const struct _GUID *v35; // rdx
  ARC::WIC *v36; // r8
  __int64 *valid; // rax
  __int64 v38; // rcx
  int v39; // eax
  int v40; // eax
  unsigned __int64 v41; // rdx
  unsigned int v42; // r8d
  GEL::WICImageResource *v43; // rsi
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 (__fastcall *v46)(_QWORD); // rax
  void (__fastcall ***v47)(_QWORD); // rcx
  struct ARC::IPlatformBitmap **v48; // rax
  __int64 v49; // rcx
  void (__fastcall ***v50)(_QWORD); // [rsp+38h] [rbp-59h] BYREF
  __int64 v51; // [rsp+40h] [rbp-51h] BYREF
  __int64 v52; // [rsp+48h] [rbp-49h] BYREF
  __int128 v53; // [rsp+50h] [rbp-41h] BYREF
  void (__fastcall ***v54)(_QWORD); // [rsp+60h] [rbp-31h] BYREF
  _DWORD v55[2]; // [rsp+68h] [rbp-29h] BYREF
  __int64 v56; // [rsp+70h] [rbp-21h]
  __int64 v57; // [rsp+78h] [rbp-19h] BYREF
  _QWORD v58[9]; // [rsp+80h] [rbp-11h] BYREF
  __int64 v59; // [rsp+D8h] [rbp+47h] BYREF
  ARC::WIC *v60; // [rsp+E8h] [rbp+57h]
  char v61; // [rsp+F0h] [rbp+5Fh]

  v61 = a4;
  v60 = a3;
  v13 = 0;
  LODWORD(v59) = 0;
  v14 = a11;
  v15 = *a11;
  if ( !*a11 )
    goto LABEL_2;
  while ( 1 )
  {
    (**v15)(v15, 1);
LABEL_2:
    *v14 = 0;
    Size = (unsigned int *)GEL::RasterImageResource::GetSize(a1, &v59);
    v17 = 0;
    *(_QWORD *)&v53 = 0;
    v18 = *Size;
    *((_QWORD *)&v53 + 1) = *(_QWORD *)Size;
    v19 = a5;
    if ( (_BYTE)a5 )
    {
      v53 = *a6;
      v18 = DWORD2(v53);
      v17 = v53;
    }
    v20 = a7;
    if ( a7 )
    {
      v21 = *a8;
      v22 = (unsigned int)a8[1];
      goto LABEL_6;
    }
    v22 = *((_QWORD *)&v53 + 1);
    v29 = v53;
    if ( v17 <= v18 && DWORD1(v53) <= HIDWORD(v53) )
    {
      v21 = v18 - v17;
      goto LABEL_27;
    }
    while ( 1 )
    {
      v21 = 0;
LABEL_27:
      if ( v17 > v18 || (v30 = HIDWORD(v29), v31 = HIDWORD(v22), (unsigned int)v30 > (unsigned int)v31) )
        v22 = 0;
      else
        v22 = (unsigned int)(v31 - v30);
LABEL_6:
      result = (*(__int64 (__fastcall **)(__int64, void (__fastcall ****)(_QWORD), _QWORD))(*(_QWORD *)a1 + 336LL))(
                 a1,
                 &v50,
                 0);
      if ( v19 )
      {
        v19 = 0;
      }
      else
      {
        v19 = 0;
        if ( !v20 )
          goto LABEL_8;
      }
      v25 = (__int64 *)ARC::IPlatformBitmapClipper::Create(&v59, v50, &v53);
      a1 = *v25;
      *v25 = 0;
      v58[1] = a1;
      v26 = v59;
      if ( v59 )
      {
        v59 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
      }
      v55[0] = v21;
      v55[1] = v22;
      a5 = 1;
      ARC::IPlatformBitmapScaler::Create(&v54, a1, v55, &a5);
      v27 = v54;
      v28 = v50;
      if ( v50 != v54 )
      {
        if ( v54 )
        {
          (**v54)(v54);
          v28 = v50;
        }
        if ( v28 )
        {
          v50 = 0;
          (*v28)[1](v28);
        }
        v28 = v27;
        v50 = v27;
      }
      if ( v28 )
        break;
      CrashWithRecovery(0x1E3C3840u, 0);
    }
    Mso::IObjectProxy::QueryObjectElseCrash<ARC::WIC::IWICPlatformBitmap const,0>(v28, v58);
    v14 = (void (__fastcall ****)(_QWORD, _QWORD))v58[0];
    if ( v58[0] )
      break;
    CrashWithRecovery(0x1E3C3840u, 0);
  }
  v32 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v58[0] + 144LL))(v58[0]);
  v33 = v32;
  v34 = v32;
  v56 = v32;
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 8LL))(v32);
  ARC::WIC::GetWICImagingFactory(&v51);
  if ( v61 )
    goto LABEL_43;
  v36 = v60;
LABEL_37:
  valid = (__int64 *)ARC::WIC::ConvertFrameToValidPixelFormat(&v59, v51, v36, v33);
  v34 = *valid;
  v56 = *valid;
  *valid = 0;
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  v38 = v59;
  if ( v59 )
  {
    v59 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  while ( 1 )
  {
    v52 = 0;
    if ( v51 )
      break;
    CrashWithRecovery(0x1E3C3840u, 0);
LABEL_43:
    if ( ARC::WIC::IsIndexedPixelFormat(a2, v35) )
    {
      v36 = a2;
      goto LABEL_37;
    }
  }
  v39 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v51 + 144LL))(v51, v34, 1, &v52);
  if ( v39 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v39, 0x129635Bu);
    __debugbreak();
  }
  v40 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v52 + 80LL))(v52);
  if ( v40 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v40, 0x129635Cu);
    __debugbreak();
  }
  v43 = (GEL::WICImageResource *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x98, v41, v42);
  v58[2] = v43;
  if ( v43 )
  {
    v48 = (struct ARC::IPlatformBitmap **)ARC::WIC::IWICPlatformBitmap::Create(
                                            &v57,
                                            v52,
                                            a10,
                                            &GUID_WICPixelFormatDontCare);
    v13 = 1;
    LODWORD(v59) = 1;
    v44 = GEL::WICImageResource::WICImageResource(v43, *v48);
  }
  else
  {
    v44 = 0;
  }
  Ofc::TOwnerPtr<GEL::IImageResource>::Attach(a11, v44);
  if ( (v13 & 1) != 0 )
  {
    v49 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 8LL))(v49);
    }
  }
  if ( v52 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
  v45 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  v46 = (__int64 (__fastcall *)(_QWORD))(*v14)[1];
  if ( v46 == Mso::TRefCountedImpl<GEL::IImage>::Release )
  {
    result = Mso::TRefCountedImpl<GEL::IImage>::Release(v14);
  }
  else if ( v46 == Mso::TRefCountedImpl<GEL::IPath>::Release )
  {
    result = Mso::TRefCountedImpl<GEL::IPath>::Release(v14);
  }
  else if ( v46 == Mso::TRefCountedImpl<Mso::IRefCounted>::Release )
  {
    result = Mso::TRefCountedImpl<Mso::IRefCounted>::Release(v14);
  }
  else
  {
    result = v46(v14);
  }
  v47 = v54;
  if ( v54 )
  {
    v54 = 0;
    result = ((__int64 (__fastcall *)(_QWORD))(*v47)[1])(v47);
  }
  if ( a1 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
LABEL_8:
  v24 = v50;
  if ( v50 )
  {
    v50 = 0;
    return ((__int64 (__fastcall *)(_QWORD))(*v24)[1])(v24);
  }
  return result;
}

```

## disassembly

```asm
0x180105a00  mov     rax, rsp
0x180105a03  mov     [rax+10h], rbx
0x180105a07  mov     [rax+20h], r9b
0x180105a0b  mov     [rax+18h], r8
0x180105a0f  push    rbp
0x180105a10  push    rsi
0x180105a11  push    rdi
0x180105a12  push    r12
0x180105a14  push    r13
0x180105a16  push    r14
0x180105a18  push    r15
0x180105a1a  lea     rbp, [rax-3Fh]
0x180105a1e  sub     rsp, 90h
0x180105a25  mov     r12, rdx
0x180105a28  mov     r14, rcx
0x180105a2b  xor     r13d, r13d
0x180105a2e  mov     dword ptr [rbp+37h+arg_0], r13d
0x180105a32  mov     rbx, [rbp+37h+arg_50]
0x180105a39  mov     rcx, [rbx]
0x180105a3c  test    rcx, rcx
0x180105a3f  jnz     loc_180105BAA
0x180105a45  mov     [rbx], r13
0x180105a48  lea     rdx, [rbp+37h+arg_0]
0x180105a4c  mov     rcx, r14
0x180105a4f  call    ?GetSize@RasterImageResource@GEL@@UEBA?AU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@XZ; GEL::RasterImageResource::GetSize(void)
0x180105a54  xor     ecx, ecx
0x180105a56  mov     dword ptr [rbp+37h+var_78], ecx
0x180105a59  mov     dword ptr [rbp+37h+var_78+4], ecx
0x180105a5c  mov     edx, [rax]
0x180105a5e  mov     dword ptr [rbp+37h+var_78+8], edx
0x180105a61  mov     eax, [rax+4]
0x180105a64  mov     dword ptr [rbp+37h+var_78+0Ch], eax
0x180105a67  mov     r15b, byte ptr [rbp+37h+arg_20]
0x180105a6b  test    r15b, r15b
0x180105a6e  jnz     loc_180105E8B
0x180105a74  mov     sil, [rbp+37h+arg_30]
0x180105a78  test    sil, sil
0x180105a7b  jz      loc_180105BC0
0x180105a81  mov     rax, [rbp+37h+arg_38]
0x180105a85  mov     ebx, [rax]
0x180105a87  mov     edi, [rax+4]
0x180105a8a  mov     rax, [r14]
0x180105a8d  xor     r8d, r8d
0x180105a90  lea     rdx, [rbp+37h+var_90]
0x180105a94  mov     rcx, r14
0x180105a97  mov     rax, [rax+150h]
0x180105a9e  call    cs:__guard_dispatch_icall_fptr
0x180105aa4  test    r15b, r15b
0x180105aa7  jnz     short loc_180105AE6
0x180105aa9  xor     r15d, r15d
0x180105aac  test    sil, sil
0x180105aaf  jnz     short loc_180105AE9
0x180105ab1  mov     rcx, [rbp+37h+var_90]
0x180105ab5  test    rcx, rcx
0x180105ab8  jz      short loc_180105ACB
0x180105aba  mov     [rbp+37h+var_90], r15
0x180105abe  mov     rax, [rcx]
0x180105ac1  mov     rax, [rax+8]
0x180105ac5  call    cs:__guard_dispatch_icall_fptr
0x180105acb  mov     rbx, [rsp+0C0h+arg_8]
0x180105ad3  add     rsp, 90h
0x180105ada  pop     r15
0x180105adc  pop     r14
0x180105ade  pop     r13
0x180105ae0  pop     r12
0x180105ae2  pop     rdi
0x180105ae3  pop     rsi
0x180105ae4  pop     rbp
0x180105ae5  retn
0x180105ae6  xor     r15d, r15d
0x180105ae9  lea     r8, [rbp+37h+var_78]
0x180105aed  mov     rdx, [rbp+37h+var_90]
0x180105af1  lea     rcx, [rbp+37h+arg_0]
0x180105af5  call    cs:__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z; ARC::IPlatformBitmapClipper::Create(ARC::IPlatformBitmap const &,Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &)
0x180105afb  mov     r14, [rax]
0x180105afe  mov     [rax], r15
0x180105b01  mov     [rbp+37h+var_40], r14
0x180105b05  mov     rcx, [rbp+37h+arg_0]
0x180105b09  test    rcx, rcx
0x180105b0c  jz      short loc_180105B1F
0x180105b0e  mov     [rbp+37h+arg_0], r15
0x180105b12  mov     rax, [rcx]
0x180105b15  mov     rax, [rax+8]
0x180105b19  call    cs:__guard_dispatch_icall_fptr
0x180105b1f  mov     [rbp+37h+var_60], ebx
0x180105b22  mov     [rbp+37h+var_5C], edi
0x180105b25  mov     [rbp+37h+arg_20], 1
0x180105b2c  lea     r9, [rbp+37h+arg_20]
0x180105b30  lea     r8, [rbp+37h+var_60]
0x180105b34  mov     rdx, r14
0x180105b37  lea     rcx, [rbp+37h+var_68]
0x180105b3b  call    cs:__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z; ARC::IPlatformBitmapScaler::Create(ARC::IPlatformBitmap const &,Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &,ARC::InterpolationMode const &)
0x180105b41  mov     rbx, [rbp+37h+var_68]
0x180105b45  mov     rcx, [rbp+37h+var_90]
0x180105b49  cmp     rcx, rbx
0x180105b4c  jz      short loc_180105B85
0x180105b4e  xchg    ax, ax
0x180105b50  test    rbx, rbx
0x180105b53  jz      short loc_180105B68
0x180105b55  mov     rax, [rbx]
0x180105b58  mov     rcx, rbx
0x180105b5b  mov     rax, [rax]
0x180105b5e  call    cs:__guard_dispatch_icall_fptr
0x180105b64  mov     rcx, [rbp+37h+var_90]
0x180105b68  test    rcx, rcx
0x180105b6b  jz      short loc_180105B7E
0x180105b6d  mov     [rbp+37h+var_90], r15
0x180105b71  mov     rax, [rcx]
0x180105b74  mov     rax, [rax+8]
0x180105b78  call    cs:__guard_dispatch_icall_fptr
0x180105b7e  mov     rcx, rbx
0x180105b81  mov     [rbp+37h+var_90], rbx
0x180105b85  test    rcx, rcx
0x180105b88  jz      short loc_180105BFC
0x180105b8a  lea     rdx, [rbp+37h+var_48]
0x180105b8e  call    ??$QueryObjectElseCrash@$$CBUIWICPlatformBitmap@WIC@ARC@@$0A@@IObjectProxy@Mso@@QEBA?AV?$TCntPtr@$$CBUIWICPlatformBitmap@WIC@ARC@@@1@XZ; Mso::IObjectProxy::QueryObjectElseCrash<ARC::WIC::IWICPlatformBitmap const,0>(void)
0x180105b93  mov     rbx, [rbp+37h+var_48]
0x180105b97  test    rbx, rbx
0x180105b9a  jnz     short loc_180105C15
0x180105b9c  xor     edx, edx
0x180105b9e  mov     ecx, 1E3C3840h
0x180105ba3  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180105ba9  nop
0x180105baa  mov     rax, [rcx]
0x180105bad  mov     edx, 1
0x180105bb2  mov     rax, [rax]
0x180105bb5  call    cs:__guard_dispatch_icall_fptr
0x180105bbb  jmp     loc_180105A45
0x180105bc0  mov     rdi, qword ptr [rbp+37h+var_78+8]
0x180105bc4  mov     r9, qword ptr [rbp+37h+var_78]
0x180105bc8  cmp     ecx, edx
0x180105bca  ja      short loc_180105C0A
0x180105bcc  mov     r8, rdi
0x180105bcf  shr     r8, 20h
0x180105bd3  mov     rax, r9
0x180105bd6  shr     rax, 20h
0x180105bda  cmp     eax, r8d
0x180105bdd  ja      short loc_180105C0A
0x180105bdf  mov     ebx, edx
0x180105be1  sub     ebx, ecx
0x180105be3  cmp     ecx, edx
0x180105be5  ja      short loc_180105C0E
0x180105be7  shr     r9, 20h
0x180105beb  shr     rdi, 20h
0x180105bef  cmp     r9d, edi
0x180105bf2  ja      short loc_180105C0E
0x180105bf4  sub     edi, r9d
0x180105bf7  jmp     loc_180105A8A
0x180105bfc  xor     edx, edx
0x180105bfe  mov     ecx, 1E3C3840h
0x180105c03  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180105c09  nop
0x180105c0a  xor     ebx, ebx
0x180105c0c  jmp     short loc_180105BE3
0x180105c0e  xor     edi, edi
0x180105c10  jmp     loc_180105A8A
0x180105c15  mov     rax, [rbx]
0x180105c18  mov     rcx, rbx
0x180105c1b  mov     rax, [rax+90h]
0x180105c22  call    cs:__guard_dispatch_icall_fptr
0x180105c28  mov     rsi, rax
0x180105c2b  mov     rdi, rax
0x180105c2e  mov     [rbp+37h+var_58], rax
0x180105c32  test    rax, rax
0x180105c35  jz      short loc_180105C48
0x180105c37  mov     rax, [rax]
0x180105c3a  mov     rcx, rdi
0x180105c3d  mov     rax, [rax+8]
0x180105c41  call    cs:__guard_dispatch_icall_fptr
0x180105c47  nop
0x180105c48  lea     rcx, [rbp+37h+var_88]
0x180105c4c  call    cs:__imp_?GetWICImagingFactory@WIC@ARC@@YA?AV?$TCntPtr@UIWICImagingFactory@@@Mso@@XZ; ARC::WIC::GetWICImagingFactory(void)
0x180105c52  cmp     [rbp+37h+arg_18], r15b
0x180105c56  jnz     short loc_180105CC1
0x180105c58  mov     r8, [rbp+37h+arg_10]
0x180105c5c  mov     r9, rsi
0x180105c5f  mov     rdx, [rbp+37h+var_88]
0x180105c63  lea     rcx, [rbp+37h+arg_0]
0x180105c67  call    cs:__imp_?ConvertFrameToValidPixelFormat@WIC@ARC@@YA?AV?$TCntPtr@UIWICBitmapSource@@@Mso@@AEAUIWICImagingFactory@@AEBU_GUID@@AEAUIWICBitmapSource@@@Z; ARC::WIC::ConvertFrameToValidPixelFormat(IWICImagingFactory &,_GUID const &,IWICBitmapSource &)
0x180105c6d  mov     rdi, [rax]
0x180105c70  test    rsi, rsi
0x180105c73  mov     [rbp+37h+var_58], rdi
0x180105c77  mov     [rax], r15
0x180105c7a  jz      short loc_180105C8C
0x180105c7c  mov     rax, [rsi]
0x180105c7f  mov     rcx, rsi
0x180105c82  mov     rax, [rax+10h]
0x180105c86  call    cs:__guard_dispatch_icall_fptr
0x180105c8c  mov     rcx, [rbp+37h+arg_0]
0x180105c90  test    rcx, rcx
0x180105c93  jz      short loc_180105CA6
0x180105c95  mov     [rbp+37h+arg_0], r15
0x180105c99  mov     rax, [rcx]
0x180105c9c  mov     rax, [rax+10h]
0x180105ca0  call    cs:__guard_dispatch_icall_fptr
0x180105ca6  mov     [rbp+37h+var_80], r15
0x180105caa  mov     rcx, [rbp+37h+var_88]
0x180105cae  test    rcx, rcx
0x180105cb1  jnz     short loc_180105CD2
0x180105cb3  xor     edx, edx
0x180105cb5  mov     ecx, 1E3C3840h
0x180105cba  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180105cc0  nop
0x180105cc1  mov     rcx, r12; this
0x180105cc4  call    ?IsIndexedPixelFormat@WIC@ARC@@YA_NAEBU_GUID@@@Z; ARC::WIC::IsIndexedPixelFormat(_GUID const &)
0x180105cc9  test    al, al
0x180105ccb  jz      short loc_180105CA6
0x180105ccd  mov     r8, r12
0x180105cd0  jmp     short loc_180105C5C
0x180105cd2  mov     rax, [rcx]
0x180105cd5  lea     r9, [rbp+37h+var_80]
0x180105cd9  mov     r12d, 1
0x180105cdf  mov     r8d, r12d
0x180105ce2  mov     rdx, rdi
0x180105ce5  mov     rax, [rax+90h]
0x180105cec  call    cs:__guard_dispatch_icall_fptr
0x180105cf2  test    eax, eax
0x180105cf4  js      loc_180105EA2
0x180105cfa  mov     rcx, [rbp+37h+var_80]
0x180105cfe  mov     rax, [rcx]
0x180105d01  mov     rdx, [rbp+37h+arg_40]
0x180105d08  movd    xmm2, dword ptr [rdx+4]
0x180105d0d  cvtdq2pd xmm2, xmm2
0x180105d11  movd    xmm1, dword ptr [rdx]
0x180105d15  cvtdq2pd xmm1, xmm1
0x180105d19  mov     rax, [rax+50h]
0x180105d1d  call    cs:__guard_dispatch_icall_fptr
0x180105d23  test    eax, eax
0x180105d25  js      loc_180105EAF
0x180105d2b  mov     ecx, 98h; this
0x180105d30  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x180105d35  mov     rsi, rax
0x180105d38  mov     [rbp+37h+var_38], rax
0x180105d3c  test    rax, rax
0x180105d3f  jnz     loc_180105E29
0x180105d45  mov     rax, r15
0x180105d48  mov     rdx, rax
0x180105d4b  mov     rcx, [rbp+37h+arg_50]
0x180105d52  call    ?Attach@?$TOwnerPtr@UIImageResource@GEL@@@Ofc@@QEAAXPEAUIImageResource@GEL@@@Z; Ofc::TOwnerPtr<GEL::IImageResource>::Attach(GEL::IImageResource *)
0x180105d57  test    r12b, r13b
0x180105d5a  jnz     loc_180105E5D
0x180105d60  mov     rcx, [rbp+37h+var_80]
0x180105d64  test    rcx, rcx
0x180105d67  jz      short loc_180105D77
0x180105d69  mov     rax, [rcx]
0x180105d6c  mov     rax, [rax+10h]
0x180105d70  call    cs:__guard_dispatch_icall_fptr
0x180105d76  nop
0x180105d77  mov     rcx, [rbp+37h+var_88]
0x180105d7b  test    rcx, rcx
0x180105d7e  jz      short loc_180105D92
0x180105d80  mov     [rbp+37h+var_88], r15
0x180105d84  mov     rax, [rcx]
0x180105d87  mov     rax, [rax+10h]
0x180105d8b  call    cs:__guard_dispatch_icall_fptr
0x180105d91  nop
0x180105d92  test    rdi, rdi
0x180105d95  jz      short loc_180105DA8
0x180105d97  mov     rax, [rdi]
0x180105d9a  mov     rcx, rdi
0x180105d9d  mov     rax, [rax+10h]
0x180105da1  call    cs:__guard_dispatch_icall_fptr
0x180105da7  nop
0x180105da8  mov     rax, [rbx]
0x180105dab  mov     rax, [rax+8]
0x180105daf  lea     rcx, ?Release@?$TRefCountedImpl@UIImage@GEL@@@Mso@@UEBAXXZ; Mso::TRefCountedImpl<GEL::IImage>::Release(void)
0x180105db6  cmp     rax, rcx
0x180105db9  jz      short loc_180105DD1
0x180105dbb  lea     rcx, ?Release@?$TRefCountedImpl@UIPath@GEL@@@Mso@@UEBAXXZ; Mso::TRefCountedImpl<GEL::IPath>::Release(void)
0x180105dc2  cmp     rax, rcx
0x180105dc5  jnz     short loc_180105E13
0x180105dc7  mov     rcx, rbx
0x180105dca  call    ?Release@?$TRefCountedImpl@UIPath@GEL@@@Mso@@UEBAXXZ; Mso::TRefCountedImpl<GEL::IPath>::Release(void)
0x180105dcf  jmp     short loc_180105DDA
0x180105dd1  mov     rcx, rbx
0x180105dd4  call    ?Release@?$TRefCountedImpl@UIImage@GEL@@@Mso@@UEBAXXZ; Mso::TRefCountedImpl<GEL::IImage>::Release(void)
0x180105dd9  nop
0x180105dda  mov     rcx, [rbp+37h+var_68]
0x180105dde  test    rcx, rcx
0x180105de1  jz      short loc_180105DF5
0x180105de3  mov     [rbp+37h+var_68], r15
0x180105de7  mov     rax, [rcx]
0x180105dea  mov     rax, [rax+8]
0x180105dee  call    cs:__guard_dispatch_icall_fptr
0x180105df4  nop
0x180105df5  test    r14, r14
0x180105df8  jz      loc_180105AB1
0x180105dfe  mov     rax, [r14]
0x180105e01  mov     rcx, r14
0x180105e04  mov     rax, [rax+8]
0x180105e08  call    cs:__guard_dispatch_icall_fptr
0x180105e0e  jmp     loc_180105AB1
0x180105e13  lea     rcx, ?Release@?$TRefCountedImpl@UIRefCounted@Mso@@@Mso@@UEBAXXZ; Mso::TRefCountedImpl<Mso::IRefCounted>::Release(void)
0x180105e1a  cmp     rax, rcx
0x180105e1d  mov     rcx, rbx
0x180105e20  jnz     short loc_180105E80
0x180105e22  call    ?Release@?$TRefCountedImpl@UIRefCounted@Mso@@@Mso@@UEBAXXZ; Mso::TRefCountedImpl<Mso::IRefCounted>::Release(void)
0x180105e27  jmp     short loc_180105DDA
0x180105e29  lea     r9, GUID_WICPixelFormatDontCare
0x180105e30  mov     r8d, [rbp+37h+arg_48]
  ... truncated ...
```
