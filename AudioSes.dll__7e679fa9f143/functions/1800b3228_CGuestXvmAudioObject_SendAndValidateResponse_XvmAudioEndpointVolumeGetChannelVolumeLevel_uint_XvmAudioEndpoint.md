# CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetChannelVolumeLevel>(uint,XvmAudioEndpointVolumeGetChannelVolumeLevel,XvmMessage * *,XvmAudioEndpointVolumeGetChannelVolumeLevel * *)

- ea: `0x1800b3228`
- end: `0x1800b356f`
- name: `??$SendAndValidateResponse@UXvmAudioEndpointVolumeGetChannelVolumeLevel@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeGetChannelVolumeLevel@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `839`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b6c00`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a5c90`
- `0x1800b3228`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b326a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b3356`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b326a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b3356`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b329e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b329e`

## string_xrefs

- `0x1800b3281`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b32c0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b34cc`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b3515`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetChannelVolumeLevel>(
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
  int ChannelVolume; // eax
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
    v32 = 88;
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
            (unsigned int)&unk_180166D5E,
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
          (unsigned int)&unk_180166DD7,
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
        ChannelVolume = XvmMessage::CastTo<XvmAudioEndpointVolumeGetChannelVolumeLevel>(v21, v39, v12);
        v9 = ChannelVolume;
        if ( ChannelVolume >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)ChannelVolume;
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
0x1800b3228  mov     rax, rsp
0x1800b322b  mov     [rax+10h], rbx
0x1800b322f  mov     [rax+18h], rsi
0x1800b3233  mov     [rax+20h], r9
0x1800b3237  push    rbp
0x1800b3238  push    rdi
0x1800b3239  push    r14
0x1800b323b  lea     rbp, [rax-7E8h]
0x1800b3242  sub     rsp, 8D0h
0x1800b3249  movaps  xmmword ptr [rax-28h], xmm6
0x1800b324d  mov     rbx, r8
0x1800b3250  mov     r14d, edx
0x1800b3253  mov     rdi, rcx
0x1800b3256  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800b325e  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800b3266  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800b326a  call    cs:__imp_QueryPerformanceCounter
0x1800b3270  mov     esi, [rdi+40h]
0x1800b3273  test    esi, esi
0x1800b3275  jns     short loc_1800B3299
0x1800b3277  mov     rcx, [rbp+7E8h]; this
0x1800b327e  mov     r9d, esi; char *
0x1800b3281  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b3288  mov     edx, 4Fh ; 'O'; void *
0x1800b328d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3292  mov     eax, esi
0x1800b3294  jmp     loc_1800B3552
0x1800b3299  mov     ecx, 810h; cb
0x1800b329e  call    cs:__imp_CoTaskMemAlloc
0x1800b32a4  mov     rsi, rax
0x1800b32a7  mov     [rsp+8E0h+var_878], rax
0x1800b32ac  test    rax, rax
0x1800b32af  jnz     short loc_1800B32D4
0x1800b32b1  mov     rcx, [rbp+7E8h]; this
0x1800b32b8  mov     ebx, 8007000Eh
0x1800b32bd  mov     r9d, ebx; char *
0x1800b32c0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b32c7  lea     edx, [rax+52h]; void *
0x1800b32ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b32cf  jmp     loc_1800B3550
0x1800b32d4  mov     [rbp+7E0h+Src], 0
0x1800b32dc  mov     [rbp+7E0h+var_824], 0
0x1800b32e3  xor     edx, edx; Val
0x1800b32e5  mov     r8d, 800h; Size
0x1800b32eb  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800b32ef  call    memset_0
0x1800b32f4  mov     [rbp+7E0h+var_820], rbx
0x1800b32f8  mov     [rbp+7E0h+var_828], 58h ; 'X'
0x1800b32ff  mov     rcx, rsi; void *
0x1800b3302  lea     rdx, [rbp+7E0h+Src]; Src
0x1800b3306  mov     r8d, 810h; Size
0x1800b330c  call    memcpy_0
0x1800b3311  mov     rax, [rsp+8E0h+var_878]
0x1800b3316  mov     [rax+0Ch], r14d
0x1800b331a  lea     rax, [rbp+7E0h+arg_18]
0x1800b3321  mov     [rbp+7E0h+var_848], rax
0x1800b3325  lea     rax, [rsp+8E0h+var_878]
0x1800b332a  mov     [rbp+7E0h+var_840], rax
0x1800b332e  mov     [rbp+7E0h+var_838], 1
0x1800b3332  mov     rcx, [rdi+28h]
0x1800b3336  mov     rax, [rcx]
0x1800b3339  mov     r9d, 810h
0x1800b333f  mov     r8, [rsp+8E0h+var_878]
0x1800b3344  mov     edx, r14d
0x1800b3347  mov     rax, [rax+20h]
0x1800b334b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3350  mov     ebx, eax
0x1800b3352  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800b3356  call    cs:__imp_QueryPerformanceCounter
0x1800b335c  xorps   xmm6, xmm6
0x1800b335f  cmp     qword ptr [rdi+48h], 0
0x1800b3364  jz      short loc_1800B3388
0x1800b3366  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800b336a  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800b336e  cvtsi2ss xmm6, rcx
0x1800b3373  mulss   xmm6, cs:__real@447a0000
0x1800b337b  xorps   xmm0, xmm0
0x1800b337e  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800b3384  divss   xmm6, xmm0
0x1800b3388  mov     rcx, [rsp+8E0h+var_878]
0x1800b338d  cmp     dword ptr [rcx+8], 1
0x1800b3391  jnz     loc_1800B344D
0x1800b3397  mov     [rsp+8E0h+var_870], 0
0x1800b33a0  lea     rdx, [rsp+8E0h+var_870]
0x1800b33a5  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b33aa  test    eax, eax
0x1800b33ac  js      loc_1800B34BE
0x1800b33b2  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b33b7  mov     r8, rax
0x1800b33ba  mov     ecx, [rax]
0x1800b33bc  cmp     ecx, 4
0x1800b33bf  jbe     loc_1800B34BE
0x1800b33c5  mov     [rbp+7E0h+arg_0], ebx
0x1800b33cb  movss   [rsp+8E0h+var_868], xmm6
0x1800b33d1  mov     [rbp+7E0h+var_860], rdi
0x1800b33d5  mov     rdx, [rsp+8E0h+var_870]
0x1800b33da  mov     ecx, [rdx+10h]
0x1800b33dd  mov     [rsp+8E0h+var_864], ecx
0x1800b33e1  mov     ecx, [rdx+4]
0x1800b33e4  mov     [rsp+8E0h+var_880], ecx
0x1800b33e8  mov     eax, [rdx+8]
0x1800b33eb  mov     [rsp+8E0h+var_880+4], eax
0x1800b33ef  mov     eax, [rdx]
0x1800b33f1  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800b33f5  lea     rax, [rbp+7E0h+arg_0]
0x1800b33fc  mov     [rsp+8E0h+var_890], rax
0x1800b3401  lea     rax, [rsp+8E0h+var_868]
0x1800b3406  mov     [rsp+8E0h+var_898], rax
0x1800b340b  lea     rax, [rbp+7E0h+var_860]
0x1800b340f  mov     [rsp+8E0h+var_8A0], rax
0x1800b3414  lea     rax, [rsp+8E0h+var_864]
0x1800b3419  mov     [rsp+8E0h+var_8A8], rax
0x1800b341e  lea     rax, [rsp+8E0h+var_880]
0x1800b3423  mov     [rsp+8E0h+var_8B0], rax
0x1800b3428  lea     rax, [rsp+8E0h+var_880+4]
0x1800b342d  mov     [rsp+8E0h+var_8B8], rax
0x1800b3432  lea     rax, [rsp+8E0h+var_870]
0x1800b3437  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800b343c  lea     rdx, unk_180166D5E
0x1800b3443  mov     rcx, r8
0x1800b3446  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b344b  jmp     short loc_1800B34BE
0x1800b344d  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b3452  mov     ecx, [rax]
0x1800b3454  cmp     ecx, 4
0x1800b3457  jbe     short loc_1800B34BE
0x1800b3459  mov     [rbp+7E0h+arg_0], ebx
0x1800b345f  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800b3465  mov     [rbp+7E0h+var_860], rdi
0x1800b3469  mov     rcx, [rsp+8E0h+var_878]
0x1800b346e  mov     edx, [rcx+8]
0x1800b3471  mov     [rsp+8E0h+var_880+4], edx
0x1800b3475  mov     ecx, [rdi+30h]
0x1800b3478  mov     [rsp+8E0h+var_880], ecx
0x1800b347c  lea     rcx, [rbp+7E0h+arg_0]
0x1800b3483  mov     [rsp+8E0h+var_8A0], rcx
0x1800b3488  lea     rcx, [rsp+8E0h+var_870]
0x1800b348d  mov     [rsp+8E0h+var_8A8], rcx
0x1800b3492  lea     rcx, [rbp+7E0h+var_860]
0x1800b3496  mov     [rsp+8E0h+var_8B0], rcx
0x1800b349b  lea     rcx, [rsp+8E0h+var_880+4]
0x1800b34a0  mov     [rsp+8E0h+var_8B8], rcx
0x1800b34a5  lea     rcx, [rsp+8E0h+var_880]
0x1800b34aa  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800b34af  lea     rdx, unk_180166DD7
0x1800b34b6  mov     rcx, rax
0x1800b34b9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b34be  mov     rcx, [rbp+7E8h]; this
0x1800b34c5  test    ebx, ebx
0x1800b34c7  jns     short loc_1800B34EC
0x1800b34c9  mov     r9d, ebx; char *
0x1800b34cc  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b34d3  mov     edx, 81h; void *
0x1800b34d8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b34dd  mov     rax, [rdi]
0x1800b34e0  mov     rcx, rdi
0x1800b34e3  mov     rax, [rax+20h]
0x1800b34e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b34ec  mov     ebx, [rdi+40h]
0x1800b34ef  test    ebx, ebx
0x1800b34f1  jns     short loc_1800B34FA
0x1800b34f3  mov     edx, 8Ah
0x1800b34f8  jmp     short loc_1800B350B
0x1800b34fa  mov     rcx, [rsp+8E0h+var_878]
0x1800b34ff  mov     ebx, [rcx+4]
0x1800b3502  test    ebx, ebx
0x1800b3504  jns     short loc_1800B3523
0x1800b3506  mov     edx, 8Ch; void *
0x1800b350b  mov     r9d, ebx; char *
0x1800b350e  mov     rcx, [rbp+7E8h]; this
0x1800b3515  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b351c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3521  jmp     short loc_1800B3541
0x1800b3523  mov     rdx, [rbp+7E0h+arg_20]
0x1800b352a  call    ??$CastTo@UXvmAudioEndpointVolumeGetChannelVolumeLevel@@@XvmMessage@@QEAAJPEAPEAUXvmAudioEndpointVolumeGetChannelVolumeLevel@@@Z; XvmMessage::CastTo<XvmAudioEndpointVolumeGetChannelVolumeLevel>(XvmAudioEndpointVolumeGetChannelVolumeLevel * *)
0x1800b352f  mov     ebx, eax
0x1800b3531  test    eax, eax
0x1800b3533  jns     short loc_1800B353F
0x1800b3535  mov     r9d, eax
0x1800b3538  mov     edx, 8Dh
0x1800b353d  jmp     short loc_1800B350E
0x1800b353f  xor     ebx, ebx
0x1800b3541  mov     rcx, [rbp+7E0h+arg_18]
0x1800b3548  mov     rax, [rsp+8E0h+var_878]
0x1800b354d  mov     [rcx], rax
0x1800b3550  mov     eax, ebx
0x1800b3552  lea     r11, [rsp+8E0h+var_10]
0x1800b355a  mov     rbx, [r11+28h]
0x1800b355e  mov     rsi, [r11+30h]
0x1800b3562  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b3567  mov     rsp, r11
0x1800b356a  pop     r14
0x1800b356c  pop     rdi
0x1800b356d  pop     rbp
0x1800b356e  retn
```
