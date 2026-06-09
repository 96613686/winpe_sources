# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetStaticObjectPosition>(uint,XvmGetStaticObjectPosition,XvmMessage * *,XvmGetStaticObjectPosition * *)

- ea: `0x1800ff9e4`
- end: `0x1800ffd36`
- name: `??$SendAndValidateResponse@UXvmGetStaticObjectPosition@@@CGuestXvmAudioObject@@QEAAJIUXvmGetStaticObjectPosition@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `850`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180101720`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800fa1fc`
- `0x1800ff9e4`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ffa26`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ffb1d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ffa26`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ffb1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ffa5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ffa5a`

## string_xrefs

- `0x1800ffa3d`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ffa7c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ffc93`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ffcdc`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetStaticObjectPosition>(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3,
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
  int StaticObject; // eax
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
    v34[0] = *a3;
    v34[1] = a3[1];
    v32 = 48;
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
            (unsigned int)&unk_180170DB1,
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
          (unsigned int)&unk_180170D64,
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
        StaticObject = XvmMessage::CastTo<XvmGetStaticObjectPosition>(v21, v39, v12);
        v9 = StaticObject;
        if ( StaticObject >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)StaticObject;
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
0x1800ff9e4  mov     rax, rsp
0x1800ff9e7  mov     [rax+10h], rbx
0x1800ff9eb  mov     [rax+18h], rsi
0x1800ff9ef  mov     [rax+20h], r9
0x1800ff9f3  push    rbp
0x1800ff9f4  push    rdi
0x1800ff9f5  push    r14
0x1800ff9f7  lea     rbp, [rax-7E8h]
0x1800ff9fe  sub     rsp, 8D0h
0x1800ffa05  movaps  xmmword ptr [rax-28h], xmm6
0x1800ffa09  mov     rsi, r8
0x1800ffa0c  mov     r14d, edx
0x1800ffa0f  mov     rbx, rcx
0x1800ffa12  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800ffa1a  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800ffa22  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800ffa26  call    cs:__imp_QueryPerformanceCounter
0x1800ffa2c  mov     edi, [rbx+40h]
0x1800ffa2f  test    edi, edi
0x1800ffa31  jns     short loc_1800FFA55
0x1800ffa33  mov     rcx, [rbp+7E8h]; this
0x1800ffa3a  mov     r9d, edi; char *
0x1800ffa3d  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ffa44  mov     edx, 4Fh ; 'O'; void *
0x1800ffa49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ffa4e  mov     eax, edi
0x1800ffa50  jmp     loc_1800FFD19
0x1800ffa55  mov     ecx, 810h; cb
0x1800ffa5a  call    cs:__imp_CoTaskMemAlloc
0x1800ffa60  mov     rdi, rax
0x1800ffa63  mov     [rsp+8E0h+var_878], rax
0x1800ffa68  test    rax, rax
0x1800ffa6b  jnz     short loc_1800FFA90
0x1800ffa6d  mov     rcx, [rbp+7E8h]; this
0x1800ffa74  mov     ebx, 8007000Eh
0x1800ffa79  mov     r9d, ebx; char *
0x1800ffa7c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ffa83  lea     edx, [rax+52h]; void *
0x1800ffa86  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ffa8b  jmp     loc_1800FFD17
0x1800ffa90  mov     [rbp+7E0h+Src], 0
0x1800ffa98  mov     [rbp+7E0h+var_824], 0
0x1800ffa9f  xor     edx, edx; Val
0x1800ffaa1  mov     r8d, 800h; Size
0x1800ffaa7  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800ffaab  call    memset_0
0x1800ffab0  mov     rax, [rsi]
0x1800ffab3  mov     [rbp+7E0h+var_820], rax
0x1800ffab7  mov     rax, [rsi+8]
0x1800ffabb  mov     [rbp+7E0h+var_818], rax
0x1800ffabf  mov     [rbp+7E0h+var_828], 30h ; '0'
0x1800ffac6  mov     rcx, rdi; void *
0x1800ffac9  lea     rdx, [rbp+7E0h+Src]; Src
0x1800ffacd  mov     r8d, 810h; Size
0x1800ffad3  call    memcpy_0
0x1800ffad8  mov     rax, [rsp+8E0h+var_878]
0x1800ffadd  mov     [rax+0Ch], r14d
0x1800ffae1  lea     rax, [rbp+7E0h+arg_18]
0x1800ffae8  mov     [rbp+7E0h+var_848], rax
0x1800ffaec  lea     rax, [rsp+8E0h+var_878]
0x1800ffaf1  mov     [rbp+7E0h+var_840], rax
0x1800ffaf5  mov     [rbp+7E0h+var_838], 1
0x1800ffaf9  mov     rcx, [rbx+28h]
0x1800ffafd  mov     rax, [rcx]
0x1800ffb00  mov     r9d, 810h
0x1800ffb06  mov     r8, [rsp+8E0h+var_878]
0x1800ffb0b  mov     edx, r14d
0x1800ffb0e  mov     rax, [rax+20h]
0x1800ffb12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffb17  mov     edi, eax
0x1800ffb19  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800ffb1d  call    cs:__imp_QueryPerformanceCounter
0x1800ffb23  xorps   xmm6, xmm6
0x1800ffb26  cmp     qword ptr [rbx+48h], 0
0x1800ffb2b  jz      short loc_1800FFB4F
0x1800ffb2d  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800ffb31  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800ffb35  cvtsi2ss xmm6, rcx
0x1800ffb3a  mulss   xmm6, cs:__real@447a0000
0x1800ffb42  xorps   xmm0, xmm0
0x1800ffb45  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800ffb4b  divss   xmm6, xmm0
0x1800ffb4f  mov     rcx, [rsp+8E0h+var_878]
0x1800ffb54  cmp     dword ptr [rcx+8], 1
0x1800ffb58  jnz     loc_1800FFC14
0x1800ffb5e  mov     [rsp+8E0h+var_870], 0
0x1800ffb67  lea     rdx, [rsp+8E0h+var_870]
0x1800ffb6c  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800ffb71  test    eax, eax
0x1800ffb73  js      loc_1800FFC85
0x1800ffb79  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ffb7e  mov     r8, rax
0x1800ffb81  mov     ecx, [rax]
0x1800ffb83  cmp     ecx, 4
0x1800ffb86  jbe     loc_1800FFC85
0x1800ffb8c  mov     [rbp+7E0h+arg_0], edi
0x1800ffb92  movss   [rsp+8E0h+var_868], xmm6
0x1800ffb98  mov     [rbp+7E0h+var_860], rbx
0x1800ffb9c  mov     rdx, [rsp+8E0h+var_870]
0x1800ffba1  mov     ecx, [rdx+10h]
0x1800ffba4  mov     [rsp+8E0h+var_864], ecx
0x1800ffba8  mov     ecx, [rdx+4]
0x1800ffbab  mov     [rsp+8E0h+var_880], ecx
0x1800ffbaf  mov     eax, [rdx+8]
0x1800ffbb2  mov     [rsp+8E0h+var_880+4], eax
0x1800ffbb6  mov     eax, [rdx]
0x1800ffbb8  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800ffbbc  lea     rax, [rbp+7E0h+arg_0]
0x1800ffbc3  mov     [rsp+8E0h+var_890], rax
0x1800ffbc8  lea     rax, [rsp+8E0h+var_868]
0x1800ffbcd  mov     [rsp+8E0h+var_898], rax
0x1800ffbd2  lea     rax, [rbp+7E0h+var_860]
0x1800ffbd6  mov     [rsp+8E0h+var_8A0], rax
0x1800ffbdb  lea     rax, [rsp+8E0h+var_864]
0x1800ffbe0  mov     [rsp+8E0h+var_8A8], rax
0x1800ffbe5  lea     rax, [rsp+8E0h+var_880]
0x1800ffbea  mov     [rsp+8E0h+var_8B0], rax
0x1800ffbef  lea     rax, [rsp+8E0h+var_880+4]
0x1800ffbf4  mov     [rsp+8E0h+var_8B8], rax
0x1800ffbf9  lea     rax, [rsp+8E0h+var_870]
0x1800ffbfe  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800ffc03  lea     rdx, unk_180170DB1
0x1800ffc0a  mov     rcx, r8
0x1800ffc0d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ffc12  jmp     short loc_1800FFC85
0x1800ffc14  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ffc19  mov     ecx, [rax]
0x1800ffc1b  cmp     ecx, 4
0x1800ffc1e  jbe     short loc_1800FFC85
0x1800ffc20  mov     [rbp+7E0h+arg_0], edi
0x1800ffc26  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800ffc2c  mov     [rbp+7E0h+var_860], rbx
0x1800ffc30  mov     rcx, [rsp+8E0h+var_878]
0x1800ffc35  mov     edx, [rcx+8]
0x1800ffc38  mov     [rsp+8E0h+var_880+4], edx
0x1800ffc3c  mov     ecx, [rbx+30h]
0x1800ffc3f  mov     [rsp+8E0h+var_880], ecx
0x1800ffc43  lea     rcx, [rbp+7E0h+arg_0]
0x1800ffc4a  mov     [rsp+8E0h+var_8A0], rcx
0x1800ffc4f  lea     rcx, [rsp+8E0h+var_870]
0x1800ffc54  mov     [rsp+8E0h+var_8A8], rcx
0x1800ffc59  lea     rcx, [rbp+7E0h+var_860]
0x1800ffc5d  mov     [rsp+8E0h+var_8B0], rcx
0x1800ffc62  lea     rcx, [rsp+8E0h+var_880+4]
0x1800ffc67  mov     [rsp+8E0h+var_8B8], rcx
0x1800ffc6c  lea     rcx, [rsp+8E0h+var_880]
0x1800ffc71  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800ffc76  lea     rdx, unk_180170D64
0x1800ffc7d  mov     rcx, rax
0x1800ffc80  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ffc85  mov     rcx, [rbp+7E8h]; this
0x1800ffc8c  test    edi, edi
0x1800ffc8e  jns     short loc_1800FFCB3
0x1800ffc90  mov     r9d, edi; char *
0x1800ffc93  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ffc9a  mov     edx, 81h; void *
0x1800ffc9f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ffca4  mov     rax, [rbx]
0x1800ffca7  mov     rcx, rbx
0x1800ffcaa  mov     rax, [rax+20h]
0x1800ffcae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ffcb3  mov     ebx, [rbx+40h]
0x1800ffcb6  test    ebx, ebx
0x1800ffcb8  jns     short loc_1800FFCC1
0x1800ffcba  mov     edx, 8Ah
0x1800ffcbf  jmp     short loc_1800FFCD2
0x1800ffcc1  mov     rcx, [rsp+8E0h+var_878]
0x1800ffcc6  mov     ebx, [rcx+4]
0x1800ffcc9  test    ebx, ebx
0x1800ffccb  jns     short loc_1800FFCEA
0x1800ffccd  mov     edx, 8Ch; void *
0x1800ffcd2  mov     r9d, ebx; char *
0x1800ffcd5  mov     rcx, [rbp+7E8h]; this
0x1800ffcdc  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ffce3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ffce8  jmp     short loc_1800FFD08
0x1800ffcea  mov     rdx, [rbp+7E0h+arg_20]
0x1800ffcf1  call    ??$CastTo@UXvmGetStaticObjectPosition@@@XvmMessage@@QEAAJPEAPEAUXvmGetStaticObjectPosition@@@Z; XvmMessage::CastTo<XvmGetStaticObjectPosition>(XvmGetStaticObjectPosition * *)
0x1800ffcf6  mov     ebx, eax
0x1800ffcf8  test    eax, eax
0x1800ffcfa  jns     short loc_1800FFD06
0x1800ffcfc  mov     r9d, eax
0x1800ffcff  mov     edx, 8Dh
0x1800ffd04  jmp     short loc_1800FFCD5
0x1800ffd06  xor     ebx, ebx
0x1800ffd08  mov     rcx, [rbp+7E0h+arg_18]
0x1800ffd0f  mov     rax, [rsp+8E0h+var_878]
0x1800ffd14  mov     [rcx], rax
0x1800ffd17  mov     eax, ebx
0x1800ffd19  lea     r11, [rsp+8E0h+var_10]
0x1800ffd21  mov     rbx, [r11+28h]
0x1800ffd25  mov     rsi, [r11+30h]
0x1800ffd29  movaps  xmm6, xmmword ptr [r11-10h]
0x1800ffd2e  mov     rsp, r11
0x1800ffd31  pop     r14
0x1800ffd33  pop     rdi
0x1800ffd34  pop     rbp
0x1800ffd35  retn
```
