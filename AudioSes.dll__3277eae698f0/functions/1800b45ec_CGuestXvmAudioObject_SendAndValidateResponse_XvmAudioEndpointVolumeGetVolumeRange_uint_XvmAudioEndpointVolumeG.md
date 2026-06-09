# CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetVolumeRange>(uint,XvmAudioEndpointVolumeGetVolumeRange,XvmMessage * *,XvmAudioEndpointVolumeGetVolumeRange * *)

- ea: `0x1800b45ec`
- end: `0x1800b493c`
- name: `??$SendAndValidateResponse@UXvmAudioEndpointVolumeGetVolumeRange@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeGetVolumeRange@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `848`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b70f0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a5e40`
- `0x1800b45ec`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b462e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b4723`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b462e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b4723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4662`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4662`

## string_xrefs

- `0x1800b4645`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b4684`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b4899`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b48e2`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetVolumeRange>(
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
  int Volume; // eax
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
  int v35; // [rsp+D0h] [rbp-38h]
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
    v35 = *((_DWORD *)a3 + 2);
    v32 = 96;
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
            (unsigned int)qword_180167428,
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
          (unsigned int)byte_180167315,
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
        Volume = XvmMessage::CastTo<XvmAudioEndpointVolumeGetVolumeRange>(v21, v40, v12);
        v9 = Volume;
        if ( Volume >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)Volume;
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
0x1800b45ec  mov     rax, rsp
0x1800b45ef  mov     [rax+10h], rbx
0x1800b45f3  mov     [rax+18h], rsi
0x1800b45f7  mov     [rax+20h], r9
0x1800b45fb  push    rbp
0x1800b45fc  push    rdi
0x1800b45fd  push    r14
0x1800b45ff  lea     rbp, [rax-7E8h]
0x1800b4606  sub     rsp, 8D0h
0x1800b460d  movaps  xmmword ptr [rax-28h], xmm6
0x1800b4611  mov     rsi, r8
0x1800b4614  mov     r14d, edx
0x1800b4617  mov     rbx, rcx
0x1800b461a  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800b4622  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800b462a  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800b462e  call    cs:__imp_QueryPerformanceCounter
0x1800b4634  mov     edi, [rbx+40h]
0x1800b4637  test    edi, edi
0x1800b4639  jns     short loc_1800B465D
0x1800b463b  mov     rcx, [rbp+7E8h]; this
0x1800b4642  mov     r9d, edi; char *
0x1800b4645  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b464c  mov     edx, 4Fh ; 'O'; void *
0x1800b4651  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4656  mov     eax, edi
0x1800b4658  jmp     loc_1800B491F
0x1800b465d  mov     ecx, 810h; cb
0x1800b4662  call    cs:__imp_CoTaskMemAlloc
0x1800b4668  mov     rdi, rax
0x1800b466b  mov     [rsp+8E0h+var_878], rax
0x1800b4670  test    rax, rax
0x1800b4673  jnz     short loc_1800B4698
0x1800b4675  mov     rcx, [rbp+7E8h]; this
0x1800b467c  mov     ebx, 8007000Eh
0x1800b4681  mov     r9d, ebx; char *
0x1800b4684  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b468b  lea     edx, [rax+52h]; void *
0x1800b468e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4693  jmp     loc_1800B491D
0x1800b4698  mov     [rbp+7E0h+Src], 0
0x1800b46a0  mov     [rbp+7E0h+var_824], 0
0x1800b46a7  xor     edx, edx; Val
0x1800b46a9  mov     r8d, 800h; Size
0x1800b46af  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800b46b3  call    memset_0
0x1800b46b8  mov     rax, [rsi]
0x1800b46bb  mov     [rbp+7E0h+var_820], rax
0x1800b46bf  mov     eax, [rsi+8]
0x1800b46c2  mov     [rbp+7E0h+var_818], eax
0x1800b46c5  mov     [rbp+7E0h+var_828], 60h ; '`'
0x1800b46cc  mov     rcx, rdi; void *
0x1800b46cf  lea     rdx, [rbp+7E0h+Src]; Src
0x1800b46d3  mov     r8d, 810h; Size
0x1800b46d9  call    memcpy_0
0x1800b46de  mov     rax, [rsp+8E0h+var_878]
0x1800b46e3  mov     [rax+0Ch], r14d
0x1800b46e7  lea     rax, [rbp+7E0h+arg_18]
0x1800b46ee  mov     [rbp+7E0h+var_848], rax
0x1800b46f2  lea     rax, [rsp+8E0h+var_878]
0x1800b46f7  mov     [rbp+7E0h+var_840], rax
0x1800b46fb  mov     [rbp+7E0h+var_838], 1
0x1800b46ff  mov     rcx, [rbx+28h]
0x1800b4703  mov     rax, [rcx]
0x1800b4706  mov     r9d, 810h
0x1800b470c  mov     r8, [rsp+8E0h+var_878]
0x1800b4711  mov     edx, r14d
0x1800b4714  mov     rax, [rax+20h]
0x1800b4718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b471d  mov     edi, eax
0x1800b471f  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800b4723  call    cs:__imp_QueryPerformanceCounter
0x1800b4729  xorps   xmm6, xmm6
0x1800b472c  cmp     qword ptr [rbx+48h], 0
0x1800b4731  jz      short loc_1800B4755
0x1800b4733  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800b4737  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800b473b  cvtsi2ss xmm6, rcx
0x1800b4740  mulss   xmm6, cs:__real@447a0000
0x1800b4748  xorps   xmm0, xmm0
0x1800b474b  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800b4751  divss   xmm6, xmm0
0x1800b4755  mov     rcx, [rsp+8E0h+var_878]
0x1800b475a  cmp     dword ptr [rcx+8], 1
0x1800b475e  jnz     loc_1800B481A
0x1800b4764  mov     [rsp+8E0h+var_870], 0
0x1800b476d  lea     rdx, [rsp+8E0h+var_870]
0x1800b4772  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b4777  test    eax, eax
0x1800b4779  js      loc_1800B488B
0x1800b477f  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b4784  mov     r8, rax
0x1800b4787  mov     ecx, [rax]
0x1800b4789  cmp     ecx, 4
0x1800b478c  jbe     loc_1800B488B
0x1800b4792  mov     [rbp+7E0h+arg_0], edi
0x1800b4798  movss   [rsp+8E0h+var_868], xmm6
0x1800b479e  mov     [rbp+7E0h+var_860], rbx
0x1800b47a2  mov     rdx, [rsp+8E0h+var_870]
0x1800b47a7  mov     ecx, [rdx+10h]
0x1800b47aa  mov     [rsp+8E0h+var_864], ecx
0x1800b47ae  mov     ecx, [rdx+4]
0x1800b47b1  mov     [rsp+8E0h+var_880], ecx
0x1800b47b5  mov     eax, [rdx+8]
0x1800b47b8  mov     [rsp+8E0h+var_880+4], eax
0x1800b47bc  mov     eax, [rdx]
0x1800b47be  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800b47c2  lea     rax, [rbp+7E0h+arg_0]
0x1800b47c9  mov     [rsp+8E0h+var_890], rax
0x1800b47ce  lea     rax, [rsp+8E0h+var_868]
0x1800b47d3  mov     [rsp+8E0h+var_898], rax
0x1800b47d8  lea     rax, [rbp+7E0h+var_860]
0x1800b47dc  mov     [rsp+8E0h+var_8A0], rax
0x1800b47e1  lea     rax, [rsp+8E0h+var_864]
0x1800b47e6  mov     [rsp+8E0h+var_8A8], rax
0x1800b47eb  lea     rax, [rsp+8E0h+var_880]
0x1800b47f0  mov     [rsp+8E0h+var_8B0], rax
0x1800b47f5  lea     rax, [rsp+8E0h+var_880+4]
0x1800b47fa  mov     [rsp+8E0h+var_8B8], rax
0x1800b47ff  lea     rax, [rsp+8E0h+var_870]
0x1800b4804  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800b4809  lea     rdx, qword_180167428
0x1800b4810  mov     rcx, r8
0x1800b4813  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b4818  jmp     short loc_1800B488B
0x1800b481a  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b481f  mov     ecx, [rax]
0x1800b4821  cmp     ecx, 4
0x1800b4824  jbe     short loc_1800B488B
0x1800b4826  mov     [rbp+7E0h+arg_0], edi
0x1800b482c  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800b4832  mov     [rbp+7E0h+var_860], rbx
0x1800b4836  mov     rcx, [rsp+8E0h+var_878]
0x1800b483b  mov     edx, [rcx+8]
0x1800b483e  mov     [rsp+8E0h+var_880+4], edx
0x1800b4842  mov     ecx, [rbx+30h]
0x1800b4845  mov     [rsp+8E0h+var_880], ecx
0x1800b4849  lea     rcx, [rbp+7E0h+arg_0]
0x1800b4850  mov     [rsp+8E0h+var_8A0], rcx
0x1800b4855  lea     rcx, [rsp+8E0h+var_870]
0x1800b485a  mov     [rsp+8E0h+var_8A8], rcx
0x1800b485f  lea     rcx, [rbp+7E0h+var_860]
0x1800b4863  mov     [rsp+8E0h+var_8B0], rcx
0x1800b4868  lea     rcx, [rsp+8E0h+var_880+4]
0x1800b486d  mov     [rsp+8E0h+var_8B8], rcx
0x1800b4872  lea     rcx, [rsp+8E0h+var_880]
0x1800b4877  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800b487c  lea     rdx, byte_180167315
0x1800b4883  mov     rcx, rax
0x1800b4886  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b488b  mov     rcx, [rbp+7E8h]; this
0x1800b4892  test    edi, edi
0x1800b4894  jns     short loc_1800B48B9
0x1800b4896  mov     r9d, edi; char *
0x1800b4899  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b48a0  mov     edx, 81h; void *
0x1800b48a5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b48aa  mov     rax, [rbx]
0x1800b48ad  mov     rcx, rbx
0x1800b48b0  mov     rax, [rax+20h]
0x1800b48b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b48b9  mov     ebx, [rbx+40h]
0x1800b48bc  test    ebx, ebx
0x1800b48be  jns     short loc_1800B48C7
0x1800b48c0  mov     edx, 8Ah
0x1800b48c5  jmp     short loc_1800B48D8
0x1800b48c7  mov     rcx, [rsp+8E0h+var_878]
0x1800b48cc  mov     ebx, [rcx+4]
0x1800b48cf  test    ebx, ebx
0x1800b48d1  jns     short loc_1800B48F0
0x1800b48d3  mov     edx, 8Ch; void *
0x1800b48d8  mov     r9d, ebx; char *
0x1800b48db  mov     rcx, [rbp+7E8h]; this
0x1800b48e2  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b48e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b48ee  jmp     short loc_1800B490E
0x1800b48f0  mov     rdx, [rbp+7E0h+arg_20]
0x1800b48f7  call    ??$CastTo@UXvmAudioEndpointVolumeGetVolumeRange@@@XvmMessage@@QEAAJPEAPEAUXvmAudioEndpointVolumeGetVolumeRange@@@Z; XvmMessage::CastTo<XvmAudioEndpointVolumeGetVolumeRange>(XvmAudioEndpointVolumeGetVolumeRange * *)
0x1800b48fc  mov     ebx, eax
0x1800b48fe  test    eax, eax
0x1800b4900  jns     short loc_1800B490C
0x1800b4902  mov     r9d, eax
0x1800b4905  mov     edx, 8Dh
0x1800b490a  jmp     short loc_1800B48DB
0x1800b490c  xor     ebx, ebx
0x1800b490e  mov     rcx, [rbp+7E0h+arg_18]
0x1800b4915  mov     rax, [rsp+8E0h+var_878]
0x1800b491a  mov     [rcx], rax
0x1800b491d  mov     eax, ebx
0x1800b491f  lea     r11, [rsp+8E0h+var_10]
0x1800b4927  mov     rbx, [r11+28h]
0x1800b492b  mov     rsi, [r11+30h]
0x1800b492f  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b4934  mov     rsp, r11
0x1800b4937  pop     r14
0x1800b4939  pop     rdi
0x1800b493a  pop     rbp
0x1800b493b  retn
```
