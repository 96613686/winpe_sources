# CGuestXvmAudioObject::SendAndValidateResponse<XvmIsFormatSupported>(uint,XvmIsFormatSupported,XvmMessage * *,XvmIsFormatSupported * *)

- ea: `0x1800ad4dc`
- end: `0x1800ad874`
- name: `??$SendAndValidateResponse@UXvmIsFormatSupported@@@CGuestXvmAudioObject@@QEAAJIUXvmIsFormatSupported@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `920`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b0aa0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2c68`
- `0x1800ad4dc`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad51e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad65b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad51e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad65b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ad552`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ad552`

## string_xrefs

- `0x1800ad535`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ad574`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ad7d1`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ad81a`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmIsFormatSupported>(
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
  int IsFormat; // eax
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
  _OWORD v34[8]; // [rsp+C8h] [rbp-40h] BYREF
  _OWORD v35[121]; // [rsp+148h] [rbp+40h]
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
    v34[5] = *(_OWORD *)(a3 + 80);
    v34[6] = *(_OWORD *)(a3 + 96);
    v34[7] = *(_OWORD *)(a3 + 112);
    v35[0] = *(_OWORD *)(a3 + 128);
    *(_QWORD *)((char *)v35 + 14) = *(_QWORD *)(a3 + 142);
    v32 = 5;
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
            (unsigned int)word_180166682,
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
          (unsigned int)&dword_1801665BC,
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
        IsFormat = XvmMessage::CastTo<XvmIsFormatSupported>(v21, v40, v12);
        v9 = IsFormat;
        if ( IsFormat >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)IsFormat;
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
0x1800ad4dc  mov     rax, rsp
0x1800ad4df  mov     [rax+10h], rbx
0x1800ad4e3  mov     [rax+18h], rsi
0x1800ad4e7  mov     [rax+20h], r9
0x1800ad4eb  push    rbp
0x1800ad4ec  push    rdi
0x1800ad4ed  push    r14
0x1800ad4ef  lea     rbp, [rax-7E8h]
0x1800ad4f6  sub     rsp, 8D0h
0x1800ad4fd  movaps  xmmword ptr [rax-28h], xmm6
0x1800ad501  mov     rsi, r8
0x1800ad504  mov     r14d, edx
0x1800ad507  mov     rbx, rcx
0x1800ad50a  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800ad512  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800ad51a  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800ad51e  call    cs:__imp_QueryPerformanceCounter
0x1800ad524  mov     edi, [rbx+40h]
0x1800ad527  test    edi, edi
0x1800ad529  jns     short loc_1800AD54D
0x1800ad52b  mov     rcx, [rbp+7E8h]; this
0x1800ad532  mov     r9d, edi; char *
0x1800ad535  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ad53c  mov     edx, 4Fh ; 'O'; void *
0x1800ad541  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad546  mov     eax, edi
0x1800ad548  jmp     loc_1800AD857
0x1800ad54d  mov     ecx, 810h; cb
0x1800ad552  call    cs:__imp_CoTaskMemAlloc
0x1800ad558  mov     rdi, rax
0x1800ad55b  mov     [rsp+8E0h+var_878], rax
0x1800ad560  test    rax, rax
0x1800ad563  jnz     short loc_1800AD588
0x1800ad565  mov     rcx, [rbp+7E8h]; this
0x1800ad56c  mov     ebx, 8007000Eh
0x1800ad571  mov     r9d, ebx; char *
0x1800ad574  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ad57b  lea     edx, [rax+52h]; void *
0x1800ad57e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad583  jmp     loc_1800AD855
0x1800ad588  mov     [rbp+7E0h+Src], 0
0x1800ad590  mov     [rbp+7E0h+var_824], 0
0x1800ad597  xor     edx, edx; Val
0x1800ad599  mov     r8d, 800h; Size
0x1800ad59f  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800ad5a3  call    memset_0
0x1800ad5a8  movups  xmm0, xmmword ptr [rsi]
0x1800ad5ab  movups  [rbp+7E0h+var_820], xmm0
0x1800ad5af  movups  xmm1, xmmword ptr [rsi+10h]
0x1800ad5b3  movups  [rbp+7E0h+var_810], xmm1
0x1800ad5b7  movups  xmm0, xmmword ptr [rsi+20h]
0x1800ad5bb  movups  [rbp+7E0h+var_800], xmm0
0x1800ad5bf  movups  xmm1, xmmword ptr [rsi+30h]
0x1800ad5c3  movups  [rbp+7E0h+var_7F0], xmm1
0x1800ad5c7  movups  xmm0, xmmword ptr [rsi+40h]
0x1800ad5cb  movups  [rbp+7E0h+var_7E0], xmm0
0x1800ad5cf  movups  xmm1, xmmword ptr [rsi+50h]
0x1800ad5d3  movups  [rbp+7E0h+var_7D0], xmm1
0x1800ad5d7  movups  xmm0, xmmword ptr [rsi+60h]
0x1800ad5db  movups  [rbp+7E0h+var_7C0], xmm0
0x1800ad5df  movups  xmm1, xmmword ptr [rsi+70h]
0x1800ad5e3  movups  [rbp+7E0h+var_7B0], xmm1
0x1800ad5e7  movups  xmm0, xmmword ptr [rsi+80h]
0x1800ad5ee  movups  [rbp+7E0h+var_7A0], xmm0
0x1800ad5f2  mov     rax, [rsi+8Eh]
0x1800ad5f9  mov     qword ptr [rbp+7E0h+var_7A0+0Eh], rax
0x1800ad5fd  mov     [rbp+7E0h+var_828], 5
0x1800ad604  mov     rcx, rdi; void *
0x1800ad607  lea     rdx, [rbp+7E0h+Src]; Src
0x1800ad60b  mov     r8d, 810h; Size
0x1800ad611  call    memcpy_0
0x1800ad616  mov     rax, [rsp+8E0h+var_878]
0x1800ad61b  mov     [rax+0Ch], r14d
0x1800ad61f  lea     rax, [rbp+7E0h+arg_18]
0x1800ad626  mov     [rbp+7E0h+var_848], rax
0x1800ad62a  lea     rax, [rsp+8E0h+var_878]
0x1800ad62f  mov     [rbp+7E0h+var_840], rax
0x1800ad633  mov     [rbp+7E0h+var_838], 1
0x1800ad637  mov     rcx, [rbx+28h]
0x1800ad63b  mov     rax, [rcx]
0x1800ad63e  mov     r9d, 810h
0x1800ad644  mov     r8, [rsp+8E0h+var_878]
0x1800ad649  mov     edx, r14d
0x1800ad64c  mov     rax, [rax+20h]
0x1800ad650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad655  mov     edi, eax
0x1800ad657  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800ad65b  call    cs:__imp_QueryPerformanceCounter
0x1800ad661  xorps   xmm6, xmm6
0x1800ad664  cmp     qword ptr [rbx+48h], 0
0x1800ad669  jz      short loc_1800AD68D
0x1800ad66b  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800ad66f  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800ad673  cvtsi2ss xmm6, rcx
0x1800ad678  mulss   xmm6, cs:__real@447a0000
0x1800ad680  xorps   xmm0, xmm0
0x1800ad683  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800ad689  divss   xmm6, xmm0
0x1800ad68d  mov     rcx, [rsp+8E0h+var_878]
0x1800ad692  cmp     dword ptr [rcx+8], 1
0x1800ad696  jnz     loc_1800AD752
0x1800ad69c  mov     [rsp+8E0h+var_870], 0
0x1800ad6a5  lea     rdx, [rsp+8E0h+var_870]
0x1800ad6aa  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800ad6af  test    eax, eax
0x1800ad6b1  js      loc_1800AD7C3
0x1800ad6b7  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ad6bc  mov     r8, rax
0x1800ad6bf  mov     ecx, [rax]
0x1800ad6c1  cmp     ecx, 4
0x1800ad6c4  jbe     loc_1800AD7C3
0x1800ad6ca  mov     [rbp+7E0h+arg_0], edi
0x1800ad6d0  movss   [rsp+8E0h+var_868], xmm6
0x1800ad6d6  mov     [rbp+7E0h+var_860], rbx
0x1800ad6da  mov     rdx, [rsp+8E0h+var_870]
0x1800ad6df  mov     ecx, [rdx+10h]
0x1800ad6e2  mov     [rsp+8E0h+var_864], ecx
0x1800ad6e6  mov     ecx, [rdx+4]
0x1800ad6e9  mov     [rsp+8E0h+var_880], ecx
0x1800ad6ed  mov     eax, [rdx+8]
0x1800ad6f0  mov     [rsp+8E0h+var_880+4], eax
0x1800ad6f4  mov     eax, [rdx]
0x1800ad6f6  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800ad6fa  lea     rax, [rbp+7E0h+arg_0]
0x1800ad701  mov     [rsp+8E0h+var_890], rax
0x1800ad706  lea     rax, [rsp+8E0h+var_868]
0x1800ad70b  mov     [rsp+8E0h+var_898], rax
0x1800ad710  lea     rax, [rbp+7E0h+var_860]
0x1800ad714  mov     [rsp+8E0h+var_8A0], rax
0x1800ad719  lea     rax, [rsp+8E0h+var_864]
0x1800ad71e  mov     [rsp+8E0h+var_8A8], rax
0x1800ad723  lea     rax, [rsp+8E0h+var_880]
0x1800ad728  mov     [rsp+8E0h+var_8B0], rax
0x1800ad72d  lea     rax, [rsp+8E0h+var_880+4]
0x1800ad732  mov     [rsp+8E0h+var_8B8], rax
0x1800ad737  lea     rax, [rsp+8E0h+var_870]
0x1800ad73c  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800ad741  lea     rdx, word_180166682
0x1800ad748  mov     rcx, r8
0x1800ad74b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ad750  jmp     short loc_1800AD7C3
0x1800ad752  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ad757  mov     ecx, [rax]
0x1800ad759  cmp     ecx, 4
0x1800ad75c  jbe     short loc_1800AD7C3
0x1800ad75e  mov     [rbp+7E0h+arg_0], edi
0x1800ad764  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800ad76a  mov     [rbp+7E0h+var_860], rbx
0x1800ad76e  mov     rcx, [rsp+8E0h+var_878]
0x1800ad773  mov     edx, [rcx+8]
0x1800ad776  mov     [rsp+8E0h+var_880+4], edx
0x1800ad77a  mov     ecx, [rbx+30h]
0x1800ad77d  mov     [rsp+8E0h+var_880], ecx
0x1800ad781  lea     rcx, [rbp+7E0h+arg_0]
0x1800ad788  mov     [rsp+8E0h+var_8A0], rcx
0x1800ad78d  lea     rcx, [rsp+8E0h+var_870]
0x1800ad792  mov     [rsp+8E0h+var_8A8], rcx
0x1800ad797  lea     rcx, [rbp+7E0h+var_860]
0x1800ad79b  mov     [rsp+8E0h+var_8B0], rcx
0x1800ad7a0  lea     rcx, [rsp+8E0h+var_880+4]
0x1800ad7a5  mov     [rsp+8E0h+var_8B8], rcx
0x1800ad7aa  lea     rcx, [rsp+8E0h+var_880]
0x1800ad7af  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800ad7b4  lea     rdx, dword_1801665BC
0x1800ad7bb  mov     rcx, rax
0x1800ad7be  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ad7c3  mov     rcx, [rbp+7E8h]; this
0x1800ad7ca  test    edi, edi
0x1800ad7cc  jns     short loc_1800AD7F1
0x1800ad7ce  mov     r9d, edi; char *
0x1800ad7d1  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ad7d8  mov     edx, 81h; void *
0x1800ad7dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ad7e2  mov     rax, [rbx]
0x1800ad7e5  mov     rcx, rbx
0x1800ad7e8  mov     rax, [rax+20h]
0x1800ad7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad7f1  mov     ebx, [rbx+40h]
0x1800ad7f4  test    ebx, ebx
0x1800ad7f6  jns     short loc_1800AD7FF
0x1800ad7f8  mov     edx, 8Ah
0x1800ad7fd  jmp     short loc_1800AD810
0x1800ad7ff  mov     rcx, [rsp+8E0h+var_878]
0x1800ad804  mov     ebx, [rcx+4]
0x1800ad807  test    ebx, ebx
0x1800ad809  jns     short loc_1800AD828
0x1800ad80b  mov     edx, 8Ch; void *
0x1800ad810  mov     r9d, ebx; char *
0x1800ad813  mov     rcx, [rbp+7E8h]; this
0x1800ad81a  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ad821  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad826  jmp     short loc_1800AD846
0x1800ad828  mov     rdx, [rbp+7E0h+arg_20]
0x1800ad82f  call    ??$CastTo@UXvmIsFormatSupported@@@XvmMessage@@QEAAJPEAPEAUXvmIsFormatSupported@@@Z; XvmMessage::CastTo<XvmIsFormatSupported>(XvmIsFormatSupported * *)
0x1800ad834  mov     ebx, eax
0x1800ad836  test    eax, eax
0x1800ad838  jns     short loc_1800AD844
0x1800ad83a  mov     r9d, eax
0x1800ad83d  mov     edx, 8Dh
0x1800ad842  jmp     short loc_1800AD813
0x1800ad844  xor     ebx, ebx
0x1800ad846  mov     rcx, [rbp+7E0h+arg_18]
0x1800ad84d  mov     rax, [rsp+8E0h+var_878]
0x1800ad852  mov     [rcx], rax
0x1800ad855  mov     eax, ebx
0x1800ad857  lea     r11, [rsp+8E0h+var_10]
0x1800ad85f  mov     rbx, [r11+28h]
0x1800ad863  mov     rsi, [r11+30h]
0x1800ad867  movaps  xmm6, xmmword ptr [r11-10h]
0x1800ad86c  mov     rsp, r11
0x1800ad86f  pop     r14
0x1800ad871  pop     rdi
0x1800ad872  pop     rbp
0x1800ad873  retn
```
