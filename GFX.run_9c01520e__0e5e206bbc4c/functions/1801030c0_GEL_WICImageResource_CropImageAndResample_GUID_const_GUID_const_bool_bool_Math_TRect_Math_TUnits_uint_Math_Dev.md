# GEL::WICImageResource::CropImageAndResample(_GUID const &,_GUID const &,bool,bool,Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &,bool,Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &,Math::TVector2<Math::TUnits<int,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>> const &,GEL::ImageFormat,Ofc::TOwnerPtr<GEL::IImageResource> &)

- ea: `0x1801030c0`
- end: `0x180103584`
- name: `?CropImageAndResample@WICImageResource@GEL@@AEBAXAEBU_GUID@@0_N1AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@1AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@5@AEBU?$TVector2@V?$TUnits@HU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@5@W4ImageFormat@2@AEAV?$TOwnerPtr@UIImageResource@GEL@@@Ofc@@@Z`
- size: `1220`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180102ad0`

## callees

- `0x180018b80`
- `0x180019f20`
- `0x180020b90`
- `0x18004ee80`
- `0x180057e70`
- `0x1800888d0`
- `0x180092a58`
- `0x1800dcec0`
- `0x1800e0238`
- `0x1801030c0`
- `0x180103584`
- `0x180103f40`

## import_xrefs

- `mso40uiWin32Client!__imp_?ConvertFrameToValidPixelFormat@WIC@ARC@@YA?AV?$TCntPtr@UIWICBitmapSource@@@Mso@@AEAUIWICImagingFactory@@AEBU_GUID@@AEAUIWICBitmapSource@@@Z` at `0x180103327`
- `mso40uiWin32Client!__imp_?ConvertFrameToValidPixelFormat@WIC@ARC@@YA?AV?$TCntPtr@UIWICBitmapSource@@@Mso@@AEAUIWICImagingFactory@@AEBU_GUID@@AEAUIWICBitmapSource@@@Z` at `0x180103327`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x1801031b5`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x1801031b5`
- `mso40uiWin32Client!__imp_?GetWICImagingFactory@WIC@ARC@@YA?AV?$TCntPtr@UIWICImagingFactory@@@Mso@@XZ` at `0x18010330c`
- `mso40uiWin32Client!__imp_?GetWICImagingFactory@WIC@ARC@@YA?AV?$TCntPtr@UIWICImagingFactory@@@Mso@@XZ` at `0x18010330c`
- `mso40uiWin32Client!__imp_?Create@IWICPlatformBitmap@WIC@ARC@@SA?AV?$TCntPtr@UIWICPlatformBitmap@WIC@ARC@@@Mso@@AEBUIWICBitmapSource@@W4ImageFormat@3@AEBU_GUID@@@Z` at `0x180103503`
- `mso40uiWin32Client!__imp_?Create@IWICPlatformBitmap@WIC@ARC@@SA?AV?$TCntPtr@UIWICPlatformBitmap@WIC@ARC@@@Mso@@AEBUIWICBitmapSource@@W4ImageFormat@3@AEBU_GUID@@@Z` at `0x180103503`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z` at `0x1801031fb`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z` at `0x1801031fb`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180103251`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801032ce`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010337a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180103251`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1801032ce`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010337a`

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
        _QWORD *a11)
{
  char v13; // r13
  _QWORD *v14; // rbx
  void (__fastcall ***v15)(_QWORD, __int64); // rcx
  unsigned int *Size; // rax
  unsigned int v17; // ecx
  unsigned int v18; // edx
  char v19; // r15
  char v20; // si
  int v21; // ebx
  int v22; // edi
  __int64 result; // rax
  void (__fastcall ***v24)(_QWORD); // rcx
  __int64 *v25; // rax
  __int64 v26; // rcx
  _QWORD *v27; // rcx
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rsi
  __int64 v31; // rdi
  const struct _GUID *v32; // rdx
  ARC::WIC *v33; // r8
  __int64 *valid; // rax
  __int64 v35; // rcx
  int v36; // eax
  int v37; // eax
  unsigned __int64 v38; // rdx
  unsigned int v39; // r8d
  GEL::WICImageResource *v40; // rsi
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 (__fastcall *v43)(__int64); // rax
  void (__fastcall ***v44)(_QWORD); // rcx
  __int64 v45; // rcx
  struct ARC::IPlatformBitmap **v46; // rax
  __int64 v47; // rcx
  void (__fastcall ***v48)(_QWORD); // [rsp+38h] [rbp-59h] BYREF
  __int64 v49; // [rsp+40h] [rbp-51h] BYREF
  __int64 v50; // [rsp+48h] [rbp-49h] BYREF
  __int128 v51; // [rsp+50h] [rbp-41h] BYREF
  void (__fastcall ***v52)(_QWORD); // [rsp+60h] [rbp-31h] BYREF
  _DWORD v53[2]; // [rsp+68h] [rbp-29h] BYREF
  __int64 v54; // [rsp+70h] [rbp-21h]
  __int64 v55; // [rsp+78h] [rbp-19h] BYREF
  _QWORD v56[9]; // [rsp+80h] [rbp-11h] BYREF
  __int64 v57; // [rsp+D8h] [rbp+47h] BYREF
  ARC::WIC *v58; // [rsp+E8h] [rbp+57h]
  char v59; // [rsp+F0h] [rbp+5Fh]

  v59 = a4;
  v58 = a3;
  v13 = 0;
  LODWORD(v57) = 0;
  v14 = a11;
  v15 = (void (__fastcall ***)(_QWORD, __int64))*a11;
  if ( *a11 )
    goto LABEL_21;
  while ( 1 )
  {
    *v14 = 0;
    Size = (unsigned int *)GEL::RasterImageResource::GetSize(a1, &v57);
    v17 = 0;
    *(_QWORD *)&v51 = 0;
    v18 = *Size;
    *((_QWORD *)&v51 + 1) = *(_QWORD *)Size;
    v19 = a5;
    if ( (_BYTE)a5 )
    {
      v51 = *a6;
      v18 = DWORD2(v51);
      v17 = v51;
    }
    v20 = a7;
    if ( a7 )
    {
      v21 = *a8;
      v22 = a8[1];
    }
    else
    {
      v21 = v17 > v18 || DWORD1(v51) > HIDWORD(v51) ? 0 : v18 - v17;
      v22 = v17 > v18 || DWORD1(v51) > HIDWORD(v51) ? 0 : HIDWORD(v51) - DWORD1(v51);
    }
    result = (*(__int64 (__fastcall **)(__int64, void (__fastcall ****)(_QWORD), _QWORD))(*(_QWORD *)a1 + 336LL))(
               a1,
               &v48,
               0);
    if ( !v19 && !v20 )
      break;
    v25 = (__int64 *)ARC::IPlatformBitmapClipper::Create(&v57, v48, &v51);
    a1 = *v25;
    *v25 = 0;
    v56[1] = a1;
    v26 = v57;
    if ( v57 )
    {
      v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
    }
    v53[0] = v21;
    v53[1] = v22;
    a5 = 1;
    ARC::IPlatformBitmapScaler::Create(&v52, a1, v53, &a5);
    v14 = v52;
    v27 = v48;
    if ( v48 != v52 )
    {
      if ( v52 )
      {
        (**v52)(v52);
        v27 = v48;
      }
      if ( v27 )
      {
        v48 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v27 + 8LL))(v27);
      }
      v27 = v14;
      v48 = (void (__fastcall ***)(_QWORD))v14;
    }
    if ( v27 )
    {
      Mso::IObjectProxy::QueryObjectElseCrash<ARC::WIC::IWICPlatformBitmap const,0>(v27, v56);
      v28 = v56[0];
      if ( !v56[0] )
        CrashWithRecovery(0x1E3C3840u, 0);
      v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 144LL))(v28);
      v30 = v29;
      v31 = v29;
      v54 = v29;
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
      ARC::WIC::GetWICImagingFactory(&v49);
      if ( v59 )
        goto LABEL_42;
      v33 = v58;
LABEL_36:
      valid = (__int64 *)ARC::WIC::ConvertFrameToValidPixelFormat(&v57, v49, v33, v30);
      v31 = *valid;
      v54 = *valid;
      *valid = 0;
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      v35 = v57;
      if ( v57 )
      {
        v57 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      }
      while ( 1 )
      {
        v50 = 0;
        if ( v49 )
          break;
        CrashWithRecovery(0x1E3C3840u, 0);
LABEL_42:
        if ( ARC::WIC::IsIndexedPixelFormat(a2, v32) )
        {
          v33 = a2;
          goto LABEL_36;
        }
      }
      v36 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v49 + 144LL))(
              v49,
              v31,
              1,
              &v50);
      if ( v36 < 0 )
      {
        Ofc::CHResultException::ThrowTag(v36, 0x129635Bu);
        __debugbreak();
      }
      v37 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 80LL))(v50);
      if ( v37 < 0 )
      {
        Ofc::CHResultException::ThrowTag(v37, 0x129635Cu);
      }
      else
      {
        v40 = (GEL::WICImageResource *)Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x98, v38, v39);
        v56[2] = v40;
        if ( v40 )
        {
          v46 = (struct ARC::IPlatformBitmap **)ARC::WIC::IWICPlatformBitmap::Create(
                                                  &v55,
                                                  v50,
                                                  a10,
                                                  &GUID_WICPixelFormatDontCare);
          v13 = 1;
          LODWORD(v57) = 1;
          v41 = GEL::WICImageResource::WICImageResource(v40, *v46);
        }
        else
        {
          v41 = 0;
        }
        Ofc::TOwnerPtr<GEL::IImageResource>::Attach(a11, v41);
        if ( (v13 & 1) != 0 )
        {
          v47 = v55;
          if ( v55 )
          {
            v55 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 8LL))(v47);
          }
        }
        if ( v50 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
        v42 = v49;
        if ( v49 )
        {
          v49 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        }
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        v43 = *(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL);
        if ( v43 == Mso::TRefCountedImpl<GEL::IImage>::Release )
        {
          result = Mso::TRefCountedImpl<GEL::IImage>::Release(v28);
          goto LABEL_59;
        }
        if ( v43 == Mso::TRefCountedImpl<GEL::IPath>::Release )
        {
          result = Mso::TRefCountedImpl<GEL::IPath>::Release(v28);
LABEL_59:
          v44 = v52;
          if ( v52 )
          {
            v52 = 0;
            result = ((__int64 (__fastcall *)(_QWORD))(*v44)[1])(v44);
          }
          if ( a1 )
            result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
          break;
        }
        v45 = v28;
        if ( v43 == Mso::TRefCountedImpl<Mso::IRefCounted>::Release )
        {
          result = Mso::TRefCountedImpl<Mso::IRefCounted>::Release(v28);
          goto LABEL_59;
        }
      }
      result = v43(v45);
      goto LABEL_59;
    }
    CrashWithRecovery(0x1E3C3840u, 0);
LABEL_21:
    (**v15)(v15, 1);
  }
  v24 = v48;
  if ( v48 )
  {
    v48 = 0;
    return ((__int64 (__fastcall *)(_QWORD))(*v24)[1])(v24);
  }
  return result;
}

```

## disassembly

```asm
0x1801030c0  mov     rax, rsp
0x1801030c3  mov     [rax+10h], rbx
0x1801030c7  mov     [rax+20h], r9b
0x1801030cb  mov     [rax+18h], r8
0x1801030cf  push    rbp
0x1801030d0  push    rsi
0x1801030d1  push    rdi
0x1801030d2  push    r12
0x1801030d4  push    r13
0x1801030d6  push    r14
0x1801030d8  push    r15
0x1801030da  lea     rbp, [rax-3Fh]
0x1801030de  sub     rsp, 90h
0x1801030e5  mov     r12, rdx
0x1801030e8  mov     r14, rcx
0x1801030eb  xor     r13d, r13d
0x1801030ee  mov     dword ptr [rbp+37h+arg_0], r13d
0x1801030f2  mov     rbx, [rbp+37h+arg_50]
0x1801030f9  mov     rcx, [rbx]
0x1801030fc  test    rcx, rcx
0x1801030ff  jnz     loc_180103258
0x180103105  mov     [rbx], r13
0x180103108  lea     rdx, [rbp+37h+arg_0]
0x18010310c  mov     rcx, r14
0x18010310f  call    ?GetSize@RasterImageResource@GEL@@UEBA?AU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@XZ; GEL::RasterImageResource::GetSize(void)
0x180103114  xor     ecx, ecx
0x180103116  mov     dword ptr [rbp+37h+var_78], ecx
0x180103119  mov     dword ptr [rbp+37h+var_78+4], ecx
0x18010311c  mov     edx, [rax]
0x18010311e  mov     dword ptr [rbp+37h+var_78+8], edx
0x180103121  mov     eax, [rax+4]
0x180103124  mov     dword ptr [rbp+37h+var_78+0Ch], eax
0x180103127  mov     r15b, byte ptr [rbp+37h+arg_20]
0x18010312b  test    r15b, r15b
0x18010312e  jnz     loc_180103544
0x180103134  mov     sil, [rbp+37h+arg_30]
0x180103138  test    sil, sil
0x18010313b  jz      loc_18010326E
0x180103141  mov     rax, [rbp+37h+arg_38]
0x180103145  mov     ebx, [rax]
0x180103147  mov     edi, [rax+4]
0x18010314a  mov     rax, [r14]
0x18010314d  xor     r8d, r8d
0x180103150  lea     rdx, [rbp+37h+var_90]
0x180103154  mov     rcx, r14
0x180103157  mov     rax, [rax+150h]
0x18010315e  call    cs:__guard_dispatch_icall_fptr
0x180103164  test    r15b, r15b
0x180103167  jnz     short loc_1801031A6
0x180103169  xor     r15d, r15d
0x18010316c  test    sil, sil
0x18010316f  jnz     short loc_1801031A9
0x180103171  mov     rcx, [rbp+37h+var_90]
0x180103175  test    rcx, rcx
0x180103178  jz      short loc_18010318B
0x18010317a  mov     [rbp+37h+var_90], r15
0x18010317e  mov     rax, [rcx]
0x180103181  mov     rax, [rax+8]
0x180103185  call    cs:__guard_dispatch_icall_fptr
0x18010318b  mov     rbx, [rsp+0C0h+arg_8]
0x180103193  add     rsp, 90h
0x18010319a  pop     r15
0x18010319c  pop     r14
0x18010319e  pop     r13
0x1801031a0  pop     r12
0x1801031a2  pop     rdi
0x1801031a3  pop     rsi
0x1801031a4  pop     rbp
0x1801031a5  retn
0x1801031a6  xor     r15d, r15d
0x1801031a9  lea     r8, [rbp+37h+var_78]
0x1801031ad  mov     rdx, [rbp+37h+var_90]
0x1801031b1  lea     rcx, [rbp+37h+arg_0]
0x1801031b5  call    cs:__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z; ARC::IPlatformBitmapClipper::Create(ARC::IPlatformBitmap const &,Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &)
0x1801031bb  mov     r14, [rax]
0x1801031be  mov     [rax], r15
0x1801031c1  mov     [rbp+37h+var_40], r14
0x1801031c5  mov     rcx, [rbp+37h+arg_0]
0x1801031c9  test    rcx, rcx
0x1801031cc  jz      short loc_1801031DF
0x1801031ce  mov     [rbp+37h+arg_0], r15
0x1801031d2  mov     rax, [rcx]
0x1801031d5  mov     rax, [rax+8]
0x1801031d9  call    cs:__guard_dispatch_icall_fptr
0x1801031df  mov     [rbp+37h+var_60], ebx
0x1801031e2  mov     [rbp+37h+var_5C], edi
0x1801031e5  mov     [rbp+37h+arg_20], 1
0x1801031ec  lea     r9, [rbp+37h+arg_20]
0x1801031f0  lea     r8, [rbp+37h+var_60]
0x1801031f4  mov     rdx, r14
0x1801031f7  lea     rcx, [rbp+37h+var_68]
0x1801031fb  call    cs:__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z; ARC::IPlatformBitmapScaler::Create(ARC::IPlatformBitmap const &,Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &,ARC::InterpolationMode const &)
0x180103201  mov     rbx, [rbp+37h+var_68]
0x180103205  mov     rcx, [rbp+37h+var_90]
0x180103209  cmp     rcx, rbx
0x18010320c  jz      short loc_180103245
0x18010320e  xchg    ax, ax
0x180103210  test    rbx, rbx
0x180103213  jz      short loc_180103228
0x180103215  mov     rax, [rbx]
0x180103218  mov     rcx, rbx
0x18010321b  mov     rax, [rax]
0x18010321e  call    cs:__guard_dispatch_icall_fptr
0x180103224  mov     rcx, [rbp+37h+var_90]
0x180103228  test    rcx, rcx
0x18010322b  jz      short loc_18010323E
0x18010322d  mov     [rbp+37h+var_90], r15
0x180103231  mov     rax, [rcx]
0x180103234  mov     rax, [rax+8]
0x180103238  call    cs:__guard_dispatch_icall_fptr
0x18010323e  mov     rcx, rbx
0x180103241  mov     [rbp+37h+var_90], rbx
0x180103245  test    rcx, rcx
0x180103248  jnz     short loc_1801032B5
0x18010324a  xor     edx, edx
0x18010324c  mov     ecx, 1E3C3840h
0x180103251  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180103257  nop
0x180103258  mov     rax, [rcx]
0x18010325b  mov     edx, 1
0x180103260  mov     rax, [rax]
0x180103263  call    cs:__guard_dispatch_icall_fptr
0x180103269  jmp     loc_180103105
0x18010326e  mov     rdi, qword ptr [rbp+37h+var_78+8]
0x180103272  mov     r9, qword ptr [rbp+37h+var_78]
0x180103276  cmp     ecx, edx
0x180103278  ja      short loc_1801032AA
0x18010327a  mov     r8, rdi
0x18010327d  shr     r8, 20h
0x180103281  mov     rax, r9
0x180103284  shr     rax, 20h
0x180103288  cmp     eax, r8d
0x18010328b  ja      short loc_1801032AA
0x18010328d  mov     ebx, edx
0x18010328f  sub     ebx, ecx
0x180103291  cmp     ecx, edx
0x180103293  ja      short loc_1801032AE
0x180103295  shr     r9, 20h
0x180103299  shr     rdi, 20h
0x18010329d  cmp     r9d, edi
0x1801032a0  ja      short loc_1801032AE
0x1801032a2  sub     edi, r9d
0x1801032a5  jmp     loc_18010314A
0x1801032aa  xor     ebx, ebx
0x1801032ac  jmp     short loc_180103291
0x1801032ae  xor     edi, edi
0x1801032b0  jmp     loc_18010314A
0x1801032b5  lea     rdx, [rbp+37h+var_48]
0x1801032b9  call    ??$QueryObjectElseCrash@$$CBUIWICPlatformBitmap@WIC@ARC@@$0A@@IObjectProxy@Mso@@QEBA?AV?$TCntPtr@$$CBUIWICPlatformBitmap@WIC@ARC@@@1@XZ; Mso::IObjectProxy::QueryObjectElseCrash<ARC::WIC::IWICPlatformBitmap const,0>(void)
0x1801032be  mov     rbx, [rbp+37h+var_48]
0x1801032c2  test    rbx, rbx
0x1801032c5  jnz     short loc_1801032D5
0x1801032c7  xor     edx, edx
0x1801032c9  mov     ecx, 1E3C3840h
0x1801032ce  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1801032d4  nop
0x1801032d5  mov     rax, [rbx]
0x1801032d8  mov     rcx, rbx
0x1801032db  mov     rax, [rax+90h]
0x1801032e2  call    cs:__guard_dispatch_icall_fptr
0x1801032e8  mov     rsi, rax
0x1801032eb  mov     rdi, rax
0x1801032ee  mov     [rbp+37h+var_58], rax
0x1801032f2  test    rax, rax
0x1801032f5  jz      short loc_180103308
0x1801032f7  mov     rax, [rax]
0x1801032fa  mov     rcx, rdi
0x1801032fd  mov     rax, [rax+8]
0x180103301  call    cs:__guard_dispatch_icall_fptr
0x180103307  nop
0x180103308  lea     rcx, [rbp+37h+var_88]
0x18010330c  call    cs:__imp_?GetWICImagingFactory@WIC@ARC@@YA?AV?$TCntPtr@UIWICImagingFactory@@@Mso@@XZ; ARC::WIC::GetWICImagingFactory(void)
0x180103312  cmp     [rbp+37h+arg_18], r15b
0x180103316  jnz     short loc_180103381
0x180103318  mov     r8, [rbp+37h+arg_10]
0x18010331c  mov     r9, rsi
0x18010331f  mov     rdx, [rbp+37h+var_88]
0x180103323  lea     rcx, [rbp+37h+arg_0]
0x180103327  call    cs:__imp_?ConvertFrameToValidPixelFormat@WIC@ARC@@YA?AV?$TCntPtr@UIWICBitmapSource@@@Mso@@AEAUIWICImagingFactory@@AEBU_GUID@@AEAUIWICBitmapSource@@@Z; ARC::WIC::ConvertFrameToValidPixelFormat(IWICImagingFactory &,_GUID const &,IWICBitmapSource &)
0x18010332d  mov     rdi, [rax]
0x180103330  test    rsi, rsi
0x180103333  mov     [rbp+37h+var_58], rdi
0x180103337  mov     [rax], r15
0x18010333a  jz      short loc_18010334C
0x18010333c  mov     rax, [rsi]
0x18010333f  mov     rcx, rsi
0x180103342  mov     rax, [rax+10h]
0x180103346  call    cs:__guard_dispatch_icall_fptr
0x18010334c  mov     rcx, [rbp+37h+arg_0]
0x180103350  test    rcx, rcx
0x180103353  jz      short loc_180103366
0x180103355  mov     [rbp+37h+arg_0], r15
0x180103359  mov     rax, [rcx]
0x18010335c  mov     rax, [rax+10h]
0x180103360  call    cs:__guard_dispatch_icall_fptr
0x180103366  mov     [rbp+37h+var_80], r15
0x18010336a  mov     rcx, [rbp+37h+var_88]
0x18010336e  test    rcx, rcx
0x180103371  jnz     short loc_180103392
0x180103373  xor     edx, edx
0x180103375  mov     ecx, 1E3C3840h
0x18010337a  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180103380  nop
0x180103381  mov     rcx, r12; this
0x180103384  call    ?IsIndexedPixelFormat@WIC@ARC@@YA_NAEBU_GUID@@@Z; ARC::WIC::IsIndexedPixelFormat(_GUID const &)
0x180103389  test    al, al
0x18010338b  jz      short loc_180103366
0x18010338d  mov     r8, r12
0x180103390  jmp     short loc_18010331C
0x180103392  mov     rax, [rcx]
0x180103395  lea     r9, [rbp+37h+var_80]
0x180103399  mov     r12d, 1
0x18010339f  mov     r8d, r12d
0x1801033a2  mov     rdx, rdi
0x1801033a5  mov     rax, [rax+90h]
0x1801033ac  call    cs:__guard_dispatch_icall_fptr
0x1801033b2  test    eax, eax
0x1801033b4  js      loc_18010355B
0x1801033ba  mov     rcx, [rbp+37h+var_80]
0x1801033be  mov     rax, [rcx]
0x1801033c1  mov     rdx, [rbp+37h+arg_40]
0x1801033c8  movd    xmm2, dword ptr [rdx+4]
0x1801033cd  cvtdq2pd xmm2, xmm2
0x1801033d1  movd    xmm1, dword ptr [rdx]
0x1801033d5  cvtdq2pd xmm1, xmm1
0x1801033d9  mov     rax, [rax+50h]
0x1801033dd  call    cs:__guard_dispatch_icall_fptr
0x1801033e3  test    eax, eax
0x1801033e5  js      loc_180103568
0x1801033eb  mov     ecx, 98h; this
0x1801033f0  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1801033f5  mov     rsi, rax
0x1801033f8  mov     [rbp+37h+var_38], rax
0x1801033fc  test    rax, rax
0x1801033ff  jnz     loc_1801034ED
0x180103405  mov     rax, r15
0x180103408  mov     rdx, rax
0x18010340b  mov     rcx, [rbp+37h+arg_50]
0x180103412  call    ?Attach@?$TOwnerPtr@UIImageResource@GEL@@@Ofc@@QEAAXPEAUIImageResource@GEL@@@Z; Ofc::TOwnerPtr<GEL::IImageResource>::Attach(GEL::IImageResource *)
0x180103417  test    r12b, r13b
0x18010341a  jnz     loc_180103521
0x180103420  mov     rcx, [rbp+37h+var_80]
0x180103424  test    rcx, rcx
0x180103427  jz      short loc_180103437
0x180103429  mov     rax, [rcx]
0x18010342c  mov     rax, [rax+10h]
0x180103430  call    cs:__guard_dispatch_icall_fptr
0x180103436  nop
0x180103437  mov     rcx, [rbp+37h+var_88]
0x18010343b  test    rcx, rcx
0x18010343e  jz      short loc_180103452
0x180103440  mov     [rbp+37h+var_88], r15
0x180103444  mov     rax, [rcx]
0x180103447  mov     rax, [rax+10h]
0x18010344b  call    cs:__guard_dispatch_icall_fptr
0x180103451  nop
0x180103452  test    rdi, rdi
0x180103455  jz      short loc_180103468
0x180103457  mov     rax, [rdi]
0x18010345a  mov     rcx, rdi
0x18010345d  mov     rax, [rax+10h]
0x180103461  call    cs:__guard_dispatch_icall_fptr
0x180103467  nop
0x180103468  mov     rax, [rbx]
0x18010346b  mov     rax, [rax+8]
0x18010346f  lea     rcx, ?Release@?$TRefCountedImpl@UIImage@GEL@@@Mso@@UEBAXXZ; Mso::TRefCountedImpl<GEL::IImage>::Release(void)
0x180103476  cmp     rax, rcx
0x180103479  jz      short loc_180103491
0x18010347b  lea     rcx, ?Release@?$TRefCountedImpl@UIPath@GEL@@@Mso@@UEBAXXZ; Mso::TRefCountedImpl<GEL::IPath>::Release(void)
0x180103482  cmp     rax, rcx
0x180103485  jnz     short loc_1801034D3
0x180103487  mov     rcx, rbx
0x18010348a  call    ?Release@?$TRefCountedImpl@UIPath@GEL@@@Mso@@UEBAXXZ; Mso::TRefCountedImpl<GEL::IPath>::Release(void)
0x18010348f  jmp     short loc_18010349A
0x180103491  mov     rcx, rbx
0x180103494  call    ?Release@?$TRefCountedImpl@UIImage@GEL@@@Mso@@UEBAXXZ; Mso::TRefCountedImpl<GEL::IImage>::Release(void)
0x180103499  nop
0x18010349a  mov     rcx, [rbp+37h+var_68]
0x18010349e  test    rcx, rcx
0x1801034a1  jz      short loc_1801034B5
0x1801034a3  mov     [rbp+37h+var_68], r15
0x1801034a7  mov     rax, [rcx]
0x1801034aa  mov     rax, [rax+8]
0x1801034ae  call    cs:__guard_dispatch_icall_fptr
0x1801034b4  nop
0x1801034b5  test    r14, r14
0x1801034b8  jz      loc_180103171
0x1801034be  mov     rax, [r14]
0x1801034c1  mov     rcx, r14
0x1801034c4  mov     rax, [rax+8]
0x1801034c8  call    cs:__guard_dispatch_icall_fptr
0x1801034ce  jmp     loc_180103171
0x1801034d3  lea     rcx, ?Release@?$TRefCountedImpl@UIRefCounted@Mso@@@Mso@@UEBAXXZ; Mso::TRefCountedImpl<Mso::IRefCounted>::Release(void)
0x1801034da  cmp     rax, rcx
0x1801034dd  mov     rcx, rbx
0x1801034e0  jnz     loc_180103578
0x1801034e6  call    ?Release@?$TRefCountedImpl@UIRefCounted@Mso@@@Mso@@UEBAXXZ; Mso::TRefCountedImpl<Mso::IRefCounted>::Release(void)
0x1801034eb  jmp     short loc_18010349A
0x1801034ed  lea     r9, GUID_WICPixelFormatDontCare
0x1801034f4  mov     r8d, [rbp+37h+arg_48]
  ... truncated ...
```
