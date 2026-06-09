# CGuestXvmAudioObject::SendAndValidateResponse<XvmSetClientProperties>(uint,XvmSetClientProperties,XvmMessage * *,XvmSetClientProperties * *)

- ea: `0x1800adf1c`
- end: `0x1800ae26c`
- name: `??$SendAndValidateResponse@UXvmSetClientProperties@@@CGuestXvmAudioObject@@QEAAJIUXvmSetClientProperties@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `848`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b14a0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2de0`
- `0x1800adf1c`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800adf5e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ae053`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800adf5e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ae053`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800adf92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800adf92`

## string_xrefs

- `0x1800adf75`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800adfb4`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ae1c9`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ae212`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmSetClientProperties>(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
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
  __int64 v34; // [rsp+C8h] [rbp-40h] BYREF
  char v35; // [rsp+D0h] [rbp-38h]
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
    v35 = *((_BYTE *)a3 + 8);
    v32 = 12;
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
            (unsigned int)byte_180165FD9,
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
          (unsigned int)&word_180165EC6,
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
        v18 = XvmMessage::CastTo<XvmSetClientProperties>(v21, v40, v12);
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
0x1800adf1c  mov     rax, rsp
0x1800adf1f  mov     [rax+10h], rbx
0x1800adf23  mov     [rax+18h], rsi
0x1800adf27  mov     [rax+20h], r9
0x1800adf2b  push    rbp
0x1800adf2c  push    rdi
0x1800adf2d  push    r14
0x1800adf2f  lea     rbp, [rax-7E8h]
0x1800adf36  sub     rsp, 8D0h
0x1800adf3d  movaps  xmmword ptr [rax-28h], xmm6
0x1800adf41  mov     rsi, r8
0x1800adf44  mov     r14d, edx
0x1800adf47  mov     rbx, rcx
0x1800adf4a  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800adf52  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800adf5a  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800adf5e  call    cs:__imp_QueryPerformanceCounter
0x1800adf64  mov     edi, [rbx+40h]
0x1800adf67  test    edi, edi
0x1800adf69  jns     short loc_1800ADF8D
0x1800adf6b  mov     rcx, [rbp+7E8h]; this
0x1800adf72  mov     r9d, edi; char *
0x1800adf75  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800adf7c  mov     edx, 4Fh ; 'O'; void *
0x1800adf81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adf86  mov     eax, edi
0x1800adf88  jmp     loc_1800AE24F
0x1800adf8d  mov     ecx, 810h; cb
0x1800adf92  call    cs:__imp_CoTaskMemAlloc
0x1800adf98  mov     rdi, rax
0x1800adf9b  mov     [rsp+8E0h+var_878], rax
0x1800adfa0  test    rax, rax
0x1800adfa3  jnz     short loc_1800ADFC8
0x1800adfa5  mov     rcx, [rbp+7E8h]; this
0x1800adfac  mov     ebx, 8007000Eh
0x1800adfb1  mov     r9d, ebx; char *
0x1800adfb4  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800adfbb  lea     edx, [rax+52h]; void *
0x1800adfbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800adfc3  jmp     loc_1800AE24D
0x1800adfc8  mov     [rbp+7E0h+Src], 0
0x1800adfd0  mov     [rbp+7E0h+var_824], 0
0x1800adfd7  xor     edx, edx; Val
0x1800adfd9  mov     r8d, 800h; Size
0x1800adfdf  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800adfe3  call    memset_0
0x1800adfe8  mov     rax, [rsi]
0x1800adfeb  mov     [rbp+7E0h+var_820], rax
0x1800adfef  mov     al, [rsi+8]
0x1800adff2  mov     [rbp+7E0h+var_818], al
0x1800adff5  mov     [rbp+7E0h+var_828], 0Ch
0x1800adffc  mov     rcx, rdi; void *
0x1800adfff  lea     rdx, [rbp+7E0h+Src]; Src
0x1800ae003  mov     r8d, 810h; Size
0x1800ae009  call    memcpy_0
0x1800ae00e  mov     rax, [rsp+8E0h+var_878]
0x1800ae013  mov     [rax+0Ch], r14d
0x1800ae017  lea     rax, [rbp+7E0h+arg_18]
0x1800ae01e  mov     [rbp+7E0h+var_848], rax
0x1800ae022  lea     rax, [rsp+8E0h+var_878]
0x1800ae027  mov     [rbp+7E0h+var_840], rax
0x1800ae02b  mov     [rbp+7E0h+var_838], 1
0x1800ae02f  mov     rcx, [rbx+28h]
0x1800ae033  mov     rax, [rcx]
0x1800ae036  mov     r9d, 810h
0x1800ae03c  mov     r8, [rsp+8E0h+var_878]
0x1800ae041  mov     edx, r14d
0x1800ae044  mov     rax, [rax+20h]
0x1800ae048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae04d  mov     edi, eax
0x1800ae04f  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800ae053  call    cs:__imp_QueryPerformanceCounter
0x1800ae059  xorps   xmm6, xmm6
0x1800ae05c  cmp     qword ptr [rbx+48h], 0
0x1800ae061  jz      short loc_1800AE085
0x1800ae063  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800ae067  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800ae06b  cvtsi2ss xmm6, rcx
0x1800ae070  mulss   xmm6, cs:__real@447a0000
0x1800ae078  xorps   xmm0, xmm0
0x1800ae07b  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800ae081  divss   xmm6, xmm0
0x1800ae085  mov     rcx, [rsp+8E0h+var_878]
0x1800ae08a  cmp     dword ptr [rcx+8], 1
0x1800ae08e  jnz     loc_1800AE14A
0x1800ae094  mov     [rsp+8E0h+var_870], 0
0x1800ae09d  lea     rdx, [rsp+8E0h+var_870]
0x1800ae0a2  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800ae0a7  test    eax, eax
0x1800ae0a9  js      loc_1800AE1BB
0x1800ae0af  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ae0b4  mov     r8, rax
0x1800ae0b7  mov     ecx, [rax]
0x1800ae0b9  cmp     ecx, 4
0x1800ae0bc  jbe     loc_1800AE1BB
0x1800ae0c2  mov     [rbp+7E0h+arg_0], edi
0x1800ae0c8  movss   [rsp+8E0h+var_868], xmm6
0x1800ae0ce  mov     [rbp+7E0h+var_860], rbx
0x1800ae0d2  mov     rdx, [rsp+8E0h+var_870]
0x1800ae0d7  mov     ecx, [rdx+10h]
0x1800ae0da  mov     [rsp+8E0h+var_864], ecx
0x1800ae0de  mov     ecx, [rdx+4]
0x1800ae0e1  mov     [rsp+8E0h+var_880], ecx
0x1800ae0e5  mov     eax, [rdx+8]
0x1800ae0e8  mov     [rsp+8E0h+var_880+4], eax
0x1800ae0ec  mov     eax, [rdx]
0x1800ae0ee  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800ae0f2  lea     rax, [rbp+7E0h+arg_0]
0x1800ae0f9  mov     [rsp+8E0h+var_890], rax
0x1800ae0fe  lea     rax, [rsp+8E0h+var_868]
0x1800ae103  mov     [rsp+8E0h+var_898], rax
0x1800ae108  lea     rax, [rbp+7E0h+var_860]
0x1800ae10c  mov     [rsp+8E0h+var_8A0], rax
0x1800ae111  lea     rax, [rsp+8E0h+var_864]
0x1800ae116  mov     [rsp+8E0h+var_8A8], rax
0x1800ae11b  lea     rax, [rsp+8E0h+var_880]
0x1800ae120  mov     [rsp+8E0h+var_8B0], rax
0x1800ae125  lea     rax, [rsp+8E0h+var_880+4]
0x1800ae12a  mov     [rsp+8E0h+var_8B8], rax
0x1800ae12f  lea     rax, [rsp+8E0h+var_870]
0x1800ae134  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800ae139  lea     rdx, byte_180165FD9
0x1800ae140  mov     rcx, r8
0x1800ae143  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ae148  jmp     short loc_1800AE1BB
0x1800ae14a  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ae14f  mov     ecx, [rax]
0x1800ae151  cmp     ecx, 4
0x1800ae154  jbe     short loc_1800AE1BB
0x1800ae156  mov     [rbp+7E0h+arg_0], edi
0x1800ae15c  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800ae162  mov     [rbp+7E0h+var_860], rbx
0x1800ae166  mov     rcx, [rsp+8E0h+var_878]
0x1800ae16b  mov     edx, [rcx+8]
0x1800ae16e  mov     [rsp+8E0h+var_880+4], edx
0x1800ae172  mov     ecx, [rbx+30h]
0x1800ae175  mov     [rsp+8E0h+var_880], ecx
0x1800ae179  lea     rcx, [rbp+7E0h+arg_0]
0x1800ae180  mov     [rsp+8E0h+var_8A0], rcx
0x1800ae185  lea     rcx, [rsp+8E0h+var_870]
0x1800ae18a  mov     [rsp+8E0h+var_8A8], rcx
0x1800ae18f  lea     rcx, [rbp+7E0h+var_860]
0x1800ae193  mov     [rsp+8E0h+var_8B0], rcx
0x1800ae198  lea     rcx, [rsp+8E0h+var_880+4]
0x1800ae19d  mov     [rsp+8E0h+var_8B8], rcx
0x1800ae1a2  lea     rcx, [rsp+8E0h+var_880]
0x1800ae1a7  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800ae1ac  lea     rdx, word_180165EC6
0x1800ae1b3  mov     rcx, rax
0x1800ae1b6  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ae1bb  mov     rcx, [rbp+7E8h]; this
0x1800ae1c2  test    edi, edi
0x1800ae1c4  jns     short loc_1800AE1E9
0x1800ae1c6  mov     r9d, edi; char *
0x1800ae1c9  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ae1d0  mov     edx, 81h; void *
0x1800ae1d5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ae1da  mov     rax, [rbx]
0x1800ae1dd  mov     rcx, rbx
0x1800ae1e0  mov     rax, [rax+20h]
0x1800ae1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae1e9  mov     ebx, [rbx+40h]
0x1800ae1ec  test    ebx, ebx
0x1800ae1ee  jns     short loc_1800AE1F7
0x1800ae1f0  mov     edx, 8Ah
0x1800ae1f5  jmp     short loc_1800AE208
0x1800ae1f7  mov     rcx, [rsp+8E0h+var_878]
0x1800ae1fc  mov     ebx, [rcx+4]
0x1800ae1ff  test    ebx, ebx
0x1800ae201  jns     short loc_1800AE220
0x1800ae203  mov     edx, 8Ch; void *
0x1800ae208  mov     r9d, ebx; char *
0x1800ae20b  mov     rcx, [rbp+7E8h]; this
0x1800ae212  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ae219  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae21e  jmp     short loc_1800AE23E
0x1800ae220  mov     rdx, [rbp+7E0h+arg_20]
0x1800ae227  call    ??$CastTo@UXvmSetClientProperties@@@XvmMessage@@QEAAJPEAPEAUXvmSetClientProperties@@@Z; XvmMessage::CastTo<XvmSetClientProperties>(XvmSetClientProperties * *)
0x1800ae22c  mov     ebx, eax
0x1800ae22e  test    eax, eax
0x1800ae230  jns     short loc_1800AE23C
0x1800ae232  mov     r9d, eax
0x1800ae235  mov     edx, 8Dh
0x1800ae23a  jmp     short loc_1800AE20B
0x1800ae23c  xor     ebx, ebx
0x1800ae23e  mov     rcx, [rbp+7E0h+arg_18]
0x1800ae245  mov     rax, [rsp+8E0h+var_878]
0x1800ae24a  mov     [rcx], rax
0x1800ae24d  mov     eax, ebx
0x1800ae24f  lea     r11, [rsp+8E0h+var_10]
0x1800ae257  mov     rbx, [r11+28h]
0x1800ae25b  mov     rsi, [r11+30h]
0x1800ae25f  movaps  xmm6, xmmword ptr [r11-10h]
0x1800ae264  mov     rsp, r11
0x1800ae267  pop     r14
0x1800ae269  pop     rdi
0x1800ae26a  pop     rbp
0x1800ae26b  retn
```
