# CGuestXvmAudioObject::SendAndValidateResponse<ChannelAudioVolume_XvmGetChannelVolume>(uint,ChannelAudioVolume_XvmGetChannelVolume,XvmMessage * *,ChannelAudioVolume_XvmGetChannelVolume * *)

- ea: `0x1800bb0f8`
- end: `0x1800bb43f`
- name: `??$SendAndValidateResponse@UChannelAudioVolume_XvmGetChannelVolume@@@CGuestXvmAudioObject@@QEAAJIUChannelAudioVolume_XvmGetChannelVolume@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `839`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c0250`
- `0x1800c0450`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2678`
- `0x1800bb0f8`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bb13a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bb226`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bb13a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bb226`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb16e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb16e`

## string_xrefs

- `0x1800bb151`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bb190`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bb39c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bb3e5`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<ChannelAudioVolume_XvmGetChannelVolume>(
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
    v32 = 116;
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
            (unsigned int)&word_180167CD6,
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
          (unsigned int)&byte_180167D4F,
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
        Channel = XvmMessage::CastTo<ChannelAudioVolume_XvmGetChannelVolume>(v21, v39, v12);
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
0x1800bb0f8  mov     rax, rsp
0x1800bb0fb  mov     [rax+10h], rbx
0x1800bb0ff  mov     [rax+18h], rsi
0x1800bb103  mov     [rax+20h], r9
0x1800bb107  push    rbp
0x1800bb108  push    rdi
0x1800bb109  push    r14
0x1800bb10b  lea     rbp, [rax-7E8h]
0x1800bb112  sub     rsp, 8D0h
0x1800bb119  movaps  xmmword ptr [rax-28h], xmm6
0x1800bb11d  mov     rbx, r8
0x1800bb120  mov     r14d, edx
0x1800bb123  mov     rdi, rcx
0x1800bb126  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bb12e  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800bb136  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800bb13a  call    cs:__imp_QueryPerformanceCounter
0x1800bb140  mov     esi, [rdi+40h]
0x1800bb143  test    esi, esi
0x1800bb145  jns     short loc_1800BB169
0x1800bb147  mov     rcx, [rbp+7E8h]; this
0x1800bb14e  mov     r9d, esi; char *
0x1800bb151  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bb158  mov     edx, 4Fh ; 'O'; void *
0x1800bb15d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb162  mov     eax, esi
0x1800bb164  jmp     loc_1800BB422
0x1800bb169  mov     ecx, 810h; cb
0x1800bb16e  call    cs:__imp_CoTaskMemAlloc
0x1800bb174  mov     rsi, rax
0x1800bb177  mov     [rsp+8E0h+var_878], rax
0x1800bb17c  test    rax, rax
0x1800bb17f  jnz     short loc_1800BB1A4
0x1800bb181  mov     rcx, [rbp+7E8h]; this
0x1800bb188  mov     ebx, 8007000Eh
0x1800bb18d  mov     r9d, ebx; char *
0x1800bb190  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bb197  lea     edx, [rax+52h]; void *
0x1800bb19a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb19f  jmp     loc_1800BB420
0x1800bb1a4  mov     [rbp+7E0h+Src], 0
0x1800bb1ac  mov     [rbp+7E0h+var_824], 0
0x1800bb1b3  xor     edx, edx; Val
0x1800bb1b5  mov     r8d, 800h; Size
0x1800bb1bb  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bb1bf  call    memset_0
0x1800bb1c4  mov     [rbp+7E0h+var_820], rbx
0x1800bb1c8  mov     [rbp+7E0h+var_828], 74h ; 't'
0x1800bb1cf  mov     rcx, rsi; void *
0x1800bb1d2  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bb1d6  mov     r8d, 810h; Size
0x1800bb1dc  call    memcpy_0
0x1800bb1e1  mov     rax, [rsp+8E0h+var_878]
0x1800bb1e6  mov     [rax+0Ch], r14d
0x1800bb1ea  lea     rax, [rbp+7E0h+arg_18]
0x1800bb1f1  mov     [rbp+7E0h+var_848], rax
0x1800bb1f5  lea     rax, [rsp+8E0h+var_878]
0x1800bb1fa  mov     [rbp+7E0h+var_840], rax
0x1800bb1fe  mov     [rbp+7E0h+var_838], 1
0x1800bb202  mov     rcx, [rdi+28h]
0x1800bb206  mov     rax, [rcx]
0x1800bb209  mov     r9d, 810h
0x1800bb20f  mov     r8, [rsp+8E0h+var_878]
0x1800bb214  mov     edx, r14d
0x1800bb217  mov     rax, [rax+20h]
0x1800bb21b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb220  mov     ebx, eax
0x1800bb222  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800bb226  call    cs:__imp_QueryPerformanceCounter
0x1800bb22c  xorps   xmm6, xmm6
0x1800bb22f  cmp     qword ptr [rdi+48h], 0
0x1800bb234  jz      short loc_1800BB258
0x1800bb236  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800bb23a  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800bb23e  cvtsi2ss xmm6, rcx
0x1800bb243  mulss   xmm6, cs:__real@447a0000
0x1800bb24b  xorps   xmm0, xmm0
0x1800bb24e  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800bb254  divss   xmm6, xmm0
0x1800bb258  mov     rcx, [rsp+8E0h+var_878]
0x1800bb25d  cmp     dword ptr [rcx+8], 1
0x1800bb261  jnz     loc_1800BB31D
0x1800bb267  mov     [rsp+8E0h+var_870], 0
0x1800bb270  lea     rdx, [rsp+8E0h+var_870]
0x1800bb275  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bb27a  test    eax, eax
0x1800bb27c  js      loc_1800BB38E
0x1800bb282  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bb287  mov     r8, rax
0x1800bb28a  mov     ecx, [rax]
0x1800bb28c  cmp     ecx, 4
0x1800bb28f  jbe     loc_1800BB38E
0x1800bb295  mov     [rbp+7E0h+arg_0], ebx
0x1800bb29b  movss   [rsp+8E0h+var_868], xmm6
0x1800bb2a1  mov     [rbp+7E0h+var_860], rdi
0x1800bb2a5  mov     rdx, [rsp+8E0h+var_870]
0x1800bb2aa  mov     ecx, [rdx+10h]
0x1800bb2ad  mov     [rsp+8E0h+var_864], ecx
0x1800bb2b1  mov     ecx, [rdx+4]
0x1800bb2b4  mov     [rsp+8E0h+var_880], ecx
0x1800bb2b8  mov     eax, [rdx+8]
0x1800bb2bb  mov     [rsp+8E0h+var_880+4], eax
0x1800bb2bf  mov     eax, [rdx]
0x1800bb2c1  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800bb2c5  lea     rax, [rbp+7E0h+arg_0]
0x1800bb2cc  mov     [rsp+8E0h+var_890], rax
0x1800bb2d1  lea     rax, [rsp+8E0h+var_868]
0x1800bb2d6  mov     [rsp+8E0h+var_898], rax
0x1800bb2db  lea     rax, [rbp+7E0h+var_860]
0x1800bb2df  mov     [rsp+8E0h+var_8A0], rax
0x1800bb2e4  lea     rax, [rsp+8E0h+var_864]
0x1800bb2e9  mov     [rsp+8E0h+var_8A8], rax
0x1800bb2ee  lea     rax, [rsp+8E0h+var_880]
0x1800bb2f3  mov     [rsp+8E0h+var_8B0], rax
0x1800bb2f8  lea     rax, [rsp+8E0h+var_880+4]
0x1800bb2fd  mov     [rsp+8E0h+var_8B8], rax
0x1800bb302  lea     rax, [rsp+8E0h+var_870]
0x1800bb307  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bb30c  lea     rdx, word_180167CD6
0x1800bb313  mov     rcx, r8
0x1800bb316  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bb31b  jmp     short loc_1800BB38E
0x1800bb31d  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bb322  mov     ecx, [rax]
0x1800bb324  cmp     ecx, 4
0x1800bb327  jbe     short loc_1800BB38E
0x1800bb329  mov     [rbp+7E0h+arg_0], ebx
0x1800bb32f  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bb335  mov     [rbp+7E0h+var_860], rdi
0x1800bb339  mov     rcx, [rsp+8E0h+var_878]
0x1800bb33e  mov     edx, [rcx+8]
0x1800bb341  mov     [rsp+8E0h+var_880+4], edx
0x1800bb345  mov     ecx, [rdi+30h]
0x1800bb348  mov     [rsp+8E0h+var_880], ecx
0x1800bb34c  lea     rcx, [rbp+7E0h+arg_0]
0x1800bb353  mov     [rsp+8E0h+var_8A0], rcx
0x1800bb358  lea     rcx, [rsp+8E0h+var_870]
0x1800bb35d  mov     [rsp+8E0h+var_8A8], rcx
0x1800bb362  lea     rcx, [rbp+7E0h+var_860]
0x1800bb366  mov     [rsp+8E0h+var_8B0], rcx
0x1800bb36b  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bb370  mov     [rsp+8E0h+var_8B8], rcx
0x1800bb375  lea     rcx, [rsp+8E0h+var_880]
0x1800bb37a  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bb37f  lea     rdx, byte_180167D4F
0x1800bb386  mov     rcx, rax
0x1800bb389  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bb38e  mov     rcx, [rbp+7E8h]; this
0x1800bb395  test    ebx, ebx
0x1800bb397  jns     short loc_1800BB3BC
0x1800bb399  mov     r9d, ebx; char *
0x1800bb39c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bb3a3  mov     edx, 81h; void *
0x1800bb3a8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bb3ad  mov     rax, [rdi]
0x1800bb3b0  mov     rcx, rdi
0x1800bb3b3  mov     rax, [rax+20h]
0x1800bb3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb3bc  mov     ebx, [rdi+40h]
0x1800bb3bf  test    ebx, ebx
0x1800bb3c1  jns     short loc_1800BB3CA
0x1800bb3c3  mov     edx, 8Ah
0x1800bb3c8  jmp     short loc_1800BB3DB
0x1800bb3ca  mov     rcx, [rsp+8E0h+var_878]
0x1800bb3cf  mov     ebx, [rcx+4]
0x1800bb3d2  test    ebx, ebx
0x1800bb3d4  jns     short loc_1800BB3F3
0x1800bb3d6  mov     edx, 8Ch; void *
0x1800bb3db  mov     r9d, ebx; char *
0x1800bb3de  mov     rcx, [rbp+7E8h]; this
0x1800bb3e5  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bb3ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb3f1  jmp     short loc_1800BB411
0x1800bb3f3  mov     rdx, [rbp+7E0h+arg_20]
0x1800bb3fa  call    ??$CastTo@UChannelAudioVolume_XvmGetChannelVolume@@@XvmMessage@@QEAAJPEAPEAUChannelAudioVolume_XvmGetChannelVolume@@@Z; XvmMessage::CastTo<ChannelAudioVolume_XvmGetChannelVolume>(ChannelAudioVolume_XvmGetChannelVolume * *)
0x1800bb3ff  mov     ebx, eax
0x1800bb401  test    eax, eax
0x1800bb403  jns     short loc_1800BB40F
0x1800bb405  mov     r9d, eax
0x1800bb408  mov     edx, 8Dh
0x1800bb40d  jmp     short loc_1800BB3DE
0x1800bb40f  xor     ebx, ebx
0x1800bb411  mov     rcx, [rbp+7E0h+arg_18]
0x1800bb418  mov     rax, [rsp+8E0h+var_878]
0x1800bb41d  mov     [rcx], rax
0x1800bb420  mov     eax, ebx
0x1800bb422  lea     r11, [rsp+8E0h+var_10]
0x1800bb42a  mov     rbx, [r11+28h]
0x1800bb42e  mov     rsi, [r11+30h]
0x1800bb432  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bb437  mov     rsp, r11
0x1800bb43a  pop     r14
0x1800bb43c  pop     rdi
0x1800bb43d  pop     rbp
0x1800bb43e  retn
```
