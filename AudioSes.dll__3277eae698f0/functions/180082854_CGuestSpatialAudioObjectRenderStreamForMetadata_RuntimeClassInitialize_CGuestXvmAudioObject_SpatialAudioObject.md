# CGuestSpatialAudioObjectRenderStreamForMetadata::RuntimeClassInitialize(CGuestXvmAudioObject *,SpatialAudioObjectRenderStreamForMetadataActivationParams2 const *,AudioClientConstructionParams const *,ulong)

- ea: `0x180082854`
- end: `0x180082e98`
- name: `?RuntimeClassInitialize@CGuestSpatialAudioObjectRenderStreamForMetadata@@QEAAJPEAVCGuestXvmAudioObject@@PEBUSpatialAudioObjectRenderStreamForMetadataActivationParams2@@PEBUAudioClientConstructionParams@@K@Z`
- size: `1604`
- prototype: `__int64 __fastcall(CGuestSpatialAudioObjectRenderStreamForMetadata *__hidden this, struct CGuestXvmAudioObject *, const struct SpatialAudioObjectRenderStreamForMetadataActivationParams2 *, const struct AudioClientConstructionParams *, unsigned int)`
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800fe7d0`

## callees

- `0x180007f00`
- `0x18000cd10`
- `0x18000d11c`
- `0x18000ebbc`
- `0x180010a90`
- `0x180025a04`
- `0x18004d8a8`
- `0x18007b934`
- `0x18007eaa8`
- `0x1800823c4`
- `0x180082854`
- `0x180087e80`
- `0x180087ed0`
- `0x180088ce8`
- `0x18008ac99`
- `0x1800994e8`
- `0x1800a42bc`
- `0x1800d65e0`
- `0x1800f9f84`
- `0x1800fc6ac`
- `0x1800fca8c`
- `0x1800fcc80`
- `0x180104fd8`
- `0x18010589c`
- `0x1801062d4`
- `0x18010cc24`
- `0x18010d1a4`
- `0x18010d3e8`
- `0x18010e7cc`
- `0x18011ddd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800829fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082cb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082d89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082e02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082e36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082e6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800829fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082cb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082d89`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082e02`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082e36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082e6d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CGuestSpatialAudioObjectRenderStreamForMetadata::RuntimeClassInitialize(
        CGuestSpatialAudioObjectRenderStreamForMetadata *this,
        struct CGuestXvmAudioObject *a2,
        const struct SpatialAudioObjectRenderStreamForMetadataActivationParams2 *a3,
        const struct AudioClientConstructionParams *a4,
        unsigned int a5)
{
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  void *v13; // rcx
  __int64 v14; // rdi
  CSpatialAudioObjectRenderStreamForMetadata *v15; // rsi
  __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rbx
  CSpatialAudioObjectRenderStreamForMetadata *v21; // rax
  CSpatialAudioObjectRenderStreamForMetadata *v22; // rdi
  CSpatialAudioObjectRenderStreamForMetadata *v23; // rax
  int MediaNotificationCallback; // edi
  __int64 v25; // rdx
  void *v26; // rcx
  int v27; // r8d
  struct ISpatialAudioObjectRenderStreamNotify *v28; // rdx
  __int64 v29; // rdx
  void *v30; // rcx
  __int64 v31; // rdx
  void *v32; // rcx
  void *v33; // rcx
  void *v34; // rcx
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  CSpatialAudioObjectRenderStreamForMetadata *v39; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B0h] BYREF
  struct ISpatialAudioMetadataClient *v41; // [rsp+58h] [rbp-A8h] BYREF
  int v42[2]; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v43; // [rsp+68h] [rbp-98h] BYREF
  struct AudioClientConstructionParams *v44; // [rsp+70h] [rbp-90h] BYREF
  LPVOID *p_pv; // [rsp+78h] [rbp-88h] BYREF
  __int64 v46; // [rsp+80h] [rbp-80h] BYREF
  char v47; // [rsp+88h] [rbp-78h]
  _BYTE v48[1568]; // [rsp+90h] [rbp-70h] BYREF
  _DWORD Src[2]; // [rsp+6B0h] [rbp+5B0h] BYREF
  unsigned int v50; // [rsp+6B8h] [rbp+5B8h]
  int v51; // [rsp+6BCh] [rbp+5BCh]
  int v52; // [rsp+6C0h] [rbp+5C0h]
  char v53[1548]; // [rsp+6C4h] [rbp+5C4h] BYREF
  _BYTE v54[1264]; // [rsp+CD0h] [rbp+BD0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1218h] [rbp+1118h]

  v44 = a4;
  Src[0] = 22;
  Src[1] = 1;
  v50 = *((_DWORD *)a2 + 12);
  v51 = 0;
  v52 = 132;
  memset_0(v53, 0, 0x600u);
  *(_QWORD *)v42 = 0;
  v8 = XvmActivateProxyAudioObject::CastTo<XvmActivateSpatialAudioStreamMetadata2>(Src, v42);
  if ( v8 < 0 )
  {
    v9 = 508;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v8,
      v35);
    return (unsigned int)v8;
  }
  v11 = *(_QWORD *)v42;
  **(_DWORD **)v42 = *((_DWORD *)a3 + 2);
  *(_DWORD *)(v11 + 4) = *((_DWORD *)a3 + 3);
  *(_DWORD *)(v11 + 8) = *((_DWORD *)a3 + 4);
  *(_DWORD *)(v11 + 12) = *((_DWORD *)a3 + 5);
  *(_OWORD *)(v11 + 16) = *((_OWORD *)a3 + 2);
  *(_DWORD *)(v11 + 32) = *((unsigned __int16 *)a3 + 24);
  *(_DWORD *)(v11 + 112) = *((_DWORD *)a3 + 17);
  v8 = CopyToXvmWaveFormatExtensible(*(const struct tWAVEFORMATEX **)a3, (struct XvmWaveFormatExtensible *)(v11 + 36));
  if ( v8 < 0 )
  {
    v9 = 518;
    goto LABEL_3;
  }
  pv = 0;
  *(_QWORD *)v42 = 0;
  p_pv = &pv;
  v46 = 0;
  v47 = 1;
  memcpy_0(v48, Src, 0x614u);
  v8 = CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(a2, v50, v48, &v46);
  wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v8 < 0 )
  {
    v12 = 522;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v8,
      (int)v42);
LABEL_10:
    v13 = pv;
    pv = 0;
    goto LABEL_11;
  }
  v39 = 0;
  v14 = *(_QWORD *)v42;
  v8 = XvmActivateProxyAudioObject::CastTo<XvmActivateSpatialAudioStreamMetadata2>(*(_QWORD *)v42, &v39);
  if ( v8 < 0 )
  {
    v12 = 525;
    goto LABEL_9;
  }
  memset_0(v54, 0, 0x4E8u);
  v15 = v39;
  v8 = PopulateSystemAudioStreamFromXvmMessage<XvmActivateSpatialAudioStreamMetadata2>(v39, v54);
  if ( v8 < 0 )
  {
    v12 = 528;
    goto LABEL_9;
  }
  v40 = 0;
  *(_QWORD *)v42 = &v40;
  v16 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(v42);
  v17 = Microsoft::WRL::AsWeak<CGuestSpatialAudioObjectRenderStreamForMetadata>(this, v16);
  v8 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x213,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v17,
      (int)v42);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v40);
    goto LABEL_10;
  }
  v18 = CGuestSpatialAudioRenderStreamBase::Initialize(
          (CGuestSpatialAudioObjectRenderStreamForMetadata *)((char *)this + 24),
          *(_DWORD *)(v14 + 12),
          (struct Microsoft::WRL::WeakRef *)&v40,
          (struct SYSTEM_AUDIO_STREAM *)v54);
  v8 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x215,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v18,
      (int)v42);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v40);
    v13 = pv;
    pv = 0;
    goto LABEL_11;
  }
  v41 = 0;
  v19 = ActivateSpatialAudioMetadataClient((char *)a3 + 32, *((_QWORD *)v44 + 3), &v41);
  v8 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x218,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v19,
      (int)v42);
LABEL_23:
    wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v41);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v40);
    v13 = pv;
    pv = 0;
LABEL_11:
    if ( v13 )
      CoTaskMemFree(v13);
    return (unsigned int)v8;
  }
  v20 = 0;
  *(_QWORD *)v42 = 0;
  v21 = (CSpatialAudioObjectRenderStreamForMetadata *)operator new[](
                                                        0x8C0u,
                                                        (const struct std::nothrow_t *)std::nothrow);
  v22 = v21;
  v39 = v21;
  if ( v21 )
  {
    memset_0(v21, 0, 0x8C0u);
    v23 = CSpatialAudioObjectRenderStreamForMetadata::CSpatialAudioObjectRenderStreamForMetadata(v22);
    Microsoft::WRL::ComPtr<CSpatialAudioObjectRenderStreamForHrtf>::Attach(v42, v23);
    v39 = 0;
    v20 = *(_QWORD *)v42;
  }
  Microsoft::WRL::Details::MakeAllocator<CAudioShellStateTracker>::~MakeAllocator<CAudioShellStateTracker>(&v39);
  *(_QWORD *)v42 = 0;
  v39 = (CSpatialAudioObjectRenderStreamForMetadata *)v20;
  Microsoft::WRL::ComPtr<CSpatialAudioObjectRenderStreamForHrtf>::InternalRelease(v42);
  if ( !v20 )
  {
    v8 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21B,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)0x8007000ELL,
      (int)v42);
LABEL_28:
    wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(&v39);
    goto LABEL_23;
  }
  MediaNotificationCallback = CSpatialAudioObjectRenderStreamForMetadata::InitializeInGuestMode(
                                (CSpatialAudioObjectRenderStreamForMetadata *)v20,
                                v44,
                                a3,
                                *((_DWORD *)v15 + 27),
                                v41,
                                *(_QWORD *)((char *)v15 + 740),
                                a5,
                                (struct SYSTEM_AUDIO_STREAM *)v54);
  if ( MediaNotificationCallback < 0 )
  {
    v25 = 546;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)MediaNotificationCallback,
      v36);
LABEL_32:
    wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(&v39);
    wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v41);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v40);
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
    v25 = 550;
    goto LABEL_31;
  }
  v28 = *(struct ISpatialAudioObjectRenderStreamNotify **)((char *)a3 + 60);
  if ( v28 )
  {
    MediaNotificationCallback = CSpatialAudioRenderStreamBase::AttachSpatialAudioObjectRenderStreamNotify(
                                  *((CSpatialAudioRenderStreamBase **)this + 64),
                                  v28);
    if ( MediaNotificationCallback < 0 )
    {
      v25 = 554;
      goto LABEL_31;
    }
  }
  v43 = 0;
  p_pv = &v43;
  v46 = 0;
  v47 = 1;
  LOBYTE(v27) = 0;
  MediaNotificationCallback = CGuestXvmAudioObject::SendAndValidateResponse<XvmPostActivateSpatialAudioStream>(
                                (int)this + 32,
                                *((_DWORD *)this + 20),
                                v27,
                                (unsigned int)&v46,
                                (__int64)&v44);
  wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( MediaNotificationCallback < 0 )
  {
    v29 = 562;
    goto LABEL_42;
  }
  MediaNotificationCallback = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<ISpatialAudioObjectRenderStreamForMetadata,ISpatialAudioObjectRenderStreamBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,CSpatialAudioRenderStreamBase>>(
                                v20,
                                &GUID_feaaf403_c1d8_450d_aa05_e0ccee7502a8,
                                (char *)this + 504);
  if ( MediaNotificationCallback < 0 )
  {
    v29 = 564;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)MediaNotificationCallback,
      v37);
    v30 = v43;
    v43 = 0;
    if ( v30 )
      CoTaskMemFree(v30);
    goto LABEL_32;
  }
  v8 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<ISpatialAudioObjectRenderStreamForMetadata,ISpatialAudioObjectRenderStreamBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,CSpatialAudioRenderStreamBase>>(
         v20,
         &GUID_bbc9c907_48d5_4a2e_a0c7_f7f0d67c1fb1,
         (char *)this + 544);
  if ( v8 < 0 )
  {
    v31 = 565;
    goto LABEL_48;
  }
  v8 = CGuestSpatialAudioRenderStreamBase::SetEventHandle(
         (CGuestSpatialAudioObjectRenderStreamForMetadata *)((char *)this + 24),
         (void *const *)a3 + 3);
  if ( v8 < 0 )
  {
    v31 = 567;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v8,
      v37);
    v32 = v43;
    v43 = 0;
    if ( v32 )
      CoTaskMemFree(v32);
    goto LABEL_28;
  }
  v33 = v43;
  v43 = 0;
  if ( v33 )
    CoTaskMemFree(v33);
  wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(&v39);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&v41);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v40);
  v34 = pv;
  pv = 0;
  if ( v34 )
    CoTaskMemFree(v34);
  return 0;
}

```

## disassembly

```asm
0x180082854  push    rbp
0x180082856  push    rbx
0x180082857  push    rsi
0x180082858  push    rdi
0x180082859  push    r12
0x18008285b  push    r13
0x18008285d  push    r14
0x18008285f  push    r15
0x180082861  lea     rbp, [rsp-10D8h]
0x180082869  mov     eax, 11D8h
0x18008286e  call    _alloca_probe
0x180082873  sub     rsp, rax
0x180082876  mov     rax, cs:__security_cookie
0x18008287d  xor     rax, rsp
0x180082880  mov     [rbp+1110h+var_50], rax
0x180082887  mov     [rsp+1210h+var_11A0], r9
0x18008288c  mov     r15, r8
0x18008288f  mov     rdi, rdx
0x180082892  mov     r14, rcx
0x180082895  mov     [rbp+1110h+Src], 16h
0x18008289f  mov     [rbp+1110h+var_B5C], 1
0x1800828a9  mov     eax, [rdx+30h]
0x1800828ac  mov     [rbp+1110h+var_B58], eax
0x1800828b2  xor     r12d, r12d
0x1800828b5  mov     [rbp+1110h+var_B54], r12d
0x1800828bc  mov     [rbp+1110h+var_B50], 84h
0x1800828c6  xor     edx, edx; Val
0x1800828c8  mov     r8d, 600h; Size
0x1800828ce  lea     rcx, [rbp+1110h+var_B4C]; void *
0x1800828d5  call    memset_0
0x1800828da  mov     qword ptr [rsp+1210h+var_11B0], r12
0x1800828df  lea     rdx, [rsp+1210h+var_11B0]
0x1800828e4  lea     rcx, [rbp+1110h+Src]
0x1800828eb  call    ??$CastTo@UXvmActivateSpatialAudioStreamMetadata2@@@XvmActivateProxyAudioObject@@QEAAJPEAPEAUXvmActivateSpatialAudioStreamMetadata2@@@Z; XvmActivateProxyAudioObject::CastTo<XvmActivateSpatialAudioStreamMetadata2>(XvmActivateSpatialAudioStreamMetadata2 * *)
0x1800828f0  mov     ebx, eax
0x1800828f2  test    eax, eax
0x1800828f4  jns     short loc_180082918
0x1800828f6  mov     edx, 1FCh; void *
0x1800828fb  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x180082902  mov     r9d, ebx; char *
0x180082905  mov     rcx, [rbp+1118h]; this
0x18008290c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082911  mov     eax, ebx
0x180082913  jmp     loc_180082E75
0x180082918  mov     eax, [r15+8]
0x18008291c  mov     rdx, qword ptr [rsp+1210h+var_11B0]
0x180082921  mov     [rdx], eax
0x180082923  mov     eax, [r15+0Ch]
0x180082927  mov     [rdx+4], eax
0x18008292a  mov     eax, [r15+10h]
0x18008292e  mov     [rdx+8], eax
0x180082931  mov     eax, [r15+14h]
0x180082935  mov     [rdx+0Ch], eax
0x180082938  movups  xmm0, xmmword ptr [r15+20h]
0x18008293d  movdqu  xmmword ptr [rdx+10h], xmm0
0x180082942  movzx   eax, word ptr [r15+30h]
0x180082947  mov     [rdx+20h], eax
0x18008294a  mov     eax, [r15+44h]
0x18008294e  mov     [rdx+70h], eax
0x180082951  add     rdx, 24h ; '$'; struct XvmWaveFormatExtensible *
0x180082955  mov     rcx, [r15]; Src
0x180082958  call    ?CopyToXvmWaveFormatExtensible@@YAJPEBUtWAVEFORMATEX@@PEAUXvmWaveFormatExtensible@@@Z; CopyToXvmWaveFormatExtensible(tWAVEFORMATEX const *,XvmWaveFormatExtensible *)
0x18008295d  mov     ebx, eax
0x18008295f  test    eax, eax
0x180082961  jns     short loc_18008296A
0x180082963  mov     edx, 206h
0x180082968  jmp     short loc_1800828FB
0x18008296a  mov     [rsp+1210h+pv], r12
0x18008296f  mov     qword ptr [rsp+1210h+var_11B0], r12
0x180082974  lea     rax, [rsp+1210h+pv]
0x180082979  mov     [rsp+1210h+var_1198], rax
0x18008297e  mov     [rbp+1110h+var_1190], r12
0x180082982  mov     [rbp+1110h+var_1188], 1
0x180082986  lea     rcx, [rbp+1110h+var_1180]; void *
0x18008298a  lea     rdx, [rbp+1110h+Src]; Src
0x180082991  mov     r8d, 614h; Size
0x180082997  call    memcpy_0
0x18008299c  lea     rax, [rsp+1210h+var_11B0]
0x1800829a1  mov     [rsp+1210h+var_11F0], rax; int
0x1800829a6  lea     r9, [rbp+1110h+var_1190]
0x1800829aa  lea     r8, [rbp+1110h+var_1180]
0x1800829ae  mov     edx, [rbp+1110h+var_B58]
0x1800829b4  mov     rcx, rdi
0x1800829b7  call    ??$SendAndValidateResponse@UXvmActivateProxyAudioObject@@@CGuestXvmAudioObject@@QEAAJIUXvmActivateProxyAudioObject@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(uint,XvmActivateProxyAudioObject,XvmMessage * *,XvmActivateProxyAudioObject * *)
0x1800829bc  mov     ebx, eax
0x1800829be  lea     rcx, [rsp+1210h+var_1198]
0x1800829c3  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1800829c8  test    ebx, ebx
0x1800829ca  jns     short loc_180082A06
0x1800829cc  mov     edx, 20Ah; void *
0x1800829d1  mov     rcx, [rbp+1118h]; this
0x1800829d8  mov     r9d, ebx; char *
0x1800829db  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x1800829e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800829e7  nop
0x1800829e8  mov     rcx, [rsp+1210h+pv]; pv
0x1800829ed  mov     [rsp+1210h+pv], r12
0x1800829f2  test    rcx, rcx
0x1800829f5  jz      loc_180082911
0x1800829fb  call    cs:__imp_CoTaskMemFree
0x180082a01  jmp     loc_180082911
0x180082a06  mov     [rsp+1210h+var_11C8], r12
0x180082a0b  lea     rdx, [rsp+1210h+var_11C8]
0x180082a10  mov     rdi, qword ptr [rsp+1210h+var_11B0]
0x180082a15  mov     rcx, rdi
0x180082a18  call    ??$CastTo@UXvmActivateSpatialAudioStreamMetadata2@@@XvmActivateProxyAudioObject@@QEAAJPEAPEAUXvmActivateSpatialAudioStreamMetadata2@@@Z; XvmActivateProxyAudioObject::CastTo<XvmActivateSpatialAudioStreamMetadata2>(XvmActivateSpatialAudioStreamMetadata2 * *)
0x180082a1d  mov     ebx, eax
0x180082a1f  test    eax, eax
0x180082a21  jns     short loc_180082A2A
0x180082a23  mov     edx, 20Dh
0x180082a28  jmp     short loc_1800829D1
0x180082a2a  xor     edx, edx; Val
0x180082a2c  mov     r8d, 4E8h; Size
0x180082a32  lea     rcx, [rbp+1110h+var_540]; void *
0x180082a39  call    memset_0
0x180082a3e  lea     rdx, [rbp+1110h+var_540]
0x180082a45  mov     rsi, [rsp+1210h+var_11C8]
0x180082a4a  mov     rcx, rsi
0x180082a4d  call    ??$PopulateSystemAudioStreamFromXvmMessage@UXvmActivateSpatialAudioStreamMetadata2@@@@YAJPEAUXvmActivateSpatialAudioStreamMetadata2@@PEAUSYSTEM_AUDIO_STREAM@@@Z; PopulateSystemAudioStreamFromXvmMessage<XvmActivateSpatialAudioStreamMetadata2>(XvmActivateSpatialAudioStreamMetadata2 *,SYSTEM_AUDIO_STREAM *)
0x180082a52  mov     ebx, eax
0x180082a54  test    eax, eax
0x180082a56  jns     short loc_180082A62
0x180082a58  mov     edx, 210h
0x180082a5d  jmp     loc_1800829D1
0x180082a62  mov     [rsp+1210h+var_11C0], r12
0x180082a67  lea     rax, [rsp+1210h+var_11C0]
0x180082a6c  mov     qword ptr [rsp+1210h+var_11B0], rax
0x180082a71  lea     rcx, [rsp+1210h+var_11B0]
0x180082a76  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x180082a7b  mov     rdx, rax
0x180082a7e  mov     rcx, r14
0x180082a81  call    ??$AsWeak@VCGuestSpatialAudioObjectRenderStreamForMetadata@@@WRL@Microsoft@@YAJPEAVCGuestSpatialAudioObjectRenderStreamForMetadata@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<CGuestSpatialAudioObjectRenderStreamForMetadata>(CGuestSpatialAudioObjectRenderStreamForMetadata *,Microsoft::WRL::WeakRef *)
0x180082a86  mov     ebx, eax
0x180082a88  test    eax, eax
0x180082a8a  jns     short loc_180082AB7
0x180082a8c  mov     rcx, [rbp+1118h]; this
0x180082a93  mov     r9d, eax; char *
0x180082a96  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x180082a9d  mov     edx, 213h; void *
0x180082aa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082aa7  nop
0x180082aa8  lea     rcx, [rsp+1210h+var_11C0]
0x180082aad  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180082ab2  jmp     loc_1800829E8
0x180082ab7  lea     r9, [rbp+1110h+var_540]; struct SYSTEM_AUDIO_STREAM *
0x180082abe  lea     r8, [rsp+1210h+var_11C0]; struct Microsoft::WRL::WeakRef *
0x180082ac3  mov     edx, [rdi+0Ch]; unsigned int
0x180082ac6  lea     rcx, [r14+18h]; this
0x180082aca  call    ?Initialize@CGuestSpatialAudioRenderStreamBase@@IEAAJIAEAVWeakRef@WRL@Microsoft@@PEAUSYSTEM_AUDIO_STREAM@@@Z; CGuestSpatialAudioRenderStreamBase::Initialize(uint,Microsoft::WRL::WeakRef &,SYSTEM_AUDIO_STREAM *)
0x180082acf  mov     ebx, eax
0x180082ad1  test    eax, eax
0x180082ad3  jns     short loc_180082B0F
0x180082ad5  mov     rcx, [rbp+1118h]; this
0x180082adc  mov     r9d, eax; char *
0x180082adf  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x180082ae6  mov     edx, 215h; void *
0x180082aeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082af0  nop
0x180082af1  lea     rcx, [rsp+1210h+var_11C0]
0x180082af6  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180082afb  nop
0x180082afc  mov     rcx, [rsp+1210h+pv]
0x180082b01  mov     [rsp+1210h+pv], 0
0x180082b0a  jmp     loc_1800829F2
0x180082b0f  mov     [rsp+1210h+var_11B8], 0
0x180082b18  lea     r8, [rsp+1210h+var_11B8]
0x180082b1d  mov     rdx, [rsp+1210h+var_11A0]
0x180082b22  mov     rdx, [rdx+18h]
0x180082b26  lea     rcx, [r15+20h]
0x180082b2a  call    ActivateSpatialAudioMetadataClient
0x180082b2f  mov     ebx, eax
0x180082b31  xor     r13d, r13d
0x180082b34  test    eax, eax
0x180082b36  jns     short loc_180082B79
0x180082b38  mov     rcx, [rbp+1118h]; this
0x180082b3f  mov     r9d, eax; char *
0x180082b42  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x180082b49  mov     edx, 218h; void *
0x180082b4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082b53  nop
0x180082b54  lea     rcx, [rsp+1210h+var_11B8]; void *
0x180082b59  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180082b5e  nop
0x180082b5f  lea     rcx, [rsp+1210h+var_11C0]
0x180082b64  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180082b69  nop
0x180082b6a  mov     rcx, [rsp+1210h+pv]
0x180082b6f  mov     [rsp+1210h+pv], r13
0x180082b74  jmp     loc_1800829F2
0x180082b79  mov     rbx, r13
0x180082b7c  mov     qword ptr [rsp+1210h+var_11B0], rbx
0x180082b81  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180082b88  mov     ecx, 8C0h; unsigned __int64
0x180082b8d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180082b92  mov     rdi, rax
0x180082b95  mov     [rsp+1210h+var_11C8], rax
0x180082b9a  test    rax, rax
0x180082b9d  jz      short loc_180082BCE
0x180082b9f  xor     edx, edx; Val
0x180082ba1  mov     r8d, 8C0h; Size
0x180082ba7  mov     rcx, rax; void *
0x180082baa  call    memset_0
0x180082baf  mov     rcx, rdi; this
0x180082bb2  call    ??0CSpatialAudioObjectRenderStreamForMetadata@@QEAA@XZ; CSpatialAudioObjectRenderStreamForMetadata::CSpatialAudioObjectRenderStreamForMetadata(void)
0x180082bb7  mov     rdx, rax
0x180082bba  lea     rcx, [rsp+1210h+var_11B0]
0x180082bbf  call    ?Attach@?$ComPtr@VCSpatialAudioObjectRenderStreamForHrtf@@@WRL@Microsoft@@QEAAXPEAVCSpatialAudioObjectRenderStreamForHrtf@@@Z; Microsoft::WRL::ComPtr<CSpatialAudioObjectRenderStreamForHrtf>::Attach(CSpatialAudioObjectRenderStreamForHrtf *)
0x180082bc4  mov     [rsp+1210h+var_11C8], r13
0x180082bc9  mov     rbx, qword ptr [rsp+1210h+var_11B0]
0x180082bce  lea     rcx, [rsp+1210h+var_11C8]
0x180082bd3  call    ??1?$MakeAllocator@VCAudioShellStateTracker@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CAudioShellStateTracker>::~MakeAllocator<CAudioShellStateTracker>(void)
0x180082bd8  mov     qword ptr [rsp+1210h+var_11B0], r13
0x180082bdd  mov     [rsp+1210h+var_11C8], rbx
0x180082be2  lea     rcx, [rsp+1210h+var_11B0]
0x180082be7  call    ?InternalRelease@?$ComPtr@VCSpatialAudioObjectRenderStreamForHrtf@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSpatialAudioObjectRenderStreamForHrtf>::InternalRelease(void)
0x180082bec  test    rbx, rbx
0x180082bef  jnz     short loc_180082C21
0x180082bf1  mov     rcx, [rbp+1118h]; this
0x180082bf8  mov     ebx, 8007000Eh
0x180082bfd  mov     r9d, ebx; char *
0x180082c00  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x180082c07  mov     edx, 21Bh; void *
0x180082c0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082c11  nop
0x180082c12  lea     rcx, [rsp+1210h+var_11C8]
0x180082c17  call    ??1?$com_ptr_t@VCSpatialAudioObjectRenderStreamForHrtf@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(void)
0x180082c1c  jmp     loc_180082B54
0x180082c21  mov     rcx, [rsp+1210h+var_11B8]
0x180082c26  lea     rax, [rbp+1110h+var_540]
0x180082c2d  mov     [rsp+1210h+var_11D8], rax; struct SYSTEM_AUDIO_STREAM *
0x180082c32  mov     eax, [rbp+1110h+arg_20]
0x180082c38  mov     [rsp+1210h+var_11E0], eax; unsigned int
0x180082c3c  mov     rax, [rsi+2E4h]
0x180082c43  mov     [rsp+1210h+var_11E8], rax; __int64
0x180082c48  mov     [rsp+1210h+var_11F0], rcx; int
0x180082c4d  mov     r9d, [rsi+6Ch]; unsigned int
0x180082c51  mov     r8, r15; struct SpatialAudioObjectRenderStreamForMetadataActivationParams2 *
0x180082c54  mov     rdx, [rsp+1210h+var_11A0]; struct AudioClientConstructionParams *
0x180082c59  mov     rcx, rbx; this
0x180082c5c  call    ?InitializeInGuestMode@CSpatialAudioObjectRenderStreamForMetadata@@QEAAJPEBUAudioClientConstructionParams@@PEBUSpatialAudioObjectRenderStreamForMetadataActivationParams2@@IPEAUISpatialAudioMetadataClient@@_JKPEAUSYSTEM_AUDIO_STREAM@@@Z; CSpatialAudioObjectRenderStreamForMetadata::InitializeInGuestMode(AudioClientConstructionParams const *,SpatialAudioObjectRenderStreamForMetadataActivationParams2 const *,uint,ISpatialAudioMetadataClient *,__int64,ulong,SYSTEM_AUDIO_STREAM *)
0x180082c61  mov     edi, eax
0x180082c63  test    eax, eax
0x180082c65  jns     short loc_180082CC0
0x180082c67  mov     edx, 222h; void *
0x180082c6c  mov     rcx, [rbp+1118h]; this
0x180082c73  mov     r9d, edi; char *
0x180082c76  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x180082c7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082c82  nop
0x180082c83  lea     rcx, [rsp+1210h+var_11C8]
0x180082c88  call    ??1?$com_ptr_t@VCSpatialAudioObjectRenderStreamForHrtf@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(void)
0x180082c8d  nop
0x180082c8e  lea     rcx, [rsp+1210h+var_11B8]; void *
0x180082c93  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180082c98  nop
0x180082c99  lea     rcx, [rsp+1210h+var_11C0]
0x180082c9e  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x180082ca3  nop
0x180082ca4  mov     rcx, [rsp+1210h+pv]; pv
0x180082ca9  mov     [rsp+1210h+pv], r13
0x180082cae  test    rcx, rcx
0x180082cb1  jz      short loc_180082CB9
0x180082cb3  call    cs:__imp_CoTaskMemFree
0x180082cb9  mov     eax, edi
0x180082cbb  jmp     loc_180082E75
0x180082cc0  lea     rsi, [rbx+18h]
0x180082cc4  mov     [r14+200h], rsi
0x180082ccb  lea     rcx, [r14+40h]
0x180082ccf  call    ?reset@?$com_ptr_t@UIMediaNotificationCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset(void)
0x180082cd4  lea     rdx, [r14+40h]; struct IMediaNotificationCallback **
0x180082cd8  mov     rcx, rsi; this
0x180082cdb  call    ?GetMediaNotificationCallback@CSpatialAudioRenderStreamBase@@QEAAJPEAPEAUIMediaNotificationCallback@@@Z; CSpatialAudioRenderStreamBase::GetMediaNotificationCallback(IMediaNotificationCallback * *)
0x180082ce0  mov     edi, eax
0x180082ce2  test    eax, eax
0x180082ce4  jns     short loc_180082CF0
0x180082ce6  mov     edx, 226h
0x180082ceb  jmp     loc_180082C6C
0x180082cf0  mov     rdx, [r15+3Ch]; struct ISpatialAudioObjectRenderStreamNotify *
0x180082cf4  test    rdx, rdx
0x180082cf7  jz      short loc_180082D15
0x180082cf9  mov     rcx, [r14+200h]; this
0x180082d00  call    ?AttachSpatialAudioObjectRenderStreamNotify@CSpatialAudioRenderStreamBase@@QEAAJPEAUISpatialAudioObjectRenderStreamNotify@@@Z; CSpatialAudioRenderStreamBase::AttachSpatialAudioObjectRenderStreamNotify(ISpatialAudioObjectRenderStreamNotify *)
0x180082d05  mov     edi, eax
0x180082d07  test    eax, eax
0x180082d09  jns     short loc_180082D15
0x180082d0b  mov     edx, 22Ah
0x180082d10  jmp     loc_180082C6C
0x180082d15  mov     [rsp+1210h+var_11A8], r13
0x180082d1a  lea     rax, [rsp+1210h+var_11A8]
0x180082d1f  mov     [rsp+1210h+var_1198], rax
0x180082d24  mov     [rbp+1110h+var_1190], r13
0x180082d28  mov     [rbp+1110h+var_1188], 1
0x180082d2c  mov     r8b, r13b
0x180082d2f  lea     rcx, [r14+20h]
0x180082d33  lea     rax, [rsp+1210h+var_11A0]
0x180082d38  mov     [rsp+1210h+var_11F0], rax; int
0x180082d3d  lea     r9, [rbp+1110h+var_1190]
0x180082d41  mov     edx, [r14+50h]
0x180082d45  call    ??$SendAndValidateResponse@UXvmPostActivateSpatialAudioStream@@@CGuestXvmAudioObject@@QEAAJIUXvmPostActivateSpatialAudioStream@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmPostActivateSpatialAudioStream>(uint,XvmPostActivateSpatialAudioStream,XvmMessage * *,XvmPostActivateSpatialAudioStream * *)
0x180082d4a  mov     edi, eax
  ... truncated ...
```
