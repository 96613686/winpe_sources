# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetChannelCount>(uint,XvmGetChannelCount,XvmMessage * *,XvmGetChannelCount * *)

- ea: `0x1800bbf34`
- end: `0x1800bc27a`
- name: `??$SendAndValidateResponse@UXvmGetChannelCount@@@CGuestXvmAudioObject@@QEAAJIUXvmGetChannelCount@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c0070`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2860`
- `0x1800bbf34`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bbf76`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bc061`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bbf76`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bc061`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bbfaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bbfaa`

## string_xrefs

- `0x1800bbf8d`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bbfcc`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bc1d7`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bc220`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetChannelCount>(__int64 a1, unsigned int a2, int a3, ...)
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
    v32 = 16;
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
            (unsigned int)&unk_1801686E4,
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
          (unsigned int)&unk_18016875D,
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
        Channel = XvmMessage::CastTo<XvmGetChannelCount>(v21, v39, v12);
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
0x1800bbf34  mov     rax, rsp
0x1800bbf37  mov     [rax+10h], rbx
0x1800bbf3b  mov     [rax+18h], rsi
0x1800bbf3f  mov     [rax+20h], r9
0x1800bbf43  push    rbp
0x1800bbf44  push    rdi
0x1800bbf45  push    r14
0x1800bbf47  lea     rbp, [rax-7E8h]
0x1800bbf4e  sub     rsp, 8D0h
0x1800bbf55  movaps  xmmword ptr [rax-28h], xmm6
0x1800bbf59  mov     ebx, r8d
0x1800bbf5c  mov     r14d, edx
0x1800bbf5f  mov     rdi, rcx
0x1800bbf62  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bbf6a  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800bbf72  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800bbf76  call    cs:__imp_QueryPerformanceCounter
0x1800bbf7c  mov     esi, [rdi+40h]
0x1800bbf7f  test    esi, esi
0x1800bbf81  jns     short loc_1800BBFA5
0x1800bbf83  mov     rcx, [rbp+7E8h]; this
0x1800bbf8a  mov     r9d, esi; char *
0x1800bbf8d  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bbf94  mov     edx, 4Fh ; 'O'; void *
0x1800bbf99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbf9e  mov     eax, esi
0x1800bbfa0  jmp     loc_1800BC25D
0x1800bbfa5  mov     ecx, 810h; cb
0x1800bbfaa  call    cs:__imp_CoTaskMemAlloc
0x1800bbfb0  mov     rsi, rax
0x1800bbfb3  mov     [rsp+8E0h+var_878], rax
0x1800bbfb8  test    rax, rax
0x1800bbfbb  jnz     short loc_1800BBFE0
0x1800bbfbd  mov     rcx, [rbp+7E8h]; this
0x1800bbfc4  mov     ebx, 8007000Eh
0x1800bbfc9  mov     r9d, ebx; char *
0x1800bbfcc  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bbfd3  lea     edx, [rax+52h]; void *
0x1800bbfd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbfdb  jmp     loc_1800BC25B
0x1800bbfe0  mov     [rbp+7E0h+Src], 0
0x1800bbfe8  mov     [rbp+7E0h+var_824], 0
0x1800bbfef  xor     edx, edx; Val
0x1800bbff1  mov     r8d, 800h; Size
0x1800bbff7  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bbffb  call    memset_0
0x1800bc000  mov     [rbp+7E0h+var_820], ebx
0x1800bc003  mov     [rbp+7E0h+var_828], 10h
0x1800bc00a  mov     rcx, rsi; void *
0x1800bc00d  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bc011  mov     r8d, 810h; Size
0x1800bc017  call    memcpy_0
0x1800bc01c  mov     rax, [rsp+8E0h+var_878]
0x1800bc021  mov     [rax+0Ch], r14d
0x1800bc025  lea     rax, [rbp+7E0h+arg_18]
0x1800bc02c  mov     [rbp+7E0h+var_848], rax
0x1800bc030  lea     rax, [rsp+8E0h+var_878]
0x1800bc035  mov     [rbp+7E0h+var_840], rax
0x1800bc039  mov     [rbp+7E0h+var_838], 1
0x1800bc03d  mov     rcx, [rdi+28h]
0x1800bc041  mov     rax, [rcx]
0x1800bc044  mov     r9d, 810h
0x1800bc04a  mov     r8, [rsp+8E0h+var_878]
0x1800bc04f  mov     edx, r14d
0x1800bc052  mov     rax, [rax+20h]
0x1800bc056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc05b  mov     ebx, eax
0x1800bc05d  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800bc061  call    cs:__imp_QueryPerformanceCounter
0x1800bc067  xorps   xmm6, xmm6
0x1800bc06a  cmp     qword ptr [rdi+48h], 0
0x1800bc06f  jz      short loc_1800BC093
0x1800bc071  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800bc075  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800bc079  cvtsi2ss xmm6, rcx
0x1800bc07e  mulss   xmm6, cs:__real@447a0000
0x1800bc086  xorps   xmm0, xmm0
0x1800bc089  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800bc08f  divss   xmm6, xmm0
0x1800bc093  mov     rcx, [rsp+8E0h+var_878]
0x1800bc098  cmp     dword ptr [rcx+8], 1
0x1800bc09c  jnz     loc_1800BC158
0x1800bc0a2  mov     [rsp+8E0h+var_870], 0
0x1800bc0ab  lea     rdx, [rsp+8E0h+var_870]
0x1800bc0b0  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bc0b5  test    eax, eax
0x1800bc0b7  js      loc_1800BC1C9
0x1800bc0bd  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bc0c2  mov     r8, rax
0x1800bc0c5  mov     ecx, [rax]
0x1800bc0c7  cmp     ecx, 4
0x1800bc0ca  jbe     loc_1800BC1C9
0x1800bc0d0  mov     [rbp+7E0h+arg_0], ebx
0x1800bc0d6  movss   [rsp+8E0h+var_868], xmm6
0x1800bc0dc  mov     [rbp+7E0h+var_860], rdi
0x1800bc0e0  mov     rdx, [rsp+8E0h+var_870]
0x1800bc0e5  mov     ecx, [rdx+10h]
0x1800bc0e8  mov     [rsp+8E0h+var_864], ecx
0x1800bc0ec  mov     ecx, [rdx+4]
0x1800bc0ef  mov     [rsp+8E0h+var_880], ecx
0x1800bc0f3  mov     eax, [rdx+8]
0x1800bc0f6  mov     [rsp+8E0h+var_880+4], eax
0x1800bc0fa  mov     eax, [rdx]
0x1800bc0fc  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800bc100  lea     rax, [rbp+7E0h+arg_0]
0x1800bc107  mov     [rsp+8E0h+var_890], rax
0x1800bc10c  lea     rax, [rsp+8E0h+var_868]
0x1800bc111  mov     [rsp+8E0h+var_898], rax
0x1800bc116  lea     rax, [rbp+7E0h+var_860]
0x1800bc11a  mov     [rsp+8E0h+var_8A0], rax
0x1800bc11f  lea     rax, [rsp+8E0h+var_864]
0x1800bc124  mov     [rsp+8E0h+var_8A8], rax
0x1800bc129  lea     rax, [rsp+8E0h+var_880]
0x1800bc12e  mov     [rsp+8E0h+var_8B0], rax
0x1800bc133  lea     rax, [rsp+8E0h+var_880+4]
0x1800bc138  mov     [rsp+8E0h+var_8B8], rax
0x1800bc13d  lea     rax, [rsp+8E0h+var_870]
0x1800bc142  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bc147  lea     rdx, unk_1801686E4
0x1800bc14e  mov     rcx, r8
0x1800bc151  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bc156  jmp     short loc_1800BC1C9
0x1800bc158  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bc15d  mov     ecx, [rax]
0x1800bc15f  cmp     ecx, 4
0x1800bc162  jbe     short loc_1800BC1C9
0x1800bc164  mov     [rbp+7E0h+arg_0], ebx
0x1800bc16a  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bc170  mov     [rbp+7E0h+var_860], rdi
0x1800bc174  mov     rcx, [rsp+8E0h+var_878]
0x1800bc179  mov     edx, [rcx+8]
0x1800bc17c  mov     [rsp+8E0h+var_880+4], edx
0x1800bc180  mov     ecx, [rdi+30h]
0x1800bc183  mov     [rsp+8E0h+var_880], ecx
0x1800bc187  lea     rcx, [rbp+7E0h+arg_0]
0x1800bc18e  mov     [rsp+8E0h+var_8A0], rcx
0x1800bc193  lea     rcx, [rsp+8E0h+var_870]
0x1800bc198  mov     [rsp+8E0h+var_8A8], rcx
0x1800bc19d  lea     rcx, [rbp+7E0h+var_860]
0x1800bc1a1  mov     [rsp+8E0h+var_8B0], rcx
0x1800bc1a6  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bc1ab  mov     [rsp+8E0h+var_8B8], rcx
0x1800bc1b0  lea     rcx, [rsp+8E0h+var_880]
0x1800bc1b5  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bc1ba  lea     rdx, unk_18016875D
0x1800bc1c1  mov     rcx, rax
0x1800bc1c4  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bc1c9  mov     rcx, [rbp+7E8h]; this
0x1800bc1d0  test    ebx, ebx
0x1800bc1d2  jns     short loc_1800BC1F7
0x1800bc1d4  mov     r9d, ebx; char *
0x1800bc1d7  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bc1de  mov     edx, 81h; void *
0x1800bc1e3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bc1e8  mov     rax, [rdi]
0x1800bc1eb  mov     rcx, rdi
0x1800bc1ee  mov     rax, [rax+20h]
0x1800bc1f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc1f7  mov     ebx, [rdi+40h]
0x1800bc1fa  test    ebx, ebx
0x1800bc1fc  jns     short loc_1800BC205
0x1800bc1fe  mov     edx, 8Ah
0x1800bc203  jmp     short loc_1800BC216
0x1800bc205  mov     rcx, [rsp+8E0h+var_878]
0x1800bc20a  mov     ebx, [rcx+4]
0x1800bc20d  test    ebx, ebx
0x1800bc20f  jns     short loc_1800BC22E
0x1800bc211  mov     edx, 8Ch; void *
0x1800bc216  mov     r9d, ebx; char *
0x1800bc219  mov     rcx, [rbp+7E8h]; this
0x1800bc220  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bc227  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc22c  jmp     short loc_1800BC24C
0x1800bc22e  mov     rdx, [rbp+7E0h+arg_20]
0x1800bc235  call    ??$CastTo@UXvmGetChannelCount@@@XvmMessage@@QEAAJPEAPEAUXvmGetChannelCount@@@Z; XvmMessage::CastTo<XvmGetChannelCount>(XvmGetChannelCount * *)
0x1800bc23a  mov     ebx, eax
0x1800bc23c  test    eax, eax
0x1800bc23e  jns     short loc_1800BC24A
0x1800bc240  mov     r9d, eax
0x1800bc243  mov     edx, 8Dh
0x1800bc248  jmp     short loc_1800BC219
0x1800bc24a  xor     ebx, ebx
0x1800bc24c  mov     rcx, [rbp+7E0h+arg_18]
0x1800bc253  mov     rax, [rsp+8E0h+var_878]
0x1800bc258  mov     [rcx], rax
0x1800bc25b  mov     eax, ebx
0x1800bc25d  lea     r11, [rsp+8E0h+var_10]
0x1800bc265  mov     rbx, [r11+28h]
0x1800bc269  mov     rsi, [r11+30h]
0x1800bc26d  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bc272  mov     rsp, r11
0x1800bc275  pop     r14
0x1800bc277  pop     rdi
0x1800bc278  pop     rbp
0x1800bc279  retn
```
