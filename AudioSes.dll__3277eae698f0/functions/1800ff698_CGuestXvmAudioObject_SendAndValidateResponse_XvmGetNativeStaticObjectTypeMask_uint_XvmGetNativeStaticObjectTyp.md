# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetNativeStaticObjectTypeMask>(uint,XvmGetNativeStaticObjectTypeMask,XvmMessage * *,XvmGetNativeStaticObjectTypeMask * *)

- ea: `0x1800ff698`
- end: `0x1800ff9de`
- name: `??$SendAndValidateResponse@UXvmGetNativeStaticObjectTypeMask@@@CGuestXvmAudioObject@@QEAAJIUXvmGetNativeStaticObjectTypeMask@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180101540`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800fa1b4`
- `0x1800ff698`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ff6da`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ff7c5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ff6da`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ff7c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ff70e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ff70e`

## string_xrefs

- `0x1800ff6f1`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ff730`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ff93b`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ff984`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetNativeStaticObjectTypeMask>(
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
  int NativeStaticObjectType; // eax
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
    v32 = 49;
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
            (unsigned int)&dword_180170A4C,
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
          (unsigned int)&byte_1801709FF,
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
        NativeStaticObjectType = XvmMessage::CastTo<XvmGetNativeStaticObjectTypeMask>(v21, v39, v12);
        v9 = NativeStaticObjectType;
        if ( NativeStaticObjectType >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)NativeStaticObjectType;
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
0x1800ff698  mov     rax, rsp
0x1800ff69b  mov     [rax+10h], rbx
0x1800ff69f  mov     [rax+18h], rsi
0x1800ff6a3  mov     [rax+20h], r9
0x1800ff6a7  push    rbp
0x1800ff6a8  push    rdi
0x1800ff6a9  push    r14
0x1800ff6ab  lea     rbp, [rax-7E8h]
0x1800ff6b2  sub     rsp, 8D0h
0x1800ff6b9  movaps  xmmword ptr [rax-28h], xmm6
0x1800ff6bd  mov     ebx, r8d
0x1800ff6c0  mov     r14d, edx
0x1800ff6c3  mov     rdi, rcx
0x1800ff6c6  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800ff6ce  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800ff6d6  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800ff6da  call    cs:__imp_QueryPerformanceCounter
0x1800ff6e0  mov     esi, [rdi+40h]
0x1800ff6e3  test    esi, esi
0x1800ff6e5  jns     short loc_1800FF709
0x1800ff6e7  mov     rcx, [rbp+7E8h]; this
0x1800ff6ee  mov     r9d, esi; char *
0x1800ff6f1  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ff6f8  mov     edx, 4Fh ; 'O'; void *
0x1800ff6fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ff702  mov     eax, esi
0x1800ff704  jmp     loc_1800FF9C1
0x1800ff709  mov     ecx, 810h; cb
0x1800ff70e  call    cs:__imp_CoTaskMemAlloc
0x1800ff714  mov     rsi, rax
0x1800ff717  mov     [rsp+8E0h+var_878], rax
0x1800ff71c  test    rax, rax
0x1800ff71f  jnz     short loc_1800FF744
0x1800ff721  mov     rcx, [rbp+7E8h]; this
0x1800ff728  mov     ebx, 8007000Eh
0x1800ff72d  mov     r9d, ebx; char *
0x1800ff730  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ff737  lea     edx, [rax+52h]; void *
0x1800ff73a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ff73f  jmp     loc_1800FF9BF
0x1800ff744  mov     [rbp+7E0h+Src], 0
0x1800ff74c  mov     [rbp+7E0h+var_824], 0
0x1800ff753  xor     edx, edx; Val
0x1800ff755  mov     r8d, 800h; Size
0x1800ff75b  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800ff75f  call    memset_0
0x1800ff764  mov     [rbp+7E0h+var_820], ebx
0x1800ff767  mov     [rbp+7E0h+var_828], 31h ; '1'
0x1800ff76e  mov     rcx, rsi; void *
0x1800ff771  lea     rdx, [rbp+7E0h+Src]; Src
0x1800ff775  mov     r8d, 810h; Size
0x1800ff77b  call    memcpy_0
0x1800ff780  mov     rax, [rsp+8E0h+var_878]
0x1800ff785  mov     [rax+0Ch], r14d
0x1800ff789  lea     rax, [rbp+7E0h+arg_18]
0x1800ff790  mov     [rbp+7E0h+var_848], rax
0x1800ff794  lea     rax, [rsp+8E0h+var_878]
0x1800ff799  mov     [rbp+7E0h+var_840], rax
0x1800ff79d  mov     [rbp+7E0h+var_838], 1
0x1800ff7a1  mov     rcx, [rdi+28h]
0x1800ff7a5  mov     rax, [rcx]
0x1800ff7a8  mov     r9d, 810h
0x1800ff7ae  mov     r8, [rsp+8E0h+var_878]
0x1800ff7b3  mov     edx, r14d
0x1800ff7b6  mov     rax, [rax+20h]
0x1800ff7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff7bf  mov     ebx, eax
0x1800ff7c1  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800ff7c5  call    cs:__imp_QueryPerformanceCounter
0x1800ff7cb  xorps   xmm6, xmm6
0x1800ff7ce  cmp     qword ptr [rdi+48h], 0
0x1800ff7d3  jz      short loc_1800FF7F7
0x1800ff7d5  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800ff7d9  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800ff7dd  cvtsi2ss xmm6, rcx
0x1800ff7e2  mulss   xmm6, cs:__real@447a0000
0x1800ff7ea  xorps   xmm0, xmm0
0x1800ff7ed  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800ff7f3  divss   xmm6, xmm0
0x1800ff7f7  mov     rcx, [rsp+8E0h+var_878]
0x1800ff7fc  cmp     dword ptr [rcx+8], 1
0x1800ff800  jnz     loc_1800FF8BC
0x1800ff806  mov     [rsp+8E0h+var_870], 0
0x1800ff80f  lea     rdx, [rsp+8E0h+var_870]
0x1800ff814  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800ff819  test    eax, eax
0x1800ff81b  js      loc_1800FF92D
0x1800ff821  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ff826  mov     r8, rax
0x1800ff829  mov     ecx, [rax]
0x1800ff82b  cmp     ecx, 4
0x1800ff82e  jbe     loc_1800FF92D
0x1800ff834  mov     [rbp+7E0h+arg_0], ebx
0x1800ff83a  movss   [rsp+8E0h+var_868], xmm6
0x1800ff840  mov     [rbp+7E0h+var_860], rdi
0x1800ff844  mov     rdx, [rsp+8E0h+var_870]
0x1800ff849  mov     ecx, [rdx+10h]
0x1800ff84c  mov     [rsp+8E0h+var_864], ecx
0x1800ff850  mov     ecx, [rdx+4]
0x1800ff853  mov     [rsp+8E0h+var_880], ecx
0x1800ff857  mov     eax, [rdx+8]
0x1800ff85a  mov     [rsp+8E0h+var_880+4], eax
0x1800ff85e  mov     eax, [rdx]
0x1800ff860  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800ff864  lea     rax, [rbp+7E0h+arg_0]
0x1800ff86b  mov     [rsp+8E0h+var_890], rax
0x1800ff870  lea     rax, [rsp+8E0h+var_868]
0x1800ff875  mov     [rsp+8E0h+var_898], rax
0x1800ff87a  lea     rax, [rbp+7E0h+var_860]
0x1800ff87e  mov     [rsp+8E0h+var_8A0], rax
0x1800ff883  lea     rax, [rsp+8E0h+var_864]
0x1800ff888  mov     [rsp+8E0h+var_8A8], rax
0x1800ff88d  lea     rax, [rsp+8E0h+var_880]
0x1800ff892  mov     [rsp+8E0h+var_8B0], rax
0x1800ff897  lea     rax, [rsp+8E0h+var_880+4]
0x1800ff89c  mov     [rsp+8E0h+var_8B8], rax
0x1800ff8a1  lea     rax, [rsp+8E0h+var_870]
0x1800ff8a6  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800ff8ab  lea     rdx, dword_180170A4C
0x1800ff8b2  mov     rcx, r8
0x1800ff8b5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ff8ba  jmp     short loc_1800FF92D
0x1800ff8bc  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ff8c1  mov     ecx, [rax]
0x1800ff8c3  cmp     ecx, 4
0x1800ff8c6  jbe     short loc_1800FF92D
0x1800ff8c8  mov     [rbp+7E0h+arg_0], ebx
0x1800ff8ce  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800ff8d4  mov     [rbp+7E0h+var_860], rdi
0x1800ff8d8  mov     rcx, [rsp+8E0h+var_878]
0x1800ff8dd  mov     edx, [rcx+8]
0x1800ff8e0  mov     [rsp+8E0h+var_880+4], edx
0x1800ff8e4  mov     ecx, [rdi+30h]
0x1800ff8e7  mov     [rsp+8E0h+var_880], ecx
0x1800ff8eb  lea     rcx, [rbp+7E0h+arg_0]
0x1800ff8f2  mov     [rsp+8E0h+var_8A0], rcx
0x1800ff8f7  lea     rcx, [rsp+8E0h+var_870]
0x1800ff8fc  mov     [rsp+8E0h+var_8A8], rcx
0x1800ff901  lea     rcx, [rbp+7E0h+var_860]
0x1800ff905  mov     [rsp+8E0h+var_8B0], rcx
0x1800ff90a  lea     rcx, [rsp+8E0h+var_880+4]
0x1800ff90f  mov     [rsp+8E0h+var_8B8], rcx
0x1800ff914  lea     rcx, [rsp+8E0h+var_880]
0x1800ff919  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800ff91e  lea     rdx, byte_1801709FF
0x1800ff925  mov     rcx, rax
0x1800ff928  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ff92d  mov     rcx, [rbp+7E8h]; this
0x1800ff934  test    ebx, ebx
0x1800ff936  jns     short loc_1800FF95B
0x1800ff938  mov     r9d, ebx; char *
0x1800ff93b  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ff942  mov     edx, 81h; void *
0x1800ff947  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ff94c  mov     rax, [rdi]
0x1800ff94f  mov     rcx, rdi
0x1800ff952  mov     rax, [rax+20h]
0x1800ff956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff95b  mov     ebx, [rdi+40h]
0x1800ff95e  test    ebx, ebx
0x1800ff960  jns     short loc_1800FF969
0x1800ff962  mov     edx, 8Ah
0x1800ff967  jmp     short loc_1800FF97A
0x1800ff969  mov     rcx, [rsp+8E0h+var_878]
0x1800ff96e  mov     ebx, [rcx+4]
0x1800ff971  test    ebx, ebx
0x1800ff973  jns     short loc_1800FF992
0x1800ff975  mov     edx, 8Ch; void *
0x1800ff97a  mov     r9d, ebx; char *
0x1800ff97d  mov     rcx, [rbp+7E8h]; this
0x1800ff984  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ff98b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ff990  jmp     short loc_1800FF9B0
0x1800ff992  mov     rdx, [rbp+7E0h+arg_20]
0x1800ff999  call    ??$CastTo@UXvmGetNativeStaticObjectTypeMask@@@XvmMessage@@QEAAJPEAPEAUXvmGetNativeStaticObjectTypeMask@@@Z; XvmMessage::CastTo<XvmGetNativeStaticObjectTypeMask>(XvmGetNativeStaticObjectTypeMask * *)
0x1800ff99e  mov     ebx, eax
0x1800ff9a0  test    eax, eax
0x1800ff9a2  jns     short loc_1800FF9AE
0x1800ff9a4  mov     r9d, eax
0x1800ff9a7  mov     edx, 8Dh
0x1800ff9ac  jmp     short loc_1800FF97D
0x1800ff9ae  xor     ebx, ebx
0x1800ff9b0  mov     rcx, [rbp+7E0h+arg_18]
0x1800ff9b7  mov     rax, [rsp+8E0h+var_878]
0x1800ff9bc  mov     [rcx], rax
0x1800ff9bf  mov     eax, ebx
0x1800ff9c1  lea     r11, [rsp+8E0h+var_10]
0x1800ff9c9  mov     rbx, [r11+28h]
0x1800ff9cd  mov     rsi, [r11+30h]
0x1800ff9d1  movaps  xmm6, xmmword ptr [r11-10h]
0x1800ff9d6  mov     rsp, r11
0x1800ff9d9  pop     r14
0x1800ff9db  pop     rdi
0x1800ff9dc  pop     rbp
0x1800ff9dd  retn
```
