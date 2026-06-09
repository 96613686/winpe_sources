# GEL::RasterImageResource::ClipFrame(ARC::IPlatformBitmap const &)

- ea: `0x1800bb35c`
- end: `0x1800bb79b`
- name: `?ClipFrame@RasterImageResource@GEL@@AEBA?AV?$TCntPtr@$$CBUIPlatformBitmap@ARC@@@Mso@@AEBUIPlatformBitmap@ARC@@@Z`
- size: `1087`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: ``

## callers

- `0x1800073c0`
- `0x1800ba6a0`
- `0x1800bbd3c`

## callees

- `0x1800085c8`
- `0x18000f890`
- `0x18004b880`
- `0x18004b8c0`
- `0x1800573f0`
- `0x180067430`
- `0x18008442c`
- `0x18008447c`
- `0x1800844a0`
- `0x1800bb35c`
- `0x180124df0`
- `0x180140d70`

## import_xrefs

- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x1800bb515`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x1800bb655`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x1800bb515`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z` at `0x1800bb655`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapFlipRotator@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapFlipRotator@ARC@@@Mso@@AEBUIPlatformBitmap@2@W4ImageTransform@2@@Z` at `0x1800bb5ca`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapFlipRotator@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapFlipRotator@ARC@@@Mso@@AEBUIPlatformBitmap@2@W4ImageTransform@2@@Z` at `0x1800bb5ca`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z` at `0x1800bb4c4`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z` at `0x1800bb6fc`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z` at `0x1800bb4c4`
- `mso40uiWin32Client!__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z` at `0x1800bb6fc`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800bb5a7`
- `Mso20Win32Client!__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ` at `0x1800bb5a7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800bb5bc`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1800bb5bc`

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
      && (byte_18051FF38 < 0
        ? Mso::AB::Optimized::ChangeGate::Evaluate((Mso::AB::Optimized::ChangeGate *)&byte_18051FF38)
        : byte_18051FF38 != 0) )
    {
      CrashWithRecovery(0x1E1008E0u, 0);
LABEL_38:
      v24 = (struct ARC::IPlatformBitmap **)ARC::IPlatformBitmapFlipRotator::Create(&v52, v6);
      v25 = *v24;
      *v24 = v3;
      v51 = v6;
      v6 = v25;
      Mso::TCntPtr<Gfx::PlanarProjectionTexturer>::~TCntPtr<Gfx::PlanarProjectionTexturer>(&v51);
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
        Mso::TCntPtr<Gfx::PlanarProjectionTexturer>::~TCntPtr<Gfx::PlanarProjectionTexturer>(&v46);
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
        Mso::TCntPtr<Gfx::PlanarProjectionTexturer>::~TCntPtr<Gfx::PlanarProjectionTexturer>(&v46);
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
0x1800bb35c  mov     [rsp-38h+arg_8], rbx
0x1800bb361  push    rbp
0x1800bb362  push    rsi
0x1800bb363  push    rdi
0x1800bb364  push    r12
0x1800bb366  push    r13
0x1800bb368  push    r14
0x1800bb36a  push    r15
0x1800bb36c  mov     rbp, rsp
0x1800bb36f  sub     rsp, 60h
0x1800bb373  mov     r15, r8
0x1800bb376  mov     rsi, rdx
0x1800bb379  mov     rbx, rcx
0x1800bb37c  xor     r14d, r14d
0x1800bb37f  mov     r9, [rcx+38h]
0x1800bb383  test    r9, r9
0x1800bb386  jz      loc_1800BB47A
0x1800bb38c  mov     eax, [r9+8]
0x1800bb390  cmp     [r9], eax
0x1800bb393  jnb     loc_1800BB47A
0x1800bb399  mov     eax, [r9+0Ch]
0x1800bb39d  cmp     [r9+4], eax
0x1800bb3a1  jnb     loc_1800BB47A
0x1800bb3a7  lea     r13, [rcx+20h]
0x1800bb3ab  cmp     [r13+0], r14d
0x1800bb3af  jbe     loc_1800BB47A
0x1800bb3b5  cmp     [r13+4], r14d
0x1800bb3b9  jbe     loc_1800BB47A
0x1800bb3bf  cmp     [r9+10h], r14d
0x1800bb3c3  jbe     loc_1800BB591
0x1800bb3c9  cmp     [r9+14h], r14d
0x1800bb3cd  jbe     loc_1800BB591
0x1800bb3d3  mov     rdi, [rbx+38h]
0x1800bb3d7  cmp     [rdi+10h], r14d
0x1800bb3db  jbe     loc_1800BB561
0x1800bb3e1  cmp     [rdi+14h], r14d
0x1800bb3e5  jbe     loc_1800BB561
0x1800bb3eb  mov     rbx, r15
0x1800bb3ee  mov     [rbp+arg_0], rbx
0x1800bb3f2  lea     rcx, [rbp+arg_0]; void **
0x1800bb3f6  call    ??$CheckedAddRefOnNewlyAssignedPtr@VWindow@GEL@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAVWindow@GEL@@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(GEL::Window * *)
0x1800bb3fb  mov     rax, [r15]
0x1800bb3fe  lea     rdx, [rbp+arg_18]
0x1800bb402  mov     rcx, r15
0x1800bb405  mov     rax, [rax+50h]
0x1800bb409  call    cs:__guard_dispatch_icall_fptr
0x1800bb40f  mov     [rbp+var_30], r14
0x1800bb413  mov     ecx, [rax]
0x1800bb415  mov     [rbp+var_28], ecx
0x1800bb418  mov     eax, [rax+4]
0x1800bb41b  mov     [rbp+var_24], eax
0x1800bb41e  lea     rdx, [rbp+var_30]
0x1800bb422  mov     rcx, rdi
0x1800bb425  call    ??$Contains@V?$TUnits@IUDevicePixels@Math@@@Math@@$0A@@?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@QEBA_NAEBU01@@Z; Math::TRect<Math::TUnits<uint,Math::DevicePixels>>::Contains<Math::TUnits<uint,Math::DevicePixels>,0>(Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &)
0x1800bb42a  test    al, al
0x1800bb42c  jz      loc_1800BB50B
0x1800bb432  mov     rcx, rdi
0x1800bb435  call    ?IsDegenerate@?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@QEBA_NXZ; Math::TRect<Math::TUnits<uint,Math::DevicePixels>>::IsDegenerate(void)
0x1800bb43a  test    al, al
0x1800bb43c  jnz     loc_1800BB558
0x1800bb442  mov     ecx, [rdi+0Ch]
0x1800bb445  sub     ecx, [rdi+4]
0x1800bb448  mov     eax, [rdi+8]
0x1800bb44b  sub     eax, [rdi]
0x1800bb44d  mov     dword ptr [rbp+arg_18], eax
0x1800bb450  mov     dword ptr [rbp+arg_18+4], ecx
0x1800bb453  mov     rax, [rbp+arg_18]
0x1800bb457  mov     [rbp+arg_18], rax
0x1800bb45b  mov     edx, r14d
0x1800bb45e  mov     r14d, 1
0x1800bb464  cmp     edx, 2
0x1800bb467  jnb     short loc_1800BB4A0
0x1800bb469  mov     ecx, edx
0x1800bb46b  mov     eax, dword ptr [rbp+rcx*4+arg_18]
0x1800bb46f  cmp     [rdi+rcx*4+10h], eax
0x1800bb473  jnz     short loc_1800BB4B5
0x1800bb475  add     edx, r14d
0x1800bb478  jmp     short loc_1800BB464
0x1800bb47a  mov     [rdx], r15
0x1800bb47d  mov     rcx, rsi; void **
0x1800bb480  call    ??$CheckedAddRefOnNewlyAssignedPtr@VWindow@GEL@@@?$TCntPtrAddRefStrategyImpl@$0A@@Details@Mso@@SAXPEAPEAVWindow@GEL@@@Z; Mso::Details::TCntPtrAddRefStrategyImpl<0>::CheckedAddRefOnNewlyAssignedPtr<GEL::Window>(GEL::Window * *)
0x1800bb485  mov     rax, rsi
0x1800bb488  mov     rbx, [rsp+60h+arg_8]
0x1800bb490  add     rsp, 60h
0x1800bb494  pop     r15
0x1800bb496  pop     r14
0x1800bb498  pop     r13
0x1800bb49a  pop     r12
0x1800bb49c  pop     rdi
0x1800bb49d  pop     rsi
0x1800bb49e  pop     rbp
0x1800bb49f  retn
0x1800bb4a0  xor     r12d, r12d
0x1800bb4a3  mov     r8d, [rdi+1Ch]
0x1800bb4a7  test    r8d, r8d
0x1800bb4aa  jnz     loc_1800BB5C3
0x1800bb4b0  mov     [rsi], rbx
0x1800bb4b3  jmp     short loc_1800BB485
0x1800bb4b5  lea     r9, [rdi+18h]
0x1800bb4b9  lea     r8, [rdi+10h]
0x1800bb4bd  mov     rdx, rbx
0x1800bb4c0  lea     rcx, [rbp+arg_18]
0x1800bb4c4  call    cs:__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z; ARC::IPlatformBitmapScaler::Create(ARC::IPlatformBitmap const &,Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &,ARC::InterpolationMode const &)
0x1800bb4ca  mov     rdx, [rax]
0x1800bb4cd  xor     r12d, r12d
0x1800bb4d0  mov     [rax], r12
0x1800bb4d3  mov     rcx, rbx
0x1800bb4d6  mov     rbx, rdx
0x1800bb4d9  mov     [rbp+arg_0], rdx
0x1800bb4dd  test    rcx, rcx
0x1800bb4e0  jz      short loc_1800BB4EF
0x1800bb4e2  mov     rax, [rcx]
0x1800bb4e5  mov     rax, [rax+8]
0x1800bb4e9  call    cs:__guard_dispatch_icall_fptr
0x1800bb4ef  mov     rcx, [rbp+arg_18]
0x1800bb4f3  test    rcx, rcx
0x1800bb4f6  jz      short loc_1800BB4A3
0x1800bb4f8  mov     [rbp+arg_18], r12
0x1800bb4fc  mov     rax, [rcx]
0x1800bb4ff  mov     rax, [rax+8]
0x1800bb503  call    cs:__guard_dispatch_icall_fptr
0x1800bb509  jmp     short loc_1800BB4A3
0x1800bb50b  mov     r8, rdi
0x1800bb50e  mov     rdx, r15
0x1800bb511  lea     rcx, [rbp+arg_18]
0x1800bb515  call    cs:__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z; ARC::IPlatformBitmapClipper::Create(ARC::IPlatformBitmap const &,Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &)
0x1800bb51b  mov     rbx, [rax]
0x1800bb51e  mov     [rax], r14
0x1800bb521  mov     [rbp+arg_0], rbx
0x1800bb525  mov     rax, [r15]
0x1800bb528  mov     rcx, r15
0x1800bb52b  mov     rax, [rax+8]
0x1800bb52f  call    cs:__guard_dispatch_icall_fptr
0x1800bb535  mov     rcx, [rbp+arg_18]
0x1800bb539  test    rcx, rcx
0x1800bb53c  jz      loc_1800BB432
0x1800bb542  mov     [rbp+arg_18], r14
0x1800bb546  mov     rax, [rcx]
0x1800bb549  mov     rax, [rax+8]
0x1800bb54d  call    cs:__guard_dispatch_icall_fptr
0x1800bb553  jmp     loc_1800BB432
0x1800bb558  mov     [rbp+arg_18], r14
0x1800bb55c  jmp     loc_1800BB453
0x1800bb561  lea     rdx, [rbp+arg_0]
0x1800bb565  mov     rcx, rdi
0x1800bb568  call    ?GetSize@?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@QEBA?AU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@2@XZ; Math::TRect<Math::TUnits<uint,Math::DevicePixels>>::GetSize(void)
0x1800bb56d  mov     r8d, r14d
0x1800bb570  mov     r14d, 1
0x1800bb576  cmp     r8d, 2
0x1800bb57a  jnb     loc_1800BB63E
0x1800bb580  mov     edx, r8d
0x1800bb583  mov     ecx, [rbx+rdx*4+20h]
0x1800bb587  cmp     [rax+rdx*4], ecx
0x1800bb58a  jnz     short loc_1800BB609
0x1800bb58c  add     r8d, r14d
0x1800bb58f  jmp     short loc_1800BB576
0x1800bb591  mov     al, cs:byte_18051FF38
0x1800bb597  test    al, al
0x1800bb599  js      short loc_1800BB5A0
0x1800bb59b  setnz   al
0x1800bb59e  jmp     short loc_1800BB5AD
0x1800bb5a0  lea     rcx, byte_18051FF38
0x1800bb5a7  call    cs:__imp_?Evaluate@ChangeGate@Optimized@AB@Mso@@AEBA_NXZ; Mso::AB::Optimized::ChangeGate::Evaluate(void)
0x1800bb5ad  test    al, al
0x1800bb5af  jz      loc_1800BB3D3
0x1800bb5b5  xor     edx, edx
0x1800bb5b7  mov     ecx, 1E1008E0h
0x1800bb5bc  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x1800bb5c2  nop
0x1800bb5c3  mov     rdx, rbx
0x1800bb5c6  lea     rcx, [rbp+arg_18]
0x1800bb5ca  call    cs:__imp_?Create@IPlatformBitmapFlipRotator@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapFlipRotator@ARC@@@Mso@@AEBUIPlatformBitmap@2@W4ImageTransform@2@@Z; ARC::IPlatformBitmapFlipRotator::Create(ARC::IPlatformBitmap const &,ARC::ImageTransform)
0x1800bb5d0  mov     rcx, [rax]
0x1800bb5d3  mov     [rax], r12
0x1800bb5d6  mov     [rbp+arg_0], rbx
0x1800bb5da  mov     rbx, rcx
0x1800bb5dd  lea     rcx, [rbp+arg_0]; void *
0x1800bb5e1  call    ??1?$TCntPtr@VPlanarProjectionTexturer@Gfx@@@Mso@@QEAA@XZ; Mso::TCntPtr<Gfx::PlanarProjectionTexturer>::~TCntPtr<Gfx::PlanarProjectionTexturer>(void)
0x1800bb5e6  mov     rcx, [rbp+arg_18]
0x1800bb5ea  test    rcx, rcx
0x1800bb5ed  jz      loc_1800BB4B0
0x1800bb5f3  mov     [rbp+arg_18], r12
0x1800bb5f7  mov     rax, [rcx]
0x1800bb5fa  mov     rax, [rax+8]
0x1800bb5fe  call    cs:__guard_dispatch_icall_fptr
0x1800bb604  jmp     loc_1800BB4B0
0x1800bb609  mov     r10d, [r13+0]
0x1800bb60d  imul    r10d, [rbx+24h]
0x1800bb612  mov     rcx, [rbx+38h]
0x1800bb616  lea     rdx, [rbp+arg_0]
0x1800bb61a  call    ?GetWidth@?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@QEBA?AV?$TUnits@IUDevicePixels@Math@@@2@XZ; Math::TRect<Math::TUnits<uint,Math::DevicePixels>>::GetWidth(void)
0x1800bb61f  mov     r9d, [rax]
0x1800bb622  lea     rdx, [rbp+arg_18]
0x1800bb626  call    ?GetHeight@?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@QEBA?AV?$TUnits@IUDevicePixels@Math@@@2@XZ; Math::TRect<Math::TUnits<uint,Math::DevicePixels>>::GetHeight(void)
0x1800bb62b  mov     eax, [rax]
0x1800bb62d  imul    eax, r9d
0x1800bb631  xor     r12d, r12d
0x1800bb634  cmp     eax, r10d
0x1800bb637  jnb     short loc_1800BB648
0x1800bb639  mov     dil, r14b
0x1800bb63c  jmp     short loc_1800BB64B
0x1800bb63e  xor     r12d, r12d
0x1800bb641  mov     r14b, r12b
0x1800bb644  mov     rcx, [rbx+38h]
0x1800bb648  mov     dil, r12b
0x1800bb64b  mov     r8, rcx
0x1800bb64e  mov     rdx, r15
0x1800bb651  lea     rcx, [rbp+arg_18]
0x1800bb655  call    cs:__imp_?Create@IPlatformBitmapClipper@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapClipper@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TRect@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@@Z; ARC::IPlatformBitmapClipper::Create(ARC::IPlatformBitmap const &,Math::TRect<Math::TUnits<uint,Math::DevicePixels>> const &)
0x1800bb65b  mov     r15, [rax]
0x1800bb65e  mov     [rax], r12
0x1800bb661  mov     [rbp+arg_0], r15
0x1800bb665  mov     rcx, [rbp+arg_18]
0x1800bb669  test    rcx, rcx
0x1800bb66c  jz      short loc_1800BB67F
0x1800bb66e  mov     [rbp+arg_18], r12
0x1800bb672  mov     rax, [rcx]
0x1800bb675  mov     rax, [rax+8]
0x1800bb679  call    cs:__guard_dispatch_icall_fptr
0x1800bb67f  mov     rax, [rbx+38h]
0x1800bb683  cmp     [rax+20h], r12b
0x1800bb687  jz      short loc_1800BB6E4
0x1800bb689  test    dil, dil
0x1800bb68c  jz      short loc_1800BB6E4
0x1800bb68e  mov     rdx, r15; struct ARC::IPlatformBitmap *
0x1800bb691  lea     rcx, [rbp+var_20]; this
0x1800bb695  call    ??0ReadLock@IPlatformBitmap@ARC@@QEAA@AEBU12@_N@Z; ARC::IPlatformBitmap::ReadLock::ReadLock(ARC::IPlatformBitmap const &,bool)
0x1800bb69a  mov     [rbp+var_38], 0
0x1800bb6a2  lea     r8, [rbp+var_38]
0x1800bb6a6  lea     rdx, [rbp+var_20]
0x1800bb6aa  lea     rcx, [rbp+var_30]
0x1800bb6ae  xchg    ax, ax
0x1800bb6b0  call    ?Create@IPlatformBitmap@ARC@@SA?AV?$TCntPtr@UIPlatformBitmap@ARC@@@Mso@@AEBVConstPixelMap@2@AEBU?$TVector2@V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@Math@@@Z; ARC::IPlatformBitmap::Create(ARC::ConstPixelMap const &,Math::TVector2<Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>> const &)
0x1800bb6b5  mov     rdx, rax
0x1800bb6b8  lea     rcx, [rbp+arg_0]
0x1800bb6bc  call    ??4?$TCntPtr@UIPlatformBitmap@ARC@@@Mso@@QEAAAEAV01@$$QEAV01@@Z; Mso::TCntPtr<ARC::IPlatformBitmap>::operator=(Mso::TCntPtr<ARC::IPlatformBitmap> &&)
0x1800bb6c1  lea     rcx, [rbp+var_30]; void *
0x1800bb6c5  call    ??1?$TCntPtr@VPlanarProjectionTexturer@Gfx@@@Mso@@QEAA@XZ; Mso::TCntPtr<Gfx::PlanarProjectionTexturer>::~TCntPtr<Gfx::PlanarProjectionTexturer>(void)
0x1800bb6ca  mov     rcx, [rbp+var_8]
0x1800bb6ce  test    rcx, rcx
0x1800bb6d1  jz      short loc_1800BB6E4
0x1800bb6d3  mov     [rbp+var_8], r12
0x1800bb6d7  mov     rax, [rcx]
0x1800bb6da  mov     rax, [rax+8]
0x1800bb6de  call    cs:__guard_dispatch_icall_fptr
0x1800bb6e4  test    r14b, r14b
0x1800bb6e7  jz      short loc_1800BB728
0x1800bb6e9  mov     r9, [rbx+38h]
0x1800bb6ed  add     r9, 18h
0x1800bb6f1  mov     r8, r13
0x1800bb6f4  mov     rdx, [rbp+arg_0]
0x1800bb6f8  lea     rcx, [rbp+var_38]
0x1800bb6fc  call    cs:__imp_?Create@IPlatformBitmapScaler@ARC@@SA?AV?$TCntPtr@UIPlatformBitmapScaler@ARC@@@Mso@@AEBUIPlatformBitmap@2@AEBU?$TSize@V?$TUnits@IUDevicePixels@Math@@@Math@@@Math@@AEBW4InterpolationMode@2@@Z; ARC::IPlatformBitmapScaler::Create(ARC::IPlatformBitmap const &,Math::TSize<Math::TUnits<uint,Math::DevicePixels>> const &,ARC::InterpolationMode const &)
0x1800bb702  mov     rdx, rax
0x1800bb705  lea     rcx, [rbp+arg_0]
0x1800bb709  call    ??4?$TCntPtr@UIPlatformBitmap@ARC@@@Mso@@QEAAAEAV01@$$QEAV01@@Z; Mso::TCntPtr<ARC::IPlatformBitmap>::operator=(Mso::TCntPtr<ARC::IPlatformBitmap> &&)
0x1800bb70e  mov     rcx, [rbp+var_38]
0x1800bb712  test    rcx, rcx
0x1800bb715  jz      short loc_1800BB728
0x1800bb717  mov     [rbp+var_38], r12
0x1800bb71b  mov     rax, [rcx]
0x1800bb71e  mov     rax, [rax+8]
0x1800bb722  call    cs:__guard_dispatch_icall_fptr
0x1800bb728  mov     rax, [rbx+38h]
0x1800bb72c  cmp     [rax+20h], r12b
0x1800bb730  jz      short loc_1800BB78E
0x1800bb732  test    dil, dil
0x1800bb735  jnz     short loc_1800BB78E
0x1800bb737  mov     rdx, [rbp+arg_0]; struct ARC::IPlatformBitmap *
0x1800bb73b  lea     rcx, [rbp+var_20]; this
0x1800bb73f  call    ??0ReadLock@IPlatformBitmap@ARC@@QEAA@AEBU12@_N@Z; ARC::IPlatformBitmap::ReadLock::ReadLock(ARC::IPlatformBitmap const &,bool)
0x1800bb744  nop
0x1800bb745  mov     [rbp+arg_18], 0
0x1800bb74d  lea     r8, [rbp+arg_18]
0x1800bb751  lea     rdx, [rbp+var_20]
0x1800bb755  lea     rcx, [rbp+var_30]
0x1800bb759  call    ?Create@IPlatformBitmap@ARC@@SA?AV?$TCntPtr@UIPlatformBitmap@ARC@@@Mso@@AEBVConstPixelMap@2@AEBU?$TVector2@V?$TUnits@MU?$TUnitsRatioTag@UDevicePixels@Math@@UInches@2@@Math@@@Math@@@Math@@@Z; ARC::IPlatformBitmap::Create(ARC::ConstPixelMap const &,Math::TVector2<Math::TUnits<float,Math::TUnitsRatioTag<Math::DevicePixels,Math::Inches>>> const &)
0x1800bb75e  mov     rdx, rax
0x1800bb761  lea     rcx, [rbp+arg_0]
0x1800bb765  call    ??4?$TCntPtr@UIPlatformBitmap@ARC@@@Mso@@QEAAAEAV01@$$QEAV01@@Z; Mso::TCntPtr<ARC::IPlatformBitmap>::operator=(Mso::TCntPtr<ARC::IPlatformBitmap> &&)
0x1800bb76a  lea     rcx, [rbp+var_30]; void *
0x1800bb76e  call    ??1?$TCntPtr@VPlanarProjectionTexturer@Gfx@@@Mso@@QEAA@XZ; Mso::TCntPtr<Gfx::PlanarProjectionTexturer>::~TCntPtr<Gfx::PlanarProjectionTexturer>(void)
0x1800bb773  nop
0x1800bb774  mov     rcx, [rbp+var_8]
0x1800bb778  test    rcx, rcx
0x1800bb77b  jz      short loc_1800BB78E
0x1800bb77d  mov     [rbp+var_8], r12
0x1800bb781  mov     rax, [rcx]
0x1800bb784  mov     rax, [rax+8]
0x1800bb788  call    cs:__guard_dispatch_icall_fptr
0x1800bb78e  mov     rax, [rbp+arg_0]
0x1800bb792  mov     [rsi], rax
0x1800bb795  jmp     loc_1800BB485
```
