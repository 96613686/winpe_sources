# CGuestXvmAudioObject::SendAndValidateResponse<XvmRegisterAudioSessionNotification>(uint,XvmRegisterAudioSessionNotification,XvmMessage * *,XvmRegisterAudioSessionNotification * *)

- ea: `0x1800bdd9c`
- end: `0x1800be0e2`
- name: `??$SendAndValidateResponse@UXvmRegisterAudioSessionNotification@@@CGuestXvmAudioObject@@QEAAJIUXvmRegisterAudioSessionNotification@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c1220`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800b9570`
- `0x1800bdd9c`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bddde`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bdec9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bddde`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bdec9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bde12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bde12`

## string_xrefs

- `0x1800bddf5`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bde34`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800be03f`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800be088`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmRegisterAudioSessionNotification>(
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
    v32 = 30;
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
            (unsigned int)qword_180167F28,
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
          (unsigned int)byte_180167FA1,
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
        v18 = XvmMessage::CastTo<XvmRegisterAudioSessionNotification>(v21, v39, v12);
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
0x1800bdd9c  mov     rax, rsp
0x1800bdd9f  mov     [rax+10h], rbx
0x1800bdda3  mov     [rax+18h], rsi
0x1800bdda7  mov     [rax+20h], r9
0x1800bddab  push    rbp
0x1800bddac  push    rdi
0x1800bddad  push    r14
0x1800bddaf  lea     rbp, [rax-7E8h]
0x1800bddb6  sub     rsp, 8D0h
0x1800bddbd  movaps  xmmword ptr [rax-28h], xmm6
0x1800bddc1  mov     bl, r8b
0x1800bddc4  mov     r14d, edx
0x1800bddc7  mov     rdi, rcx
0x1800bddca  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bddd2  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800bddda  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800bddde  call    cs:__imp_QueryPerformanceCounter
0x1800bdde4  mov     esi, [rdi+40h]
0x1800bdde7  test    esi, esi
0x1800bdde9  jns     short loc_1800BDE0D
0x1800bddeb  mov     rcx, [rbp+7E8h]; this
0x1800bddf2  mov     r9d, esi; char *
0x1800bddf5  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bddfc  mov     edx, 4Fh ; 'O'; void *
0x1800bde01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bde06  mov     eax, esi
0x1800bde08  jmp     loc_1800BE0C5
0x1800bde0d  mov     ecx, 810h; cb
0x1800bde12  call    cs:__imp_CoTaskMemAlloc
0x1800bde18  mov     rsi, rax
0x1800bde1b  mov     [rsp+8E0h+var_878], rax
0x1800bde20  test    rax, rax
0x1800bde23  jnz     short loc_1800BDE48
0x1800bde25  mov     rcx, [rbp+7E8h]; this
0x1800bde2c  mov     ebx, 8007000Eh
0x1800bde31  mov     r9d, ebx; char *
0x1800bde34  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bde3b  lea     edx, [rax+52h]; void *
0x1800bde3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bde43  jmp     loc_1800BE0C3
0x1800bde48  mov     [rbp+7E0h+Src], 0
0x1800bde50  mov     [rbp+7E0h+var_824], 0
0x1800bde57  xor     edx, edx; Val
0x1800bde59  mov     r8d, 800h; Size
0x1800bde5f  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bde63  call    memset_0
0x1800bde68  mov     [rbp+7E0h+var_820], bl
0x1800bde6b  mov     [rbp+7E0h+var_828], 1Eh
0x1800bde72  mov     rcx, rsi; void *
0x1800bde75  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bde79  mov     r8d, 810h; Size
0x1800bde7f  call    memcpy_0
0x1800bde84  mov     rax, [rsp+8E0h+var_878]
0x1800bde89  mov     [rax+0Ch], r14d
0x1800bde8d  lea     rax, [rbp+7E0h+arg_18]
0x1800bde94  mov     [rbp+7E0h+var_848], rax
0x1800bde98  lea     rax, [rsp+8E0h+var_878]
0x1800bde9d  mov     [rbp+7E0h+var_840], rax
0x1800bdea1  mov     [rbp+7E0h+var_838], 1
0x1800bdea5  mov     rcx, [rdi+28h]
0x1800bdea9  mov     rax, [rcx]
0x1800bdeac  mov     r9d, 810h
0x1800bdeb2  mov     r8, [rsp+8E0h+var_878]
0x1800bdeb7  mov     edx, r14d
0x1800bdeba  mov     rax, [rax+20h]
0x1800bdebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdec3  mov     ebx, eax
0x1800bdec5  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800bdec9  call    cs:__imp_QueryPerformanceCounter
0x1800bdecf  xorps   xmm6, xmm6
0x1800bded2  cmp     qword ptr [rdi+48h], 0
0x1800bded7  jz      short loc_1800BDEFB
0x1800bded9  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800bdedd  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800bdee1  cvtsi2ss xmm6, rcx
0x1800bdee6  mulss   xmm6, cs:__real@447a0000
0x1800bdeee  xorps   xmm0, xmm0
0x1800bdef1  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800bdef7  divss   xmm6, xmm0
0x1800bdefb  mov     rcx, [rsp+8E0h+var_878]
0x1800bdf00  cmp     dword ptr [rcx+8], 1
0x1800bdf04  jnz     loc_1800BDFC0
0x1800bdf0a  mov     [rsp+8E0h+var_870], 0
0x1800bdf13  lea     rdx, [rsp+8E0h+var_870]
0x1800bdf18  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bdf1d  test    eax, eax
0x1800bdf1f  js      loc_1800BE031
0x1800bdf25  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bdf2a  mov     r8, rax
0x1800bdf2d  mov     ecx, [rax]
0x1800bdf2f  cmp     ecx, 4
0x1800bdf32  jbe     loc_1800BE031
0x1800bdf38  mov     [rbp+7E0h+arg_0], ebx
0x1800bdf3e  movss   [rsp+8E0h+var_868], xmm6
0x1800bdf44  mov     [rbp+7E0h+var_860], rdi
0x1800bdf48  mov     rdx, [rsp+8E0h+var_870]
0x1800bdf4d  mov     ecx, [rdx+10h]
0x1800bdf50  mov     [rsp+8E0h+var_864], ecx
0x1800bdf54  mov     ecx, [rdx+4]
0x1800bdf57  mov     [rsp+8E0h+var_880], ecx
0x1800bdf5b  mov     eax, [rdx+8]
0x1800bdf5e  mov     [rsp+8E0h+var_880+4], eax
0x1800bdf62  mov     eax, [rdx]
0x1800bdf64  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800bdf68  lea     rax, [rbp+7E0h+arg_0]
0x1800bdf6f  mov     [rsp+8E0h+var_890], rax
0x1800bdf74  lea     rax, [rsp+8E0h+var_868]
0x1800bdf79  mov     [rsp+8E0h+var_898], rax
0x1800bdf7e  lea     rax, [rbp+7E0h+var_860]
0x1800bdf82  mov     [rsp+8E0h+var_8A0], rax
0x1800bdf87  lea     rax, [rsp+8E0h+var_864]
0x1800bdf8c  mov     [rsp+8E0h+var_8A8], rax
0x1800bdf91  lea     rax, [rsp+8E0h+var_880]
0x1800bdf96  mov     [rsp+8E0h+var_8B0], rax
0x1800bdf9b  lea     rax, [rsp+8E0h+var_880+4]
0x1800bdfa0  mov     [rsp+8E0h+var_8B8], rax
0x1800bdfa5  lea     rax, [rsp+8E0h+var_870]
0x1800bdfaa  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bdfaf  lea     rdx, qword_180167F28
0x1800bdfb6  mov     rcx, r8
0x1800bdfb9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bdfbe  jmp     short loc_1800BE031
0x1800bdfc0  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bdfc5  mov     ecx, [rax]
0x1800bdfc7  cmp     ecx, 4
0x1800bdfca  jbe     short loc_1800BE031
0x1800bdfcc  mov     [rbp+7E0h+arg_0], ebx
0x1800bdfd2  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bdfd8  mov     [rbp+7E0h+var_860], rdi
0x1800bdfdc  mov     rcx, [rsp+8E0h+var_878]
0x1800bdfe1  mov     edx, [rcx+8]
0x1800bdfe4  mov     [rsp+8E0h+var_880+4], edx
0x1800bdfe8  mov     ecx, [rdi+30h]
0x1800bdfeb  mov     [rsp+8E0h+var_880], ecx
0x1800bdfef  lea     rcx, [rbp+7E0h+arg_0]
0x1800bdff6  mov     [rsp+8E0h+var_8A0], rcx
0x1800bdffb  lea     rcx, [rsp+8E0h+var_870]
0x1800be000  mov     [rsp+8E0h+var_8A8], rcx
0x1800be005  lea     rcx, [rbp+7E0h+var_860]
0x1800be009  mov     [rsp+8E0h+var_8B0], rcx
0x1800be00e  lea     rcx, [rsp+8E0h+var_880+4]
0x1800be013  mov     [rsp+8E0h+var_8B8], rcx
0x1800be018  lea     rcx, [rsp+8E0h+var_880]
0x1800be01d  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800be022  lea     rdx, byte_180167FA1
0x1800be029  mov     rcx, rax
0x1800be02c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800be031  mov     rcx, [rbp+7E8h]; this
0x1800be038  test    ebx, ebx
0x1800be03a  jns     short loc_1800BE05F
0x1800be03c  mov     r9d, ebx; char *
0x1800be03f  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800be046  mov     edx, 81h; void *
0x1800be04b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800be050  mov     rax, [rdi]
0x1800be053  mov     rcx, rdi
0x1800be056  mov     rax, [rax+20h]
0x1800be05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be05f  mov     ebx, [rdi+40h]
0x1800be062  test    ebx, ebx
0x1800be064  jns     short loc_1800BE06D
0x1800be066  mov     edx, 8Ah
0x1800be06b  jmp     short loc_1800BE07E
0x1800be06d  mov     rcx, [rsp+8E0h+var_878]
0x1800be072  mov     ebx, [rcx+4]
0x1800be075  test    ebx, ebx
0x1800be077  jns     short loc_1800BE096
0x1800be079  mov     edx, 8Ch; void *
0x1800be07e  mov     r9d, ebx; char *
0x1800be081  mov     rcx, [rbp+7E8h]; this
0x1800be088  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800be08f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be094  jmp     short loc_1800BE0B4
0x1800be096  mov     rdx, [rbp+7E0h+arg_20]
0x1800be09d  call    ??$CastTo@UXvmRegisterAudioSessionNotification@@@XvmMessage@@QEAAJPEAPEAUXvmRegisterAudioSessionNotification@@@Z; XvmMessage::CastTo<XvmRegisterAudioSessionNotification>(XvmRegisterAudioSessionNotification * *)
0x1800be0a2  mov     ebx, eax
0x1800be0a4  test    eax, eax
0x1800be0a6  jns     short loc_1800BE0B2
0x1800be0a8  mov     r9d, eax
0x1800be0ab  mov     edx, 8Dh
0x1800be0b0  jmp     short loc_1800BE081
0x1800be0b2  xor     ebx, ebx
0x1800be0b4  mov     rcx, [rbp+7E0h+arg_18]
0x1800be0bb  mov     rax, [rsp+8E0h+var_878]
0x1800be0c0  mov     [rcx], rax
0x1800be0c3  mov     eax, ebx
0x1800be0c5  lea     r11, [rsp+8E0h+var_10]
0x1800be0cd  mov     rbx, [r11+28h]
0x1800be0d1  mov     rsi, [r11+30h]
0x1800be0d5  movaps  xmm6, xmmword ptr [r11-10h]
0x1800be0da  mov     rsp, r11
0x1800be0dd  pop     r14
0x1800be0df  pop     rdi
0x1800be0e0  pop     rbp
0x1800be0e1  retn
```
