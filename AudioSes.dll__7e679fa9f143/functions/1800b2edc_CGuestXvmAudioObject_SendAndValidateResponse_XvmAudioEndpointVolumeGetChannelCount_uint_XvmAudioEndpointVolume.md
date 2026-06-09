# CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetChannelCount>(uint,XvmAudioEndpointVolumeGetChannelCount,XvmMessage * *,XvmAudioEndpointVolumeGetChannelCount * *)

- ea: `0x1800b2edc`
- end: `0x1800b3222`
- name: `??$SendAndValidateResponse@UXvmAudioEndpointVolumeGetChannelCount@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeGetChannelCount@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b6b20`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a5c48`
- `0x1800b2edc`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b2f1e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b3009`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b2f1e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b3009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b2f52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b2f52`

## string_xrefs

- `0x1800b2f35`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b2f74`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b317f`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b31c8`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetChannelCount>(
        __int64 a1,
        unsigned int a2,
        int a3,
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
  int Channel; // eax
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
  _DWORD v34[516]; // [rsp+C8h] [rbp-40h] BYREF
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
    v32 = 81;
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
            (unsigned int)&unk_1801672C8,
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
          (unsigned int)&unk_180167341,
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
        Channel = XvmMessage::CastTo<XvmAudioEndpointVolumeGetChannelCount>(v21, v39, v12);
        v9 = Channel;
        if ( Channel >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)Channel;
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
0x1800b2edc  mov     rax, rsp
0x1800b2edf  mov     [rax+10h], rbx
0x1800b2ee3  mov     [rax+18h], rsi
0x1800b2ee7  mov     [rax+20h], r9
0x1800b2eeb  push    rbp
0x1800b2eec  push    rdi
0x1800b2eed  push    r14
0x1800b2eef  lea     rbp, [rax-7E8h]
0x1800b2ef6  sub     rsp, 8D0h
0x1800b2efd  movaps  xmmword ptr [rax-28h], xmm6
0x1800b2f01  mov     ebx, r8d
0x1800b2f04  mov     r14d, edx
0x1800b2f07  mov     rdi, rcx
0x1800b2f0a  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800b2f12  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800b2f1a  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800b2f1e  call    cs:__imp_QueryPerformanceCounter
0x1800b2f24  mov     esi, [rdi+40h]
0x1800b2f27  test    esi, esi
0x1800b2f29  jns     short loc_1800B2F4D
0x1800b2f2b  mov     rcx, [rbp+7E8h]; this
0x1800b2f32  mov     r9d, esi; char *
0x1800b2f35  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b2f3c  mov     edx, 4Fh ; 'O'; void *
0x1800b2f41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2f46  mov     eax, esi
0x1800b2f48  jmp     loc_1800B3205
0x1800b2f4d  mov     ecx, 810h; cb
0x1800b2f52  call    cs:__imp_CoTaskMemAlloc
0x1800b2f58  mov     rsi, rax
0x1800b2f5b  mov     [rsp+8E0h+var_878], rax
0x1800b2f60  test    rax, rax
0x1800b2f63  jnz     short loc_1800B2F88
0x1800b2f65  mov     rcx, [rbp+7E8h]; this
0x1800b2f6c  mov     ebx, 8007000Eh
0x1800b2f71  mov     r9d, ebx; char *
0x1800b2f74  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b2f7b  lea     edx, [rax+52h]; void *
0x1800b2f7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b2f83  jmp     loc_1800B3203
0x1800b2f88  mov     [rbp+7E0h+Src], 0
0x1800b2f90  mov     [rbp+7E0h+var_824], 0
0x1800b2f97  xor     edx, edx; Val
0x1800b2f99  mov     r8d, 800h; Size
0x1800b2f9f  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800b2fa3  call    memset_0
0x1800b2fa8  mov     [rbp+7E0h+var_820], ebx
0x1800b2fab  mov     [rbp+7E0h+var_828], 51h ; 'Q'
0x1800b2fb2  mov     rcx, rsi; void *
0x1800b2fb5  lea     rdx, [rbp+7E0h+Src]; Src
0x1800b2fb9  mov     r8d, 810h; Size
0x1800b2fbf  call    memcpy_0
0x1800b2fc4  mov     rax, [rsp+8E0h+var_878]
0x1800b2fc9  mov     [rax+0Ch], r14d
0x1800b2fcd  lea     rax, [rbp+7E0h+arg_18]
0x1800b2fd4  mov     [rbp+7E0h+var_848], rax
0x1800b2fd8  lea     rax, [rsp+8E0h+var_878]
0x1800b2fdd  mov     [rbp+7E0h+var_840], rax
0x1800b2fe1  mov     [rbp+7E0h+var_838], 1
0x1800b2fe5  mov     rcx, [rdi+28h]
0x1800b2fe9  mov     rax, [rcx]
0x1800b2fec  mov     r9d, 810h
0x1800b2ff2  mov     r8, [rsp+8E0h+var_878]
0x1800b2ff7  mov     edx, r14d
0x1800b2ffa  mov     rax, [rax+20h]
0x1800b2ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3003  mov     ebx, eax
0x1800b3005  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800b3009  call    cs:__imp_QueryPerformanceCounter
0x1800b300f  xorps   xmm6, xmm6
0x1800b3012  cmp     qword ptr [rdi+48h], 0
0x1800b3017  jz      short loc_1800B303B
0x1800b3019  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800b301d  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800b3021  cvtsi2ss xmm6, rcx
0x1800b3026  mulss   xmm6, cs:__real@447a0000
0x1800b302e  xorps   xmm0, xmm0
0x1800b3031  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800b3037  divss   xmm6, xmm0
0x1800b303b  mov     rcx, [rsp+8E0h+var_878]
0x1800b3040  cmp     dword ptr [rcx+8], 1
0x1800b3044  jnz     loc_1800B3100
0x1800b304a  mov     [rsp+8E0h+var_870], 0
0x1800b3053  lea     rdx, [rsp+8E0h+var_870]
0x1800b3058  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b305d  test    eax, eax
0x1800b305f  js      loc_1800B3171
0x1800b3065  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b306a  mov     r8, rax
0x1800b306d  mov     ecx, [rax]
0x1800b306f  cmp     ecx, 4
0x1800b3072  jbe     loc_1800B3171
0x1800b3078  mov     [rbp+7E0h+arg_0], ebx
0x1800b307e  movss   [rsp+8E0h+var_868], xmm6
0x1800b3084  mov     [rbp+7E0h+var_860], rdi
0x1800b3088  mov     rdx, [rsp+8E0h+var_870]
0x1800b308d  mov     ecx, [rdx+10h]
0x1800b3090  mov     [rsp+8E0h+var_864], ecx
0x1800b3094  mov     ecx, [rdx+4]
0x1800b3097  mov     [rsp+8E0h+var_880], ecx
0x1800b309b  mov     eax, [rdx+8]
0x1800b309e  mov     [rsp+8E0h+var_880+4], eax
0x1800b30a2  mov     eax, [rdx]
0x1800b30a4  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800b30a8  lea     rax, [rbp+7E0h+arg_0]
0x1800b30af  mov     [rsp+8E0h+var_890], rax
0x1800b30b4  lea     rax, [rsp+8E0h+var_868]
0x1800b30b9  mov     [rsp+8E0h+var_898], rax
0x1800b30be  lea     rax, [rbp+7E0h+var_860]
0x1800b30c2  mov     [rsp+8E0h+var_8A0], rax
0x1800b30c7  lea     rax, [rsp+8E0h+var_864]
0x1800b30cc  mov     [rsp+8E0h+var_8A8], rax
0x1800b30d1  lea     rax, [rsp+8E0h+var_880]
0x1800b30d6  mov     [rsp+8E0h+var_8B0], rax
0x1800b30db  lea     rax, [rsp+8E0h+var_880+4]
0x1800b30e0  mov     [rsp+8E0h+var_8B8], rax
0x1800b30e5  lea     rax, [rsp+8E0h+var_870]
0x1800b30ea  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800b30ef  lea     rdx, unk_1801672C8
0x1800b30f6  mov     rcx, r8
0x1800b30f9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b30fe  jmp     short loc_1800B3171
0x1800b3100  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b3105  mov     ecx, [rax]
0x1800b3107  cmp     ecx, 4
0x1800b310a  jbe     short loc_1800B3171
0x1800b310c  mov     [rbp+7E0h+arg_0], ebx
0x1800b3112  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800b3118  mov     [rbp+7E0h+var_860], rdi
0x1800b311c  mov     rcx, [rsp+8E0h+var_878]
0x1800b3121  mov     edx, [rcx+8]
0x1800b3124  mov     [rsp+8E0h+var_880+4], edx
0x1800b3128  mov     ecx, [rdi+30h]
0x1800b312b  mov     [rsp+8E0h+var_880], ecx
0x1800b312f  lea     rcx, [rbp+7E0h+arg_0]
0x1800b3136  mov     [rsp+8E0h+var_8A0], rcx
0x1800b313b  lea     rcx, [rsp+8E0h+var_870]
0x1800b3140  mov     [rsp+8E0h+var_8A8], rcx
0x1800b3145  lea     rcx, [rbp+7E0h+var_860]
0x1800b3149  mov     [rsp+8E0h+var_8B0], rcx
0x1800b314e  lea     rcx, [rsp+8E0h+var_880+4]
0x1800b3153  mov     [rsp+8E0h+var_8B8], rcx
0x1800b3158  lea     rcx, [rsp+8E0h+var_880]
0x1800b315d  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800b3162  lea     rdx, unk_180167341
0x1800b3169  mov     rcx, rax
0x1800b316c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b3171  mov     rcx, [rbp+7E8h]; this
0x1800b3178  test    ebx, ebx
0x1800b317a  jns     short loc_1800B319F
0x1800b317c  mov     r9d, ebx; char *
0x1800b317f  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b3186  mov     edx, 81h; void *
0x1800b318b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b3190  mov     rax, [rdi]
0x1800b3193  mov     rcx, rdi
0x1800b3196  mov     rax, [rax+20h]
0x1800b319a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b319f  mov     ebx, [rdi+40h]
0x1800b31a2  test    ebx, ebx
0x1800b31a4  jns     short loc_1800B31AD
0x1800b31a6  mov     edx, 8Ah
0x1800b31ab  jmp     short loc_1800B31BE
0x1800b31ad  mov     rcx, [rsp+8E0h+var_878]
0x1800b31b2  mov     ebx, [rcx+4]
0x1800b31b5  test    ebx, ebx
0x1800b31b7  jns     short loc_1800B31D6
0x1800b31b9  mov     edx, 8Ch; void *
0x1800b31be  mov     r9d, ebx; char *
0x1800b31c1  mov     rcx, [rbp+7E8h]; this
0x1800b31c8  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b31cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b31d4  jmp     short loc_1800B31F4
0x1800b31d6  mov     rdx, [rbp+7E0h+arg_20]
0x1800b31dd  call    ??$CastTo@UXvmAudioEndpointVolumeGetChannelCount@@@XvmMessage@@QEAAJPEAPEAUXvmAudioEndpointVolumeGetChannelCount@@@Z; XvmMessage::CastTo<XvmAudioEndpointVolumeGetChannelCount>(XvmAudioEndpointVolumeGetChannelCount * *)
0x1800b31e2  mov     ebx, eax
0x1800b31e4  test    eax, eax
0x1800b31e6  jns     short loc_1800B31F2
0x1800b31e8  mov     r9d, eax
0x1800b31eb  mov     edx, 8Dh
0x1800b31f0  jmp     short loc_1800B31C1
0x1800b31f2  xor     ebx, ebx
0x1800b31f4  mov     rcx, [rbp+7E0h+arg_18]
0x1800b31fb  mov     rax, [rsp+8E0h+var_878]
0x1800b3200  mov     [rcx], rax
0x1800b3203  mov     eax, ebx
0x1800b3205  lea     r11, [rsp+8E0h+var_10]
0x1800b320d  mov     rbx, [r11+28h]
0x1800b3211  mov     rsi, [r11+30h]
0x1800b3215  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b321a  mov     rsp, r11
0x1800b321d  pop     r14
0x1800b321f  pop     rdi
0x1800b3220  pop     rbp
0x1800b3221  retn
```
