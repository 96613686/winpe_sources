# CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetMute>(uint,XvmAudioEndpointVolumeGetMute,XvmMessage * *,XvmAudioEndpointVolumeGetMute * *)

- ea: `0x1800b3f50`
- end: `0x1800b4296`
- name: `??$SendAndValidateResponse@UXvmAudioEndpointVolumeGetMute@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeGetMute@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b7000`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a5db0`
- `0x1800b3f50`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b3f92`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b407d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b3f92`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b407d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b3fc6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b3fc6`

## string_xrefs

- `0x1800b3fa9`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b3fe8`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b41f3`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b423c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetMute>(
        __int64 a1,
        unsigned int a2,
        char a3,
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
  int v18; // eax
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
  _BYTE v34[2064]; // [rsp+C8h] [rbp-40h] BYREF
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
    v32 = 91;
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
            (unsigned int)&word_180166BA6,
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
          (unsigned int)byte_180166A93,
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
        v18 = XvmMessage::CastTo<XvmAudioEndpointVolumeGetMute>(v21, v39, v12);
        v9 = v18;
        if ( v18 >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)v18;
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
0x1800b3f50  mov     rax, rsp
0x1800b3f53  mov     [rax+10h], rbx
0x1800b3f57  mov     [rax+18h], rsi
0x1800b3f5b  mov     [rax+20h], r9
0x1800b3f5f  push    rbp
0x1800b3f60  push    rdi
0x1800b3f61  push    r14
0x1800b3f63  lea     rbp, [rax-7E8h]
0x1800b3f6a  sub     rsp, 8D0h
0x1800b3f71  movaps  xmmword ptr [rax-28h], xmm6
0x1800b3f75  mov     bl, r8b
0x1800b3f78  mov     r14d, edx
0x1800b3f7b  mov     rdi, rcx
0x1800b3f7e  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800b3f86  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800b3f8e  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800b3f92  call    cs:__imp_QueryPerformanceCounter
0x1800b3f98  mov     esi, [rdi+40h]
0x1800b3f9b  test    esi, esi
0x1800b3f9d  jns     short loc_1800B3FC1
0x1800b3f9f  mov     rcx, [rbp+7E8h]; this
0x1800b3fa6  mov     r9d, esi; char *
0x1800b3fa9  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b3fb0  mov     edx, 4Fh ; 'O'; void *
0x1800b3fb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3fba  mov     eax, esi
0x1800b3fbc  jmp     loc_1800B4279
0x1800b3fc1  mov     ecx, 810h; cb
0x1800b3fc6  call    cs:__imp_CoTaskMemAlloc
0x1800b3fcc  mov     rsi, rax
0x1800b3fcf  mov     [rsp+8E0h+var_878], rax
0x1800b3fd4  test    rax, rax
0x1800b3fd7  jnz     short loc_1800B3FFC
0x1800b3fd9  mov     rcx, [rbp+7E8h]; this
0x1800b3fe0  mov     ebx, 8007000Eh
0x1800b3fe5  mov     r9d, ebx; char *
0x1800b3fe8  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b3fef  lea     edx, [rax+52h]; void *
0x1800b3ff2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3ff7  jmp     loc_1800B4277
0x1800b3ffc  mov     [rbp+7E0h+Src], 0
0x1800b4004  mov     [rbp+7E0h+var_824], 0
0x1800b400b  xor     edx, edx; Val
0x1800b400d  mov     r8d, 800h; Size
0x1800b4013  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800b4017  call    memset_0
0x1800b401c  mov     [rbp+7E0h+var_820], bl
0x1800b401f  mov     [rbp+7E0h+var_828], 5Bh ; '['
0x1800b4026  mov     rcx, rsi; void *
0x1800b4029  lea     rdx, [rbp+7E0h+Src]; Src
0x1800b402d  mov     r8d, 810h; Size
0x1800b4033  call    memcpy_0
0x1800b4038  mov     rax, [rsp+8E0h+var_878]
0x1800b403d  mov     [rax+0Ch], r14d
0x1800b4041  lea     rax, [rbp+7E0h+arg_18]
0x1800b4048  mov     [rbp+7E0h+var_848], rax
0x1800b404c  lea     rax, [rsp+8E0h+var_878]
0x1800b4051  mov     [rbp+7E0h+var_840], rax
0x1800b4055  mov     [rbp+7E0h+var_838], 1
0x1800b4059  mov     rcx, [rdi+28h]
0x1800b405d  mov     rax, [rcx]
0x1800b4060  mov     r9d, 810h
0x1800b4066  mov     r8, [rsp+8E0h+var_878]
0x1800b406b  mov     edx, r14d
0x1800b406e  mov     rax, [rax+20h]
0x1800b4072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4077  mov     ebx, eax
0x1800b4079  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800b407d  call    cs:__imp_QueryPerformanceCounter
0x1800b4083  xorps   xmm6, xmm6
0x1800b4086  cmp     qword ptr [rdi+48h], 0
0x1800b408b  jz      short loc_1800B40AF
0x1800b408d  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800b4091  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800b4095  cvtsi2ss xmm6, rcx
0x1800b409a  mulss   xmm6, cs:__real@447a0000
0x1800b40a2  xorps   xmm0, xmm0
0x1800b40a5  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800b40ab  divss   xmm6, xmm0
0x1800b40af  mov     rcx, [rsp+8E0h+var_878]
0x1800b40b4  cmp     dword ptr [rcx+8], 1
0x1800b40b8  jnz     loc_1800B4174
0x1800b40be  mov     [rsp+8E0h+var_870], 0
0x1800b40c7  lea     rdx, [rsp+8E0h+var_870]
0x1800b40cc  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b40d1  test    eax, eax
0x1800b40d3  js      loc_1800B41E5
0x1800b40d9  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b40de  mov     r8, rax
0x1800b40e1  mov     ecx, [rax]
0x1800b40e3  cmp     ecx, 4
0x1800b40e6  jbe     loc_1800B41E5
0x1800b40ec  mov     [rbp+7E0h+arg_0], ebx
0x1800b40f2  movss   [rsp+8E0h+var_868], xmm6
0x1800b40f8  mov     [rbp+7E0h+var_860], rdi
0x1800b40fc  mov     rdx, [rsp+8E0h+var_870]
0x1800b4101  mov     ecx, [rdx+10h]
0x1800b4104  mov     [rsp+8E0h+var_864], ecx
0x1800b4108  mov     ecx, [rdx+4]
0x1800b410b  mov     [rsp+8E0h+var_880], ecx
0x1800b410f  mov     eax, [rdx+8]
0x1800b4112  mov     [rsp+8E0h+var_880+4], eax
0x1800b4116  mov     eax, [rdx]
0x1800b4118  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800b411c  lea     rax, [rbp+7E0h+arg_0]
0x1800b4123  mov     [rsp+8E0h+var_890], rax
0x1800b4128  lea     rax, [rsp+8E0h+var_868]
0x1800b412d  mov     [rsp+8E0h+var_898], rax
0x1800b4132  lea     rax, [rbp+7E0h+var_860]
0x1800b4136  mov     [rsp+8E0h+var_8A0], rax
0x1800b413b  lea     rax, [rsp+8E0h+var_864]
0x1800b4140  mov     [rsp+8E0h+var_8A8], rax
0x1800b4145  lea     rax, [rsp+8E0h+var_880]
0x1800b414a  mov     [rsp+8E0h+var_8B0], rax
0x1800b414f  lea     rax, [rsp+8E0h+var_880+4]
0x1800b4154  mov     [rsp+8E0h+var_8B8], rax
0x1800b4159  lea     rax, [rsp+8E0h+var_870]
0x1800b415e  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800b4163  lea     rdx, word_180166BA6
0x1800b416a  mov     rcx, r8
0x1800b416d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b4172  jmp     short loc_1800B41E5
0x1800b4174  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b4179  mov     ecx, [rax]
0x1800b417b  cmp     ecx, 4
0x1800b417e  jbe     short loc_1800B41E5
0x1800b4180  mov     [rbp+7E0h+arg_0], ebx
0x1800b4186  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800b418c  mov     [rbp+7E0h+var_860], rdi
0x1800b4190  mov     rcx, [rsp+8E0h+var_878]
0x1800b4195  mov     edx, [rcx+8]
0x1800b4198  mov     [rsp+8E0h+var_880+4], edx
0x1800b419c  mov     ecx, [rdi+30h]
0x1800b419f  mov     [rsp+8E0h+var_880], ecx
0x1800b41a3  lea     rcx, [rbp+7E0h+arg_0]
0x1800b41aa  mov     [rsp+8E0h+var_8A0], rcx
0x1800b41af  lea     rcx, [rsp+8E0h+var_870]
0x1800b41b4  mov     [rsp+8E0h+var_8A8], rcx
0x1800b41b9  lea     rcx, [rbp+7E0h+var_860]
0x1800b41bd  mov     [rsp+8E0h+var_8B0], rcx
0x1800b41c2  lea     rcx, [rsp+8E0h+var_880+4]
0x1800b41c7  mov     [rsp+8E0h+var_8B8], rcx
0x1800b41cc  lea     rcx, [rsp+8E0h+var_880]
0x1800b41d1  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800b41d6  lea     rdx, byte_180166A93
0x1800b41dd  mov     rcx, rax
0x1800b41e0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b41e5  mov     rcx, [rbp+7E8h]; this
0x1800b41ec  test    ebx, ebx
0x1800b41ee  jns     short loc_1800B4213
0x1800b41f0  mov     r9d, ebx; char *
0x1800b41f3  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b41fa  mov     edx, 81h; void *
0x1800b41ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b4204  mov     rax, [rdi]
0x1800b4207  mov     rcx, rdi
0x1800b420a  mov     rax, [rax+20h]
0x1800b420e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4213  mov     ebx, [rdi+40h]
0x1800b4216  test    ebx, ebx
0x1800b4218  jns     short loc_1800B4221
0x1800b421a  mov     edx, 8Ah
0x1800b421f  jmp     short loc_1800B4232
0x1800b4221  mov     rcx, [rsp+8E0h+var_878]
0x1800b4226  mov     ebx, [rcx+4]
0x1800b4229  test    ebx, ebx
0x1800b422b  jns     short loc_1800B424A
0x1800b422d  mov     edx, 8Ch; void *
0x1800b4232  mov     r9d, ebx; char *
0x1800b4235  mov     rcx, [rbp+7E8h]; this
0x1800b423c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b4243  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4248  jmp     short loc_1800B4268
0x1800b424a  mov     rdx, [rbp+7E0h+arg_20]
0x1800b4251  call    ??$CastTo@UXvmAudioEndpointVolumeGetMute@@@XvmMessage@@QEAAJPEAPEAUXvmAudioEndpointVolumeGetMute@@@Z; XvmMessage::CastTo<XvmAudioEndpointVolumeGetMute>(XvmAudioEndpointVolumeGetMute * *)
0x1800b4256  mov     ebx, eax
0x1800b4258  test    eax, eax
0x1800b425a  jns     short loc_1800B4266
0x1800b425c  mov     r9d, eax
0x1800b425f  mov     edx, 8Dh
0x1800b4264  jmp     short loc_1800B4235
0x1800b4266  xor     ebx, ebx
0x1800b4268  mov     rcx, [rbp+7E0h+arg_18]
0x1800b426f  mov     rax, [rsp+8E0h+var_878]
0x1800b4274  mov     [rcx], rax
0x1800b4277  mov     eax, ebx
0x1800b4279  lea     r11, [rsp+8E0h+var_10]
0x1800b4281  mov     rbx, [r11+28h]
0x1800b4285  mov     rsi, [r11+30h]
0x1800b4289  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b428e  mov     rsp, r11
0x1800b4291  pop     r14
0x1800b4293  pop     rdi
0x1800b4294  pop     rbp
0x1800b4295  retn
```
