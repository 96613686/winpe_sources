# CGuestXvmAudioObject::SendAndValidateResponse<XvmIsOffloadCapable>(uint,XvmIsOffloadCapable,XvmMessage * *,XvmIsOffloadCapable * *)

- ea: `0x1800ad87c`
- end: `0x1800adbca`
- name: `??$SendAndValidateResponse@UXvmIsOffloadCapable@@@CGuestXvmAudioObject@@QEAAJIUXvmIsOffloadCapable@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `846`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b0c90`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2ce0`
- `0x1800ad87c`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad8be`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad9b1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad8be`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ad9b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ad8f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ad8f2`

## string_xrefs

- `0x1800ad8d5`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ad914`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800adb27`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800adb70`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmIsOffloadCapable>(__int64 a1, unsigned int a2, int *a3, ...)
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
  int IsOffload; // eax
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
  int v34; // [rsp+C8h] [rbp-40h] BYREF
  char v35; // [rsp+CCh] [rbp-3Ch]
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
    memset_0(&v34, 0, 0x800u);
    v34 = *a3;
    v35 = *((_BYTE *)a3 + 4);
    v32 = 11;
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
            (unsigned int)&byte_18016609F,
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
          (unsigned int)&dword_180165F8C,
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
        IsOffload = XvmMessage::CastTo<XvmIsOffloadCapable>(v21, v40, v12);
        v9 = IsOffload;
        if ( IsOffload >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)IsOffload;
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
0x1800ad87c  mov     rax, rsp
0x1800ad87f  mov     [rax+10h], rbx
0x1800ad883  mov     [rax+18h], rsi
0x1800ad887  mov     [rax+20h], r9
0x1800ad88b  push    rbp
0x1800ad88c  push    rdi
0x1800ad88d  push    r14
0x1800ad88f  lea     rbp, [rax-7E8h]
0x1800ad896  sub     rsp, 8D0h
0x1800ad89d  movaps  xmmword ptr [rax-28h], xmm6
0x1800ad8a1  mov     rsi, r8
0x1800ad8a4  mov     r14d, edx
0x1800ad8a7  mov     rbx, rcx
0x1800ad8aa  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800ad8b2  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800ad8ba  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800ad8be  call    cs:__imp_QueryPerformanceCounter
0x1800ad8c4  mov     edi, [rbx+40h]
0x1800ad8c7  test    edi, edi
0x1800ad8c9  jns     short loc_1800AD8ED
0x1800ad8cb  mov     rcx, [rbp+7E8h]; this
0x1800ad8d2  mov     r9d, edi; char *
0x1800ad8d5  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ad8dc  mov     edx, 4Fh ; 'O'; void *
0x1800ad8e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad8e6  mov     eax, edi
0x1800ad8e8  jmp     loc_1800ADBAD
0x1800ad8ed  mov     ecx, 810h; cb
0x1800ad8f2  call    cs:__imp_CoTaskMemAlloc
0x1800ad8f8  mov     rdi, rax
0x1800ad8fb  mov     [rsp+8E0h+var_878], rax
0x1800ad900  test    rax, rax
0x1800ad903  jnz     short loc_1800AD928
0x1800ad905  mov     rcx, [rbp+7E8h]; this
0x1800ad90c  mov     ebx, 8007000Eh
0x1800ad911  mov     r9d, ebx; char *
0x1800ad914  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ad91b  lea     edx, [rax+52h]; void *
0x1800ad91e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad923  jmp     loc_1800ADBAB
0x1800ad928  mov     [rbp+7E0h+Src], 0
0x1800ad930  mov     [rbp+7E0h+var_824], 0
0x1800ad937  xor     edx, edx; Val
0x1800ad939  mov     r8d, 800h; Size
0x1800ad93f  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800ad943  call    memset_0
0x1800ad948  mov     eax, [rsi]
0x1800ad94a  mov     [rbp+7E0h+var_820], eax
0x1800ad94d  mov     al, [rsi+4]
0x1800ad950  mov     [rbp+7E0h+var_81C], al
0x1800ad953  mov     [rbp+7E0h+var_828], 0Bh
0x1800ad95a  mov     rcx, rdi; void *
0x1800ad95d  lea     rdx, [rbp+7E0h+Src]; Src
0x1800ad961  mov     r8d, 810h; Size
0x1800ad967  call    memcpy_0
0x1800ad96c  mov     rax, [rsp+8E0h+var_878]
0x1800ad971  mov     [rax+0Ch], r14d
0x1800ad975  lea     rax, [rbp+7E0h+arg_18]
0x1800ad97c  mov     [rbp+7E0h+var_848], rax
0x1800ad980  lea     rax, [rsp+8E0h+var_878]
0x1800ad985  mov     [rbp+7E0h+var_840], rax
0x1800ad989  mov     [rbp+7E0h+var_838], 1
0x1800ad98d  mov     rcx, [rbx+28h]
0x1800ad991  mov     rax, [rcx]
0x1800ad994  mov     r9d, 810h
0x1800ad99a  mov     r8, [rsp+8E0h+var_878]
0x1800ad99f  mov     edx, r14d
0x1800ad9a2  mov     rax, [rax+20h]
0x1800ad9a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad9ab  mov     edi, eax
0x1800ad9ad  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800ad9b1  call    cs:__imp_QueryPerformanceCounter
0x1800ad9b7  xorps   xmm6, xmm6
0x1800ad9ba  cmp     qword ptr [rbx+48h], 0
0x1800ad9bf  jz      short loc_1800AD9E3
0x1800ad9c1  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800ad9c5  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800ad9c9  cvtsi2ss xmm6, rcx
0x1800ad9ce  mulss   xmm6, cs:__real@447a0000
0x1800ad9d6  xorps   xmm0, xmm0
0x1800ad9d9  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800ad9df  divss   xmm6, xmm0
0x1800ad9e3  mov     rcx, [rsp+8E0h+var_878]
0x1800ad9e8  cmp     dword ptr [rcx+8], 1
0x1800ad9ec  jnz     loc_1800ADAA8
0x1800ad9f2  mov     [rsp+8E0h+var_870], 0
0x1800ad9fb  lea     rdx, [rsp+8E0h+var_870]
0x1800ada00  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800ada05  test    eax, eax
0x1800ada07  js      loc_1800ADB19
0x1800ada0d  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ada12  mov     r8, rax
0x1800ada15  mov     ecx, [rax]
0x1800ada17  cmp     ecx, 4
0x1800ada1a  jbe     loc_1800ADB19
0x1800ada20  mov     [rbp+7E0h+arg_0], edi
0x1800ada26  movss   [rsp+8E0h+var_868], xmm6
0x1800ada2c  mov     [rbp+7E0h+var_860], rbx
0x1800ada30  mov     rdx, [rsp+8E0h+var_870]
0x1800ada35  mov     ecx, [rdx+10h]
0x1800ada38  mov     [rsp+8E0h+var_864], ecx
0x1800ada3c  mov     ecx, [rdx+4]
0x1800ada3f  mov     [rsp+8E0h+var_880], ecx
0x1800ada43  mov     eax, [rdx+8]
0x1800ada46  mov     [rsp+8E0h+var_880+4], eax
0x1800ada4a  mov     eax, [rdx]
0x1800ada4c  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800ada50  lea     rax, [rbp+7E0h+arg_0]
0x1800ada57  mov     [rsp+8E0h+var_890], rax
0x1800ada5c  lea     rax, [rsp+8E0h+var_868]
0x1800ada61  mov     [rsp+8E0h+var_898], rax
0x1800ada66  lea     rax, [rbp+7E0h+var_860]
0x1800ada6a  mov     [rsp+8E0h+var_8A0], rax
0x1800ada6f  lea     rax, [rsp+8E0h+var_864]
0x1800ada74  mov     [rsp+8E0h+var_8A8], rax
0x1800ada79  lea     rax, [rsp+8E0h+var_880]
0x1800ada7e  mov     [rsp+8E0h+var_8B0], rax
0x1800ada83  lea     rax, [rsp+8E0h+var_880+4]
0x1800ada88  mov     [rsp+8E0h+var_8B8], rax
0x1800ada8d  lea     rax, [rsp+8E0h+var_870]
0x1800ada92  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800ada97  lea     rdx, byte_18016609F
0x1800ada9e  mov     rcx, r8
0x1800adaa1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800adaa6  jmp     short loc_1800ADB19
0x1800adaa8  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800adaad  mov     ecx, [rax]
0x1800adaaf  cmp     ecx, 4
0x1800adab2  jbe     short loc_1800ADB19
0x1800adab4  mov     [rbp+7E0h+arg_0], edi
0x1800adaba  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800adac0  mov     [rbp+7E0h+var_860], rbx
0x1800adac4  mov     rcx, [rsp+8E0h+var_878]
0x1800adac9  mov     edx, [rcx+8]
0x1800adacc  mov     [rsp+8E0h+var_880+4], edx
0x1800adad0  mov     ecx, [rbx+30h]
0x1800adad3  mov     [rsp+8E0h+var_880], ecx
0x1800adad7  lea     rcx, [rbp+7E0h+arg_0]
0x1800adade  mov     [rsp+8E0h+var_8A0], rcx
0x1800adae3  lea     rcx, [rsp+8E0h+var_870]
0x1800adae8  mov     [rsp+8E0h+var_8A8], rcx
0x1800adaed  lea     rcx, [rbp+7E0h+var_860]
0x1800adaf1  mov     [rsp+8E0h+var_8B0], rcx
0x1800adaf6  lea     rcx, [rsp+8E0h+var_880+4]
0x1800adafb  mov     [rsp+8E0h+var_8B8], rcx
0x1800adb00  lea     rcx, [rsp+8E0h+var_880]
0x1800adb05  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800adb0a  lea     rdx, dword_180165F8C
0x1800adb11  mov     rcx, rax
0x1800adb14  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800adb19  mov     rcx, [rbp+7E8h]; this
0x1800adb20  test    edi, edi
0x1800adb22  jns     short loc_1800ADB47
0x1800adb24  mov     r9d, edi; char *
0x1800adb27  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800adb2e  mov     edx, 81h; void *
0x1800adb33  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800adb38  mov     rax, [rbx]
0x1800adb3b  mov     rcx, rbx
0x1800adb3e  mov     rax, [rax+20h]
0x1800adb42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800adb47  mov     ebx, [rbx+40h]
0x1800adb4a  test    ebx, ebx
0x1800adb4c  jns     short loc_1800ADB55
0x1800adb4e  mov     edx, 8Ah
0x1800adb53  jmp     short loc_1800ADB66
0x1800adb55  mov     rcx, [rsp+8E0h+var_878]
0x1800adb5a  mov     ebx, [rcx+4]
0x1800adb5d  test    ebx, ebx
0x1800adb5f  jns     short loc_1800ADB7E
0x1800adb61  mov     edx, 8Ch; void *
0x1800adb66  mov     r9d, ebx; char *
0x1800adb69  mov     rcx, [rbp+7E8h]; this
0x1800adb70  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800adb77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adb7c  jmp     short loc_1800ADB9C
0x1800adb7e  mov     rdx, [rbp+7E0h+arg_20]
0x1800adb85  call    ??$CastTo@UXvmIsOffloadCapable@@@XvmMessage@@QEAAJPEAPEAUXvmIsOffloadCapable@@@Z; XvmMessage::CastTo<XvmIsOffloadCapable>(XvmIsOffloadCapable * *)
0x1800adb8a  mov     ebx, eax
0x1800adb8c  test    eax, eax
0x1800adb8e  jns     short loc_1800ADB9A
0x1800adb90  mov     r9d, eax
0x1800adb93  mov     edx, 8Dh
0x1800adb98  jmp     short loc_1800ADB69
0x1800adb9a  xor     ebx, ebx
0x1800adb9c  mov     rcx, [rbp+7E0h+arg_18]
0x1800adba3  mov     rax, [rsp+8E0h+var_878]
0x1800adba8  mov     [rcx], rax
0x1800adbab  mov     eax, ebx
0x1800adbad  lea     r11, [rsp+8E0h+var_10]
0x1800adbb5  mov     rbx, [r11+28h]
0x1800adbb9  mov     rsi, [r11+30h]
0x1800adbbd  movaps  xmm6, xmmword ptr [r11-10h]
0x1800adbc2  mov     rsp, r11
0x1800adbc5  pop     r14
0x1800adbc7  pop     rdi
0x1800adbc8  pop     rbp
0x1800adbc9  retn
```
