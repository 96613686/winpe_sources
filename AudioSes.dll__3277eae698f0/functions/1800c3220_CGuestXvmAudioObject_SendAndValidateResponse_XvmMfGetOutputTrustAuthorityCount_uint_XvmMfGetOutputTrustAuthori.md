# CGuestXvmAudioObject::SendAndValidateResponse<XvmMfGetOutputTrustAuthorityCount>(uint,XvmMfGetOutputTrustAuthorityCount,XvmMessage * *,XvmMfGetOutputTrustAuthorityCount * *)

- ea: `0x1800c3220`
- end: `0x1800c3566`
- name: `??$SendAndValidateResponse@UXvmMfGetOutputTrustAuthorityCount@@@CGuestXvmAudioObject@@QEAAJIUXvmMfGetOutputTrustAuthorityCount@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c3bc0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800c29cc`
- `0x1800c3220`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c3262`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c334d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c3262`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c334d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c3296`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c3296`

## string_xrefs

- `0x1800c3279`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800c32b8`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800c34c3`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800c350c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmMfGetOutputTrustAuthorityCount>(
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
  int OutputTrustAuthority; // eax
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
    v32 = 61;
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
            (unsigned int)&dword_180168D14,
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
          (unsigned int)byte_180168D8D,
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
        OutputTrustAuthority = XvmMessage::CastTo<XvmMfGetOutputTrustAuthorityCount>(v21, v39, v12);
        v9 = OutputTrustAuthority;
        if ( OutputTrustAuthority >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)OutputTrustAuthority;
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
0x1800c3220  mov     rax, rsp
0x1800c3223  mov     [rax+10h], rbx
0x1800c3227  mov     [rax+18h], rsi
0x1800c322b  mov     [rax+20h], r9
0x1800c322f  push    rbp
0x1800c3230  push    rdi
0x1800c3231  push    r14
0x1800c3233  lea     rbp, [rax-7E8h]
0x1800c323a  sub     rsp, 8D0h
0x1800c3241  movaps  xmmword ptr [rax-28h], xmm6
0x1800c3245  mov     ebx, r8d
0x1800c3248  mov     r14d, edx
0x1800c324b  mov     rdi, rcx
0x1800c324e  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800c3256  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800c325e  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800c3262  call    cs:__imp_QueryPerformanceCounter
0x1800c3268  mov     esi, [rdi+40h]
0x1800c326b  test    esi, esi
0x1800c326d  jns     short loc_1800C3291
0x1800c326f  mov     rcx, [rbp+7E8h]; this
0x1800c3276  mov     r9d, esi; char *
0x1800c3279  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c3280  mov     edx, 4Fh ; 'O'; void *
0x1800c3285  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c328a  mov     eax, esi
0x1800c328c  jmp     loc_1800C3549
0x1800c3291  mov     ecx, 810h; cb
0x1800c3296  call    cs:__imp_CoTaskMemAlloc
0x1800c329c  mov     rsi, rax
0x1800c329f  mov     [rsp+8E0h+var_878], rax
0x1800c32a4  test    rax, rax
0x1800c32a7  jnz     short loc_1800C32CC
0x1800c32a9  mov     rcx, [rbp+7E8h]; this
0x1800c32b0  mov     ebx, 8007000Eh
0x1800c32b5  mov     r9d, ebx; char *
0x1800c32b8  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c32bf  lea     edx, [rax+52h]; void *
0x1800c32c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c32c7  jmp     loc_1800C3547
0x1800c32cc  mov     [rbp+7E0h+Src], 0
0x1800c32d4  mov     [rbp+7E0h+var_824], 0
0x1800c32db  xor     edx, edx; Val
0x1800c32dd  mov     r8d, 800h; Size
0x1800c32e3  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800c32e7  call    memset_0
0x1800c32ec  mov     [rbp+7E0h+var_820], ebx
0x1800c32ef  mov     [rbp+7E0h+var_828], 3Dh ; '='
0x1800c32f6  mov     rcx, rsi; void *
0x1800c32f9  lea     rdx, [rbp+7E0h+Src]; Src
0x1800c32fd  mov     r8d, 810h; Size
0x1800c3303  call    memcpy_0
0x1800c3308  mov     rax, [rsp+8E0h+var_878]
0x1800c330d  mov     [rax+0Ch], r14d
0x1800c3311  lea     rax, [rbp+7E0h+arg_18]
0x1800c3318  mov     [rbp+7E0h+var_848], rax
0x1800c331c  lea     rax, [rsp+8E0h+var_878]
0x1800c3321  mov     [rbp+7E0h+var_840], rax
0x1800c3325  mov     [rbp+7E0h+var_838], 1
0x1800c3329  mov     rcx, [rdi+28h]
0x1800c332d  mov     rax, [rcx]
0x1800c3330  mov     r9d, 810h
0x1800c3336  mov     r8, [rsp+8E0h+var_878]
0x1800c333b  mov     edx, r14d
0x1800c333e  mov     rax, [rax+20h]
0x1800c3342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3347  mov     ebx, eax
0x1800c3349  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800c334d  call    cs:__imp_QueryPerformanceCounter
0x1800c3353  xorps   xmm6, xmm6
0x1800c3356  cmp     qword ptr [rdi+48h], 0
0x1800c335b  jz      short loc_1800C337F
0x1800c335d  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800c3361  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800c3365  cvtsi2ss xmm6, rcx
0x1800c336a  mulss   xmm6, cs:__real@447a0000
0x1800c3372  xorps   xmm0, xmm0
0x1800c3375  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800c337b  divss   xmm6, xmm0
0x1800c337f  mov     rcx, [rsp+8E0h+var_878]
0x1800c3384  cmp     dword ptr [rcx+8], 1
0x1800c3388  jnz     loc_1800C3444
0x1800c338e  mov     [rsp+8E0h+var_870], 0
0x1800c3397  lea     rdx, [rsp+8E0h+var_870]
0x1800c339c  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800c33a1  test    eax, eax
0x1800c33a3  js      loc_1800C34B5
0x1800c33a9  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800c33ae  mov     r8, rax
0x1800c33b1  mov     ecx, [rax]
0x1800c33b3  cmp     ecx, 4
0x1800c33b6  jbe     loc_1800C34B5
0x1800c33bc  mov     [rbp+7E0h+arg_0], ebx
0x1800c33c2  movss   [rsp+8E0h+var_868], xmm6
0x1800c33c8  mov     [rbp+7E0h+var_860], rdi
0x1800c33cc  mov     rdx, [rsp+8E0h+var_870]
0x1800c33d1  mov     ecx, [rdx+10h]
0x1800c33d4  mov     [rsp+8E0h+var_864], ecx
0x1800c33d8  mov     ecx, [rdx+4]
0x1800c33db  mov     [rsp+8E0h+var_880], ecx
0x1800c33df  mov     eax, [rdx+8]
0x1800c33e2  mov     [rsp+8E0h+var_880+4], eax
0x1800c33e6  mov     eax, [rdx]
0x1800c33e8  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800c33ec  lea     rax, [rbp+7E0h+arg_0]
0x1800c33f3  mov     [rsp+8E0h+var_890], rax
0x1800c33f8  lea     rax, [rsp+8E0h+var_868]
0x1800c33fd  mov     [rsp+8E0h+var_898], rax
0x1800c3402  lea     rax, [rbp+7E0h+var_860]
0x1800c3406  mov     [rsp+8E0h+var_8A0], rax
0x1800c340b  lea     rax, [rsp+8E0h+var_864]
0x1800c3410  mov     [rsp+8E0h+var_8A8], rax
0x1800c3415  lea     rax, [rsp+8E0h+var_880]
0x1800c341a  mov     [rsp+8E0h+var_8B0], rax
0x1800c341f  lea     rax, [rsp+8E0h+var_880+4]
0x1800c3424  mov     [rsp+8E0h+var_8B8], rax
0x1800c3429  lea     rax, [rsp+8E0h+var_870]
0x1800c342e  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800c3433  lea     rdx, dword_180168D14
0x1800c343a  mov     rcx, r8
0x1800c343d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c3442  jmp     short loc_1800C34B5
0x1800c3444  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800c3449  mov     ecx, [rax]
0x1800c344b  cmp     ecx, 4
0x1800c344e  jbe     short loc_1800C34B5
0x1800c3450  mov     [rbp+7E0h+arg_0], ebx
0x1800c3456  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800c345c  mov     [rbp+7E0h+var_860], rdi
0x1800c3460  mov     rcx, [rsp+8E0h+var_878]
0x1800c3465  mov     edx, [rcx+8]
0x1800c3468  mov     [rsp+8E0h+var_880+4], edx
0x1800c346c  mov     ecx, [rdi+30h]
0x1800c346f  mov     [rsp+8E0h+var_880], ecx
0x1800c3473  lea     rcx, [rbp+7E0h+arg_0]
0x1800c347a  mov     [rsp+8E0h+var_8A0], rcx
0x1800c347f  lea     rcx, [rsp+8E0h+var_870]
0x1800c3484  mov     [rsp+8E0h+var_8A8], rcx
0x1800c3489  lea     rcx, [rbp+7E0h+var_860]
0x1800c348d  mov     [rsp+8E0h+var_8B0], rcx
0x1800c3492  lea     rcx, [rsp+8E0h+var_880+4]
0x1800c3497  mov     [rsp+8E0h+var_8B8], rcx
0x1800c349c  lea     rcx, [rsp+8E0h+var_880]
0x1800c34a1  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800c34a6  lea     rdx, byte_180168D8D
0x1800c34ad  mov     rcx, rax
0x1800c34b0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c34b5  mov     rcx, [rbp+7E8h]; this
0x1800c34bc  test    ebx, ebx
0x1800c34be  jns     short loc_1800C34E3
0x1800c34c0  mov     r9d, ebx; char *
0x1800c34c3  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c34ca  mov     edx, 81h; void *
0x1800c34cf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c34d4  mov     rax, [rdi]
0x1800c34d7  mov     rcx, rdi
0x1800c34da  mov     rax, [rax+20h]
0x1800c34de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c34e3  mov     ebx, [rdi+40h]
0x1800c34e6  test    ebx, ebx
0x1800c34e8  jns     short loc_1800C34F1
0x1800c34ea  mov     edx, 8Ah
0x1800c34ef  jmp     short loc_1800C3502
0x1800c34f1  mov     rcx, [rsp+8E0h+var_878]
0x1800c34f6  mov     ebx, [rcx+4]
0x1800c34f9  test    ebx, ebx
0x1800c34fb  jns     short loc_1800C351A
0x1800c34fd  mov     edx, 8Ch; void *
0x1800c3502  mov     r9d, ebx; char *
0x1800c3505  mov     rcx, [rbp+7E8h]; this
0x1800c350c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c3513  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c3518  jmp     short loc_1800C3538
0x1800c351a  mov     rdx, [rbp+7E0h+arg_20]
0x1800c3521  call    ??$CastTo@UXvmMfGetOutputTrustAuthorityCount@@@XvmMessage@@QEAAJPEAPEAUXvmMfGetOutputTrustAuthorityCount@@@Z; XvmMessage::CastTo<XvmMfGetOutputTrustAuthorityCount>(XvmMfGetOutputTrustAuthorityCount * *)
0x1800c3526  mov     ebx, eax
0x1800c3528  test    eax, eax
0x1800c352a  jns     short loc_1800C3536
0x1800c352c  mov     r9d, eax
0x1800c352f  mov     edx, 8Dh
0x1800c3534  jmp     short loc_1800C3505
0x1800c3536  xor     ebx, ebx
0x1800c3538  mov     rcx, [rbp+7E0h+arg_18]
0x1800c353f  mov     rax, [rsp+8E0h+var_878]
0x1800c3544  mov     [rcx], rax
0x1800c3547  mov     eax, ebx
0x1800c3549  lea     r11, [rsp+8E0h+var_10]
0x1800c3551  mov     rbx, [r11+28h]
0x1800c3555  mov     rsi, [r11+30h]
0x1800c3559  movaps  xmm6, xmmword ptr [r11-10h]
0x1800c355e  mov     rsp, r11
0x1800c3561  pop     r14
0x1800c3563  pop     rdi
0x1800c3564  pop     rbp
0x1800c3565  retn
```
