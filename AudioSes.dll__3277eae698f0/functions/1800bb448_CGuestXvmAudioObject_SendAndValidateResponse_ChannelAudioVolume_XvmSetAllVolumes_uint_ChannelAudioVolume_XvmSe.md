# CGuestXvmAudioObject::SendAndValidateResponse<ChannelAudioVolume_XvmSetAllVolumes>(uint,ChannelAudioVolume_XvmSetAllVolumes,XvmMessage * *,ChannelAudioVolume_XvmSetAllVolumes * *)

- ea: `0x1800bb448`
- end: `0x1800bb812`
- name: `??$SendAndValidateResponse@UChannelAudioVolume_XvmSetAllVolumes@@@CGuestXvmAudioObject@@QEAAJIUChannelAudioVolume_XvmSetAllVolumes@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `970`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c1990`
- `0x1800c1da0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a26c0`
- `0x1800bb448`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bb48a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bb5f9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bb48a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bb5f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb4be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bb4be`

## string_xrefs

- `0x1800bb4a1`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bb4e0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bb76f`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bb7b8`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CGuestXvmAudioObject::SendAndValidateResponse<ChannelAudioVolume_XvmSetAllVolumes>(
        __int64 a1,
        unsigned int a2,
        _OWORD *a3,
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
  _OWORD v34[12]; // [rsp+C8h] [rbp-40h] BYREF
  _OWORD v35[117]; // [rsp+188h] [rbp+80h]
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
    v34[0] = *a3;
    v34[1] = a3[1];
    v34[2] = a3[2];
    v34[3] = a3[3];
    v34[4] = a3[4];
    v34[5] = a3[5];
    v34[6] = a3[6];
    v34[7] = a3[7];
    v34[8] = a3[8];
    v34[9] = a3[9];
    v34[10] = a3[10];
    v34[11] = a3[11];
    v35[0] = a3[12];
    *(_OWORD *)((char *)v35 + 12) = *(_OWORD *)((char *)a3 + 204);
    v32 = 117;
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
            (unsigned int)qword_180167C10,
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
          (unsigned int)byte_180167C89,
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
        v18 = XvmMessage::CastTo<ChannelAudioVolume_XvmSetAllVolumes>(v21, v40, v12);
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
0x1800bb448  mov     rax, rsp
0x1800bb44b  mov     [rax+10h], rbx
0x1800bb44f  mov     [rax+18h], rsi
0x1800bb453  mov     [rax+20h], r9
0x1800bb457  push    rbp
0x1800bb458  push    rdi
0x1800bb459  push    r14
0x1800bb45b  lea     rbp, [rax-7E8h]
0x1800bb462  sub     rsp, 8D0h
0x1800bb469  movaps  xmmword ptr [rax-28h], xmm6
0x1800bb46d  mov     rsi, r8
0x1800bb470  mov     r14d, edx
0x1800bb473  mov     rbx, rcx
0x1800bb476  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bb47e  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800bb486  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800bb48a  call    cs:__imp_QueryPerformanceCounter
0x1800bb490  mov     edi, [rbx+40h]
0x1800bb493  test    edi, edi
0x1800bb495  jns     short loc_1800BB4B9
0x1800bb497  mov     rcx, [rbp+7E8h]; this
0x1800bb49e  mov     r9d, edi; char *
0x1800bb4a1  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bb4a8  mov     edx, 4Fh ; 'O'; void *
0x1800bb4ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb4b2  mov     eax, edi
0x1800bb4b4  jmp     loc_1800BB7F5
0x1800bb4b9  mov     ecx, 810h; cb
0x1800bb4be  call    cs:__imp_CoTaskMemAlloc
0x1800bb4c4  mov     rdi, rax
0x1800bb4c7  mov     [rsp+8E0h+var_878], rax
0x1800bb4cc  test    rax, rax
0x1800bb4cf  jnz     short loc_1800BB4F4
0x1800bb4d1  mov     rcx, [rbp+7E8h]; this
0x1800bb4d8  mov     ebx, 8007000Eh
0x1800bb4dd  mov     r9d, ebx; char *
0x1800bb4e0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bb4e7  lea     edx, [rax+52h]; void *
0x1800bb4ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb4ef  jmp     loc_1800BB7F3
0x1800bb4f4  mov     [rbp+7E0h+Src], 0
0x1800bb4fc  mov     [rbp+7E0h+var_824], 0
0x1800bb503  xor     edx, edx; Val
0x1800bb505  mov     r8d, 800h; Size
0x1800bb50b  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bb50f  call    memset_0
0x1800bb514  movups  xmm0, xmmword ptr [rsi]
0x1800bb517  movups  [rbp+7E0h+var_820], xmm0
0x1800bb51b  movups  xmm1, xmmword ptr [rsi+10h]
0x1800bb51f  movups  [rbp+7E0h+var_810], xmm1
0x1800bb523  movups  xmm0, xmmword ptr [rsi+20h]
0x1800bb527  movups  [rbp+7E0h+var_800], xmm0
0x1800bb52b  movups  xmm1, xmmword ptr [rsi+30h]
0x1800bb52f  movups  [rbp+7E0h+var_7F0], xmm1
0x1800bb533  movups  xmm0, xmmword ptr [rsi+40h]
0x1800bb537  movups  [rbp+7E0h+var_7E0], xmm0
0x1800bb53b  movups  xmm1, xmmword ptr [rsi+50h]
0x1800bb53f  movups  [rbp+7E0h+var_7D0], xmm1
0x1800bb543  movups  xmm0, xmmword ptr [rsi+60h]
0x1800bb547  movups  [rbp+7E0h+var_7C0], xmm0
0x1800bb54b  movups  xmm1, xmmword ptr [rsi+70h]
0x1800bb54f  movups  [rbp+7E0h+var_7B0], xmm1
0x1800bb553  movups  xmm0, xmmword ptr [rsi+80h]
0x1800bb55a  movups  [rbp+7E0h+var_7A0], xmm0
0x1800bb55e  movups  xmm1, xmmword ptr [rsi+90h]
0x1800bb565  movups  [rbp+7E0h+var_790], xmm1
0x1800bb569  movups  xmm0, xmmword ptr [rsi+0A0h]
0x1800bb570  movups  [rbp+7E0h+var_780], xmm0
0x1800bb574  movups  xmm1, xmmword ptr [rsi+0B0h]
0x1800bb57b  movups  [rbp+7E0h+var_770], xmm1
0x1800bb57f  movups  xmm0, xmmword ptr [rsi+0C0h]
0x1800bb586  movups  [rbp+7E0h+var_760], xmm0
0x1800bb58d  movups  xmm1, xmmword ptr [rsi+0CCh]
0x1800bb594  movups  [rbp+7E0h+var_760+0Ch], xmm1
0x1800bb59b  mov     [rbp+7E0h+var_828], 75h ; 'u'
0x1800bb5a2  mov     rcx, rdi; void *
0x1800bb5a5  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bb5a9  mov     r8d, 810h; Size
0x1800bb5af  call    memcpy_0
0x1800bb5b4  mov     rax, [rsp+8E0h+var_878]
0x1800bb5b9  mov     [rax+0Ch], r14d
0x1800bb5bd  lea     rax, [rbp+7E0h+arg_18]
0x1800bb5c4  mov     [rbp+7E0h+var_848], rax
0x1800bb5c8  lea     rax, [rsp+8E0h+var_878]
0x1800bb5cd  mov     [rbp+7E0h+var_840], rax
0x1800bb5d1  mov     [rbp+7E0h+var_838], 1
0x1800bb5d5  mov     rcx, [rbx+28h]
0x1800bb5d9  mov     rax, [rcx]
0x1800bb5dc  mov     r9d, 810h
0x1800bb5e2  mov     r8, [rsp+8E0h+var_878]
0x1800bb5e7  mov     edx, r14d
0x1800bb5ea  mov     rax, [rax+20h]
0x1800bb5ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb5f3  mov     edi, eax
0x1800bb5f5  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800bb5f9  call    cs:__imp_QueryPerformanceCounter
0x1800bb5ff  xorps   xmm6, xmm6
0x1800bb602  cmp     qword ptr [rbx+48h], 0
0x1800bb607  jz      short loc_1800BB62B
0x1800bb609  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800bb60d  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800bb611  cvtsi2ss xmm6, rcx
0x1800bb616  mulss   xmm6, cs:__real@447a0000
0x1800bb61e  xorps   xmm0, xmm0
0x1800bb621  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800bb627  divss   xmm6, xmm0
0x1800bb62b  mov     rcx, [rsp+8E0h+var_878]
0x1800bb630  cmp     dword ptr [rcx+8], 1
0x1800bb634  jnz     loc_1800BB6F0
0x1800bb63a  mov     [rsp+8E0h+var_870], 0
0x1800bb643  lea     rdx, [rsp+8E0h+var_870]
0x1800bb648  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bb64d  test    eax, eax
0x1800bb64f  js      loc_1800BB761
0x1800bb655  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bb65a  mov     r8, rax
0x1800bb65d  mov     ecx, [rax]
0x1800bb65f  cmp     ecx, 4
0x1800bb662  jbe     loc_1800BB761
0x1800bb668  mov     [rbp+7E0h+arg_0], edi
0x1800bb66e  movss   [rsp+8E0h+var_868], xmm6
0x1800bb674  mov     [rbp+7E0h+var_860], rbx
0x1800bb678  mov     rdx, [rsp+8E0h+var_870]
0x1800bb67d  mov     ecx, [rdx+10h]
0x1800bb680  mov     [rsp+8E0h+var_864], ecx
0x1800bb684  mov     ecx, [rdx+4]
0x1800bb687  mov     [rsp+8E0h+var_880], ecx
0x1800bb68b  mov     eax, [rdx+8]
0x1800bb68e  mov     [rsp+8E0h+var_880+4], eax
0x1800bb692  mov     eax, [rdx]
0x1800bb694  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800bb698  lea     rax, [rbp+7E0h+arg_0]
0x1800bb69f  mov     [rsp+8E0h+var_890], rax
0x1800bb6a4  lea     rax, [rsp+8E0h+var_868]
0x1800bb6a9  mov     [rsp+8E0h+var_898], rax
0x1800bb6ae  lea     rax, [rbp+7E0h+var_860]
0x1800bb6b2  mov     [rsp+8E0h+var_8A0], rax
0x1800bb6b7  lea     rax, [rsp+8E0h+var_864]
0x1800bb6bc  mov     [rsp+8E0h+var_8A8], rax
0x1800bb6c1  lea     rax, [rsp+8E0h+var_880]
0x1800bb6c6  mov     [rsp+8E0h+var_8B0], rax
0x1800bb6cb  lea     rax, [rsp+8E0h+var_880+4]
0x1800bb6d0  mov     [rsp+8E0h+var_8B8], rax
0x1800bb6d5  lea     rax, [rsp+8E0h+var_870]
0x1800bb6da  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bb6df  lea     rdx, qword_180167C10
0x1800bb6e6  mov     rcx, r8
0x1800bb6e9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bb6ee  jmp     short loc_1800BB761
0x1800bb6f0  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bb6f5  mov     ecx, [rax]
0x1800bb6f7  cmp     ecx, 4
0x1800bb6fa  jbe     short loc_1800BB761
0x1800bb6fc  mov     [rbp+7E0h+arg_0], edi
0x1800bb702  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bb708  mov     [rbp+7E0h+var_860], rbx
0x1800bb70c  mov     rcx, [rsp+8E0h+var_878]
0x1800bb711  mov     edx, [rcx+8]
0x1800bb714  mov     [rsp+8E0h+var_880+4], edx
0x1800bb718  mov     ecx, [rbx+30h]
0x1800bb71b  mov     [rsp+8E0h+var_880], ecx
0x1800bb71f  lea     rcx, [rbp+7E0h+arg_0]
0x1800bb726  mov     [rsp+8E0h+var_8A0], rcx
0x1800bb72b  lea     rcx, [rsp+8E0h+var_870]
0x1800bb730  mov     [rsp+8E0h+var_8A8], rcx
0x1800bb735  lea     rcx, [rbp+7E0h+var_860]
0x1800bb739  mov     [rsp+8E0h+var_8B0], rcx
0x1800bb73e  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bb743  mov     [rsp+8E0h+var_8B8], rcx
0x1800bb748  lea     rcx, [rsp+8E0h+var_880]
0x1800bb74d  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bb752  lea     rdx, byte_180167C89
0x1800bb759  mov     rcx, rax
0x1800bb75c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bb761  mov     rcx, [rbp+7E8h]; this
0x1800bb768  test    edi, edi
0x1800bb76a  jns     short loc_1800BB78F
0x1800bb76c  mov     r9d, edi; char *
0x1800bb76f  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bb776  mov     edx, 81h; void *
0x1800bb77b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bb780  mov     rax, [rbx]
0x1800bb783  mov     rcx, rbx
0x1800bb786  mov     rax, [rax+20h]
0x1800bb78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb78f  mov     ebx, [rbx+40h]
0x1800bb792  test    ebx, ebx
0x1800bb794  jns     short loc_1800BB79D
0x1800bb796  mov     edx, 8Ah
0x1800bb79b  jmp     short loc_1800BB7AE
0x1800bb79d  mov     rcx, [rsp+8E0h+var_878]
0x1800bb7a2  mov     ebx, [rcx+4]
0x1800bb7a5  test    ebx, ebx
0x1800bb7a7  jns     short loc_1800BB7C6
0x1800bb7a9  mov     edx, 8Ch; void *
0x1800bb7ae  mov     r9d, ebx; char *
0x1800bb7b1  mov     rcx, [rbp+7E8h]; this
0x1800bb7b8  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bb7bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bb7c4  jmp     short loc_1800BB7E4
0x1800bb7c6  mov     rdx, [rbp+7E0h+arg_20]
0x1800bb7cd  call    ??$CastTo@UChannelAudioVolume_XvmSetAllVolumes@@@XvmMessage@@QEAAJPEAPEAUChannelAudioVolume_XvmSetAllVolumes@@@Z; XvmMessage::CastTo<ChannelAudioVolume_XvmSetAllVolumes>(ChannelAudioVolume_XvmSetAllVolumes * *)
0x1800bb7d2  mov     ebx, eax
0x1800bb7d4  test    eax, eax
0x1800bb7d6  jns     short loc_1800BB7E2
0x1800bb7d8  mov     r9d, eax
0x1800bb7db  mov     edx, 8Dh
0x1800bb7e0  jmp     short loc_1800BB7B1
0x1800bb7e2  xor     ebx, ebx
0x1800bb7e4  mov     rcx, [rbp+7E0h+arg_18]
0x1800bb7eb  mov     rax, [rsp+8E0h+var_878]
0x1800bb7f0  mov     [rcx], rax
0x1800bb7f3  mov     eax, ebx
0x1800bb7f5  lea     r11, [rsp+8E0h+var_10]
0x1800bb7fd  mov     rbx, [r11+28h]
0x1800bb801  mov     rsi, [r11+30h]
0x1800bb805  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bb80a  mov     rsp, r11
0x1800bb80d  pop     r14
0x1800bb80f  pop     rdi
0x1800bb810  pop     rbp
0x1800bb811  retn
```
