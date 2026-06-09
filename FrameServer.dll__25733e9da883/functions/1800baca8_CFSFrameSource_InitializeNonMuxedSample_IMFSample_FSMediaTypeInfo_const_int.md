# CFSFrameSource::InitializeNonMuxedSample(IMFSample *,FSMediaTypeInfo const &,int)

- ea: `0x1800baca8`
- end: `0x1800bb2f9`
- name: `?InitializeNonMuxedSample@CFSFrameSource@@IEAAJPEAUIMFSample@@AEBUFSMediaTypeInfo@@H@Z`
- size: `1617`
- prototype: `__int64 __fastcall(CFSFrameSource *this, struct IMFAttributes *, const struct FSMediaTypeInfo *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ba558`

## callees

- `0x180004712`
- `0x18000478c`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x18000ad10`
- `0x1800ba3dc`
- `0x1800baca8`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bb05e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bb088`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bb05e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800bb088`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800bafca`
- `MFPlat!MFCreateMemoryBuffer` at `0x1800bafca`

## pseudocode

```c
__int64 __fastcall CFSFrameSource::InitializeNonMuxedSample(
        CFSFrameSource *this,
        struct IMFAttributes *a2,
        const struct FSMediaTypeInfo *a3,
        int a4)
{
  signed __int64 v8; // r15
  int v9; // edi
  struct IMFSampleVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetUINT64)(IMFSample *, IMFMediaBuffer **); // rbx
  void *p_Size; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r13
  struct IMFSampleVtbl *v16; // rax
  HRESULT (__stdcall *GetUnknown)(IMFSample *, const GUID *const, const IID *const, LPVOID *); // rbx
  struct IMFMediaType *v18; // rdi
  HRESULT (__stdcall *v19)(IMFMediaType *, const GUID *const, const IID *const, LPVOID *); // rbx
  struct IMFMediaBuffer *v20; // rdx
  HRESULT v21; // eax
  __int64 v22; // rdx
  _DWORD *v23; // rcx
  struct IMFSampleVtbl *v24; // rax
  HRESULT (__stdcall *v25)(IMFSample *, const GUID *const, const IID *const, LPVOID *); // rbx
  size_t v26; // rcx
  struct IMFSampleVtbl *v27; // rax
  HRESULT (__stdcall *v28)(IMFSample *, const GUID *const, const IID *const, LPVOID *); // rbx
  int v30; // [rsp+30h] [rbp-48h] BYREF
  IMFMediaBuffer *ppBuffer; // [rsp+38h] [rbp-40h] BYREF
  struct IMFMediaType *v32; // [rsp+40h] [rbp-38h] BYREF
  struct CFSMemStreamSource *v33; // [rsp+48h] [rbp-30h] BYREF
  struct CFSMemStreamSource *v34; // [rsp+50h] [rbp-28h] BYREF
  struct CFSMemStreamSource *v35; // [rsp+58h] [rbp-20h] BYREF
  void *v36; // [rsp+60h] [rbp-18h] BYREF
  size_t Size; // [rsp+C0h] [rbp+48h] BYREF

  v35 = 0;
  v34 = 0;
  v33 = 0;
  v8 = _InterlockedIncrement64(&qword_18010EEB0);
  v9 = (*(__int64 (__fastcall **)(CFSFrameSource *, __int64))(*(_QWORD *)this + 24LL))(this, 3);
  if ( v9 >= 0 )
  {
    lpVtbl = (struct IMFSampleVtbl *)a2->lpVtbl;
    Size = 0;
    v32 = 0;
    ((void (__fastcall *)(struct IMFAttributes *, __int64 *, GUID *, struct IMFMediaType **))lpVtbl->GetUnknown)(
      a2,
      MFSourceReader_SampleAttribute_MediaType,
      &GUID_44ae0fa8_ea31_4109_8d2e_4cae4997c555,
      &v32);
    GetUINT64 = (HRESULT (__stdcall *)(IMFSample *, IMFMediaBuffer **))a2->lpVtbl[1].GetUINT64;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&Size);
    v9 = ((__int64 (__fastcall *)(struct IMFAttributes *, size_t *))GetUINT64)(a2, &Size);
    if ( v9 < 0 )
      goto LABEL_3;
    v9 = ((__int64 (__fastcall *)(struct IMFAttributes *, __int64))a2->lpVtbl[1].Release)(
           a2,
           136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 56LL);
    if ( v9 < 0 )
      goto LABEL_3;
    v9 = ((__int64 (__fastcall *)(struct IMFAttributes *, __int64))a2->lpVtbl[1].GetItemType)(
           a2,
           136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 64LL);
    if ( v9 < 0 )
      goto LABEL_3;
    *(_QWORD *)(136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 40) = v8;
    *(_DWORD *)(136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 124) = 0;
    v13 = *((_QWORD *)this + 2);
    v14 = 136 * (*(unsigned int *)(v13 + 36) + 1LL);
    *(_OWORD *)(v14 + v13) = *(_OWORD *)a3;
    v15 = -(__int64)(a4 == 0) & 0x1000000000000000LL;
    *(_OWORD *)(v14 + v13 + 16) = *((_OWORD *)a3 + 1);
    *(_QWORD *)(v14 + v13 + 32) = *((_QWORD *)a3 + 4);
    *(_QWORD *)(136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 112) |= v15;
    v9 = CFSMemStreamSource::CreateInstance(
           (struct FSMemoryStream *)(*((_QWORD *)this + 2)
                                   + 40LL
                                   + 136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL)),
           (struct IMFMediaBuffer *)Size,
           a2,
           v32,
           &v35);
    if ( v9 < 0 )
      goto LABEL_3;
    if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add((char *)this + 32, v35) )
    {
      v9 = -2147024882;
LABEL_3:
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v32);
      p_Size = &Size;
LABEL_47:
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(p_Size);
      goto LABEL_48;
    }
    ++*(_DWORD *)(*((_QWORD *)this + 2) + 36LL);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v32);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&Size);
    v16 = (struct IMFSampleVtbl *)a2->lpVtbl;
    v32 = 0;
    ppBuffer = 0;
    GetUnknown = v16->GetUnknown;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v32);
    if ( ((int (__fastcall *)(struct IMFAttributes *, const GUID *, GUID *, struct IMFMediaType **))GetUnknown)(
           a2,
           &MFSampleExtension_CaptureMetadata,
           &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3,
           &v32) < 0
      || !v32 )
    {
      goto LABEL_38;
    }
    *(_QWORD *)(136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 40) = v8;
    *(_QWORD *)(136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 56) = 0;
    *(_QWORD *)(136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 64) = 0;
    *(_DWORD *)(136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 120) = 0;
    *(_DWORD *)(136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 124) = 1;
    *(_QWORD *)(136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 112) |= v15;
    v18 = v32;
    v19 = v32->lpVtbl->GetUnknown;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppBuffer);
    if ( ((int (__fastcall *)(struct IMFMediaType *, const GUID *, GUID *, IMFMediaBuffer **))v19)(
           v18,
           &MF_CAPTURE_METADATA_FRAME_RAWSTREAM,
           &GUID_045fa593_8799_42b8_bc8d_8968c6453507,
           &ppBuffer) >= 0 )
    {
      v20 = ppBuffer;
      if ( ppBuffer )
      {
LABEL_34:
        v9 = CFSMemStreamSource::CreateInstance(
               (struct FSMemoryStream *)(*((_QWORD *)this + 2)
                                       + 40LL
                                       + 136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL)),
               v20,
               (struct IMFAttributes *)v32,
               0,
               &v34);
        if ( v9 < 0 )
          goto LABEL_17;
        if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add((char *)this + 32, v34) )
        {
          v9 = -2147024882;
          goto LABEL_17;
        }
        ++*(_DWORD *)(*((_QWORD *)this + 2) + 36LL);
LABEL_38:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppBuffer);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v32);
        v24 = (struct IMFSampleVtbl *)a2->lpVtbl;
        v32 = 0;
        Size = 0;
        v25 = v24->GetUnknown;
        wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v32);
        if ( ((int (__fastcall *)(struct IMFAttributes *, const GUID *, GUID *, struct IMFMediaType **))v25)(
               a2,
               &MFSampleExtension_PhotoThumbnail,
               &GUID_045fa593_8799_42b8_bc8d_8968c6453507,
               &v32) >= 0 )
        {
          v26 = Size;
          v27 = (struct IMFSampleVtbl *)a2->lpVtbl;
          Size = 0;
          v28 = v27->GetUnknown;
          if ( v26 )
            (*(void (__fastcall **)(size_t))(*(_QWORD *)v26 + 16LL))(v26);
          if ( ((int (__fastcall *)(struct IMFAttributes *, const GUID *, GUID *, size_t *))v28)(
                 a2,
                 &MFSampleExtension_PhotoThumbnailMediaType,
                 &GUID_44ae0fa8_ea31_4109_8d2e_4cae4997c555,
                 &Size) >= 0 )
          {
            *(_QWORD *)(136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 40) = v8;
            *(_QWORD *)(136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 56) = 0;
            *(_QWORD *)(136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 64) = 0;
            *(_DWORD *)(136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 120) = 0;
            *(_DWORD *)(136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 124) = 2;
            *(_QWORD *)(136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL) + *((_QWORD *)this + 2) + 112) |= v15;
            v9 = CFSMemStreamSource::CreateInstance(
                   (struct FSMemoryStream *)(*((_QWORD *)this + 2)
                                           + 40LL
                                           + 136LL * *(unsigned int *)(*((_QWORD *)this + 2) + 36LL)),
                   (struct IMFMediaBuffer *)v32,
                   0,
                   (struct IMFMediaType *)Size,
                   &v33);
            if ( v9 >= 0 )
            {
              if ( (unsigned int)CTUnkArray<IMFMediaType>::Add((char *)this + 32, v33) )
                ++*(_DWORD *)(*((_QWORD *)this + 2) + 36LL);
              else
                v9 = -2147024882;
            }
          }
        }
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&Size);
        p_Size = &v32;
        goto LABEL_47;
      }
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppBuffer);
    v21 = MFCreateMemoryBuffer(8u, &ppBuffer);
    v9 = v21;
    if ( v21 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_17:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppBuffer);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v32);
        goto LABEL_48;
      }
      v22 = 34;
LABEL_16:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v22, WPP_4cc38aabc67231271a40771778f093a4_Traceguids, this, v21);
      goto LABEL_17;
    }
    v36 = 0;
    LODWORD(Size) = 0;
    v30 = 0;
    v21 = ((__int64 (__fastcall *)(IMFMediaBuffer *, void **, size_t *, int *))ppBuffer->lpVtbl->Lock)(
            ppBuffer,
            &v36,
            &Size,
            &v30);
    v9 = v21;
    if ( v21 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_17;
      v22 = 35;
      goto LABEL_16;
    }
    v23 = v36;
    if ( v36 )
    {
      if ( (unsigned int)Size >= 8uLL )
      {
        *(_DWORD *)v36 = 0x80000000;
        v23[1] = 0;
LABEL_27:
        v21 = ((__int64 (__fastcall *)(IMFMediaBuffer *))ppBuffer->lpVtbl->Unlock)(ppBuffer);
        v9 = v21;
        if ( v21 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_17;
          v22 = 36;
          goto LABEL_16;
        }
        v21 = ((__int64 (__fastcall *)(IMFMediaBuffer *, __int64))ppBuffer->lpVtbl->SetCurrentLength)(ppBuffer, 8);
        v9 = v21;
        if ( v21 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_17;
          v22 = 37;
          goto LABEL_16;
        }
        v20 = ppBuffer;
        goto LABEL_34;
      }
      memset_0(v36, 0, (unsigned int)Size);
      *(_DWORD *)_o__errno() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno() = 22;
    }
    invalid_parameter_noinfo();
    goto LABEL_27;
  }
LABEL_48:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v33);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v34);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v35);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800baca8  push    rbp
0x1800bacaa  push    rbx
0x1800bacab  push    rsi
0x1800bacac  push    rdi
0x1800bacad  push    r12
0x1800bacaf  push    r13
0x1800bacb1  push    r14
0x1800bacb3  push    r15
0x1800bacb5  mov     rbp, rsp
0x1800bacb8  sub     rsp, 78h
0x1800bacbc  xor     ebx, ebx
0x1800bacbe  mov     r13d, r9d
0x1800bacc1  mov     r12, r8
0x1800bacc4  mov     [rbp+var_20], rbx
0x1800bacc8  mov     r14, rdx
0x1800baccb  mov     [rbp+var_28], rbx
0x1800baccf  mov     rsi, rcx
0x1800bacd2  mov     [rbp+var_30], rbx
0x1800bacd6  lea     r15d, [rbx+1]
0x1800bacda  lock xadd cs:qword_18010EEB0, r15
0x1800bace3  mov     rax, [rcx]
0x1800bace6  lea     edx, [rbx+3]
0x1800bace9  inc     r15
0x1800bacec  mov     rax, [rax+18h]
0x1800bacf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bacf5  mov     edi, eax
0x1800bacf7  test    eax, eax
0x1800bacf9  js      loc_1800BB2CB
0x1800bacff  mov     rax, [r14]
0x1800bad02  lea     r9, [rbp+var_38]
0x1800bad06  lea     r8, _GUID_44ae0fa8_ea31_4109_8d2e_4cae4997c555
0x1800bad0d  mov     [rbp+Size], rbx
0x1800bad11  lea     rdx, MFSourceReader_SampleAttribute_MediaType
0x1800bad18  mov     [rbp+var_38], rbx
0x1800bad1c  mov     rcx, r14
0x1800bad1f  mov     rax, [rax+88h]
0x1800bad26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bad2b  mov     rax, [r14]
0x1800bad2e  lea     rcx, [rbp+Size]
0x1800bad32  mov     rbx, [rax+148h]
0x1800bad39  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800bad3e  lea     rdx, [rbp+Size]
0x1800bad42  mov     rcx, r14
0x1800bad45  mov     rax, rbx
0x1800bad48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bad4d  xor     ebx, ebx
0x1800bad4f  mov     edi, eax
0x1800bad51  test    eax, eax
0x1800bad53  jns     short loc_1800BAD67
0x1800bad55  lea     rcx, [rbp+var_38]; void *
0x1800bad59  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bad5e  lea     rcx, [rbp+Size]
0x1800bad62  jmp     loc_1800BB2C6
0x1800bad67  mov     rdx, [rsi+10h]
0x1800bad6b  mov     r8, [r14]
0x1800bad6e  mov     eax, [rdx+24h]
0x1800bad71  add     rdx, 38h ; '8'
0x1800bad75  imul    rcx, rax, 88h
0x1800bad7c  mov     rax, [r8+118h]
0x1800bad83  add     rdx, rcx
0x1800bad86  mov     rcx, r14
0x1800bad89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bad8e  mov     edi, eax
0x1800bad90  test    eax, eax
0x1800bad92  js      short loc_1800BAD55
0x1800bad94  mov     rdx, [rsi+10h]
0x1800bad98  mov     r8, [r14]
0x1800bad9b  mov     eax, [rdx+24h]
0x1800bad9e  add     rdx, 40h ; '@'
0x1800bada2  imul    rcx, rax, 88h
0x1800bada9  mov     rax, [r8+128h]
0x1800badb0  add     rdx, rcx
0x1800badb3  mov     rcx, r14
0x1800badb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800badbb  mov     edi, eax
0x1800badbd  test    eax, eax
0x1800badbf  js      short loc_1800BAD55
0x1800badc1  mov     rdx, [rsi+10h]
0x1800badc5  mov     eax, [rdx+24h]
0x1800badc8  imul    rcx, rax, 88h
0x1800badcf  mov     [rcx+rdx+28h], r15
0x1800badd4  mov     rdx, [rsi+10h]
0x1800badd8  mov     eax, [rdx+24h]
0x1800baddb  imul    rcx, rax, 88h
0x1800bade2  mov     [rcx+rdx+7Ch], ebx
0x1800bade6  mov     rdx, [rsi+10h]
0x1800badea  movups  xmm0, xmmword ptr [r12]
0x1800badef  mov     eax, [rdx+24h]
0x1800badf2  inc     rax
0x1800badf5  imul    rcx, rax, 88h
0x1800badfc  neg     r13d
0x1800badff  mov     rax, 1000000000000000h
0x1800bae09  sbb     r13, r13
0x1800bae0c  not     r13
0x1800bae0f  movups  xmmword ptr [rcx+rdx], xmm0
0x1800bae13  and     r13, rax
0x1800bae16  movups  xmm1, xmmword ptr [r12+10h]
0x1800bae1c  movups  xmmword ptr [rcx+rdx+10h], xmm1
0x1800bae21  movsd   xmm0, qword ptr [r12+20h]
0x1800bae28  movsd   qword ptr [rcx+rdx+20h], xmm0
0x1800bae2e  mov     rdx, [rsi+10h]
0x1800bae32  mov     eax, [rdx+24h]
0x1800bae35  imul    rcx, rax, 88h
0x1800bae3c  or      [rcx+rdx+70h], r13
0x1800bae41  mov     r8, [rsi+10h]
0x1800bae45  mov     r9, [rbp+var_38]; struct IMFMediaType *
0x1800bae49  mov     rdx, [rbp+Size]; struct IMFMediaBuffer *
0x1800bae4d  mov     eax, [r8+24h]
0x1800bae51  add     r8, 28h ; '('
0x1800bae55  imul    rcx, rax, 88h
0x1800bae5c  lea     rax, [rbp+var_20]
0x1800bae60  add     rcx, r8; struct FSMemoryStream *
0x1800bae63  mov     [rsp+78h+var_58], rax; struct CFSMemStreamSource **
0x1800bae68  mov     r8, r14; struct IMFAttributes *
0x1800bae6b  call    ?CreateInstance@CFSMemStreamSource@@SAJPEAUFSMemoryStream@@PEAUIMFMediaBuffer@@PEAUIMFAttributes@@PEAUIMFMediaType@@PEAPEAV1@@Z; CFSMemStreamSource::CreateInstance(FSMemoryStream *,IMFMediaBuffer *,IMFAttributes *,IMFMediaType *,CFSMemStreamSource * *)
0x1800bae70  mov     edi, eax
0x1800bae72  test    eax, eax
0x1800bae74  js      loc_1800BAD55
0x1800bae7a  mov     rdx, [rbp+var_20]
0x1800bae7e  lea     r12, [rsi+20h]
0x1800bae82  mov     rcx, r12
0x1800bae85  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x1800bae8a  lea     rcx, [rbp+var_38]; void *
0x1800bae8e  test    eax, eax
0x1800bae90  jnz     short loc_1800BAE9C
0x1800bae92  mov     edi, 8007000Eh
0x1800bae97  jmp     loc_1800BAD59
0x1800bae9c  mov     rax, [rsi+10h]
0x1800baea0  inc     dword ptr [rax+24h]
0x1800baea3  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800baea8  lea     rcx, [rbp+Size]; void *
0x1800baeac  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800baeb1  mov     rax, [r14]
0x1800baeb4  lea     rcx, [rbp+var_38]
0x1800baeb8  mov     [rbp+var_38], rbx
0x1800baebc  mov     [rbp+ppBuffer], rbx
0x1800baec0  mov     rbx, [rax+88h]
0x1800baec7  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800baecc  lea     r9, [rbp+var_38]
0x1800baed0  mov     rcx, r14
0x1800baed3  lea     r8, _GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3
0x1800baeda  mov     rax, rbx
0x1800baedd  lea     rdx, MFSampleExtension_CaptureMetadata
0x1800baee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baee9  xor     ebx, ebx
0x1800baeeb  test    eax, eax
0x1800baeed  js      loc_1800BB152
0x1800baef3  cmp     [rbp+var_38], rbx
0x1800baef7  jz      loc_1800BB152
0x1800baefd  mov     rdx, [rsi+10h]
0x1800baf01  mov     eax, [rdx+24h]
0x1800baf04  imul    rcx, rax, 88h
0x1800baf0b  mov     [rcx+rdx+28h], r15
0x1800baf10  mov     rdx, [rsi+10h]
0x1800baf14  mov     eax, [rdx+24h]
0x1800baf17  imul    rcx, rax, 88h
0x1800baf1e  mov     [rcx+rdx+38h], rbx
0x1800baf23  mov     rdx, [rsi+10h]
0x1800baf27  mov     eax, [rdx+24h]
0x1800baf2a  imul    rcx, rax, 88h
0x1800baf31  mov     [rcx+rdx+40h], rbx
0x1800baf36  mov     rdx, [rsi+10h]
0x1800baf3a  mov     eax, [rdx+24h]
0x1800baf3d  imul    rcx, rax, 88h
0x1800baf44  mov     [rcx+rdx+78h], ebx
0x1800baf48  mov     rdx, [rsi+10h]
0x1800baf4c  mov     eax, [rdx+24h]
0x1800baf4f  imul    rcx, rax, 88h
0x1800baf56  mov     dword ptr [rcx+rdx+7Ch], 1
0x1800baf5e  mov     rdx, [rsi+10h]
0x1800baf62  mov     eax, [rdx+24h]
0x1800baf65  imul    rcx, rax, 88h
0x1800baf6c  or      [rcx+rdx+70h], r13
0x1800baf71  lea     rcx, [rbp+ppBuffer]
0x1800baf75  mov     rdi, [rbp+var_38]
0x1800baf79  mov     rax, [rdi]
0x1800baf7c  mov     rbx, [rax+88h]
0x1800baf83  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800baf88  lea     r9, [rbp+ppBuffer]
0x1800baf8c  mov     rcx, rdi
0x1800baf8f  lea     r8, _GUID_045fa593_8799_42b8_bc8d_8968c6453507
0x1800baf96  mov     rax, rbx
0x1800baf99  lea     rdx, MF_CAPTURE_METADATA_FRAME_RAWSTREAM
0x1800bafa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bafa5  xor     ebx, ebx
0x1800bafa7  test    eax, eax
0x1800bafa9  js      short loc_1800BAFB8
0x1800bafab  mov     rdx, [rbp+ppBuffer]
0x1800bafaf  test    rdx, rdx
0x1800bafb2  jnz     loc_1800BB0FC
0x1800bafb8  lea     rcx, [rbp+ppBuffer]
0x1800bafbc  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800bafc1  lea     rdx, [rbp+ppBuffer]; ppBuffer
0x1800bafc5  mov     ecx, 8; cbMaxLength
0x1800bafca  call    cs:__imp_MFCreateMemoryBuffer
0x1800bafd0  mov     edi, eax
0x1800bafd2  test    eax, eax
0x1800bafd4  jns     short loc_1800BB019
0x1800bafd6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bafdd  jb      short loc_1800BB002
0x1800bafdf  mov     edx, 22h ; '"'
0x1800bafe4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bafeb  lea     r8, WPP_4cc38aabc67231271a40771778f093a4_Traceguids
0x1800baff2  mov     r9, rsi
0x1800baff5  mov     dword ptr [rsp+78h+var_58], eax
0x1800baff9  mov     rcx, [rcx+10h]
0x1800baffd  call    WPP_SF_qD
0x1800bb002  lea     rcx, [rbp+ppBuffer]; void *
0x1800bb006  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bb00b  lea     rcx, [rbp+var_38]; void *
0x1800bb00f  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bb014  jmp     loc_1800BB2CB
0x1800bb019  mov     rcx, [rbp+ppBuffer]
0x1800bb01d  lea     r9, [rbp+var_48]
0x1800bb021  mov     [rbp+var_18], rbx
0x1800bb025  lea     r8, [rbp+Size]
0x1800bb029  mov     dword ptr [rbp+Size], ebx
0x1800bb02c  lea     rdx, [rbp+var_18]
0x1800bb030  mov     [rbp+var_48], ebx
0x1800bb033  mov     rax, [rcx]
0x1800bb036  mov     rax, [rax+18h]
0x1800bb03a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb03f  mov     edi, eax
0x1800bb041  test    eax, eax
0x1800bb043  jns     short loc_1800BB055
0x1800bb045  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bb04c  jb      short loc_1800BB002
0x1800bb04e  mov     edx, 23h ; '#'
0x1800bb053  jmp     short loc_1800BAFE4
0x1800bb055  mov     rcx, [rbp+var_18]; void *
0x1800bb059  test    rcx, rcx
0x1800bb05c  jnz     short loc_1800BB06C
0x1800bb05e  call    cs:__imp__o__errno
0x1800bb064  mov     dword ptr [rax], 16h
0x1800bb06a  jmp     short loc_1800BB094
0x1800bb06c  mov     r8d, dword ptr [rbp+Size]; Size
0x1800bb070  cmp     r8, 8
0x1800bb074  jb      short loc_1800BB081
0x1800bb076  mov     dword ptr [rcx], 80000000h
0x1800bb07c  mov     [rcx+4], ebx
0x1800bb07f  jmp     short loc_1800BB099
0x1800bb081  xor     edx, edx; Val
0x1800bb083  call    memset_0
0x1800bb088  call    cs:__imp__o__errno
0x1800bb08e  mov     dword ptr [rax], 22h ; '"'
0x1800bb094  call    _invalid_parameter_noinfo
0x1800bb099  mov     rcx, [rbp+ppBuffer]
0x1800bb09d  mov     rax, [rcx]
0x1800bb0a0  mov     rax, [rax+20h]
0x1800bb0a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb0a9  mov     edi, eax
0x1800bb0ab  test    eax, eax
0x1800bb0ad  jns     short loc_1800BB0C6
0x1800bb0af  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bb0b6  jb      loc_1800BB002
0x1800bb0bc  mov     edx, 24h ; '$'
0x1800bb0c1  jmp     loc_1800BAFE4
0x1800bb0c6  mov     rcx, [rbp+ppBuffer]
0x1800bb0ca  mov     edx, 8
0x1800bb0cf  mov     rax, [rcx]
0x1800bb0d2  mov     rax, [rax+30h]
0x1800bb0d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb0db  mov     edi, eax
0x1800bb0dd  test    eax, eax
0x1800bb0df  jns     short loc_1800BB0F8
0x1800bb0e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800bb0e8  jb      loc_1800BB002
0x1800bb0ee  mov     edx, 25h ; '%'
0x1800bb0f3  jmp     loc_1800BAFE4
0x1800bb0f8  mov     rdx, [rbp+ppBuffer]; struct IMFMediaBuffer *
0x1800bb0fc  mov     r9, [rsi+10h]
0x1800bb100  mov     r8, [rbp+var_38]; struct IMFAttributes *
0x1800bb104  mov     eax, [r9+24h]
0x1800bb108  add     r9, 28h ; '('
0x1800bb10c  imul    rcx, rax, 88h
0x1800bb113  lea     rax, [rbp+var_28]
0x1800bb117  add     rcx, r9; struct FSMemoryStream *
0x1800bb11a  mov     [rsp+78h+var_58], rax; struct CFSMemStreamSource **
0x1800bb11f  xor     r9d, r9d; struct IMFMediaType *
0x1800bb122  call    ?CreateInstance@CFSMemStreamSource@@SAJPEAUFSMemoryStream@@PEAUIMFMediaBuffer@@PEAUIMFAttributes@@PEAUIMFMediaType@@PEAPEAV1@@Z; CFSMemStreamSource::CreateInstance(FSMemoryStream *,IMFMediaBuffer *,IMFAttributes *,IMFMediaType *,CFSMemStreamSource * *)
0x1800bb127  mov     edi, eax
0x1800bb129  test    eax, eax
0x1800bb12b  js      loc_1800BB002
0x1800bb131  mov     rdx, [rbp+var_28]
0x1800bb135  mov     rcx, r12
0x1800bb138  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x1800bb13d  test    eax, eax
0x1800bb13f  jnz     short loc_1800BB14B
0x1800bb141  mov     edi, 8007000Eh
0x1800bb146  jmp     loc_1800BB002
0x1800bb14b  mov     rax, [rsi+10h]
0x1800bb14f  inc     dword ptr [rax+24h]
0x1800bb152  lea     rcx, [rbp+ppBuffer]; void *
0x1800bb156  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bb15b  lea     rcx, [rbp+var_38]; void *
0x1800bb15f  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bb164  mov     rax, [r14]
0x1800bb167  lea     rcx, [rbp+var_38]
0x1800bb16b  mov     [rbp+var_38], rbx
0x1800bb16f  mov     [rbp+Size], rbx
  ... truncated ...
```
