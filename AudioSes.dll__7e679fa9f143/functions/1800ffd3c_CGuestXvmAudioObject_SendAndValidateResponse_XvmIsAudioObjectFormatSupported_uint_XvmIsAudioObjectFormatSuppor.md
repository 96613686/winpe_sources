# CGuestXvmAudioObject::SendAndValidateResponse<XvmIsAudioObjectFormatSupported>(uint,XvmIsAudioObjectFormatSupported,XvmMessage * *,XvmIsAudioObjectFormatSupported * *)

- ea: `0x1800ffd3c`
- end: `0x1801000a8`
- name: `??$SendAndValidateResponse@UXvmIsAudioObjectFormatSupported@@@CGuestXvmAudioObject@@QEAAJIUXvmIsAudioObjectFormatSupported@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `876`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180101990`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800fa244`
- `0x1800ffd3c`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ffd7e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ffe8f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ffd7e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ffe8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ffdb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ffdb2`

## string_xrefs

- `0x1800ffd95`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ffdd4`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x180100005`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18010004e`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmIsAudioObjectFormatSupported>(
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
  int IsAudioObjectFormat; // eax
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
  _OWORD v34[4]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v35; // [rsp+108h] [rbp+0h]
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
    v35 = *(_QWORD *)(a3 + 64);
    v32 = 52;
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
            (unsigned int)&unk_1801710C9,
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
          (unsigned int)&unk_18017107C,
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
        IsAudioObjectFormat = XvmMessage::CastTo<XvmIsAudioObjectFormatSupported>(v21, v40, v12);
        v9 = IsAudioObjectFormat;
        if ( IsAudioObjectFormat >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)IsAudioObjectFormat;
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
0x1800ffd3c  mov     rax, rsp
0x1800ffd3f  mov     [rax+10h], rbx
0x1800ffd43  mov     [rax+18h], rsi
0x1800ffd47  mov     [rax+20h], r9
0x1800ffd4b  push    rbp
0x1800ffd4c  push    rdi
0x1800ffd4d  push    r14
0x1800ffd4f  lea     rbp, [rax-7E8h]
0x1800ffd56  sub     rsp, 8D0h
0x1800ffd5d  movaps  xmmword ptr [rax-28h], xmm6
0x1800ffd61  mov     rsi, r8
0x1800ffd64  mov     r14d, edx
0x1800ffd67  mov     rbx, rcx
0x1800ffd6a  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800ffd72  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800ffd7a  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800ffd7e  call    cs:__imp_QueryPerformanceCounter
0x1800ffd84  mov     edi, [rbx+40h]
0x1800ffd87  test    edi, edi
0x1800ffd89  jns     short loc_1800FFDAD
0x1800ffd8b  mov     rcx, [rbp+7E8h]; this
0x1800ffd92  mov     r9d, edi; char *
0x1800ffd95  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ffd9c  mov     edx, 4Fh ; 'O'; void *
0x1800ffda1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ffda6  mov     eax, edi
0x1800ffda8  jmp     loc_18010008B
0x1800ffdad  mov     ecx, 810h; cb
0x1800ffdb2  call    cs:__imp_CoTaskMemAlloc
0x1800ffdb8  mov     rdi, rax
0x1800ffdbb  mov     [rsp+8E0h+var_878], rax
0x1800ffdc0  test    rax, rax
0x1800ffdc3  jnz     short loc_1800FFDE8
0x1800ffdc5  mov     rcx, [rbp+7E8h]; this
0x1800ffdcc  mov     ebx, 8007000Eh
0x1800ffdd1  mov     r9d, ebx; char *
0x1800ffdd4  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ffddb  lea     edx, [rax+52h]; void *
0x1800ffdde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ffde3  jmp     loc_180100089
0x1800ffde8  mov     [rbp+7E0h+Src], 0
0x1800ffdf0  mov     [rbp+7E0h+var_824], 0
0x1800ffdf7  xor     edx, edx; Val
0x1800ffdf9  mov     r8d, 800h; Size
0x1800ffdff  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800ffe03  call    memset_0
0x1800ffe08  movups  xmm0, xmmword ptr [rsi]
0x1800ffe0b  movaps  [rbp+7E0h+var_820], xmm0
0x1800ffe0f  movups  xmm1, xmmword ptr [rsi+10h]
0x1800ffe13  movaps  [rbp+7E0h+var_810], xmm1
0x1800ffe17  movups  xmm0, xmmword ptr [rsi+20h]
0x1800ffe1b  movaps  [rbp+7E0h+var_800], xmm0
0x1800ffe1f  movups  xmm1, xmmword ptr [rsi+30h]
0x1800ffe23  movaps  [rbp+7E0h+var_7F0], xmm1
0x1800ffe27  movsd   xmm0, qword ptr [rsi+40h]
0x1800ffe2c  movsd   [rbp+7E0h+var_7E0], xmm0
0x1800ffe31  mov     [rbp+7E0h+var_828], 34h ; '4'
0x1800ffe38  mov     rcx, rdi; void *
0x1800ffe3b  lea     rdx, [rbp+7E0h+Src]; Src
0x1800ffe3f  mov     r8d, 810h; Size
0x1800ffe45  call    memcpy_0
0x1800ffe4a  mov     rax, [rsp+8E0h+var_878]
0x1800ffe4f  mov     [rax+0Ch], r14d
0x1800ffe53  lea     rax, [rbp+7E0h+arg_18]
0x1800ffe5a  mov     [rbp+7E0h+var_848], rax
0x1800ffe5e  lea     rax, [rsp+8E0h+var_878]
0x1800ffe63  mov     [rbp+7E0h+var_840], rax
0x1800ffe67  mov     [rbp+7E0h+var_838], 1
0x1800ffe6b  mov     rcx, [rbx+28h]
0x1800ffe6f  mov     rax, [rcx]
0x1800ffe72  mov     r9d, 810h
0x1800ffe78  mov     r8, [rsp+8E0h+var_878]
0x1800ffe7d  mov     edx, r14d
0x1800ffe80  mov     rax, [rax+20h]
0x1800ffe84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffe89  mov     edi, eax
0x1800ffe8b  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800ffe8f  call    cs:__imp_QueryPerformanceCounter
0x1800ffe95  xorps   xmm6, xmm6
0x1800ffe98  cmp     qword ptr [rbx+48h], 0
0x1800ffe9d  jz      short loc_1800FFEC1
0x1800ffe9f  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800ffea3  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800ffea7  cvtsi2ss xmm6, rcx
0x1800ffeac  mulss   xmm6, cs:__real@447a0000
0x1800ffeb4  xorps   xmm0, xmm0
0x1800ffeb7  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800ffebd  divss   xmm6, xmm0
0x1800ffec1  mov     rcx, [rsp+8E0h+var_878]
0x1800ffec6  cmp     dword ptr [rcx+8], 1
0x1800ffeca  jnz     loc_1800FFF86
0x1800ffed0  mov     [rsp+8E0h+var_870], 0
0x1800ffed9  lea     rdx, [rsp+8E0h+var_870]
0x1800ffede  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800ffee3  test    eax, eax
0x1800ffee5  js      loc_1800FFFF7
0x1800ffeeb  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ffef0  mov     r8, rax
0x1800ffef3  mov     ecx, [rax]
0x1800ffef5  cmp     ecx, 4
0x1800ffef8  jbe     loc_1800FFFF7
0x1800ffefe  mov     [rbp+7E0h+arg_0], edi
0x1800fff04  movss   [rsp+8E0h+var_868], xmm6
0x1800fff0a  mov     [rbp+7E0h+var_860], rbx
0x1800fff0e  mov     rdx, [rsp+8E0h+var_870]
0x1800fff13  mov     ecx, [rdx+10h]
0x1800fff16  mov     [rsp+8E0h+var_864], ecx
0x1800fff1a  mov     ecx, [rdx+4]
0x1800fff1d  mov     [rsp+8E0h+var_880], ecx
0x1800fff21  mov     eax, [rdx+8]
0x1800fff24  mov     [rsp+8E0h+var_880+4], eax
0x1800fff28  mov     eax, [rdx]
0x1800fff2a  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800fff2e  lea     rax, [rbp+7E0h+arg_0]
0x1800fff35  mov     [rsp+8E0h+var_890], rax
0x1800fff3a  lea     rax, [rsp+8E0h+var_868]
0x1800fff3f  mov     [rsp+8E0h+var_898], rax
0x1800fff44  lea     rax, [rbp+7E0h+var_860]
0x1800fff48  mov     [rsp+8E0h+var_8A0], rax
0x1800fff4d  lea     rax, [rsp+8E0h+var_864]
0x1800fff52  mov     [rsp+8E0h+var_8A8], rax
0x1800fff57  lea     rax, [rsp+8E0h+var_880]
0x1800fff5c  mov     [rsp+8E0h+var_8B0], rax
0x1800fff61  lea     rax, [rsp+8E0h+var_880+4]
0x1800fff66  mov     [rsp+8E0h+var_8B8], rax
0x1800fff6b  lea     rax, [rsp+8E0h+var_870]
0x1800fff70  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800fff75  lea     rdx, unk_1801710C9
0x1800fff7c  mov     rcx, r8
0x1800fff7f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800fff84  jmp     short loc_1800FFFF7
0x1800fff86  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800fff8b  mov     ecx, [rax]
0x1800fff8d  cmp     ecx, 4
0x1800fff90  jbe     short loc_1800FFFF7
0x1800fff92  mov     [rbp+7E0h+arg_0], edi
0x1800fff98  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800fff9e  mov     [rbp+7E0h+var_860], rbx
0x1800fffa2  mov     rcx, [rsp+8E0h+var_878]
0x1800fffa7  mov     edx, [rcx+8]
0x1800fffaa  mov     [rsp+8E0h+var_880+4], edx
0x1800fffae  mov     ecx, [rbx+30h]
0x1800fffb1  mov     [rsp+8E0h+var_880], ecx
0x1800fffb5  lea     rcx, [rbp+7E0h+arg_0]
0x1800fffbc  mov     [rsp+8E0h+var_8A0], rcx
0x1800fffc1  lea     rcx, [rsp+8E0h+var_870]
0x1800fffc6  mov     [rsp+8E0h+var_8A8], rcx
0x1800fffcb  lea     rcx, [rbp+7E0h+var_860]
0x1800fffcf  mov     [rsp+8E0h+var_8B0], rcx
0x1800fffd4  lea     rcx, [rsp+8E0h+var_880+4]
0x1800fffd9  mov     [rsp+8E0h+var_8B8], rcx
0x1800fffde  lea     rcx, [rsp+8E0h+var_880]
0x1800fffe3  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800fffe8  lea     rdx, unk_18017107C
0x1800fffef  mov     rcx, rax
0x1800ffff2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ffff7  mov     rcx, [rbp+7E8h]; this
0x1800ffffe  test    edi, edi
0x180100000  jns     short loc_180100025
0x180100002  mov     r9d, edi; char *
0x180100005  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010000c  mov     edx, 81h; void *
0x180100011  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180100016  mov     rax, [rbx]
0x180100019  mov     rcx, rbx
0x18010001c  mov     rax, [rax+20h]
0x180100020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100025  mov     ebx, [rbx+40h]
0x180100028  test    ebx, ebx
0x18010002a  jns     short loc_180100033
0x18010002c  mov     edx, 8Ah
0x180100031  jmp     short loc_180100044
0x180100033  mov     rcx, [rsp+8E0h+var_878]
0x180100038  mov     ebx, [rcx+4]
0x18010003b  test    ebx, ebx
0x18010003d  jns     short loc_18010005C
0x18010003f  mov     edx, 8Ch; void *
0x180100044  mov     r9d, ebx; char *
0x180100047  mov     rcx, [rbp+7E8h]; this
0x18010004e  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180100055  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010005a  jmp     short loc_18010007A
0x18010005c  mov     rdx, [rbp+7E0h+arg_20]
0x180100063  call    ??$CastTo@UXvmIsAudioObjectFormatSupported@@@XvmMessage@@QEAAJPEAPEAUXvmIsAudioObjectFormatSupported@@@Z; XvmMessage::CastTo<XvmIsAudioObjectFormatSupported>(XvmIsAudioObjectFormatSupported * *)
0x180100068  mov     ebx, eax
0x18010006a  test    eax, eax
0x18010006c  jns     short loc_180100078
0x18010006e  mov     r9d, eax
0x180100071  mov     edx, 8Dh
0x180100076  jmp     short loc_180100047
0x180100078  xor     ebx, ebx
0x18010007a  mov     rcx, [rbp+7E0h+arg_18]
0x180100081  mov     rax, [rsp+8E0h+var_878]
0x180100086  mov     [rcx], rax
0x180100089  mov     eax, ebx
0x18010008b  lea     r11, [rsp+8E0h+var_10]
0x180100093  mov     rbx, [r11+28h]
0x180100097  mov     rsi, [r11+30h]
0x18010009b  movaps  xmm6, xmmword ptr [r11-10h]
0x1801000a0  mov     rsp, r11
0x1801000a3  pop     r14
0x1801000a5  pop     rdi
0x1801000a6  pop     rbp
0x1801000a7  retn
```
