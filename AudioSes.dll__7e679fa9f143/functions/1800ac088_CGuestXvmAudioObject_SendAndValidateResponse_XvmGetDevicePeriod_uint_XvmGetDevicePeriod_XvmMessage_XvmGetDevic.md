# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetDevicePeriod>(uint,XvmGetDevicePeriod,XvmMessage * *,XvmGetDevicePeriod * *)

- ea: `0x1800ac088`
- end: `0x1800ac3e4`
- name: `??$SendAndValidateResponse@UXvmGetDevicePeriod@@@CGuestXvmAudioObject@@QEAAJIUXvmGetDevicePeriod@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `860`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800af7a0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2968`
- `0x1800ac088`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ac0ca`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ac1cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ac0ca`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ac1cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ac0fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ac0fe`

## string_xrefs

- `0x1800ac0e1`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ac120`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ac341`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ac38a`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetDevicePeriod>(__int64 a1, unsigned int a2, __int64 a3, ...)
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
  int Device; // eax
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
  _QWORD v34[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int16 v35; // [rsp+D8h] [rbp-30h]
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
    v34[0] = *(_QWORD *)a3;
    v34[1] = *(_QWORD *)(a3 + 8);
    v35 = *(_WORD *)(a3 + 16);
    v32 = 3;
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
            (unsigned int)&unk_180166543,
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
          (unsigned int)&unk_180166430,
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
        Device = XvmMessage::CastTo<XvmGetDevicePeriod>(v21, v40, v12);
        v9 = Device;
        if ( Device >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)Device;
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
0x1800ac088  mov     rax, rsp
0x1800ac08b  mov     [rax+10h], rbx
0x1800ac08f  mov     [rax+18h], rsi
0x1800ac093  mov     [rax+20h], r9
0x1800ac097  push    rbp
0x1800ac098  push    rdi
0x1800ac099  push    r14
0x1800ac09b  lea     rbp, [rax-7E8h]
0x1800ac0a2  sub     rsp, 8D0h
0x1800ac0a9  movaps  xmmword ptr [rax-28h], xmm6
0x1800ac0ad  mov     rsi, r8
0x1800ac0b0  mov     r14d, edx
0x1800ac0b3  mov     rbx, rcx
0x1800ac0b6  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800ac0be  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800ac0c6  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800ac0ca  call    cs:__imp_QueryPerformanceCounter
0x1800ac0d0  mov     edi, [rbx+40h]
0x1800ac0d3  test    edi, edi
0x1800ac0d5  jns     short loc_1800AC0F9
0x1800ac0d7  mov     rcx, [rbp+7E8h]; this
0x1800ac0de  mov     r9d, edi; char *
0x1800ac0e1  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ac0e8  mov     edx, 4Fh ; 'O'; void *
0x1800ac0ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac0f2  mov     eax, edi
0x1800ac0f4  jmp     loc_1800AC3C7
0x1800ac0f9  mov     ecx, 810h; cb
0x1800ac0fe  call    cs:__imp_CoTaskMemAlloc
0x1800ac104  mov     rdi, rax
0x1800ac107  mov     [rsp+8E0h+var_878], rax
0x1800ac10c  test    rax, rax
0x1800ac10f  jnz     short loc_1800AC134
0x1800ac111  mov     rcx, [rbp+7E8h]; this
0x1800ac118  mov     ebx, 8007000Eh
0x1800ac11d  mov     r9d, ebx; char *
0x1800ac120  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ac127  lea     edx, [rax+52h]; void *
0x1800ac12a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac12f  jmp     loc_1800AC3C5
0x1800ac134  mov     [rbp+7E0h+Src], 0
0x1800ac13c  mov     [rbp+7E0h+var_824], 0
0x1800ac143  xor     edx, edx; Val
0x1800ac145  mov     r8d, 800h; Size
0x1800ac14b  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800ac14f  call    memset_0
0x1800ac154  mov     rax, [rsi]
0x1800ac157  mov     [rbp+7E0h+var_820], rax
0x1800ac15b  movsd   xmm0, qword ptr [rsi+8]
0x1800ac160  movsd   [rbp+7E0h+var_818], xmm0
0x1800ac165  movzx   eax, word ptr [rsi+10h]
0x1800ac169  mov     [rbp+7E0h+var_810], ax
0x1800ac16d  mov     [rbp+7E0h+var_828], 3
0x1800ac174  mov     rcx, rdi; void *
0x1800ac177  lea     rdx, [rbp+7E0h+Src]; Src
0x1800ac17b  mov     r8d, 810h; Size
0x1800ac181  call    memcpy_0
0x1800ac186  mov     rax, [rsp+8E0h+var_878]
0x1800ac18b  mov     [rax+0Ch], r14d
0x1800ac18f  lea     rax, [rbp+7E0h+arg_18]
0x1800ac196  mov     [rbp+7E0h+var_848], rax
0x1800ac19a  lea     rax, [rsp+8E0h+var_878]
0x1800ac19f  mov     [rbp+7E0h+var_840], rax
0x1800ac1a3  mov     [rbp+7E0h+var_838], 1
0x1800ac1a7  mov     rcx, [rbx+28h]
0x1800ac1ab  mov     rax, [rcx]
0x1800ac1ae  mov     r9d, 810h
0x1800ac1b4  mov     r8, [rsp+8E0h+var_878]
0x1800ac1b9  mov     edx, r14d
0x1800ac1bc  mov     rax, [rax+20h]
0x1800ac1c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac1c5  mov     edi, eax
0x1800ac1c7  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800ac1cb  call    cs:__imp_QueryPerformanceCounter
0x1800ac1d1  xorps   xmm6, xmm6
0x1800ac1d4  cmp     qword ptr [rbx+48h], 0
0x1800ac1d9  jz      short loc_1800AC1FD
0x1800ac1db  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800ac1df  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800ac1e3  cvtsi2ss xmm6, rcx
0x1800ac1e8  mulss   xmm6, cs:__real@447a0000
0x1800ac1f0  xorps   xmm0, xmm0
0x1800ac1f3  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800ac1f9  divss   xmm6, xmm0
0x1800ac1fd  mov     rcx, [rsp+8E0h+var_878]
0x1800ac202  cmp     dword ptr [rcx+8], 1
0x1800ac206  jnz     loc_1800AC2C2
0x1800ac20c  mov     [rsp+8E0h+var_870], 0
0x1800ac215  lea     rdx, [rsp+8E0h+var_870]
0x1800ac21a  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800ac21f  test    eax, eax
0x1800ac221  js      loc_1800AC333
0x1800ac227  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ac22c  mov     r8, rax
0x1800ac22f  mov     ecx, [rax]
0x1800ac231  cmp     ecx, 4
0x1800ac234  jbe     loc_1800AC333
0x1800ac23a  mov     [rbp+7E0h+arg_0], edi
0x1800ac240  movss   [rsp+8E0h+var_868], xmm6
0x1800ac246  mov     [rbp+7E0h+var_860], rbx
0x1800ac24a  mov     rdx, [rsp+8E0h+var_870]
0x1800ac24f  mov     ecx, [rdx+10h]
0x1800ac252  mov     [rsp+8E0h+var_864], ecx
0x1800ac256  mov     ecx, [rdx+4]
0x1800ac259  mov     [rsp+8E0h+var_880], ecx
0x1800ac25d  mov     eax, [rdx+8]
0x1800ac260  mov     [rsp+8E0h+var_880+4], eax
0x1800ac264  mov     eax, [rdx]
0x1800ac266  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800ac26a  lea     rax, [rbp+7E0h+arg_0]
0x1800ac271  mov     [rsp+8E0h+var_890], rax
0x1800ac276  lea     rax, [rsp+8E0h+var_868]
0x1800ac27b  mov     [rsp+8E0h+var_898], rax
0x1800ac280  lea     rax, [rbp+7E0h+var_860]
0x1800ac284  mov     [rsp+8E0h+var_8A0], rax
0x1800ac289  lea     rax, [rsp+8E0h+var_864]
0x1800ac28e  mov     [rsp+8E0h+var_8A8], rax
0x1800ac293  lea     rax, [rsp+8E0h+var_880]
0x1800ac298  mov     [rsp+8E0h+var_8B0], rax
0x1800ac29d  lea     rax, [rsp+8E0h+var_880+4]
0x1800ac2a2  mov     [rsp+8E0h+var_8B8], rax
0x1800ac2a7  lea     rax, [rsp+8E0h+var_870]
0x1800ac2ac  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800ac2b1  lea     rdx, unk_180166543
0x1800ac2b8  mov     rcx, r8
0x1800ac2bb  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ac2c0  jmp     short loc_1800AC333
0x1800ac2c2  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ac2c7  mov     ecx, [rax]
0x1800ac2c9  cmp     ecx, 4
0x1800ac2cc  jbe     short loc_1800AC333
0x1800ac2ce  mov     [rbp+7E0h+arg_0], edi
0x1800ac2d4  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800ac2da  mov     [rbp+7E0h+var_860], rbx
0x1800ac2de  mov     rcx, [rsp+8E0h+var_878]
0x1800ac2e3  mov     edx, [rcx+8]
0x1800ac2e6  mov     [rsp+8E0h+var_880+4], edx
0x1800ac2ea  mov     ecx, [rbx+30h]
0x1800ac2ed  mov     [rsp+8E0h+var_880], ecx
0x1800ac2f1  lea     rcx, [rbp+7E0h+arg_0]
0x1800ac2f8  mov     [rsp+8E0h+var_8A0], rcx
0x1800ac2fd  lea     rcx, [rsp+8E0h+var_870]
0x1800ac302  mov     [rsp+8E0h+var_8A8], rcx
0x1800ac307  lea     rcx, [rbp+7E0h+var_860]
0x1800ac30b  mov     [rsp+8E0h+var_8B0], rcx
0x1800ac310  lea     rcx, [rsp+8E0h+var_880+4]
0x1800ac315  mov     [rsp+8E0h+var_8B8], rcx
0x1800ac31a  lea     rcx, [rsp+8E0h+var_880]
0x1800ac31f  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800ac324  lea     rdx, unk_180166430
0x1800ac32b  mov     rcx, rax
0x1800ac32e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ac333  mov     rcx, [rbp+7E8h]; this
0x1800ac33a  test    edi, edi
0x1800ac33c  jns     short loc_1800AC361
0x1800ac33e  mov     r9d, edi; char *
0x1800ac341  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ac348  mov     edx, 81h; void *
0x1800ac34d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ac352  mov     rax, [rbx]
0x1800ac355  mov     rcx, rbx
0x1800ac358  mov     rax, [rax+20h]
0x1800ac35c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac361  mov     ebx, [rbx+40h]
0x1800ac364  test    ebx, ebx
0x1800ac366  jns     short loc_1800AC36F
0x1800ac368  mov     edx, 8Ah
0x1800ac36d  jmp     short loc_1800AC380
0x1800ac36f  mov     rcx, [rsp+8E0h+var_878]
0x1800ac374  mov     ebx, [rcx+4]
0x1800ac377  test    ebx, ebx
0x1800ac379  jns     short loc_1800AC398
0x1800ac37b  mov     edx, 8Ch; void *
0x1800ac380  mov     r9d, ebx; char *
0x1800ac383  mov     rcx, [rbp+7E8h]; this
0x1800ac38a  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ac391  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac396  jmp     short loc_1800AC3B6
0x1800ac398  mov     rdx, [rbp+7E0h+arg_20]
0x1800ac39f  call    ??$CastTo@UXvmGetDevicePeriod@@@XvmMessage@@QEAAJPEAPEAUXvmGetDevicePeriod@@@Z; XvmMessage::CastTo<XvmGetDevicePeriod>(XvmGetDevicePeriod * *)
0x1800ac3a4  mov     ebx, eax
0x1800ac3a6  test    eax, eax
0x1800ac3a8  jns     short loc_1800AC3B4
0x1800ac3aa  mov     r9d, eax
0x1800ac3ad  mov     edx, 8Dh
0x1800ac3b2  jmp     short loc_1800AC383
0x1800ac3b4  xor     ebx, ebx
0x1800ac3b6  mov     rcx, [rbp+7E0h+arg_18]
0x1800ac3bd  mov     rax, [rsp+8E0h+var_878]
0x1800ac3c2  mov     [rcx], rax
0x1800ac3c5  mov     eax, ebx
0x1800ac3c7  lea     r11, [rsp+8E0h+var_10]
0x1800ac3cf  mov     rbx, [r11+28h]
0x1800ac3d3  mov     rsi, [r11+30h]
0x1800ac3d7  movaps  xmm6, xmmword ptr [r11-10h]
0x1800ac3dc  mov     rsp, r11
0x1800ac3df  pop     r14
0x1800ac3e1  pop     rdi
0x1800ac3e2  pop     rbp
0x1800ac3e3  retn
```
