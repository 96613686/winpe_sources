# CGuestXvmAudioObject::SendAndValidateResponse<XvmInitializeSharedAudioStream>(uint,XvmInitializeSharedAudioStream,XvmMessage * *,XvmInitializeSharedAudioStream * *)

- ea: `0x1800ad184`
- end: `0x1800ad4d6`
- name: `??$SendAndValidateResponse@UXvmInitializeSharedAudioStream@@@CGuestXvmAudioObject@@QEAAJIUXvmInitializeSharedAudioStream@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `850`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b0690`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2bf0`
- `0x1800ad184`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad1c5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad2bd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad1c5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad2bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ad1f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ad1f9`

## string_xrefs

- `0x1800ad1dc`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ad21b`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ad433`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ad47c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmInitializeSharedAudioStream>(
        __int64 a1,
        unsigned int a2,
        const void *a3,
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
    memcpy_0(v34, a3, 0x524u);
    v32 = 15;
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
            (unsigned int)byte_180165CC1,
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
          (unsigned int)&byte_180165C27,
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
        v18 = XvmMessage::CastTo<XvmInitializeSharedAudioStream>(v21, v39, v12);
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
0x1800ad184  mov     rax, rsp
0x1800ad187  mov     [rax+10h], rbx
0x1800ad18b  mov     [rax+18h], rsi
0x1800ad18f  mov     [rax+20h], r9
0x1800ad193  push    rbp
0x1800ad194  push    rdi
0x1800ad195  push    r14
0x1800ad197  lea     rbp, [rax-7E8h]
0x1800ad19e  sub     rsp, 8D0h
0x1800ad1a5  movaps  xmmword ptr [rax-28h], xmm6
0x1800ad1a9  mov     r14, r8
0x1800ad1ac  mov     esi, edx
0x1800ad1ae  mov     rbx, rcx
0x1800ad1b1  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800ad1b9  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800ad1c1  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800ad1c5  call    cs:__imp_QueryPerformanceCounter
0x1800ad1cb  mov     edi, [rbx+40h]
0x1800ad1ce  test    edi, edi
0x1800ad1d0  jns     short loc_1800AD1F4
0x1800ad1d2  mov     rcx, [rbp+7E8h]; this
0x1800ad1d9  mov     r9d, edi; char *
0x1800ad1dc  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ad1e3  mov     edx, 4Fh ; 'O'; void *
0x1800ad1e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad1ed  mov     eax, edi
0x1800ad1ef  jmp     loc_1800AD4B9
0x1800ad1f4  mov     ecx, 810h; cb
0x1800ad1f9  call    cs:__imp_CoTaskMemAlloc
0x1800ad1ff  mov     rdi, rax
0x1800ad202  mov     [rsp+8E0h+var_878], rax
0x1800ad207  test    rax, rax
0x1800ad20a  jnz     short loc_1800AD22F
0x1800ad20c  mov     rcx, [rbp+7E8h]; this
0x1800ad213  mov     ebx, 8007000Eh
0x1800ad218  mov     r9d, ebx; char *
0x1800ad21b  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ad222  lea     edx, [rax+52h]; void *
0x1800ad225  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad22a  jmp     loc_1800AD4B7
0x1800ad22f  mov     [rbp+7E0h+Src], 0
0x1800ad237  mov     [rbp+7E0h+var_824], 0
0x1800ad23e  xor     edx, edx; Val
0x1800ad240  mov     r8d, 800h; Size
0x1800ad246  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800ad24a  call    memset_0
0x1800ad24f  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800ad253  mov     rdx, r14; Src
0x1800ad256  mov     r8d, 524h; Size
0x1800ad25c  call    memcpy_0
0x1800ad261  mov     [rbp+7E0h+var_828], 0Fh
0x1800ad268  mov     rcx, rdi; void *
0x1800ad26b  lea     rdx, [rbp+7E0h+Src]; Src
0x1800ad26f  mov     r8d, 810h; Size
0x1800ad275  call    memcpy_0
0x1800ad27a  mov     rax, [rsp+8E0h+var_878]
0x1800ad27f  mov     [rax+0Ch], esi
0x1800ad282  lea     rax, [rbp+7E0h+arg_18]
0x1800ad289  mov     [rbp+7E0h+var_848], rax
0x1800ad28d  lea     rax, [rsp+8E0h+var_878]
0x1800ad292  mov     [rbp+7E0h+var_840], rax
0x1800ad296  mov     [rbp+7E0h+var_838], 1
0x1800ad29a  mov     rcx, [rbx+28h]
0x1800ad29e  mov     rax, [rcx]
0x1800ad2a1  mov     r9d, 810h
0x1800ad2a7  mov     r8, [rsp+8E0h+var_878]
0x1800ad2ac  mov     edx, esi
0x1800ad2ae  mov     rax, [rax+20h]
0x1800ad2b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad2b7  mov     edi, eax
0x1800ad2b9  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800ad2bd  call    cs:__imp_QueryPerformanceCounter
0x1800ad2c3  xorps   xmm6, xmm6
0x1800ad2c6  cmp     qword ptr [rbx+48h], 0
0x1800ad2cb  jz      short loc_1800AD2EF
0x1800ad2cd  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800ad2d1  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800ad2d5  cvtsi2ss xmm6, rcx
0x1800ad2da  mulss   xmm6, cs:__real@447a0000
0x1800ad2e2  xorps   xmm0, xmm0
0x1800ad2e5  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800ad2eb  divss   xmm6, xmm0
0x1800ad2ef  mov     rcx, [rsp+8E0h+var_878]
0x1800ad2f4  cmp     dword ptr [rcx+8], 1
0x1800ad2f8  jnz     loc_1800AD3B4
0x1800ad2fe  mov     [rsp+8E0h+var_870], 0
0x1800ad307  lea     rdx, [rsp+8E0h+var_870]
0x1800ad30c  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800ad311  test    eax, eax
0x1800ad313  js      loc_1800AD425
0x1800ad319  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ad31e  mov     r8, rax
0x1800ad321  mov     ecx, [rax]
0x1800ad323  cmp     ecx, 4
0x1800ad326  jbe     loc_1800AD425
0x1800ad32c  mov     [rbp+7E0h+arg_0], edi
0x1800ad332  movss   [rsp+8E0h+var_868], xmm6
0x1800ad338  mov     [rbp+7E0h+var_860], rbx
0x1800ad33c  mov     rdx, [rsp+8E0h+var_870]
0x1800ad341  mov     ecx, [rdx+10h]
0x1800ad344  mov     [rsp+8E0h+var_864], ecx
0x1800ad348  mov     ecx, [rdx+4]
0x1800ad34b  mov     [rsp+8E0h+var_880], ecx
0x1800ad34f  mov     eax, [rdx+8]
0x1800ad352  mov     [rsp+8E0h+var_880+4], eax
0x1800ad356  mov     eax, [rdx]
0x1800ad358  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800ad35c  lea     rax, [rbp+7E0h+arg_0]
0x1800ad363  mov     [rsp+8E0h+var_890], rax
0x1800ad368  lea     rax, [rsp+8E0h+var_868]
0x1800ad36d  mov     [rsp+8E0h+var_898], rax
0x1800ad372  lea     rax, [rbp+7E0h+var_860]
0x1800ad376  mov     [rsp+8E0h+var_8A0], rax
0x1800ad37b  lea     rax, [rsp+8E0h+var_864]
0x1800ad380  mov     [rsp+8E0h+var_8A8], rax
0x1800ad385  lea     rax, [rsp+8E0h+var_880]
0x1800ad38a  mov     [rsp+8E0h+var_8B0], rax
0x1800ad38f  lea     rax, [rsp+8E0h+var_880+4]
0x1800ad394  mov     [rsp+8E0h+var_8B8], rax
0x1800ad399  lea     rax, [rsp+8E0h+var_870]
0x1800ad39e  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800ad3a3  lea     rdx, byte_180165CC1
0x1800ad3aa  mov     rcx, r8
0x1800ad3ad  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ad3b2  jmp     short loc_1800AD425
0x1800ad3b4  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ad3b9  mov     ecx, [rax]
0x1800ad3bb  cmp     ecx, 4
0x1800ad3be  jbe     short loc_1800AD425
0x1800ad3c0  mov     [rbp+7E0h+arg_0], edi
0x1800ad3c6  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800ad3cc  mov     [rbp+7E0h+var_860], rbx
0x1800ad3d0  mov     rcx, [rsp+8E0h+var_878]
0x1800ad3d5  mov     edx, [rcx+8]
0x1800ad3d8  mov     [rsp+8E0h+var_880+4], edx
0x1800ad3dc  mov     ecx, [rbx+30h]
0x1800ad3df  mov     [rsp+8E0h+var_880], ecx
0x1800ad3e3  lea     rcx, [rbp+7E0h+arg_0]
0x1800ad3ea  mov     [rsp+8E0h+var_8A0], rcx
0x1800ad3ef  lea     rcx, [rsp+8E0h+var_870]
0x1800ad3f4  mov     [rsp+8E0h+var_8A8], rcx
0x1800ad3f9  lea     rcx, [rbp+7E0h+var_860]
0x1800ad3fd  mov     [rsp+8E0h+var_8B0], rcx
0x1800ad402  lea     rcx, [rsp+8E0h+var_880+4]
0x1800ad407  mov     [rsp+8E0h+var_8B8], rcx
0x1800ad40c  lea     rcx, [rsp+8E0h+var_880]
0x1800ad411  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800ad416  lea     rdx, byte_180165C27
0x1800ad41d  mov     rcx, rax
0x1800ad420  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ad425  mov     rcx, [rbp+7E8h]; this
0x1800ad42c  test    edi, edi
0x1800ad42e  jns     short loc_1800AD453
0x1800ad430  mov     r9d, edi; char *
0x1800ad433  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ad43a  mov     edx, 81h; void *
0x1800ad43f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ad444  mov     rax, [rbx]
0x1800ad447  mov     rcx, rbx
0x1800ad44a  mov     rax, [rax+20h]
0x1800ad44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad453  mov     ebx, [rbx+40h]
0x1800ad456  test    ebx, ebx
0x1800ad458  jns     short loc_1800AD461
0x1800ad45a  mov     edx, 8Ah
0x1800ad45f  jmp     short loc_1800AD472
0x1800ad461  mov     rcx, [rsp+8E0h+var_878]
0x1800ad466  mov     ebx, [rcx+4]
0x1800ad469  test    ebx, ebx
0x1800ad46b  jns     short loc_1800AD48A
0x1800ad46d  mov     edx, 8Ch; void *
0x1800ad472  mov     r9d, ebx; char *
0x1800ad475  mov     rcx, [rbp+7E8h]; this
0x1800ad47c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ad483  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad488  jmp     short loc_1800AD4A8
0x1800ad48a  mov     rdx, [rbp+7E0h+arg_20]
0x1800ad491  call    ??$CastTo@UXvmInitializeSharedAudioStream@@@XvmMessage@@QEAAJPEAPEAUXvmInitializeSharedAudioStream@@@Z; XvmMessage::CastTo<XvmInitializeSharedAudioStream>(XvmInitializeSharedAudioStream * *)
0x1800ad496  mov     ebx, eax
0x1800ad498  test    eax, eax
0x1800ad49a  jns     short loc_1800AD4A6
0x1800ad49c  mov     r9d, eax
0x1800ad49f  mov     edx, 8Dh
0x1800ad4a4  jmp     short loc_1800AD475
0x1800ad4a6  xor     ebx, ebx
0x1800ad4a8  mov     rcx, [rbp+7E0h+arg_18]
0x1800ad4af  mov     rax, [rsp+8E0h+var_878]
0x1800ad4b4  mov     [rcx], rax
0x1800ad4b7  mov     eax, ebx
0x1800ad4b9  lea     r11, [rsp+8E0h+var_10]
0x1800ad4c1  mov     rbx, [r11+28h]
0x1800ad4c5  mov     rsi, [r11+30h]
0x1800ad4c9  movaps  xmm6, xmmword ptr [r11-10h]
0x1800ad4ce  mov     rsp, r11
0x1800ad4d1  pop     r14
0x1800ad4d3  pop     rdi
0x1800ad4d4  pop     rbp
0x1800ad4d5  retn
```
