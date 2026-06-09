# CGuestXvmAudioObject::SendAndValidateResponse<XvmFormatEnumeratorGetCount>(uint,XvmFormatEnumeratorGetCount,XvmMessage * *,XvmFormatEnumeratorGetCount * *)

- ea: `0x1800fe8f4`
- end: `0x1800fec3a`
- name: `??$SendAndValidateResponse@UXvmFormatEnumeratorGetCount@@@CGuestXvmAudioObject@@QEAAJIUXvmFormatEnumeratorGetCount@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180100dd0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800fa000`
- `0x1800fe8f4`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800fe936`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800fea21`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800fe936`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800fea21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fe96a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800fe96a`

## string_xrefs

- `0x1800fe94d`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800fe98c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800feb97`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800febe0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmFormatEnumeratorGetCount>(
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
    v32 = 58;
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
            (unsigned int)&unk_180170F8A,
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
          (unsigned int)&unk_180170F3D,
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
        v18 = XvmMessage::CastTo<XvmFormatEnumeratorGetCount>(v21, v39, v12);
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
0x1800fe8f4  mov     rax, rsp
0x1800fe8f7  mov     [rax+10h], rbx
0x1800fe8fb  mov     [rax+18h], rsi
0x1800fe8ff  mov     [rax+20h], r9
0x1800fe903  push    rbp
0x1800fe904  push    rdi
0x1800fe905  push    r14
0x1800fe907  lea     rbp, [rax-7E8h]
0x1800fe90e  sub     rsp, 8D0h
0x1800fe915  movaps  xmmword ptr [rax-28h], xmm6
0x1800fe919  mov     ebx, r8d
0x1800fe91c  mov     r14d, edx
0x1800fe91f  mov     rdi, rcx
0x1800fe922  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800fe92a  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800fe932  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800fe936  call    cs:__imp_QueryPerformanceCounter
0x1800fe93c  mov     esi, [rdi+40h]
0x1800fe93f  test    esi, esi
0x1800fe941  jns     short loc_1800FE965
0x1800fe943  mov     rcx, [rbp+7E8h]; this
0x1800fe94a  mov     r9d, esi; char *
0x1800fe94d  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800fe954  mov     edx, 4Fh ; 'O'; void *
0x1800fe959  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fe95e  mov     eax, esi
0x1800fe960  jmp     loc_1800FEC1D
0x1800fe965  mov     ecx, 810h; cb
0x1800fe96a  call    cs:__imp_CoTaskMemAlloc
0x1800fe970  mov     rsi, rax
0x1800fe973  mov     [rsp+8E0h+var_878], rax
0x1800fe978  test    rax, rax
0x1800fe97b  jnz     short loc_1800FE9A0
0x1800fe97d  mov     rcx, [rbp+7E8h]; this
0x1800fe984  mov     ebx, 8007000Eh
0x1800fe989  mov     r9d, ebx; char *
0x1800fe98c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800fe993  lea     edx, [rax+52h]; void *
0x1800fe996  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fe99b  jmp     loc_1800FEC1B
0x1800fe9a0  mov     [rbp+7E0h+Src], 0
0x1800fe9a8  mov     [rbp+7E0h+var_824], 0
0x1800fe9af  xor     edx, edx; Val
0x1800fe9b1  mov     r8d, 800h; Size
0x1800fe9b7  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800fe9bb  call    memset_0
0x1800fe9c0  mov     [rbp+7E0h+var_820], ebx
0x1800fe9c3  mov     [rbp+7E0h+var_828], 3Ah ; ':'
0x1800fe9ca  mov     rcx, rsi; void *
0x1800fe9cd  lea     rdx, [rbp+7E0h+Src]; Src
0x1800fe9d1  mov     r8d, 810h; Size
0x1800fe9d7  call    memcpy_0
0x1800fe9dc  mov     rax, [rsp+8E0h+var_878]
0x1800fe9e1  mov     [rax+0Ch], r14d
0x1800fe9e5  lea     rax, [rbp+7E0h+arg_18]
0x1800fe9ec  mov     [rbp+7E0h+var_848], rax
0x1800fe9f0  lea     rax, [rsp+8E0h+var_878]
0x1800fe9f5  mov     [rbp+7E0h+var_840], rax
0x1800fe9f9  mov     [rbp+7E0h+var_838], 1
0x1800fe9fd  mov     rcx, [rdi+28h]
0x1800fea01  mov     rax, [rcx]
0x1800fea04  mov     r9d, 810h
0x1800fea0a  mov     r8, [rsp+8E0h+var_878]
0x1800fea0f  mov     edx, r14d
0x1800fea12  mov     rax, [rax+20h]
0x1800fea16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fea1b  mov     ebx, eax
0x1800fea1d  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800fea21  call    cs:__imp_QueryPerformanceCounter
0x1800fea27  xorps   xmm6, xmm6
0x1800fea2a  cmp     qword ptr [rdi+48h], 0
0x1800fea2f  jz      short loc_1800FEA53
0x1800fea31  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800fea35  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800fea39  cvtsi2ss xmm6, rcx
0x1800fea3e  mulss   xmm6, cs:__real@447a0000
0x1800fea46  xorps   xmm0, xmm0
0x1800fea49  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800fea4f  divss   xmm6, xmm0
0x1800fea53  mov     rcx, [rsp+8E0h+var_878]
0x1800fea58  cmp     dword ptr [rcx+8], 1
0x1800fea5c  jnz     loc_1800FEB18
0x1800fea62  mov     [rsp+8E0h+var_870], 0
0x1800fea6b  lea     rdx, [rsp+8E0h+var_870]
0x1800fea70  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800fea75  test    eax, eax
0x1800fea77  js      loc_1800FEB89
0x1800fea7d  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800fea82  mov     r8, rax
0x1800fea85  mov     ecx, [rax]
0x1800fea87  cmp     ecx, 4
0x1800fea8a  jbe     loc_1800FEB89
0x1800fea90  mov     [rbp+7E0h+arg_0], ebx
0x1800fea96  movss   [rsp+8E0h+var_868], xmm6
0x1800fea9c  mov     [rbp+7E0h+var_860], rdi
0x1800feaa0  mov     rdx, [rsp+8E0h+var_870]
0x1800feaa5  mov     ecx, [rdx+10h]
0x1800feaa8  mov     [rsp+8E0h+var_864], ecx
0x1800feaac  mov     ecx, [rdx+4]
0x1800feaaf  mov     [rsp+8E0h+var_880], ecx
0x1800feab3  mov     eax, [rdx+8]
0x1800feab6  mov     [rsp+8E0h+var_880+4], eax
0x1800feaba  mov     eax, [rdx]
0x1800feabc  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800feac0  lea     rax, [rbp+7E0h+arg_0]
0x1800feac7  mov     [rsp+8E0h+var_890], rax
0x1800feacc  lea     rax, [rsp+8E0h+var_868]
0x1800fead1  mov     [rsp+8E0h+var_898], rax
0x1800fead6  lea     rax, [rbp+7E0h+var_860]
0x1800feada  mov     [rsp+8E0h+var_8A0], rax
0x1800feadf  lea     rax, [rsp+8E0h+var_864]
0x1800feae4  mov     [rsp+8E0h+var_8A8], rax
0x1800feae9  lea     rax, [rsp+8E0h+var_880]
0x1800feaee  mov     [rsp+8E0h+var_8B0], rax
0x1800feaf3  lea     rax, [rsp+8E0h+var_880+4]
0x1800feaf8  mov     [rsp+8E0h+var_8B8], rax
0x1800feafd  lea     rax, [rsp+8E0h+var_870]
0x1800feb02  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800feb07  lea     rdx, unk_180170F8A
0x1800feb0e  mov     rcx, r8
0x1800feb11  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800feb16  jmp     short loc_1800FEB89
0x1800feb18  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800feb1d  mov     ecx, [rax]
0x1800feb1f  cmp     ecx, 4
0x1800feb22  jbe     short loc_1800FEB89
0x1800feb24  mov     [rbp+7E0h+arg_0], ebx
0x1800feb2a  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800feb30  mov     [rbp+7E0h+var_860], rdi
0x1800feb34  mov     rcx, [rsp+8E0h+var_878]
0x1800feb39  mov     edx, [rcx+8]
0x1800feb3c  mov     [rsp+8E0h+var_880+4], edx
0x1800feb40  mov     ecx, [rdi+30h]
0x1800feb43  mov     [rsp+8E0h+var_880], ecx
0x1800feb47  lea     rcx, [rbp+7E0h+arg_0]
0x1800feb4e  mov     [rsp+8E0h+var_8A0], rcx
0x1800feb53  lea     rcx, [rsp+8E0h+var_870]
0x1800feb58  mov     [rsp+8E0h+var_8A8], rcx
0x1800feb5d  lea     rcx, [rbp+7E0h+var_860]
0x1800feb61  mov     [rsp+8E0h+var_8B0], rcx
0x1800feb66  lea     rcx, [rsp+8E0h+var_880+4]
0x1800feb6b  mov     [rsp+8E0h+var_8B8], rcx
0x1800feb70  lea     rcx, [rsp+8E0h+var_880]
0x1800feb75  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800feb7a  lea     rdx, unk_180170F3D
0x1800feb81  mov     rcx, rax
0x1800feb84  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800feb89  mov     rcx, [rbp+7E8h]; this
0x1800feb90  test    ebx, ebx
0x1800feb92  jns     short loc_1800FEBB7
0x1800feb94  mov     r9d, ebx; char *
0x1800feb97  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800feb9e  mov     edx, 81h; void *
0x1800feba3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800feba8  mov     rax, [rdi]
0x1800febab  mov     rcx, rdi
0x1800febae  mov     rax, [rax+20h]
0x1800febb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800febb7  mov     ebx, [rdi+40h]
0x1800febba  test    ebx, ebx
0x1800febbc  jns     short loc_1800FEBC5
0x1800febbe  mov     edx, 8Ah
0x1800febc3  jmp     short loc_1800FEBD6
0x1800febc5  mov     rcx, [rsp+8E0h+var_878]
0x1800febca  mov     ebx, [rcx+4]
0x1800febcd  test    ebx, ebx
0x1800febcf  jns     short loc_1800FEBEE
0x1800febd1  mov     edx, 8Ch; void *
0x1800febd6  mov     r9d, ebx; char *
0x1800febd9  mov     rcx, [rbp+7E8h]; this
0x1800febe0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800febe7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800febec  jmp     short loc_1800FEC0C
0x1800febee  mov     rdx, [rbp+7E0h+arg_20]
0x1800febf5  call    ??$CastTo@UXvmFormatEnumeratorGetCount@@@XvmMessage@@QEAAJPEAPEAUXvmFormatEnumeratorGetCount@@@Z; XvmMessage::CastTo<XvmFormatEnumeratorGetCount>(XvmFormatEnumeratorGetCount * *)
0x1800febfa  mov     ebx, eax
0x1800febfc  test    eax, eax
0x1800febfe  jns     short loc_1800FEC0A
0x1800fec00  mov     r9d, eax
0x1800fec03  mov     edx, 8Dh
0x1800fec08  jmp     short loc_1800FEBD9
0x1800fec0a  xor     ebx, ebx
0x1800fec0c  mov     rcx, [rbp+7E0h+arg_18]
0x1800fec13  mov     rax, [rsp+8E0h+var_878]
0x1800fec18  mov     [rcx], rax
0x1800fec1b  mov     eax, ebx
0x1800fec1d  lea     r11, [rsp+8E0h+var_10]
0x1800fec25  mov     rbx, [r11+28h]
0x1800fec29  mov     rsi, [r11+30h]
0x1800fec2d  movaps  xmm6, xmmword ptr [r11-10h]
0x1800fec32  mov     rsp, r11
0x1800fec35  pop     r14
0x1800fec37  pop     rdi
0x1800fec38  pop     rbp
0x1800fec39  retn
```
