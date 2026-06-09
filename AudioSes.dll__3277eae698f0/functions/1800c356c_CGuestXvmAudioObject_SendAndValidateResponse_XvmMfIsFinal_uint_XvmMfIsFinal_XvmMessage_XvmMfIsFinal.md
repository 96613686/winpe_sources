# CGuestXvmAudioObject::SendAndValidateResponse<XvmMfIsFinal>(uint,XvmMfIsFinal,XvmMessage * *,XvmMfIsFinal * *)

- ea: `0x1800c356c`
- end: `0x1800c38b2`
- name: `??$SendAndValidateResponse@UXvmMfIsFinal@@@CGuestXvmAudioObject@@QEAAJIUXvmMfIsFinal@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c3c90`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800c2a14`
- `0x1800c356c`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c35ae`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c3699`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c35ae`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c3699`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c35e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c35e2`

## string_xrefs

- `0x1800c35c5`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800c3604`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800c380f`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800c3858`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmMfIsFinal>(__int64 a1, unsigned int a2, char a3, ...)
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
    v32 = 62;
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
            (unsigned int)&dword_180168B5C,
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
          (unsigned int)word_180168AC2,
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
        v18 = XvmMessage::CastTo<XvmMfIsFinal>(v21, v39, v12);
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
0x1800c356c  mov     rax, rsp
0x1800c356f  mov     [rax+10h], rbx
0x1800c3573  mov     [rax+18h], rsi
0x1800c3577  mov     [rax+20h], r9
0x1800c357b  push    rbp
0x1800c357c  push    rdi
0x1800c357d  push    r14
0x1800c357f  lea     rbp, [rax-7E8h]
0x1800c3586  sub     rsp, 8D0h
0x1800c358d  movaps  xmmword ptr [rax-28h], xmm6
0x1800c3591  mov     bl, r8b
0x1800c3594  mov     r14d, edx
0x1800c3597  mov     rdi, rcx
0x1800c359a  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800c35a2  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800c35aa  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800c35ae  call    cs:__imp_QueryPerformanceCounter
0x1800c35b4  mov     esi, [rdi+40h]
0x1800c35b7  test    esi, esi
0x1800c35b9  jns     short loc_1800C35DD
0x1800c35bb  mov     rcx, [rbp+7E8h]; this
0x1800c35c2  mov     r9d, esi; char *
0x1800c35c5  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c35cc  mov     edx, 4Fh ; 'O'; void *
0x1800c35d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c35d6  mov     eax, esi
0x1800c35d8  jmp     loc_1800C3895
0x1800c35dd  mov     ecx, 810h; cb
0x1800c35e2  call    cs:__imp_CoTaskMemAlloc
0x1800c35e8  mov     rsi, rax
0x1800c35eb  mov     [rsp+8E0h+var_878], rax
0x1800c35f0  test    rax, rax
0x1800c35f3  jnz     short loc_1800C3618
0x1800c35f5  mov     rcx, [rbp+7E8h]; this
0x1800c35fc  mov     ebx, 8007000Eh
0x1800c3601  mov     r9d, ebx; char *
0x1800c3604  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c360b  lea     edx, [rax+52h]; void *
0x1800c360e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c3613  jmp     loc_1800C3893
0x1800c3618  mov     [rbp+7E0h+Src], 0
0x1800c3620  mov     [rbp+7E0h+var_824], 0
0x1800c3627  xor     edx, edx; Val
0x1800c3629  mov     r8d, 800h; Size
0x1800c362f  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800c3633  call    memset_0
0x1800c3638  mov     [rbp+7E0h+var_820], bl
0x1800c363b  mov     [rbp+7E0h+var_828], 3Eh ; '>'
0x1800c3642  mov     rcx, rsi; void *
0x1800c3645  lea     rdx, [rbp+7E0h+Src]; Src
0x1800c3649  mov     r8d, 810h; Size
0x1800c364f  call    memcpy_0
0x1800c3654  mov     rax, [rsp+8E0h+var_878]
0x1800c3659  mov     [rax+0Ch], r14d
0x1800c365d  lea     rax, [rbp+7E0h+arg_18]
0x1800c3664  mov     [rbp+7E0h+var_848], rax
0x1800c3668  lea     rax, [rsp+8E0h+var_878]
0x1800c366d  mov     [rbp+7E0h+var_840], rax
0x1800c3671  mov     [rbp+7E0h+var_838], 1
0x1800c3675  mov     rcx, [rdi+28h]
0x1800c3679  mov     rax, [rcx]
0x1800c367c  mov     r9d, 810h
0x1800c3682  mov     r8, [rsp+8E0h+var_878]
0x1800c3687  mov     edx, r14d
0x1800c368a  mov     rax, [rax+20h]
0x1800c368e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3693  mov     ebx, eax
0x1800c3695  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800c3699  call    cs:__imp_QueryPerformanceCounter
0x1800c369f  xorps   xmm6, xmm6
0x1800c36a2  cmp     qword ptr [rdi+48h], 0
0x1800c36a7  jz      short loc_1800C36CB
0x1800c36a9  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800c36ad  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800c36b1  cvtsi2ss xmm6, rcx
0x1800c36b6  mulss   xmm6, cs:__real@447a0000
0x1800c36be  xorps   xmm0, xmm0
0x1800c36c1  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800c36c7  divss   xmm6, xmm0
0x1800c36cb  mov     rcx, [rsp+8E0h+var_878]
0x1800c36d0  cmp     dword ptr [rcx+8], 1
0x1800c36d4  jnz     loc_1800C3790
0x1800c36da  mov     [rsp+8E0h+var_870], 0
0x1800c36e3  lea     rdx, [rsp+8E0h+var_870]
0x1800c36e8  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800c36ed  test    eax, eax
0x1800c36ef  js      loc_1800C3801
0x1800c36f5  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800c36fa  mov     r8, rax
0x1800c36fd  mov     ecx, [rax]
0x1800c36ff  cmp     ecx, 4
0x1800c3702  jbe     loc_1800C3801
0x1800c3708  mov     [rbp+7E0h+arg_0], ebx
0x1800c370e  movss   [rsp+8E0h+var_868], xmm6
0x1800c3714  mov     [rbp+7E0h+var_860], rdi
0x1800c3718  mov     rdx, [rsp+8E0h+var_870]
0x1800c371d  mov     ecx, [rdx+10h]
0x1800c3720  mov     [rsp+8E0h+var_864], ecx
0x1800c3724  mov     ecx, [rdx+4]
0x1800c3727  mov     [rsp+8E0h+var_880], ecx
0x1800c372b  mov     eax, [rdx+8]
0x1800c372e  mov     [rsp+8E0h+var_880+4], eax
0x1800c3732  mov     eax, [rdx]
0x1800c3734  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800c3738  lea     rax, [rbp+7E0h+arg_0]
0x1800c373f  mov     [rsp+8E0h+var_890], rax
0x1800c3744  lea     rax, [rsp+8E0h+var_868]
0x1800c3749  mov     [rsp+8E0h+var_898], rax
0x1800c374e  lea     rax, [rbp+7E0h+var_860]
0x1800c3752  mov     [rsp+8E0h+var_8A0], rax
0x1800c3757  lea     rax, [rsp+8E0h+var_864]
0x1800c375c  mov     [rsp+8E0h+var_8A8], rax
0x1800c3761  lea     rax, [rsp+8E0h+var_880]
0x1800c3766  mov     [rsp+8E0h+var_8B0], rax
0x1800c376b  lea     rax, [rsp+8E0h+var_880+4]
0x1800c3770  mov     [rsp+8E0h+var_8B8], rax
0x1800c3775  lea     rax, [rsp+8E0h+var_870]
0x1800c377a  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800c377f  lea     rdx, dword_180168B5C
0x1800c3786  mov     rcx, r8
0x1800c3789  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c378e  jmp     short loc_1800C3801
0x1800c3790  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800c3795  mov     ecx, [rax]
0x1800c3797  cmp     ecx, 4
0x1800c379a  jbe     short loc_1800C3801
0x1800c379c  mov     [rbp+7E0h+arg_0], ebx
0x1800c37a2  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800c37a8  mov     [rbp+7E0h+var_860], rdi
0x1800c37ac  mov     rcx, [rsp+8E0h+var_878]
0x1800c37b1  mov     edx, [rcx+8]
0x1800c37b4  mov     [rsp+8E0h+var_880+4], edx
0x1800c37b8  mov     ecx, [rdi+30h]
0x1800c37bb  mov     [rsp+8E0h+var_880], ecx
0x1800c37bf  lea     rcx, [rbp+7E0h+arg_0]
0x1800c37c6  mov     [rsp+8E0h+var_8A0], rcx
0x1800c37cb  lea     rcx, [rsp+8E0h+var_870]
0x1800c37d0  mov     [rsp+8E0h+var_8A8], rcx
0x1800c37d5  lea     rcx, [rbp+7E0h+var_860]
0x1800c37d9  mov     [rsp+8E0h+var_8B0], rcx
0x1800c37de  lea     rcx, [rsp+8E0h+var_880+4]
0x1800c37e3  mov     [rsp+8E0h+var_8B8], rcx
0x1800c37e8  lea     rcx, [rsp+8E0h+var_880]
0x1800c37ed  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800c37f2  lea     rdx, word_180168AC2
0x1800c37f9  mov     rcx, rax
0x1800c37fc  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c3801  mov     rcx, [rbp+7E8h]; this
0x1800c3808  test    ebx, ebx
0x1800c380a  jns     short loc_1800C382F
0x1800c380c  mov     r9d, ebx; char *
0x1800c380f  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c3816  mov     edx, 81h; void *
0x1800c381b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c3820  mov     rax, [rdi]
0x1800c3823  mov     rcx, rdi
0x1800c3826  mov     rax, [rax+20h]
0x1800c382a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c382f  mov     ebx, [rdi+40h]
0x1800c3832  test    ebx, ebx
0x1800c3834  jns     short loc_1800C383D
0x1800c3836  mov     edx, 8Ah
0x1800c383b  jmp     short loc_1800C384E
0x1800c383d  mov     rcx, [rsp+8E0h+var_878]
0x1800c3842  mov     ebx, [rcx+4]
0x1800c3845  test    ebx, ebx
0x1800c3847  jns     short loc_1800C3866
0x1800c3849  mov     edx, 8Ch; void *
0x1800c384e  mov     r9d, ebx; char *
0x1800c3851  mov     rcx, [rbp+7E8h]; this
0x1800c3858  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c385f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c3864  jmp     short loc_1800C3884
0x1800c3866  mov     rdx, [rbp+7E0h+arg_20]
0x1800c386d  call    ??$CastTo@UXvmMfIsFinal@@@XvmMessage@@QEAAJPEAPEAUXvmMfIsFinal@@@Z; XvmMessage::CastTo<XvmMfIsFinal>(XvmMfIsFinal * *)
0x1800c3872  mov     ebx, eax
0x1800c3874  test    eax, eax
0x1800c3876  jns     short loc_1800C3882
0x1800c3878  mov     r9d, eax
0x1800c387b  mov     edx, 8Dh
0x1800c3880  jmp     short loc_1800C3851
0x1800c3882  xor     ebx, ebx
0x1800c3884  mov     rcx, [rbp+7E0h+arg_18]
0x1800c388b  mov     rax, [rsp+8E0h+var_878]
0x1800c3890  mov     [rcx], rax
0x1800c3893  mov     eax, ebx
0x1800c3895  lea     r11, [rsp+8E0h+var_10]
0x1800c389d  mov     rbx, [r11+28h]
0x1800c38a1  mov     rsi, [r11+30h]
0x1800c38a5  movaps  xmm6, xmmword ptr [r11-10h]
0x1800c38aa  mov     rsp, r11
0x1800c38ad  pop     r14
0x1800c38af  pop     rdi
0x1800c38b0  pop     rbp
0x1800c38b1  retn
```
