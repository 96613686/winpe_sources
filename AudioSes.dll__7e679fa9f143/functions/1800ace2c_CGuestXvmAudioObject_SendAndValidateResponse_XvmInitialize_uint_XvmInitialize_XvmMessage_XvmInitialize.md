# CGuestXvmAudioObject::SendAndValidateResponse<XvmInitialize>(uint,XvmInitialize,XvmMessage * *,XvmInitialize * *)

- ea: `0x1800ace2c`
- end: `0x1800ad17e`
- name: `??$SendAndValidateResponse@UXvmInitialize@@@CGuestXvmAudioObject@@QEAAJIUXvmInitialize@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `850`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b0080`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2b78`
- `0x1800ace2c`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ace6d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800acf65`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ace6d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800acf65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800acea1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800acea1`

## string_xrefs

- `0x1800ace84`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800acec3`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ad0db`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ad124`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmInitialize>(__int64 a1, unsigned int a2, const void *a3, ...)
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
    memcpy_0(v34, a3, 0x534u);
    v32 = 4;
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
            (unsigned int)&unk_18016647D,
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
          (unsigned int)&unk_18016636A,
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
        v18 = XvmMessage::CastTo<XvmInitialize>(v21, v39, v12);
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
0x1800ace2c  mov     rax, rsp
0x1800ace2f  mov     [rax+10h], rbx
0x1800ace33  mov     [rax+18h], rsi
0x1800ace37  mov     [rax+20h], r9
0x1800ace3b  push    rbp
0x1800ace3c  push    rdi
0x1800ace3d  push    r14
0x1800ace3f  lea     rbp, [rax-7E8h]
0x1800ace46  sub     rsp, 8D0h
0x1800ace4d  movaps  xmmword ptr [rax-28h], xmm6
0x1800ace51  mov     r14, r8
0x1800ace54  mov     esi, edx
0x1800ace56  mov     rbx, rcx
0x1800ace59  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800ace61  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800ace69  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800ace6d  call    cs:__imp_QueryPerformanceCounter
0x1800ace73  mov     edi, [rbx+40h]
0x1800ace76  test    edi, edi
0x1800ace78  jns     short loc_1800ACE9C
0x1800ace7a  mov     rcx, [rbp+7E8h]; this
0x1800ace81  mov     r9d, edi; char *
0x1800ace84  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ace8b  mov     edx, 4Fh ; 'O'; void *
0x1800ace90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ace95  mov     eax, edi
0x1800ace97  jmp     loc_1800AD161
0x1800ace9c  mov     ecx, 810h; cb
0x1800acea1  call    cs:__imp_CoTaskMemAlloc
0x1800acea7  mov     rdi, rax
0x1800aceaa  mov     [rsp+8E0h+var_878], rax
0x1800aceaf  test    rax, rax
0x1800aceb2  jnz     short loc_1800ACED7
0x1800aceb4  mov     rcx, [rbp+7E8h]; this
0x1800acebb  mov     ebx, 8007000Eh
0x1800acec0  mov     r9d, ebx; char *
0x1800acec3  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800aceca  lea     edx, [rax+52h]; void *
0x1800acecd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aced2  jmp     loc_1800AD15F
0x1800aced7  mov     [rbp+7E0h+Src], 0
0x1800acedf  mov     [rbp+7E0h+var_824], 0
0x1800acee6  xor     edx, edx; Val
0x1800acee8  mov     r8d, 800h; Size
0x1800aceee  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800acef2  call    memset_0
0x1800acef7  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800acefb  mov     rdx, r14; Src
0x1800acefe  mov     r8d, 534h; Size
0x1800acf04  call    memcpy_0
0x1800acf09  mov     [rbp+7E0h+var_828], 4
0x1800acf10  mov     rcx, rdi; void *
0x1800acf13  lea     rdx, [rbp+7E0h+Src]; Src
0x1800acf17  mov     r8d, 810h; Size
0x1800acf1d  call    memcpy_0
0x1800acf22  mov     rax, [rsp+8E0h+var_878]
0x1800acf27  mov     [rax+0Ch], esi
0x1800acf2a  lea     rax, [rbp+7E0h+arg_18]
0x1800acf31  mov     [rbp+7E0h+var_848], rax
0x1800acf35  lea     rax, [rsp+8E0h+var_878]
0x1800acf3a  mov     [rbp+7E0h+var_840], rax
0x1800acf3e  mov     [rbp+7E0h+var_838], 1
0x1800acf42  mov     rcx, [rbx+28h]
0x1800acf46  mov     rax, [rcx]
0x1800acf49  mov     r9d, 810h
0x1800acf4f  mov     r8, [rsp+8E0h+var_878]
0x1800acf54  mov     edx, esi
0x1800acf56  mov     rax, [rax+20h]
0x1800acf5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acf5f  mov     edi, eax
0x1800acf61  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800acf65  call    cs:__imp_QueryPerformanceCounter
0x1800acf6b  xorps   xmm6, xmm6
0x1800acf6e  cmp     qword ptr [rbx+48h], 0
0x1800acf73  jz      short loc_1800ACF97
0x1800acf75  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800acf79  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800acf7d  cvtsi2ss xmm6, rcx
0x1800acf82  mulss   xmm6, cs:__real@447a0000
0x1800acf8a  xorps   xmm0, xmm0
0x1800acf8d  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800acf93  divss   xmm6, xmm0
0x1800acf97  mov     rcx, [rsp+8E0h+var_878]
0x1800acf9c  cmp     dword ptr [rcx+8], 1
0x1800acfa0  jnz     loc_1800AD05C
0x1800acfa6  mov     [rsp+8E0h+var_870], 0
0x1800acfaf  lea     rdx, [rsp+8E0h+var_870]
0x1800acfb4  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800acfb9  test    eax, eax
0x1800acfbb  js      loc_1800AD0CD
0x1800acfc1  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800acfc6  mov     r8, rax
0x1800acfc9  mov     ecx, [rax]
0x1800acfcb  cmp     ecx, 4
0x1800acfce  jbe     loc_1800AD0CD
0x1800acfd4  mov     [rbp+7E0h+arg_0], edi
0x1800acfda  movss   [rsp+8E0h+var_868], xmm6
0x1800acfe0  mov     [rbp+7E0h+var_860], rbx
0x1800acfe4  mov     rdx, [rsp+8E0h+var_870]
0x1800acfe9  mov     ecx, [rdx+10h]
0x1800acfec  mov     [rsp+8E0h+var_864], ecx
0x1800acff0  mov     ecx, [rdx+4]
0x1800acff3  mov     [rsp+8E0h+var_880], ecx
0x1800acff7  mov     eax, [rdx+8]
0x1800acffa  mov     [rsp+8E0h+var_880+4], eax
0x1800acffe  mov     eax, [rdx]
0x1800ad000  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800ad004  lea     rax, [rbp+7E0h+arg_0]
0x1800ad00b  mov     [rsp+8E0h+var_890], rax
0x1800ad010  lea     rax, [rsp+8E0h+var_868]
0x1800ad015  mov     [rsp+8E0h+var_898], rax
0x1800ad01a  lea     rax, [rbp+7E0h+var_860]
0x1800ad01e  mov     [rsp+8E0h+var_8A0], rax
0x1800ad023  lea     rax, [rsp+8E0h+var_864]
0x1800ad028  mov     [rsp+8E0h+var_8A8], rax
0x1800ad02d  lea     rax, [rsp+8E0h+var_880]
0x1800ad032  mov     [rsp+8E0h+var_8B0], rax
0x1800ad037  lea     rax, [rsp+8E0h+var_880+4]
0x1800ad03c  mov     [rsp+8E0h+var_8B8], rax
0x1800ad041  lea     rax, [rsp+8E0h+var_870]
0x1800ad046  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800ad04b  lea     rdx, unk_18016647D
0x1800ad052  mov     rcx, r8
0x1800ad055  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ad05a  jmp     short loc_1800AD0CD
0x1800ad05c  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ad061  mov     ecx, [rax]
0x1800ad063  cmp     ecx, 4
0x1800ad066  jbe     short loc_1800AD0CD
0x1800ad068  mov     [rbp+7E0h+arg_0], edi
0x1800ad06e  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800ad074  mov     [rbp+7E0h+var_860], rbx
0x1800ad078  mov     rcx, [rsp+8E0h+var_878]
0x1800ad07d  mov     edx, [rcx+8]
0x1800ad080  mov     [rsp+8E0h+var_880+4], edx
0x1800ad084  mov     ecx, [rbx+30h]
0x1800ad087  mov     [rsp+8E0h+var_880], ecx
0x1800ad08b  lea     rcx, [rbp+7E0h+arg_0]
0x1800ad092  mov     [rsp+8E0h+var_8A0], rcx
0x1800ad097  lea     rcx, [rsp+8E0h+var_870]
0x1800ad09c  mov     [rsp+8E0h+var_8A8], rcx
0x1800ad0a1  lea     rcx, [rbp+7E0h+var_860]
0x1800ad0a5  mov     [rsp+8E0h+var_8B0], rcx
0x1800ad0aa  lea     rcx, [rsp+8E0h+var_880+4]
0x1800ad0af  mov     [rsp+8E0h+var_8B8], rcx
0x1800ad0b4  lea     rcx, [rsp+8E0h+var_880]
0x1800ad0b9  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800ad0be  lea     rdx, unk_18016636A
0x1800ad0c5  mov     rcx, rax
0x1800ad0c8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ad0cd  mov     rcx, [rbp+7E8h]; this
0x1800ad0d4  test    edi, edi
0x1800ad0d6  jns     short loc_1800AD0FB
0x1800ad0d8  mov     r9d, edi; char *
0x1800ad0db  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ad0e2  mov     edx, 81h; void *
0x1800ad0e7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ad0ec  mov     rax, [rbx]
0x1800ad0ef  mov     rcx, rbx
0x1800ad0f2  mov     rax, [rax+20h]
0x1800ad0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad0fb  mov     ebx, [rbx+40h]
0x1800ad0fe  test    ebx, ebx
0x1800ad100  jns     short loc_1800AD109
0x1800ad102  mov     edx, 8Ah
0x1800ad107  jmp     short loc_1800AD11A
0x1800ad109  mov     rcx, [rsp+8E0h+var_878]
0x1800ad10e  mov     ebx, [rcx+4]
0x1800ad111  test    ebx, ebx
0x1800ad113  jns     short loc_1800AD132
0x1800ad115  mov     edx, 8Ch; void *
0x1800ad11a  mov     r9d, ebx; char *
0x1800ad11d  mov     rcx, [rbp+7E8h]; this
0x1800ad124  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ad12b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad130  jmp     short loc_1800AD150
0x1800ad132  mov     rdx, [rbp+7E0h+arg_20]
0x1800ad139  call    ??$CastTo@UXvmInitialize@@@XvmMessage@@QEAAJPEAPEAUXvmInitialize@@@Z; XvmMessage::CastTo<XvmInitialize>(XvmInitialize * *)
0x1800ad13e  mov     ebx, eax
0x1800ad140  test    eax, eax
0x1800ad142  jns     short loc_1800AD14E
0x1800ad144  mov     r9d, eax
0x1800ad147  mov     edx, 8Dh
0x1800ad14c  jmp     short loc_1800AD11D
0x1800ad14e  xor     ebx, ebx
0x1800ad150  mov     rcx, [rbp+7E0h+arg_18]
0x1800ad157  mov     rax, [rsp+8E0h+var_878]
0x1800ad15c  mov     [rcx], rax
0x1800ad15f  mov     eax, ebx
0x1800ad161  lea     r11, [rsp+8E0h+var_10]
0x1800ad169  mov     rbx, [r11+28h]
0x1800ad16d  mov     rsi, [r11+30h]
0x1800ad171  movaps  xmm6, xmmword ptr [r11-10h]
0x1800ad176  mov     rsp, r11
0x1800ad179  pop     r14
0x1800ad17b  pop     rdi
0x1800ad17c  pop     rbp
0x1800ad17d  retn
```
