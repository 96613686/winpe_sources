# CGuestXvmAudioObject::SendAndValidateResponse<XvmSetChannelVolume>(uint,XvmSetChannelVolume,XvmMessage * *,XvmSetChannelVolume * *)

- ea: `0x1800be4a8`
- end: `0x1800be7ef`
- name: `??$SendAndValidateResponse@UXvmSetChannelVolume@@@CGuestXvmAudioObject@@QEAAJIUXvmSetChannelVolume@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `839`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c2080`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2d98`
- `0x1800be4a8`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800be4ea`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800be5d6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800be4ea`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800be5d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be51e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be51e`

## string_xrefs

- `0x1800be501`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800be540`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800be74c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800be795`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmSetChannelVolume>(
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
    v32 = 17;
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
            (unsigned int)&unk_18016861E,
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
          (unsigned int)&unk_180168697,
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
        v18 = XvmMessage::CastTo<XvmSetChannelVolume>(v21, v39, v12);
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
0x1800be4a8  mov     rax, rsp
0x1800be4ab  mov     [rax+10h], rbx
0x1800be4af  mov     [rax+18h], rsi
0x1800be4b3  mov     [rax+20h], r9
0x1800be4b7  push    rbp
0x1800be4b8  push    rdi
0x1800be4b9  push    r14
0x1800be4bb  lea     rbp, [rax-7E8h]
0x1800be4c2  sub     rsp, 8D0h
0x1800be4c9  movaps  xmmword ptr [rax-28h], xmm6
0x1800be4cd  mov     rbx, r8
0x1800be4d0  mov     r14d, edx
0x1800be4d3  mov     rdi, rcx
0x1800be4d6  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800be4de  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800be4e6  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800be4ea  call    cs:__imp_QueryPerformanceCounter
0x1800be4f0  mov     esi, [rdi+40h]
0x1800be4f3  test    esi, esi
0x1800be4f5  jns     short loc_1800BE519
0x1800be4f7  mov     rcx, [rbp+7E8h]; this
0x1800be4fe  mov     r9d, esi; char *
0x1800be501  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800be508  mov     edx, 4Fh ; 'O'; void *
0x1800be50d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be512  mov     eax, esi
0x1800be514  jmp     loc_1800BE7D2
0x1800be519  mov     ecx, 810h; cb
0x1800be51e  call    cs:__imp_CoTaskMemAlloc
0x1800be524  mov     rsi, rax
0x1800be527  mov     [rsp+8E0h+var_878], rax
0x1800be52c  test    rax, rax
0x1800be52f  jnz     short loc_1800BE554
0x1800be531  mov     rcx, [rbp+7E8h]; this
0x1800be538  mov     ebx, 8007000Eh
0x1800be53d  mov     r9d, ebx; char *
0x1800be540  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800be547  lea     edx, [rax+52h]; void *
0x1800be54a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be54f  jmp     loc_1800BE7D0
0x1800be554  mov     [rbp+7E0h+Src], 0
0x1800be55c  mov     [rbp+7E0h+var_824], 0
0x1800be563  xor     edx, edx; Val
0x1800be565  mov     r8d, 800h; Size
0x1800be56b  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800be56f  call    memset_0
0x1800be574  mov     [rbp+7E0h+var_820], rbx
0x1800be578  mov     [rbp+7E0h+var_828], 11h
0x1800be57f  mov     rcx, rsi; void *
0x1800be582  lea     rdx, [rbp+7E0h+Src]; Src
0x1800be586  mov     r8d, 810h; Size
0x1800be58c  call    memcpy_0
0x1800be591  mov     rax, [rsp+8E0h+var_878]
0x1800be596  mov     [rax+0Ch], r14d
0x1800be59a  lea     rax, [rbp+7E0h+arg_18]
0x1800be5a1  mov     [rbp+7E0h+var_848], rax
0x1800be5a5  lea     rax, [rsp+8E0h+var_878]
0x1800be5aa  mov     [rbp+7E0h+var_840], rax
0x1800be5ae  mov     [rbp+7E0h+var_838], 1
0x1800be5b2  mov     rcx, [rdi+28h]
0x1800be5b6  mov     rax, [rcx]
0x1800be5b9  mov     r9d, 810h
0x1800be5bf  mov     r8, [rsp+8E0h+var_878]
0x1800be5c4  mov     edx, r14d
0x1800be5c7  mov     rax, [rax+20h]
0x1800be5cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be5d0  mov     ebx, eax
0x1800be5d2  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800be5d6  call    cs:__imp_QueryPerformanceCounter
0x1800be5dc  xorps   xmm6, xmm6
0x1800be5df  cmp     qword ptr [rdi+48h], 0
0x1800be5e4  jz      short loc_1800BE608
0x1800be5e6  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800be5ea  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800be5ee  cvtsi2ss xmm6, rcx
0x1800be5f3  mulss   xmm6, cs:__real@447a0000
0x1800be5fb  xorps   xmm0, xmm0
0x1800be5fe  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800be604  divss   xmm6, xmm0
0x1800be608  mov     rcx, [rsp+8E0h+var_878]
0x1800be60d  cmp     dword ptr [rcx+8], 1
0x1800be611  jnz     loc_1800BE6CD
0x1800be617  mov     [rsp+8E0h+var_870], 0
0x1800be620  lea     rdx, [rsp+8E0h+var_870]
0x1800be625  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800be62a  test    eax, eax
0x1800be62c  js      loc_1800BE73E
0x1800be632  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800be637  mov     r8, rax
0x1800be63a  mov     ecx, [rax]
0x1800be63c  cmp     ecx, 4
0x1800be63f  jbe     loc_1800BE73E
0x1800be645  mov     [rbp+7E0h+arg_0], ebx
0x1800be64b  movss   [rsp+8E0h+var_868], xmm6
0x1800be651  mov     [rbp+7E0h+var_860], rdi
0x1800be655  mov     rdx, [rsp+8E0h+var_870]
0x1800be65a  mov     ecx, [rdx+10h]
0x1800be65d  mov     [rsp+8E0h+var_864], ecx
0x1800be661  mov     ecx, [rdx+4]
0x1800be664  mov     [rsp+8E0h+var_880], ecx
0x1800be668  mov     eax, [rdx+8]
0x1800be66b  mov     [rsp+8E0h+var_880+4], eax
0x1800be66f  mov     eax, [rdx]
0x1800be671  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800be675  lea     rax, [rbp+7E0h+arg_0]
0x1800be67c  mov     [rsp+8E0h+var_890], rax
0x1800be681  lea     rax, [rsp+8E0h+var_868]
0x1800be686  mov     [rsp+8E0h+var_898], rax
0x1800be68b  lea     rax, [rbp+7E0h+var_860]
0x1800be68f  mov     [rsp+8E0h+var_8A0], rax
0x1800be694  lea     rax, [rsp+8E0h+var_864]
0x1800be699  mov     [rsp+8E0h+var_8A8], rax
0x1800be69e  lea     rax, [rsp+8E0h+var_880]
0x1800be6a3  mov     [rsp+8E0h+var_8B0], rax
0x1800be6a8  lea     rax, [rsp+8E0h+var_880+4]
0x1800be6ad  mov     [rsp+8E0h+var_8B8], rax
0x1800be6b2  lea     rax, [rsp+8E0h+var_870]
0x1800be6b7  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800be6bc  lea     rdx, unk_18016861E
0x1800be6c3  mov     rcx, r8
0x1800be6c6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800be6cb  jmp     short loc_1800BE73E
0x1800be6cd  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800be6d2  mov     ecx, [rax]
0x1800be6d4  cmp     ecx, 4
0x1800be6d7  jbe     short loc_1800BE73E
0x1800be6d9  mov     [rbp+7E0h+arg_0], ebx
0x1800be6df  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800be6e5  mov     [rbp+7E0h+var_860], rdi
0x1800be6e9  mov     rcx, [rsp+8E0h+var_878]
0x1800be6ee  mov     edx, [rcx+8]
0x1800be6f1  mov     [rsp+8E0h+var_880+4], edx
0x1800be6f5  mov     ecx, [rdi+30h]
0x1800be6f8  mov     [rsp+8E0h+var_880], ecx
0x1800be6fc  lea     rcx, [rbp+7E0h+arg_0]
0x1800be703  mov     [rsp+8E0h+var_8A0], rcx
0x1800be708  lea     rcx, [rsp+8E0h+var_870]
0x1800be70d  mov     [rsp+8E0h+var_8A8], rcx
0x1800be712  lea     rcx, [rbp+7E0h+var_860]
0x1800be716  mov     [rsp+8E0h+var_8B0], rcx
0x1800be71b  lea     rcx, [rsp+8E0h+var_880+4]
0x1800be720  mov     [rsp+8E0h+var_8B8], rcx
0x1800be725  lea     rcx, [rsp+8E0h+var_880]
0x1800be72a  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800be72f  lea     rdx, unk_180168697
0x1800be736  mov     rcx, rax
0x1800be739  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800be73e  mov     rcx, [rbp+7E8h]; this
0x1800be745  test    ebx, ebx
0x1800be747  jns     short loc_1800BE76C
0x1800be749  mov     r9d, ebx; char *
0x1800be74c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800be753  mov     edx, 81h; void *
0x1800be758  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800be75d  mov     rax, [rdi]
0x1800be760  mov     rcx, rdi
0x1800be763  mov     rax, [rax+20h]
0x1800be767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be76c  mov     ebx, [rdi+40h]
0x1800be76f  test    ebx, ebx
0x1800be771  jns     short loc_1800BE77A
0x1800be773  mov     edx, 8Ah
0x1800be778  jmp     short loc_1800BE78B
0x1800be77a  mov     rcx, [rsp+8E0h+var_878]
0x1800be77f  mov     ebx, [rcx+4]
0x1800be782  test    ebx, ebx
0x1800be784  jns     short loc_1800BE7A3
0x1800be786  mov     edx, 8Ch; void *
0x1800be78b  mov     r9d, ebx; char *
0x1800be78e  mov     rcx, [rbp+7E8h]; this
0x1800be795  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800be79c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be7a1  jmp     short loc_1800BE7C1
0x1800be7a3  mov     rdx, [rbp+7E0h+arg_20]
0x1800be7aa  call    ??$CastTo@UXvmSetChannelVolume@@@XvmMessage@@QEAAJPEAPEAUXvmSetChannelVolume@@@Z; XvmMessage::CastTo<XvmSetChannelVolume>(XvmSetChannelVolume * *)
0x1800be7af  mov     ebx, eax
0x1800be7b1  test    eax, eax
0x1800be7b3  jns     short loc_1800BE7BF
0x1800be7b5  mov     r9d, eax
0x1800be7b8  mov     edx, 8Dh
0x1800be7bd  jmp     short loc_1800BE78E
0x1800be7bf  xor     ebx, ebx
0x1800be7c1  mov     rcx, [rbp+7E0h+arg_18]
0x1800be7c8  mov     rax, [rsp+8E0h+var_878]
0x1800be7cd  mov     [rcx], rax
0x1800be7d0  mov     eax, ebx
0x1800be7d2  lea     r11, [rsp+8E0h+var_10]
0x1800be7da  mov     rbx, [r11+28h]
0x1800be7de  mov     rsi, [r11+30h]
0x1800be7e2  movaps  xmm6, xmmword ptr [r11-10h]
0x1800be7e7  mov     rsp, r11
0x1800be7ea  pop     r14
0x1800be7ec  pop     rdi
0x1800be7ed  pop     rbp
0x1800be7ee  retn
```
