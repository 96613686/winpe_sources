# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetIsSystemSoundsSession>(uint,XvmGetIsSystemSoundsSession,XvmMessage * *,XvmGetIsSystemSoundsSession * *)

- ea: `0x180083b58`
- end: `0x180083e9e`
- name: `??$SendAndValidateResponse@UXvmGetIsSystemSoundsSession@@@CGuestXvmAudioObject@@QEAAJIUXvmGetIsSystemSoundsSession@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180083a90`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180083b58`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800b93f8`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180083b9a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180083c85`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180083b9a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180083c85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180083bce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180083bce`

## string_xrefs

- `0x180083bb1`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x180083bf0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x180083dfb`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x180083e44`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetIsSystemSoundsSession>(
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
  int IsSystemSounds; // eax
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
    v32 = 126;
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
            (unsigned int)&unk_1801678F8,
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
          (unsigned int)&unk_180167971,
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
        IsSystemSounds = XvmMessage::CastTo<XvmGetIsSystemSoundsSession>(v21, v39, v12);
        v9 = IsSystemSounds;
        if ( IsSystemSounds >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)IsSystemSounds;
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
0x180083b58  mov     rax, rsp
0x180083b5b  mov     [rax+10h], rbx
0x180083b5f  mov     [rax+18h], rsi
0x180083b63  mov     [rax+20h], r9
0x180083b67  push    rbp
0x180083b68  push    rdi
0x180083b69  push    r14
0x180083b6b  lea     rbp, [rax-7E8h]
0x180083b72  sub     rsp, 8D0h
0x180083b79  movaps  xmmword ptr [rax-28h], xmm6
0x180083b7d  mov     ebx, r8d
0x180083b80  mov     r14d, edx
0x180083b83  mov     rdi, rcx
0x180083b86  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x180083b8e  mov     qword ptr [rbp+7E0h+var_858], 0
0x180083b96  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x180083b9a  call    cs:__imp_QueryPerformanceCounter
0x180083ba0  mov     esi, [rdi+40h]
0x180083ba3  test    esi, esi
0x180083ba5  jns     short loc_180083BC9
0x180083ba7  mov     rcx, [rbp+7E8h]; this
0x180083bae  mov     r9d, esi; char *
0x180083bb1  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180083bb8  mov     edx, 4Fh ; 'O'; void *
0x180083bbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083bc2  mov     eax, esi
0x180083bc4  jmp     loc_180083E81
0x180083bc9  mov     ecx, 810h; cb
0x180083bce  call    cs:__imp_CoTaskMemAlloc
0x180083bd4  mov     rsi, rax
0x180083bd7  mov     [rsp+8E0h+var_878], rax
0x180083bdc  test    rax, rax
0x180083bdf  jnz     short loc_180083C04
0x180083be1  mov     rcx, [rbp+7E8h]; this
0x180083be8  mov     ebx, 8007000Eh
0x180083bed  mov     r9d, ebx; char *
0x180083bf0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180083bf7  lea     edx, [rax+52h]; void *
0x180083bfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083bff  jmp     loc_180083E7F
0x180083c04  mov     [rbp+7E0h+Src], 0
0x180083c0c  mov     [rbp+7E0h+var_824], 0
0x180083c13  xor     edx, edx; Val
0x180083c15  mov     r8d, 800h; Size
0x180083c1b  lea     rcx, [rbp+7E0h+var_820]; void *
0x180083c1f  call    memset_0
0x180083c24  mov     [rbp+7E0h+var_820], ebx
0x180083c27  mov     [rbp+7E0h+var_828], 7Eh ; '~'
0x180083c2e  mov     rcx, rsi; void *
0x180083c31  lea     rdx, [rbp+7E0h+Src]; Src
0x180083c35  mov     r8d, 810h; Size
0x180083c3b  call    memcpy_0
0x180083c40  mov     rax, [rsp+8E0h+var_878]
0x180083c45  mov     [rax+0Ch], r14d
0x180083c49  lea     rax, [rbp+7E0h+arg_18]
0x180083c50  mov     [rbp+7E0h+var_848], rax
0x180083c54  lea     rax, [rsp+8E0h+var_878]
0x180083c59  mov     [rbp+7E0h+var_840], rax
0x180083c5d  mov     [rbp+7E0h+var_838], 1
0x180083c61  mov     rcx, [rdi+28h]
0x180083c65  mov     rax, [rcx]
0x180083c68  mov     r9d, 810h
0x180083c6e  mov     r8, [rsp+8E0h+var_878]
0x180083c73  mov     edx, r14d
0x180083c76  mov     rax, [rax+20h]
0x180083c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083c7f  mov     ebx, eax
0x180083c81  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x180083c85  call    cs:__imp_QueryPerformanceCounter
0x180083c8b  xorps   xmm6, xmm6
0x180083c8e  cmp     qword ptr [rdi+48h], 0
0x180083c93  jz      short loc_180083CB7
0x180083c95  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x180083c99  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x180083c9d  cvtsi2ss xmm6, rcx
0x180083ca2  mulss   xmm6, cs:__real@447a0000
0x180083caa  xorps   xmm0, xmm0
0x180083cad  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x180083cb3  divss   xmm6, xmm0
0x180083cb7  mov     rcx, [rsp+8E0h+var_878]
0x180083cbc  cmp     dword ptr [rcx+8], 1
0x180083cc0  jnz     loc_180083D7C
0x180083cc6  mov     [rsp+8E0h+var_870], 0
0x180083ccf  lea     rdx, [rsp+8E0h+var_870]
0x180083cd4  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x180083cd9  test    eax, eax
0x180083cdb  js      loc_180083DED
0x180083ce1  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x180083ce6  mov     r8, rax
0x180083ce9  mov     ecx, [rax]
0x180083ceb  cmp     ecx, 4
0x180083cee  jbe     loc_180083DED
0x180083cf4  mov     [rbp+7E0h+arg_0], ebx
0x180083cfa  movss   [rsp+8E0h+var_868], xmm6
0x180083d00  mov     [rbp+7E0h+var_860], rdi
0x180083d04  mov     rdx, [rsp+8E0h+var_870]
0x180083d09  mov     ecx, [rdx+10h]
0x180083d0c  mov     [rsp+8E0h+var_864], ecx
0x180083d10  mov     ecx, [rdx+4]
0x180083d13  mov     [rsp+8E0h+var_880], ecx
0x180083d17  mov     eax, [rdx+8]
0x180083d1a  mov     [rsp+8E0h+var_880+4], eax
0x180083d1e  mov     eax, [rdx]
0x180083d20  mov     dword ptr [rsp+8E0h+var_870], eax
0x180083d24  lea     rax, [rbp+7E0h+arg_0]
0x180083d2b  mov     [rsp+8E0h+var_890], rax
0x180083d30  lea     rax, [rsp+8E0h+var_868]
0x180083d35  mov     [rsp+8E0h+var_898], rax
0x180083d3a  lea     rax, [rbp+7E0h+var_860]
0x180083d3e  mov     [rsp+8E0h+var_8A0], rax
0x180083d43  lea     rax, [rsp+8E0h+var_864]
0x180083d48  mov     [rsp+8E0h+var_8A8], rax
0x180083d4d  lea     rax, [rsp+8E0h+var_880]
0x180083d52  mov     [rsp+8E0h+var_8B0], rax
0x180083d57  lea     rax, [rsp+8E0h+var_880+4]
0x180083d5c  mov     [rsp+8E0h+var_8B8], rax
0x180083d61  lea     rax, [rsp+8E0h+var_870]
0x180083d66  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x180083d6b  lea     rdx, unk_1801678F8
0x180083d72  mov     rcx, r8
0x180083d75  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180083d7a  jmp     short loc_180083DED
0x180083d7c  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x180083d81  mov     ecx, [rax]
0x180083d83  cmp     ecx, 4
0x180083d86  jbe     short loc_180083DED
0x180083d88  mov     [rbp+7E0h+arg_0], ebx
0x180083d8e  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x180083d94  mov     [rbp+7E0h+var_860], rdi
0x180083d98  mov     rcx, [rsp+8E0h+var_878]
0x180083d9d  mov     edx, [rcx+8]
0x180083da0  mov     [rsp+8E0h+var_880+4], edx
0x180083da4  mov     ecx, [rdi+30h]
0x180083da7  mov     [rsp+8E0h+var_880], ecx
0x180083dab  lea     rcx, [rbp+7E0h+arg_0]
0x180083db2  mov     [rsp+8E0h+var_8A0], rcx
0x180083db7  lea     rcx, [rsp+8E0h+var_870]
0x180083dbc  mov     [rsp+8E0h+var_8A8], rcx
0x180083dc1  lea     rcx, [rbp+7E0h+var_860]
0x180083dc5  mov     [rsp+8E0h+var_8B0], rcx
0x180083dca  lea     rcx, [rsp+8E0h+var_880+4]
0x180083dcf  mov     [rsp+8E0h+var_8B8], rcx
0x180083dd4  lea     rcx, [rsp+8E0h+var_880]
0x180083dd9  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x180083dde  lea     rdx, unk_180167971
0x180083de5  mov     rcx, rax
0x180083de8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180083ded  mov     rcx, [rbp+7E8h]; this
0x180083df4  test    ebx, ebx
0x180083df6  jns     short loc_180083E1B
0x180083df8  mov     r9d, ebx; char *
0x180083dfb  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180083e02  mov     edx, 81h; void *
0x180083e07  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180083e0c  mov     rax, [rdi]
0x180083e0f  mov     rcx, rdi
0x180083e12  mov     rax, [rax+20h]
0x180083e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083e1b  mov     ebx, [rdi+40h]
0x180083e1e  test    ebx, ebx
0x180083e20  jns     short loc_180083E29
0x180083e22  mov     edx, 8Ah
0x180083e27  jmp     short loc_180083E3A
0x180083e29  mov     rcx, [rsp+8E0h+var_878]
0x180083e2e  mov     ebx, [rcx+4]
0x180083e31  test    ebx, ebx
0x180083e33  jns     short loc_180083E52
0x180083e35  mov     edx, 8Ch; void *
0x180083e3a  mov     r9d, ebx; char *
0x180083e3d  mov     rcx, [rbp+7E8h]; this
0x180083e44  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180083e4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180083e50  jmp     short loc_180083E70
0x180083e52  mov     rdx, [rbp+7E0h+arg_20]
0x180083e59  call    ??$CastTo@UXvmGetIsSystemSoundsSession@@@XvmMessage@@QEAAJPEAPEAUXvmGetIsSystemSoundsSession@@@Z; XvmMessage::CastTo<XvmGetIsSystemSoundsSession>(XvmGetIsSystemSoundsSession * *)
0x180083e5e  mov     ebx, eax
0x180083e60  test    eax, eax
0x180083e62  jns     short loc_180083E6E
0x180083e64  mov     r9d, eax
0x180083e67  mov     edx, 8Dh
0x180083e6c  jmp     short loc_180083E3D
0x180083e6e  xor     ebx, ebx
0x180083e70  mov     rcx, [rbp+7E0h+arg_18]
0x180083e77  mov     rax, [rsp+8E0h+var_878]
0x180083e7c  mov     [rcx], rax
0x180083e7f  mov     eax, ebx
0x180083e81  lea     r11, [rsp+8E0h+var_10]
0x180083e89  mov     rbx, [r11+28h]
0x180083e8d  mov     rsi, [r11+30h]
0x180083e91  movaps  xmm6, xmmword ptr [r11-10h]
0x180083e96  mov     rsp, r11
0x180083e99  pop     r14
0x180083e9b  pop     rdi
0x180083e9c  pop     rbp
0x180083e9d  retn
```
