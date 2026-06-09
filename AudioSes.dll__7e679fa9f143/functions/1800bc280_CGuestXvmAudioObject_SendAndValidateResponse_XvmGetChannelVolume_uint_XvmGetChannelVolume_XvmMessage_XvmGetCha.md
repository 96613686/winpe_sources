# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetChannelVolume>(uint,XvmGetChannelVolume,XvmMessage * *,XvmGetChannelVolume * *)

- ea: `0x1800bc280`
- end: `0x1800bc5c7`
- name: `??$SendAndValidateResponse@UXvmGetChannelVolume@@@CGuestXvmAudioObject@@QEAAJIUXvmGetChannelVolume@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `839`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c0350`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a28a8`
- `0x1800bc280`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bc2c2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bc3ae`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bc2c2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bc3ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bc2f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bc2f6`

## string_xrefs

- `0x1800bc2d9`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bc318`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bc524`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bc56d`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetChannelVolume>(
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
    v32 = 18;
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
            (unsigned int)&unk_180168558,
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
          (unsigned int)&unk_1801685D1,
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
        Channel = XvmMessage::CastTo<XvmGetChannelVolume>(v21, v39, v12);
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
0x1800bc280  mov     rax, rsp
0x1800bc283  mov     [rax+10h], rbx
0x1800bc287  mov     [rax+18h], rsi
0x1800bc28b  mov     [rax+20h], r9
0x1800bc28f  push    rbp
0x1800bc290  push    rdi
0x1800bc291  push    r14
0x1800bc293  lea     rbp, [rax-7E8h]
0x1800bc29a  sub     rsp, 8D0h
0x1800bc2a1  movaps  xmmword ptr [rax-28h], xmm6
0x1800bc2a5  mov     rbx, r8
0x1800bc2a8  mov     r14d, edx
0x1800bc2ab  mov     rdi, rcx
0x1800bc2ae  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bc2b6  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800bc2be  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800bc2c2  call    cs:__imp_QueryPerformanceCounter
0x1800bc2c8  mov     esi, [rdi+40h]
0x1800bc2cb  test    esi, esi
0x1800bc2cd  jns     short loc_1800BC2F1
0x1800bc2cf  mov     rcx, [rbp+7E8h]; this
0x1800bc2d6  mov     r9d, esi; char *
0x1800bc2d9  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bc2e0  mov     edx, 4Fh ; 'O'; void *
0x1800bc2e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc2ea  mov     eax, esi
0x1800bc2ec  jmp     loc_1800BC5AA
0x1800bc2f1  mov     ecx, 810h; cb
0x1800bc2f6  call    cs:__imp_CoTaskMemAlloc
0x1800bc2fc  mov     rsi, rax
0x1800bc2ff  mov     [rsp+8E0h+var_878], rax
0x1800bc304  test    rax, rax
0x1800bc307  jnz     short loc_1800BC32C
0x1800bc309  mov     rcx, [rbp+7E8h]; this
0x1800bc310  mov     ebx, 8007000Eh
0x1800bc315  mov     r9d, ebx; char *
0x1800bc318  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bc31f  lea     edx, [rax+52h]; void *
0x1800bc322  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc327  jmp     loc_1800BC5A8
0x1800bc32c  mov     [rbp+7E0h+Src], 0
0x1800bc334  mov     [rbp+7E0h+var_824], 0
0x1800bc33b  xor     edx, edx; Val
0x1800bc33d  mov     r8d, 800h; Size
0x1800bc343  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bc347  call    memset_0
0x1800bc34c  mov     [rbp+7E0h+var_820], rbx
0x1800bc350  mov     [rbp+7E0h+var_828], 12h
0x1800bc357  mov     rcx, rsi; void *
0x1800bc35a  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bc35e  mov     r8d, 810h; Size
0x1800bc364  call    memcpy_0
0x1800bc369  mov     rax, [rsp+8E0h+var_878]
0x1800bc36e  mov     [rax+0Ch], r14d
0x1800bc372  lea     rax, [rbp+7E0h+arg_18]
0x1800bc379  mov     [rbp+7E0h+var_848], rax
0x1800bc37d  lea     rax, [rsp+8E0h+var_878]
0x1800bc382  mov     [rbp+7E0h+var_840], rax
0x1800bc386  mov     [rbp+7E0h+var_838], 1
0x1800bc38a  mov     rcx, [rdi+28h]
0x1800bc38e  mov     rax, [rcx]
0x1800bc391  mov     r9d, 810h
0x1800bc397  mov     r8, [rsp+8E0h+var_878]
0x1800bc39c  mov     edx, r14d
0x1800bc39f  mov     rax, [rax+20h]
0x1800bc3a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc3a8  mov     ebx, eax
0x1800bc3aa  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800bc3ae  call    cs:__imp_QueryPerformanceCounter
0x1800bc3b4  xorps   xmm6, xmm6
0x1800bc3b7  cmp     qword ptr [rdi+48h], 0
0x1800bc3bc  jz      short loc_1800BC3E0
0x1800bc3be  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800bc3c2  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800bc3c6  cvtsi2ss xmm6, rcx
0x1800bc3cb  mulss   xmm6, cs:__real@447a0000
0x1800bc3d3  xorps   xmm0, xmm0
0x1800bc3d6  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800bc3dc  divss   xmm6, xmm0
0x1800bc3e0  mov     rcx, [rsp+8E0h+var_878]
0x1800bc3e5  cmp     dword ptr [rcx+8], 1
0x1800bc3e9  jnz     loc_1800BC4A5
0x1800bc3ef  mov     [rsp+8E0h+var_870], 0
0x1800bc3f8  lea     rdx, [rsp+8E0h+var_870]
0x1800bc3fd  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bc402  test    eax, eax
0x1800bc404  js      loc_1800BC516
0x1800bc40a  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bc40f  mov     r8, rax
0x1800bc412  mov     ecx, [rax]
0x1800bc414  cmp     ecx, 4
0x1800bc417  jbe     loc_1800BC516
0x1800bc41d  mov     [rbp+7E0h+arg_0], ebx
0x1800bc423  movss   [rsp+8E0h+var_868], xmm6
0x1800bc429  mov     [rbp+7E0h+var_860], rdi
0x1800bc42d  mov     rdx, [rsp+8E0h+var_870]
0x1800bc432  mov     ecx, [rdx+10h]
0x1800bc435  mov     [rsp+8E0h+var_864], ecx
0x1800bc439  mov     ecx, [rdx+4]
0x1800bc43c  mov     [rsp+8E0h+var_880], ecx
0x1800bc440  mov     eax, [rdx+8]
0x1800bc443  mov     [rsp+8E0h+var_880+4], eax
0x1800bc447  mov     eax, [rdx]
0x1800bc449  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800bc44d  lea     rax, [rbp+7E0h+arg_0]
0x1800bc454  mov     [rsp+8E0h+var_890], rax
0x1800bc459  lea     rax, [rsp+8E0h+var_868]
0x1800bc45e  mov     [rsp+8E0h+var_898], rax
0x1800bc463  lea     rax, [rbp+7E0h+var_860]
0x1800bc467  mov     [rsp+8E0h+var_8A0], rax
0x1800bc46c  lea     rax, [rsp+8E0h+var_864]
0x1800bc471  mov     [rsp+8E0h+var_8A8], rax
0x1800bc476  lea     rax, [rsp+8E0h+var_880]
0x1800bc47b  mov     [rsp+8E0h+var_8B0], rax
0x1800bc480  lea     rax, [rsp+8E0h+var_880+4]
0x1800bc485  mov     [rsp+8E0h+var_8B8], rax
0x1800bc48a  lea     rax, [rsp+8E0h+var_870]
0x1800bc48f  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bc494  lea     rdx, unk_180168558
0x1800bc49b  mov     rcx, r8
0x1800bc49e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bc4a3  jmp     short loc_1800BC516
0x1800bc4a5  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bc4aa  mov     ecx, [rax]
0x1800bc4ac  cmp     ecx, 4
0x1800bc4af  jbe     short loc_1800BC516
0x1800bc4b1  mov     [rbp+7E0h+arg_0], ebx
0x1800bc4b7  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bc4bd  mov     [rbp+7E0h+var_860], rdi
0x1800bc4c1  mov     rcx, [rsp+8E0h+var_878]
0x1800bc4c6  mov     edx, [rcx+8]
0x1800bc4c9  mov     [rsp+8E0h+var_880+4], edx
0x1800bc4cd  mov     ecx, [rdi+30h]
0x1800bc4d0  mov     [rsp+8E0h+var_880], ecx
0x1800bc4d4  lea     rcx, [rbp+7E0h+arg_0]
0x1800bc4db  mov     [rsp+8E0h+var_8A0], rcx
0x1800bc4e0  lea     rcx, [rsp+8E0h+var_870]
0x1800bc4e5  mov     [rsp+8E0h+var_8A8], rcx
0x1800bc4ea  lea     rcx, [rbp+7E0h+var_860]
0x1800bc4ee  mov     [rsp+8E0h+var_8B0], rcx
0x1800bc4f3  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bc4f8  mov     [rsp+8E0h+var_8B8], rcx
0x1800bc4fd  lea     rcx, [rsp+8E0h+var_880]
0x1800bc502  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bc507  lea     rdx, unk_1801685D1
0x1800bc50e  mov     rcx, rax
0x1800bc511  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bc516  mov     rcx, [rbp+7E8h]; this
0x1800bc51d  test    ebx, ebx
0x1800bc51f  jns     short loc_1800BC544
0x1800bc521  mov     r9d, ebx; char *
0x1800bc524  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bc52b  mov     edx, 81h; void *
0x1800bc530  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bc535  mov     rax, [rdi]
0x1800bc538  mov     rcx, rdi
0x1800bc53b  mov     rax, [rax+20h]
0x1800bc53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc544  mov     ebx, [rdi+40h]
0x1800bc547  test    ebx, ebx
0x1800bc549  jns     short loc_1800BC552
0x1800bc54b  mov     edx, 8Ah
0x1800bc550  jmp     short loc_1800BC563
0x1800bc552  mov     rcx, [rsp+8E0h+var_878]
0x1800bc557  mov     ebx, [rcx+4]
0x1800bc55a  test    ebx, ebx
0x1800bc55c  jns     short loc_1800BC57B
0x1800bc55e  mov     edx, 8Ch; void *
0x1800bc563  mov     r9d, ebx; char *
0x1800bc566  mov     rcx, [rbp+7E8h]; this
0x1800bc56d  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bc574  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc579  jmp     short loc_1800BC599
0x1800bc57b  mov     rdx, [rbp+7E0h+arg_20]
0x1800bc582  call    ??$CastTo@UXvmGetChannelVolume@@@XvmMessage@@QEAAJPEAPEAUXvmGetChannelVolume@@@Z; XvmMessage::CastTo<XvmGetChannelVolume>(XvmGetChannelVolume * *)
0x1800bc587  mov     ebx, eax
0x1800bc589  test    eax, eax
0x1800bc58b  jns     short loc_1800BC597
0x1800bc58d  mov     r9d, eax
0x1800bc590  mov     edx, 8Dh
0x1800bc595  jmp     short loc_1800BC566
0x1800bc597  xor     ebx, ebx
0x1800bc599  mov     rcx, [rbp+7E0h+arg_18]
0x1800bc5a0  mov     rax, [rsp+8E0h+var_878]
0x1800bc5a5  mov     [rcx], rax
0x1800bc5a8  mov     eax, ebx
0x1800bc5aa  lea     r11, [rsp+8E0h+var_10]
0x1800bc5b2  mov     rbx, [r11+28h]
0x1800bc5b6  mov     rsi, [r11+30h]
0x1800bc5ba  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bc5bf  mov     rsp, r11
0x1800bc5c2  pop     r14
0x1800bc5c4  pop     rdi
0x1800bc5c5  pop     rbp
0x1800bc5c6  retn
```
