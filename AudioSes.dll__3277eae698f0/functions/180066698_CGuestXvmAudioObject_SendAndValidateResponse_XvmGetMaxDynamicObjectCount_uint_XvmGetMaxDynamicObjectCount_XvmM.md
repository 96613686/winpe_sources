# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetMaxDynamicObjectCount>(uint,XvmGetMaxDynamicObjectCount,XvmMessage * *,XvmGetMaxDynamicObjectCount * *)

- ea: `0x180066698`
- end: `0x1800669de`
- name: `??$SendAndValidateResponse@UXvmGetMaxDynamicObjectCount@@@CGuestXvmAudioObject@@QEAAJIUXvmGetMaxDynamicObjectCount@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180101110`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x180066698`
- `0x18007731c`
- `0x180079754`
- `0x18007a2b4`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800666da`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800667c5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800666da`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800667c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006670e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18006670e`

## string_xrefs

- `0x1800666f1`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x180066730`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18006693b`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x180066984`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetMaxDynamicObjectCount>(
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
  int MaxDynamicObject; // eax
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
    v32 = 50;
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
            (unsigned int)byte_180170C25,
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
          (unsigned int)qword_180170EF0,
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
        MaxDynamicObject = XvmMessage::CastTo<XvmGetMaxDynamicObjectCount>(v21, v39, v12);
        v9 = MaxDynamicObject;
        if ( MaxDynamicObject >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)MaxDynamicObject;
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
0x180066698  mov     rax, rsp
0x18006669b  mov     [rax+10h], rbx
0x18006669f  mov     [rax+18h], rsi
0x1800666a3  mov     [rax+20h], r9
0x1800666a7  push    rbp
0x1800666a8  push    rdi
0x1800666a9  push    r14
0x1800666ab  lea     rbp, [rax-7E8h]
0x1800666b2  sub     rsp, 8D0h
0x1800666b9  movaps  xmmword ptr [rax-28h], xmm6
0x1800666bd  mov     ebx, r8d
0x1800666c0  mov     r14d, edx
0x1800666c3  mov     rdi, rcx
0x1800666c6  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800666ce  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800666d6  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800666da  call    cs:__imp_QueryPerformanceCounter
0x1800666e0  mov     esi, [rdi+40h]
0x1800666e3  test    esi, esi
0x1800666e5  jns     short loc_180066709
0x1800666e7  mov     rcx, [rbp+7E8h]; this
0x1800666ee  mov     r9d, esi; char *
0x1800666f1  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800666f8  mov     edx, 4Fh ; 'O'; void *
0x1800666fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066702  mov     eax, esi
0x180066704  jmp     loc_1800669C1
0x180066709  mov     ecx, 810h; cb
0x18006670e  call    cs:__imp_CoTaskMemAlloc
0x180066714  mov     rsi, rax
0x180066717  mov     [rsp+8E0h+var_878], rax
0x18006671c  test    rax, rax
0x18006671f  jnz     short loc_180066744
0x180066721  mov     rcx, [rbp+7E8h]; this
0x180066728  mov     ebx, 8007000Eh
0x18006672d  mov     r9d, ebx; char *
0x180066730  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180066737  lea     edx, [rax+52h]; void *
0x18006673a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006673f  jmp     loc_1800669BF
0x180066744  mov     [rbp+7E0h+Src], 0
0x18006674c  mov     [rbp+7E0h+var_824], 0
0x180066753  xor     edx, edx; Val
0x180066755  mov     r8d, 800h; Size
0x18006675b  lea     rcx, [rbp+7E0h+var_820]; void *
0x18006675f  call    memset_0
0x180066764  mov     [rbp+7E0h+var_820], ebx
0x180066767  mov     [rbp+7E0h+var_828], 32h ; '2'
0x18006676e  mov     rcx, rsi; void *
0x180066771  lea     rdx, [rbp+7E0h+Src]; Src
0x180066775  mov     r8d, 810h; Size
0x18006677b  call    memcpy_0
0x180066780  mov     rax, [rsp+8E0h+var_878]
0x180066785  mov     [rax+0Ch], r14d
0x180066789  lea     rax, [rbp+7E0h+arg_18]
0x180066790  mov     [rbp+7E0h+var_848], rax
0x180066794  lea     rax, [rsp+8E0h+var_878]
0x180066799  mov     [rbp+7E0h+var_840], rax
0x18006679d  mov     [rbp+7E0h+var_838], 1
0x1800667a1  mov     rcx, [rdi+28h]
0x1800667a5  mov     rax, [rcx]
0x1800667a8  mov     r9d, 810h
0x1800667ae  mov     r8, [rsp+8E0h+var_878]
0x1800667b3  mov     edx, r14d
0x1800667b6  mov     rax, [rax+20h]
0x1800667ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800667bf  mov     ebx, eax
0x1800667c1  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800667c5  call    cs:__imp_QueryPerformanceCounter
0x1800667cb  xorps   xmm6, xmm6
0x1800667ce  cmp     qword ptr [rdi+48h], 0
0x1800667d3  jz      short loc_1800667F7
0x1800667d5  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800667d9  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800667dd  cvtsi2ss xmm6, rcx
0x1800667e2  mulss   xmm6, cs:__real@447a0000
0x1800667ea  xorps   xmm0, xmm0
0x1800667ed  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800667f3  divss   xmm6, xmm0
0x1800667f7  mov     rcx, [rsp+8E0h+var_878]
0x1800667fc  cmp     dword ptr [rcx+8], 1
0x180066800  jnz     loc_1800668BC
0x180066806  mov     [rsp+8E0h+var_870], 0
0x18006680f  lea     rdx, [rsp+8E0h+var_870]
0x180066814  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x180066819  test    eax, eax
0x18006681b  js      loc_18006692D
0x180066821  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x180066826  mov     r8, rax
0x180066829  mov     ecx, [rax]
0x18006682b  cmp     ecx, 4
0x18006682e  jbe     loc_18006692D
0x180066834  mov     [rbp+7E0h+arg_0], ebx
0x18006683a  movss   [rsp+8E0h+var_868], xmm6
0x180066840  mov     [rbp+7E0h+var_860], rdi
0x180066844  mov     rdx, [rsp+8E0h+var_870]
0x180066849  mov     ecx, [rdx+10h]
0x18006684c  mov     [rsp+8E0h+var_864], ecx
0x180066850  mov     ecx, [rdx+4]
0x180066853  mov     [rsp+8E0h+var_880], ecx
0x180066857  mov     eax, [rdx+8]
0x18006685a  mov     [rsp+8E0h+var_880+4], eax
0x18006685e  mov     eax, [rdx]
0x180066860  mov     dword ptr [rsp+8E0h+var_870], eax
0x180066864  lea     rax, [rbp+7E0h+arg_0]
0x18006686b  mov     [rsp+8E0h+var_890], rax
0x180066870  lea     rax, [rsp+8E0h+var_868]
0x180066875  mov     [rsp+8E0h+var_898], rax
0x18006687a  lea     rax, [rbp+7E0h+var_860]
0x18006687e  mov     [rsp+8E0h+var_8A0], rax
0x180066883  lea     rax, [rsp+8E0h+var_864]
0x180066888  mov     [rsp+8E0h+var_8A8], rax
0x18006688d  lea     rax, [rsp+8E0h+var_880]
0x180066892  mov     [rsp+8E0h+var_8B0], rax
0x180066897  lea     rax, [rsp+8E0h+var_880+4]
0x18006689c  mov     [rsp+8E0h+var_8B8], rax
0x1800668a1  lea     rax, [rsp+8E0h+var_870]
0x1800668a6  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800668ab  lea     rdx, byte_180170C25
0x1800668b2  mov     rcx, r8
0x1800668b5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800668ba  jmp     short loc_18006692D
0x1800668bc  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800668c1  mov     ecx, [rax]
0x1800668c3  cmp     ecx, 4
0x1800668c6  jbe     short loc_18006692D
0x1800668c8  mov     [rbp+7E0h+arg_0], ebx
0x1800668ce  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800668d4  mov     [rbp+7E0h+var_860], rdi
0x1800668d8  mov     rcx, [rsp+8E0h+var_878]
0x1800668dd  mov     edx, [rcx+8]
0x1800668e0  mov     [rsp+8E0h+var_880+4], edx
0x1800668e4  mov     ecx, [rdi+30h]
0x1800668e7  mov     [rsp+8E0h+var_880], ecx
0x1800668eb  lea     rcx, [rbp+7E0h+arg_0]
0x1800668f2  mov     [rsp+8E0h+var_8A0], rcx
0x1800668f7  lea     rcx, [rsp+8E0h+var_870]
0x1800668fc  mov     [rsp+8E0h+var_8A8], rcx
0x180066901  lea     rcx, [rbp+7E0h+var_860]
0x180066905  mov     [rsp+8E0h+var_8B0], rcx
0x18006690a  lea     rcx, [rsp+8E0h+var_880+4]
0x18006690f  mov     [rsp+8E0h+var_8B8], rcx
0x180066914  lea     rcx, [rsp+8E0h+var_880]
0x180066919  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x18006691e  lea     rdx, qword_180170EF0
0x180066925  mov     rcx, rax
0x180066928  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18006692d  mov     rcx, [rbp+7E8h]; this
0x180066934  test    ebx, ebx
0x180066936  jns     short loc_18006695B
0x180066938  mov     r9d, ebx; char *
0x18006693b  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180066942  mov     edx, 81h; void *
0x180066947  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006694c  mov     rax, [rdi]
0x18006694f  mov     rcx, rdi
0x180066952  mov     rax, [rax+20h]
0x180066956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006695b  mov     ebx, [rdi+40h]
0x18006695e  test    ebx, ebx
0x180066960  jns     short loc_180066969
0x180066962  mov     edx, 8Ah
0x180066967  jmp     short loc_18006697A
0x180066969  mov     rcx, [rsp+8E0h+var_878]
0x18006696e  mov     ebx, [rcx+4]
0x180066971  test    ebx, ebx
0x180066973  jns     short loc_180066992
0x180066975  mov     edx, 8Ch; void *
0x18006697a  mov     r9d, ebx; char *
0x18006697d  mov     rcx, [rbp+7E8h]; this
0x180066984  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18006698b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066990  jmp     short loc_1800669B0
0x180066992  mov     rdx, [rbp+7E0h+arg_20]
0x180066999  call    ??$CastTo@UXvmGetMaxDynamicObjectCount@@@XvmMessage@@QEAAJPEAPEAUXvmGetMaxDynamicObjectCount@@@Z; XvmMessage::CastTo<XvmGetMaxDynamicObjectCount>(XvmGetMaxDynamicObjectCount * *)
0x18006699e  mov     ebx, eax
0x1800669a0  test    eax, eax
0x1800669a2  jns     short loc_1800669AE
0x1800669a4  mov     r9d, eax
0x1800669a7  mov     edx, 8Dh
0x1800669ac  jmp     short loc_18006697D
0x1800669ae  xor     ebx, ebx
0x1800669b0  mov     rcx, [rbp+7E0h+arg_18]
0x1800669b7  mov     rax, [rsp+8E0h+var_878]
0x1800669bc  mov     [rcx], rax
0x1800669bf  mov     eax, ebx
0x1800669c1  lea     r11, [rsp+8E0h+var_10]
0x1800669c9  mov     rbx, [r11+28h]
0x1800669cd  mov     rsi, [r11+30h]
0x1800669d1  movaps  xmm6, xmmword ptr [r11-10h]
0x1800669d6  mov     rsp, r11
0x1800669d9  pop     r14
0x1800669db  pop     rdi
0x1800669dc  pop     rbp
0x1800669dd  retn
```
