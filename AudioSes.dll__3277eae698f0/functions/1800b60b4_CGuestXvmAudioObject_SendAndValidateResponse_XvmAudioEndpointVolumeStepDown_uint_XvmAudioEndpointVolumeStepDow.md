# CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeStepDown>(uint,XvmAudioEndpointVolumeStepDown,XvmMessage * *,XvmAudioEndpointVolumeStepDown * *)

- ea: `0x1800b60b4`
- end: `0x1800b6406`
- name: `??$SendAndValidateResponse@UXvmAudioEndpointVolumeStepDown@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeStepDown@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `850`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b7880`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a6080`
- `0x1800b60b4`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b60f6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b61ed`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b60f6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b61ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b612a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b612a`

## string_xrefs

- `0x1800b610d`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b614c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b6363`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b63ac`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeStepDown>(
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
    v32 = 94;
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
            (unsigned int)&dword_180166954,
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
          (unsigned int)word_1801668BA,
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
        v18 = XvmMessage::CastTo<XvmAudioEndpointVolumeStepDown>(v21, v39, v12);
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
0x1800b60b4  mov     rax, rsp
0x1800b60b7  mov     [rax+10h], rbx
0x1800b60bb  mov     [rax+18h], rsi
0x1800b60bf  mov     [rax+20h], r9
0x1800b60c3  push    rbp
0x1800b60c4  push    rdi
0x1800b60c5  push    r14
0x1800b60c7  lea     rbp, [rax-7E8h]
0x1800b60ce  sub     rsp, 8D0h
0x1800b60d5  movaps  xmmword ptr [rax-28h], xmm6
0x1800b60d9  mov     rsi, r8
0x1800b60dc  mov     r14d, edx
0x1800b60df  mov     rbx, rcx
0x1800b60e2  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800b60ea  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800b60f2  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800b60f6  call    cs:__imp_QueryPerformanceCounter
0x1800b60fc  mov     edi, [rbx+40h]
0x1800b60ff  test    edi, edi
0x1800b6101  jns     short loc_1800B6125
0x1800b6103  mov     rcx, [rbp+7E8h]; this
0x1800b610a  mov     r9d, edi; char *
0x1800b610d  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b6114  mov     edx, 4Fh ; 'O'; void *
0x1800b6119  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b611e  mov     eax, edi
0x1800b6120  jmp     loc_1800B63E9
0x1800b6125  mov     ecx, 810h; cb
0x1800b612a  call    cs:__imp_CoTaskMemAlloc
0x1800b6130  mov     rdi, rax
0x1800b6133  mov     [rsp+8E0h+var_878], rax
0x1800b6138  test    rax, rax
0x1800b613b  jnz     short loc_1800B6160
0x1800b613d  mov     rcx, [rbp+7E8h]; this
0x1800b6144  mov     ebx, 8007000Eh
0x1800b6149  mov     r9d, ebx; char *
0x1800b614c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b6153  lea     edx, [rax+52h]; void *
0x1800b6156  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b615b  jmp     loc_1800B63E7
0x1800b6160  mov     [rbp+7E0h+Src], 0
0x1800b6168  mov     [rbp+7E0h+var_824], 0
0x1800b616f  xor     edx, edx; Val
0x1800b6171  mov     r8d, 800h; Size
0x1800b6177  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800b617b  call    memset_0
0x1800b6180  mov     rax, [rsi]
0x1800b6183  mov     [rbp+7E0h+var_820], rax
0x1800b6187  mov     rax, [rsi+8]
0x1800b618b  mov     [rbp+7E0h+var_818], rax
0x1800b618f  mov     [rbp+7E0h+var_828], 5Eh ; '^'
0x1800b6196  mov     rcx, rdi; void *
0x1800b6199  lea     rdx, [rbp+7E0h+Src]; Src
0x1800b619d  mov     r8d, 810h; Size
0x1800b61a3  call    memcpy_0
0x1800b61a8  mov     rax, [rsp+8E0h+var_878]
0x1800b61ad  mov     [rax+0Ch], r14d
0x1800b61b1  lea     rax, [rbp+7E0h+arg_18]
0x1800b61b8  mov     [rbp+7E0h+var_848], rax
0x1800b61bc  lea     rax, [rsp+8E0h+var_878]
0x1800b61c1  mov     [rbp+7E0h+var_840], rax
0x1800b61c5  mov     [rbp+7E0h+var_838], 1
0x1800b61c9  mov     rcx, [rbx+28h]
0x1800b61cd  mov     rax, [rcx]
0x1800b61d0  mov     r9d, 810h
0x1800b61d6  mov     r8, [rsp+8E0h+var_878]
0x1800b61db  mov     edx, r14d
0x1800b61de  mov     rax, [rax+20h]
0x1800b61e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b61e7  mov     edi, eax
0x1800b61e9  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800b61ed  call    cs:__imp_QueryPerformanceCounter
0x1800b61f3  xorps   xmm6, xmm6
0x1800b61f6  cmp     qword ptr [rbx+48h], 0
0x1800b61fb  jz      short loc_1800B621F
0x1800b61fd  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800b6201  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800b6205  cvtsi2ss xmm6, rcx
0x1800b620a  mulss   xmm6, cs:__real@447a0000
0x1800b6212  xorps   xmm0, xmm0
0x1800b6215  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800b621b  divss   xmm6, xmm0
0x1800b621f  mov     rcx, [rsp+8E0h+var_878]
0x1800b6224  cmp     dword ptr [rcx+8], 1
0x1800b6228  jnz     loc_1800B62E4
0x1800b622e  mov     [rsp+8E0h+var_870], 0
0x1800b6237  lea     rdx, [rsp+8E0h+var_870]
0x1800b623c  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b6241  test    eax, eax
0x1800b6243  js      loc_1800B6355
0x1800b6249  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b624e  mov     r8, rax
0x1800b6251  mov     ecx, [rax]
0x1800b6253  cmp     ecx, 4
0x1800b6256  jbe     loc_1800B6355
0x1800b625c  mov     [rbp+7E0h+arg_0], edi
0x1800b6262  movss   [rsp+8E0h+var_868], xmm6
0x1800b6268  mov     [rbp+7E0h+var_860], rbx
0x1800b626c  mov     rdx, [rsp+8E0h+var_870]
0x1800b6271  mov     ecx, [rdx+10h]
0x1800b6274  mov     [rsp+8E0h+var_864], ecx
0x1800b6278  mov     ecx, [rdx+4]
0x1800b627b  mov     [rsp+8E0h+var_880], ecx
0x1800b627f  mov     eax, [rdx+8]
0x1800b6282  mov     [rsp+8E0h+var_880+4], eax
0x1800b6286  mov     eax, [rdx]
0x1800b6288  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800b628c  lea     rax, [rbp+7E0h+arg_0]
0x1800b6293  mov     [rsp+8E0h+var_890], rax
0x1800b6298  lea     rax, [rsp+8E0h+var_868]
0x1800b629d  mov     [rsp+8E0h+var_898], rax
0x1800b62a2  lea     rax, [rbp+7E0h+var_860]
0x1800b62a6  mov     [rsp+8E0h+var_8A0], rax
0x1800b62ab  lea     rax, [rsp+8E0h+var_864]
0x1800b62b0  mov     [rsp+8E0h+var_8A8], rax
0x1800b62b5  lea     rax, [rsp+8E0h+var_880]
0x1800b62ba  mov     [rsp+8E0h+var_8B0], rax
0x1800b62bf  lea     rax, [rsp+8E0h+var_880+4]
0x1800b62c4  mov     [rsp+8E0h+var_8B8], rax
0x1800b62c9  lea     rax, [rsp+8E0h+var_870]
0x1800b62ce  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800b62d3  lea     rdx, dword_180166954
0x1800b62da  mov     rcx, r8
0x1800b62dd  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b62e2  jmp     short loc_1800B6355
0x1800b62e4  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b62e9  mov     ecx, [rax]
0x1800b62eb  cmp     ecx, 4
0x1800b62ee  jbe     short loc_1800B6355
0x1800b62f0  mov     [rbp+7E0h+arg_0], edi
0x1800b62f6  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800b62fc  mov     [rbp+7E0h+var_860], rbx
0x1800b6300  mov     rcx, [rsp+8E0h+var_878]
0x1800b6305  mov     edx, [rcx+8]
0x1800b6308  mov     [rsp+8E0h+var_880+4], edx
0x1800b630c  mov     ecx, [rbx+30h]
0x1800b630f  mov     [rsp+8E0h+var_880], ecx
0x1800b6313  lea     rcx, [rbp+7E0h+arg_0]
0x1800b631a  mov     [rsp+8E0h+var_8A0], rcx
0x1800b631f  lea     rcx, [rsp+8E0h+var_870]
0x1800b6324  mov     [rsp+8E0h+var_8A8], rcx
0x1800b6329  lea     rcx, [rbp+7E0h+var_860]
0x1800b632d  mov     [rsp+8E0h+var_8B0], rcx
0x1800b6332  lea     rcx, [rsp+8E0h+var_880+4]
0x1800b6337  mov     [rsp+8E0h+var_8B8], rcx
0x1800b633c  lea     rcx, [rsp+8E0h+var_880]
0x1800b6341  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800b6346  lea     rdx, word_1801668BA
0x1800b634d  mov     rcx, rax
0x1800b6350  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b6355  mov     rcx, [rbp+7E8h]; this
0x1800b635c  test    edi, edi
0x1800b635e  jns     short loc_1800B6383
0x1800b6360  mov     r9d, edi; char *
0x1800b6363  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b636a  mov     edx, 81h; void *
0x1800b636f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b6374  mov     rax, [rbx]
0x1800b6377  mov     rcx, rbx
0x1800b637a  mov     rax, [rax+20h]
0x1800b637e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6383  mov     ebx, [rbx+40h]
0x1800b6386  test    ebx, ebx
0x1800b6388  jns     short loc_1800B6391
0x1800b638a  mov     edx, 8Ah
0x1800b638f  jmp     short loc_1800B63A2
0x1800b6391  mov     rcx, [rsp+8E0h+var_878]
0x1800b6396  mov     ebx, [rcx+4]
0x1800b6399  test    ebx, ebx
0x1800b639b  jns     short loc_1800B63BA
0x1800b639d  mov     edx, 8Ch; void *
0x1800b63a2  mov     r9d, ebx; char *
0x1800b63a5  mov     rcx, [rbp+7E8h]; this
0x1800b63ac  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b63b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b63b8  jmp     short loc_1800B63D8
0x1800b63ba  mov     rdx, [rbp+7E0h+arg_20]
0x1800b63c1  call    ??$CastTo@UXvmAudioEndpointVolumeStepDown@@@XvmMessage@@QEAAJPEAPEAUXvmAudioEndpointVolumeStepDown@@@Z; XvmMessage::CastTo<XvmAudioEndpointVolumeStepDown>(XvmAudioEndpointVolumeStepDown * *)
0x1800b63c6  mov     ebx, eax
0x1800b63c8  test    eax, eax
0x1800b63ca  jns     short loc_1800B63D6
0x1800b63cc  mov     r9d, eax
0x1800b63cf  mov     edx, 8Dh
0x1800b63d4  jmp     short loc_1800B63A5
0x1800b63d6  xor     ebx, ebx
0x1800b63d8  mov     rcx, [rbp+7E0h+arg_18]
0x1800b63df  mov     rax, [rsp+8E0h+var_878]
0x1800b63e4  mov     [rcx], rax
0x1800b63e7  mov     eax, ebx
0x1800b63e9  lea     r11, [rsp+8E0h+var_10]
0x1800b63f1  mov     rbx, [r11+28h]
0x1800b63f5  mov     rsi, [r11+30h]
0x1800b63f9  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b63fe  mov     rsp, r11
0x1800b6401  pop     r14
0x1800b6403  pop     rdi
0x1800b6404  pop     rbp
0x1800b6405  retn
```
