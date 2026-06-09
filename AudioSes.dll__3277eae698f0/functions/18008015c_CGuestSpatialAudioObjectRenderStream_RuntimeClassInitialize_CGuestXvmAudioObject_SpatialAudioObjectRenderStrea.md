# CGuestSpatialAudioObjectRenderStream::RuntimeClassInitialize(CGuestXvmAudioObject *,SpatialAudioObjectRenderStreamActivationParams2 const *,AudioClientConstructionParams const *,ulong)

- ea: `0x18008015c`
- end: `0x18008071c`
- name: `?RuntimeClassInitialize@CGuestSpatialAudioObjectRenderStream@@QEAAJPEAVCGuestXvmAudioObject@@PEBUSpatialAudioObjectRenderStreamActivationParams2@@PEBUAudioClientConstructionParams@@K@Z`
- size: `1472`
- prototype: `__int64 __fastcall(CGuestSpatialAudioObjectRenderStream *__hidden this, struct CGuestXvmAudioObject *, const struct SpatialAudioObjectRenderStreamActivationParams2 *, const struct AudioClientConstructionParams *, unsigned int)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800fe588`

## callees

- `0x18000cd10`
- `0x18000d11c`
- `0x18000ebbc`
- `0x180010a90`
- `0x180025a04`
- `0x18004d8a8`
- `0x18007b934`
- `0x18007eaa8`
- `0x18008015c`
- `0x1800823c4`
- `0x180087e80`
- `0x180087ed0`
- `0x180088ce8`
- `0x18008ac99`
- `0x1800994e8`
- `0x1800a42bc`
- `0x1800f9e8c`
- `0x1800fc554`
- `0x1800fc934`
- `0x1800fcc80`
- `0x180104fd8`
- `0x18010589c`
- `0x18010600c`
- `0x18010ca1c`
- `0x18010cd28`
- `0x18010d3e8`
- `0x18010e7cc`
- `0x18011ddd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800802f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080525`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800805fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080670`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800806c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800806f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800802f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080525`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800805fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080670`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800806c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800806f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CGuestSpatialAudioObjectRenderStream::RuntimeClassInitialize(
        CGuestSpatialAudioObjectRenderStream *this,
        struct CGuestXvmAudioObject *a2,
        const struct SpatialAudioObjectRenderStreamActivationParams2 *a3,
        const struct AudioClientConstructionParams *a4,
        unsigned int a5)
{
  int v9; // ebx
  __int64 v10; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  void *v14; // rcx
  __int64 v15; // rdi
  CSpatialAudioObjectRenderStream *v16; // rsi
  __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rbx
  CSpatialAudioObjectRenderStream *v21; // rax
  CSpatialAudioObjectRenderStream *v22; // rdi
  CSpatialAudioObjectRenderStream *v23; // rax
  int MediaNotificationCallback; // edi
  __int64 v25; // rdx
  void *v26; // rcx
  int v27; // r8d
  struct ISpatialAudioObjectRenderStreamNotify *v28; // rdx
  __int64 v29; // rdx
  void *v30; // rcx
  __int64 v31; // rdx
  void *v32; // rcx
  bool v33; // zf
  void *v34; // rcx
  void *v35; // rcx
  int v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  CSpatialAudioObjectRenderStream *v40; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v41; // [rsp+40h] [rbp-C0h] BYREF
  int v42[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v43; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID *p_pv; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A0h] BYREF
  char v46; // [rsp+68h] [rbp-98h]
  _BYTE v47[1568]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD Src[2]; // [rsp+690h] [rbp+590h] BYREF
  unsigned int v49; // [rsp+698h] [rbp+598h]
  int v50; // [rsp+69Ch] [rbp+59Ch]
  int v51; // [rsp+6A0h] [rbp+5A0h]
  char v52[1548]; // [rsp+6A4h] [rbp+5A4h] BYREF
  _BYTE v53[1264]; // [rsp+CB0h] [rbp+BB0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+11F8h] [rbp+10F8h]

  Src[0] = 15;
  Src[1] = 1;
  v49 = *((_DWORD *)a2 + 12);
  v50 = 0;
  v51 = 130;
  memset_0(v52, 0, 0x600u);
  *(_QWORD *)v42 = 0;
  v9 = XvmActivateProxyAudioObject::CastTo<XvmActivateSpatialAudioStream2>(Src, v42);
  if ( v9 < 0 )
  {
    v10 = 340;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v9,
      v36);
    return (unsigned int)v9;
  }
  v12 = *(_QWORD *)v42;
  **(_DWORD **)v42 = *((_DWORD *)a3 + 2);
  *(_DWORD *)(v12 + 4) = *((_DWORD *)a3 + 3);
  *(_DWORD *)(v12 + 8) = *((_DWORD *)a3 + 4);
  *(_DWORD *)(v12 + 12) = *((_DWORD *)a3 + 5);
  *(_DWORD *)(v12 + 92) = *((_DWORD *)a3 + 10);
  v9 = CopyToXvmWaveFormatExtensible(*(const struct tWAVEFORMATEX **)a3, (struct XvmWaveFormatExtensible *)(v12 + 16));
  if ( v9 < 0 )
  {
    v10 = 348;
    goto LABEL_3;
  }
  pv = 0;
  *(_QWORD *)v42 = 0;
  p_pv = &pv;
  v45 = 0;
  v46 = 1;
  memcpy_0(v47, Src, 0x614u);
  v9 = CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(a2, v49, v47, &v45);
  wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v9 < 0 )
  {
    v13 = 352;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v9,
      (int)v42);
LABEL_10:
    v14 = pv;
    pv = 0;
    goto LABEL_11;
  }
  v40 = 0;
  v15 = *(_QWORD *)v42;
  v9 = XvmActivateProxyAudioObject::CastTo<XvmActivateSpatialAudioStream2>(*(_QWORD *)v42, &v40);
  if ( v9 < 0 )
  {
    v13 = 355;
    goto LABEL_9;
  }
  memset_0(v53, 0, 0x4E8u);
  v16 = v40;
  v9 = PopulateSystemAudioStreamFromXvmMessage<XvmActivateSpatialAudioStream2>(v40, v53);
  if ( v9 < 0 )
  {
    v13 = 358;
    goto LABEL_9;
  }
  v41 = 0;
  *(_QWORD *)v42 = &v41;
  v17 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(v42);
  v18 = Microsoft::WRL::AsWeak<CGuestSpatialAudioObjectRenderStream>(this, v17);
  v9 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x169,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v18,
      (int)v42);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v41);
    goto LABEL_10;
  }
  v19 = CGuestSpatialAudioRenderStreamBase::Initialize(
          (CGuestSpatialAudioObjectRenderStream *)((char *)this + 24),
          *(_DWORD *)(v15 + 12),
          (struct Microsoft::WRL::WeakRef *)&v41,
          (struct SYSTEM_AUDIO_STREAM *)v53);
  v9 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16B,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v19,
      (int)v42);
LABEL_21:
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v41);
    v14 = pv;
    pv = 0;
LABEL_11:
    if ( v14 )
      CoTaskMemFree(v14);
    return (unsigned int)v9;
  }
  v20 = 0;
  *(_QWORD *)v42 = 0;
  v21 = (CSpatialAudioObjectRenderStream *)operator new[](0x8C0u, (const struct std::nothrow_t *)std::nothrow);
  v22 = v21;
  v40 = v21;
  if ( v21 )
  {
    memset_0(v21, 0, 0x8C0u);
    v23 = CSpatialAudioObjectRenderStream::CSpatialAudioObjectRenderStream(v22);
    Microsoft::WRL::ComPtr<CSpatialAudioObjectRenderStreamForHrtf>::Attach(v42, v23);
    v40 = 0;
    v20 = *(_QWORD *)v42;
  }
  Microsoft::WRL::Details::MakeAllocator<CAudioShellStateTracker>::~MakeAllocator<CAudioShellStateTracker>(&v40);
  *(_QWORD *)v42 = 0;
  v40 = (CSpatialAudioObjectRenderStream *)v20;
  Microsoft::WRL::ComPtr<CSpatialAudioObjectRenderStreamForHrtf>::InternalRelease(v42);
  if ( !v20 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16E,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)0x8007000ELL,
      (int)v42);
    wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(&v40);
    goto LABEL_21;
  }
  MediaNotificationCallback = CSpatialAudioObjectRenderStream::InitializeInGuestMode(
                                (CSpatialAudioObjectRenderStream *)v20,
                                a4,
                                a3,
                                *((_DWORD *)v16 + 22),
                                a5,
                                (struct SYSTEM_AUDIO_STREAM *)v53);
  if ( MediaNotificationCallback < 0 )
  {
    v25 = 371;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)MediaNotificationCallback,
      v37);
LABEL_29:
    wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(&v40);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v41);
    v26 = pv;
    pv = 0;
    if ( v26 )
      CoTaskMemFree(v26);
    return (unsigned int)MediaNotificationCallback;
  }
  *((_QWORD *)this + 64) = v20 + 24;
  wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset((char *)this + 64);
  MediaNotificationCallback = CSpatialAudioRenderStreamBase::GetMediaNotificationCallback(
                                (CSpatialAudioRenderStreamBase *)(v20 + 24),
                                (struct IMediaNotificationCallback **)this + 8);
  if ( MediaNotificationCallback < 0 )
  {
    v25 = 375;
    goto LABEL_28;
  }
  v28 = (struct ISpatialAudioObjectRenderStreamNotify *)*((_QWORD *)a3 + 4);
  if ( v28 )
  {
    MediaNotificationCallback = CSpatialAudioRenderStreamBase::AttachSpatialAudioObjectRenderStreamNotify(
                                  *((CSpatialAudioRenderStreamBase **)this + 64),
                                  v28);
    if ( MediaNotificationCallback < 0 )
    {
      v25 = 379;
      goto LABEL_28;
    }
  }
  v43 = 0;
  p_pv = &v43;
  v45 = 0;
  v46 = 1;
  LOBYTE(v27) = 0;
  MediaNotificationCallback = CGuestXvmAudioObject::SendAndValidateResponse<XvmPostActivateSpatialAudioStream>(
                                (int)this + 32,
                                *((_DWORD *)this + 20),
                                v27,
                                (unsigned int)&v45,
                                (__int64)v42);
  wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( MediaNotificationCallback < 0 )
  {
    v29 = 387;
    goto LABEL_39;
  }
  MediaNotificationCallback = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<ISpatialAudioObjectRenderStream,ISpatialAudioObjectRenderStreamBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,CSpatialAudioRenderStreamBase>>(
                                v20,
                                &GUID_feaaf403_c1d8_450d_aa05_e0ccee7502a8,
                                (char *)this + 504);
  if ( MediaNotificationCallback < 0 )
  {
    v29 = 389;
LABEL_39:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)MediaNotificationCallback,
      v38);
    v30 = v43;
    v43 = 0;
    if ( v30 )
      CoTaskMemFree(v30);
    goto LABEL_29;
  }
  v9 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<ISpatialAudioObjectRenderStream,ISpatialAudioObjectRenderStreamBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,CSpatialAudioRenderStreamBase>>(
         v20,
         &GUID_bab5f473_b423_477b_85f5_b5a332a04153,
         (char *)this + 544);
  if ( v9 < 0 )
  {
    v31 = 390;
LABEL_45:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v9,
      v38);
    v32 = v43;
    v33 = v43 == 0;
    v43 = 0;
    if ( !v33 )
      CoTaskMemFree(v32);
    wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(&v40);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v41);
    v14 = pv;
    pv = 0;
    goto LABEL_11;
  }
  v9 = CGuestSpatialAudioRenderStreamBase::SetEventHandle(
         (CGuestSpatialAudioObjectRenderStream *)((char *)this + 24),
         (void *const *)a3 + 3);
  if ( v9 < 0 )
  {
    v31 = 392;
    goto LABEL_45;
  }
  v34 = v43;
  v43 = 0;
  if ( v34 )
    CoTaskMemFree(v34);
  wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(&v40);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v41);
  v35 = pv;
  pv = 0;
  if ( v35 )
    CoTaskMemFree(v35);
  return 0;
}

```

## disassembly

```asm
0x18008015c  push    rbp
0x18008015e  push    rbx
0x18008015f  push    rsi
0x180080160  push    rdi
0x180080161  push    r12
0x180080163  push    r13
0x180080165  push    r14
0x180080167  push    r15
0x180080169  lea     rbp, [rsp-10B8h]
0x180080171  mov     eax, 11B8h
0x180080176  call    _alloca_probe
0x18008017b  sub     rsp, rax
0x18008017e  mov     rax, cs:__security_cookie
0x180080185  xor     rax, rsp
0x180080188  mov     [rbp+10F0h+var_50], rax
0x18008018f  mov     r13, r9
0x180080192  mov     r15, r8
0x180080195  mov     rdi, rdx
0x180080198  mov     r14, rcx
0x18008019b  mov     [rbp+10F0h+Src], 0Fh
0x1800801a5  mov     [rbp+10F0h+var_B5C], 1
0x1800801af  mov     eax, [rdx+30h]
0x1800801b2  mov     [rbp+10F0h+var_B58], eax
0x1800801b8  xor     r12d, r12d
0x1800801bb  mov     [rbp+10F0h+var_B54], r12d
0x1800801c2  mov     [rbp+10F0h+var_B50], 82h
0x1800801cc  xor     edx, edx; Val
0x1800801ce  mov     r8d, 600h; Size
0x1800801d4  lea     rcx, [rbp+10F0h+var_B4C]; void *
0x1800801db  call    memset_0
0x1800801e0  mov     qword ptr [rsp+11F0h+var_11A8], r12
0x1800801e5  lea     rdx, [rsp+11F0h+var_11A8]
0x1800801ea  lea     rcx, [rbp+10F0h+Src]
0x1800801f1  call    ??$CastTo@UXvmActivateSpatialAudioStream2@@@XvmActivateProxyAudioObject@@QEAAJPEAPEAUXvmActivateSpatialAudioStream2@@@Z; XvmActivateProxyAudioObject::CastTo<XvmActivateSpatialAudioStream2>(XvmActivateSpatialAudioStream2 * *)
0x1800801f6  mov     ebx, eax
0x1800801f8  test    eax, eax
0x1800801fa  jns     short loc_18008021E
0x1800801fc  mov     edx, 154h; void *
0x180080201  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x180080208  mov     r9d, ebx; char *
0x18008020b  mov     rcx, [rbp+10F8h]; this
0x180080212  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080217  mov     eax, ebx
0x180080219  jmp     loc_1800806F9
0x18008021e  mov     eax, [r15+8]
0x180080222  mov     rdx, qword ptr [rsp+11F0h+var_11A8]
0x180080227  mov     [rdx], eax
0x180080229  mov     eax, [r15+0Ch]
0x18008022d  mov     [rdx+4], eax
0x180080230  mov     eax, [r15+10h]
0x180080234  mov     [rdx+8], eax
0x180080237  mov     eax, [r15+14h]
0x18008023b  mov     [rdx+0Ch], eax
0x18008023e  mov     eax, [r15+28h]
0x180080242  mov     [rdx+5Ch], eax
0x180080245  add     rdx, 10h; struct XvmWaveFormatExtensible *
0x180080249  mov     rcx, [r15]; Src
0x18008024c  call    ?CopyToXvmWaveFormatExtensible@@YAJPEBUtWAVEFORMATEX@@PEAUXvmWaveFormatExtensible@@@Z; CopyToXvmWaveFormatExtensible(tWAVEFORMATEX const *,XvmWaveFormatExtensible *)
0x180080251  mov     ebx, eax
0x180080253  test    eax, eax
0x180080255  jns     short loc_18008025E
0x180080257  mov     edx, 15Ch
0x18008025c  jmp     short loc_180080201
0x18008025e  mov     [rsp+11F0h+pv], r12
0x180080263  mov     qword ptr [rsp+11F0h+var_11A8], r12
0x180080268  lea     rax, [rsp+11F0h+pv]
0x18008026d  mov     [rsp+11F0h+var_1198], rax
0x180080272  mov     [rsp+11F0h+var_1190], r12
0x180080277  mov     [rsp+11F0h+var_1188], 1
0x18008027c  lea     rcx, [rsp+11F0h+var_1180]; void *
0x180080281  lea     rdx, [rbp+10F0h+Src]; Src
0x180080288  mov     r8d, 614h; Size
0x18008028e  call    memcpy_0
0x180080293  lea     rax, [rsp+11F0h+var_11A8]
0x180080298  mov     qword ptr [rsp+11F0h+var_11D0], rax; int
0x18008029d  lea     r9, [rsp+11F0h+var_1190]
0x1800802a2  lea     r8, [rsp+11F0h+var_1180]
0x1800802a7  mov     edx, [rbp+10F0h+var_B58]
0x1800802ad  mov     rcx, rdi
0x1800802b0  call    ??$SendAndValidateResponse@UXvmActivateProxyAudioObject@@@CGuestXvmAudioObject@@QEAAJIUXvmActivateProxyAudioObject@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(uint,XvmActivateProxyAudioObject,XvmMessage * *,XvmActivateProxyAudioObject * *)
0x1800802b5  mov     ebx, eax
0x1800802b7  lea     rcx, [rsp+11F0h+var_1198]
0x1800802bc  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800802c1  test    ebx, ebx
0x1800802c3  jns     short loc_1800802FF
0x1800802c5  mov     edx, 160h; void *
0x1800802ca  mov     rcx, [rbp+10F8h]; this
0x1800802d1  mov     r9d, ebx; char *
0x1800802d4  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x1800802db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800802e0  nop
0x1800802e1  mov     rcx, [rsp+11F0h+pv]; pv
0x1800802e6  mov     [rsp+11F0h+pv], r12
0x1800802eb  test    rcx, rcx
0x1800802ee  jz      loc_180080217
0x1800802f4  call    cs:__imp_CoTaskMemFree
0x1800802fa  jmp     loc_180080217
0x1800802ff  mov     [rsp+11F0h+var_11B8], r12
0x180080304  lea     rdx, [rsp+11F0h+var_11B8]
0x180080309  mov     rdi, qword ptr [rsp+11F0h+var_11A8]
0x18008030e  mov     rcx, rdi
0x180080311  call    ??$CastTo@UXvmActivateSpatialAudioStream2@@@XvmActivateProxyAudioObject@@QEAAJPEAPEAUXvmActivateSpatialAudioStream2@@@Z; XvmActivateProxyAudioObject::CastTo<XvmActivateSpatialAudioStream2>(XvmActivateSpatialAudioStream2 * *)
0x180080316  mov     ebx, eax
0x180080318  test    eax, eax
0x18008031a  jns     short loc_180080323
0x18008031c  mov     edx, 163h
0x180080321  jmp     short loc_1800802CA
0x180080323  xor     edx, edx; Val
0x180080325  mov     r8d, 4E8h; Size
0x18008032b  lea     rcx, [rbp+10F0h+var_540]; void *
0x180080332  call    memset_0
0x180080337  lea     rdx, [rbp+10F0h+var_540]
0x18008033e  mov     rsi, [rsp+11F0h+var_11B8]
0x180080343  mov     rcx, rsi
0x180080346  call    ??$PopulateSystemAudioStreamFromXvmMessage@UXvmActivateSpatialAudioStream2@@@@YAJPEAUXvmActivateSpatialAudioStream2@@PEAUSYSTEM_AUDIO_STREAM@@@Z; PopulateSystemAudioStreamFromXvmMessage<XvmActivateSpatialAudioStream2>(XvmActivateSpatialAudioStream2 *,SYSTEM_AUDIO_STREAM *)
0x18008034b  mov     ebx, eax
0x18008034d  test    eax, eax
0x18008034f  jns     short loc_18008035B
0x180080351  mov     edx, 166h
0x180080356  jmp     loc_1800802CA
0x18008035b  mov     [rsp+11F0h+var_11B0], r12
0x180080360  lea     rax, [rsp+11F0h+var_11B0]
0x180080365  mov     qword ptr [rsp+11F0h+var_11A8], rax
0x18008036a  lea     rcx, [rsp+11F0h+var_11A8]
0x18008036f  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x180080374  mov     rdx, rax
0x180080377  mov     rcx, r14
0x18008037a  call    ??$AsWeak@VCGuestSpatialAudioObjectRenderStream@@@WRL@Microsoft@@YAJPEAVCGuestSpatialAudioObjectRenderStream@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<CGuestSpatialAudioObjectRenderStream>(CGuestSpatialAudioObjectRenderStream *,Microsoft::WRL::WeakRef *)
0x18008037f  mov     ebx, eax
0x180080381  test    eax, eax
0x180080383  jns     short loc_1800803B0
0x180080385  mov     rcx, [rbp+10F8h]; this
0x18008038c  mov     r9d, eax; char *
0x18008038f  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x180080396  mov     edx, 169h; void *
0x18008039b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800803a0  nop
0x1800803a1  lea     rcx, [rsp+11F0h+var_11B0]
0x1800803a6  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800803ab  jmp     loc_1800802E1
0x1800803b0  lea     r9, [rbp+10F0h+var_540]; struct SYSTEM_AUDIO_STREAM *
0x1800803b7  lea     r8, [rsp+11F0h+var_11B0]; struct Microsoft::WRL::WeakRef *
0x1800803bc  mov     edx, [rdi+0Ch]; unsigned int
0x1800803bf  lea     rcx, [r14+18h]; this
0x1800803c3  call    ?Initialize@CGuestSpatialAudioRenderStreamBase@@IEAAJIAEAVWeakRef@WRL@Microsoft@@PEAUSYSTEM_AUDIO_STREAM@@@Z; CGuestSpatialAudioRenderStreamBase::Initialize(uint,Microsoft::WRL::WeakRef &,SYSTEM_AUDIO_STREAM *)
0x1800803c8  mov     ebx, eax
0x1800803ca  test    eax, eax
0x1800803cc  jns     short loc_180080408
0x1800803ce  mov     rcx, [rbp+10F8h]; this
0x1800803d5  mov     r9d, eax; char *
0x1800803d8  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x1800803df  mov     edx, 16Bh; void *
0x1800803e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800803e9  nop
0x1800803ea  lea     rcx, [rsp+11F0h+var_11B0]
0x1800803ef  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x1800803f4  nop
0x1800803f5  mov     rcx, [rsp+11F0h+pv]
0x1800803fa  mov     [rsp+11F0h+pv], 0
0x180080403  jmp     loc_1800802EB
0x180080408  xor     ebx, ebx
0x18008040a  mov     qword ptr [rsp+11F0h+var_11A8], rbx
0x18008040f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180080416  mov     ecx, 8C0h; unsigned __int64
0x18008041b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180080420  mov     rdi, rax
0x180080423  mov     [rsp+11F0h+var_11B8], rax
0x180080428  test    rax, rax
0x18008042b  jz      short loc_18008045C
0x18008042d  xor     edx, edx; Val
0x18008042f  mov     r8d, 8C0h; Size
0x180080435  mov     rcx, rax; void *
0x180080438  call    memset_0
0x18008043d  mov     rcx, rdi; this
0x180080440  call    ??0CSpatialAudioObjectRenderStream@@QEAA@XZ; CSpatialAudioObjectRenderStream::CSpatialAudioObjectRenderStream(void)
0x180080445  mov     rdx, rax
0x180080448  lea     rcx, [rsp+11F0h+var_11A8]
0x18008044d  call    ?Attach@?$ComPtr@VCSpatialAudioObjectRenderStreamForHrtf@@@WRL@Microsoft@@QEAAXPEAVCSpatialAudioObjectRenderStreamForHrtf@@@Z; Microsoft::WRL::ComPtr<CSpatialAudioObjectRenderStreamForHrtf>::Attach(CSpatialAudioObjectRenderStreamForHrtf *)
0x180080452  mov     [rsp+11F0h+var_11B8], rbx
0x180080457  mov     rbx, qword ptr [rsp+11F0h+var_11A8]
0x18008045c  lea     rcx, [rsp+11F0h+var_11B8]
0x180080461  call    ??1?$MakeAllocator@VCAudioShellStateTracker@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CAudioShellStateTracker>::~MakeAllocator<CAudioShellStateTracker>(void)
0x180080466  mov     qword ptr [rsp+11F0h+var_11A8], 0
0x18008046f  mov     [rsp+11F0h+var_11B8], rbx
0x180080474  lea     rcx, [rsp+11F0h+var_11A8]
0x180080479  call    ?InternalRelease@?$ComPtr@VCSpatialAudioObjectRenderStreamForHrtf@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSpatialAudioObjectRenderStreamForHrtf>::InternalRelease(void)
0x18008047e  test    rbx, rbx
0x180080481  jnz     short loc_1800804B3
0x180080483  mov     rcx, [rbp+10F8h]; this
0x18008048a  mov     ebx, 8007000Eh
0x18008048f  mov     r9d, ebx; char *
0x180080492  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x180080499  mov     edx, 16Eh; void *
0x18008049e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800804a3  nop
0x1800804a4  lea     rcx, [rsp+11F0h+var_11B8]
0x1800804a9  call    ??1?$com_ptr_t@VCSpatialAudioObjectRenderStreamForHrtf@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(void)
0x1800804ae  jmp     loc_1800803EA
0x1800804b3  lea     rax, [rbp+10F0h+var_540]
0x1800804ba  mov     [rsp+11F0h+var_11C8], rax; struct SYSTEM_AUDIO_STREAM *
0x1800804bf  mov     eax, [rbp+10F0h+arg_20]
0x1800804c5  mov     [rsp+11F0h+var_11D0], eax; int
0x1800804c9  mov     r9d, [rsi+58h]; unsigned int
0x1800804cd  mov     r8, r15; struct SpatialAudioObjectRenderStreamActivationParams2 *
0x1800804d0  mov     rdx, r13; struct AudioClientConstructionParams *
0x1800804d3  mov     rcx, rbx; this
0x1800804d6  call    ?InitializeInGuestMode@CSpatialAudioObjectRenderStream@@QEAAJPEBUAudioClientConstructionParams@@PEBUSpatialAudioObjectRenderStreamActivationParams2@@IKPEAUSYSTEM_AUDIO_STREAM@@@Z; CSpatialAudioObjectRenderStream::InitializeInGuestMode(AudioClientConstructionParams const *,SpatialAudioObjectRenderStreamActivationParams2 const *,uint,ulong,SYSTEM_AUDIO_STREAM *)
0x1800804db  mov     edi, eax
0x1800804dd  xor     r13d, r13d
0x1800804e0  test    eax, eax
0x1800804e2  jns     short loc_180080532
0x1800804e4  mov     edx, 173h; void *
0x1800804e9  mov     rcx, [rbp+10F8h]; this
0x1800804f0  mov     r9d, edi; char *
0x1800804f3  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x1800804fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800804ff  nop
0x180080500  lea     rcx, [rsp+11F0h+var_11B8]
0x180080505  call    ??1?$com_ptr_t@VCSpatialAudioObjectRenderStreamForHrtf@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(void)
0x18008050a  nop
0x18008050b  lea     rcx, [rsp+11F0h+var_11B0]
0x180080510  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180080515  nop
0x180080516  mov     rcx, [rsp+11F0h+pv]; pv
0x18008051b  mov     [rsp+11F0h+pv], r13
0x180080520  test    rcx, rcx
0x180080523  jz      short loc_18008052B
0x180080525  call    cs:__imp_CoTaskMemFree
0x18008052b  mov     eax, edi
0x18008052d  jmp     loc_1800806F9
0x180080532  lea     rsi, [rbx+18h]
0x180080536  mov     [r14+200h], rsi
0x18008053d  lea     rcx, [r14+40h]
0x180080541  call    ?reset@?$com_ptr_t@UIMediaNotificationCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset(void)
0x180080546  lea     rdx, [r14+40h]; struct IMediaNotificationCallback **
0x18008054a  mov     rcx, rsi; this
0x18008054d  call    ?GetMediaNotificationCallback@CSpatialAudioRenderStreamBase@@QEAAJPEAPEAUIMediaNotificationCallback@@@Z; CSpatialAudioRenderStreamBase::GetMediaNotificationCallback(IMediaNotificationCallback * *)
0x180080552  mov     edi, eax
0x180080554  test    eax, eax
0x180080556  jns     short loc_18008055F
0x180080558  mov     edx, 177h
0x18008055d  jmp     short loc_1800804E9
0x18008055f  mov     rdx, [r15+20h]; struct ISpatialAudioObjectRenderStreamNotify *
0x180080563  test    rdx, rdx
0x180080566  jz      short loc_180080584
0x180080568  mov     rcx, [r14+200h]; this
0x18008056f  call    ?AttachSpatialAudioObjectRenderStreamNotify@CSpatialAudioRenderStreamBase@@QEAAJPEAUISpatialAudioObjectRenderStreamNotify@@@Z; CSpatialAudioRenderStreamBase::AttachSpatialAudioObjectRenderStreamNotify(ISpatialAudioObjectRenderStreamNotify *)
0x180080574  mov     edi, eax
0x180080576  test    eax, eax
0x180080578  jns     short loc_180080584
0x18008057a  mov     edx, 17Bh
0x18008057f  jmp     loc_1800804E9
0x180080584  mov     [rsp+11F0h+var_11A0], r13
0x180080589  lea     rax, [rsp+11F0h+var_11A0]
0x18008058e  mov     [rsp+11F0h+var_1198], rax
0x180080593  mov     [rsp+11F0h+var_1190], r13
0x180080598  mov     [rsp+11F0h+var_1188], 1
0x18008059d  mov     r8b, r13b
0x1800805a0  lea     rcx, [r14+20h]
0x1800805a4  lea     rax, [rsp+11F0h+var_11A8]
0x1800805a9  mov     qword ptr [rsp+11F0h+var_11D0], rax; int
0x1800805ae  lea     r9, [rsp+11F0h+var_1190]
0x1800805b3  mov     edx, [r14+50h]
0x1800805b7  call    ??$SendAndValidateResponse@UXvmPostActivateSpatialAudioStream@@@CGuestXvmAudioObject@@QEAAJIUXvmPostActivateSpatialAudioStream@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmPostActivateSpatialAudioStream>(uint,XvmPostActivateSpatialAudioStream,XvmMessage * *,XvmPostActivateSpatialAudioStream * *)
0x1800805bc  mov     edi, eax
0x1800805be  lea     rcx, [rsp+11F0h+var_1198]
0x1800805c3  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800805c8  test    edi, edi
0x1800805ca  jns     short loc_180080606
0x1800805cc  mov     edx, 183h; void *
0x1800805d1  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x1800805d8  mov     r9d, edi; char *
0x1800805db  mov     rcx, [rbp+10F8h]; this
0x1800805e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800805e7  nop
0x1800805e8  mov     rcx, [rsp+11F0h+var_11A0]; pv
0x1800805ed  mov     [rsp+11F0h+var_11A0], r13
0x1800805f2  test    rcx, rcx
0x1800805f5  jz      loc_180080500
0x1800805fb  call    cs:__imp_CoTaskMemFree
0x180080601  jmp     loc_180080500
0x180080606  lea     r8, [r14+1F8h]
0x18008060d  lea     rdx, _GUID_feaaf403_c1d8_450d_aa05_e0ccee7502a8
0x180080614  mov     rcx, rbx
0x180080617  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$ChainInterfaces@UISpatialAudioObjectRenderStream@@UISpatialAudioObjectRenderStreamBase@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@VCSpatialAudioRenderStreamBase@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$ChainInterfaces@UISpatialAudioObjectRenderStream@@UISpatialAudioObjectRenderStreamBase@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@VCSpatialAudioRenderStreamBase@@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<ISpatialAudioObjectRenderStream,ISpatialAudioObjectRenderStreamBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,CSpatialAudioRenderStreamBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<ISpatialAudioObjectRenderStream,ISpatialAudioObjectRenderStreamBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,CSpatialAudioRenderStreamBase> *,_GUID const &,void * *)
0x18008061c  mov     edi, eax
0x18008061e  test    eax, eax
0x180080620  jns     short loc_180080629
0x180080622  mov     edx, 185h
0x180080627  jmp     short loc_1800805D1
0x180080629  lea     r8, [r14+220h]
0x180080630  lea     rdx, _GUID_bab5f473_b423_477b_85f5_b5a332a04153
0x180080637  mov     rcx, rbx
0x18008063a  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$ChainInterfaces@UISpatialAudioObjectRenderStream@@UISpatialAudioObjectRenderStreamBase@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@VCSpatialAudioRenderStreamBase@@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$ChainInterfaces@UISpatialAudioObjectRenderStream@@UISpatialAudioObjectRenderStreamBase@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@VCSpatialAudioRenderStreamBase@@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<ISpatialAudioObjectRenderStream,ISpatialAudioObjectRenderStreamBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,CSpatialAudioRenderStreamBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<ISpatialAudioObjectRenderStream,ISpatialAudioObjectRenderStreamBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,CSpatialAudioRenderStreamBase> *,_GUID const &,void * *)
0x18008063f  mov     ebx, eax
0x180080641  test    eax, eax
0x180080643  jns     short loc_18008069C
0x180080645  mov     edx, 186h; void *
0x18008064a  mov     r9d, ebx; char *
0x18008064d  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
  ... truncated ...
```
