# CGuestSpatialAudioObjectRenderStreamForHrtf::RuntimeClassInitialize(CGuestXvmAudioObject *,SpatialAudioHrtfActivationParams2 const *,AudioClientConstructionParams const *,ulong)

- ea: `0x18007b2e8`
- end: `0x18007b92c`
- name: `?RuntimeClassInitialize@CGuestSpatialAudioObjectRenderStreamForHrtf@@QEAAJPEAVCGuestXvmAudioObject@@PEBUSpatialAudioHrtfActivationParams2@@PEBUAudioClientConstructionParams@@K@Z`
- size: `1604`
- prototype: `__int64 __fastcall(CGuestSpatialAudioObjectRenderStreamForHrtf *__hidden this, struct CGuestXvmAudioObject *, const struct SpatialAudioHrtfActivationParams2 *, const struct AudioClientConstructionParams *, unsigned int)`
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800fe6ac`

## callees

- `0x18000cd10`
- `0x18000d11c`
- `0x18000ebbc`
- `0x180010a90`
- `0x180025a04`
- `0x18004d8a8`
- `0x18007b2e8`
- `0x18007b934`
- `0x18007eaa8`
- `0x1800823c4`
- `0x180087e80`
- `0x180087ed0`
- `0x180088ce8`
- `0x18008ac99`
- `0x1800994e8`
- `0x1800a42bc`
- `0x1800f9f08`
- `0x1800fc600`
- `0x1800fc9e0`
- `0x1800fcc80`
- `0x180104fd8`
- `0x18010589c`
- `0x180106170`
- `0x18010cb20`
- `0x18010cf60`
- `0x18010d3e8`
- `0x18010e7cc`
- `0x18011ddd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b735`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b80b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b880`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b8d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b901`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b735`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b80b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b880`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b8d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007b901`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CGuestSpatialAudioObjectRenderStreamForHrtf::RuntimeClassInitialize(
        CGuestSpatialAudioObjectRenderStreamForHrtf *this,
        struct CGuestXvmAudioObject *a2,
        const struct SpatialAudioHrtfActivationParams2 *a3,
        const struct AudioClientConstructionParams *a4,
        unsigned int a5)
{
  int v9; // ebx
  __int64 v10; // rdx
  __int64 v12; // rdx
  __int64 v13; // rax
  _OWORD *v14; // rax
  _DWORD *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  void *v18; // rcx
  __int64 v19; // rdi
  CSpatialAudioObjectRenderStreamForHrtf *v20; // rsi
  __int64 v21; // rax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rbx
  CSpatialAudioObjectRenderStreamForHrtf *v25; // rax
  CSpatialAudioObjectRenderStreamForHrtf *v26; // rdi
  CSpatialAudioObjectRenderStreamForHrtf *v27; // rax
  int MediaNotificationCallback; // edi
  __int64 v29; // rdx
  void *v30; // rcx
  int v31; // r8d
  struct ISpatialAudioObjectRenderStreamNotify *v32; // rdx
  __int64 v33; // rdx
  void *v34; // rcx
  __int64 v35; // rdx
  void *v36; // rcx
  bool v37; // zf
  void *v38; // rcx
  void *v39; // rcx
  int v40; // [rsp+20h] [rbp-E0h]
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  CSpatialAudioObjectRenderStreamForHrtf *v44; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+40h] [rbp-C0h] BYREF
  int v46[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v47; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID *p_pv; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+60h] [rbp-A0h] BYREF
  char v50; // [rsp+68h] [rbp-98h]
  _BYTE v51[1568]; // [rsp+70h] [rbp-90h] BYREF
  _DWORD Src[2]; // [rsp+690h] [rbp+590h] BYREF
  unsigned int v53; // [rsp+698h] [rbp+598h]
  int v54; // [rsp+69Ch] [rbp+59Ch]
  int v55; // [rsp+6A0h] [rbp+5A0h]
  char v56[1548]; // [rsp+6A4h] [rbp+5A4h] BYREF
  _BYTE v57[1264]; // [rsp+CB0h] [rbp+BB0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+11F8h] [rbp+10F8h]

  Src[0] = 16;
  Src[1] = 1;
  v53 = *((_DWORD *)a2 + 12);
  v54 = 0;
  v55 = 131;
  memset_0(v56, 0, 0x600u);
  *(_QWORD *)v46 = 0;
  v9 = XvmActivateProxyAudioObject::CastTo<XvmActivateSpatialAudioStreamHrtf2>(Src, v46);
  if ( v9 < 0 )
  {
    v10 = 413;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v9,
      v40);
    return (unsigned int)v9;
  }
  v12 = *(_QWORD *)v46;
  **(_DWORD **)v46 = *((_DWORD *)a3 + 2);
  *(_DWORD *)(v12 + 4) = *((_DWORD *)a3 + 3);
  *(_DWORD *)(v12 + 8) = *((_DWORD *)a3 + 4);
  *(_DWORD *)(v12 + 12) = *((_DWORD *)a3 + 5);
  *(_BYTE *)(v12 + 16) = *((_QWORD *)a3 + 5) != 0;
  *(_BYTE *)(v12 + 17) = *((_QWORD *)a3 + 6) != 0;
  *(_BYTE *)(v12 + 18) = *((_QWORD *)a3 + 7) != 0;
  *(_BYTE *)(v12 + 19) = *((_QWORD *)a3 + 8) != 0;
  *(_DWORD *)(v12 + 172) = *((_DWORD *)a3 + 18);
  v13 = *((_QWORD *)a3 + 5);
  if ( v13 )
  {
    *(_OWORD *)(v12 + 20) = *(_OWORD *)v13;
    *(_DWORD *)(v12 + 36) = *(_DWORD *)(v13 + 16);
  }
  v14 = (_OWORD *)*((_QWORD *)a3 + 6);
  if ( v14 )
    *(_OWORD *)(v12 + 40) = *v14;
  v15 = (_DWORD *)*((_QWORD *)a3 + 7);
  if ( v15 )
    *(_DWORD *)(v12 + 56) = *v15;
  v16 = *((_QWORD *)a3 + 8);
  if ( v16 )
  {
    *(_OWORD *)(v12 + 60) = *(_OWORD *)v16;
    *(_OWORD *)(v12 + 76) = *(_OWORD *)(v16 + 16);
    *(_DWORD *)(v12 + 92) = *(_DWORD *)(v16 + 32);
  }
  v9 = CopyToXvmWaveFormatExtensible(*(const struct tWAVEFORMATEX **)a3, (struct XvmWaveFormatExtensible *)(v12 + 96));
  if ( v9 < 0 )
  {
    v10 = 442;
    goto LABEL_3;
  }
  pv = 0;
  *(_QWORD *)v46 = 0;
  p_pv = &pv;
  v49 = 0;
  v50 = 1;
  memcpy_0(v51, Src, 0x614u);
  v9 = CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(a2, v53, v51, &v49);
  wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v9 < 0 )
  {
    v17 = 446;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v9,
      (int)v46);
LABEL_18:
    v18 = pv;
    pv = 0;
    goto LABEL_19;
  }
  v44 = 0;
  v19 = *(_QWORD *)v46;
  v9 = XvmActivateProxyAudioObject::CastTo<XvmActivateSpatialAudioStreamHrtf2>(*(_QWORD *)v46, &v44);
  if ( v9 < 0 )
  {
    v17 = 449;
    goto LABEL_17;
  }
  memset_0(v57, 0, 0x4E8u);
  v20 = v44;
  v9 = PopulateSystemAudioStreamFromXvmMessage<XvmActivateSpatialAudioStreamHrtf2>(v44, v57);
  if ( v9 < 0 )
  {
    v17 = 452;
    goto LABEL_17;
  }
  v45 = 0;
  *(_QWORD *)v46 = &v45;
  v21 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(v46);
  v22 = Microsoft::WRL::AsWeak<CGuestSpatialAudioObjectRenderStreamForHrtf>(this, v21);
  v9 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C7,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v22,
      (int)v46);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v45);
    goto LABEL_18;
  }
  v23 = CGuestSpatialAudioRenderStreamBase::Initialize(
          (CGuestSpatialAudioObjectRenderStreamForHrtf *)((char *)this + 24),
          *(_DWORD *)(v19 + 12),
          (struct Microsoft::WRL::WeakRef *)&v45,
          (struct SYSTEM_AUDIO_STREAM *)v57);
  v9 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C9,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v23,
      (int)v46);
LABEL_29:
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v45);
    v18 = pv;
    pv = 0;
LABEL_19:
    if ( v18 )
      CoTaskMemFree(v18);
    return (unsigned int)v9;
  }
  v24 = 0;
  *(_QWORD *)v46 = 0;
  v25 = (CSpatialAudioObjectRenderStreamForHrtf *)operator new[](0x8C0u, (const struct std::nothrow_t *)std::nothrow);
  v26 = v25;
  v44 = v25;
  if ( v25 )
  {
    memset_0(v25, 0, 0x8C0u);
    v27 = CSpatialAudioObjectRenderStreamForHrtf::CSpatialAudioObjectRenderStreamForHrtf(v26);
    Microsoft::WRL::ComPtr<CSpatialAudioObjectRenderStreamForHrtf>::Attach(v46, v27);
    v44 = 0;
    v24 = *(_QWORD *)v46;
  }
  Microsoft::WRL::Details::MakeAllocator<CAudioShellStateTracker>::~MakeAllocator<CAudioShellStateTracker>(&v44);
  *(_QWORD *)v46 = 0;
  v44 = (CSpatialAudioObjectRenderStreamForHrtf *)v24;
  Microsoft::WRL::ComPtr<CSpatialAudioObjectRenderStreamForHrtf>::InternalRelease(v46);
  if ( !v24 )
  {
    v9 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CC,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)0x8007000ELL,
      (int)v46);
    wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(&v44);
    goto LABEL_29;
  }
  MediaNotificationCallback = CSpatialAudioObjectRenderStreamForHrtf::InitializeInGuestMode(
                                (CSpatialAudioObjectRenderStreamForHrtf *)v24,
                                a4,
                                a3,
                                *((_DWORD *)v20 + 42),
                                a5,
                                (struct SYSTEM_AUDIO_STREAM *)v57);
  if ( MediaNotificationCallback < 0 )
  {
    v29 = 465;
LABEL_36:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)MediaNotificationCallback,
      v41);
LABEL_37:
    wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(&v44);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v45);
    v30 = pv;
    pv = 0;
    if ( v30 )
      CoTaskMemFree(v30);
    return (unsigned int)MediaNotificationCallback;
  }
  *((_QWORD *)this + 64) = v24 + 24;
  wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset((char *)this + 64);
  MediaNotificationCallback = CSpatialAudioRenderStreamBase::GetMediaNotificationCallback(
                                (CSpatialAudioRenderStreamBase *)(v24 + 24),
                                (struct IMediaNotificationCallback **)this + 8);
  if ( MediaNotificationCallback < 0 )
  {
    v29 = 469;
    goto LABEL_36;
  }
  v32 = (struct ISpatialAudioObjectRenderStreamNotify *)*((_QWORD *)a3 + 4);
  if ( v32 )
  {
    MediaNotificationCallback = CSpatialAudioRenderStreamBase::AttachSpatialAudioObjectRenderStreamNotify(
                                  *((CSpatialAudioRenderStreamBase **)this + 64),
                                  v32);
    if ( MediaNotificationCallback < 0 )
    {
      v29 = 473;
      goto LABEL_36;
    }
  }
  v47 = 0;
  p_pv = &v47;
  v49 = 0;
  v50 = 1;
  LOBYTE(v31) = 0;
  MediaNotificationCallback = CGuestXvmAudioObject::SendAndValidateResponse<XvmPostActivateSpatialAudioStream>(
                                (int)this + 32,
                                *((_DWORD *)this + 20),
                                v31,
                                (unsigned int)&v49,
                                (__int64)v46);
  wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( MediaNotificationCallback < 0 )
  {
    v33 = 481;
    goto LABEL_47;
  }
  MediaNotificationCallback = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<ISpatialAudioObjectRenderStreamForHrtf,ISpatialAudioObjectRenderStreamBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,CSpatialAudioRenderStreamBase>>(
                                v24,
                                &GUID_feaaf403_c1d8_450d_aa05_e0ccee7502a8,
                                (char *)this + 504);
  if ( MediaNotificationCallback < 0 )
  {
    v33 = 483;
LABEL_47:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)MediaNotificationCallback,
      v42);
    v34 = v47;
    v47 = 0;
    if ( v34 )
      CoTaskMemFree(v34);
    goto LABEL_37;
  }
  v9 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::ChainInterfaces<ISpatialAudioObjectRenderStreamForHrtf,ISpatialAudioObjectRenderStreamBase,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,CSpatialAudioRenderStreamBase>>(
         v24,
         &GUID_e08deef9_5363_406e_9fdc_080ee247bbe0,
         (char *)this + 544);
  if ( v9 < 0 )
  {
    v35 = 484;
LABEL_53:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"avcore\\audiocore\\client\\spatialaudioclient\\guestspatialaudiostream.cpp",
      (const char *)(unsigned int)v9,
      v42);
    v36 = v47;
    v37 = v47 == 0;
    v47 = 0;
    if ( !v37 )
      CoTaskMemFree(v36);
    wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(&v44);
    Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v45);
    v18 = pv;
    pv = 0;
    goto LABEL_19;
  }
  v9 = CGuestSpatialAudioRenderStreamBase::SetEventHandle(
         (CGuestSpatialAudioObjectRenderStreamForHrtf *)((char *)this + 24),
         (void *const *)a3 + 3);
  if ( v9 < 0 )
  {
    v35 = 486;
    goto LABEL_53;
  }
  v38 = v47;
  v47 = 0;
  if ( v38 )
    CoTaskMemFree(v38);
  wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(&v44);
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(&v45);
  v39 = pv;
  pv = 0;
  if ( v39 )
    CoTaskMemFree(v39);
  return 0;
}

```

## disassembly

```asm
0x18007b2e8  push    rbp
0x18007b2ea  push    rbx
0x18007b2eb  push    rsi
0x18007b2ec  push    rdi
0x18007b2ed  push    r12
0x18007b2ef  push    r13
0x18007b2f1  push    r14
0x18007b2f3  push    r15
0x18007b2f5  lea     rbp, [rsp-10B8h]
0x18007b2fd  mov     eax, 11B8h
0x18007b302  call    _alloca_probe
0x18007b307  sub     rsp, rax
0x18007b30a  mov     rax, cs:__security_cookie
0x18007b311  xor     rax, rsp
0x18007b314  mov     [rbp+10F0h+var_50], rax
0x18007b31b  mov     r13, r9
0x18007b31e  mov     r14, r8
0x18007b321  mov     rdi, rdx
0x18007b324  mov     r15, rcx
0x18007b327  mov     [rbp+10F0h+Src], 10h
0x18007b331  mov     [rbp+10F0h+var_B5C], 1
0x18007b33b  mov     eax, [rdx+30h]
0x18007b33e  mov     [rbp+10F0h+var_B58], eax
0x18007b344  xor     r12d, r12d
0x18007b347  mov     [rbp+10F0h+var_B54], r12d
0x18007b34e  mov     [rbp+10F0h+var_B50], 83h
0x18007b358  xor     edx, edx; Val
0x18007b35a  mov     r8d, 600h; Size
0x18007b360  lea     rcx, [rbp+10F0h+var_B4C]; void *
0x18007b367  call    memset_0
0x18007b36c  mov     qword ptr [rsp+11F0h+var_11A8], r12
0x18007b371  lea     rdx, [rsp+11F0h+var_11A8]
0x18007b376  lea     rcx, [rbp+10F0h+Src]
0x18007b37d  call    ??$CastTo@UXvmActivateSpatialAudioStreamHrtf2@@@XvmActivateProxyAudioObject@@QEAAJPEAPEAUXvmActivateSpatialAudioStreamHrtf2@@@Z; XvmActivateProxyAudioObject::CastTo<XvmActivateSpatialAudioStreamHrtf2>(XvmActivateSpatialAudioStreamHrtf2 * *)
0x18007b382  mov     ebx, eax
0x18007b384  test    eax, eax
0x18007b386  jns     short loc_18007B3AA
0x18007b388  mov     edx, 19Dh; void *
0x18007b38d  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x18007b394  mov     r9d, ebx; char *
0x18007b397  mov     rcx, [rbp+10F8h]; this
0x18007b39e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b3a3  mov     eax, ebx
0x18007b3a5  jmp     loc_18007B909
0x18007b3aa  mov     eax, [r14+8]
0x18007b3ae  mov     rdx, qword ptr [rsp+11F0h+var_11A8]
0x18007b3b3  mov     [rdx], eax
0x18007b3b5  mov     eax, [r14+0Ch]
0x18007b3b9  mov     [rdx+4], eax
0x18007b3bc  mov     eax, [r14+10h]
0x18007b3c0  mov     [rdx+8], eax
0x18007b3c3  mov     eax, [r14+14h]
0x18007b3c7  mov     [rdx+0Ch], eax
0x18007b3ca  cmp     [r14+28h], r12
0x18007b3ce  setnz   al
0x18007b3d1  mov     [rdx+10h], al
0x18007b3d4  cmp     [r14+30h], r12
0x18007b3d8  setnz   al
0x18007b3db  mov     [rdx+11h], al
0x18007b3de  cmp     [r14+38h], r12
0x18007b3e2  setnz   al
0x18007b3e5  mov     [rdx+12h], al
0x18007b3e8  cmp     [r14+40h], r12
0x18007b3ec  setnz   al
0x18007b3ef  mov     [rdx+13h], al
0x18007b3f2  mov     eax, [r14+48h]
0x18007b3f6  mov     [rdx+0ACh], eax
0x18007b3fc  mov     rax, [r14+28h]
0x18007b400  test    rax, rax
0x18007b403  jz      short loc_18007B412
0x18007b405  movups  xmm0, xmmword ptr [rax]
0x18007b408  movups  xmmword ptr [rdx+14h], xmm0
0x18007b40c  mov     eax, [rax+10h]
0x18007b40f  mov     [rdx+24h], eax
0x18007b412  mov     rax, [r14+30h]
0x18007b416  test    rax, rax
0x18007b419  jz      short loc_18007B423
0x18007b41b  movups  xmm0, xmmword ptr [rax]
0x18007b41e  movdqu  xmmword ptr [rdx+28h], xmm0
0x18007b423  mov     rax, [r14+38h]
0x18007b427  test    rax, rax
0x18007b42a  jz      short loc_18007B431
0x18007b42c  mov     eax, [rax]
0x18007b42e  mov     [rdx+38h], eax
0x18007b431  mov     rax, [r14+40h]
0x18007b435  test    rax, rax
0x18007b438  jz      short loc_18007B44F
0x18007b43a  movups  xmm0, xmmword ptr [rax]
0x18007b43d  movups  xmmword ptr [rdx+3Ch], xmm0
0x18007b441  movups  xmm1, xmmword ptr [rax+10h]
0x18007b445  movups  xmmword ptr [rdx+4Ch], xmm1
0x18007b449  mov     eax, [rax+20h]
0x18007b44c  mov     [rdx+5Ch], eax
0x18007b44f  add     rdx, 60h ; '`'; struct XvmWaveFormatExtensible *
0x18007b453  mov     rcx, [r14]; Src
0x18007b456  call    ?CopyToXvmWaveFormatExtensible@@YAJPEBUtWAVEFORMATEX@@PEAUXvmWaveFormatExtensible@@@Z; CopyToXvmWaveFormatExtensible(tWAVEFORMATEX const *,XvmWaveFormatExtensible *)
0x18007b45b  mov     ebx, eax
0x18007b45d  test    eax, eax
0x18007b45f  jns     short loc_18007B46B
0x18007b461  mov     edx, 1BAh
0x18007b466  jmp     loc_18007B38D
0x18007b46b  mov     [rsp+11F0h+pv], r12
0x18007b470  mov     qword ptr [rsp+11F0h+var_11A8], r12
0x18007b475  lea     rax, [rsp+11F0h+pv]
0x18007b47a  mov     [rsp+11F0h+var_1198], rax
0x18007b47f  mov     [rsp+11F0h+var_1190], r12
0x18007b484  mov     [rsp+11F0h+var_1188], 1
0x18007b489  lea     rcx, [rsp+11F0h+var_1180]; void *
0x18007b48e  lea     rdx, [rbp+10F0h+Src]; Src
0x18007b495  mov     r8d, 614h; Size
0x18007b49b  call    memcpy_0
0x18007b4a0  lea     rax, [rsp+11F0h+var_11A8]
0x18007b4a5  mov     qword ptr [rsp+11F0h+var_11D0], rax; int
0x18007b4aa  lea     r9, [rsp+11F0h+var_1190]
0x18007b4af  lea     r8, [rsp+11F0h+var_1180]
0x18007b4b4  mov     edx, [rbp+10F0h+var_B58]
0x18007b4ba  mov     rcx, rdi
0x18007b4bd  call    ??$SendAndValidateResponse@UXvmActivateProxyAudioObject@@@CGuestXvmAudioObject@@QEAAJIUXvmActivateProxyAudioObject@@PEAPEAUXvmMessage@@PEAPEAU1@@Z; CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(uint,XvmActivateProxyAudioObject,XvmMessage * *,XvmActivateProxyAudioObject * *)
0x18007b4c2  mov     ebx, eax
0x18007b4c4  lea     rcx, [rsp+11F0h+var_1198]
0x18007b4c9  call    ??1?$out_param_t@V?$unique_ptr@UXvmMessage@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18007b4ce  test    ebx, ebx
0x18007b4d0  jns     short loc_18007B50C
0x18007b4d2  mov     edx, 1BEh; void *
0x18007b4d7  mov     rcx, [rbp+10F8h]; this
0x18007b4de  mov     r9d, ebx; char *
0x18007b4e1  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x18007b4e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b4ed  nop
0x18007b4ee  mov     rcx, [rsp+11F0h+pv]; pv
0x18007b4f3  mov     [rsp+11F0h+pv], r12
0x18007b4f8  test    rcx, rcx
0x18007b4fb  jz      loc_18007B3A3
0x18007b501  call    cs:__imp_CoTaskMemFree
0x18007b507  jmp     loc_18007B3A3
0x18007b50c  mov     [rsp+11F0h+var_11B8], r12
0x18007b511  lea     rdx, [rsp+11F0h+var_11B8]
0x18007b516  mov     rdi, qword ptr [rsp+11F0h+var_11A8]
0x18007b51b  mov     rcx, rdi
0x18007b51e  call    ??$CastTo@UXvmActivateSpatialAudioStreamHrtf2@@@XvmActivateProxyAudioObject@@QEAAJPEAPEAUXvmActivateSpatialAudioStreamHrtf2@@@Z; XvmActivateProxyAudioObject::CastTo<XvmActivateSpatialAudioStreamHrtf2>(XvmActivateSpatialAudioStreamHrtf2 * *)
0x18007b523  mov     ebx, eax
0x18007b525  test    eax, eax
0x18007b527  jns     short loc_18007B530
0x18007b529  mov     edx, 1C1h
0x18007b52e  jmp     short loc_18007B4D7
0x18007b530  xor     edx, edx; Val
0x18007b532  mov     r8d, 4E8h; Size
0x18007b538  lea     rcx, [rbp+10F0h+var_540]; void *
0x18007b53f  call    memset_0
0x18007b544  lea     rdx, [rbp+10F0h+var_540]
0x18007b54b  mov     rsi, [rsp+11F0h+var_11B8]
0x18007b550  mov     rcx, rsi
0x18007b553  call    ??$PopulateSystemAudioStreamFromXvmMessage@UXvmActivateSpatialAudioStreamHrtf2@@@@YAJPEAUXvmActivateSpatialAudioStreamHrtf2@@PEAUSYSTEM_AUDIO_STREAM@@@Z; PopulateSystemAudioStreamFromXvmMessage<XvmActivateSpatialAudioStreamHrtf2>(XvmActivateSpatialAudioStreamHrtf2 *,SYSTEM_AUDIO_STREAM *)
0x18007b558  mov     ebx, eax
0x18007b55a  test    eax, eax
0x18007b55c  jns     short loc_18007B568
0x18007b55e  mov     edx, 1C4h
0x18007b563  jmp     loc_18007B4D7
0x18007b568  mov     [rsp+11F0h+var_11B0], r12
0x18007b56d  lea     rax, [rsp+11F0h+var_11B0]
0x18007b572  mov     qword ptr [rsp+11F0h+var_11A8], rax
0x18007b577  lea     rcx, [rsp+11F0h+var_11A8]
0x18007b57c  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18007b581  mov     rdx, rax
0x18007b584  mov     rcx, r15
0x18007b587  call    ??$AsWeak@VCGuestSpatialAudioObjectRenderStreamForHrtf@@@WRL@Microsoft@@YAJPEAVCGuestSpatialAudioObjectRenderStreamForHrtf@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<CGuestSpatialAudioObjectRenderStreamForHrtf>(CGuestSpatialAudioObjectRenderStreamForHrtf *,Microsoft::WRL::WeakRef *)
0x18007b58c  mov     ebx, eax
0x18007b58e  test    eax, eax
0x18007b590  jns     short loc_18007B5BD
0x18007b592  mov     rcx, [rbp+10F8h]; this
0x18007b599  mov     r9d, eax; char *
0x18007b59c  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x18007b5a3  mov     edx, 1C7h; void *
0x18007b5a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b5ad  nop
0x18007b5ae  lea     rcx, [rsp+11F0h+var_11B0]
0x18007b5b3  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18007b5b8  jmp     loc_18007B4EE
0x18007b5bd  lea     r9, [rbp+10F0h+var_540]; struct SYSTEM_AUDIO_STREAM *
0x18007b5c4  lea     r8, [rsp+11F0h+var_11B0]; struct Microsoft::WRL::WeakRef *
0x18007b5c9  mov     edx, [rdi+0Ch]; unsigned int
0x18007b5cc  lea     rcx, [r15+18h]; this
0x18007b5d0  call    ?Initialize@CGuestSpatialAudioRenderStreamBase@@IEAAJIAEAVWeakRef@WRL@Microsoft@@PEAUSYSTEM_AUDIO_STREAM@@@Z; CGuestSpatialAudioRenderStreamBase::Initialize(uint,Microsoft::WRL::WeakRef &,SYSTEM_AUDIO_STREAM *)
0x18007b5d5  mov     ebx, eax
0x18007b5d7  test    eax, eax
0x18007b5d9  jns     short loc_18007B615
0x18007b5db  mov     rcx, [rbp+10F8h]; this
0x18007b5e2  mov     r9d, eax; char *
0x18007b5e5  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x18007b5ec  mov     edx, 1C9h; void *
0x18007b5f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b5f6  nop
0x18007b5f7  lea     rcx, [rsp+11F0h+var_11B0]
0x18007b5fc  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18007b601  nop
0x18007b602  mov     rcx, [rsp+11F0h+pv]
0x18007b607  mov     [rsp+11F0h+pv], 0
0x18007b610  jmp     loc_18007B4F8
0x18007b615  xor     ebx, ebx
0x18007b617  mov     qword ptr [rsp+11F0h+var_11A8], rbx
0x18007b61c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007b623  mov     ecx, 8C0h; unsigned __int64
0x18007b628  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18007b62d  mov     rdi, rax
0x18007b630  mov     [rsp+11F0h+var_11B8], rax
0x18007b635  test    rax, rax
0x18007b638  jz      short loc_18007B669
0x18007b63a  xor     edx, edx; Val
0x18007b63c  mov     r8d, 8C0h; Size
0x18007b642  mov     rcx, rax; void *
0x18007b645  call    memset_0
0x18007b64a  mov     rcx, rdi; this
0x18007b64d  call    ??0CSpatialAudioObjectRenderStreamForHrtf@@QEAA@XZ; CSpatialAudioObjectRenderStreamForHrtf::CSpatialAudioObjectRenderStreamForHrtf(void)
0x18007b652  mov     rdx, rax
0x18007b655  lea     rcx, [rsp+11F0h+var_11A8]
0x18007b65a  call    ?Attach@?$ComPtr@VCSpatialAudioObjectRenderStreamForHrtf@@@WRL@Microsoft@@QEAAXPEAVCSpatialAudioObjectRenderStreamForHrtf@@@Z; Microsoft::WRL::ComPtr<CSpatialAudioObjectRenderStreamForHrtf>::Attach(CSpatialAudioObjectRenderStreamForHrtf *)
0x18007b65f  mov     [rsp+11F0h+var_11B8], rbx
0x18007b664  mov     rbx, qword ptr [rsp+11F0h+var_11A8]
0x18007b669  lea     rcx, [rsp+11F0h+var_11B8]
0x18007b66e  call    ??1?$MakeAllocator@VCAudioShellStateTracker@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CAudioShellStateTracker>::~MakeAllocator<CAudioShellStateTracker>(void)
0x18007b673  mov     qword ptr [rsp+11F0h+var_11A8], 0
0x18007b67c  mov     [rsp+11F0h+var_11B8], rbx
0x18007b681  lea     rcx, [rsp+11F0h+var_11A8]
0x18007b686  call    ?InternalRelease@?$ComPtr@VCSpatialAudioObjectRenderStreamForHrtf@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CSpatialAudioObjectRenderStreamForHrtf>::InternalRelease(void)
0x18007b68b  test    rbx, rbx
0x18007b68e  jnz     short loc_18007B6C0
0x18007b690  mov     rcx, [rbp+10F8h]; this
0x18007b697  mov     ebx, 8007000Eh
0x18007b69c  mov     r9d, ebx; char *
0x18007b69f  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x18007b6a6  mov     edx, 1CCh; void *
0x18007b6ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b6b0  nop
0x18007b6b1  lea     rcx, [rsp+11F0h+var_11B8]
0x18007b6b6  call    ??1?$com_ptr_t@VCSpatialAudioObjectRenderStreamForHrtf@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(void)
0x18007b6bb  jmp     loc_18007B5F7
0x18007b6c0  lea     rax, [rbp+10F0h+var_540]
0x18007b6c7  mov     [rsp+11F0h+var_11C8], rax; struct SYSTEM_AUDIO_STREAM *
0x18007b6cc  mov     eax, [rbp+10F0h+arg_20]
0x18007b6d2  mov     [rsp+11F0h+var_11D0], eax; int
0x18007b6d6  mov     r9d, [rsi+0A8h]; unsigned int
0x18007b6dd  mov     r8, r14; struct SpatialAudioHrtfActivationParams2 *
0x18007b6e0  mov     rdx, r13; struct AudioClientConstructionParams *
0x18007b6e3  mov     rcx, rbx; this
0x18007b6e6  call    ?InitializeInGuestMode@CSpatialAudioObjectRenderStreamForHrtf@@QEAAJPEBUAudioClientConstructionParams@@PEBUSpatialAudioHrtfActivationParams2@@IKPEAUSYSTEM_AUDIO_STREAM@@@Z; CSpatialAudioObjectRenderStreamForHrtf::InitializeInGuestMode(AudioClientConstructionParams const *,SpatialAudioHrtfActivationParams2 const *,uint,ulong,SYSTEM_AUDIO_STREAM *)
0x18007b6eb  mov     edi, eax
0x18007b6ed  xor     r13d, r13d
0x18007b6f0  test    eax, eax
0x18007b6f2  jns     short loc_18007B742
0x18007b6f4  mov     edx, 1D1h; void *
0x18007b6f9  mov     rcx, [rbp+10F8h]; this
0x18007b700  mov     r9d, edi; char *
0x18007b703  lea     r8, aAvcoreAudiocor_84; "avcore\\audiocore\\client\\spatialaudio"...
0x18007b70a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007b70f  nop
0x18007b710  lea     rcx, [rsp+11F0h+var_11B8]
0x18007b715  call    ??1?$com_ptr_t@VCSpatialAudioObjectRenderStreamForHrtf@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>::~com_ptr_t<CSpatialAudioObjectRenderStreamForHrtf,wil::err_returncode_policy>(void)
0x18007b71a  nop
0x18007b71b  lea     rcx, [rsp+11F0h+var_11B0]
0x18007b720  call    ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
0x18007b725  nop
0x18007b726  mov     rcx, [rsp+11F0h+pv]; pv
0x18007b72b  mov     [rsp+11F0h+pv], r13
0x18007b730  test    rcx, rcx
0x18007b733  jz      short loc_18007B73B
0x18007b735  call    cs:__imp_CoTaskMemFree
0x18007b73b  mov     eax, edi
0x18007b73d  jmp     loc_18007B909
0x18007b742  lea     rsi, [rbx+18h]
0x18007b746  mov     [r15+200h], rsi
0x18007b74d  lea     rcx, [r15+40h]
0x18007b751  call    ?reset@?$com_ptr_t@UIMediaNotificationCallback@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMediaNotificationCallback,wil::err_returncode_policy>::reset(void)
0x18007b756  lea     rdx, [r15+40h]; struct IMediaNotificationCallback **
0x18007b75a  mov     rcx, rsi; this
0x18007b75d  call    ?GetMediaNotificationCallback@CSpatialAudioRenderStreamBase@@QEAAJPEAPEAUIMediaNotificationCallback@@@Z; CSpatialAudioRenderStreamBase::GetMediaNotificationCallback(IMediaNotificationCallback * *)
0x18007b762  mov     edi, eax
0x18007b764  test    eax, eax
0x18007b766  jns     short loc_18007B76F
0x18007b768  mov     edx, 1D5h
0x18007b76d  jmp     short loc_18007B6F9
0x18007b76f  mov     rdx, [r14+20h]; struct ISpatialAudioObjectRenderStreamNotify *
0x18007b773  test    rdx, rdx
0x18007b776  jz      short loc_18007B794
0x18007b778  mov     rcx, [r15+200h]; this
0x18007b77f  call    ?AttachSpatialAudioObjectRenderStreamNotify@CSpatialAudioRenderStreamBase@@QEAAJPEAUISpatialAudioObjectRenderStreamNotify@@@Z; CSpatialAudioRenderStreamBase::AttachSpatialAudioObjectRenderStreamNotify(ISpatialAudioObjectRenderStreamNotify *)
0x18007b784  mov     edi, eax
0x18007b786  test    eax, eax
0x18007b788  jns     short loc_18007B794
0x18007b78a  mov     edx, 1D9h
0x18007b78f  jmp     loc_18007B6F9
0x18007b794  mov     [rsp+11F0h+var_11A0], r13
0x18007b799  lea     rax, [rsp+11F0h+var_11A0]
0x18007b79e  mov     [rsp+11F0h+var_1198], rax
0x18007b7a3  mov     [rsp+11F0h+var_1190], r13
0x18007b7a8  mov     [rsp+11F0h+var_1188], 1
0x18007b7ad  mov     r8b, r13b
0x18007b7b0  lea     rcx, [r15+20h]
0x18007b7b4  lea     rax, [rsp+11F0h+var_11A8]
0x18007b7b9  mov     qword ptr [rsp+11F0h+var_11D0], rax; int
0x18007b7be  lea     r9, [rsp+11F0h+var_1190]
  ... truncated ...
```
