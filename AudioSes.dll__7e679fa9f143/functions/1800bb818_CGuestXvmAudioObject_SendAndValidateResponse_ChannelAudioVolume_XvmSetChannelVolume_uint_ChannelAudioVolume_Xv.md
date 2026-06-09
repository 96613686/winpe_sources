# CGuestXvmAudioObject::SendAndValidateResponse<ChannelAudioVolume_XvmSetChannelVolume>(uint,ChannelAudioVolume_XvmSetChannelVolume,XvmMessage * *,ChannelAudioVolume_XvmSetChannelVolume * *)

- ea: `0x1800bb818`
- end: `0x1800bbb6b`
- name: `??$SendAndValidateResponse@UChannelAudioVolume_XvmSetChannelVolume@@@CGuestXvmAudioObject@@QEAAJIUChannelAudioVolume_XvmSetChannelVolume@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `851`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c1fb0`
- `0x1800c2140`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2730`
- `0x1800bb818`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bb85a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bb952`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bb85a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bb952`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb88e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb88e`

## string_xrefs

- `0x1800bb871`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bb8b0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bbac8`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bbb11`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<ChannelAudioVolume_XvmSetChannelVolume>(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
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
  __int64 v34; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v35; // [rsp+D0h] [rbp-38h]
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
    memset_0(&v34, 0, 0x800u);
    v34 = *a3;
    v35 = *(_OWORD *)(a3 + 1);
    v32 = 115;
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
            (unsigned int)&unk_180167D9C,
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
          (unsigned int)&unk_180167E15,
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
        v18 = XvmMessage::CastTo<ChannelAudioVolume_XvmSetChannelVolume>(v21, v40, v12);
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
0x1800bb818  mov     rax, rsp
0x1800bb81b  mov     [rax+10h], rbx
0x1800bb81f  mov     [rax+18h], rsi
0x1800bb823  mov     [rax+20h], r9
0x1800bb827  push    rbp
0x1800bb828  push    rdi
0x1800bb829  push    r14
0x1800bb82b  lea     rbp, [rax-7E8h]
0x1800bb832  sub     rsp, 8D0h
0x1800bb839  movaps  xmmword ptr [rax-28h], xmm6
0x1800bb83d  mov     rsi, r8
0x1800bb840  mov     r14d, edx
0x1800bb843  mov     rbx, rcx
0x1800bb846  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bb84e  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800bb856  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800bb85a  call    cs:__imp_QueryPerformanceCounter
0x1800bb860  mov     edi, [rbx+40h]
0x1800bb863  test    edi, edi
0x1800bb865  jns     short loc_1800BB889
0x1800bb867  mov     rcx, [rbp+7E8h]; this
0x1800bb86e  mov     r9d, edi; char *
0x1800bb871  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bb878  mov     edx, 4Fh ; 'O'; void *
0x1800bb87d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb882  mov     eax, edi
0x1800bb884  jmp     loc_1800BBB4E
0x1800bb889  mov     ecx, 810h; cb
0x1800bb88e  call    cs:__imp_CoTaskMemAlloc
0x1800bb894  mov     rdi, rax
0x1800bb897  mov     [rsp+8E0h+var_878], rax
0x1800bb89c  test    rax, rax
0x1800bb89f  jnz     short loc_1800BB8C4
0x1800bb8a1  mov     rcx, [rbp+7E8h]; this
0x1800bb8a8  mov     ebx, 8007000Eh
0x1800bb8ad  mov     r9d, ebx; char *
0x1800bb8b0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bb8b7  lea     edx, [rax+52h]; void *
0x1800bb8ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb8bf  jmp     loc_1800BBB4C
0x1800bb8c4  mov     [rbp+7E0h+Src], 0
0x1800bb8cc  mov     [rbp+7E0h+var_824], 0
0x1800bb8d3  xor     edx, edx; Val
0x1800bb8d5  mov     r8d, 800h; Size
0x1800bb8db  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bb8df  call    memset_0
0x1800bb8e4  mov     rax, [rsi]
0x1800bb8e7  mov     [rbp+7E0h+var_820], rax
0x1800bb8eb  movups  xmm0, xmmword ptr [rsi+8]
0x1800bb8ef  movdqu  [rbp+7E0h+var_818], xmm0
0x1800bb8f4  mov     [rbp+7E0h+var_828], 73h ; 's'
0x1800bb8fb  mov     rcx, rdi; void *
0x1800bb8fe  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bb902  mov     r8d, 810h; Size
0x1800bb908  call    memcpy_0
0x1800bb90d  mov     rax, [rsp+8E0h+var_878]
0x1800bb912  mov     [rax+0Ch], r14d
0x1800bb916  lea     rax, [rbp+7E0h+arg_18]
0x1800bb91d  mov     [rbp+7E0h+var_848], rax
0x1800bb921  lea     rax, [rsp+8E0h+var_878]
0x1800bb926  mov     [rbp+7E0h+var_840], rax
0x1800bb92a  mov     [rbp+7E0h+var_838], 1
0x1800bb92e  mov     rcx, [rbx+28h]
0x1800bb932  mov     rax, [rcx]
0x1800bb935  mov     r9d, 810h
0x1800bb93b  mov     r8, [rsp+8E0h+var_878]
0x1800bb940  mov     edx, r14d
0x1800bb943  mov     rax, [rax+20h]
0x1800bb947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb94c  mov     edi, eax
0x1800bb94e  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800bb952  call    cs:__imp_QueryPerformanceCounter
0x1800bb958  xorps   xmm6, xmm6
0x1800bb95b  cmp     qword ptr [rbx+48h], 0
0x1800bb960  jz      short loc_1800BB984
0x1800bb962  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800bb966  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800bb96a  cvtsi2ss xmm6, rcx
0x1800bb96f  mulss   xmm6, cs:__real@447a0000
0x1800bb977  xorps   xmm0, xmm0
0x1800bb97a  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800bb980  divss   xmm6, xmm0
0x1800bb984  mov     rcx, [rsp+8E0h+var_878]
0x1800bb989  cmp     dword ptr [rcx+8], 1
0x1800bb98d  jnz     loc_1800BBA49
0x1800bb993  mov     [rsp+8E0h+var_870], 0
0x1800bb99c  lea     rdx, [rsp+8E0h+var_870]
0x1800bb9a1  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bb9a6  test    eax, eax
0x1800bb9a8  js      loc_1800BBABA
0x1800bb9ae  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bb9b3  mov     r8, rax
0x1800bb9b6  mov     ecx, [rax]
0x1800bb9b8  cmp     ecx, 4
0x1800bb9bb  jbe     loc_1800BBABA
0x1800bb9c1  mov     [rbp+7E0h+arg_0], edi
0x1800bb9c7  movss   [rsp+8E0h+var_868], xmm6
0x1800bb9cd  mov     [rbp+7E0h+var_860], rbx
0x1800bb9d1  mov     rdx, [rsp+8E0h+var_870]
0x1800bb9d6  mov     ecx, [rdx+10h]
0x1800bb9d9  mov     [rsp+8E0h+var_864], ecx
0x1800bb9dd  mov     ecx, [rdx+4]
0x1800bb9e0  mov     [rsp+8E0h+var_880], ecx
0x1800bb9e4  mov     eax, [rdx+8]
0x1800bb9e7  mov     [rsp+8E0h+var_880+4], eax
0x1800bb9eb  mov     eax, [rdx]
0x1800bb9ed  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800bb9f1  lea     rax, [rbp+7E0h+arg_0]
0x1800bb9f8  mov     [rsp+8E0h+var_890], rax
0x1800bb9fd  lea     rax, [rsp+8E0h+var_868]
0x1800bba02  mov     [rsp+8E0h+var_898], rax
0x1800bba07  lea     rax, [rbp+7E0h+var_860]
0x1800bba0b  mov     [rsp+8E0h+var_8A0], rax
0x1800bba10  lea     rax, [rsp+8E0h+var_864]
0x1800bba15  mov     [rsp+8E0h+var_8A8], rax
0x1800bba1a  lea     rax, [rsp+8E0h+var_880]
0x1800bba1f  mov     [rsp+8E0h+var_8B0], rax
0x1800bba24  lea     rax, [rsp+8E0h+var_880+4]
0x1800bba29  mov     [rsp+8E0h+var_8B8], rax
0x1800bba2e  lea     rax, [rsp+8E0h+var_870]
0x1800bba33  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bba38  lea     rdx, unk_180167D9C
0x1800bba3f  mov     rcx, r8
0x1800bba42  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bba47  jmp     short loc_1800BBABA
0x1800bba49  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bba4e  mov     ecx, [rax]
0x1800bba50  cmp     ecx, 4
0x1800bba53  jbe     short loc_1800BBABA
0x1800bba55  mov     [rbp+7E0h+arg_0], edi
0x1800bba5b  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bba61  mov     [rbp+7E0h+var_860], rbx
0x1800bba65  mov     rcx, [rsp+8E0h+var_878]
0x1800bba6a  mov     edx, [rcx+8]
0x1800bba6d  mov     [rsp+8E0h+var_880+4], edx
0x1800bba71  mov     ecx, [rbx+30h]
0x1800bba74  mov     [rsp+8E0h+var_880], ecx
0x1800bba78  lea     rcx, [rbp+7E0h+arg_0]
0x1800bba7f  mov     [rsp+8E0h+var_8A0], rcx
0x1800bba84  lea     rcx, [rsp+8E0h+var_870]
0x1800bba89  mov     [rsp+8E0h+var_8A8], rcx
0x1800bba8e  lea     rcx, [rbp+7E0h+var_860]
0x1800bba92  mov     [rsp+8E0h+var_8B0], rcx
0x1800bba97  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bba9c  mov     [rsp+8E0h+var_8B8], rcx
0x1800bbaa1  lea     rcx, [rsp+8E0h+var_880]
0x1800bbaa6  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bbaab  lea     rdx, unk_180167E15
0x1800bbab2  mov     rcx, rax
0x1800bbab5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bbaba  mov     rcx, [rbp+7E8h]; this
0x1800bbac1  test    edi, edi
0x1800bbac3  jns     short loc_1800BBAE8
0x1800bbac5  mov     r9d, edi; char *
0x1800bbac8  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bbacf  mov     edx, 81h; void *
0x1800bbad4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bbad9  mov     rax, [rbx]
0x1800bbadc  mov     rcx, rbx
0x1800bbadf  mov     rax, [rax+20h]
0x1800bbae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbae8  mov     ebx, [rbx+40h]
0x1800bbaeb  test    ebx, ebx
0x1800bbaed  jns     short loc_1800BBAF6
0x1800bbaef  mov     edx, 8Ah
0x1800bbaf4  jmp     short loc_1800BBB07
0x1800bbaf6  mov     rcx, [rsp+8E0h+var_878]
0x1800bbafb  mov     ebx, [rcx+4]
0x1800bbafe  test    ebx, ebx
0x1800bbb00  jns     short loc_1800BBB1F
0x1800bbb02  mov     edx, 8Ch; void *
0x1800bbb07  mov     r9d, ebx; char *
0x1800bbb0a  mov     rcx, [rbp+7E8h]; this
0x1800bbb11  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bbb18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbb1d  jmp     short loc_1800BBB3D
0x1800bbb1f  mov     rdx, [rbp+7E0h+arg_20]
0x1800bbb26  call    ??$CastTo@UChannelAudioVolume_XvmSetChannelVolume@@@XvmMessage@@QEAAJPEAPEAUChannelAudioVolume_XvmSetChannelVolume@@@Z; XvmMessage::CastTo<ChannelAudioVolume_XvmSetChannelVolume>(ChannelAudioVolume_XvmSetChannelVolume * *)
0x1800bbb2b  mov     ebx, eax
0x1800bbb2d  test    eax, eax
0x1800bbb2f  jns     short loc_1800BBB3B
0x1800bbb31  mov     r9d, eax
0x1800bbb34  mov     edx, 8Dh
0x1800bbb39  jmp     short loc_1800BBB0A
0x1800bbb3b  xor     ebx, ebx
0x1800bbb3d  mov     rcx, [rbp+7E0h+arg_18]
0x1800bbb44  mov     rax, [rsp+8E0h+var_878]
0x1800bbb49  mov     [rcx], rax
0x1800bbb4c  mov     eax, ebx
0x1800bbb4e  lea     r11, [rsp+8E0h+var_10]
0x1800bbb56  mov     rbx, [r11+28h]
0x1800bbb5a  mov     rsi, [r11+30h]
0x1800bbb5e  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bbb63  mov     rsp, r11
0x1800bbb66  pop     r14
0x1800bbb68  pop     rdi
0x1800bbb69  pop     rbp
0x1800bbb6a  retn
```
