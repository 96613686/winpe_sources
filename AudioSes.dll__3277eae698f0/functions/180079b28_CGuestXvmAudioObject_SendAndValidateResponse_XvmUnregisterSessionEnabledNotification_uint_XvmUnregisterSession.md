# CGuestXvmAudioObject::SendAndValidateResponse<XvmUnregisterSessionEnabledNotification>(uint,XvmUnregisterSessionEnabledNotification,XvmMessage * *,XvmUnregisterSessionEnabledNotification * *)

- ea: `0x180079b28`
- end: `0x180079e99`
- name: `??$SendAndValidateResponse@UXvmUnregisterSessionEnabledNotification@@@CGuestXvmAudioObject@@QEAAJIUXvmUnregisterSessionEnabledNotification@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `881`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800799b0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180079b28`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180079b6a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180079c55`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180079b6a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180079c55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180079b9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180079b9e`

## string_xrefs

- `0x180079b81`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x180079bc0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x180079dcb`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x180079e14`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x180079e4a`: `avcore\published\audiocore\include\CrossVmComm.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmUnregisterSessionEnabledNotification>(
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
  const struct _tlgProvider_t *v12; // rax
  int v13; // r9d
  const struct _tlgProvider_t *v14; // rax
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  int v19; // [rsp+28h] [rbp-E0h]
  _DWORD *v20; // [rsp+68h] [rbp-A0h] BYREF
  int v21[2]; // [rsp+70h] [rbp-98h] BYREF
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
  _QWORD *v39; // [rsp+918h] [rbp+810h]
  va_list va1; // [rsp+920h] [rbp+818h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v37 = va_arg(va1, _QWORD *);
  v39 = va_arg(va1, _QWORD *);
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
  v20 = v8;
  if ( v8 )
  {
    Src = 0;
    v33 = 0;
    memset_0(v34, 0, 0x800u);
    v34[0] = a3;
    v32 = 122;
    memcpy_0(v8, &Src, 0x810u);
    v20[3] = a2;
    va_copy(v28, va);
    v29 = &v20;
    v30 = 1;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _DWORD *, __int64))(**(_QWORD **)(a1 + 40) + 32LL))(
            *(_QWORD *)(a1 + 40),
            a2,
            v20,
            2064);
    QueryPerformanceCounter(&v26);
    v11 = 0.0;
    if ( *(_QWORD *)(a1 + 72) )
      v11 = (float)((float)(v26.LowPart - PerformanceCount.LowPart) * 1000.0) / (float)(int)*(_QWORD *)(a1 + 72);
    if ( v20[2] == 1 )
    {
      v22 = 0;
      if ( (int)XvmMessage::CastTo<XvmActivateProxyAudioObject>(v20, &v22) >= 0 )
      {
        v12 = GuestXvmAudioObjectTelemetryProvider::Provider();
        if ( *(_DWORD *)v12 > 4u )
        {
          v36 = v10;
          v23 = v11;
          v25 = a1;
          v24 = v22[4];
          v21[0] = v22[1];
          v21[1] = v22[2];
          LODWORD(v22) = *v22;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v12,
            (unsigned int)&word_1801676A6,
            (_DWORD)v12,
            v13,
            (__int64)&v22,
            (__int64)&v21[1],
            (__int64)v21,
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
        v21[1] = v20[2];
        v21[0] = *(_DWORD *)(a1 + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v14,
          (unsigned int)&byte_18016771F,
          v15,
          v16,
          (__int64)v21,
          (__int64)&v21[1],
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
      v9 = v20[1];
      if ( v9 >= 0 )
      {
        v18 = v39;
        *v39 = 0;
        if ( v20[2] == 122 )
        {
          *v18 = v20 + 4;
          v9 = 0;
          goto LABEL_23;
        }
        v9 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x308,
          (unsigned int)"avcore\\published\\audiocore\\include\\CrossVmComm.h",
          (const char *)0x80070057LL,
          v19);
        v17 = 141;
      }
      else
      {
        v17 = 140;
      }
    }
    else
    {
      v17 = 138;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
      (const char *)(unsigned int)v9,
      v19);
LABEL_23:
    *v37 = v20;
    return (unsigned int)v9;
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
0x180079b28  mov     rax, rsp
0x180079b2b  mov     [rax+10h], rbx
0x180079b2f  mov     [rax+18h], rsi
0x180079b33  mov     [rax+20h], r9
0x180079b37  push    rbp
0x180079b38  push    rdi
0x180079b39  push    r14
0x180079b3b  lea     rbp, [rax-7E8h]
0x180079b42  sub     rsp, 8D0h
0x180079b49  movaps  xmmword ptr [rax-28h], xmm6
0x180079b4d  mov     bl, r8b
0x180079b50  mov     r14d, edx
0x180079b53  mov     rdi, rcx
0x180079b56  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x180079b5e  mov     qword ptr [rbp+7E0h+var_858], 0
0x180079b66  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x180079b6a  call    cs:__imp_QueryPerformanceCounter
0x180079b70  mov     esi, [rdi+40h]
0x180079b73  test    esi, esi
0x180079b75  jns     short loc_180079B99
0x180079b77  mov     rcx, [rbp+7E8h]; this
0x180079b7e  mov     r9d, esi; char *
0x180079b81  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180079b88  mov     edx, 4Fh ; 'O'; void *
0x180079b8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079b92  mov     eax, esi
0x180079b94  jmp     loc_180079E7C
0x180079b99  mov     ecx, 810h; cb
0x180079b9e  call    cs:__imp_CoTaskMemAlloc
0x180079ba4  mov     rsi, rax
0x180079ba7  mov     [rsp+8E0h+var_880], rax
0x180079bac  test    rax, rax
0x180079baf  jnz     short loc_180079BD4
0x180079bb1  mov     rcx, [rbp+7E8h]; this
0x180079bb8  mov     ebx, 8007000Eh
0x180079bbd  mov     r9d, ebx; char *
0x180079bc0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180079bc7  lea     edx, [rax+52h]; void *
0x180079bca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079bcf  jmp     loc_180079E7A
0x180079bd4  mov     [rbp+7E0h+Src], 0
0x180079bdc  mov     [rbp+7E0h+var_824], 0
0x180079be3  xor     edx, edx; Val
0x180079be5  mov     r8d, 800h; Size
0x180079beb  lea     rcx, [rbp+7E0h+var_820]; void *
0x180079bef  call    memset_0
0x180079bf4  mov     [rbp+7E0h+var_820], bl
0x180079bf7  mov     [rbp+7E0h+var_828], 7Ah ; 'z'
0x180079bfe  mov     rcx, rsi; void *
0x180079c01  lea     rdx, [rbp+7E0h+Src]; Src
0x180079c05  mov     r8d, 810h; Size
0x180079c0b  call    memcpy_0
0x180079c10  mov     rax, [rsp+8E0h+var_880]
0x180079c15  mov     [rax+0Ch], r14d
0x180079c19  lea     rax, [rbp+7E0h+arg_18]
0x180079c20  mov     [rbp+7E0h+var_848], rax
0x180079c24  lea     rax, [rsp+8E0h+var_880]
0x180079c29  mov     [rbp+7E0h+var_840], rax
0x180079c2d  mov     [rbp+7E0h+var_838], 1
0x180079c31  mov     rcx, [rdi+28h]
0x180079c35  mov     rax, [rcx]
0x180079c38  mov     r9d, 810h
0x180079c3e  mov     r8, [rsp+8E0h+var_880]
0x180079c43  mov     edx, r14d
0x180079c46  mov     rax, [rax+20h]
0x180079c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079c4f  mov     ebx, eax
0x180079c51  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x180079c55  call    cs:__imp_QueryPerformanceCounter
0x180079c5b  xorps   xmm6, xmm6
0x180079c5e  cmp     qword ptr [rdi+48h], 0
0x180079c63  jz      short loc_180079C87
0x180079c65  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x180079c69  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x180079c6d  cvtsi2ss xmm6, rcx
0x180079c72  mulss   xmm6, cs:__real@447a0000
0x180079c7a  xorps   xmm0, xmm0
0x180079c7d  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x180079c83  divss   xmm6, xmm0
0x180079c87  mov     rcx, [rsp+8E0h+var_880]
0x180079c8c  cmp     dword ptr [rcx+8], 1
0x180079c90  jnz     loc_180079D4C
0x180079c96  mov     [rsp+8E0h+var_870], 0
0x180079c9f  lea     rdx, [rsp+8E0h+var_870]
0x180079ca4  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x180079ca9  test    eax, eax
0x180079cab  js      loc_180079DBD
0x180079cb1  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x180079cb6  mov     r8, rax
0x180079cb9  mov     ecx, [rax]
0x180079cbb  cmp     ecx, 4
0x180079cbe  jbe     loc_180079DBD
0x180079cc4  mov     [rbp+7E0h+arg_0], ebx
0x180079cca  movss   [rsp+8E0h+var_868], xmm6
0x180079cd0  mov     [rbp+7E0h+var_860], rdi
0x180079cd4  mov     rdx, [rsp+8E0h+var_870]
0x180079cd9  mov     ecx, [rdx+10h]
0x180079cdc  mov     [rsp+8E0h+var_864], ecx
0x180079ce0  mov     ecx, [rdx+4]
0x180079ce3  mov     [rsp+8E0h+var_878], ecx
0x180079ce7  mov     eax, [rdx+8]
0x180079cea  mov     [rsp+8E0h+var_878+4], eax
0x180079cee  mov     eax, [rdx]
0x180079cf0  mov     dword ptr [rsp+8E0h+var_870], eax
0x180079cf4  lea     rax, [rbp+7E0h+arg_0]
0x180079cfb  mov     [rsp+8E0h+var_890], rax
0x180079d00  lea     rax, [rsp+8E0h+var_868]
0x180079d05  mov     [rsp+8E0h+var_898], rax
0x180079d0a  lea     rax, [rbp+7E0h+var_860]
0x180079d0e  mov     [rsp+8E0h+var_8A0], rax
0x180079d13  lea     rax, [rsp+8E0h+var_864]
0x180079d18  mov     [rsp+8E0h+var_8A8], rax
0x180079d1d  lea     rax, [rsp+8E0h+var_878]
0x180079d22  mov     [rsp+8E0h+var_8B0], rax
0x180079d27  lea     rax, [rsp+8E0h+var_878+4]
0x180079d2c  mov     [rsp+8E0h+var_8B8], rax
0x180079d31  lea     rax, [rsp+8E0h+var_870]
0x180079d36  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x180079d3b  lea     rdx, word_1801676A6
0x180079d42  mov     rcx, r8
0x180079d45  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180079d4a  jmp     short loc_180079DBD
0x180079d4c  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x180079d51  mov     ecx, [rax]
0x180079d53  cmp     ecx, 4
0x180079d56  jbe     short loc_180079DBD
0x180079d58  mov     [rbp+7E0h+arg_0], ebx
0x180079d5e  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x180079d64  mov     [rbp+7E0h+var_860], rdi
0x180079d68  mov     rcx, [rsp+8E0h+var_880]
0x180079d6d  mov     edx, [rcx+8]
0x180079d70  mov     [rsp+8E0h+var_878+4], edx
0x180079d74  mov     ecx, [rdi+30h]
0x180079d77  mov     [rsp+8E0h+var_878], ecx
0x180079d7b  lea     rcx, [rbp+7E0h+arg_0]
0x180079d82  mov     [rsp+8E0h+var_8A0], rcx
0x180079d87  lea     rcx, [rsp+8E0h+var_870]
0x180079d8c  mov     [rsp+8E0h+var_8A8], rcx
0x180079d91  lea     rcx, [rbp+7E0h+var_860]
0x180079d95  mov     [rsp+8E0h+var_8B0], rcx
0x180079d9a  lea     rcx, [rsp+8E0h+var_878+4]
0x180079d9f  mov     [rsp+8E0h+var_8B8], rcx
0x180079da4  lea     rcx, [rsp+8E0h+var_878]
0x180079da9  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x180079dae  lea     rdx, byte_18016771F
0x180079db5  mov     rcx, rax
0x180079db8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180079dbd  mov     rcx, [rbp+7E8h]; this
0x180079dc4  test    ebx, ebx
0x180079dc6  jns     short loc_180079DEB
0x180079dc8  mov     r9d, ebx; char *
0x180079dcb  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180079dd2  mov     edx, 81h; void *
0x180079dd7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180079ddc  mov     rax, [rdi]
0x180079ddf  mov     rcx, rdi
0x180079de2  mov     rax, [rax+20h]
0x180079de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079deb  mov     ebx, [rdi+40h]
0x180079dee  test    ebx, ebx
0x180079df0  jns     short loc_180079DF9
0x180079df2  mov     edx, 8Ah
0x180079df7  jmp     short loc_180079E0A
0x180079df9  mov     rax, [rsp+8E0h+var_880]
0x180079dfe  mov     ebx, [rax+4]
0x180079e01  test    ebx, ebx
0x180079e03  jns     short loc_180079E22
0x180079e05  mov     edx, 8Ch; void *
0x180079e0a  mov     rcx, [rbp+7E8h]; this
0x180079e11  mov     r9d, ebx; char *
0x180079e14  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180079e1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079e20  jmp     short loc_180079E6B
0x180079e22  mov     rcx, [rbp+7E0h+arg_20]
0x180079e29  mov     qword ptr [rcx], 0
0x180079e30  mov     rax, [rsp+8E0h+var_880]
0x180079e35  cmp     dword ptr [rax+8], 7Ah ; 'z'
0x180079e39  jz      short loc_180079E62
0x180079e3b  mov     rcx, [rbp+7E8h]; this
0x180079e42  mov     ebx, 80070057h
0x180079e47  mov     r9d, ebx; char *
0x180079e4a  lea     r8, aAvcorePublishe_2; "avcore\\published\\audiocore\\include\\"...
0x180079e51  mov     edx, 308h; void *
0x180079e56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079e5b  mov     edx, 8Dh
0x180079e60  jmp     short loc_180079E0A
0x180079e62  add     rax, 10h
0x180079e66  mov     [rcx], rax
0x180079e69  xor     ebx, ebx
0x180079e6b  mov     rdx, [rbp+7E0h+arg_18]
0x180079e72  mov     rcx, [rsp+8E0h+var_880]
0x180079e77  mov     [rdx], rcx
0x180079e7a  mov     eax, ebx
0x180079e7c  lea     r11, [rsp+8E0h+var_10]
0x180079e84  mov     rbx, [r11+28h]
0x180079e88  mov     rsi, [r11+30h]
0x180079e8c  movaps  xmm6, xmmword ptr [r11-10h]
0x180079e91  mov     rsp, r11
0x180079e94  pop     r14
0x180079e96  pop     rdi
0x180079e97  pop     rbp
0x180079e98  retn
```
