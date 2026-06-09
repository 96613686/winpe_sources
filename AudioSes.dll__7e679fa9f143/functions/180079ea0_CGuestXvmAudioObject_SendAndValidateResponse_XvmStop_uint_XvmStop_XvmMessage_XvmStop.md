# CGuestXvmAudioObject::SendAndValidateResponse<XvmStop>(uint,XvmStop,XvmMessage * *,XvmStop * *)

- ea: `0x180079ea0`
- end: `0x18007a1e6`
- name: `??$SendAndValidateResponse@UXvmStop@@@CGuestXvmAudioObject@@QEAAJIUXvmStop@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180079810`
- `0x18010ed20`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180079ea0`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2f48`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180079ee2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180079fcd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180079ee2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180079fcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180079f16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180079f16`

## string_xrefs

- `0x180079ef9`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x180079f38`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18007a143`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18007a18c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmStop>(__int64 a1, unsigned int a2, char a3, ...)
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
    v32 = 8;
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
            (unsigned int)&unk_18016622B,
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
          (unsigned int)&unk_180166118,
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
        v18 = XvmMessage::CastTo<XvmStop>(v21, v39, v12);
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
0x180079ea0  mov     rax, rsp
0x180079ea3  mov     [rax+10h], rbx
0x180079ea7  mov     [rax+18h], rsi
0x180079eab  mov     [rax+20h], r9
0x180079eaf  push    rbp
0x180079eb0  push    rdi
0x180079eb1  push    r14
0x180079eb3  lea     rbp, [rax-7E8h]
0x180079eba  sub     rsp, 8D0h
0x180079ec1  movaps  xmmword ptr [rax-28h], xmm6
0x180079ec5  mov     bl, r8b
0x180079ec8  mov     r14d, edx
0x180079ecb  mov     rdi, rcx
0x180079ece  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x180079ed6  mov     qword ptr [rbp+7E0h+var_858], 0
0x180079ede  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x180079ee2  call    cs:__imp_QueryPerformanceCounter
0x180079ee8  mov     esi, [rdi+40h]
0x180079eeb  test    esi, esi
0x180079eed  jns     short loc_180079F11
0x180079eef  mov     rcx, [rbp+7E8h]; this
0x180079ef6  mov     r9d, esi; char *
0x180079ef9  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180079f00  mov     edx, 4Fh ; 'O'; void *
0x180079f05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079f0a  mov     eax, esi
0x180079f0c  jmp     loc_18007A1C9
0x180079f11  mov     ecx, 810h; cb
0x180079f16  call    cs:__imp_CoTaskMemAlloc
0x180079f1c  mov     rsi, rax
0x180079f1f  mov     [rsp+8E0h+var_878], rax
0x180079f24  test    rax, rax
0x180079f27  jnz     short loc_180079F4C
0x180079f29  mov     rcx, [rbp+7E8h]; this
0x180079f30  mov     ebx, 8007000Eh
0x180079f35  mov     r9d, ebx; char *
0x180079f38  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180079f3f  lea     edx, [rax+52h]; void *
0x180079f42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079f47  jmp     loc_18007A1C7
0x180079f4c  mov     [rbp+7E0h+Src], 0
0x180079f54  mov     [rbp+7E0h+var_824], 0
0x180079f5b  xor     edx, edx; Val
0x180079f5d  mov     r8d, 800h; Size
0x180079f63  lea     rcx, [rbp+7E0h+var_820]; void *
0x180079f67  call    memset_0
0x180079f6c  mov     [rbp+7E0h+var_820], bl
0x180079f6f  mov     [rbp+7E0h+var_828], 8
0x180079f76  mov     rcx, rsi; void *
0x180079f79  lea     rdx, [rbp+7E0h+Src]; Src
0x180079f7d  mov     r8d, 810h; Size
0x180079f83  call    memcpy_0
0x180079f88  mov     rax, [rsp+8E0h+var_878]
0x180079f8d  mov     [rax+0Ch], r14d
0x180079f91  lea     rax, [rbp+7E0h+arg_18]
0x180079f98  mov     [rbp+7E0h+var_848], rax
0x180079f9c  lea     rax, [rsp+8E0h+var_878]
0x180079fa1  mov     [rbp+7E0h+var_840], rax
0x180079fa5  mov     [rbp+7E0h+var_838], 1
0x180079fa9  mov     rcx, [rdi+28h]
0x180079fad  mov     rax, [rcx]
0x180079fb0  mov     r9d, 810h
0x180079fb6  mov     r8, [rsp+8E0h+var_878]
0x180079fbb  mov     edx, r14d
0x180079fbe  mov     rax, [rax+20h]
0x180079fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079fc7  mov     ebx, eax
0x180079fc9  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x180079fcd  call    cs:__imp_QueryPerformanceCounter
0x180079fd3  xorps   xmm6, xmm6
0x180079fd6  cmp     qword ptr [rdi+48h], 0
0x180079fdb  jz      short loc_180079FFF
0x180079fdd  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x180079fe1  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x180079fe5  cvtsi2ss xmm6, rcx
0x180079fea  mulss   xmm6, cs:__real@447a0000
0x180079ff2  xorps   xmm0, xmm0
0x180079ff5  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x180079ffb  divss   xmm6, xmm0
0x180079fff  mov     rcx, [rsp+8E0h+var_878]
0x18007a004  cmp     dword ptr [rcx+8], 1
0x18007a008  jnz     loc_18007A0C4
0x18007a00e  mov     [rsp+8E0h+var_870], 0
0x18007a017  lea     rdx, [rsp+8E0h+var_870]
0x18007a01c  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x18007a021  test    eax, eax
0x18007a023  js      loc_18007A135
0x18007a029  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x18007a02e  mov     r8, rax
0x18007a031  mov     ecx, [rax]
0x18007a033  cmp     ecx, 4
0x18007a036  jbe     loc_18007A135
0x18007a03c  mov     [rbp+7E0h+arg_0], ebx
0x18007a042  movss   [rsp+8E0h+var_868], xmm6
0x18007a048  mov     [rbp+7E0h+var_860], rdi
0x18007a04c  mov     rdx, [rsp+8E0h+var_870]
0x18007a051  mov     ecx, [rdx+10h]
0x18007a054  mov     [rsp+8E0h+var_864], ecx
0x18007a058  mov     ecx, [rdx+4]
0x18007a05b  mov     [rsp+8E0h+var_880], ecx
0x18007a05f  mov     eax, [rdx+8]
0x18007a062  mov     [rsp+8E0h+var_880+4], eax
0x18007a066  mov     eax, [rdx]
0x18007a068  mov     dword ptr [rsp+8E0h+var_870], eax
0x18007a06c  lea     rax, [rbp+7E0h+arg_0]
0x18007a073  mov     [rsp+8E0h+var_890], rax
0x18007a078  lea     rax, [rsp+8E0h+var_868]
0x18007a07d  mov     [rsp+8E0h+var_898], rax
0x18007a082  lea     rax, [rbp+7E0h+var_860]
0x18007a086  mov     [rsp+8E0h+var_8A0], rax
0x18007a08b  lea     rax, [rsp+8E0h+var_864]
0x18007a090  mov     [rsp+8E0h+var_8A8], rax
0x18007a095  lea     rax, [rsp+8E0h+var_880]
0x18007a09a  mov     [rsp+8E0h+var_8B0], rax
0x18007a09f  lea     rax, [rsp+8E0h+var_880+4]
0x18007a0a4  mov     [rsp+8E0h+var_8B8], rax
0x18007a0a9  lea     rax, [rsp+8E0h+var_870]
0x18007a0ae  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x18007a0b3  lea     rdx, unk_18016622B
0x18007a0ba  mov     rcx, r8
0x18007a0bd  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007a0c2  jmp     short loc_18007A135
0x18007a0c4  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x18007a0c9  mov     ecx, [rax]
0x18007a0cb  cmp     ecx, 4
0x18007a0ce  jbe     short loc_18007A135
0x18007a0d0  mov     [rbp+7E0h+arg_0], ebx
0x18007a0d6  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x18007a0dc  mov     [rbp+7E0h+var_860], rdi
0x18007a0e0  mov     rcx, [rsp+8E0h+var_878]
0x18007a0e5  mov     edx, [rcx+8]
0x18007a0e8  mov     [rsp+8E0h+var_880+4], edx
0x18007a0ec  mov     ecx, [rdi+30h]
0x18007a0ef  mov     [rsp+8E0h+var_880], ecx
0x18007a0f3  lea     rcx, [rbp+7E0h+arg_0]
0x18007a0fa  mov     [rsp+8E0h+var_8A0], rcx
0x18007a0ff  lea     rcx, [rsp+8E0h+var_870]
0x18007a104  mov     [rsp+8E0h+var_8A8], rcx
0x18007a109  lea     rcx, [rbp+7E0h+var_860]
0x18007a10d  mov     [rsp+8E0h+var_8B0], rcx
0x18007a112  lea     rcx, [rsp+8E0h+var_880+4]
0x18007a117  mov     [rsp+8E0h+var_8B8], rcx
0x18007a11c  lea     rcx, [rsp+8E0h+var_880]
0x18007a121  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x18007a126  lea     rdx, unk_180166118
0x18007a12d  mov     rcx, rax
0x18007a130  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18007a135  mov     rcx, [rbp+7E8h]; this
0x18007a13c  test    ebx, ebx
0x18007a13e  jns     short loc_18007A163
0x18007a140  mov     r9d, ebx; char *
0x18007a143  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18007a14a  mov     edx, 81h; void *
0x18007a14f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007a154  mov     rax, [rdi]
0x18007a157  mov     rcx, rdi
0x18007a15a  mov     rax, [rax+20h]
0x18007a15e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a163  mov     ebx, [rdi+40h]
0x18007a166  test    ebx, ebx
0x18007a168  jns     short loc_18007A171
0x18007a16a  mov     edx, 8Ah
0x18007a16f  jmp     short loc_18007A182
0x18007a171  mov     rcx, [rsp+8E0h+var_878]
0x18007a176  mov     ebx, [rcx+4]
0x18007a179  test    ebx, ebx
0x18007a17b  jns     short loc_18007A19A
0x18007a17d  mov     edx, 8Ch; void *
0x18007a182  mov     r9d, ebx; char *
0x18007a185  mov     rcx, [rbp+7E8h]; this
0x18007a18c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18007a193  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a198  jmp     short loc_18007A1B8
0x18007a19a  mov     rdx, [rbp+7E0h+arg_20]
0x18007a1a1  call    ??$CastTo@UXvmStop@@@XvmMessage@@QEAAJPEAPEAUXvmStop@@@Z; XvmMessage::CastTo<XvmStop>(XvmStop * *)
0x18007a1a6  mov     ebx, eax
0x18007a1a8  test    eax, eax
0x18007a1aa  jns     short loc_18007A1B6
0x18007a1ac  mov     r9d, eax
0x18007a1af  mov     edx, 8Dh
0x18007a1b4  jmp     short loc_18007A185
0x18007a1b6  xor     ebx, ebx
0x18007a1b8  mov     rcx, [rbp+7E0h+arg_18]
0x18007a1bf  mov     rax, [rsp+8E0h+var_878]
0x18007a1c4  mov     [rcx], rax
0x18007a1c7  mov     eax, ebx
0x18007a1c9  lea     r11, [rsp+8E0h+var_10]
0x18007a1d1  mov     rbx, [r11+28h]
0x18007a1d5  mov     rsi, [r11+30h]
0x18007a1d9  movaps  xmm6, xmmword ptr [r11-10h]
0x18007a1de  mov     rsp, r11
0x18007a1e1  pop     r14
0x18007a1e3  pop     rdi
0x18007a1e4  pop     rbp
0x18007a1e5  retn
```
