# CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetStepInfo>(uint,XvmAudioEndpointVolumeGetStepInfo,XvmMessage * *,XvmAudioEndpointVolumeGetStepInfo * *)

- ea: `0x1800b429c`
- end: `0x1800b45e3`
- name: `??$SendAndValidateResponse@UXvmAudioEndpointVolumeGetStepInfo@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeGetStepInfo@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `839`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b7220`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a5df8`
- `0x1800b429c`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b42de`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b43ca`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b42de`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b43ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4312`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4312`

## string_xrefs

- `0x1800b42f5`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b4334`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b4540`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b4589`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetStepInfo>(
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
  int Step; // eax
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
    v32 = 92;
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
            (unsigned int)qword_180166AE0,
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
          (unsigned int)byte_1801669CD,
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
        Step = XvmMessage::CastTo<XvmAudioEndpointVolumeGetStepInfo>(v21, v39, v12);
        v9 = Step;
        if ( Step >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)Step;
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
0x1800b429c  mov     rax, rsp
0x1800b429f  mov     [rax+10h], rbx
0x1800b42a3  mov     [rax+18h], rsi
0x1800b42a7  mov     [rax+20h], r9
0x1800b42ab  push    rbp
0x1800b42ac  push    rdi
0x1800b42ad  push    r14
0x1800b42af  lea     rbp, [rax-7E8h]
0x1800b42b6  sub     rsp, 8D0h
0x1800b42bd  movaps  xmmword ptr [rax-28h], xmm6
0x1800b42c1  mov     rbx, r8
0x1800b42c4  mov     r14d, edx
0x1800b42c7  mov     rdi, rcx
0x1800b42ca  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800b42d2  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800b42da  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800b42de  call    cs:__imp_QueryPerformanceCounter
0x1800b42e4  mov     esi, [rdi+40h]
0x1800b42e7  test    esi, esi
0x1800b42e9  jns     short loc_1800B430D
0x1800b42eb  mov     rcx, [rbp+7E8h]; this
0x1800b42f2  mov     r9d, esi; char *
0x1800b42f5  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b42fc  mov     edx, 4Fh ; 'O'; void *
0x1800b4301  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4306  mov     eax, esi
0x1800b4308  jmp     loc_1800B45C6
0x1800b430d  mov     ecx, 810h; cb
0x1800b4312  call    cs:__imp_CoTaskMemAlloc
0x1800b4318  mov     rsi, rax
0x1800b431b  mov     [rsp+8E0h+var_878], rax
0x1800b4320  test    rax, rax
0x1800b4323  jnz     short loc_1800B4348
0x1800b4325  mov     rcx, [rbp+7E8h]; this
0x1800b432c  mov     ebx, 8007000Eh
0x1800b4331  mov     r9d, ebx; char *
0x1800b4334  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b433b  lea     edx, [rax+52h]; void *
0x1800b433e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4343  jmp     loc_1800B45C4
0x1800b4348  mov     [rbp+7E0h+Src], 0
0x1800b4350  mov     [rbp+7E0h+var_824], 0
0x1800b4357  xor     edx, edx; Val
0x1800b4359  mov     r8d, 800h; Size
0x1800b435f  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800b4363  call    memset_0
0x1800b4368  mov     [rbp+7E0h+var_820], rbx
0x1800b436c  mov     [rbp+7E0h+var_828], 5Ch ; '\'
0x1800b4373  mov     rcx, rsi; void *
0x1800b4376  lea     rdx, [rbp+7E0h+Src]; Src
0x1800b437a  mov     r8d, 810h; Size
0x1800b4380  call    memcpy_0
0x1800b4385  mov     rax, [rsp+8E0h+var_878]
0x1800b438a  mov     [rax+0Ch], r14d
0x1800b438e  lea     rax, [rbp+7E0h+arg_18]
0x1800b4395  mov     [rbp+7E0h+var_848], rax
0x1800b4399  lea     rax, [rsp+8E0h+var_878]
0x1800b439e  mov     [rbp+7E0h+var_840], rax
0x1800b43a2  mov     [rbp+7E0h+var_838], 1
0x1800b43a6  mov     rcx, [rdi+28h]
0x1800b43aa  mov     rax, [rcx]
0x1800b43ad  mov     r9d, 810h
0x1800b43b3  mov     r8, [rsp+8E0h+var_878]
0x1800b43b8  mov     edx, r14d
0x1800b43bb  mov     rax, [rax+20h]
0x1800b43bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b43c4  mov     ebx, eax
0x1800b43c6  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800b43ca  call    cs:__imp_QueryPerformanceCounter
0x1800b43d0  xorps   xmm6, xmm6
0x1800b43d3  cmp     qword ptr [rdi+48h], 0
0x1800b43d8  jz      short loc_1800B43FC
0x1800b43da  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800b43de  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800b43e2  cvtsi2ss xmm6, rcx
0x1800b43e7  mulss   xmm6, cs:__real@447a0000
0x1800b43ef  xorps   xmm0, xmm0
0x1800b43f2  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800b43f8  divss   xmm6, xmm0
0x1800b43fc  mov     rcx, [rsp+8E0h+var_878]
0x1800b4401  cmp     dword ptr [rcx+8], 1
0x1800b4405  jnz     loc_1800B44C1
0x1800b440b  mov     [rsp+8E0h+var_870], 0
0x1800b4414  lea     rdx, [rsp+8E0h+var_870]
0x1800b4419  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b441e  test    eax, eax
0x1800b4420  js      loc_1800B4532
0x1800b4426  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b442b  mov     r8, rax
0x1800b442e  mov     ecx, [rax]
0x1800b4430  cmp     ecx, 4
0x1800b4433  jbe     loc_1800B4532
0x1800b4439  mov     [rbp+7E0h+arg_0], ebx
0x1800b443f  movss   [rsp+8E0h+var_868], xmm6
0x1800b4445  mov     [rbp+7E0h+var_860], rdi
0x1800b4449  mov     rdx, [rsp+8E0h+var_870]
0x1800b444e  mov     ecx, [rdx+10h]
0x1800b4451  mov     [rsp+8E0h+var_864], ecx
0x1800b4455  mov     ecx, [rdx+4]
0x1800b4458  mov     [rsp+8E0h+var_880], ecx
0x1800b445c  mov     eax, [rdx+8]
0x1800b445f  mov     [rsp+8E0h+var_880+4], eax
0x1800b4463  mov     eax, [rdx]
0x1800b4465  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800b4469  lea     rax, [rbp+7E0h+arg_0]
0x1800b4470  mov     [rsp+8E0h+var_890], rax
0x1800b4475  lea     rax, [rsp+8E0h+var_868]
0x1800b447a  mov     [rsp+8E0h+var_898], rax
0x1800b447f  lea     rax, [rbp+7E0h+var_860]
0x1800b4483  mov     [rsp+8E0h+var_8A0], rax
0x1800b4488  lea     rax, [rsp+8E0h+var_864]
0x1800b448d  mov     [rsp+8E0h+var_8A8], rax
0x1800b4492  lea     rax, [rsp+8E0h+var_880]
0x1800b4497  mov     [rsp+8E0h+var_8B0], rax
0x1800b449c  lea     rax, [rsp+8E0h+var_880+4]
0x1800b44a1  mov     [rsp+8E0h+var_8B8], rax
0x1800b44a6  lea     rax, [rsp+8E0h+var_870]
0x1800b44ab  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800b44b0  lea     rdx, qword_180166AE0
0x1800b44b7  mov     rcx, r8
0x1800b44ba  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b44bf  jmp     short loc_1800B4532
0x1800b44c1  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b44c6  mov     ecx, [rax]
0x1800b44c8  cmp     ecx, 4
0x1800b44cb  jbe     short loc_1800B4532
0x1800b44cd  mov     [rbp+7E0h+arg_0], ebx
0x1800b44d3  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800b44d9  mov     [rbp+7E0h+var_860], rdi
0x1800b44dd  mov     rcx, [rsp+8E0h+var_878]
0x1800b44e2  mov     edx, [rcx+8]
0x1800b44e5  mov     [rsp+8E0h+var_880+4], edx
0x1800b44e9  mov     ecx, [rdi+30h]
0x1800b44ec  mov     [rsp+8E0h+var_880], ecx
0x1800b44f0  lea     rcx, [rbp+7E0h+arg_0]
0x1800b44f7  mov     [rsp+8E0h+var_8A0], rcx
0x1800b44fc  lea     rcx, [rsp+8E0h+var_870]
0x1800b4501  mov     [rsp+8E0h+var_8A8], rcx
0x1800b4506  lea     rcx, [rbp+7E0h+var_860]
0x1800b450a  mov     [rsp+8E0h+var_8B0], rcx
0x1800b450f  lea     rcx, [rsp+8E0h+var_880+4]
0x1800b4514  mov     [rsp+8E0h+var_8B8], rcx
0x1800b4519  lea     rcx, [rsp+8E0h+var_880]
0x1800b451e  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800b4523  lea     rdx, byte_1801669CD
0x1800b452a  mov     rcx, rax
0x1800b452d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b4532  mov     rcx, [rbp+7E8h]; this
0x1800b4539  test    ebx, ebx
0x1800b453b  jns     short loc_1800B4560
0x1800b453d  mov     r9d, ebx; char *
0x1800b4540  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b4547  mov     edx, 81h; void *
0x1800b454c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b4551  mov     rax, [rdi]
0x1800b4554  mov     rcx, rdi
0x1800b4557  mov     rax, [rax+20h]
0x1800b455b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4560  mov     ebx, [rdi+40h]
0x1800b4563  test    ebx, ebx
0x1800b4565  jns     short loc_1800B456E
0x1800b4567  mov     edx, 8Ah
0x1800b456c  jmp     short loc_1800B457F
0x1800b456e  mov     rcx, [rsp+8E0h+var_878]
0x1800b4573  mov     ebx, [rcx+4]
0x1800b4576  test    ebx, ebx
0x1800b4578  jns     short loc_1800B4597
0x1800b457a  mov     edx, 8Ch; void *
0x1800b457f  mov     r9d, ebx; char *
0x1800b4582  mov     rcx, [rbp+7E8h]; this
0x1800b4589  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b4590  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4595  jmp     short loc_1800B45B5
0x1800b4597  mov     rdx, [rbp+7E0h+arg_20]
0x1800b459e  call    ??$CastTo@UXvmAudioEndpointVolumeGetStepInfo@@@XvmMessage@@QEAAJPEAPEAUXvmAudioEndpointVolumeGetStepInfo@@@Z; XvmMessage::CastTo<XvmAudioEndpointVolumeGetStepInfo>(XvmAudioEndpointVolumeGetStepInfo * *)
0x1800b45a3  mov     ebx, eax
0x1800b45a5  test    eax, eax
0x1800b45a7  jns     short loc_1800B45B3
0x1800b45a9  mov     r9d, eax
0x1800b45ac  mov     edx, 8Dh
0x1800b45b1  jmp     short loc_1800B4582
0x1800b45b3  xor     ebx, ebx
0x1800b45b5  mov     rcx, [rbp+7E0h+arg_18]
0x1800b45bc  mov     rax, [rsp+8E0h+var_878]
0x1800b45c1  mov     [rcx], rax
0x1800b45c4  mov     eax, ebx
0x1800b45c6  lea     r11, [rsp+8E0h+var_10]
0x1800b45ce  mov     rbx, [r11+28h]
0x1800b45d2  mov     rsi, [r11+30h]
0x1800b45d6  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b45db  mov     rsp, r11
0x1800b45de  pop     r14
0x1800b45e0  pop     rdi
0x1800b45e1  pop     rbp
0x1800b45e2  retn
```
