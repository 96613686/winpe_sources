# CGuestXvmAudioObject::SendAndValidateResponse<XvmPostActivateSpatialAudioStream>(uint,XvmPostActivateSpatialAudioStream,XvmMessage * *,XvmPostActivateSpatialAudioStream * *)

- ea: `0x18010d3e8`
- end: `0x18010d72e`
- name: `??$SendAndValidateResponse@UXvmPostActivateSpatialAudioStream@@@CGuestXvmAudioObject@@QEAAJIUXvmPostActivateSpatialAudioStream@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007b2e8`
- `0x18008015c`
- `0x180082854`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1801021a0`
- `0x18010d3e8`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010d42a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010d515`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010d42a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010d515`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010d45e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010d45e`

## string_xrefs

- `0x18010d441`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18010d480`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18010d68b`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18010d6d4`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmPostActivateSpatialAudioStream>(
        __int64 a1,
        unsigned int a2,
        char a3,
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
  _BYTE v34[2064]; // [rsp+C8h] [rbp-40h] BYREF
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
    v32 = 57;
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
            (unsigned int)&unk_180172C6F,
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
          (unsigned int)&unk_180172A96,
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
        v18 = XvmMessage::CastTo<XvmPostActivateSpatialAudioStream>(v21, v39, v12);
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
0x18010d3e8  mov     rax, rsp
0x18010d3eb  mov     [rax+10h], rbx
0x18010d3ef  mov     [rax+18h], rsi
0x18010d3f3  mov     [rax+20h], r9
0x18010d3f7  push    rbp
0x18010d3f8  push    rdi
0x18010d3f9  push    r14
0x18010d3fb  lea     rbp, [rax-7E8h]
0x18010d402  sub     rsp, 8D0h
0x18010d409  movaps  xmmword ptr [rax-28h], xmm6
0x18010d40d  mov     bl, r8b
0x18010d410  mov     r14d, edx
0x18010d413  mov     rdi, rcx
0x18010d416  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x18010d41e  mov     qword ptr [rbp+7E0h+var_858], 0
0x18010d426  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x18010d42a  call    cs:__imp_QueryPerformanceCounter
0x18010d430  mov     esi, [rdi+40h]
0x18010d433  test    esi, esi
0x18010d435  jns     short loc_18010D459
0x18010d437  mov     rcx, [rbp+7E8h]; this
0x18010d43e  mov     r9d, esi; char *
0x18010d441  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010d448  mov     edx, 4Fh ; 'O'; void *
0x18010d44d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d452  mov     eax, esi
0x18010d454  jmp     loc_18010D711
0x18010d459  mov     ecx, 810h; cb
0x18010d45e  call    cs:__imp_CoTaskMemAlloc
0x18010d464  mov     rsi, rax
0x18010d467  mov     [rsp+8E0h+var_878], rax
0x18010d46c  test    rax, rax
0x18010d46f  jnz     short loc_18010D494
0x18010d471  mov     rcx, [rbp+7E8h]; this
0x18010d478  mov     ebx, 8007000Eh
0x18010d47d  mov     r9d, ebx; char *
0x18010d480  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010d487  lea     edx, [rax+52h]; void *
0x18010d48a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d48f  jmp     loc_18010D70F
0x18010d494  mov     [rbp+7E0h+Src], 0
0x18010d49c  mov     [rbp+7E0h+var_824], 0
0x18010d4a3  xor     edx, edx; Val
0x18010d4a5  mov     r8d, 800h; Size
0x18010d4ab  lea     rcx, [rbp+7E0h+var_820]; void *
0x18010d4af  call    memset_0
0x18010d4b4  mov     [rbp+7E0h+var_820], bl
0x18010d4b7  mov     [rbp+7E0h+var_828], 39h ; '9'
0x18010d4be  mov     rcx, rsi; void *
0x18010d4c1  lea     rdx, [rbp+7E0h+Src]; Src
0x18010d4c5  mov     r8d, 810h; Size
0x18010d4cb  call    memcpy_0
0x18010d4d0  mov     rax, [rsp+8E0h+var_878]
0x18010d4d5  mov     [rax+0Ch], r14d
0x18010d4d9  lea     rax, [rbp+7E0h+arg_18]
0x18010d4e0  mov     [rbp+7E0h+var_848], rax
0x18010d4e4  lea     rax, [rsp+8E0h+var_878]
0x18010d4e9  mov     [rbp+7E0h+var_840], rax
0x18010d4ed  mov     [rbp+7E0h+var_838], 1
0x18010d4f1  mov     rcx, [rdi+28h]
0x18010d4f5  mov     rax, [rcx]
0x18010d4f8  mov     r9d, 810h
0x18010d4fe  mov     r8, [rsp+8E0h+var_878]
0x18010d503  mov     edx, r14d
0x18010d506  mov     rax, [rax+20h]
0x18010d50a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d50f  mov     ebx, eax
0x18010d511  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x18010d515  call    cs:__imp_QueryPerformanceCounter
0x18010d51b  xorps   xmm6, xmm6
0x18010d51e  cmp     qword ptr [rdi+48h], 0
0x18010d523  jz      short loc_18010D547
0x18010d525  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x18010d529  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x18010d52d  cvtsi2ss xmm6, rcx
0x18010d532  mulss   xmm6, cs:__real@447a0000
0x18010d53a  xorps   xmm0, xmm0
0x18010d53d  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x18010d543  divss   xmm6, xmm0
0x18010d547  mov     rcx, [rsp+8E0h+var_878]
0x18010d54c  cmp     dword ptr [rcx+8], 1
0x18010d550  jnz     loc_18010D60C
0x18010d556  mov     [rsp+8E0h+var_870], 0
0x18010d55f  lea     rdx, [rsp+8E0h+var_870]
0x18010d564  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x18010d569  test    eax, eax
0x18010d56b  js      loc_18010D67D
0x18010d571  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x18010d576  mov     r8, rax
0x18010d579  mov     ecx, [rax]
0x18010d57b  cmp     ecx, 4
0x18010d57e  jbe     loc_18010D67D
0x18010d584  mov     [rbp+7E0h+arg_0], ebx
0x18010d58a  movss   [rsp+8E0h+var_868], xmm6
0x18010d590  mov     [rbp+7E0h+var_860], rdi
0x18010d594  mov     rdx, [rsp+8E0h+var_870]
0x18010d599  mov     ecx, [rdx+10h]
0x18010d59c  mov     [rsp+8E0h+var_864], ecx
0x18010d5a0  mov     ecx, [rdx+4]
0x18010d5a3  mov     [rsp+8E0h+var_880], ecx
0x18010d5a7  mov     eax, [rdx+8]
0x18010d5aa  mov     [rsp+8E0h+var_880+4], eax
0x18010d5ae  mov     eax, [rdx]
0x18010d5b0  mov     dword ptr [rsp+8E0h+var_870], eax
0x18010d5b4  lea     rax, [rbp+7E0h+arg_0]
0x18010d5bb  mov     [rsp+8E0h+var_890], rax
0x18010d5c0  lea     rax, [rsp+8E0h+var_868]
0x18010d5c5  mov     [rsp+8E0h+var_898], rax
0x18010d5ca  lea     rax, [rbp+7E0h+var_860]
0x18010d5ce  mov     [rsp+8E0h+var_8A0], rax
0x18010d5d3  lea     rax, [rsp+8E0h+var_864]
0x18010d5d8  mov     [rsp+8E0h+var_8A8], rax
0x18010d5dd  lea     rax, [rsp+8E0h+var_880]
0x18010d5e2  mov     [rsp+8E0h+var_8B0], rax
0x18010d5e7  lea     rax, [rsp+8E0h+var_880+4]
0x18010d5ec  mov     [rsp+8E0h+var_8B8], rax
0x18010d5f1  lea     rax, [rsp+8E0h+var_870]
0x18010d5f6  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x18010d5fb  lea     rdx, unk_180172C6F
0x18010d602  mov     rcx, r8
0x18010d605  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18010d60a  jmp     short loc_18010D67D
0x18010d60c  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x18010d611  mov     ecx, [rax]
0x18010d613  cmp     ecx, 4
0x18010d616  jbe     short loc_18010D67D
0x18010d618  mov     [rbp+7E0h+arg_0], ebx
0x18010d61e  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x18010d624  mov     [rbp+7E0h+var_860], rdi
0x18010d628  mov     rcx, [rsp+8E0h+var_878]
0x18010d62d  mov     edx, [rcx+8]
0x18010d630  mov     [rsp+8E0h+var_880+4], edx
0x18010d634  mov     ecx, [rdi+30h]
0x18010d637  mov     [rsp+8E0h+var_880], ecx
0x18010d63b  lea     rcx, [rbp+7E0h+arg_0]
0x18010d642  mov     [rsp+8E0h+var_8A0], rcx
0x18010d647  lea     rcx, [rsp+8E0h+var_870]
0x18010d64c  mov     [rsp+8E0h+var_8A8], rcx
0x18010d651  lea     rcx, [rbp+7E0h+var_860]
0x18010d655  mov     [rsp+8E0h+var_8B0], rcx
0x18010d65a  lea     rcx, [rsp+8E0h+var_880+4]
0x18010d65f  mov     [rsp+8E0h+var_8B8], rcx
0x18010d664  lea     rcx, [rsp+8E0h+var_880]
0x18010d669  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x18010d66e  lea     rdx, unk_180172A96
0x18010d675  mov     rcx, rax
0x18010d678  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18010d67d  mov     rcx, [rbp+7E8h]; this
0x18010d684  test    ebx, ebx
0x18010d686  jns     short loc_18010D6AB
0x18010d688  mov     r9d, ebx; char *
0x18010d68b  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010d692  mov     edx, 81h; void *
0x18010d697  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010d69c  mov     rax, [rdi]
0x18010d69f  mov     rcx, rdi
0x18010d6a2  mov     rax, [rax+20h]
0x18010d6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d6ab  mov     ebx, [rdi+40h]
0x18010d6ae  test    ebx, ebx
0x18010d6b0  jns     short loc_18010D6B9
0x18010d6b2  mov     edx, 8Ah
0x18010d6b7  jmp     short loc_18010D6CA
0x18010d6b9  mov     rcx, [rsp+8E0h+var_878]
0x18010d6be  mov     ebx, [rcx+4]
0x18010d6c1  test    ebx, ebx
0x18010d6c3  jns     short loc_18010D6E2
0x18010d6c5  mov     edx, 8Ch; void *
0x18010d6ca  mov     r9d, ebx; char *
0x18010d6cd  mov     rcx, [rbp+7E8h]; this
0x18010d6d4  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010d6db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d6e0  jmp     short loc_18010D700
0x18010d6e2  mov     rdx, [rbp+7E0h+arg_20]
0x18010d6e9  call    ??$CastTo@UXvmPostActivateSpatialAudioStream@@@XvmMessage@@QEAAJPEAPEAUXvmPostActivateSpatialAudioStream@@@Z; XvmMessage::CastTo<XvmPostActivateSpatialAudioStream>(XvmPostActivateSpatialAudioStream * *)
0x18010d6ee  mov     ebx, eax
0x18010d6f0  test    eax, eax
0x18010d6f2  jns     short loc_18010D6FE
0x18010d6f4  mov     r9d, eax
0x18010d6f7  mov     edx, 8Dh
0x18010d6fc  jmp     short loc_18010D6CD
0x18010d6fe  xor     ebx, ebx
0x18010d700  mov     rcx, [rbp+7E0h+arg_18]
0x18010d707  mov     rax, [rsp+8E0h+var_878]
0x18010d70c  mov     [rcx], rax
0x18010d70f  mov     eax, ebx
0x18010d711  lea     r11, [rsp+8E0h+var_10]
0x18010d719  mov     rbx, [r11+28h]
0x18010d71d  mov     rsi, [r11+30h]
0x18010d721  movaps  xmm6, xmmword ptr [r11-10h]
0x18010d726  mov     rsp, r11
0x18010d729  pop     r14
0x18010d72b  pop     rdi
0x18010d72c  pop     rbp
0x18010d72d  retn
```
