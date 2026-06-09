# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetBufferSizeLimits>(uint,XvmGetBufferSizeLimits,XvmMessage * *,XvmGetBufferSizeLimits * *)

- ea: `0x1800ab99c`
- end: `0x1800abd10`
- name: `??$SendAndValidateResponse@UXvmGetBufferSizeLimits@@@CGuestXvmAudioObject@@QEAAJIUXvmGetBufferSizeLimits@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `884`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800af460`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a27e8`
- `0x1800ab99c`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ab9de`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800abaf7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ab9de`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800abaf7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aba12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800aba12`

## string_xrefs

- `0x1800ab9f5`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800aba34`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800abc6d`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800abcb6`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetBufferSizeLimits>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
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
  int BufferSize; // eax
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
  _OWORD v34[5]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v35; // [rsp+118h] [rbp+10h]
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
    memset_0(v34, 0, 0x800u);
    v34[0] = *(_OWORD *)a3;
    v34[1] = *(_OWORD *)(a3 + 16);
    v34[2] = *(_OWORD *)(a3 + 32);
    v34[3] = *(_OWORD *)(a3 + 48);
    v34[4] = *(_OWORD *)(a3 + 64);
    v35 = *(_QWORD *)(a3 + 80);
    v32 = 10;
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
            (unsigned int)&unk_180165F13,
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
          (unsigned int)&unk_180165E00,
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
        BufferSize = XvmMessage::CastTo<XvmGetBufferSizeLimits>(v21, v40, v12);
        v9 = BufferSize;
        if ( BufferSize >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)BufferSize;
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
0x1800ab99c  mov     rax, rsp
0x1800ab99f  mov     [rax+10h], rbx
0x1800ab9a3  mov     [rax+18h], rsi
0x1800ab9a7  mov     [rax+20h], r9
0x1800ab9ab  push    rbp
0x1800ab9ac  push    rdi
0x1800ab9ad  push    r14
0x1800ab9af  lea     rbp, [rax-7E8h]
0x1800ab9b6  sub     rsp, 8D0h
0x1800ab9bd  movaps  xmmword ptr [rax-28h], xmm6
0x1800ab9c1  mov     rsi, r8
0x1800ab9c4  mov     r14d, edx
0x1800ab9c7  mov     rbx, rcx
0x1800ab9ca  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800ab9d2  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800ab9da  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800ab9de  call    cs:__imp_QueryPerformanceCounter
0x1800ab9e4  mov     edi, [rbx+40h]
0x1800ab9e7  test    edi, edi
0x1800ab9e9  jns     short loc_1800ABA0D
0x1800ab9eb  mov     rcx, [rbp+7E8h]; this
0x1800ab9f2  mov     r9d, edi; char *
0x1800ab9f5  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ab9fc  mov     edx, 4Fh ; 'O'; void *
0x1800aba01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aba06  mov     eax, edi
0x1800aba08  jmp     loc_1800ABCF3
0x1800aba0d  mov     ecx, 810h; cb
0x1800aba12  call    cs:__imp_CoTaskMemAlloc
0x1800aba18  mov     rdi, rax
0x1800aba1b  mov     [rsp+8E0h+var_878], rax
0x1800aba20  test    rax, rax
0x1800aba23  jnz     short loc_1800ABA48
0x1800aba25  mov     rcx, [rbp+7E8h]; this
0x1800aba2c  mov     ebx, 8007000Eh
0x1800aba31  mov     r9d, ebx; char *
0x1800aba34  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800aba3b  lea     edx, [rax+52h]; void *
0x1800aba3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aba43  jmp     loc_1800ABCF1
0x1800aba48  mov     [rbp+7E0h+Src], 0
0x1800aba50  mov     [rbp+7E0h+var_824], 0
0x1800aba57  xor     edx, edx; Val
0x1800aba59  mov     r8d, 800h; Size
0x1800aba5f  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800aba63  call    memset_0
0x1800aba68  movups  xmm0, xmmword ptr [rsi]
0x1800aba6b  movaps  [rbp+7E0h+var_820], xmm0
0x1800aba6f  movups  xmm1, xmmword ptr [rsi+10h]
0x1800aba73  movaps  [rbp+7E0h+var_810], xmm1
0x1800aba77  movups  xmm0, xmmword ptr [rsi+20h]
0x1800aba7b  movaps  [rbp+7E0h+var_800], xmm0
0x1800aba7f  movups  xmm1, xmmword ptr [rsi+30h]
0x1800aba83  movaps  [rbp+7E0h+var_7F0], xmm1
0x1800aba87  movups  xmm0, xmmword ptr [rsi+40h]
0x1800aba8b  movaps  [rbp+7E0h+var_7E0], xmm0
0x1800aba8f  movsd   xmm1, qword ptr [rsi+50h]
0x1800aba94  movsd   [rbp+7E0h+var_7D0], xmm1
0x1800aba99  mov     [rbp+7E0h+var_828], 0Ah
0x1800abaa0  mov     rcx, rdi; void *
0x1800abaa3  lea     rdx, [rbp+7E0h+Src]; Src
0x1800abaa7  mov     r8d, 810h; Size
0x1800abaad  call    memcpy_0
0x1800abab2  mov     rax, [rsp+8E0h+var_878]
0x1800abab7  mov     [rax+0Ch], r14d
0x1800ababb  lea     rax, [rbp+7E0h+arg_18]
0x1800abac2  mov     [rbp+7E0h+var_848], rax
0x1800abac6  lea     rax, [rsp+8E0h+var_878]
0x1800abacb  mov     [rbp+7E0h+var_840], rax
0x1800abacf  mov     [rbp+7E0h+var_838], 1
0x1800abad3  mov     rcx, [rbx+28h]
0x1800abad7  mov     rax, [rcx]
0x1800abada  mov     r9d, 810h
0x1800abae0  mov     r8, [rsp+8E0h+var_878]
0x1800abae5  mov     edx, r14d
0x1800abae8  mov     rax, [rax+20h]
0x1800abaec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abaf1  mov     edi, eax
0x1800abaf3  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800abaf7  call    cs:__imp_QueryPerformanceCounter
0x1800abafd  xorps   xmm6, xmm6
0x1800abb00  cmp     qword ptr [rbx+48h], 0
0x1800abb05  jz      short loc_1800ABB29
0x1800abb07  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800abb0b  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800abb0f  cvtsi2ss xmm6, rcx
0x1800abb14  mulss   xmm6, cs:__real@447a0000
0x1800abb1c  xorps   xmm0, xmm0
0x1800abb1f  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800abb25  divss   xmm6, xmm0
0x1800abb29  mov     rcx, [rsp+8E0h+var_878]
0x1800abb2e  cmp     dword ptr [rcx+8], 1
0x1800abb32  jnz     loc_1800ABBEE
0x1800abb38  mov     [rsp+8E0h+var_870], 0
0x1800abb41  lea     rdx, [rsp+8E0h+var_870]
0x1800abb46  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800abb4b  test    eax, eax
0x1800abb4d  js      loc_1800ABC5F
0x1800abb53  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800abb58  mov     r8, rax
0x1800abb5b  mov     ecx, [rax]
0x1800abb5d  cmp     ecx, 4
0x1800abb60  jbe     loc_1800ABC5F
0x1800abb66  mov     [rbp+7E0h+arg_0], edi
0x1800abb6c  movss   [rsp+8E0h+var_868], xmm6
0x1800abb72  mov     [rbp+7E0h+var_860], rbx
0x1800abb76  mov     rdx, [rsp+8E0h+var_870]
0x1800abb7b  mov     ecx, [rdx+10h]
0x1800abb7e  mov     [rsp+8E0h+var_864], ecx
0x1800abb82  mov     ecx, [rdx+4]
0x1800abb85  mov     [rsp+8E0h+var_880], ecx
0x1800abb89  mov     eax, [rdx+8]
0x1800abb8c  mov     [rsp+8E0h+var_880+4], eax
0x1800abb90  mov     eax, [rdx]
0x1800abb92  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800abb96  lea     rax, [rbp+7E0h+arg_0]
0x1800abb9d  mov     [rsp+8E0h+var_890], rax
0x1800abba2  lea     rax, [rsp+8E0h+var_868]
0x1800abba7  mov     [rsp+8E0h+var_898], rax
0x1800abbac  lea     rax, [rbp+7E0h+var_860]
0x1800abbb0  mov     [rsp+8E0h+var_8A0], rax
0x1800abbb5  lea     rax, [rsp+8E0h+var_864]
0x1800abbba  mov     [rsp+8E0h+var_8A8], rax
0x1800abbbf  lea     rax, [rsp+8E0h+var_880]
0x1800abbc4  mov     [rsp+8E0h+var_8B0], rax
0x1800abbc9  lea     rax, [rsp+8E0h+var_880+4]
0x1800abbce  mov     [rsp+8E0h+var_8B8], rax
0x1800abbd3  lea     rax, [rsp+8E0h+var_870]
0x1800abbd8  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800abbdd  lea     rdx, unk_180165F13
0x1800abbe4  mov     rcx, r8
0x1800abbe7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800abbec  jmp     short loc_1800ABC5F
0x1800abbee  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800abbf3  mov     ecx, [rax]
0x1800abbf5  cmp     ecx, 4
0x1800abbf8  jbe     short loc_1800ABC5F
0x1800abbfa  mov     [rbp+7E0h+arg_0], edi
0x1800abc00  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800abc06  mov     [rbp+7E0h+var_860], rbx
0x1800abc0a  mov     rcx, [rsp+8E0h+var_878]
0x1800abc0f  mov     edx, [rcx+8]
0x1800abc12  mov     [rsp+8E0h+var_880+4], edx
0x1800abc16  mov     ecx, [rbx+30h]
0x1800abc19  mov     [rsp+8E0h+var_880], ecx
0x1800abc1d  lea     rcx, [rbp+7E0h+arg_0]
0x1800abc24  mov     [rsp+8E0h+var_8A0], rcx
0x1800abc29  lea     rcx, [rsp+8E0h+var_870]
0x1800abc2e  mov     [rsp+8E0h+var_8A8], rcx
0x1800abc33  lea     rcx, [rbp+7E0h+var_860]
0x1800abc37  mov     [rsp+8E0h+var_8B0], rcx
0x1800abc3c  lea     rcx, [rsp+8E0h+var_880+4]
0x1800abc41  mov     [rsp+8E0h+var_8B8], rcx
0x1800abc46  lea     rcx, [rsp+8E0h+var_880]
0x1800abc4b  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800abc50  lea     rdx, unk_180165E00
0x1800abc57  mov     rcx, rax
0x1800abc5a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800abc5f  mov     rcx, [rbp+7E8h]; this
0x1800abc66  test    edi, edi
0x1800abc68  jns     short loc_1800ABC8D
0x1800abc6a  mov     r9d, edi; char *
0x1800abc6d  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800abc74  mov     edx, 81h; void *
0x1800abc79  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800abc7e  mov     rax, [rbx]
0x1800abc81  mov     rcx, rbx
0x1800abc84  mov     rax, [rax+20h]
0x1800abc88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abc8d  mov     ebx, [rbx+40h]
0x1800abc90  test    ebx, ebx
0x1800abc92  jns     short loc_1800ABC9B
0x1800abc94  mov     edx, 8Ah
0x1800abc99  jmp     short loc_1800ABCAC
0x1800abc9b  mov     rcx, [rsp+8E0h+var_878]
0x1800abca0  mov     ebx, [rcx+4]
0x1800abca3  test    ebx, ebx
0x1800abca5  jns     short loc_1800ABCC4
0x1800abca7  mov     edx, 8Ch; void *
0x1800abcac  mov     r9d, ebx; char *
0x1800abcaf  mov     rcx, [rbp+7E8h]; this
0x1800abcb6  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800abcbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800abcc2  jmp     short loc_1800ABCE2
0x1800abcc4  mov     rdx, [rbp+7E0h+arg_20]
0x1800abccb  call    ??$CastTo@UXvmGetBufferSizeLimits@@@XvmMessage@@QEAAJPEAPEAUXvmGetBufferSizeLimits@@@Z; XvmMessage::CastTo<XvmGetBufferSizeLimits>(XvmGetBufferSizeLimits * *)
0x1800abcd0  mov     ebx, eax
0x1800abcd2  test    eax, eax
0x1800abcd4  jns     short loc_1800ABCE0
0x1800abcd6  mov     r9d, eax
0x1800abcd9  mov     edx, 8Dh
0x1800abcde  jmp     short loc_1800ABCAF
0x1800abce0  xor     ebx, ebx
0x1800abce2  mov     rcx, [rbp+7E0h+arg_18]
0x1800abce9  mov     rax, [rsp+8E0h+var_878]
0x1800abcee  mov     [rcx], rax
0x1800abcf1  mov     eax, ebx
0x1800abcf3  lea     r11, [rsp+8E0h+var_10]
0x1800abcfb  mov     rbx, [r11+28h]
0x1800abcff  mov     rsi, [r11+30h]
0x1800abd03  movaps  xmm6, xmmword ptr [r11-10h]
0x1800abd08  mov     rsp, r11
0x1800abd0b  pop     r14
0x1800abd0d  pop     rdi
0x1800abd0e  pop     rbp
0x1800abd0f  retn
```
