# FSCloneMFMediaTypeWithSubtype(IMFMediaType *,_GUID const &,uint,IMFMediaType * *)

- ea: `0x18002545c`
- end: `0x1800259e3`
- name: `?FSCloneMFMediaTypeWithSubtype@@YAJPEAUIMFMediaType@@AEBU_GUID@@IPEAPEAU1@@Z`
- size: `1415`
- prototype: `__int64 __fastcall(struct IMFMediaType *, const struct _GUID *, char, struct IMFMediaType **)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025270`
- `0x18005fe80`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18002545c`
- `0x180025ed0`
- `0x180026364`
- `0x18002c008`
- `0x180044f30`
- `0x1800607cc`
- `0x180077010`

## import_xrefs

- `MFPlat!MFCreateMediaType` at `0x1800256b7`
- `MFPlat!MFCreateMediaType` at `0x1800256b7`
- `MFPlat!MFCreateVideoMediaType` at `0x180025543`
- `MFPlat!MFCreateVideoMediaType` at `0x180025543`

## pseudocode

```c
__int64 __fastcall FSCloneMFMediaTypeWithSubtype(
        struct IMFMediaType *a1,
        const struct _GUID *a2,
        char a3,
        struct IMFMediaType **a4)
{
  HRESULT v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // rdx
  const MFVIDEOFORMAT *v12; // rax
  HRESULT v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  IMFVideoMediaType *v16; // rdi
  HRESULT (__stdcall *QueryInterface)(IMFVideoMediaType *, const IID *const, void **); // rbx
  __int64 v18; // rax
  bool v19; // al
  char v20; // r9
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  IMFMediaType *ppMFType; // [rsp+30h] [rbp-40h] BYREF
  IMFVideoMediaType *ppIVideoMediaType; // [rsp+38h] [rbp-38h] BYREF
  int v27; // [rsp+40h] [rbp-30h] BYREF
  __int64 v28; // [rsp+48h] [rbp-28h] BYREF
  struct _GUID v29; // [rsp+50h] [rbp-20h] BYREF

  v28 = 0;
  ppMFType = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    v9 = -2147024809;
    if ( !g_wppLevels )
      return v9;
    v10 = 135;
    goto LABEL_4;
  }
  if ( a4 )
  {
    *a4 = 0;
    if ( ((__int64 (__fastcall *)(struct IMFMediaType *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
           a1,
           &GUID_b99f381f_a8f9_47a2_a5af_ca3a225a3890,
           &v28) < 0 )
    {
      wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&ppMFType);
      v8 = MFCreateMediaType(&ppMFType);
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_70;
        v10 = 140;
        goto LABEL_4;
      }
      v8 = ((__int64 (__fastcall *)(struct IMFMediaType *, IMFMediaType *))a1->lpVtbl->CopyAllItems)(a1, ppMFType);
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_70;
        v10 = 141;
        goto LABEL_4;
      }
    }
    else
    {
      ppIVideoMediaType = 0;
      v12 = (const MFVIDEOFORMAT *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 304LL))(v28);
      v13 = MFCreateVideoMediaType(v12, &ppIVideoMediaType);
      v9 = v13;
      if ( v13 < 0 )
      {
        if ( !g_wppLevels )
        {
LABEL_15:
          wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppIVideoMediaType);
          goto LABEL_70;
        }
        v14 = 137;
LABEL_14:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v13);
        goto LABEL_15;
      }
      v15 = (*(__int64 (__fastcall **)(__int64, IMFVideoMediaType *))(*(_QWORD *)v28 + 256LL))(v28, ppIVideoMediaType);
      v9 = v15;
      if ( v15 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 138, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v15);
        if ( ppIVideoMediaType )
          ((void (__fastcall *)(IMFVideoMediaType *))ppIVideoMediaType->lpVtbl->Release)(ppIVideoMediaType);
        goto LABEL_70;
      }
      v16 = ppIVideoMediaType;
      QueryInterface = ppIVideoMediaType->lpVtbl->QueryInterface;
      wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&ppMFType);
      v13 = ((__int64 (__fastcall *)(IMFVideoMediaType *, GUID *, IMFMediaType **))QueryInterface)(
              v16,
              &GUID_44ae0fa8_ea31_4109_8d2e_4cae4997c555,
              &ppMFType);
      v9 = v13;
      if ( v13 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_15;
        v14 = 139;
        goto LABEL_14;
      }
      wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppIVideoMediaType);
    }
    v18 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
      v18 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
    if ( v18 )
    {
      v27 = 0;
      v29 = GUID_00000000_0000_0000_0000_000000000000;
      v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, struct _GUID *))ppMFType->lpVtbl->GetGUID)(
             ppMFType,
             &MF_MT_SUBTYPE,
             &v29);
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_70;
        v10 = 142;
LABEL_4:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v8);
        goto LABEL_70;
      }
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_FrameServerDX12Support>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FrameServerDX12Support>::GetImpl'::`2'::impl);
      v19 = FSIsKnownCompressedFormat(&v29);
      if ( v20 )
      {
        if ( !v19 )
          goto LABEL_45;
        v21 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&MFVideoFormat_NV12.Data1;
        if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&MFVideoFormat_NV12.Data1 )
          v21 = *(_QWORD *)a2->Data4 - *(_QWORD *)MFVideoFormat_NV12.Data4;
        if ( v21 )
        {
          v22 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&MFVideoFormat_RGB32.Data1;
          if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&MFVideoFormat_RGB32.Data1 )
            v22 = *(_QWORD *)a2->Data4 - *(_QWORD *)MFVideoFormat_RGB32.Data4;
          if ( v22 )
          {
LABEL_45:
            v8 = -2147024809;
            v9 = -2147024809;
            if ( !g_wppLevels )
              goto LABEL_70;
            v10 = 143;
            goto LABEL_4;
          }
        }
      }
      else
      {
        if ( !v19 )
          goto LABEL_67;
        v23 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&MFVideoFormat_NV12.Data1;
        if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&MFVideoFormat_NV12.Data1 )
          v23 = *(_QWORD *)a2->Data4 - *(_QWORD *)MFVideoFormat_NV12.Data4;
        if ( v23 )
        {
LABEL_67:
          v8 = -2147024809;
          v9 = -2147024809;
          if ( !g_wppLevels )
            goto LABEL_70;
          v10 = 144;
          goto LABEL_4;
        }
      }
      v8 = MFGetAttribute2UINT32asUINT64(ppMFType, &MF_MT_FRAME_SIZE, &ppIVideoMediaType, &v27);
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_70;
        v10 = 145;
        goto LABEL_4;
      }
      if ( (v27 & 1) != 0 )
      {
        v9 = -1072875852;
        if ( !g_wppLevels )
          goto LABEL_70;
        v11 = 146;
        goto LABEL_9;
      }
      v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, const struct _GUID *))ppMFType->lpVtbl->SetGUID)(
             ppMFType,
             &MF_MT_SUBTYPE,
             a2);
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_70;
        v10 = 147;
        goto LABEL_4;
      }
      ((void (__fastcall *)(IMFMediaType *, const GUID *))ppMFType->lpVtbl->DeleteItem)(ppMFType, &MF_MT_COMPRESSED);
      ((void (__fastcall *)(IMFMediaType *, const GUID *))ppMFType->lpVtbl->DeleteItem)(ppMFType, &MF_MT_SAMPLE_SIZE);
      ((void (__fastcall *)(IMFMediaType *, const GUID *))ppMFType->lpVtbl->DeleteItem)(ppMFType, &MF_MT_AVG_BITRATE);
      ((void (__fastcall *)(IMFMediaType *, const GUID *))ppMFType->lpVtbl->DeleteItem)(ppMFType, &MF_MT_MPEG2_PROFILE);
      ((void (__fastcall *)(IMFMediaType *, const GUID *))ppMFType->lpVtbl->DeleteItem)(ppMFType, &MF_MT_MPEG2_LEVEL);
      ((void (__fastcall *)(IMFMediaType *, __int128 *))ppMFType->lpVtbl->DeleteItem)(ppMFType, &MF_MT_VIDEO_ROTATION);
      ((void (__fastcall *)(IMFMediaType *, const GUID *))ppMFType->lpVtbl->DeleteItem)(
        ppMFType,
        &MF_MT_MINIMUM_DISPLAY_APERTURE);
      v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
             ppMFType,
             &MF_MT_ALL_SAMPLES_INDEPENDENT,
             1);
      v9 = v8;
      if ( v8 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_70;
        v10 = 148;
        goto LABEL_4;
      }
      if ( a3 >= 0 )
      {
        v8 = ((__int64 (__fastcall *)(IMFMediaType *, const GUID *, __int64))ppMFType->lpVtbl->SetUINT32)(
               ppMFType,
               &MF_MT_VIDEO_NOMINAL_RANGE,
               1);
        v9 = v8;
        if ( v8 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_70;
          v10 = 149;
          goto LABEL_4;
        }
      }
    }
    *a4 = ppMFType;
    ppMFType = 0;
    goto LABEL_70;
  }
  v9 = -2147467261;
  if ( !g_wppLevels )
    return v9;
  v11 = 136;
LABEL_9:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v9);
LABEL_70:
  if ( ppMFType )
    ((void (__fastcall *)(IMFMediaType *))ppMFType->lpVtbl->Release)(ppMFType);
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  return v9;
}

```

## disassembly

```asm
0x18002545c  mov     [rsp-28h+arg_10], rbx
0x180025461  push    rbp
0x180025462  push    rsi
0x180025463  push    rdi
0x180025464  push    r14
0x180025466  push    r15
0x180025468  mov     rbp, rsp
0x18002546b  sub     rsp, 70h
0x18002546f  mov     rax, cs:__security_cookie
0x180025476  xor     rax, rsp
0x180025479  mov     [rbp+var_10], rax
0x18002547d  mov     [rbp+var_28], 0
0x180025485  mov     r14, r9
0x180025488  mov     [rbp+ppMFType], 0
0x180025490  mov     r15d, r8d
0x180025493  mov     rsi, rdx
0x180025496  mov     rdi, rcx
0x180025499  test    rcx, rcx
0x18002549c  jnz     short loc_1800254DA
0x18002549e  mov     eax, 80070057h
0x1800254a3  mov     ebx, eax
0x1800254a5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800254ac  jb      loc_1800259C1
0x1800254b2  mov     edx, 87h
0x1800254b7  mov     [rsp+70h+var_50], eax
0x1800254bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800254c2  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x1800254c9  xor     r9d, r9d
0x1800254cc  mov     rcx, [rcx+10h]
0x1800254d0  call    WPP_SF_qD
0x1800254d5  jmp     loc_180025997
0x1800254da  test    r14, r14
0x1800254dd  jnz     short loc_1800254FC
0x1800254df  mov     ebx, 80004003h
0x1800254e4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800254eb  jb      loc_1800259C1
0x1800254f1  mov     edx, 88h
0x1800254f6  mov     [rsp+70h+var_50], ebx
0x1800254fa  jmp     short loc_1800254BB
0x1800254fc  mov     qword ptr [r9], 0
0x180025503  lea     r8, [rbp+var_28]
0x180025507  mov     rax, [rcx]
0x18002550a  lea     rdx, _GUID_b99f381f_a8f9_47a2_a5af_ca3a225a3890
0x180025511  mov     rax, [rax]
0x180025514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025519  test    eax, eax
0x18002551b  js      loc_1800256AA
0x180025521  mov     rcx, [rbp+var_28]
0x180025525  mov     [rbp+ppIVideoMediaType], 0
0x18002552d  mov     rax, [rcx]
0x180025530  mov     rax, [rax+130h]
0x180025537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002553c  lea     rdx, [rbp+ppIVideoMediaType]; ppIVideoMediaType
0x180025540  mov     rcx, rax; pVideoFormat
0x180025543  call    cs:__imp_MFCreateVideoMediaType
0x180025549  mov     ebx, eax
0x18002554b  test    eax, eax
0x18002554d  jns     short loc_180025589
0x18002554f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025556  jb      short loc_18002557B
0x180025558  mov     edx, 89h
0x18002555d  mov     rcx, cs:WPP_GLOBAL_Control
0x180025564  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18002556b  xor     r9d, r9d
0x18002556e  mov     [rsp+70h+var_50], eax
0x180025572  mov     rcx, [rcx+10h]
0x180025576  call    WPP_SF_qD
0x18002557b  lea     rcx, [rbp+ppIVideoMediaType]
0x18002557f  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180025584  jmp     loc_180025997
0x180025589  mov     rcx, [rbp+var_28]
0x18002558d  mov     rdx, [rbp+ppIVideoMediaType]
0x180025591  mov     rax, [rcx]
0x180025594  mov     rax, [rax+100h]
0x18002559b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255a0  mov     ebx, eax
0x1800255a2  test    eax, eax
0x1800255a4  jns     short loc_1800255F0
0x1800255a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800255ad  jb      short loc_1800255D2
0x1800255af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255b6  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x1800255bd  mov     edx, 8Ah
0x1800255c2  mov     [rsp+70h+var_50], eax
0x1800255c6  xor     r9d, r9d
0x1800255c9  mov     rcx, [rcx+10h]
0x1800255cd  call    WPP_SF_qD
0x1800255d2  mov     rcx, [rbp+ppIVideoMediaType]
0x1800255d6  test    rcx, rcx
0x1800255d9  jz      loc_180025997
0x1800255df  mov     rax, [rcx]
0x1800255e2  mov     rax, [rax+10h]
0x1800255e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800255eb  jmp     loc_180025997
0x1800255f0  mov     rdi, [rbp+ppIVideoMediaType]
0x1800255f4  lea     rcx, [rbp+ppMFType]
0x1800255f8  mov     rax, [rdi]
0x1800255fb  mov     rbx, [rax]
0x1800255fe  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x180025603  lea     r8, [rbp+ppMFType]
0x180025607  mov     rcx, rdi
0x18002560a  lea     rdx, _GUID_44ae0fa8_ea31_4109_8d2e_4cae4997c555
0x180025611  mov     rax, rbx
0x180025614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025619  mov     ebx, eax
0x18002561b  test    eax, eax
0x18002561d  jns     short loc_180025636
0x18002561f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025626  jb      loc_18002557B
0x18002562c  mov     edx, 8Bh
0x180025631  jmp     loc_18002555D
0x180025636  lea     rcx, [rbp+ppIVideoMediaType]
0x18002563a  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18002563f  mov     rax, [rsi]
0x180025642  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180025649  jnz     short loc_180025656
0x18002564b  mov     rax, [rsi+8]
0x18002564f  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180025656  test    rax, rax
0x180025659  jz      loc_180025988
0x18002565f  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180025666  mov     rcx, [rbp+ppMFType]
0x18002566a  lea     r8, [rbp+var_20]
0x18002566e  lea     rdx, MF_MT_SUBTYPE
0x180025675  mov     [rbp+var_30], 0
0x18002567c  movdqu  xmmword ptr [rbp+var_20.Data1], xmm0
0x180025681  mov     rax, [rcx]
0x180025684  mov     rax, [rax+50h]
0x180025688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002568d  mov     ebx, eax
0x18002568f  test    eax, eax
0x180025691  jns     short loc_180025711
0x180025693  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002569a  jb      loc_180025997
0x1800256a0  mov     edx, 8Eh
0x1800256a5  jmp     loc_1800254B7
0x1800256aa  lea     rcx, [rbp+ppMFType]
0x1800256ae  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x1800256b3  lea     rcx, [rbp+ppMFType]; ppMFType
0x1800256b7  call    cs:__imp_MFCreateMediaType
0x1800256bd  mov     ebx, eax
0x1800256bf  test    eax, eax
0x1800256c1  jns     short loc_1800256DA
0x1800256c3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800256ca  jb      loc_180025997
0x1800256d0  mov     edx, 8Ch
0x1800256d5  jmp     loc_1800254B7
0x1800256da  mov     rax, [rdi]
0x1800256dd  mov     rcx, rdi
0x1800256e0  mov     rdx, [rbp+ppMFType]
0x1800256e4  mov     rax, [rax+100h]
0x1800256eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256f0  mov     ebx, eax
0x1800256f2  test    eax, eax
0x1800256f4  jns     loc_18002563F
0x1800256fa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025701  jb      loc_180025997
0x180025707  mov     edx, 8Dh
0x18002570c  jmp     loc_1800254B7
0x180025711  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FrameServerDX12Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FrameServerDX12Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FrameServerDX12Support> `wil::Feature<__WilFeatureTraits_Feature_FrameServerDX12Support>::GetImpl(void)'::`2'::impl
0x180025718  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FrameServerDX12Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FrameServerDX12Support>::__private_IsEnabled(void)
0x18002571d  lea     rcx, [rbp+var_20]; struct _GUID *
0x180025721  mov     r9b, al
0x180025724  call    ?FSIsKnownCompressedFormat@@YA_NAEBU_GUID@@@Z; FSIsKnownCompressedFormat(_GUID const &)
0x180025729  test    r9b, r9b
0x18002572c  jz      short loc_180025788
0x18002572e  test    al, al
0x180025730  jz      short loc_18002576A
0x180025732  mov     rax, [rsi]
0x180025735  sub     rax, qword ptr cs:MFVideoFormat_NV12.Data1
0x18002573c  jnz     short loc_180025749
0x18002573e  mov     rax, [rsi+8]
0x180025742  sub     rax, qword ptr cs:MFVideoFormat_NV12.Data4
0x180025749  test    rax, rax
0x18002574c  jz      short loc_1800257B0
0x18002574e  mov     rax, [rsi]
0x180025751  sub     rax, qword ptr cs:MFVideoFormat_RGB32.Data1
0x180025758  jnz     short loc_180025765
0x18002575a  mov     rax, [rsi+8]
0x18002575e  sub     rax, qword ptr cs:MFVideoFormat_RGB32.Data4
0x180025765  test    rax, rax
0x180025768  jz      short loc_1800257B0
0x18002576a  mov     eax, 80070057h
0x18002576f  mov     ebx, eax
0x180025771  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025778  jb      loc_180025997
0x18002577e  mov     edx, 8Fh
0x180025783  jmp     loc_1800254B7
0x180025788  test    al, al
0x18002578a  jz      loc_18002596E
0x180025790  mov     rax, [rsi]
0x180025793  sub     rax, qword ptr cs:MFVideoFormat_NV12.Data1
0x18002579a  jnz     short loc_1800257A7
0x18002579c  mov     rax, [rsi+8]
0x1800257a0  sub     rax, qword ptr cs:MFVideoFormat_NV12.Data4
0x1800257a7  test    rax, rax
0x1800257aa  jnz     loc_18002596E
0x1800257b0  mov     rcx, [rbp+ppMFType]
0x1800257b4  lea     r9, [rbp+var_30]
0x1800257b8  lea     r8, [rbp+ppIVideoMediaType]
0x1800257bc  lea     rdx, MF_MT_FRAME_SIZE
0x1800257c3  call    MFGetAttribute2UINT32asUINT64
0x1800257c8  mov     ebx, eax
0x1800257ca  test    eax, eax
0x1800257cc  jns     short loc_1800257E5
0x1800257ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800257d5  jb      loc_180025997
0x1800257db  mov     edx, 91h
0x1800257e0  jmp     loc_1800254B7
0x1800257e5  test    byte ptr [rbp+var_30], 1
0x1800257e9  jz      short loc_180025807
0x1800257eb  mov     ebx, 0C00D36B4h
0x1800257f0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800257f7  jb      loc_180025997
0x1800257fd  mov     edx, 92h
0x180025802  jmp     loc_1800254F6
0x180025807  mov     rcx, [rbp+ppMFType]
0x18002580b  lea     rdx, MF_MT_SUBTYPE
0x180025812  mov     r8, rsi
0x180025815  mov     rax, [rcx]
0x180025818  mov     rax, [rax+0C0h]
0x18002581f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025824  mov     ebx, eax
0x180025826  test    eax, eax
0x180025828  jns     short loc_180025841
0x18002582a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025831  jb      loc_180025997
0x180025837  mov     edx, 93h
0x18002583c  jmp     loc_1800254B7
0x180025841  mov     rcx, [rbp+ppMFType]
0x180025845  lea     rdx, MF_MT_COMPRESSED
0x18002584c  mov     rax, [rcx]
0x18002584f  mov     rax, [rax+98h]
0x180025856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002585b  mov     rcx, [rbp+ppMFType]
0x18002585f  lea     rdx, MF_MT_SAMPLE_SIZE
0x180025866  mov     rax, [rcx]
0x180025869  mov     rax, [rax+98h]
0x180025870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025875  mov     rcx, [rbp+ppMFType]
0x180025879  lea     rdx, MF_MT_AVG_BITRATE
0x180025880  mov     rax, [rcx]
0x180025883  mov     rax, [rax+98h]
0x18002588a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002588f  mov     rcx, [rbp+ppMFType]
0x180025893  lea     rdx, MF_MT_MPEG2_PROFILE
0x18002589a  mov     rax, [rcx]
0x18002589d  mov     rax, [rax+98h]
0x1800258a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258a9  mov     rcx, [rbp+ppMFType]
0x1800258ad  lea     rdx, MF_MT_MPEG2_LEVEL
0x1800258b4  mov     rax, [rcx]
0x1800258b7  mov     rax, [rax+98h]
0x1800258be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258c3  mov     rcx, [rbp+ppMFType]
0x1800258c7  lea     rdx, MF_MT_VIDEO_ROTATION
0x1800258ce  mov     rax, [rcx]
0x1800258d1  mov     rax, [rax+98h]
0x1800258d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258dd  mov     rcx, [rbp+ppMFType]
0x1800258e1  lea     rdx, MF_MT_MINIMUM_DISPLAY_APERTURE
0x1800258e8  mov     rax, [rcx]
0x1800258eb  mov     rax, [rax+98h]
0x1800258f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800258f7  mov     rcx, [rbp+ppMFType]
0x1800258fb  lea     rdx, MF_MT_ALL_SAMPLES_INDEPENDENT
0x180025902  mov     r8d, 1
0x180025908  mov     rax, [rcx]
0x18002590b  mov     rax, [rax+0A8h]
0x180025912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025917  mov     ebx, eax
0x180025919  test    eax, eax
0x18002591b  jns     short loc_180025930
0x18002591d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025924  jb      short loc_180025997
0x180025926  mov     edx, 94h
0x18002592b  jmp     loc_1800254B7
0x180025930  test    r15b, r15b
0x180025933  js      short loc_180025988
0x180025935  mov     rcx, [rbp+ppMFType]
0x180025939  lea     rdx, MF_MT_VIDEO_NOMINAL_RANGE
0x180025940  mov     r8d, 1
0x180025946  mov     rax, [rcx]
0x180025949  mov     rax, [rax+0A8h]
0x180025950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025955  mov     ebx, eax
0x180025957  test    eax, eax
0x180025959  jns     short loc_180025988
0x18002595b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180025962  jb      short loc_180025997
0x180025964  mov     edx, 95h
0x180025969  jmp     loc_1800254B7
0x18002596e  mov     eax, 80070057h
0x180025973  mov     ebx, eax
0x180025975  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002597c  jb      short loc_180025997
0x18002597e  mov     edx, 90h
0x180025983  jmp     loc_1800254B7
0x180025988  mov     rax, [rbp+ppMFType]
0x18002598c  mov     [r14], rax
  ... truncated ...
```
