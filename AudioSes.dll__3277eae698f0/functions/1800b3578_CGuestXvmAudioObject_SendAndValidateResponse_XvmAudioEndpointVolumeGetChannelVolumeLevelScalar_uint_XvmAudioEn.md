# CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetChannelVolumeLevelScalar>(uint,XvmAudioEndpointVolumeGetChannelVolumeLevelScalar,XvmMessage * *,XvmAudioEndpointVolumeGetChannelVolumeLevelScalar * *)

- ea: `0x1800b3578`
- end: `0x1800b38bf`
- name: `??$SendAndValidateResponse@UXvmAudioEndpointVolumeGetChannelVolumeLevelScalar@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeGetChannelVolumeLevelScalar@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `839`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b6d00`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a5cd8`
- `0x1800b3578`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b35ba`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b36a6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b35ba`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b36a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b35ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b35ee`

## string_xrefs

- `0x1800b35d1`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b3610`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b381c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b3865`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetChannelVolumeLevelScalar>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        ...)
{
  int v6; // esi
  _DWORD *v8; // rsi
  int v9; // ebx
  int v10; // ebx
  float v11; // xmm6_4
  const struct _tlgProvider_t *v12; // r8
  int v13; // r9d
  const struct _tlgProvider_t *v14; // rax
  int v15; // r9d
  __int64 v16; // rdx
  unsigned __int64 v17; // r9
  int ChannelVolumeLevel; // eax
  int v19; // [rsp+28h] [rbp-E0h]
  int v20[2]; // [rsp+68h] [rbp-A0h] BYREF
  _DWORD *v21; // [rsp+70h] [rbp-98h] BYREF
  _DWORD *v22; // [rsp+78h] [rbp-90h] BYREF
  float v23; // [rsp+80h] [rbp-88h] BYREF
  int v24; // [rsp+84h] [rbp-84h] BYREF
  __int64 v25; // [rsp+88h] [rbp-80h] BYREF
  LARGE_INTEGER v26; // [rsp+90h] [rbp-78h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+98h] [rbp-70h] BYREF
  va_list v28; // [rsp+A0h] [rbp-68h]
  _DWORD **v29; // [rsp+A8h] [rbp-60h]
  char v30; // [rsp+B0h] [rbp-58h]
  __int64 Src; // [rsp+B8h] [rbp-50h] BYREF
  int v32; // [rsp+C0h] [rbp-48h]
  int v33; // [rsp+C4h] [rbp-44h]
  _QWORD v34[258]; // [rsp+C8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8F0h] [rbp+7E8h]
  int v36; // [rsp+8F8h] [rbp+7F0h] BYREF
  _QWORD *v37; // [rsp+910h] [rbp+808h] BYREF
  va_list va; // [rsp+910h] [rbp+808h]
  __int64 v39; // [rsp+918h] [rbp+810h]
  va_list va1; // [rsp+920h] [rbp+818h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v37 = va_arg(va1, _QWORD *);
  v39 = va_arg(va1, _QWORD);
  PerformanceCount.QuadPart = 0;
  v26.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v6 = *(_DWORD *)(a1 + 64);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
      (const char *)(unsigned int)v6,
      v19);
    return (unsigned int)v6;
  }
  v8 = CoTaskMemAlloc(0x810u);
  v21 = v8;
  if ( v8 )
  {
    Src = 0;
    v33 = 0;
    memset_0(v34, 0, 0x800u);
    v34[0] = a3;
    v32 = 89;
    memcpy_0(v8, &Src, 0x810u);
    v21[3] = a2;
    va_copy(v28, va);
    v29 = &v21;
    v30 = 1;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _DWORD *, __int64))(**(_QWORD **)(a1 + 40) + 32LL))(
            *(_QWORD *)(a1 + 40),
            a2,
            v21,
            2064);
    QueryPerformanceCounter(&v26);
    v11 = 0.0;
    if ( *(_QWORD *)(a1 + 72) )
      v11 = (float)((float)(v26.LowPart - PerformanceCount.LowPart) * 1000.0) / (float)(int)*(_QWORD *)(a1 + 72);
    if ( v21[2] == 1 )
    {
      v22 = 0;
      if ( (int)XvmMessage::CastTo<XvmActivateProxyAudioObject>(v21, &v22) >= 0 )
      {
        v12 = GuestXvmAudioObjectTelemetryProvider::Provider();
        if ( *(_DWORD *)v12 > 4u )
        {
          v36 = v10;
          v23 = v11;
          v25 = a1;
          v24 = v22[4];
          v20[0] = v22[1];
          v20[1] = v22[2];
          LODWORD(v22) = *v22;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v12,
            (unsigned int)word_180166D32,
            (_DWORD)v12,
            v13,
            (__int64)&v22,
            (__int64)&v20[1],
            (__int64)v20,
            (__int64)&v24,
            (__int64)&v25,
            (__int64)&v23,
            (__int64)&v36);
        }
      }
    }
    else
    {
      v14 = GuestXvmAudioObjectTelemetryProvider::Provider();
      if ( *(_DWORD *)v14 > 4u )
      {
        v36 = v10;
        *(float *)&v22 = v11;
        v25 = a1;
        v20[1] = v21[2];
        v20[0] = *(_DWORD *)(a1 + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v14,
          (unsigned int)&byte_180166C1F,
          (_DWORD)v12,
          v15,
          (__int64)v20,
          (__int64)&v20[1],
          (__int64)&v25,
          (__int64)&v22,
          (__int64)&v36);
      }
    }
    if ( v10 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
        (const char *)(unsigned int)v10,
        v19);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    }
    v9 = *(_DWORD *)(a1 + 64);
    if ( v9 >= 0 )
    {
      v9 = v21[1];
      if ( v9 >= 0 )
      {
        ChannelVolumeLevel = XvmMessage::CastTo<XvmAudioEndpointVolumeGetChannelVolumeLevelScalar>(v21, v39, v12);
        v9 = ChannelVolumeLevel;
        if ( ChannelVolumeLevel >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)ChannelVolumeLevel;
        v16 = 141;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
          (const char *)v17,
          v19);
LABEL_24:
        *v37 = v21;
        return (unsigned int)v9;
      }
      v16 = 140;
    }
    else
    {
      v16 = 138;
    }
    v17 = (unsigned int)v9;
    goto LABEL_20;
  }
  v9 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x52,
    (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
    (const char *)0x8007000ELL,
    v19);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800b3578  mov     rax, rsp
0x1800b357b  mov     [rax+10h], rbx
0x1800b357f  mov     [rax+18h], rsi
0x1800b3583  mov     [rax+20h], r9
0x1800b3587  push    rbp
0x1800b3588  push    rdi
0x1800b3589  push    r14
0x1800b358b  lea     rbp, [rax-7E8h]
0x1800b3592  sub     rsp, 8D0h
0x1800b3599  movaps  xmmword ptr [rax-28h], xmm6
0x1800b359d  mov     rbx, r8
0x1800b35a0  mov     r14d, edx
0x1800b35a3  mov     rdi, rcx
0x1800b35a6  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800b35ae  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800b35b6  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800b35ba  call    cs:__imp_QueryPerformanceCounter
0x1800b35c0  mov     esi, [rdi+40h]
0x1800b35c3  test    esi, esi
0x1800b35c5  jns     short loc_1800B35E9
0x1800b35c7  mov     rcx, [rbp+7E8h]; this
0x1800b35ce  mov     r9d, esi; char *
0x1800b35d1  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b35d8  mov     edx, 4Fh ; 'O'; void *
0x1800b35dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b35e2  mov     eax, esi
0x1800b35e4  jmp     loc_1800B38A2
0x1800b35e9  mov     ecx, 810h; cb
0x1800b35ee  call    cs:__imp_CoTaskMemAlloc
0x1800b35f4  mov     rsi, rax
0x1800b35f7  mov     [rsp+8E0h+var_878], rax
0x1800b35fc  test    rax, rax
0x1800b35ff  jnz     short loc_1800B3624
0x1800b3601  mov     rcx, [rbp+7E8h]; this
0x1800b3608  mov     ebx, 8007000Eh
0x1800b360d  mov     r9d, ebx; char *
0x1800b3610  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b3617  lea     edx, [rax+52h]; void *
0x1800b361a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b361f  jmp     loc_1800B38A0
0x1800b3624  mov     [rbp+7E0h+Src], 0
0x1800b362c  mov     [rbp+7E0h+var_824], 0
0x1800b3633  xor     edx, edx; Val
0x1800b3635  mov     r8d, 800h; Size
0x1800b363b  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800b363f  call    memset_0
0x1800b3644  mov     [rbp+7E0h+var_820], rbx
0x1800b3648  mov     [rbp+7E0h+var_828], 59h ; 'Y'
0x1800b364f  mov     rcx, rsi; void *
0x1800b3652  lea     rdx, [rbp+7E0h+Src]; Src
0x1800b3656  mov     r8d, 810h; Size
0x1800b365c  call    memcpy_0
0x1800b3661  mov     rax, [rsp+8E0h+var_878]
0x1800b3666  mov     [rax+0Ch], r14d
0x1800b366a  lea     rax, [rbp+7E0h+arg_18]
0x1800b3671  mov     [rbp+7E0h+var_848], rax
0x1800b3675  lea     rax, [rsp+8E0h+var_878]
0x1800b367a  mov     [rbp+7E0h+var_840], rax
0x1800b367e  mov     [rbp+7E0h+var_838], 1
0x1800b3682  mov     rcx, [rdi+28h]
0x1800b3686  mov     rax, [rcx]
0x1800b3689  mov     r9d, 810h
0x1800b368f  mov     r8, [rsp+8E0h+var_878]
0x1800b3694  mov     edx, r14d
0x1800b3697  mov     rax, [rax+20h]
0x1800b369b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b36a0  mov     ebx, eax
0x1800b36a2  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800b36a6  call    cs:__imp_QueryPerformanceCounter
0x1800b36ac  xorps   xmm6, xmm6
0x1800b36af  cmp     qword ptr [rdi+48h], 0
0x1800b36b4  jz      short loc_1800B36D8
0x1800b36b6  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800b36ba  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800b36be  cvtsi2ss xmm6, rcx
0x1800b36c3  mulss   xmm6, cs:__real@447a0000
0x1800b36cb  xorps   xmm0, xmm0
0x1800b36ce  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800b36d4  divss   xmm6, xmm0
0x1800b36d8  mov     rcx, [rsp+8E0h+var_878]
0x1800b36dd  cmp     dword ptr [rcx+8], 1
0x1800b36e1  jnz     loc_1800B379D
0x1800b36e7  mov     [rsp+8E0h+var_870], 0
0x1800b36f0  lea     rdx, [rsp+8E0h+var_870]
0x1800b36f5  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b36fa  test    eax, eax
0x1800b36fc  js      loc_1800B380E
0x1800b3702  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b3707  mov     r8, rax
0x1800b370a  mov     ecx, [rax]
0x1800b370c  cmp     ecx, 4
0x1800b370f  jbe     loc_1800B380E
0x1800b3715  mov     [rbp+7E0h+arg_0], ebx
0x1800b371b  movss   [rsp+8E0h+var_868], xmm6
0x1800b3721  mov     [rbp+7E0h+var_860], rdi
0x1800b3725  mov     rdx, [rsp+8E0h+var_870]
0x1800b372a  mov     ecx, [rdx+10h]
0x1800b372d  mov     [rsp+8E0h+var_864], ecx
0x1800b3731  mov     ecx, [rdx+4]
0x1800b3734  mov     [rsp+8E0h+var_880], ecx
0x1800b3738  mov     eax, [rdx+8]
0x1800b373b  mov     [rsp+8E0h+var_880+4], eax
0x1800b373f  mov     eax, [rdx]
0x1800b3741  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800b3745  lea     rax, [rbp+7E0h+arg_0]
0x1800b374c  mov     [rsp+8E0h+var_890], rax
0x1800b3751  lea     rax, [rsp+8E0h+var_868]
0x1800b3756  mov     [rsp+8E0h+var_898], rax
0x1800b375b  lea     rax, [rbp+7E0h+var_860]
0x1800b375f  mov     [rsp+8E0h+var_8A0], rax
0x1800b3764  lea     rax, [rsp+8E0h+var_864]
0x1800b3769  mov     [rsp+8E0h+var_8A8], rax
0x1800b376e  lea     rax, [rsp+8E0h+var_880]
0x1800b3773  mov     [rsp+8E0h+var_8B0], rax
0x1800b3778  lea     rax, [rsp+8E0h+var_880+4]
0x1800b377d  mov     [rsp+8E0h+var_8B8], rax
0x1800b3782  lea     rax, [rsp+8E0h+var_870]
0x1800b3787  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800b378c  lea     rdx, word_180166D32
0x1800b3793  mov     rcx, r8
0x1800b3796  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b379b  jmp     short loc_1800B380E
0x1800b379d  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b37a2  mov     ecx, [rax]
0x1800b37a4  cmp     ecx, 4
0x1800b37a7  jbe     short loc_1800B380E
0x1800b37a9  mov     [rbp+7E0h+arg_0], ebx
0x1800b37af  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800b37b5  mov     [rbp+7E0h+var_860], rdi
0x1800b37b9  mov     rcx, [rsp+8E0h+var_878]
0x1800b37be  mov     edx, [rcx+8]
0x1800b37c1  mov     [rsp+8E0h+var_880+4], edx
0x1800b37c5  mov     ecx, [rdi+30h]
0x1800b37c8  mov     [rsp+8E0h+var_880], ecx
0x1800b37cc  lea     rcx, [rbp+7E0h+arg_0]
0x1800b37d3  mov     [rsp+8E0h+var_8A0], rcx
0x1800b37d8  lea     rcx, [rsp+8E0h+var_870]
0x1800b37dd  mov     [rsp+8E0h+var_8A8], rcx
0x1800b37e2  lea     rcx, [rbp+7E0h+var_860]
0x1800b37e6  mov     [rsp+8E0h+var_8B0], rcx
0x1800b37eb  lea     rcx, [rsp+8E0h+var_880+4]
0x1800b37f0  mov     [rsp+8E0h+var_8B8], rcx
0x1800b37f5  lea     rcx, [rsp+8E0h+var_880]
0x1800b37fa  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800b37ff  lea     rdx, byte_180166C1F
0x1800b3806  mov     rcx, rax
0x1800b3809  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b380e  mov     rcx, [rbp+7E8h]; this
0x1800b3815  test    ebx, ebx
0x1800b3817  jns     short loc_1800B383C
0x1800b3819  mov     r9d, ebx; char *
0x1800b381c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b3823  mov     edx, 81h; void *
0x1800b3828  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b382d  mov     rax, [rdi]
0x1800b3830  mov     rcx, rdi
0x1800b3833  mov     rax, [rax+20h]
0x1800b3837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b383c  mov     ebx, [rdi+40h]
0x1800b383f  test    ebx, ebx
0x1800b3841  jns     short loc_1800B384A
0x1800b3843  mov     edx, 8Ah
0x1800b3848  jmp     short loc_1800B385B
0x1800b384a  mov     rcx, [rsp+8E0h+var_878]
0x1800b384f  mov     ebx, [rcx+4]
0x1800b3852  test    ebx, ebx
0x1800b3854  jns     short loc_1800B3873
0x1800b3856  mov     edx, 8Ch; void *
0x1800b385b  mov     r9d, ebx; char *
0x1800b385e  mov     rcx, [rbp+7E8h]; this
0x1800b3865  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b386c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3871  jmp     short loc_1800B3891
0x1800b3873  mov     rdx, [rbp+7E0h+arg_20]
0x1800b387a  call    ??$CastTo@UXvmAudioEndpointVolumeGetChannelVolumeLevelScalar@@@XvmMessage@@QEAAJPEAPEAUXvmAudioEndpointVolumeGetChannelVolumeLevelScalar@@@Z; XvmMessage::CastTo<XvmAudioEndpointVolumeGetChannelVolumeLevelScalar>(XvmAudioEndpointVolumeGetChannelVolumeLevelScalar * *)
0x1800b387f  mov     ebx, eax
0x1800b3881  test    eax, eax
0x1800b3883  jns     short loc_1800B388F
0x1800b3885  mov     r9d, eax
0x1800b3888  mov     edx, 8Dh
0x1800b388d  jmp     short loc_1800B385E
0x1800b388f  xor     ebx, ebx
0x1800b3891  mov     rcx, [rbp+7E0h+arg_18]
0x1800b3898  mov     rax, [rsp+8E0h+var_878]
0x1800b389d  mov     [rcx], rax
0x1800b38a0  mov     eax, ebx
0x1800b38a2  lea     r11, [rsp+8E0h+var_10]
0x1800b38aa  mov     rbx, [r11+28h]
0x1800b38ae  mov     rsi, [r11+30h]
0x1800b38b2  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b38b7  mov     rsp, r11
0x1800b38ba  pop     r14
0x1800b38bc  pop     rdi
0x1800b38bd  pop     rbp
0x1800b38be  retn
```
