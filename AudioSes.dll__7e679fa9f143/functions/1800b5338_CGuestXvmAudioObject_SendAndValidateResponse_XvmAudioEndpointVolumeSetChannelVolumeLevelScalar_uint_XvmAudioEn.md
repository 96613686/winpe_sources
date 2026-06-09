# CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeSetChannelVolumeLevelScalar>(uint,XvmAudioEndpointVolumeSetChannelVolumeLevelScalar,XvmMessage * *,XvmAudioEndpointVolumeSetChannelVolumeLevelScalar * *)

- ea: `0x1800b5338`
- end: `0x1800b568b`
- name: `??$SendAndValidateResponse@UXvmAudioEndpointVolumeSetChannelVolumeLevelScalar@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeSetChannelVolumeLevelScalar@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `851`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b7540`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a5f60`
- `0x1800b5338`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b537a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b5472`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b537a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b5472`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b53ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b53ae`

## string_xrefs

- `0x1800b5391`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b53d0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b55e8`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b5631`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeSetChannelVolumeLevelScalar>(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        ...)
{
  int v6; // edi
  _DWORD *v8; // rdi
  int v9; // ebx
  int v10; // edi
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
  __int64 v34; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v35; // [rsp+D0h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+8F0h] [rbp+7E8h]
  int v37; // [rsp+8F8h] [rbp+7F0h] BYREF
  _QWORD *v38; // [rsp+910h] [rbp+808h] BYREF
  va_list va; // [rsp+910h] [rbp+808h]
  __int64 v40; // [rsp+918h] [rbp+810h]
  va_list va1; // [rsp+920h] [rbp+818h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v38 = va_arg(va1, _QWORD *);
  v40 = va_arg(va1, _QWORD);
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
    memset_0(&v34, 0, 0x800u);
    v34 = *a3;
    v35 = *(_OWORD *)(a3 + 1);
    v32 = 87;
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
          v37 = v10;
          v23 = v11;
          v25 = a1;
          v24 = v22[4];
          v20[0] = v22[1];
          v20[1] = v22[2];
          LODWORD(v22) = *v22;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v12,
            (unsigned int)&unk_180166E24,
            (_DWORD)v12,
            v13,
            (__int64)&v22,
            (__int64)&v20[1],
            (__int64)v20,
            (__int64)&v24,
            (__int64)&v25,
            (__int64)&v23,
            (__int64)&v37);
        }
      }
    }
    else
    {
      v14 = GuestXvmAudioObjectTelemetryProvider::Provider();
      if ( *(_DWORD *)v14 > 4u )
      {
        v37 = v10;
        *(float *)&v22 = v11;
        v25 = a1;
        v20[1] = v21[2];
        v20[0] = *(_DWORD *)(a1 + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v14,
          (unsigned int)&unk_180166E9D,
          (_DWORD)v12,
          v15,
          (__int64)v20,
          (__int64)&v20[1],
          (__int64)&v25,
          (__int64)&v22,
          (__int64)&v37);
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
        v18 = XvmMessage::CastTo<XvmAudioEndpointVolumeSetChannelVolumeLevelScalar>(v21, v40, v12);
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
        *v38 = v21;
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
0x1800b5338  mov     rax, rsp
0x1800b533b  mov     [rax+10h], rbx
0x1800b533f  mov     [rax+18h], rsi
0x1800b5343  mov     [rax+20h], r9
0x1800b5347  push    rbp
0x1800b5348  push    rdi
0x1800b5349  push    r14
0x1800b534b  lea     rbp, [rax-7E8h]
0x1800b5352  sub     rsp, 8D0h
0x1800b5359  movaps  xmmword ptr [rax-28h], xmm6
0x1800b535d  mov     rsi, r8
0x1800b5360  mov     r14d, edx
0x1800b5363  mov     rbx, rcx
0x1800b5366  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800b536e  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800b5376  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800b537a  call    cs:__imp_QueryPerformanceCounter
0x1800b5380  mov     edi, [rbx+40h]
0x1800b5383  test    edi, edi
0x1800b5385  jns     short loc_1800B53A9
0x1800b5387  mov     rcx, [rbp+7E8h]; this
0x1800b538e  mov     r9d, edi; char *
0x1800b5391  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b5398  mov     edx, 4Fh ; 'O'; void *
0x1800b539d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b53a2  mov     eax, edi
0x1800b53a4  jmp     loc_1800B566E
0x1800b53a9  mov     ecx, 810h; cb
0x1800b53ae  call    cs:__imp_CoTaskMemAlloc
0x1800b53b4  mov     rdi, rax
0x1800b53b7  mov     [rsp+8E0h+var_878], rax
0x1800b53bc  test    rax, rax
0x1800b53bf  jnz     short loc_1800B53E4
0x1800b53c1  mov     rcx, [rbp+7E8h]; this
0x1800b53c8  mov     ebx, 8007000Eh
0x1800b53cd  mov     r9d, ebx; char *
0x1800b53d0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b53d7  lea     edx, [rax+52h]; void *
0x1800b53da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b53df  jmp     loc_1800B566C
0x1800b53e4  mov     [rbp+7E0h+Src], 0
0x1800b53ec  mov     [rbp+7E0h+var_824], 0
0x1800b53f3  xor     edx, edx; Val
0x1800b53f5  mov     r8d, 800h; Size
0x1800b53fb  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800b53ff  call    memset_0
0x1800b5404  mov     rax, [rsi]
0x1800b5407  mov     [rbp+7E0h+var_820], rax
0x1800b540b  movups  xmm0, xmmword ptr [rsi+8]
0x1800b540f  movdqu  [rbp+7E0h+var_818], xmm0
0x1800b5414  mov     [rbp+7E0h+var_828], 57h ; 'W'
0x1800b541b  mov     rcx, rdi; void *
0x1800b541e  lea     rdx, [rbp+7E0h+Src]; Src
0x1800b5422  mov     r8d, 810h; Size
0x1800b5428  call    memcpy_0
0x1800b542d  mov     rax, [rsp+8E0h+var_878]
0x1800b5432  mov     [rax+0Ch], r14d
0x1800b5436  lea     rax, [rbp+7E0h+arg_18]
0x1800b543d  mov     [rbp+7E0h+var_848], rax
0x1800b5441  lea     rax, [rsp+8E0h+var_878]
0x1800b5446  mov     [rbp+7E0h+var_840], rax
0x1800b544a  mov     [rbp+7E0h+var_838], 1
0x1800b544e  mov     rcx, [rbx+28h]
0x1800b5452  mov     rax, [rcx]
0x1800b5455  mov     r9d, 810h
0x1800b545b  mov     r8, [rsp+8E0h+var_878]
0x1800b5460  mov     edx, r14d
0x1800b5463  mov     rax, [rax+20h]
0x1800b5467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b546c  mov     edi, eax
0x1800b546e  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800b5472  call    cs:__imp_QueryPerformanceCounter
0x1800b5478  xorps   xmm6, xmm6
0x1800b547b  cmp     qword ptr [rbx+48h], 0
0x1800b5480  jz      short loc_1800B54A4
0x1800b5482  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800b5486  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800b548a  cvtsi2ss xmm6, rcx
0x1800b548f  mulss   xmm6, cs:__real@447a0000
0x1800b5497  xorps   xmm0, xmm0
0x1800b549a  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800b54a0  divss   xmm6, xmm0
0x1800b54a4  mov     rcx, [rsp+8E0h+var_878]
0x1800b54a9  cmp     dword ptr [rcx+8], 1
0x1800b54ad  jnz     loc_1800B5569
0x1800b54b3  mov     [rsp+8E0h+var_870], 0
0x1800b54bc  lea     rdx, [rsp+8E0h+var_870]
0x1800b54c1  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b54c6  test    eax, eax
0x1800b54c8  js      loc_1800B55DA
0x1800b54ce  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b54d3  mov     r8, rax
0x1800b54d6  mov     ecx, [rax]
0x1800b54d8  cmp     ecx, 4
0x1800b54db  jbe     loc_1800B55DA
0x1800b54e1  mov     [rbp+7E0h+arg_0], edi
0x1800b54e7  movss   [rsp+8E0h+var_868], xmm6
0x1800b54ed  mov     [rbp+7E0h+var_860], rbx
0x1800b54f1  mov     rdx, [rsp+8E0h+var_870]
0x1800b54f6  mov     ecx, [rdx+10h]
0x1800b54f9  mov     [rsp+8E0h+var_864], ecx
0x1800b54fd  mov     ecx, [rdx+4]
0x1800b5500  mov     [rsp+8E0h+var_880], ecx
0x1800b5504  mov     eax, [rdx+8]
0x1800b5507  mov     [rsp+8E0h+var_880+4], eax
0x1800b550b  mov     eax, [rdx]
0x1800b550d  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800b5511  lea     rax, [rbp+7E0h+arg_0]
0x1800b5518  mov     [rsp+8E0h+var_890], rax
0x1800b551d  lea     rax, [rsp+8E0h+var_868]
0x1800b5522  mov     [rsp+8E0h+var_898], rax
0x1800b5527  lea     rax, [rbp+7E0h+var_860]
0x1800b552b  mov     [rsp+8E0h+var_8A0], rax
0x1800b5530  lea     rax, [rsp+8E0h+var_864]
0x1800b5535  mov     [rsp+8E0h+var_8A8], rax
0x1800b553a  lea     rax, [rsp+8E0h+var_880]
0x1800b553f  mov     [rsp+8E0h+var_8B0], rax
0x1800b5544  lea     rax, [rsp+8E0h+var_880+4]
0x1800b5549  mov     [rsp+8E0h+var_8B8], rax
0x1800b554e  lea     rax, [rsp+8E0h+var_870]
0x1800b5553  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800b5558  lea     rdx, unk_180166E24
0x1800b555f  mov     rcx, r8
0x1800b5562  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b5567  jmp     short loc_1800B55DA
0x1800b5569  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b556e  mov     ecx, [rax]
0x1800b5570  cmp     ecx, 4
0x1800b5573  jbe     short loc_1800B55DA
0x1800b5575  mov     [rbp+7E0h+arg_0], edi
0x1800b557b  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800b5581  mov     [rbp+7E0h+var_860], rbx
0x1800b5585  mov     rcx, [rsp+8E0h+var_878]
0x1800b558a  mov     edx, [rcx+8]
0x1800b558d  mov     [rsp+8E0h+var_880+4], edx
0x1800b5591  mov     ecx, [rbx+30h]
0x1800b5594  mov     [rsp+8E0h+var_880], ecx
0x1800b5598  lea     rcx, [rbp+7E0h+arg_0]
0x1800b559f  mov     [rsp+8E0h+var_8A0], rcx
0x1800b55a4  lea     rcx, [rsp+8E0h+var_870]
0x1800b55a9  mov     [rsp+8E0h+var_8A8], rcx
0x1800b55ae  lea     rcx, [rbp+7E0h+var_860]
0x1800b55b2  mov     [rsp+8E0h+var_8B0], rcx
0x1800b55b7  lea     rcx, [rsp+8E0h+var_880+4]
0x1800b55bc  mov     [rsp+8E0h+var_8B8], rcx
0x1800b55c1  lea     rcx, [rsp+8E0h+var_880]
0x1800b55c6  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800b55cb  lea     rdx, unk_180166E9D
0x1800b55d2  mov     rcx, rax
0x1800b55d5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b55da  mov     rcx, [rbp+7E8h]; this
0x1800b55e1  test    edi, edi
0x1800b55e3  jns     short loc_1800B5608
0x1800b55e5  mov     r9d, edi; char *
0x1800b55e8  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b55ef  mov     edx, 81h; void *
0x1800b55f4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b55f9  mov     rax, [rbx]
0x1800b55fc  mov     rcx, rbx
0x1800b55ff  mov     rax, [rax+20h]
0x1800b5603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5608  mov     ebx, [rbx+40h]
0x1800b560b  test    ebx, ebx
0x1800b560d  jns     short loc_1800B5616
0x1800b560f  mov     edx, 8Ah
0x1800b5614  jmp     short loc_1800B5627
0x1800b5616  mov     rcx, [rsp+8E0h+var_878]
0x1800b561b  mov     ebx, [rcx+4]
0x1800b561e  test    ebx, ebx
0x1800b5620  jns     short loc_1800B563F
0x1800b5622  mov     edx, 8Ch; void *
0x1800b5627  mov     r9d, ebx; char *
0x1800b562a  mov     rcx, [rbp+7E8h]; this
0x1800b5631  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b5638  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b563d  jmp     short loc_1800B565D
0x1800b563f  mov     rdx, [rbp+7E0h+arg_20]
0x1800b5646  call    ??$CastTo@UXvmAudioEndpointVolumeSetChannelVolumeLevelScalar@@@XvmMessage@@QEAAJPEAPEAUXvmAudioEndpointVolumeSetChannelVolumeLevelScalar@@@Z; XvmMessage::CastTo<XvmAudioEndpointVolumeSetChannelVolumeLevelScalar>(XvmAudioEndpointVolumeSetChannelVolumeLevelScalar * *)
0x1800b564b  mov     ebx, eax
0x1800b564d  test    eax, eax
0x1800b564f  jns     short loc_1800B565B
0x1800b5651  mov     r9d, eax
0x1800b5654  mov     edx, 8Dh
0x1800b5659  jmp     short loc_1800B562A
0x1800b565b  xor     ebx, ebx
0x1800b565d  mov     rcx, [rbp+7E0h+arg_18]
0x1800b5664  mov     rax, [rsp+8E0h+var_878]
0x1800b5669  mov     [rcx], rax
0x1800b566c  mov     eax, ebx
0x1800b566e  lea     r11, [rsp+8E0h+var_10]
0x1800b5676  mov     rbx, [r11+28h]
0x1800b567a  mov     rsi, [r11+30h]
0x1800b567e  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b5683  mov     rsp, r11
0x1800b5686  pop     r14
0x1800b5688  pop     rdi
0x1800b5689  pop     rbp
0x1800b568a  retn
```
