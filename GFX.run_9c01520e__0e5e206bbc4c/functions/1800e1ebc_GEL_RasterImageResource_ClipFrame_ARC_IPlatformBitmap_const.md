# GEL::RasterImageResource::ClipFrame(ARC::IPlatformBitmap const &)

- ea: `0x1800e1ebc`
- end: `0x1800e2308`
- name: `?ClipFrame@RasterImageResource@GEL@@AEBA?AV?$TCntPtr@$$CBUIPlatformBitmap@ARC@@@Mso@@AEBUIPlatformBitmap@ARC@@@Z`
- size: `1100`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: ``

## callers

- `0x1800078a0`
- `0x1800e1610`
- `0x18010d8a8`

## callees

- `0x18000ef20`
- `0x18000f790`
- `0x18004be8c`
- `0x18004becc`
- `0x180057e70`
- `0x1800613f8`
- `0x180061448`
- `0x18006146c`
- `0x1800dfe68`
- `0x1800e1ebc`
- `0x1800e5810`
- `0x180128208`
- `0x18013f7a0`

## import_xrefs

- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x1800e2075`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x1800e21c2`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x1800e2075`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x1800e21c2`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapFlipRotator@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapFlipRotator@ARC@@@Mso@@AEBUIPlatformBitmap@2@W4ImageTransform@2@@Z` at `0x1800e2137`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapFlipRotator@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapFlipRotator@ARC@@@Mso@@AEBUIPlatformBitmap@2@W4ImageTransform@2@@Z` at `0x1800e2137`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z` at `0x1800e2024`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z` at `0x1800e2269`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z` at `0x1800e2024`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z` at `0x1800e2269`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800e210b`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800e210b`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e2120`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800e2120`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void **__fastcall GEL::RasterImageResource::ClipFrame(__int64 a1, void **a2, struct ARC::IPlatformBitmap *a3)
{
  struct ARC::IPlatformBitmap *v3; // r12
  struct ARC::IPlatformBitmap *v6; // rbx
  _DWORD *v7; // r9
  __int64 v8; // r13
  _DWORD *v9; // rdi
  int *v10; // rax
  int v11; // ecx
  unsigned int i; // edx
  struct ARC::IPlatformBitmap **v14; // rax
  struct ARC::IPlatformBitmap *v15; // rdx
  struct ARC::IPlatformBitmap *v16; // rcx
  struct ARC::IPlatformBitmap *v17; // rcx
  struct ARC::IPlatformBitmap **v18; // rax
  struct ARC::IPlatformBitmap *v19; // rcx
  __int64 Size; // rax
  unsigned int v21; // r8d
  char v22; // r14
  struct ARC::IPlatformBitmap **v24; // rax
  struct ARC::IPlatformBitmap *v25; // rcx
  struct ARC::IPlatformBitmap *v26; // rcx
  unsigned int *Width; // rax
  __int64 v28; // rcx
  __int64 v29; // r8
  _DWORD *Height; // rax
  __int64 v31; // rcx
  int v32; // r9d
  unsigned int v33; // r10d
  char v34; // di
  struct ARC::IPlatformBitmap **v35; // rax
  bool v36; // r8
  struct ARC::IPlatformBitmap *v37; // r15
  struct ARC::IPlatformBitmap *v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // [rsp+28h] [rbp-38h] BYREF
  __int64 v46; // [rsp+30h] [rbp-30h] BYREF
  int v47; // [rsp+38h] [rbp-28h]
  int v48; // [rsp+3Ch] [rbp-24h]
  _BYTE v49[24]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v50; // [rsp+58h] [rbp-8h]
  struct ARC::IPlatformBitmap *v51; // [rsp+A0h] [rbp+40h] BYREF
  struct ARC::IPlatformBitmap *v52; // [rsp+B8h] [rbp+58h] BYREF

  v6 = (struct ARC::IPlatformBitmap *)a1;
  v7 = *(_DWORD **)(a1 + 56);
  if ( v7 && *v7 < v7[2] && v7[1] < v7[3] && (v8 = a1 + 32, *(_DWORD *)(a1 + 32)) && *(_DWORD *)(a1 + 36) )
  {
    if ( (!v7[4] || !v7[5])
      && (byte_180523FA0 < 0
        ? Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_180523FA0)
        : byte_180523FA0 != 0) )
    {
      CrashWithRecovery(0x1E1008E0u, 0);
LABEL_38:
      v24 = (struct ARC::IPlatformBitmap **)ARC::IPlatformBitmapFlipRotator::Create(&v52, v6);
      v25 = *v24;
      *v24 = v3;
      v51 = v6;
      v6 = v25;
      Mso::TCntPtr<GEL::IScene>::~TCntPtr<GEL::IScene>(&v51);
      v26 = v52;
      if ( v52 )
      {
        v52 = v3;
        (*(void (__fastcall **)(struct ARC::IPlatformBitmap *))(*(_QWORD *)v26 + 8LL))(v26);
      }
LABEL_21:
      *a2 = v6;
      return a2;
    }
    v9 = (_DWORD *)*((_QWORD *)v6 + 7);
    if ( v9[4] && v9[5] )
    {
      v6 = a3;
      v51 = a3;
      Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>((void *const *)&v51);
      v10 = (int *)(*(__int64 (__fastcall **)(struct ARC::IPlatformBitmap *, struct ARC::IPlatformBitmap **))(*(_QWORD *)a3 + 80LL))(
                     a3,
                     &v52);
      v46 = 0;
      v47 = *v10;
      v48 = v10[1];
      if ( !(unsigned __int8)Math::TRect<Math::TUnits<unsigned int,Math::DevicePixels>>::Contains<Math::TUnits<unsigned int,Math::DevicePixels>,0>(
                               v9,
                               &v46) )
      {
        v18 = (struct ARC::IPlatformBitmap **)ARC::IPlatformBitmapClipper::Create(&v52, a3, v9);
        v6 = *v18;
        *v18 = 0;
        v51 = v6;
        (*(void (__fastcall **)(struct ARC::IPlatformBitmap *))(*(_QWORD *)a3 + 8LL))(a3);
        v19 = v52;
        if ( v52 )
        {
          v52 = 0;
          (*(void (__fastcall **)(struct ARC::IPlatformBitmap *))(*(_QWORD *)v19 + 8LL))(v19);
        }
      }
      if ( (unsigned __int8)Math::TRect<Math::TUnits<unsigned int,Math::DevicePixels>>::IsDegenerate(v9) )
      {
        v52 = 0;
      }
      else
      {
        v11 = v9[3] - v9[1];
        LODWORD(v52) = v9[2] - *v9;
        HIDWORD(v52) = v11;
      }
      for ( i = 0; ; ++i )
      {
        if ( i >= 2 )
        {
          v3 = 0;
          goto LABEL_20;
        }
        if ( v9[i + 4] != *((_DWORD *)&v52 + i) )
          break;
      }
      v14 = (struct ARC::IPlatformBitmap **)ARC::IPlatformBitmapScaler::Create(&v52, v6, v9 + 4, v9 + 6);
      v15 = *v14;
      v3 = 0;
      *v14 = 0;
      v16 = v6;
      v6 = v15;
      v51 = v15;
      if ( v16 )
        (*(void (__fastcall **)(struct ARC::IPlatformBitmap *))(*(_QWORD *)v16 + 8LL))(v16);
      v17 = v52;
      if ( v52 )
      {
        v52 = 0;
        (*(void (__fastcall **)(struct ARC::IPlatformBitmap *))(*(_QWORD *)v17 + 8LL))(v17);
      }
LABEL_20:
      if ( !v9[7] )
        goto LABEL_21;
      goto LABEL_38;
    }
    Size = Math::TRect<Math::TUnits<unsigned int,Math::DevicePixels>>::GetSize(*((_QWORD *)v6 + 7), &v51);
    v21 = 0;
    v22 = 1;
    while ( 1 )
    {
      if ( v21 >= 2 )
      {
        v22 = 0;
        v31 = *((_QWORD *)v6 + 7);
        goto LABEL_43;
      }
      if ( *(_DWORD *)(Size + 4LL * v21) != *((_DWORD *)v6 + v21 + 8) )
        break;
      ++v21;
    }
    Width = (unsigned int *)Math::TRect<Math::TUnits<unsigned int,Math::DevicePixels>>::GetWidth(
                              *((_QWORD *)v6 + 7),
                              &v51);
    Height = (_DWORD *)Math::TRect<Math::TUnits<unsigned int,Math::DevicePixels>>::GetHeight(v28, &v52, v29, *Width);
    if ( v32 * *Height < v33 )
    {
      v34 = 1;
      goto LABEL_44;
    }
LABEL_43:
    v34 = 0;
LABEL_44:
    v35 = (struct ARC::IPlatformBitmap **)ARC::IPlatformBitmapClipper::Create(&v52, a3, v31);
    v37 = *v35;
    *v35 = 0;
    v51 = v37;
    v38 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*(void (__fastcall **)(struct ARC::IPlatformBitmap *))(*(_QWORD *)v38 + 8LL))(v38);
    }
    if ( *(_BYTE *)(*((_QWORD *)v6 + 7) + 32LL) )
    {
      if ( v34 )
      {
        ARC::IPlatformBitmap::ReadLock::ReadLock((ARC::IPlatformBitmap::ReadLock *)v49, v37, v36);
        v45 = 0;
        v39 = ARC::IPlatformBitmap::Create(&v46, v49, &v45);
        Mso::TCntPtr<ARC::IPlatformBitmap>::operator=(&v51, v39);
        Mso::TCntPtr<ARC::IRecolorEffectProgram>::~TCntPtr<ARC::IRecolorEffectProgram>(&v46);
        v40 = v50;
        if ( v50 )
        {
          v50 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
        }
      }
    }
    if ( v22 )
    {
      v41 = ARC::IPlatformBitmapScaler::Create(&v45, v51, v8, *((_QWORD *)v6 + 7) + 24LL);
      Mso::TCntPtr<ARC::IPlatformBitmap>::operator=(&v51, v41);
      v42 = v45;
      if ( v45 )
      {
        v45 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 8LL))(v42);
      }
    }
    if ( *(_BYTE *)(*((_QWORD *)v6 + 7) + 32LL) )
    {
      if ( !v34 )
      {
        ARC::IPlatformBitmap::ReadLock::ReadLock((ARC::IPlatformBitmap::ReadLock *)v49, v51, v36);
        v52 = 0;
        v43 = ARC::IPlatformBitmap::Create(&v46, v49, &v52);
        Mso::TCntPtr<ARC::IPlatformBitmap>::operator=(&v51, v43);
        Mso::TCntPtr<ARC::IRecolorEffectProgram>::~TCntPtr<ARC::IRecolorEffectProgram>(&v46);
        v44 = v50;
        if ( v50 )
        {
          v50 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
        }
      }
    }
    *a2 = v51;
  }
  else
  {
    *a2 = a3;
    Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(a2);
  }
  return a2;
}

```

## disassembly

```asm
0x1800e1ebc  mov     [rsp-38h+arg_8], rbx
0x1800e1ec1  push    rbp
0x1800e1ec2  push    rsi
0x1800e1ec3  push    rdi
0x1800e1ec4  push    r12
0x1800e1ec6  push    r13
0x1800e1ec8  push    r14
0x1800e1eca  push    r15
0x1800e1ecc  mov     rbp, rsp
0x1800e1ecf  sub     rsp, 60h
0x1800e1ed3  mov     r15, r8
0x1800e1ed6  mov     rsi, rdx
0x1800e1ed9  mov     rbx, rcx
0x1800e1edc  xor     r14d, r14d
0x1800e1edf  mov     r9, [rcx+38h]
0x1800e1ee3  test    r9, r9
0x1800e1ee6  jz      loc_1800E1FDA
0x1800e1eec  mov     eax, [r9+8]
0x1800e1ef0  cmp     [r9], eax
0x1800e1ef3  jnb     loc_1800E1FDA
0x1800e1ef9  mov     eax, [r9+0Ch]
0x1800e1efd  cmp     [r9+4], eax
0x1800e1f01  jnb     loc_1800E1FDA
0x1800e1f07  lea     r13, [rcx+20h]
0x1800e1f0b  cmp     [r13+0], r14d
0x1800e1f0f  jbe     loc_1800E1FDA
0x1800e1f15  cmp     [r13+4], r14d
0x1800e1f19  jbe     loc_1800E1FDA
0x1800e1f1f  cmp     [r9+10h], r14d
0x1800e1f23  jbe     loc_1800E20F5
0x1800e1f29  cmp     [r9+14h], r14d
0x1800e1f2d  jbe     loc_1800E20F5
0x1800e1f33  mov     rdi, [rbx+38h]
0x1800e1f37  cmp     [rdi+10h], r14d
0x1800e1f3b  jbe     loc_1800E20C1
0x1800e1f41  cmp     [rdi+14h], r14d
0x1800e1f45  jbe     loc_1800E20C1
0x1800e1f4b  mov     rbx, r15
0x1800e1f4e  mov     [rbp+arg_0], rbx
0x1800e1f52  lea     rcx, [rbp+arg_0]; void **
0x1800e1f56  call    ??$CheckedAddRefOnNewlyAssignedPtr@VWindow@GEL@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAVWindow@GEL@@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(GEL::Window * *)
0x1800e1f5b  mov     rax, [r15]
0x1800e1f5e  lea     rdx, [rbp+arg_18]
0x1800e1f62  mov     rcx, r15
0x1800e1f65  mov     rax, [rax+50h]
0x1800e1f69  call    cs:__guard_dispatch_icall_fptr
0x1800e1f6f  mov     [rbp+var_30], r14
0x1800e1f73  mov     ecx, [rax]
0x1800e1f75  mov     [rbp+var_28], ecx
0x1800e1f78  mov     eax, [rax+4]
0x1800e1f7b  mov     [rbp+var_24], eax
0x1800e1f7e  lea     rdx, [rbp+var_30]
0x1800e1f82  mov     rcx, rdi
0x1800e1f85  call    ??$Contains@V?$TUnits@IUDevicePixels@Math@@@Math@@$0A@@?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@QEBA_NAEBU01@@Z; Math::TRect<Math::TUnits<uint,Math::DevicePixels>>::Contains<Math::TUnits<uint,Math::DevicePixels>,0>(Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &)
0x1800e1f8a  test    al, al
0x1800e1f8c  jz      loc_1800E206B
0x1800e1f92  mov     rcx, rdi
0x1800e1f95  call    ?IsDegenerate@?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@QEBA_NXZ; Math::TRect<Math::TUnits<uint,Math::DevicePixels>>::IsDegenerate(void)
0x1800e1f9a  test    al, al
0x1800e1f9c  jnz     loc_1800E20B8
0x1800e1fa2  mov     ecx, [rdi+0Ch]
0x1800e1fa5  sub     ecx, [rdi+4]
0x1800e1fa8  mov     eax, [rdi+8]
0x1800e1fab  sub     eax, [rdi]
0x1800e1fad  mov     dword ptr [rbp+arg_18], eax
0x1800e1fb0  mov     dword ptr [rbp+arg_18+4], ecx
0x1800e1fb3  mov     rax, [rbp+arg_18]
0x1800e1fb7  mov     [rbp+arg_18], rax
0x1800e1fbb  mov     edx, r14d
0x1800e1fbe  mov     r14d, 1
0x1800e1fc4  cmp     edx, 2
0x1800e1fc7  jnb     short loc_1800E2000
0x1800e1fc9  mov     ecx, edx
0x1800e1fcb  mov     eax, dword ptr [rbp+rcx*4+arg_18]
0x1800e1fcf  cmp     [rdi+rcx*4+10h], eax
0x1800e1fd3  jnz     short loc_1800E2015
0x1800e1fd5  add     edx, r14d
0x1800e1fd8  jmp     short loc_1800E1FC4
0x1800e1fda  mov     [rdx], r15
0x1800e1fdd  mov     rcx, rsi; void **
0x1800e1fe0  call    ??$CheckedAddRefOnNewlyAssignedPtr@VWindow@GEL@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAVWindow@GEL@@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(GEL::Window * *)
0x1800e1fe5  mov     rax, rsi
0x1800e1fe8  mov     rbx, [rsp+60h+arg_8]
0x1800e1ff0  add     rsp, 60h
0x1800e1ff4  pop     r15
0x1800e1ff6  pop     r14
0x1800e1ff8  pop     r13
0x1800e1ffa  pop     r12
0x1800e1ffc  pop     rdi
0x1800e1ffd  pop     rsi
0x1800e1ffe  pop     rbp
0x1800e1fff  retn
0x1800e2000  xor     r12d, r12d
0x1800e2003  mov     r8d, [rdi+1Ch]
0x1800e2007  test    r8d, r8d
0x1800e200a  jnz     loc_1800E2130
0x1800e2010  mov     [rsi], rbx
0x1800e2013  jmp     short loc_1800E1FE5
0x1800e2015  lea     r9, [rdi+18h]
0x1800e2019  lea     r8, [rdi+10h]
0x1800e201d  mov     rdx, rbx
0x1800e2020  lea     rcx, [rbp+arg_18]
0x1800e2024  call    cs:__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z; ARC::IPlatformBitmapScaler::Create(ARC::IPlatformBitmap const &,Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &,ARC::InterpolationMode const &)
0x1800e202a  mov     rdx, [rax]
0x1800e202d  xor     r12d, r12d
0x1800e2030  mov     [rax], r12
0x1800e2033  mov     rcx, rbx
0x1800e2036  mov     rbx, rdx
0x1800e2039  mov     [rbp+arg_0], rdx
0x1800e203d  test    rcx, rcx
0x1800e2040  jz      short loc_1800E204F
0x1800e2042  mov     rax, [rcx]
0x1800e2045  mov     rax, [rax+8]
0x1800e2049  call    cs:__guard_dispatch_icall_fptr
0x1800e204f  mov     rcx, [rbp+arg_18]
0x1800e2053  test    rcx, rcx
0x1800e2056  jz      short loc_1800E2003
0x1800e2058  mov     [rbp+arg_18], r12
0x1800e205c  mov     rax, [rcx]
0x1800e205f  mov     rax, [rax+8]
0x1800e2063  call    cs:__guard_dispatch_icall_fptr
0x1800e2069  jmp     short loc_1800E2003
0x1800e206b  mov     r8, rdi
0x1800e206e  mov     rdx, r15
0x1800e2071  lea     rcx, [rbp+arg_18]
0x1800e2075  call    cs:__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z; ARC::IPlatformBitmapClipper::Create(ARC::IPlatformBitmap const &,Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &)
0x1800e207b  mov     rbx, [rax]
0x1800e207e  mov     [rax], r14
0x1800e2081  mov     [rbp+arg_0], rbx
0x1800e2085  mov     rax, [r15]
0x1800e2088  mov     rcx, r15
0x1800e208b  mov     rax, [rax+8]
0x1800e208f  call    cs:__guard_dispatch_icall_fptr
0x1800e2095  mov     rcx, [rbp+arg_18]
0x1800e2099  test    rcx, rcx
0x1800e209c  jz      loc_1800E1F92
0x1800e20a2  mov     [rbp+arg_18], r14
0x1800e20a6  mov     rax, [rcx]
0x1800e20a9  mov     rax, [rax+8]
0x1800e20ad  call    cs:__guard_dispatch_icall_fptr
0x1800e20b3  jmp     loc_1800E1F92
0x1800e20b8  mov     [rbp+arg_18], r14
0x1800e20bc  jmp     loc_1800E1FB3
0x1800e20c1  lea     rdx, [rbp+arg_0]
0x1800e20c5  mov     rcx, rdi
0x1800e20c8  call    ?GetSize@?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@QEBA?AU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@2@XZ; Math::TRect<Math::TUnits<uint,Math::DevicePixels>>::GetSize(void)
0x1800e20cd  mov     r8d, r14d
0x1800e20d0  mov     r14d, 1
0x1800e20d6  cmp     r8d, 2
0x1800e20da  jnb     loc_1800E21AB
0x1800e20e0  mov     edx, r8d
0x1800e20e3  mov     ecx, [rbx+rdx*4+20h]
0x1800e20e7  cmp     [rax+rdx*4], ecx
0x1800e20ea  jnz     loc_1800E2176
0x1800e20f0  add     r8d, r14d
0x1800e20f3  jmp     short loc_1800E20D6
0x1800e20f5  mov     al, cs:byte_180523FA0
0x1800e20fb  test    al, al
0x1800e20fd  js      short loc_1800E2104
0x1800e20ff  setnz   al
0x1800e2102  jmp     short loc_1800E2111
0x1800e2104  lea     rcx, byte_180523FA0
0x1800e210b  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1800e2111  test    al, al
0x1800e2113  jz      loc_1800E1F33
0x1800e2119  xor     edx, edx
0x1800e211b  mov     ecx, 1E1008E0h
0x1800e2120  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800e2126  nop
0x1800e2127  nop     word ptr [rax+rax+00000000h]
0x1800e2130  mov     rdx, rbx
0x1800e2133  lea     rcx, [rbp+arg_18]
0x1800e2137  call    cs:__imp_?Create@IPlatformBitmapFlipRotator@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapFlipRotator@ARC@@@Mso@@AEBUIPlatformBitmap@2@W4ImageTransform@2@@Z; ARC::IPlatformBitmapFlipRotator::Create(ARC::IPlatformBitmap const &,ARC::ImageTransform)
0x1800e213d  mov     rcx, [rax]
0x1800e2140  mov     [rax], r12
0x1800e2143  mov     [rbp+arg_0], rbx
0x1800e2147  mov     rbx, rcx
0x1800e214a  lea     rcx, [rbp+arg_0]
0x1800e214e  call    ??1?$TCntPtr@UIScene@GEL@@@Mso@@QEAA@XZ; Mso::TCntPtr<GEL::IScene>::~TCntPtr<GEL::IScene>(void)
0x1800e2153  mov     rcx, [rbp+arg_18]
0x1800e2157  test    rcx, rcx
0x1800e215a  jz      loc_1800E2010
0x1800e2160  mov     [rbp+arg_18], r12
0x1800e2164  mov     rax, [rcx]
0x1800e2167  mov     rax, [rax+8]
0x1800e216b  call    cs:__guard_dispatch_icall_fptr
0x1800e2171  jmp     loc_1800E2010
0x1800e2176  mov     r10d, [r13+0]
0x1800e217a  imul    r10d, [rbx+24h]
0x1800e217f  mov     rcx, [rbx+38h]
0x1800e2183  lea     rdx, [rbp+arg_0]
0x1800e2187  call    ?GetWidth@?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@QEBA?AV?$TUnits@IUDevicePixels@Math@@@2@XZ; Math::TRect<Math::TUnits<uint,Math::DevicePixels>>::GetWidth(void)
0x1800e218c  mov     r9d, [rax]
0x1800e218f  lea     rdx, [rbp+arg_18]
0x1800e2193  call    ?GetHeight@?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@QEBA?AV?$TUnits@IUDevicePixels@Math@@@2@XZ; Math::TRect<Math::TUnits<uint,Math::DevicePixels>>::GetHeight(void)
0x1800e2198  mov     eax, [rax]
0x1800e219a  imul    eax, r9d
0x1800e219e  xor     r12d, r12d
0x1800e21a1  cmp     eax, r10d
0x1800e21a4  jnb     short loc_1800E21B5
0x1800e21a6  mov     dil, r14b
0x1800e21a9  jmp     short loc_1800E21B8
0x1800e21ab  xor     r12d, r12d
0x1800e21ae  mov     r14b, r12b
0x1800e21b1  mov     rcx, [rbx+38h]
0x1800e21b5  mov     dil, r12b
0x1800e21b8  mov     r8, rcx
0x1800e21bb  mov     rdx, r15
0x1800e21be  lea     rcx, [rbp+arg_18]
0x1800e21c2  call    cs:__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z; ARC::IPlatformBitmapClipper::Create(ARC::IPlatformBitmap const &,Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &)
0x1800e21c8  mov     r15, [rax]
0x1800e21cb  mov     [rax], r12
0x1800e21ce  mov     [rbp+arg_0], r15
0x1800e21d2  mov     rcx, [rbp+arg_18]
0x1800e21d6  test    rcx, rcx
0x1800e21d9  jz      short loc_1800E21EC
0x1800e21db  mov     [rbp+arg_18], r12
0x1800e21df  mov     rax, [rcx]
0x1800e21e2  mov     rax, [rax+8]
0x1800e21e6  call    cs:__guard_dispatch_icall_fptr
0x1800e21ec  mov     rax, [rbx+38h]
0x1800e21f0  cmp     [rax+20h], r12b
0x1800e21f4  jz      short loc_1800E2251
0x1800e21f6  test    dil, dil
0x1800e21f9  jz      short loc_1800E2251
0x1800e21fb  mov     rdx, r15; struct ARC::IPlatformBitmap *
0x1800e21fe  lea     rcx, [rbp+var_20]; this
0x1800e2202  call    ??0ReadLock@IPlatformBitmap@ARC@@QEAA@AEBU12@_N@Z; ARC::IPlatformBitmap::ReadLock::ReadLock(ARC::IPlatformBitmap const &,bool)
0x1800e2207  mov     [rbp+var_38], 0
0x1800e220f  lea     r8, [rbp+var_38]
0x1800e2213  lea     rdx, [rbp+var_20]
0x1800e2217  lea     rcx, [rbp+var_30]
0x1800e221b  call    ?Create@IPlatformBitmap@ARC@@SA?AV?$TCntPtr@UIPlatformBitmap@ARC@@@Mso@@AEBVConstPixelMap@2@AEBU?$TVector2@V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@Math@@@Z; ARC::IPlatformBitmap::Create(ARC::ConstPixelMap const &,Math::TVector2<Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>> const &)
0x1800e2220  mov     rdx, rax
0x1800e2223  lea     rcx, [rbp+arg_0]
0x1800e2227  call    ??4?$TCntPtr@UIPlatformBitmap@ARC@@@Mso@@QEAAAEAV01@$$QEAV01@@Z; Mso::TCntPtr<ARC::IPlatformBitmap>::operator=(Mso::TCntPtr<ARC::IPlatformBitmap> &&)
0x1800e222c  lea     rcx, [rbp+var_30]; void *
0x1800e2230  call    ??1?$TCntPtr@UIRecolorEffectProgram@ARC@@@Mso@@QEAA@XZ; Mso::TCntPtr<ARC::IRecolorEffectProgram>::~TCntPtr<ARC::IRecolorEffectProgram>(void)
0x1800e2235  mov     rcx, [rbp+var_8]
0x1800e2239  test    rcx, rcx
0x1800e223c  jz      short loc_1800E2251
0x1800e223e  xchg    ax, ax
0x1800e2240  mov     [rbp+var_8], r12
0x1800e2244  mov     rax, [rcx]
0x1800e2247  mov     rax, [rax+8]
0x1800e224b  call    cs:__guard_dispatch_icall_fptr
0x1800e2251  test    r14b, r14b
0x1800e2254  jz      short loc_1800E2295
0x1800e2256  mov     r9, [rbx+38h]
0x1800e225a  add     r9, 18h
0x1800e225e  mov     r8, r13
0x1800e2261  mov     rdx, [rbp+arg_0]
0x1800e2265  lea     rcx, [rbp+var_38]
0x1800e2269  call    cs:__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z; ARC::IPlatformBitmapScaler::Create(ARC::IPlatformBitmap const &,Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &,ARC::InterpolationMode const &)
0x1800e226f  mov     rdx, rax
0x1800e2272  lea     rcx, [rbp+arg_0]
0x1800e2276  call    ??4?$TCntPtr@UIPlatformBitmap@ARC@@@Mso@@QEAAAEAV01@$$QEAV01@@Z; Mso::TCntPtr<ARC::IPlatformBitmap>::operator=(Mso::TCntPtr<ARC::IPlatformBitmap> &&)
0x1800e227b  mov     rcx, [rbp+var_38]
0x1800e227f  test    rcx, rcx
0x1800e2282  jz      short loc_1800E2295
0x1800e2284  mov     [rbp+var_38], r12
0x1800e2288  mov     rax, [rcx]
0x1800e228b  mov     rax, [rax+8]
0x1800e228f  call    cs:__guard_dispatch_icall_fptr
0x1800e2295  mov     rax, [rbx+38h]
0x1800e2299  cmp     [rax+20h], r12b
0x1800e229d  jz      short loc_1800E22FB
0x1800e229f  test    dil, dil
0x1800e22a2  jnz     short loc_1800E22FB
0x1800e22a4  mov     rdx, [rbp+arg_0]; struct ARC::IPlatformBitmap *
0x1800e22a8  lea     rcx, [rbp+var_20]; this
0x1800e22ac  call    ??0ReadLock@IPlatformBitmap@ARC@@QEAA@AEBU12@_N@Z; ARC::IPlatformBitmap::ReadLock::ReadLock(ARC::IPlatformBitmap const &,bool)
0x1800e22b1  nop
0x1800e22b2  mov     [rbp+arg_18], 0
0x1800e22ba  lea     r8, [rbp+arg_18]
0x1800e22be  lea     rdx, [rbp+var_20]
0x1800e22c2  lea     rcx, [rbp+var_30]
0x1800e22c6  call    ?Create@IPlatformBitmap@ARC@@SA?AV?$TCntPtr@UIPlatformBitmap@ARC@@@Mso@@AEBVConstPixelMap@2@AEBU?$TVector2@V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@Math@@@Z; ARC::IPlatformBitmap::Create(ARC::ConstPixelMap const &,Math::TVector2<Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>> const &)
0x1800e22cb  mov     rdx, rax
0x1800e22ce  lea     rcx, [rbp+arg_0]
0x1800e22d2  call    ??4?$TCntPtr@UIPlatformBitmap@ARC@@@Mso@@QEAAAEAV01@$$QEAV01@@Z; Mso::TCntPtr<ARC::IPlatformBitmap>::operator=(Mso::TCntPtr<ARC::IPlatformBitmap> &&)
0x1800e22d7  lea     rcx, [rbp+var_30]; void *
0x1800e22db  call    ??1?$TCntPtr@UIRecolorEffectProgram@ARC@@@Mso@@QEAA@XZ; Mso::TCntPtr<ARC::IRecolorEffectProgram>::~TCntPtr<ARC::IRecolorEffectProgram>(void)
0x1800e22e0  nop
0x1800e22e1  mov     rcx, [rbp+var_8]
0x1800e22e5  test    rcx, rcx
0x1800e22e8  jz      short loc_1800E22FB
0x1800e22ea  mov     [rbp+var_8], r12
0x1800e22ee  mov     rax, [rcx]
0x1800e22f1  mov     rax, [rax+8]
0x1800e22f5  call    cs:__guard_dispatch_icall_fptr
0x1800e22fb  mov     rax, [rbp+arg_0]
0x1800e22ff  mov     [rsi], rax
0x1800e2302  jmp     loc_1800E1FE5
```
