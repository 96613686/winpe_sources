# CGuestXvmAudioObject::SendAndValidateResponse<XvmReset>(uint,XvmReset,XvmMessage * *,XvmReset * *)

- ea: `0x1800adbd0`
- end: `0x1800adf16`
- name: `??$SendAndValidateResponse@UXvmReset@@@CGuestXvmAudioObject@@QEAAJIUXvmReset@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b11f0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x18007a25c`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800adbd0`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800adc12`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800adcfd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800adc12`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800adcfd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800adc46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800adc46`

## string_xrefs

- `0x1800adc29`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800adc68`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ade73`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800adebc`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmReset>(__int64 a1, unsigned int a2, char a3, ...)
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
    v32 = 9;
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
            (unsigned int)byte_180166165,
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
          (unsigned int)word_180166052,
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
        v18 = XvmMessage::CastTo<XvmReset>(v21, v39, v12);
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
0x1800adbd0  mov     rax, rsp
0x1800adbd3  mov     [rax+10h], rbx
0x1800adbd7  mov     [rax+18h], rsi
0x1800adbdb  mov     [rax+20h], r9
0x1800adbdf  push    rbp
0x1800adbe0  push    rdi
0x1800adbe1  push    r14
0x1800adbe3  lea     rbp, [rax-7E8h]
0x1800adbea  sub     rsp, 8D0h
0x1800adbf1  movaps  xmmword ptr [rax-28h], xmm6
0x1800adbf5  mov     bl, r8b
0x1800adbf8  mov     r14d, edx
0x1800adbfb  mov     rdi, rcx
0x1800adbfe  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800adc06  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800adc0e  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800adc12  call    cs:__imp_QueryPerformanceCounter
0x1800adc18  mov     esi, [rdi+40h]
0x1800adc1b  test    esi, esi
0x1800adc1d  jns     short loc_1800ADC41
0x1800adc1f  mov     rcx, [rbp+7E8h]; this
0x1800adc26  mov     r9d, esi; char *
0x1800adc29  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800adc30  mov     edx, 4Fh ; 'O'; void *
0x1800adc35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adc3a  mov     eax, esi
0x1800adc3c  jmp     loc_1800ADEF9
0x1800adc41  mov     ecx, 810h; cb
0x1800adc46  call    cs:__imp_CoTaskMemAlloc
0x1800adc4c  mov     rsi, rax
0x1800adc4f  mov     [rsp+8E0h+var_878], rax
0x1800adc54  test    rax, rax
0x1800adc57  jnz     short loc_1800ADC7C
0x1800adc59  mov     rcx, [rbp+7E8h]; this
0x1800adc60  mov     ebx, 8007000Eh
0x1800adc65  mov     r9d, ebx; char *
0x1800adc68  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800adc6f  lea     edx, [rax+52h]; void *
0x1800adc72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adc77  jmp     loc_1800ADEF7
0x1800adc7c  mov     [rbp+7E0h+Src], 0
0x1800adc84  mov     [rbp+7E0h+var_824], 0
0x1800adc8b  xor     edx, edx; Val
0x1800adc8d  mov     r8d, 800h; Size
0x1800adc93  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800adc97  call    memset_0
0x1800adc9c  mov     [rbp+7E0h+var_820], bl
0x1800adc9f  mov     [rbp+7E0h+var_828], 9
0x1800adca6  mov     rcx, rsi; void *
0x1800adca9  lea     rdx, [rbp+7E0h+Src]; Src
0x1800adcad  mov     r8d, 810h; Size
0x1800adcb3  call    memcpy_0
0x1800adcb8  mov     rax, [rsp+8E0h+var_878]
0x1800adcbd  mov     [rax+0Ch], r14d
0x1800adcc1  lea     rax, [rbp+7E0h+arg_18]
0x1800adcc8  mov     [rbp+7E0h+var_848], rax
0x1800adccc  lea     rax, [rsp+8E0h+var_878]
0x1800adcd1  mov     [rbp+7E0h+var_840], rax
0x1800adcd5  mov     [rbp+7E0h+var_838], 1
0x1800adcd9  mov     rcx, [rdi+28h]
0x1800adcdd  mov     rax, [rcx]
0x1800adce0  mov     r9d, 810h
0x1800adce6  mov     r8, [rsp+8E0h+var_878]
0x1800adceb  mov     edx, r14d
0x1800adcee  mov     rax, [rax+20h]
0x1800adcf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adcf7  mov     ebx, eax
0x1800adcf9  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800adcfd  call    cs:__imp_QueryPerformanceCounter
0x1800add03  xorps   xmm6, xmm6
0x1800add06  cmp     qword ptr [rdi+48h], 0
0x1800add0b  jz      short loc_1800ADD2F
0x1800add0d  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800add11  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800add15  cvtsi2ss xmm6, rcx
0x1800add1a  mulss   xmm6, cs:__real@447a0000
0x1800add22  xorps   xmm0, xmm0
0x1800add25  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800add2b  divss   xmm6, xmm0
0x1800add2f  mov     rcx, [rsp+8E0h+var_878]
0x1800add34  cmp     dword ptr [rcx+8], 1
0x1800add38  jnz     loc_1800ADDF4
0x1800add3e  mov     [rsp+8E0h+var_870], 0
0x1800add47  lea     rdx, [rsp+8E0h+var_870]
0x1800add4c  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800add51  test    eax, eax
0x1800add53  js      loc_1800ADE65
0x1800add59  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800add5e  mov     r8, rax
0x1800add61  mov     ecx, [rax]
0x1800add63  cmp     ecx, 4
0x1800add66  jbe     loc_1800ADE65
0x1800add6c  mov     [rbp+7E0h+arg_0], ebx
0x1800add72  movss   [rsp+8E0h+var_868], xmm6
0x1800add78  mov     [rbp+7E0h+var_860], rdi
0x1800add7c  mov     rdx, [rsp+8E0h+var_870]
0x1800add81  mov     ecx, [rdx+10h]
0x1800add84  mov     [rsp+8E0h+var_864], ecx
0x1800add88  mov     ecx, [rdx+4]
0x1800add8b  mov     [rsp+8E0h+var_880], ecx
0x1800add8f  mov     eax, [rdx+8]
0x1800add92  mov     [rsp+8E0h+var_880+4], eax
0x1800add96  mov     eax, [rdx]
0x1800add98  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800add9c  lea     rax, [rbp+7E0h+arg_0]
0x1800adda3  mov     [rsp+8E0h+var_890], rax
0x1800adda8  lea     rax, [rsp+8E0h+var_868]
0x1800addad  mov     [rsp+8E0h+var_898], rax
0x1800addb2  lea     rax, [rbp+7E0h+var_860]
0x1800addb6  mov     [rsp+8E0h+var_8A0], rax
0x1800addbb  lea     rax, [rsp+8E0h+var_864]
0x1800addc0  mov     [rsp+8E0h+var_8A8], rax
0x1800addc5  lea     rax, [rsp+8E0h+var_880]
0x1800addca  mov     [rsp+8E0h+var_8B0], rax
0x1800addcf  lea     rax, [rsp+8E0h+var_880+4]
0x1800addd4  mov     [rsp+8E0h+var_8B8], rax
0x1800addd9  lea     rax, [rsp+8E0h+var_870]
0x1800addde  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800adde3  lea     rdx, byte_180166165
0x1800addea  mov     rcx, r8
0x1800added  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800addf2  jmp     short loc_1800ADE65
0x1800addf4  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800addf9  mov     ecx, [rax]
0x1800addfb  cmp     ecx, 4
0x1800addfe  jbe     short loc_1800ADE65
0x1800ade00  mov     [rbp+7E0h+arg_0], ebx
0x1800ade06  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800ade0c  mov     [rbp+7E0h+var_860], rdi
0x1800ade10  mov     rcx, [rsp+8E0h+var_878]
0x1800ade15  mov     edx, [rcx+8]
0x1800ade18  mov     [rsp+8E0h+var_880+4], edx
0x1800ade1c  mov     ecx, [rdi+30h]
0x1800ade1f  mov     [rsp+8E0h+var_880], ecx
0x1800ade23  lea     rcx, [rbp+7E0h+arg_0]
0x1800ade2a  mov     [rsp+8E0h+var_8A0], rcx
0x1800ade2f  lea     rcx, [rsp+8E0h+var_870]
0x1800ade34  mov     [rsp+8E0h+var_8A8], rcx
0x1800ade39  lea     rcx, [rbp+7E0h+var_860]
0x1800ade3d  mov     [rsp+8E0h+var_8B0], rcx
0x1800ade42  lea     rcx, [rsp+8E0h+var_880+4]
0x1800ade47  mov     [rsp+8E0h+var_8B8], rcx
0x1800ade4c  lea     rcx, [rsp+8E0h+var_880]
0x1800ade51  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800ade56  lea     rdx, word_180166052
0x1800ade5d  mov     rcx, rax
0x1800ade60  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ade65  mov     rcx, [rbp+7E8h]; this
0x1800ade6c  test    ebx, ebx
0x1800ade6e  jns     short loc_1800ADE93
0x1800ade70  mov     r9d, ebx; char *
0x1800ade73  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ade7a  mov     edx, 81h; void *
0x1800ade7f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ade84  mov     rax, [rdi]
0x1800ade87  mov     rcx, rdi
0x1800ade8a  mov     rax, [rax+20h]
0x1800ade8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ade93  mov     ebx, [rdi+40h]
0x1800ade96  test    ebx, ebx
0x1800ade98  jns     short loc_1800ADEA1
0x1800ade9a  mov     edx, 8Ah
0x1800ade9f  jmp     short loc_1800ADEB2
0x1800adea1  mov     rcx, [rsp+8E0h+var_878]
0x1800adea6  mov     ebx, [rcx+4]
0x1800adea9  test    ebx, ebx
0x1800adeab  jns     short loc_1800ADECA
0x1800adead  mov     edx, 8Ch; void *
0x1800adeb2  mov     r9d, ebx; char *
0x1800adeb5  mov     rcx, [rbp+7E8h]; this
0x1800adebc  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800adec3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adec8  jmp     short loc_1800ADEE8
0x1800adeca  mov     rdx, [rbp+7E0h+arg_20]
0x1800aded1  call    ??$CastTo@UXvmReset@@@XvmMessage@@QEAAJPEAPEAUXvmReset@@@Z; XvmMessage::CastTo<XvmReset>(XvmReset * *)
0x1800aded6  mov     ebx, eax
0x1800aded8  test    eax, eax
0x1800adeda  jns     short loc_1800ADEE6
0x1800adedc  mov     r9d, eax
0x1800adedf  mov     edx, 8Dh
0x1800adee4  jmp     short loc_1800ADEB5
0x1800adee6  xor     ebx, ebx
0x1800adee8  mov     rcx, [rbp+7E0h+arg_18]
0x1800adeef  mov     rax, [rsp+8E0h+var_878]
0x1800adef4  mov     [rcx], rax
0x1800adef7  mov     eax, ebx
0x1800adef9  lea     r11, [rsp+8E0h+var_10]
0x1800adf01  mov     rbx, [r11+28h]
0x1800adf05  mov     rsi, [r11+30h]
0x1800adf09  movaps  xmm6, xmmword ptr [r11-10h]
0x1800adf0e  mov     rsp, r11
0x1800adf11  pop     r14
0x1800adf13  pop     rdi
0x1800adf14  pop     rbp
0x1800adf15  retn
```
