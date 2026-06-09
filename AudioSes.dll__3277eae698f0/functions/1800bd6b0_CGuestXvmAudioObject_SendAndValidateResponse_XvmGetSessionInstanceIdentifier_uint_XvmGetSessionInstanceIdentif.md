# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetSessionInstanceIdentifier>(uint,XvmGetSessionInstanceIdentifier,XvmMessage * *,XvmGetSessionInstanceIdentifier * *)

- ea: `0x1800bd6b0`
- end: `0x1800bda49`
- name: `??$SendAndValidateResponse@UXvmGetSessionInstanceIdentifier@@@CGuestXvmAudioObject@@QEAAJIUXvmGetSessionInstanceIdentifier@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `921`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c0ef0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800b94b4`
- `0x1800bd6b0`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd6f2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd830`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd6f2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd830`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bd726`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bd726`

## string_xrefs

- `0x1800bd709`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bd748`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bd9a6`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bd9ef`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetSessionInstanceIdentifier>(
        __int64 a1,
        unsigned int a2,
        _OWORD *a3,
        ...)
{
  int v6; // esi
  _DWORD *v8; // rsi
  int v9; // ebx
  _OWORD *v10; // rax
  __int64 v11; // rcx
  int v12; // ebx
  float v13; // xmm6_4
  const struct _tlgProvider_t *v14; // r8
  int v15; // r9d
  const struct _tlgProvider_t *v16; // rax
  int v17; // r9d
  __int64 v18; // rdx
  unsigned __int64 v19; // r9
  int SessionInstance; // eax
  int v21; // [rsp+28h] [rbp-E0h]
  int v22[2]; // [rsp+68h] [rbp-A0h] BYREF
  _DWORD *v23; // [rsp+70h] [rbp-98h] BYREF
  _DWORD *v24; // [rsp+78h] [rbp-90h] BYREF
  float v25; // [rsp+80h] [rbp-88h] BYREF
  int v26; // [rsp+84h] [rbp-84h] BYREF
  __int64 v27; // [rsp+88h] [rbp-80h] BYREF
  LARGE_INTEGER v28; // [rsp+90h] [rbp-78h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+98h] [rbp-70h] BYREF
  va_list v30; // [rsp+A0h] [rbp-68h]
  _DWORD **v31; // [rsp+A8h] [rbp-60h]
  char v32; // [rsp+B0h] [rbp-58h]
  __int64 Src; // [rsp+B8h] [rbp-50h] BYREF
  int v34; // [rsp+C0h] [rbp-48h]
  int v35; // [rsp+C4h] [rbp-44h]
  _BYTE v36[2064]; // [rsp+C8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8F0h] [rbp+7E8h]
  int v38; // [rsp+8F8h] [rbp+7F0h] BYREF
  _QWORD *v39; // [rsp+910h] [rbp+808h] BYREF
  va_list va; // [rsp+910h] [rbp+808h]
  __int64 v41; // [rsp+918h] [rbp+810h]
  va_list va1; // [rsp+920h] [rbp+818h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v39 = va_arg(va1, _QWORD *);
  v41 = va_arg(va1, _QWORD);
  PerformanceCount.QuadPart = 0;
  v28.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v6 = *(_DWORD *)(a1 + 64);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
      (const char *)(unsigned int)v6,
      v21);
    return (unsigned int)v6;
  }
  v8 = CoTaskMemAlloc(0x810u);
  v23 = v8;
  if ( v8 )
  {
    Src = 0;
    v35 = 0;
    memset_0(v36, 0, 0x800u);
    v10 = v36;
    v11 = 8;
    do
    {
      *v10 = *a3;
      v10[1] = a3[1];
      v10[2] = a3[2];
      v10[3] = a3[3];
      v10[4] = a3[4];
      v10[5] = a3[5];
      v10[6] = a3[6];
      v10[7] = a3[7];
      v10 += 8;
      a3 += 8;
      --v11;
    }
    while ( v11 );
    v34 = 125;
    memcpy_0(v8, &Src, 0x810u);
    v23[3] = a2;
    va_copy(v30, va);
    v31 = &v23;
    v32 = 1;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _DWORD *, __int64))(**(_QWORD **)(a1 + 40) + 32LL))(
            *(_QWORD *)(a1 + 40),
            a2,
            v23,
            2064);
    QueryPerformanceCounter(&v28);
    v13 = 0.0;
    if ( *(_QWORD *)(a1 + 72) )
      v13 = (float)((float)(v28.LowPart - PerformanceCount.LowPart) * 1000.0) / (float)(int)*(_QWORD *)(a1 + 72);
    if ( v23[2] == 1 )
    {
      v24 = 0;
      if ( (int)XvmMessage::CastTo<XvmActivateProxyAudioObject>(v23, &v24) >= 0 )
      {
        v14 = GuestXvmAudioObjectTelemetryProvider::Provider();
        if ( *(_DWORD *)v14 > 4u )
        {
          v38 = v12;
          v25 = v13;
          v27 = a1;
          v26 = v24[4];
          v22[0] = v24[1];
          v22[1] = v24[2];
          LODWORD(v24) = *v24;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v14,
            (unsigned int)&word_1801679BE,
            (_DWORD)v14,
            v15,
            (__int64)&v24,
            (__int64)&v22[1],
            (__int64)v22,
            (__int64)&v26,
            (__int64)&v27,
            (__int64)&v25,
            (__int64)&v38);
        }
      }
    }
    else
    {
      v16 = GuestXvmAudioObjectTelemetryProvider::Provider();
      if ( *(_DWORD *)v16 > 4u )
      {
        v38 = v12;
        *(float *)&v24 = v13;
        v27 = a1;
        v22[1] = v23[2];
        v22[0] = *(_DWORD *)(a1 + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v16,
          (unsigned int)&byte_180167A37,
          (_DWORD)v14,
          v17,
          (__int64)v22,
          (__int64)&v22[1],
          (__int64)&v27,
          (__int64)&v24,
          (__int64)&v38);
      }
    }
    if ( v12 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
        (const char *)(unsigned int)v12,
        v21);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    }
    v9 = *(_DWORD *)(a1 + 64);
    if ( v9 >= 0 )
    {
      v9 = v23[1];
      if ( v9 >= 0 )
      {
        SessionInstance = XvmMessage::CastTo<XvmGetSessionInstanceIdentifier>(v23, v41, v14);
        v9 = SessionInstance;
        if ( SessionInstance >= 0 )
        {
          v9 = 0;
          goto LABEL_26;
        }
        v19 = (unsigned int)SessionInstance;
        v18 = 141;
LABEL_22:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
          (const char *)v19,
          v21);
LABEL_26:
        *v39 = v23;
        return (unsigned int)v9;
      }
      v18 = 140;
    }
    else
    {
      v18 = 138;
    }
    v19 = (unsigned int)v9;
    goto LABEL_22;
  }
  v9 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x52,
    (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
    (const char *)0x8007000ELL,
    v21);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800bd6b0  mov     rax, rsp
0x1800bd6b3  mov     [rax+10h], rbx
0x1800bd6b7  mov     [rax+18h], rsi
0x1800bd6bb  mov     [rax+20h], r9
0x1800bd6bf  push    rbp
0x1800bd6c0  push    rdi
0x1800bd6c1  push    r14
0x1800bd6c3  lea     rbp, [rax-7E8h]
0x1800bd6ca  sub     rsp, 8D0h
0x1800bd6d1  movaps  xmmword ptr [rax-28h], xmm6
0x1800bd6d5  mov     rbx, r8
0x1800bd6d8  mov     r14d, edx
0x1800bd6db  mov     rdi, rcx
0x1800bd6de  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bd6e6  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800bd6ee  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800bd6f2  call    cs:__imp_QueryPerformanceCounter
0x1800bd6f8  mov     esi, [rdi+40h]
0x1800bd6fb  test    esi, esi
0x1800bd6fd  jns     short loc_1800BD721
0x1800bd6ff  mov     rcx, [rbp+7E8h]; this
0x1800bd706  mov     r9d, esi; char *
0x1800bd709  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bd710  mov     edx, 4Fh ; 'O'; void *
0x1800bd715  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd71a  mov     eax, esi
0x1800bd71c  jmp     loc_1800BDA2C
0x1800bd721  mov     ecx, 810h; cb
0x1800bd726  call    cs:__imp_CoTaskMemAlloc
0x1800bd72c  mov     rsi, rax
0x1800bd72f  mov     [rsp+8E0h+var_878], rax
0x1800bd734  test    rax, rax
0x1800bd737  jnz     short loc_1800BD75C
0x1800bd739  mov     rcx, [rbp+7E8h]; this
0x1800bd740  mov     ebx, 8007000Eh
0x1800bd745  mov     r9d, ebx; char *
0x1800bd748  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bd74f  lea     edx, [rax+52h]; void *
0x1800bd752  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd757  jmp     loc_1800BDA2A
0x1800bd75c  mov     [rbp+7E0h+Src], 0
0x1800bd764  mov     [rbp+7E0h+var_824], 0
0x1800bd76b  xor     edx, edx; Val
0x1800bd76d  mov     r8d, 800h; Size
0x1800bd773  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bd777  call    memset_0
0x1800bd77c  lea     rax, [rbp+7E0h+var_820]
0x1800bd780  mov     ecx, 8
0x1800bd785  lea     edx, [rcx+78h]
0x1800bd788  movups  xmm0, xmmword ptr [rbx]
0x1800bd78b  movups  xmmword ptr [rax], xmm0
0x1800bd78e  movups  xmm1, xmmword ptr [rbx+10h]
0x1800bd792  movups  xmmword ptr [rax+10h], xmm1
0x1800bd796  movups  xmm0, xmmword ptr [rbx+20h]
0x1800bd79a  movups  xmmword ptr [rax+20h], xmm0
0x1800bd79e  movups  xmm1, xmmword ptr [rbx+30h]
0x1800bd7a2  movups  xmmword ptr [rax+30h], xmm1
0x1800bd7a6  movups  xmm0, xmmword ptr [rbx+40h]
0x1800bd7aa  movups  xmmword ptr [rax+40h], xmm0
0x1800bd7ae  movups  xmm1, xmmword ptr [rbx+50h]
0x1800bd7b2  movups  xmmword ptr [rax+50h], xmm1
0x1800bd7b6  movups  xmm0, xmmword ptr [rbx+60h]
0x1800bd7ba  movups  xmmword ptr [rax+60h], xmm0
0x1800bd7be  movups  xmm1, xmmword ptr [rbx+70h]
0x1800bd7c2  movups  xmmword ptr [rax+70h], xmm1
0x1800bd7c6  add     rax, rdx
0x1800bd7c9  add     rbx, rdx
0x1800bd7cc  sub     rcx, 1
0x1800bd7d0  jnz     short loc_1800BD788
0x1800bd7d2  mov     [rbp+7E0h+var_828], 7Dh ; '}'
0x1800bd7d9  mov     rcx, rsi; void *
0x1800bd7dc  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bd7e0  mov     r8d, 810h; Size
0x1800bd7e6  call    memcpy_0
0x1800bd7eb  mov     rax, [rsp+8E0h+var_878]
0x1800bd7f0  mov     [rax+0Ch], r14d
0x1800bd7f4  lea     rax, [rbp+7E0h+arg_18]
0x1800bd7fb  mov     [rbp+7E0h+var_848], rax
0x1800bd7ff  lea     rax, [rsp+8E0h+var_878]
0x1800bd804  mov     [rbp+7E0h+var_840], rax
0x1800bd808  mov     [rbp+7E0h+var_838], 1
0x1800bd80c  mov     rcx, [rdi+28h]
0x1800bd810  mov     rax, [rcx]
0x1800bd813  mov     r9d, 810h
0x1800bd819  mov     r8, [rsp+8E0h+var_878]
0x1800bd81e  mov     edx, r14d
0x1800bd821  mov     rax, [rax+20h]
0x1800bd825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd82a  mov     ebx, eax
0x1800bd82c  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800bd830  call    cs:__imp_QueryPerformanceCounter
0x1800bd836  xorps   xmm6, xmm6
0x1800bd839  cmp     qword ptr [rdi+48h], 0
0x1800bd83e  jz      short loc_1800BD862
0x1800bd840  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800bd844  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800bd848  cvtsi2ss xmm6, rcx
0x1800bd84d  mulss   xmm6, cs:__real@447a0000
0x1800bd855  xorps   xmm0, xmm0
0x1800bd858  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800bd85e  divss   xmm6, xmm0
0x1800bd862  mov     rcx, [rsp+8E0h+var_878]
0x1800bd867  cmp     dword ptr [rcx+8], 1
0x1800bd86b  jnz     loc_1800BD927
0x1800bd871  mov     [rsp+8E0h+var_870], 0
0x1800bd87a  lea     rdx, [rsp+8E0h+var_870]
0x1800bd87f  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bd884  test    eax, eax
0x1800bd886  js      loc_1800BD998
0x1800bd88c  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bd891  mov     r8, rax
0x1800bd894  mov     ecx, [rax]
0x1800bd896  cmp     ecx, 4
0x1800bd899  jbe     loc_1800BD998
0x1800bd89f  mov     [rbp+7E0h+arg_0], ebx
0x1800bd8a5  movss   [rsp+8E0h+var_868], xmm6
0x1800bd8ab  mov     [rbp+7E0h+var_860], rdi
0x1800bd8af  mov     rdx, [rsp+8E0h+var_870]
0x1800bd8b4  mov     ecx, [rdx+10h]
0x1800bd8b7  mov     [rsp+8E0h+var_864], ecx
0x1800bd8bb  mov     ecx, [rdx+4]
0x1800bd8be  mov     [rsp+8E0h+var_880], ecx
0x1800bd8c2  mov     eax, [rdx+8]
0x1800bd8c5  mov     [rsp+8E0h+var_880+4], eax
0x1800bd8c9  mov     eax, [rdx]
0x1800bd8cb  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800bd8cf  lea     rax, [rbp+7E0h+arg_0]
0x1800bd8d6  mov     [rsp+8E0h+var_890], rax
0x1800bd8db  lea     rax, [rsp+8E0h+var_868]
0x1800bd8e0  mov     [rsp+8E0h+var_898], rax
0x1800bd8e5  lea     rax, [rbp+7E0h+var_860]
0x1800bd8e9  mov     [rsp+8E0h+var_8A0], rax
0x1800bd8ee  lea     rax, [rsp+8E0h+var_864]
0x1800bd8f3  mov     [rsp+8E0h+var_8A8], rax
0x1800bd8f8  lea     rax, [rsp+8E0h+var_880]
0x1800bd8fd  mov     [rsp+8E0h+var_8B0], rax
0x1800bd902  lea     rax, [rsp+8E0h+var_880+4]
0x1800bd907  mov     [rsp+8E0h+var_8B8], rax
0x1800bd90c  lea     rax, [rsp+8E0h+var_870]
0x1800bd911  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bd916  lea     rdx, word_1801679BE
0x1800bd91d  mov     rcx, r8
0x1800bd920  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bd925  jmp     short loc_1800BD998
0x1800bd927  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bd92c  mov     ecx, [rax]
0x1800bd92e  cmp     ecx, 4
0x1800bd931  jbe     short loc_1800BD998
0x1800bd933  mov     [rbp+7E0h+arg_0], ebx
0x1800bd939  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bd93f  mov     [rbp+7E0h+var_860], rdi
0x1800bd943  mov     rcx, [rsp+8E0h+var_878]
0x1800bd948  mov     edx, [rcx+8]
0x1800bd94b  mov     [rsp+8E0h+var_880+4], edx
0x1800bd94f  mov     ecx, [rdi+30h]
0x1800bd952  mov     [rsp+8E0h+var_880], ecx
0x1800bd956  lea     rcx, [rbp+7E0h+arg_0]
0x1800bd95d  mov     [rsp+8E0h+var_8A0], rcx
0x1800bd962  lea     rcx, [rsp+8E0h+var_870]
0x1800bd967  mov     [rsp+8E0h+var_8A8], rcx
0x1800bd96c  lea     rcx, [rbp+7E0h+var_860]
0x1800bd970  mov     [rsp+8E0h+var_8B0], rcx
0x1800bd975  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bd97a  mov     [rsp+8E0h+var_8B8], rcx
0x1800bd97f  lea     rcx, [rsp+8E0h+var_880]
0x1800bd984  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bd989  lea     rdx, byte_180167A37
0x1800bd990  mov     rcx, rax
0x1800bd993  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bd998  mov     rcx, [rbp+7E8h]; this
0x1800bd99f  test    ebx, ebx
0x1800bd9a1  jns     short loc_1800BD9C6
0x1800bd9a3  mov     r9d, ebx; char *
0x1800bd9a6  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bd9ad  mov     edx, 81h; void *
0x1800bd9b2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bd9b7  mov     rax, [rdi]
0x1800bd9ba  mov     rcx, rdi
0x1800bd9bd  mov     rax, [rax+20h]
0x1800bd9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd9c6  mov     ebx, [rdi+40h]
0x1800bd9c9  test    ebx, ebx
0x1800bd9cb  jns     short loc_1800BD9D4
0x1800bd9cd  mov     edx, 8Ah
0x1800bd9d2  jmp     short loc_1800BD9E5
0x1800bd9d4  mov     rcx, [rsp+8E0h+var_878]
0x1800bd9d9  mov     ebx, [rcx+4]
0x1800bd9dc  test    ebx, ebx
0x1800bd9de  jns     short loc_1800BD9FD
0x1800bd9e0  mov     edx, 8Ch; void *
0x1800bd9e5  mov     r9d, ebx; char *
0x1800bd9e8  mov     rcx, [rbp+7E8h]; this
0x1800bd9ef  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bd9f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd9fb  jmp     short loc_1800BDA1B
0x1800bd9fd  mov     rdx, [rbp+7E0h+arg_20]
0x1800bda04  call    ??$CastTo@UXvmGetSessionInstanceIdentifier@@@XvmMessage@@QEAAJPEAPEAUXvmGetSessionInstanceIdentifier@@@Z; XvmMessage::CastTo<XvmGetSessionInstanceIdentifier>(XvmGetSessionInstanceIdentifier * *)
0x1800bda09  mov     ebx, eax
0x1800bda0b  test    eax, eax
0x1800bda0d  jns     short loc_1800BDA19
0x1800bda0f  mov     r9d, eax
0x1800bda12  mov     edx, 8Dh
0x1800bda17  jmp     short loc_1800BD9E8
0x1800bda19  xor     ebx, ebx
0x1800bda1b  mov     rcx, [rbp+7E0h+arg_18]
0x1800bda22  mov     rax, [rsp+8E0h+var_878]
0x1800bda27  mov     [rcx], rax
0x1800bda2a  mov     eax, ebx
0x1800bda2c  lea     r11, [rsp+8E0h+var_10]
0x1800bda34  mov     rbx, [r11+28h]
0x1800bda38  mov     rsi, [r11+30h]
0x1800bda3c  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bda41  mov     rsp, r11
0x1800bda44  pop     r14
0x1800bda46  pop     rdi
0x1800bda47  pop     rbp
0x1800bda48  retn
```
