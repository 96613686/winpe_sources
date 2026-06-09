# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetGroupingParam>(uint,XvmGetGroupingParam,XvmMessage * *,XvmGetGroupingParam * *)

- ea: `0x1800bc928`
- end: `0x1800bcc7a`
- name: `??$SendAndValidateResponse@UXvmGetGroupingParam@@@CGuestXvmAudioObject@@QEAAJIUXvmGetGroupingParam@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `850`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c0720`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800b93b0`
- `0x1800bc928`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bc96a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bca61`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bc96a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bca61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bc99e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bc99e`

## string_xrefs

- `0x1800bc981`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bc9c0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bcbd7`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bcc20`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetGroupingParam>(
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
  int Grouping; // eax
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
    v32 = 28;
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
            (unsigned int)&dword_1801680B4,
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
          (unsigned int)byte_18016812D,
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
        Grouping = XvmMessage::CastTo<XvmGetGroupingParam>(v21, v39, v12);
        v9 = Grouping;
        if ( Grouping >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)Grouping;
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
0x1800bc928  mov     rax, rsp
0x1800bc92b  mov     [rax+10h], rbx
0x1800bc92f  mov     [rax+18h], rsi
0x1800bc933  mov     [rax+20h], r9
0x1800bc937  push    rbp
0x1800bc938  push    rdi
0x1800bc939  push    r14
0x1800bc93b  lea     rbp, [rax-7E8h]
0x1800bc942  sub     rsp, 8D0h
0x1800bc949  movaps  xmmword ptr [rax-28h], xmm6
0x1800bc94d  mov     rsi, r8
0x1800bc950  mov     r14d, edx
0x1800bc953  mov     rbx, rcx
0x1800bc956  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bc95e  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800bc966  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800bc96a  call    cs:__imp_QueryPerformanceCounter
0x1800bc970  mov     edi, [rbx+40h]
0x1800bc973  test    edi, edi
0x1800bc975  jns     short loc_1800BC999
0x1800bc977  mov     rcx, [rbp+7E8h]; this
0x1800bc97e  mov     r9d, edi; char *
0x1800bc981  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bc988  mov     edx, 4Fh ; 'O'; void *
0x1800bc98d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc992  mov     eax, edi
0x1800bc994  jmp     loc_1800BCC5D
0x1800bc999  mov     ecx, 810h; cb
0x1800bc99e  call    cs:__imp_CoTaskMemAlloc
0x1800bc9a4  mov     rdi, rax
0x1800bc9a7  mov     [rsp+8E0h+var_878], rax
0x1800bc9ac  test    rax, rax
0x1800bc9af  jnz     short loc_1800BC9D4
0x1800bc9b1  mov     rcx, [rbp+7E8h]; this
0x1800bc9b8  mov     ebx, 8007000Eh
0x1800bc9bd  mov     r9d, ebx; char *
0x1800bc9c0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bc9c7  lea     edx, [rax+52h]; void *
0x1800bc9ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc9cf  jmp     loc_1800BCC5B
0x1800bc9d4  mov     [rbp+7E0h+Src], 0
0x1800bc9dc  mov     [rbp+7E0h+var_824], 0
0x1800bc9e3  xor     edx, edx; Val
0x1800bc9e5  mov     r8d, 800h; Size
0x1800bc9eb  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bc9ef  call    memset_0
0x1800bc9f4  mov     rax, [rsi]
0x1800bc9f7  mov     [rbp+7E0h+var_820], rax
0x1800bc9fb  mov     rax, [rsi+8]
0x1800bc9ff  mov     [rbp+7E0h+var_818], rax
0x1800bca03  mov     [rbp+7E0h+var_828], 1Ch
0x1800bca0a  mov     rcx, rdi; void *
0x1800bca0d  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bca11  mov     r8d, 810h; Size
0x1800bca17  call    memcpy_0
0x1800bca1c  mov     rax, [rsp+8E0h+var_878]
0x1800bca21  mov     [rax+0Ch], r14d
0x1800bca25  lea     rax, [rbp+7E0h+arg_18]
0x1800bca2c  mov     [rbp+7E0h+var_848], rax
0x1800bca30  lea     rax, [rsp+8E0h+var_878]
0x1800bca35  mov     [rbp+7E0h+var_840], rax
0x1800bca39  mov     [rbp+7E0h+var_838], 1
0x1800bca3d  mov     rcx, [rbx+28h]
0x1800bca41  mov     rax, [rcx]
0x1800bca44  mov     r9d, 810h
0x1800bca4a  mov     r8, [rsp+8E0h+var_878]
0x1800bca4f  mov     edx, r14d
0x1800bca52  mov     rax, [rax+20h]
0x1800bca56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bca5b  mov     edi, eax
0x1800bca5d  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800bca61  call    cs:__imp_QueryPerformanceCounter
0x1800bca67  xorps   xmm6, xmm6
0x1800bca6a  cmp     qword ptr [rbx+48h], 0
0x1800bca6f  jz      short loc_1800BCA93
0x1800bca71  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800bca75  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800bca79  cvtsi2ss xmm6, rcx
0x1800bca7e  mulss   xmm6, cs:__real@447a0000
0x1800bca86  xorps   xmm0, xmm0
0x1800bca89  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800bca8f  divss   xmm6, xmm0
0x1800bca93  mov     rcx, [rsp+8E0h+var_878]
0x1800bca98  cmp     dword ptr [rcx+8], 1
0x1800bca9c  jnz     loc_1800BCB58
0x1800bcaa2  mov     [rsp+8E0h+var_870], 0
0x1800bcaab  lea     rdx, [rsp+8E0h+var_870]
0x1800bcab0  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bcab5  test    eax, eax
0x1800bcab7  js      loc_1800BCBC9
0x1800bcabd  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bcac2  mov     r8, rax
0x1800bcac5  mov     ecx, [rax]
0x1800bcac7  cmp     ecx, 4
0x1800bcaca  jbe     loc_1800BCBC9
0x1800bcad0  mov     [rbp+7E0h+arg_0], edi
0x1800bcad6  movss   [rsp+8E0h+var_868], xmm6
0x1800bcadc  mov     [rbp+7E0h+var_860], rbx
0x1800bcae0  mov     rdx, [rsp+8E0h+var_870]
0x1800bcae5  mov     ecx, [rdx+10h]
0x1800bcae8  mov     [rsp+8E0h+var_864], ecx
0x1800bcaec  mov     ecx, [rdx+4]
0x1800bcaef  mov     [rsp+8E0h+var_880], ecx
0x1800bcaf3  mov     eax, [rdx+8]
0x1800bcaf6  mov     [rsp+8E0h+var_880+4], eax
0x1800bcafa  mov     eax, [rdx]
0x1800bcafc  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800bcb00  lea     rax, [rbp+7E0h+arg_0]
0x1800bcb07  mov     [rsp+8E0h+var_890], rax
0x1800bcb0c  lea     rax, [rsp+8E0h+var_868]
0x1800bcb11  mov     [rsp+8E0h+var_898], rax
0x1800bcb16  lea     rax, [rbp+7E0h+var_860]
0x1800bcb1a  mov     [rsp+8E0h+var_8A0], rax
0x1800bcb1f  lea     rax, [rsp+8E0h+var_864]
0x1800bcb24  mov     [rsp+8E0h+var_8A8], rax
0x1800bcb29  lea     rax, [rsp+8E0h+var_880]
0x1800bcb2e  mov     [rsp+8E0h+var_8B0], rax
0x1800bcb33  lea     rax, [rsp+8E0h+var_880+4]
0x1800bcb38  mov     [rsp+8E0h+var_8B8], rax
0x1800bcb3d  lea     rax, [rsp+8E0h+var_870]
0x1800bcb42  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bcb47  lea     rdx, dword_1801680B4
0x1800bcb4e  mov     rcx, r8
0x1800bcb51  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bcb56  jmp     short loc_1800BCBC9
0x1800bcb58  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bcb5d  mov     ecx, [rax]
0x1800bcb5f  cmp     ecx, 4
0x1800bcb62  jbe     short loc_1800BCBC9
0x1800bcb64  mov     [rbp+7E0h+arg_0], edi
0x1800bcb6a  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bcb70  mov     [rbp+7E0h+var_860], rbx
0x1800bcb74  mov     rcx, [rsp+8E0h+var_878]
0x1800bcb79  mov     edx, [rcx+8]
0x1800bcb7c  mov     [rsp+8E0h+var_880+4], edx
0x1800bcb80  mov     ecx, [rbx+30h]
0x1800bcb83  mov     [rsp+8E0h+var_880], ecx
0x1800bcb87  lea     rcx, [rbp+7E0h+arg_0]
0x1800bcb8e  mov     [rsp+8E0h+var_8A0], rcx
0x1800bcb93  lea     rcx, [rsp+8E0h+var_870]
0x1800bcb98  mov     [rsp+8E0h+var_8A8], rcx
0x1800bcb9d  lea     rcx, [rbp+7E0h+var_860]
0x1800bcba1  mov     [rsp+8E0h+var_8B0], rcx
0x1800bcba6  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bcbab  mov     [rsp+8E0h+var_8B8], rcx
0x1800bcbb0  lea     rcx, [rsp+8E0h+var_880]
0x1800bcbb5  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bcbba  lea     rdx, byte_18016812D
0x1800bcbc1  mov     rcx, rax
0x1800bcbc4  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bcbc9  mov     rcx, [rbp+7E8h]; this
0x1800bcbd0  test    edi, edi
0x1800bcbd2  jns     short loc_1800BCBF7
0x1800bcbd4  mov     r9d, edi; char *
0x1800bcbd7  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bcbde  mov     edx, 81h; void *
0x1800bcbe3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bcbe8  mov     rax, [rbx]
0x1800bcbeb  mov     rcx, rbx
0x1800bcbee  mov     rax, [rax+20h]
0x1800bcbf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcbf7  mov     ebx, [rbx+40h]
0x1800bcbfa  test    ebx, ebx
0x1800bcbfc  jns     short loc_1800BCC05
0x1800bcbfe  mov     edx, 8Ah
0x1800bcc03  jmp     short loc_1800BCC16
0x1800bcc05  mov     rcx, [rsp+8E0h+var_878]
0x1800bcc0a  mov     ebx, [rcx+4]
0x1800bcc0d  test    ebx, ebx
0x1800bcc0f  jns     short loc_1800BCC2E
0x1800bcc11  mov     edx, 8Ch; void *
0x1800bcc16  mov     r9d, ebx; char *
0x1800bcc19  mov     rcx, [rbp+7E8h]; this
0x1800bcc20  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bcc27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcc2c  jmp     short loc_1800BCC4C
0x1800bcc2e  mov     rdx, [rbp+7E0h+arg_20]
0x1800bcc35  call    ??$CastTo@UXvmGetGroupingParam@@@XvmMessage@@QEAAJPEAPEAUXvmGetGroupingParam@@@Z; XvmMessage::CastTo<XvmGetGroupingParam>(XvmGetGroupingParam * *)
0x1800bcc3a  mov     ebx, eax
0x1800bcc3c  test    eax, eax
0x1800bcc3e  jns     short loc_1800BCC4A
0x1800bcc40  mov     r9d, eax
0x1800bcc43  mov     edx, 8Dh
0x1800bcc48  jmp     short loc_1800BCC19
0x1800bcc4a  xor     ebx, ebx
0x1800bcc4c  mov     rcx, [rbp+7E0h+arg_18]
0x1800bcc53  mov     rax, [rsp+8E0h+var_878]
0x1800bcc58  mov     [rcx], rax
0x1800bcc5b  mov     eax, ebx
0x1800bcc5d  lea     r11, [rsp+8E0h+var_10]
0x1800bcc65  mov     rbx, [r11+28h]
0x1800bcc69  mov     rsi, [r11+30h]
0x1800bcc6d  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bcc72  mov     rsp, r11
0x1800bcc75  pop     r14
0x1800bcc77  pop     rdi
0x1800bcc78  pop     rbp
0x1800bcc79  retn
```
