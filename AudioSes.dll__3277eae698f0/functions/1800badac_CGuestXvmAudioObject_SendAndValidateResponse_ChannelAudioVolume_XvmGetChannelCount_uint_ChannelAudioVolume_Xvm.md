# CGuestXvmAudioObject::SendAndValidateResponse<ChannelAudioVolume_XvmGetChannelCount>(uint,ChannelAudioVolume_XvmGetChannelCount,XvmMessage * *,ChannelAudioVolume_XvmGetChannelCount * *)

- ea: `0x1800badac`
- end: `0x1800bb0f2`
- name: `??$SendAndValidateResponse@UChannelAudioVolume_XvmGetChannelCount@@@CGuestXvmAudioObject@@QEAAJIUChannelAudioVolume_XvmGetChannelCount@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bff80`
- `0x1800c0160`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2630`
- `0x1800badac`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800badee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800baed9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800badee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800baed9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bae22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bae22`

## string_xrefs

- `0x1800bae05`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bae44`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bb04f`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bb098`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<ChannelAudioVolume_XvmGetChannelCount>(
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
  int Channel; // eax
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
    v32 = 114;
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
            (unsigned int)word_180167E62,
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
          (unsigned int)byte_180167EDB,
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
        Channel = XvmMessage::CastTo<ChannelAudioVolume_XvmGetChannelCount>(v21, v39, v12);
        v9 = Channel;
        if ( Channel >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)Channel;
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
0x1800badac  mov     rax, rsp
0x1800badaf  mov     [rax+10h], rbx
0x1800badb3  mov     [rax+18h], rsi
0x1800badb7  mov     [rax+20h], r9
0x1800badbb  push    rbp
0x1800badbc  push    rdi
0x1800badbd  push    r14
0x1800badbf  lea     rbp, [rax-7E8h]
0x1800badc6  sub     rsp, 8D0h
0x1800badcd  movaps  xmmword ptr [rax-28h], xmm6
0x1800badd1  mov     ebx, r8d
0x1800badd4  mov     r14d, edx
0x1800badd7  mov     rdi, rcx
0x1800badda  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bade2  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800badea  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800badee  call    cs:__imp_QueryPerformanceCounter
0x1800badf4  mov     esi, [rdi+40h]
0x1800badf7  test    esi, esi
0x1800badf9  jns     short loc_1800BAE1D
0x1800badfb  mov     rcx, [rbp+7E8h]; this
0x1800bae02  mov     r9d, esi; char *
0x1800bae05  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bae0c  mov     edx, 4Fh ; 'O'; void *
0x1800bae11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bae16  mov     eax, esi
0x1800bae18  jmp     loc_1800BB0D5
0x1800bae1d  mov     ecx, 810h; cb
0x1800bae22  call    cs:__imp_CoTaskMemAlloc
0x1800bae28  mov     rsi, rax
0x1800bae2b  mov     [rsp+8E0h+var_878], rax
0x1800bae30  test    rax, rax
0x1800bae33  jnz     short loc_1800BAE58
0x1800bae35  mov     rcx, [rbp+7E8h]; this
0x1800bae3c  mov     ebx, 8007000Eh
0x1800bae41  mov     r9d, ebx; char *
0x1800bae44  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bae4b  lea     edx, [rax+52h]; void *
0x1800bae4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bae53  jmp     loc_1800BB0D3
0x1800bae58  mov     [rbp+7E0h+Src], 0
0x1800bae60  mov     [rbp+7E0h+var_824], 0
0x1800bae67  xor     edx, edx; Val
0x1800bae69  mov     r8d, 800h; Size
0x1800bae6f  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bae73  call    memset_0
0x1800bae78  mov     [rbp+7E0h+var_820], ebx
0x1800bae7b  mov     [rbp+7E0h+var_828], 72h ; 'r'
0x1800bae82  mov     rcx, rsi; void *
0x1800bae85  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bae89  mov     r8d, 810h; Size
0x1800bae8f  call    memcpy_0
0x1800bae94  mov     rax, [rsp+8E0h+var_878]
0x1800bae99  mov     [rax+0Ch], r14d
0x1800bae9d  lea     rax, [rbp+7E0h+arg_18]
0x1800baea4  mov     [rbp+7E0h+var_848], rax
0x1800baea8  lea     rax, [rsp+8E0h+var_878]
0x1800baead  mov     [rbp+7E0h+var_840], rax
0x1800baeb1  mov     [rbp+7E0h+var_838], 1
0x1800baeb5  mov     rcx, [rdi+28h]
0x1800baeb9  mov     rax, [rcx]
0x1800baebc  mov     r9d, 810h
0x1800baec2  mov     r8, [rsp+8E0h+var_878]
0x1800baec7  mov     edx, r14d
0x1800baeca  mov     rax, [rax+20h]
0x1800baece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800baed3  mov     ebx, eax
0x1800baed5  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800baed9  call    cs:__imp_QueryPerformanceCounter
0x1800baedf  xorps   xmm6, xmm6
0x1800baee2  cmp     qword ptr [rdi+48h], 0
0x1800baee7  jz      short loc_1800BAF0B
0x1800baee9  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800baeed  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800baef1  cvtsi2ss xmm6, rcx
0x1800baef6  mulss   xmm6, cs:__real@447a0000
0x1800baefe  xorps   xmm0, xmm0
0x1800baf01  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800baf07  divss   xmm6, xmm0
0x1800baf0b  mov     rcx, [rsp+8E0h+var_878]
0x1800baf10  cmp     dword ptr [rcx+8], 1
0x1800baf14  jnz     loc_1800BAFD0
0x1800baf1a  mov     [rsp+8E0h+var_870], 0
0x1800baf23  lea     rdx, [rsp+8E0h+var_870]
0x1800baf28  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800baf2d  test    eax, eax
0x1800baf2f  js      loc_1800BB041
0x1800baf35  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800baf3a  mov     r8, rax
0x1800baf3d  mov     ecx, [rax]
0x1800baf3f  cmp     ecx, 4
0x1800baf42  jbe     loc_1800BB041
0x1800baf48  mov     [rbp+7E0h+arg_0], ebx
0x1800baf4e  movss   [rsp+8E0h+var_868], xmm6
0x1800baf54  mov     [rbp+7E0h+var_860], rdi
0x1800baf58  mov     rdx, [rsp+8E0h+var_870]
0x1800baf5d  mov     ecx, [rdx+10h]
0x1800baf60  mov     [rsp+8E0h+var_864], ecx
0x1800baf64  mov     ecx, [rdx+4]
0x1800baf67  mov     [rsp+8E0h+var_880], ecx
0x1800baf6b  mov     eax, [rdx+8]
0x1800baf6e  mov     [rsp+8E0h+var_880+4], eax
0x1800baf72  mov     eax, [rdx]
0x1800baf74  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800baf78  lea     rax, [rbp+7E0h+arg_0]
0x1800baf7f  mov     [rsp+8E0h+var_890], rax
0x1800baf84  lea     rax, [rsp+8E0h+var_868]
0x1800baf89  mov     [rsp+8E0h+var_898], rax
0x1800baf8e  lea     rax, [rbp+7E0h+var_860]
0x1800baf92  mov     [rsp+8E0h+var_8A0], rax
0x1800baf97  lea     rax, [rsp+8E0h+var_864]
0x1800baf9c  mov     [rsp+8E0h+var_8A8], rax
0x1800bafa1  lea     rax, [rsp+8E0h+var_880]
0x1800bafa6  mov     [rsp+8E0h+var_8B0], rax
0x1800bafab  lea     rax, [rsp+8E0h+var_880+4]
0x1800bafb0  mov     [rsp+8E0h+var_8B8], rax
0x1800bafb5  lea     rax, [rsp+8E0h+var_870]
0x1800bafba  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bafbf  lea     rdx, word_180167E62
0x1800bafc6  mov     rcx, r8
0x1800bafc9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bafce  jmp     short loc_1800BB041
0x1800bafd0  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bafd5  mov     ecx, [rax]
0x1800bafd7  cmp     ecx, 4
0x1800bafda  jbe     short loc_1800BB041
0x1800bafdc  mov     [rbp+7E0h+arg_0], ebx
0x1800bafe2  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bafe8  mov     [rbp+7E0h+var_860], rdi
0x1800bafec  mov     rcx, [rsp+8E0h+var_878]
0x1800baff1  mov     edx, [rcx+8]
0x1800baff4  mov     [rsp+8E0h+var_880+4], edx
0x1800baff8  mov     ecx, [rdi+30h]
0x1800baffb  mov     [rsp+8E0h+var_880], ecx
0x1800bafff  lea     rcx, [rbp+7E0h+arg_0]
0x1800bb006  mov     [rsp+8E0h+var_8A0], rcx
0x1800bb00b  lea     rcx, [rsp+8E0h+var_870]
0x1800bb010  mov     [rsp+8E0h+var_8A8], rcx
0x1800bb015  lea     rcx, [rbp+7E0h+var_860]
0x1800bb019  mov     [rsp+8E0h+var_8B0], rcx
0x1800bb01e  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bb023  mov     [rsp+8E0h+var_8B8], rcx
0x1800bb028  lea     rcx, [rsp+8E0h+var_880]
0x1800bb02d  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bb032  lea     rdx, byte_180167EDB
0x1800bb039  mov     rcx, rax
0x1800bb03c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bb041  mov     rcx, [rbp+7E8h]; this
0x1800bb048  test    ebx, ebx
0x1800bb04a  jns     short loc_1800BB06F
0x1800bb04c  mov     r9d, ebx; char *
0x1800bb04f  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bb056  mov     edx, 81h; void *
0x1800bb05b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bb060  mov     rax, [rdi]
0x1800bb063  mov     rcx, rdi
0x1800bb066  mov     rax, [rax+20h]
0x1800bb06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb06f  mov     ebx, [rdi+40h]
0x1800bb072  test    ebx, ebx
0x1800bb074  jns     short loc_1800BB07D
0x1800bb076  mov     edx, 8Ah
0x1800bb07b  jmp     short loc_1800BB08E
0x1800bb07d  mov     rcx, [rsp+8E0h+var_878]
0x1800bb082  mov     ebx, [rcx+4]
0x1800bb085  test    ebx, ebx
0x1800bb087  jns     short loc_1800BB0A6
0x1800bb089  mov     edx, 8Ch; void *
0x1800bb08e  mov     r9d, ebx; char *
0x1800bb091  mov     rcx, [rbp+7E8h]; this
0x1800bb098  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bb09f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb0a4  jmp     short loc_1800BB0C4
0x1800bb0a6  mov     rdx, [rbp+7E0h+arg_20]
0x1800bb0ad  call    ??$CastTo@UChannelAudioVolume_XvmGetChannelCount@@@XvmMessage@@QEAAJPEAPEAUChannelAudioVolume_XvmGetChannelCount@@@Z; XvmMessage::CastTo<ChannelAudioVolume_XvmGetChannelCount>(ChannelAudioVolume_XvmGetChannelCount * *)
0x1800bb0b2  mov     ebx, eax
0x1800bb0b4  test    eax, eax
0x1800bb0b6  jns     short loc_1800BB0C2
0x1800bb0b8  mov     r9d, eax
0x1800bb0bb  mov     edx, 8Dh
0x1800bb0c0  jmp     short loc_1800BB091
0x1800bb0c2  xor     ebx, ebx
0x1800bb0c4  mov     rcx, [rbp+7E0h+arg_18]
0x1800bb0cb  mov     rax, [rsp+8E0h+var_878]
0x1800bb0d0  mov     [rcx], rax
0x1800bb0d3  mov     eax, ebx
0x1800bb0d5  lea     r11, [rsp+8E0h+var_10]
0x1800bb0dd  mov     rbx, [r11+28h]
0x1800bb0e1  mov     rsi, [r11+30h]
0x1800bb0e5  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bb0ea  mov     rsp, r11
0x1800bb0ed  pop     r14
0x1800bb0ef  pop     rdi
0x1800bb0f0  pop     rbp
0x1800bb0f1  retn
```
