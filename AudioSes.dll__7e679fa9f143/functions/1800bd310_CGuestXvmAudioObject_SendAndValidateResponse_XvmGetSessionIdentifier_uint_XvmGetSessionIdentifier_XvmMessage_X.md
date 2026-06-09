# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetSessionIdentifier>(uint,XvmGetSessionIdentifier,XvmMessage * *,XvmGetSessionIdentifier * *)

- ea: `0x1800bd310`
- end: `0x1800bd6a9`
- name: `??$SendAndValidateResponse@UXvmGetSessionIdentifier@@@CGuestXvmAudioObject@@QEAAJIUXvmGetSessionIdentifier@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `921`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c0cb0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800b9440`
- `0x1800bd310`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd352`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd490`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd352`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd490`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bd386`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bd386`

## string_xrefs

- `0x1800bd369`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bd3a8`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bd606`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bd64f`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetSessionIdentifier>(
        __int64 a1,
        unsigned int a2,
        _OWORD *a3,
        ...)
{
  int v6; // esi
  _DWORD *v8; // rsi
  int v9; // ebx
  _OWORD *v10; // rax
  __int64 v11; // rcx
  int v12; // ebx
  float v13; // xmm6_4
  const struct _tlgProvider_t *v14; // r8
  int v15; // r9d
  const struct _tlgProvider_t *v16; // rax
  int v17; // r9d
  __int64 v18; // rdx
  unsigned __int64 v19; // r9
  int Session; // eax
  int v21; // [rsp+28h] [rbp-E0h]
  int v22[2]; // [rsp+68h] [rbp-A0h] BYREF
  _DWORD *v23; // [rsp+70h] [rbp-98h] BYREF
  _DWORD *v24; // [rsp+78h] [rbp-90h] BYREF
  float v25; // [rsp+80h] [rbp-88h] BYREF
  int v26; // [rsp+84h] [rbp-84h] BYREF
  __int64 v27; // [rsp+88h] [rbp-80h] BYREF
  LARGE_INTEGER v28; // [rsp+90h] [rbp-78h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+98h] [rbp-70h] BYREF
  va_list v30; // [rsp+A0h] [rbp-68h]
  _DWORD **v31; // [rsp+A8h] [rbp-60h]
  char v32; // [rsp+B0h] [rbp-58h]
  __int64 Src; // [rsp+B8h] [rbp-50h] BYREF
  int v34; // [rsp+C0h] [rbp-48h]
  int v35; // [rsp+C4h] [rbp-44h]
  _BYTE v36[2064]; // [rsp+C8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8F0h] [rbp+7E8h]
  int v38; // [rsp+8F8h] [rbp+7F0h] BYREF
  _QWORD *v39; // [rsp+910h] [rbp+808h] BYREF
  va_list va; // [rsp+910h] [rbp+808h]
  __int64 v41; // [rsp+918h] [rbp+810h]
  va_list va1; // [rsp+920h] [rbp+818h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v39 = va_arg(va1, _QWORD *);
  v41 = va_arg(va1, _QWORD);
  PerformanceCount.QuadPart = 0;
  v28.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v6 = *(_DWORD *)(a1 + 64);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
      (const char *)(unsigned int)v6,
      v21);
    return (unsigned int)v6;
  }
  v8 = CoTaskMemAlloc(0x810u);
  v23 = v8;
  if ( v8 )
  {
    Src = 0;
    v35 = 0;
    memset_0(v36, 0, 0x800u);
    v10 = v36;
    v11 = 8;
    do
    {
      *v10 = *a3;
      v10[1] = a3[1];
      v10[2] = a3[2];
      v10[3] = a3[3];
      v10[4] = a3[4];
      v10[5] = a3[5];
      v10[6] = a3[6];
      v10[7] = a3[7];
      v10 += 8;
      a3 += 8;
      --v11;
    }
    while ( v11 );
    v34 = 124;
    memcpy_0(v8, &Src, 0x810u);
    v23[3] = a2;
    va_copy(v30, va);
    v31 = &v23;
    v32 = 1;
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _DWORD *, __int64))(**(_QWORD **)(a1 + 40) + 32LL))(
            *(_QWORD *)(a1 + 40),
            a2,
            v23,
            2064);
    QueryPerformanceCounter(&v28);
    v13 = 0.0;
    if ( *(_QWORD *)(a1 + 72) )
      v13 = (float)((float)(v28.LowPart - PerformanceCount.LowPart) * 1000.0) / (float)(int)*(_QWORD *)(a1 + 72);
    if ( v23[2] == 1 )
    {
      v24 = 0;
      if ( (int)XvmMessage::CastTo<XvmActivateProxyAudioObject>(v23, &v24) >= 0 )
      {
        v14 = GuestXvmAudioObjectTelemetryProvider::Provider();
        if ( *(_DWORD *)v14 > 4u )
        {
          v38 = v12;
          v25 = v13;
          v27 = a1;
          v26 = v24[4];
          v22[0] = v24[1];
          v22[1] = v24[2];
          LODWORD(v24) = *v24;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v14,
            (unsigned int)&unk_180167A84,
            (_DWORD)v14,
            v15,
            (__int64)&v24,
            (__int64)&v22[1],
            (__int64)v22,
            (__int64)&v26,
            (__int64)&v27,
            (__int64)&v25,
            (__int64)&v38);
        }
      }
    }
    else
    {
      v16 = GuestXvmAudioObjectTelemetryProvider::Provider();
      if ( *(_DWORD *)v16 > 4u )
      {
        v38 = v12;
        *(float *)&v24 = v13;
        v27 = a1;
        v22[1] = v23[2];
        v22[0] = *(_DWORD *)(a1 + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v16,
          (unsigned int)&unk_180167AFD,
          (_DWORD)v14,
          v17,
          (__int64)v22,
          (__int64)&v22[1],
          (__int64)&v27,
          (__int64)&v24,
          (__int64)&v38);
      }
    }
    if ( v12 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
        (const char *)(unsigned int)v12,
        v21);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    }
    v9 = *(_DWORD *)(a1 + 64);
    if ( v9 >= 0 )
    {
      v9 = v23[1];
      if ( v9 >= 0 )
      {
        Session = XvmMessage::CastTo<XvmGetSessionIdentifier>(v23, v41, v14);
        v9 = Session;
        if ( Session >= 0 )
        {
          v9 = 0;
          goto LABEL_26;
        }
        v19 = (unsigned int)Session;
        v18 = 141;
LABEL_22:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
          (const char *)v19,
          v21);
LABEL_26:
        *v39 = v23;
        return (unsigned int)v9;
      }
      v18 = 140;
    }
    else
    {
      v18 = 138;
    }
    v19 = (unsigned int)v9;
    goto LABEL_22;
  }
  v9 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x52,
    (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
    (const char *)0x8007000ELL,
    v21);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800bd310  mov     rax, rsp
0x1800bd313  mov     [rax+10h], rbx
0x1800bd317  mov     [rax+18h], rsi
0x1800bd31b  mov     [rax+20h], r9
0x1800bd31f  push    rbp
0x1800bd320  push    rdi
0x1800bd321  push    r14
0x1800bd323  lea     rbp, [rax-7E8h]
0x1800bd32a  sub     rsp, 8D0h
0x1800bd331  movaps  xmmword ptr [rax-28h], xmm6
0x1800bd335  mov     rbx, r8
0x1800bd338  mov     r14d, edx
0x1800bd33b  mov     rdi, rcx
0x1800bd33e  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bd346  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800bd34e  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800bd352  call    cs:__imp_QueryPerformanceCounter
0x1800bd358  mov     esi, [rdi+40h]
0x1800bd35b  test    esi, esi
0x1800bd35d  jns     short loc_1800BD381
0x1800bd35f  mov     rcx, [rbp+7E8h]; this
0x1800bd366  mov     r9d, esi; char *
0x1800bd369  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bd370  mov     edx, 4Fh ; 'O'; void *
0x1800bd375  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd37a  mov     eax, esi
0x1800bd37c  jmp     loc_1800BD68C
0x1800bd381  mov     ecx, 810h; cb
0x1800bd386  call    cs:__imp_CoTaskMemAlloc
0x1800bd38c  mov     rsi, rax
0x1800bd38f  mov     [rsp+8E0h+var_878], rax
0x1800bd394  test    rax, rax
0x1800bd397  jnz     short loc_1800BD3BC
0x1800bd399  mov     rcx, [rbp+7E8h]; this
0x1800bd3a0  mov     ebx, 8007000Eh
0x1800bd3a5  mov     r9d, ebx; char *
0x1800bd3a8  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bd3af  lea     edx, [rax+52h]; void *
0x1800bd3b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd3b7  jmp     loc_1800BD68A
0x1800bd3bc  mov     [rbp+7E0h+Src], 0
0x1800bd3c4  mov     [rbp+7E0h+var_824], 0
0x1800bd3cb  xor     edx, edx; Val
0x1800bd3cd  mov     r8d, 800h; Size
0x1800bd3d3  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bd3d7  call    memset_0
0x1800bd3dc  lea     rax, [rbp+7E0h+var_820]
0x1800bd3e0  mov     ecx, 8
0x1800bd3e5  lea     edx, [rcx+78h]
0x1800bd3e8  movups  xmm0, xmmword ptr [rbx]
0x1800bd3eb  movups  xmmword ptr [rax], xmm0
0x1800bd3ee  movups  xmm1, xmmword ptr [rbx+10h]
0x1800bd3f2  movups  xmmword ptr [rax+10h], xmm1
0x1800bd3f6  movups  xmm0, xmmword ptr [rbx+20h]
0x1800bd3fa  movups  xmmword ptr [rax+20h], xmm0
0x1800bd3fe  movups  xmm1, xmmword ptr [rbx+30h]
0x1800bd402  movups  xmmword ptr [rax+30h], xmm1
0x1800bd406  movups  xmm0, xmmword ptr [rbx+40h]
0x1800bd40a  movups  xmmword ptr [rax+40h], xmm0
0x1800bd40e  movups  xmm1, xmmword ptr [rbx+50h]
0x1800bd412  movups  xmmword ptr [rax+50h], xmm1
0x1800bd416  movups  xmm0, xmmword ptr [rbx+60h]
0x1800bd41a  movups  xmmword ptr [rax+60h], xmm0
0x1800bd41e  movups  xmm1, xmmword ptr [rbx+70h]
0x1800bd422  movups  xmmword ptr [rax+70h], xmm1
0x1800bd426  add     rax, rdx
0x1800bd429  add     rbx, rdx
0x1800bd42c  sub     rcx, 1
0x1800bd430  jnz     short loc_1800BD3E8
0x1800bd432  mov     [rbp+7E0h+var_828], 7Ch ; '|'
0x1800bd439  mov     rcx, rsi; void *
0x1800bd43c  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bd440  mov     r8d, 810h; Size
0x1800bd446  call    memcpy_0
0x1800bd44b  mov     rax, [rsp+8E0h+var_878]
0x1800bd450  mov     [rax+0Ch], r14d
0x1800bd454  lea     rax, [rbp+7E0h+arg_18]
0x1800bd45b  mov     [rbp+7E0h+var_848], rax
0x1800bd45f  lea     rax, [rsp+8E0h+var_878]
0x1800bd464  mov     [rbp+7E0h+var_840], rax
0x1800bd468  mov     [rbp+7E0h+var_838], 1
0x1800bd46c  mov     rcx, [rdi+28h]
0x1800bd470  mov     rax, [rcx]
0x1800bd473  mov     r9d, 810h
0x1800bd479  mov     r8, [rsp+8E0h+var_878]
0x1800bd47e  mov     edx, r14d
0x1800bd481  mov     rax, [rax+20h]
0x1800bd485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd48a  mov     ebx, eax
0x1800bd48c  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800bd490  call    cs:__imp_QueryPerformanceCounter
0x1800bd496  xorps   xmm6, xmm6
0x1800bd499  cmp     qword ptr [rdi+48h], 0
0x1800bd49e  jz      short loc_1800BD4C2
0x1800bd4a0  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800bd4a4  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800bd4a8  cvtsi2ss xmm6, rcx
0x1800bd4ad  mulss   xmm6, cs:__real@447a0000
0x1800bd4b5  xorps   xmm0, xmm0
0x1800bd4b8  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800bd4be  divss   xmm6, xmm0
0x1800bd4c2  mov     rcx, [rsp+8E0h+var_878]
0x1800bd4c7  cmp     dword ptr [rcx+8], 1
0x1800bd4cb  jnz     loc_1800BD587
0x1800bd4d1  mov     [rsp+8E0h+var_870], 0
0x1800bd4da  lea     rdx, [rsp+8E0h+var_870]
0x1800bd4df  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bd4e4  test    eax, eax
0x1800bd4e6  js      loc_1800BD5F8
0x1800bd4ec  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bd4f1  mov     r8, rax
0x1800bd4f4  mov     ecx, [rax]
0x1800bd4f6  cmp     ecx, 4
0x1800bd4f9  jbe     loc_1800BD5F8
0x1800bd4ff  mov     [rbp+7E0h+arg_0], ebx
0x1800bd505  movss   [rsp+8E0h+var_868], xmm6
0x1800bd50b  mov     [rbp+7E0h+var_860], rdi
0x1800bd50f  mov     rdx, [rsp+8E0h+var_870]
0x1800bd514  mov     ecx, [rdx+10h]
0x1800bd517  mov     [rsp+8E0h+var_864], ecx
0x1800bd51b  mov     ecx, [rdx+4]
0x1800bd51e  mov     [rsp+8E0h+var_880], ecx
0x1800bd522  mov     eax, [rdx+8]
0x1800bd525  mov     [rsp+8E0h+var_880+4], eax
0x1800bd529  mov     eax, [rdx]
0x1800bd52b  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800bd52f  lea     rax, [rbp+7E0h+arg_0]
0x1800bd536  mov     [rsp+8E0h+var_890], rax
0x1800bd53b  lea     rax, [rsp+8E0h+var_868]
0x1800bd540  mov     [rsp+8E0h+var_898], rax
0x1800bd545  lea     rax, [rbp+7E0h+var_860]
0x1800bd549  mov     [rsp+8E0h+var_8A0], rax
0x1800bd54e  lea     rax, [rsp+8E0h+var_864]
0x1800bd553  mov     [rsp+8E0h+var_8A8], rax
0x1800bd558  lea     rax, [rsp+8E0h+var_880]
0x1800bd55d  mov     [rsp+8E0h+var_8B0], rax
0x1800bd562  lea     rax, [rsp+8E0h+var_880+4]
0x1800bd567  mov     [rsp+8E0h+var_8B8], rax
0x1800bd56c  lea     rax, [rsp+8E0h+var_870]
0x1800bd571  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bd576  lea     rdx, unk_180167A84
0x1800bd57d  mov     rcx, r8
0x1800bd580  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bd585  jmp     short loc_1800BD5F8
0x1800bd587  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bd58c  mov     ecx, [rax]
0x1800bd58e  cmp     ecx, 4
0x1800bd591  jbe     short loc_1800BD5F8
0x1800bd593  mov     [rbp+7E0h+arg_0], ebx
0x1800bd599  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bd59f  mov     [rbp+7E0h+var_860], rdi
0x1800bd5a3  mov     rcx, [rsp+8E0h+var_878]
0x1800bd5a8  mov     edx, [rcx+8]
0x1800bd5ab  mov     [rsp+8E0h+var_880+4], edx
0x1800bd5af  mov     ecx, [rdi+30h]
0x1800bd5b2  mov     [rsp+8E0h+var_880], ecx
0x1800bd5b6  lea     rcx, [rbp+7E0h+arg_0]
0x1800bd5bd  mov     [rsp+8E0h+var_8A0], rcx
0x1800bd5c2  lea     rcx, [rsp+8E0h+var_870]
0x1800bd5c7  mov     [rsp+8E0h+var_8A8], rcx
0x1800bd5cc  lea     rcx, [rbp+7E0h+var_860]
0x1800bd5d0  mov     [rsp+8E0h+var_8B0], rcx
0x1800bd5d5  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bd5da  mov     [rsp+8E0h+var_8B8], rcx
0x1800bd5df  lea     rcx, [rsp+8E0h+var_880]
0x1800bd5e4  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bd5e9  lea     rdx, unk_180167AFD
0x1800bd5f0  mov     rcx, rax
0x1800bd5f3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bd5f8  mov     rcx, [rbp+7E8h]; this
0x1800bd5ff  test    ebx, ebx
0x1800bd601  jns     short loc_1800BD626
0x1800bd603  mov     r9d, ebx; char *
0x1800bd606  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bd60d  mov     edx, 81h; void *
0x1800bd612  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bd617  mov     rax, [rdi]
0x1800bd61a  mov     rcx, rdi
0x1800bd61d  mov     rax, [rax+20h]
0x1800bd621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd626  mov     ebx, [rdi+40h]
0x1800bd629  test    ebx, ebx
0x1800bd62b  jns     short loc_1800BD634
0x1800bd62d  mov     edx, 8Ah
0x1800bd632  jmp     short loc_1800BD645
0x1800bd634  mov     rcx, [rsp+8E0h+var_878]
0x1800bd639  mov     ebx, [rcx+4]
0x1800bd63c  test    ebx, ebx
0x1800bd63e  jns     short loc_1800BD65D
0x1800bd640  mov     edx, 8Ch; void *
0x1800bd645  mov     r9d, ebx; char *
0x1800bd648  mov     rcx, [rbp+7E8h]; this
0x1800bd64f  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bd656  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd65b  jmp     short loc_1800BD67B
0x1800bd65d  mov     rdx, [rbp+7E0h+arg_20]
0x1800bd664  call    ??$CastTo@UXvmGetSessionIdentifier@@@XvmMessage@@QEAAJPEAPEAUXvmGetSessionIdentifier@@@Z; XvmMessage::CastTo<XvmGetSessionIdentifier>(XvmGetSessionIdentifier * *)
0x1800bd669  mov     ebx, eax
0x1800bd66b  test    eax, eax
0x1800bd66d  jns     short loc_1800BD679
0x1800bd66f  mov     r9d, eax
0x1800bd672  mov     edx, 8Dh
0x1800bd677  jmp     short loc_1800BD648
0x1800bd679  xor     ebx, ebx
0x1800bd67b  mov     rcx, [rbp+7E0h+arg_18]
0x1800bd682  mov     rax, [rsp+8E0h+var_878]
0x1800bd687  mov     [rcx], rax
0x1800bd68a  mov     eax, ebx
0x1800bd68c  lea     r11, [rsp+8E0h+var_10]
0x1800bd694  mov     rbx, [r11+28h]
0x1800bd698  mov     rsi, [r11+30h]
0x1800bd69c  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bd6a1  mov     rsp, r11
0x1800bd6a4  pop     r14
0x1800bd6a6  pop     rdi
0x1800bd6a7  pop     rbp
0x1800bd6a8  retn
```
