# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetStreamLatency>(uint,XvmGetStreamLatency,XvmMessage * *,XvmGetStreamLatency * *)

- ea: `0x1800acadc`
- end: `0x1800ace23`
- name: `??$SendAndValidateResponse@UXvmGetStreamLatency@@@CGuestXvmAudioObject@@QEAAJIUXvmGetStreamLatency@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `839`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800afeb0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2b30`
- `0x1800acadc`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800acb1e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800acc0a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800acb1e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800acc0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800acb52`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800acb52`

## string_xrefs

- `0x1800acb35`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800acb74`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800acd80`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800acdc9`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetStreamLatency>(
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
  int Stream; // eax
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
    v32 = 6;
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
            (unsigned int)&byte_1801663B7,
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
          (unsigned int)&dword_1801662A4,
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
        Stream = XvmMessage::CastTo<XvmGetStreamLatency>(v21, v39, v12);
        v9 = Stream;
        if ( Stream >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)Stream;
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
0x1800acadc  mov     rax, rsp
0x1800acadf  mov     [rax+10h], rbx
0x1800acae3  mov     [rax+18h], rsi
0x1800acae7  mov     [rax+20h], r9
0x1800acaeb  push    rbp
0x1800acaec  push    rdi
0x1800acaed  push    r14
0x1800acaef  lea     rbp, [rax-7E8h]
0x1800acaf6  sub     rsp, 8D0h
0x1800acafd  movaps  xmmword ptr [rax-28h], xmm6
0x1800acb01  mov     rbx, r8
0x1800acb04  mov     r14d, edx
0x1800acb07  mov     rdi, rcx
0x1800acb0a  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800acb12  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800acb1a  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800acb1e  call    cs:__imp_QueryPerformanceCounter
0x1800acb24  mov     esi, [rdi+40h]
0x1800acb27  test    esi, esi
0x1800acb29  jns     short loc_1800ACB4D
0x1800acb2b  mov     rcx, [rbp+7E8h]; this
0x1800acb32  mov     r9d, esi; char *
0x1800acb35  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800acb3c  mov     edx, 4Fh ; 'O'; void *
0x1800acb41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800acb46  mov     eax, esi
0x1800acb48  jmp     loc_1800ACE06
0x1800acb4d  mov     ecx, 810h; cb
0x1800acb52  call    cs:__imp_CoTaskMemAlloc
0x1800acb58  mov     rsi, rax
0x1800acb5b  mov     [rsp+8E0h+var_878], rax
0x1800acb60  test    rax, rax
0x1800acb63  jnz     short loc_1800ACB88
0x1800acb65  mov     rcx, [rbp+7E8h]; this
0x1800acb6c  mov     ebx, 8007000Eh
0x1800acb71  mov     r9d, ebx; char *
0x1800acb74  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800acb7b  lea     edx, [rax+52h]; void *
0x1800acb7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800acb83  jmp     loc_1800ACE04
0x1800acb88  mov     [rbp+7E0h+Src], 0
0x1800acb90  mov     [rbp+7E0h+var_824], 0
0x1800acb97  xor     edx, edx; Val
0x1800acb99  mov     r8d, 800h; Size
0x1800acb9f  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800acba3  call    memset_0
0x1800acba8  mov     [rbp+7E0h+var_820], rbx
0x1800acbac  mov     [rbp+7E0h+var_828], 6
0x1800acbb3  mov     rcx, rsi; void *
0x1800acbb6  lea     rdx, [rbp+7E0h+Src]; Src
0x1800acbba  mov     r8d, 810h; Size
0x1800acbc0  call    memcpy_0
0x1800acbc5  mov     rax, [rsp+8E0h+var_878]
0x1800acbca  mov     [rax+0Ch], r14d
0x1800acbce  lea     rax, [rbp+7E0h+arg_18]
0x1800acbd5  mov     [rbp+7E0h+var_848], rax
0x1800acbd9  lea     rax, [rsp+8E0h+var_878]
0x1800acbde  mov     [rbp+7E0h+var_840], rax
0x1800acbe2  mov     [rbp+7E0h+var_838], 1
0x1800acbe6  mov     rcx, [rdi+28h]
0x1800acbea  mov     rax, [rcx]
0x1800acbed  mov     r9d, 810h
0x1800acbf3  mov     r8, [rsp+8E0h+var_878]
0x1800acbf8  mov     edx, r14d
0x1800acbfb  mov     rax, [rax+20h]
0x1800acbff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acc04  mov     ebx, eax
0x1800acc06  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800acc0a  call    cs:__imp_QueryPerformanceCounter
0x1800acc10  xorps   xmm6, xmm6
0x1800acc13  cmp     qword ptr [rdi+48h], 0
0x1800acc18  jz      short loc_1800ACC3C
0x1800acc1a  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800acc1e  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800acc22  cvtsi2ss xmm6, rcx
0x1800acc27  mulss   xmm6, cs:__real@447a0000
0x1800acc2f  xorps   xmm0, xmm0
0x1800acc32  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800acc38  divss   xmm6, xmm0
0x1800acc3c  mov     rcx, [rsp+8E0h+var_878]
0x1800acc41  cmp     dword ptr [rcx+8], 1
0x1800acc45  jnz     loc_1800ACD01
0x1800acc4b  mov     [rsp+8E0h+var_870], 0
0x1800acc54  lea     rdx, [rsp+8E0h+var_870]
0x1800acc59  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800acc5e  test    eax, eax
0x1800acc60  js      loc_1800ACD72
0x1800acc66  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800acc6b  mov     r8, rax
0x1800acc6e  mov     ecx, [rax]
0x1800acc70  cmp     ecx, 4
0x1800acc73  jbe     loc_1800ACD72
0x1800acc79  mov     [rbp+7E0h+arg_0], ebx
0x1800acc7f  movss   [rsp+8E0h+var_868], xmm6
0x1800acc85  mov     [rbp+7E0h+var_860], rdi
0x1800acc89  mov     rdx, [rsp+8E0h+var_870]
0x1800acc8e  mov     ecx, [rdx+10h]
0x1800acc91  mov     [rsp+8E0h+var_864], ecx
0x1800acc95  mov     ecx, [rdx+4]
0x1800acc98  mov     [rsp+8E0h+var_880], ecx
0x1800acc9c  mov     eax, [rdx+8]
0x1800acc9f  mov     [rsp+8E0h+var_880+4], eax
0x1800acca3  mov     eax, [rdx]
0x1800acca5  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800acca9  lea     rax, [rbp+7E0h+arg_0]
0x1800accb0  mov     [rsp+8E0h+var_890], rax
0x1800accb5  lea     rax, [rsp+8E0h+var_868]
0x1800accba  mov     [rsp+8E0h+var_898], rax
0x1800accbf  lea     rax, [rbp+7E0h+var_860]
0x1800accc3  mov     [rsp+8E0h+var_8A0], rax
0x1800accc8  lea     rax, [rsp+8E0h+var_864]
0x1800acccd  mov     [rsp+8E0h+var_8A8], rax
0x1800accd2  lea     rax, [rsp+8E0h+var_880]
0x1800accd7  mov     [rsp+8E0h+var_8B0], rax
0x1800accdc  lea     rax, [rsp+8E0h+var_880+4]
0x1800acce1  mov     [rsp+8E0h+var_8B8], rax
0x1800acce6  lea     rax, [rsp+8E0h+var_870]
0x1800acceb  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800accf0  lea     rdx, byte_1801663B7
0x1800accf7  mov     rcx, r8
0x1800accfa  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800accff  jmp     short loc_1800ACD72
0x1800acd01  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800acd06  mov     ecx, [rax]
0x1800acd08  cmp     ecx, 4
0x1800acd0b  jbe     short loc_1800ACD72
0x1800acd0d  mov     [rbp+7E0h+arg_0], ebx
0x1800acd13  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800acd19  mov     [rbp+7E0h+var_860], rdi
0x1800acd1d  mov     rcx, [rsp+8E0h+var_878]
0x1800acd22  mov     edx, [rcx+8]
0x1800acd25  mov     [rsp+8E0h+var_880+4], edx
0x1800acd29  mov     ecx, [rdi+30h]
0x1800acd2c  mov     [rsp+8E0h+var_880], ecx
0x1800acd30  lea     rcx, [rbp+7E0h+arg_0]
0x1800acd37  mov     [rsp+8E0h+var_8A0], rcx
0x1800acd3c  lea     rcx, [rsp+8E0h+var_870]
0x1800acd41  mov     [rsp+8E0h+var_8A8], rcx
0x1800acd46  lea     rcx, [rbp+7E0h+var_860]
0x1800acd4a  mov     [rsp+8E0h+var_8B0], rcx
0x1800acd4f  lea     rcx, [rsp+8E0h+var_880+4]
0x1800acd54  mov     [rsp+8E0h+var_8B8], rcx
0x1800acd59  lea     rcx, [rsp+8E0h+var_880]
0x1800acd5e  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800acd63  lea     rdx, dword_1801662A4
0x1800acd6a  mov     rcx, rax
0x1800acd6d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800acd72  mov     rcx, [rbp+7E8h]; this
0x1800acd79  test    ebx, ebx
0x1800acd7b  jns     short loc_1800ACDA0
0x1800acd7d  mov     r9d, ebx; char *
0x1800acd80  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800acd87  mov     edx, 81h; void *
0x1800acd8c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800acd91  mov     rax, [rdi]
0x1800acd94  mov     rcx, rdi
0x1800acd97  mov     rax, [rax+20h]
0x1800acd9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acda0  mov     ebx, [rdi+40h]
0x1800acda3  test    ebx, ebx
0x1800acda5  jns     short loc_1800ACDAE
0x1800acda7  mov     edx, 8Ah
0x1800acdac  jmp     short loc_1800ACDBF
0x1800acdae  mov     rcx, [rsp+8E0h+var_878]
0x1800acdb3  mov     ebx, [rcx+4]
0x1800acdb6  test    ebx, ebx
0x1800acdb8  jns     short loc_1800ACDD7
0x1800acdba  mov     edx, 8Ch; void *
0x1800acdbf  mov     r9d, ebx; char *
0x1800acdc2  mov     rcx, [rbp+7E8h]; this
0x1800acdc9  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800acdd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800acdd5  jmp     short loc_1800ACDF5
0x1800acdd7  mov     rdx, [rbp+7E0h+arg_20]
0x1800acdde  call    ??$CastTo@UXvmGetStreamLatency@@@XvmMessage@@QEAAJPEAPEAUXvmGetStreamLatency@@@Z; XvmMessage::CastTo<XvmGetStreamLatency>(XvmGetStreamLatency * *)
0x1800acde3  mov     ebx, eax
0x1800acde5  test    eax, eax
0x1800acde7  jns     short loc_1800ACDF3
0x1800acde9  mov     r9d, eax
0x1800acdec  mov     edx, 8Dh
0x1800acdf1  jmp     short loc_1800ACDC2
0x1800acdf3  xor     ebx, ebx
0x1800acdf5  mov     rcx, [rbp+7E0h+arg_18]
0x1800acdfc  mov     rax, [rsp+8E0h+var_878]
0x1800ace01  mov     [rcx], rax
0x1800ace04  mov     eax, ebx
0x1800ace06  lea     r11, [rsp+8E0h+var_10]
0x1800ace0e  mov     rbx, [r11+28h]
0x1800ace12  mov     rsi, [r11+30h]
0x1800ace16  movaps  xmm6, xmmword ptr [r11-10h]
0x1800ace1b  mov     rsp, r11
0x1800ace1e  pop     r14
0x1800ace20  pop     rdi
0x1800ace21  pop     rbp
0x1800ace22  retn
```
