# CGuestXvmAudioObject::SendAndValidateResponse<XvmMfGetOutputTrustAuthorityByIndex>(uint,XvmMfGetOutputTrustAuthorityByIndex,XvmMessage * *,XvmMfGetOutputTrustAuthorityByIndex * *)

- ea: `0x1800c2ed4`
- end: `0x1800c321a`
- name: `??$SendAndValidateResponse@UXvmMfGetOutputTrustAuthorityByIndex@@@CGuestXvmAudioObject@@QEAAJIUXvmMfGetOutputTrustAuthorityByIndex@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c3a90`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800c2984`
- `0x1800c2ed4`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c2f16`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c3001`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c2f16`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c3001`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c2f4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c2f4a`

## string_xrefs

- `0x1800c2f2d`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800c2f6c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800c3177`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800c31c0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmMfGetOutputTrustAuthorityByIndex>(
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
  int OutputTrustAuthorityBy; // eax
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
    v32 = 60;
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
            (unsigned int)&unk_180168CE8,
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
          (unsigned int)&unk_180168C4E,
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
        OutputTrustAuthorityBy = XvmMessage::CastTo<XvmMfGetOutputTrustAuthorityByIndex>(v21, v39, v12);
        v9 = OutputTrustAuthorityBy;
        if ( OutputTrustAuthorityBy >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)OutputTrustAuthorityBy;
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
0x1800c2ed4  mov     rax, rsp
0x1800c2ed7  mov     [rax+10h], rbx
0x1800c2edb  mov     [rax+18h], rsi
0x1800c2edf  mov     [rax+20h], r9
0x1800c2ee3  push    rbp
0x1800c2ee4  push    rdi
0x1800c2ee5  push    r14
0x1800c2ee7  lea     rbp, [rax-7E8h]
0x1800c2eee  sub     rsp, 8D0h
0x1800c2ef5  movaps  xmmword ptr [rax-28h], xmm6
0x1800c2ef9  mov     ebx, r8d
0x1800c2efc  mov     r14d, edx
0x1800c2eff  mov     rdi, rcx
0x1800c2f02  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800c2f0a  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800c2f12  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800c2f16  call    cs:__imp_QueryPerformanceCounter
0x1800c2f1c  mov     esi, [rdi+40h]
0x1800c2f1f  test    esi, esi
0x1800c2f21  jns     short loc_1800C2F45
0x1800c2f23  mov     rcx, [rbp+7E8h]; this
0x1800c2f2a  mov     r9d, esi; char *
0x1800c2f2d  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c2f34  mov     edx, 4Fh ; 'O'; void *
0x1800c2f39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c2f3e  mov     eax, esi
0x1800c2f40  jmp     loc_1800C31FD
0x1800c2f45  mov     ecx, 810h; cb
0x1800c2f4a  call    cs:__imp_CoTaskMemAlloc
0x1800c2f50  mov     rsi, rax
0x1800c2f53  mov     [rsp+8E0h+var_878], rax
0x1800c2f58  test    rax, rax
0x1800c2f5b  jnz     short loc_1800C2F80
0x1800c2f5d  mov     rcx, [rbp+7E8h]; this
0x1800c2f64  mov     ebx, 8007000Eh
0x1800c2f69  mov     r9d, ebx; char *
0x1800c2f6c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c2f73  lea     edx, [rax+52h]; void *
0x1800c2f76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c2f7b  jmp     loc_1800C31FB
0x1800c2f80  mov     [rbp+7E0h+Src], 0
0x1800c2f88  mov     [rbp+7E0h+var_824], 0
0x1800c2f8f  xor     edx, edx; Val
0x1800c2f91  mov     r8d, 800h; Size
0x1800c2f97  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800c2f9b  call    memset_0
0x1800c2fa0  mov     [rbp+7E0h+var_820], ebx
0x1800c2fa3  mov     [rbp+7E0h+var_828], 3Ch ; '<'
0x1800c2faa  mov     rcx, rsi; void *
0x1800c2fad  lea     rdx, [rbp+7E0h+Src]; Src
0x1800c2fb1  mov     r8d, 810h; Size
0x1800c2fb7  call    memcpy_0
0x1800c2fbc  mov     rax, [rsp+8E0h+var_878]
0x1800c2fc1  mov     [rax+0Ch], r14d
0x1800c2fc5  lea     rax, [rbp+7E0h+arg_18]
0x1800c2fcc  mov     [rbp+7E0h+var_848], rax
0x1800c2fd0  lea     rax, [rsp+8E0h+var_878]
0x1800c2fd5  mov     [rbp+7E0h+var_840], rax
0x1800c2fd9  mov     [rbp+7E0h+var_838], 1
0x1800c2fdd  mov     rcx, [rdi+28h]
0x1800c2fe1  mov     rax, [rcx]
0x1800c2fe4  mov     r9d, 810h
0x1800c2fea  mov     r8, [rsp+8E0h+var_878]
0x1800c2fef  mov     edx, r14d
0x1800c2ff2  mov     rax, [rax+20h]
0x1800c2ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2ffb  mov     ebx, eax
0x1800c2ffd  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800c3001  call    cs:__imp_QueryPerformanceCounter
0x1800c3007  xorps   xmm6, xmm6
0x1800c300a  cmp     qword ptr [rdi+48h], 0
0x1800c300f  jz      short loc_1800C3033
0x1800c3011  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800c3015  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800c3019  cvtsi2ss xmm6, rcx
0x1800c301e  mulss   xmm6, cs:__real@447a0000
0x1800c3026  xorps   xmm0, xmm0
0x1800c3029  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800c302f  divss   xmm6, xmm0
0x1800c3033  mov     rcx, [rsp+8E0h+var_878]
0x1800c3038  cmp     dword ptr [rcx+8], 1
0x1800c303c  jnz     loc_1800C30F8
0x1800c3042  mov     [rsp+8E0h+var_870], 0
0x1800c304b  lea     rdx, [rsp+8E0h+var_870]
0x1800c3050  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800c3055  test    eax, eax
0x1800c3057  js      loc_1800C3169
0x1800c305d  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800c3062  mov     r8, rax
0x1800c3065  mov     ecx, [rax]
0x1800c3067  cmp     ecx, 4
0x1800c306a  jbe     loc_1800C3169
0x1800c3070  mov     [rbp+7E0h+arg_0], ebx
0x1800c3076  movss   [rsp+8E0h+var_868], xmm6
0x1800c307c  mov     [rbp+7E0h+var_860], rdi
0x1800c3080  mov     rdx, [rsp+8E0h+var_870]
0x1800c3085  mov     ecx, [rdx+10h]
0x1800c3088  mov     [rsp+8E0h+var_864], ecx
0x1800c308c  mov     ecx, [rdx+4]
0x1800c308f  mov     [rsp+8E0h+var_880], ecx
0x1800c3093  mov     eax, [rdx+8]
0x1800c3096  mov     [rsp+8E0h+var_880+4], eax
0x1800c309a  mov     eax, [rdx]
0x1800c309c  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800c30a0  lea     rax, [rbp+7E0h+arg_0]
0x1800c30a7  mov     [rsp+8E0h+var_890], rax
0x1800c30ac  lea     rax, [rsp+8E0h+var_868]
0x1800c30b1  mov     [rsp+8E0h+var_898], rax
0x1800c30b6  lea     rax, [rbp+7E0h+var_860]
0x1800c30ba  mov     [rsp+8E0h+var_8A0], rax
0x1800c30bf  lea     rax, [rsp+8E0h+var_864]
0x1800c30c4  mov     [rsp+8E0h+var_8A8], rax
0x1800c30c9  lea     rax, [rsp+8E0h+var_880]
0x1800c30ce  mov     [rsp+8E0h+var_8B0], rax
0x1800c30d3  lea     rax, [rsp+8E0h+var_880+4]
0x1800c30d8  mov     [rsp+8E0h+var_8B8], rax
0x1800c30dd  lea     rax, [rsp+8E0h+var_870]
0x1800c30e2  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800c30e7  lea     rdx, unk_180168CE8
0x1800c30ee  mov     rcx, r8
0x1800c30f1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c30f6  jmp     short loc_1800C3169
0x1800c30f8  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800c30fd  mov     ecx, [rax]
0x1800c30ff  cmp     ecx, 4
0x1800c3102  jbe     short loc_1800C3169
0x1800c3104  mov     [rbp+7E0h+arg_0], ebx
0x1800c310a  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800c3110  mov     [rbp+7E0h+var_860], rdi
0x1800c3114  mov     rcx, [rsp+8E0h+var_878]
0x1800c3119  mov     edx, [rcx+8]
0x1800c311c  mov     [rsp+8E0h+var_880+4], edx
0x1800c3120  mov     ecx, [rdi+30h]
0x1800c3123  mov     [rsp+8E0h+var_880], ecx
0x1800c3127  lea     rcx, [rbp+7E0h+arg_0]
0x1800c312e  mov     [rsp+8E0h+var_8A0], rcx
0x1800c3133  lea     rcx, [rsp+8E0h+var_870]
0x1800c3138  mov     [rsp+8E0h+var_8A8], rcx
0x1800c313d  lea     rcx, [rbp+7E0h+var_860]
0x1800c3141  mov     [rsp+8E0h+var_8B0], rcx
0x1800c3146  lea     rcx, [rsp+8E0h+var_880+4]
0x1800c314b  mov     [rsp+8E0h+var_8B8], rcx
0x1800c3150  lea     rcx, [rsp+8E0h+var_880]
0x1800c3155  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800c315a  lea     rdx, unk_180168C4E
0x1800c3161  mov     rcx, rax
0x1800c3164  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c3169  mov     rcx, [rbp+7E8h]; this
0x1800c3170  test    ebx, ebx
0x1800c3172  jns     short loc_1800C3197
0x1800c3174  mov     r9d, ebx; char *
0x1800c3177  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c317e  mov     edx, 81h; void *
0x1800c3183  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c3188  mov     rax, [rdi]
0x1800c318b  mov     rcx, rdi
0x1800c318e  mov     rax, [rax+20h]
0x1800c3192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3197  mov     ebx, [rdi+40h]
0x1800c319a  test    ebx, ebx
0x1800c319c  jns     short loc_1800C31A5
0x1800c319e  mov     edx, 8Ah
0x1800c31a3  jmp     short loc_1800C31B6
0x1800c31a5  mov     rcx, [rsp+8E0h+var_878]
0x1800c31aa  mov     ebx, [rcx+4]
0x1800c31ad  test    ebx, ebx
0x1800c31af  jns     short loc_1800C31CE
0x1800c31b1  mov     edx, 8Ch; void *
0x1800c31b6  mov     r9d, ebx; char *
0x1800c31b9  mov     rcx, [rbp+7E8h]; this
0x1800c31c0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c31c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c31cc  jmp     short loc_1800C31EC
0x1800c31ce  mov     rdx, [rbp+7E0h+arg_20]
0x1800c31d5  call    ??$CastTo@UXvmMfGetOutputTrustAuthorityByIndex@@@XvmMessage@@QEAAJPEAPEAUXvmMfGetOutputTrustAuthorityByIndex@@@Z; XvmMessage::CastTo<XvmMfGetOutputTrustAuthorityByIndex>(XvmMfGetOutputTrustAuthorityByIndex * *)
0x1800c31da  mov     ebx, eax
0x1800c31dc  test    eax, eax
0x1800c31de  jns     short loc_1800C31EA
0x1800c31e0  mov     r9d, eax
0x1800c31e3  mov     edx, 8Dh
0x1800c31e8  jmp     short loc_1800C31B9
0x1800c31ea  xor     ebx, ebx
0x1800c31ec  mov     rcx, [rbp+7E0h+arg_18]
0x1800c31f3  mov     rax, [rsp+8E0h+var_878]
0x1800c31f8  mov     [rcx], rax
0x1800c31fb  mov     eax, ebx
0x1800c31fd  lea     r11, [rsp+8E0h+var_10]
0x1800c3205  mov     rbx, [r11+28h]
0x1800c3209  mov     rsi, [r11+30h]
0x1800c320d  movaps  xmm6, xmmword ptr [r11-10h]
0x1800c3212  mov     rsp, r11
0x1800c3215  pop     r14
0x1800c3217  pop     rdi
0x1800c3218  pop     rbp
0x1800c3219  retn
```
