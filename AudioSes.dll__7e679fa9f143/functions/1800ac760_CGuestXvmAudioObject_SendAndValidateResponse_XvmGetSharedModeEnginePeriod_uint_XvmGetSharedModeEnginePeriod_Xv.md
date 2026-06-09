# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetSharedModeEnginePeriod>(uint,XvmGetSharedModeEnginePeriod,XvmMessage * *,XvmGetSharedModeEnginePeriod * *)

- ea: `0x1800ac760`
- end: `0x1800acad4`
- name: `??$SendAndValidateResponse@UXvmGetSharedModeEnginePeriod@@@CGuestXvmAudioObject@@QEAAJIUXvmGetSharedModeEnginePeriod@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `884`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800afd10`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2ab8`
- `0x1800ac760`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ac7a2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ac8bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ac7a2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ac8bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ac7d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ac7d6`

## string_xrefs

- `0x1800ac7b9`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ac7f8`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800aca31`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800aca7a`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetSharedModeEnginePeriod>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        ...)
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
  int SharedModeEngine; // eax
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
  _OWORD v34[5]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v35; // [rsp+118h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+8F0h] [rbp+7E8h]
  int v37; // [rsp+8F8h] [rbp+7F0h] BYREF
  _QWORD *v38; // [rsp+910h] [rbp+808h] BYREF
  va_list va; // [rsp+910h] [rbp+808h]
  __int64 v40; // [rsp+918h] [rbp+810h]
  va_list va1; // [rsp+920h] [rbp+818h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v38 = va_arg(va1, _QWORD *);
  v40 = va_arg(va1, _QWORD);
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
    v34[0] = *(_OWORD *)a3;
    v34[1] = *(_OWORD *)(a3 + 16);
    v34[2] = *(_OWORD *)(a3 + 32);
    v34[3] = *(_OWORD *)(a3 + 48);
    v34[4] = *(_OWORD *)(a3 + 64);
    v35 = *(_QWORD *)(a3 + 80);
    v32 = 13;
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
          v37 = v10;
          v23 = v11;
          v25 = a1;
          v24 = v22[4];
          v20[0] = v22[1];
          v20[1] = v22[2];
          LODWORD(v22) = *v22;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v12,
            (unsigned int)&unk_180165E4D,
            (_DWORD)v12,
            v13,
            (__int64)&v22,
            (__int64)&v20[1],
            (__int64)v20,
            (__int64)&v24,
            (__int64)&v25,
            (__int64)&v23,
            (__int64)&v37);
        }
      }
    }
    else
    {
      v14 = GuestXvmAudioObjectTelemetryProvider::Provider();
      if ( *(_DWORD *)v14 > 4u )
      {
        v37 = v10;
        *(float *)&v22 = v11;
        v25 = a1;
        v20[1] = v21[2];
        v20[0] = *(_DWORD *)(a1 + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v14,
          (unsigned int)&unk_180165D3A,
          (_DWORD)v12,
          v15,
          (__int64)v20,
          (__int64)&v20[1],
          (__int64)&v25,
          (__int64)&v22,
          (__int64)&v37);
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
        SharedModeEngine = XvmMessage::CastTo<XvmGetSharedModeEnginePeriod>(v21, v40, v12);
        v9 = SharedModeEngine;
        if ( SharedModeEngine >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)SharedModeEngine;
        v16 = 141;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
          (const char *)v17,
          v19);
LABEL_24:
        *v38 = v21;
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
0x1800ac760  mov     rax, rsp
0x1800ac763  mov     [rax+10h], rbx
0x1800ac767  mov     [rax+18h], rsi
0x1800ac76b  mov     [rax+20h], r9
0x1800ac76f  push    rbp
0x1800ac770  push    rdi
0x1800ac771  push    r14
0x1800ac773  lea     rbp, [rax-7E8h]
0x1800ac77a  sub     rsp, 8D0h
0x1800ac781  movaps  xmmword ptr [rax-28h], xmm6
0x1800ac785  mov     rsi, r8
0x1800ac788  mov     r14d, edx
0x1800ac78b  mov     rbx, rcx
0x1800ac78e  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800ac796  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800ac79e  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800ac7a2  call    cs:__imp_QueryPerformanceCounter
0x1800ac7a8  mov     edi, [rbx+40h]
0x1800ac7ab  test    edi, edi
0x1800ac7ad  jns     short loc_1800AC7D1
0x1800ac7af  mov     rcx, [rbp+7E8h]; this
0x1800ac7b6  mov     r9d, edi; char *
0x1800ac7b9  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ac7c0  mov     edx, 4Fh ; 'O'; void *
0x1800ac7c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac7ca  mov     eax, edi
0x1800ac7cc  jmp     loc_1800ACAB7
0x1800ac7d1  mov     ecx, 810h; cb
0x1800ac7d6  call    cs:__imp_CoTaskMemAlloc
0x1800ac7dc  mov     rdi, rax
0x1800ac7df  mov     [rsp+8E0h+var_878], rax
0x1800ac7e4  test    rax, rax
0x1800ac7e7  jnz     short loc_1800AC80C
0x1800ac7e9  mov     rcx, [rbp+7E8h]; this
0x1800ac7f0  mov     ebx, 8007000Eh
0x1800ac7f5  mov     r9d, ebx; char *
0x1800ac7f8  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ac7ff  lea     edx, [rax+52h]; void *
0x1800ac802  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac807  jmp     loc_1800ACAB5
0x1800ac80c  mov     [rbp+7E0h+Src], 0
0x1800ac814  mov     [rbp+7E0h+var_824], 0
0x1800ac81b  xor     edx, edx; Val
0x1800ac81d  mov     r8d, 800h; Size
0x1800ac823  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800ac827  call    memset_0
0x1800ac82c  movups  xmm0, xmmword ptr [rsi]
0x1800ac82f  movaps  [rbp+7E0h+var_820], xmm0
0x1800ac833  movups  xmm1, xmmword ptr [rsi+10h]
0x1800ac837  movaps  [rbp+7E0h+var_810], xmm1
0x1800ac83b  movups  xmm0, xmmword ptr [rsi+20h]
0x1800ac83f  movaps  [rbp+7E0h+var_800], xmm0
0x1800ac843  movups  xmm1, xmmword ptr [rsi+30h]
0x1800ac847  movaps  [rbp+7E0h+var_7F0], xmm1
0x1800ac84b  movups  xmm0, xmmword ptr [rsi+40h]
0x1800ac84f  movaps  [rbp+7E0h+var_7E0], xmm0
0x1800ac853  movsd   xmm1, qword ptr [rsi+50h]
0x1800ac858  movsd   [rbp+7E0h+var_7D0], xmm1
0x1800ac85d  mov     [rbp+7E0h+var_828], 0Dh
0x1800ac864  mov     rcx, rdi; void *
0x1800ac867  lea     rdx, [rbp+7E0h+Src]; Src
0x1800ac86b  mov     r8d, 810h; Size
0x1800ac871  call    memcpy_0
0x1800ac876  mov     rax, [rsp+8E0h+var_878]
0x1800ac87b  mov     [rax+0Ch], r14d
0x1800ac87f  lea     rax, [rbp+7E0h+arg_18]
0x1800ac886  mov     [rbp+7E0h+var_848], rax
0x1800ac88a  lea     rax, [rsp+8E0h+var_878]
0x1800ac88f  mov     [rbp+7E0h+var_840], rax
0x1800ac893  mov     [rbp+7E0h+var_838], 1
0x1800ac897  mov     rcx, [rbx+28h]
0x1800ac89b  mov     rax, [rcx]
0x1800ac89e  mov     r9d, 810h
0x1800ac8a4  mov     r8, [rsp+8E0h+var_878]
0x1800ac8a9  mov     edx, r14d
0x1800ac8ac  mov     rax, [rax+20h]
0x1800ac8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac8b5  mov     edi, eax
0x1800ac8b7  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800ac8bb  call    cs:__imp_QueryPerformanceCounter
0x1800ac8c1  xorps   xmm6, xmm6
0x1800ac8c4  cmp     qword ptr [rbx+48h], 0
0x1800ac8c9  jz      short loc_1800AC8ED
0x1800ac8cb  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800ac8cf  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800ac8d3  cvtsi2ss xmm6, rcx
0x1800ac8d8  mulss   xmm6, cs:__real@447a0000
0x1800ac8e0  xorps   xmm0, xmm0
0x1800ac8e3  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800ac8e9  divss   xmm6, xmm0
0x1800ac8ed  mov     rcx, [rsp+8E0h+var_878]
0x1800ac8f2  cmp     dword ptr [rcx+8], 1
0x1800ac8f6  jnz     loc_1800AC9B2
0x1800ac8fc  mov     [rsp+8E0h+var_870], 0
0x1800ac905  lea     rdx, [rsp+8E0h+var_870]
0x1800ac90a  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800ac90f  test    eax, eax
0x1800ac911  js      loc_1800ACA23
0x1800ac917  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ac91c  mov     r8, rax
0x1800ac91f  mov     ecx, [rax]
0x1800ac921  cmp     ecx, 4
0x1800ac924  jbe     loc_1800ACA23
0x1800ac92a  mov     [rbp+7E0h+arg_0], edi
0x1800ac930  movss   [rsp+8E0h+var_868], xmm6
0x1800ac936  mov     [rbp+7E0h+var_860], rbx
0x1800ac93a  mov     rdx, [rsp+8E0h+var_870]
0x1800ac93f  mov     ecx, [rdx+10h]
0x1800ac942  mov     [rsp+8E0h+var_864], ecx
0x1800ac946  mov     ecx, [rdx+4]
0x1800ac949  mov     [rsp+8E0h+var_880], ecx
0x1800ac94d  mov     eax, [rdx+8]
0x1800ac950  mov     [rsp+8E0h+var_880+4], eax
0x1800ac954  mov     eax, [rdx]
0x1800ac956  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800ac95a  lea     rax, [rbp+7E0h+arg_0]
0x1800ac961  mov     [rsp+8E0h+var_890], rax
0x1800ac966  lea     rax, [rsp+8E0h+var_868]
0x1800ac96b  mov     [rsp+8E0h+var_898], rax
0x1800ac970  lea     rax, [rbp+7E0h+var_860]
0x1800ac974  mov     [rsp+8E0h+var_8A0], rax
0x1800ac979  lea     rax, [rsp+8E0h+var_864]
0x1800ac97e  mov     [rsp+8E0h+var_8A8], rax
0x1800ac983  lea     rax, [rsp+8E0h+var_880]
0x1800ac988  mov     [rsp+8E0h+var_8B0], rax
0x1800ac98d  lea     rax, [rsp+8E0h+var_880+4]
0x1800ac992  mov     [rsp+8E0h+var_8B8], rax
0x1800ac997  lea     rax, [rsp+8E0h+var_870]
0x1800ac99c  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800ac9a1  lea     rdx, unk_180165E4D
0x1800ac9a8  mov     rcx, r8
0x1800ac9ab  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ac9b0  jmp     short loc_1800ACA23
0x1800ac9b2  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ac9b7  mov     ecx, [rax]
0x1800ac9b9  cmp     ecx, 4
0x1800ac9bc  jbe     short loc_1800ACA23
0x1800ac9be  mov     [rbp+7E0h+arg_0], edi
0x1800ac9c4  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800ac9ca  mov     [rbp+7E0h+var_860], rbx
0x1800ac9ce  mov     rcx, [rsp+8E0h+var_878]
0x1800ac9d3  mov     edx, [rcx+8]
0x1800ac9d6  mov     [rsp+8E0h+var_880+4], edx
0x1800ac9da  mov     ecx, [rbx+30h]
0x1800ac9dd  mov     [rsp+8E0h+var_880], ecx
0x1800ac9e1  lea     rcx, [rbp+7E0h+arg_0]
0x1800ac9e8  mov     [rsp+8E0h+var_8A0], rcx
0x1800ac9ed  lea     rcx, [rsp+8E0h+var_870]
0x1800ac9f2  mov     [rsp+8E0h+var_8A8], rcx
0x1800ac9f7  lea     rcx, [rbp+7E0h+var_860]
0x1800ac9fb  mov     [rsp+8E0h+var_8B0], rcx
0x1800aca00  lea     rcx, [rsp+8E0h+var_880+4]
0x1800aca05  mov     [rsp+8E0h+var_8B8], rcx
0x1800aca0a  lea     rcx, [rsp+8E0h+var_880]
0x1800aca0f  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800aca14  lea     rdx, unk_180165D3A
0x1800aca1b  mov     rcx, rax
0x1800aca1e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800aca23  mov     rcx, [rbp+7E8h]; this
0x1800aca2a  test    edi, edi
0x1800aca2c  jns     short loc_1800ACA51
0x1800aca2e  mov     r9d, edi; char *
0x1800aca31  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800aca38  mov     edx, 81h; void *
0x1800aca3d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aca42  mov     rax, [rbx]
0x1800aca45  mov     rcx, rbx
0x1800aca48  mov     rax, [rax+20h]
0x1800aca4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aca51  mov     ebx, [rbx+40h]
0x1800aca54  test    ebx, ebx
0x1800aca56  jns     short loc_1800ACA5F
0x1800aca58  mov     edx, 8Ah
0x1800aca5d  jmp     short loc_1800ACA70
0x1800aca5f  mov     rcx, [rsp+8E0h+var_878]
0x1800aca64  mov     ebx, [rcx+4]
0x1800aca67  test    ebx, ebx
0x1800aca69  jns     short loc_1800ACA88
0x1800aca6b  mov     edx, 8Ch; void *
0x1800aca70  mov     r9d, ebx; char *
0x1800aca73  mov     rcx, [rbp+7E8h]; this
0x1800aca7a  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800aca81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aca86  jmp     short loc_1800ACAA6
0x1800aca88  mov     rdx, [rbp+7E0h+arg_20]
0x1800aca8f  call    ??$CastTo@UXvmGetSharedModeEnginePeriod@@@XvmMessage@@QEAAJPEAPEAUXvmGetSharedModeEnginePeriod@@@Z; XvmMessage::CastTo<XvmGetSharedModeEnginePeriod>(XvmGetSharedModeEnginePeriod * *)
0x1800aca94  mov     ebx, eax
0x1800aca96  test    eax, eax
0x1800aca98  jns     short loc_1800ACAA4
0x1800aca9a  mov     r9d, eax
0x1800aca9d  mov     edx, 8Dh
0x1800acaa2  jmp     short loc_1800ACA73
0x1800acaa4  xor     ebx, ebx
0x1800acaa6  mov     rcx, [rbp+7E0h+arg_18]
0x1800acaad  mov     rax, [rsp+8E0h+var_878]
0x1800acab2  mov     [rcx], rax
0x1800acab5  mov     eax, ebx
0x1800acab7  lea     r11, [rsp+8E0h+var_10]
0x1800acabf  mov     rbx, [r11+28h]
0x1800acac3  mov     rsi, [r11+30h]
0x1800acac7  movaps  xmm6, xmmword ptr [r11-10h]
0x1800acacc  mov     rsp, r11
0x1800acacf  pop     r14
0x1800acad1  pop     rdi
0x1800acad2  pop     rbp
0x1800acad3  retn
```
