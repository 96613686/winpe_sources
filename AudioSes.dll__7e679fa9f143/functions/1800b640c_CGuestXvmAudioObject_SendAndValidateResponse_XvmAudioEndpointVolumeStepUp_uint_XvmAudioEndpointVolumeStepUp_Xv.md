# CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeStepUp>(uint,XvmAudioEndpointVolumeStepUp,XvmMessage * *,XvmAudioEndpointVolumeStepUp * *)

- ea: `0x1800b640c`
- end: `0x1800b675e`
- name: `??$SendAndValidateResponse@UXvmAudioEndpointVolumeStepUp@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeStepUp@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `850`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b7950`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a60c8`
- `0x1800b640c`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b644e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b6545`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b644e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b6545`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b6482`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b6482`

## string_xrefs

- `0x1800b6465`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b64a4`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b66bb`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b6704`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeStepUp>(
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
    v32 = 93;
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
            (unsigned int)&unk_180166980,
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
          (unsigned int)&unk_1801669F9,
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
        v18 = XvmMessage::CastTo<XvmAudioEndpointVolumeStepUp>(v21, v39, v12);
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
0x1800b640c  mov     rax, rsp
0x1800b640f  mov     [rax+10h], rbx
0x1800b6413  mov     [rax+18h], rsi
0x1800b6417  mov     [rax+20h], r9
0x1800b641b  push    rbp
0x1800b641c  push    rdi
0x1800b641d  push    r14
0x1800b641f  lea     rbp, [rax-7E8h]
0x1800b6426  sub     rsp, 8D0h
0x1800b642d  movaps  xmmword ptr [rax-28h], xmm6
0x1800b6431  mov     rsi, r8
0x1800b6434  mov     r14d, edx
0x1800b6437  mov     rbx, rcx
0x1800b643a  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800b6442  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800b644a  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800b644e  call    cs:__imp_QueryPerformanceCounter
0x1800b6454  mov     edi, [rbx+40h]
0x1800b6457  test    edi, edi
0x1800b6459  jns     short loc_1800B647D
0x1800b645b  mov     rcx, [rbp+7E8h]; this
0x1800b6462  mov     r9d, edi; char *
0x1800b6465  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b646c  mov     edx, 4Fh ; 'O'; void *
0x1800b6471  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6476  mov     eax, edi
0x1800b6478  jmp     loc_1800B6741
0x1800b647d  mov     ecx, 810h; cb
0x1800b6482  call    cs:__imp_CoTaskMemAlloc
0x1800b6488  mov     rdi, rax
0x1800b648b  mov     [rsp+8E0h+var_878], rax
0x1800b6490  test    rax, rax
0x1800b6493  jnz     short loc_1800B64B8
0x1800b6495  mov     rcx, [rbp+7E8h]; this
0x1800b649c  mov     ebx, 8007000Eh
0x1800b64a1  mov     r9d, ebx; char *
0x1800b64a4  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b64ab  lea     edx, [rax+52h]; void *
0x1800b64ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b64b3  jmp     loc_1800B673F
0x1800b64b8  mov     [rbp+7E0h+Src], 0
0x1800b64c0  mov     [rbp+7E0h+var_824], 0
0x1800b64c7  xor     edx, edx; Val
0x1800b64c9  mov     r8d, 800h; Size
0x1800b64cf  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800b64d3  call    memset_0
0x1800b64d8  mov     rax, [rsi]
0x1800b64db  mov     [rbp+7E0h+var_820], rax
0x1800b64df  mov     rax, [rsi+8]
0x1800b64e3  mov     [rbp+7E0h+var_818], rax
0x1800b64e7  mov     [rbp+7E0h+var_828], 5Dh ; ']'
0x1800b64ee  mov     rcx, rdi; void *
0x1800b64f1  lea     rdx, [rbp+7E0h+Src]; Src
0x1800b64f5  mov     r8d, 810h; Size
0x1800b64fb  call    memcpy_0
0x1800b6500  mov     rax, [rsp+8E0h+var_878]
0x1800b6505  mov     [rax+0Ch], r14d
0x1800b6509  lea     rax, [rbp+7E0h+arg_18]
0x1800b6510  mov     [rbp+7E0h+var_848], rax
0x1800b6514  lea     rax, [rsp+8E0h+var_878]
0x1800b6519  mov     [rbp+7E0h+var_840], rax
0x1800b651d  mov     [rbp+7E0h+var_838], 1
0x1800b6521  mov     rcx, [rbx+28h]
0x1800b6525  mov     rax, [rcx]
0x1800b6528  mov     r9d, 810h
0x1800b652e  mov     r8, [rsp+8E0h+var_878]
0x1800b6533  mov     edx, r14d
0x1800b6536  mov     rax, [rax+20h]
0x1800b653a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b653f  mov     edi, eax
0x1800b6541  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800b6545  call    cs:__imp_QueryPerformanceCounter
0x1800b654b  xorps   xmm6, xmm6
0x1800b654e  cmp     qword ptr [rbx+48h], 0
0x1800b6553  jz      short loc_1800B6577
0x1800b6555  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800b6559  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800b655d  cvtsi2ss xmm6, rcx
0x1800b6562  mulss   xmm6, cs:__real@447a0000
0x1800b656a  xorps   xmm0, xmm0
0x1800b656d  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800b6573  divss   xmm6, xmm0
0x1800b6577  mov     rcx, [rsp+8E0h+var_878]
0x1800b657c  cmp     dword ptr [rcx+8], 1
0x1800b6580  jnz     loc_1800B663C
0x1800b6586  mov     [rsp+8E0h+var_870], 0
0x1800b658f  lea     rdx, [rsp+8E0h+var_870]
0x1800b6594  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b6599  test    eax, eax
0x1800b659b  js      loc_1800B66AD
0x1800b65a1  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b65a6  mov     r8, rax
0x1800b65a9  mov     ecx, [rax]
0x1800b65ab  cmp     ecx, 4
0x1800b65ae  jbe     loc_1800B66AD
0x1800b65b4  mov     [rbp+7E0h+arg_0], edi
0x1800b65ba  movss   [rsp+8E0h+var_868], xmm6
0x1800b65c0  mov     [rbp+7E0h+var_860], rbx
0x1800b65c4  mov     rdx, [rsp+8E0h+var_870]
0x1800b65c9  mov     ecx, [rdx+10h]
0x1800b65cc  mov     [rsp+8E0h+var_864], ecx
0x1800b65d0  mov     ecx, [rdx+4]
0x1800b65d3  mov     [rsp+8E0h+var_880], ecx
0x1800b65d7  mov     eax, [rdx+8]
0x1800b65da  mov     [rsp+8E0h+var_880+4], eax
0x1800b65de  mov     eax, [rdx]
0x1800b65e0  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800b65e4  lea     rax, [rbp+7E0h+arg_0]
0x1800b65eb  mov     [rsp+8E0h+var_890], rax
0x1800b65f0  lea     rax, [rsp+8E0h+var_868]
0x1800b65f5  mov     [rsp+8E0h+var_898], rax
0x1800b65fa  lea     rax, [rbp+7E0h+var_860]
0x1800b65fe  mov     [rsp+8E0h+var_8A0], rax
0x1800b6603  lea     rax, [rsp+8E0h+var_864]
0x1800b6608  mov     [rsp+8E0h+var_8A8], rax
0x1800b660d  lea     rax, [rsp+8E0h+var_880]
0x1800b6612  mov     [rsp+8E0h+var_8B0], rax
0x1800b6617  lea     rax, [rsp+8E0h+var_880+4]
0x1800b661c  mov     [rsp+8E0h+var_8B8], rax
0x1800b6621  lea     rax, [rsp+8E0h+var_870]
0x1800b6626  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800b662b  lea     rdx, unk_180166980
0x1800b6632  mov     rcx, r8
0x1800b6635  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b663a  jmp     short loc_1800B66AD
0x1800b663c  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b6641  mov     ecx, [rax]
0x1800b6643  cmp     ecx, 4
0x1800b6646  jbe     short loc_1800B66AD
0x1800b6648  mov     [rbp+7E0h+arg_0], edi
0x1800b664e  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800b6654  mov     [rbp+7E0h+var_860], rbx
0x1800b6658  mov     rcx, [rsp+8E0h+var_878]
0x1800b665d  mov     edx, [rcx+8]
0x1800b6660  mov     [rsp+8E0h+var_880+4], edx
0x1800b6664  mov     ecx, [rbx+30h]
0x1800b6667  mov     [rsp+8E0h+var_880], ecx
0x1800b666b  lea     rcx, [rbp+7E0h+arg_0]
0x1800b6672  mov     [rsp+8E0h+var_8A0], rcx
0x1800b6677  lea     rcx, [rsp+8E0h+var_870]
0x1800b667c  mov     [rsp+8E0h+var_8A8], rcx
0x1800b6681  lea     rcx, [rbp+7E0h+var_860]
0x1800b6685  mov     [rsp+8E0h+var_8B0], rcx
0x1800b668a  lea     rcx, [rsp+8E0h+var_880+4]
0x1800b668f  mov     [rsp+8E0h+var_8B8], rcx
0x1800b6694  lea     rcx, [rsp+8E0h+var_880]
0x1800b6699  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800b669e  lea     rdx, unk_1801669F9
0x1800b66a5  mov     rcx, rax
0x1800b66a8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b66ad  mov     rcx, [rbp+7E8h]; this
0x1800b66b4  test    edi, edi
0x1800b66b6  jns     short loc_1800B66DB
0x1800b66b8  mov     r9d, edi; char *
0x1800b66bb  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b66c2  mov     edx, 81h; void *
0x1800b66c7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b66cc  mov     rax, [rbx]
0x1800b66cf  mov     rcx, rbx
0x1800b66d2  mov     rax, [rax+20h]
0x1800b66d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b66db  mov     ebx, [rbx+40h]
0x1800b66de  test    ebx, ebx
0x1800b66e0  jns     short loc_1800B66E9
0x1800b66e2  mov     edx, 8Ah
0x1800b66e7  jmp     short loc_1800B66FA
0x1800b66e9  mov     rcx, [rsp+8E0h+var_878]
0x1800b66ee  mov     ebx, [rcx+4]
0x1800b66f1  test    ebx, ebx
0x1800b66f3  jns     short loc_1800B6712
0x1800b66f5  mov     edx, 8Ch; void *
0x1800b66fa  mov     r9d, ebx; char *
0x1800b66fd  mov     rcx, [rbp+7E8h]; this
0x1800b6704  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b670b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6710  jmp     short loc_1800B6730
0x1800b6712  mov     rdx, [rbp+7E0h+arg_20]
0x1800b6719  call    ??$CastTo@UXvmAudioEndpointVolumeStepUp@@@XvmMessage@@QEAAJPEAPEAUXvmAudioEndpointVolumeStepUp@@@Z; XvmMessage::CastTo<XvmAudioEndpointVolumeStepUp>(XvmAudioEndpointVolumeStepUp * *)
0x1800b671e  mov     ebx, eax
0x1800b6720  test    eax, eax
0x1800b6722  jns     short loc_1800B672E
0x1800b6724  mov     r9d, eax
0x1800b6727  mov     edx, 8Dh
0x1800b672c  jmp     short loc_1800B66FD
0x1800b672e  xor     ebx, ebx
0x1800b6730  mov     rcx, [rbp+7E0h+arg_18]
0x1800b6737  mov     rax, [rsp+8E0h+var_878]
0x1800b673c  mov     [rcx], rax
0x1800b673f  mov     eax, ebx
0x1800b6741  lea     r11, [rsp+8E0h+var_10]
0x1800b6749  mov     rbx, [r11+28h]
0x1800b674d  mov     rsi, [r11+30h]
0x1800b6751  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b6756  mov     rsp, r11
0x1800b6759  pop     r14
0x1800b675b  pop     rdi
0x1800b675c  pop     rbp
0x1800b675d  retn
```
