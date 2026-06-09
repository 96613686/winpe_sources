# CGuestXvmAudioObject::SendAndValidateResponse<XvmMfGetAction>(uint,XvmMfGetAction,XvmMessage * *,XvmMfGetAction * *)

- ea: `0x1800c2b84`
- end: `0x1800c2ecb`
- name: `??$SendAndValidateResponse@UXvmMfGetAction@@@CGuestXvmAudioObject@@QEAAJIUXvmMfGetAction@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `839`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c391c`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800c293c`
- `0x1800c2b84`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c2bc6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c2cb2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c2bc6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800c2cb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c2bfa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c2bfa`

## string_xrefs

- `0x1800c2bdd`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800c2c1c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800c2e28`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800c2e71`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmMfGetAction>(__int64 a1, unsigned int a2, __int64 a3, ...)
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
    v34[0] = a3;
    v32 = 63;
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
            (unsigned int)&unk_180168B88,
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
          (unsigned int)&unk_180168C01,
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
        v18 = XvmMessage::CastTo<XvmMfGetAction>(v21, v39, v12);
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
0x1800c2b84  mov     rax, rsp
0x1800c2b87  mov     [rax+10h], rbx
0x1800c2b8b  mov     [rax+18h], rsi
0x1800c2b8f  mov     [rax+20h], r9
0x1800c2b93  push    rbp
0x1800c2b94  push    rdi
0x1800c2b95  push    r14
0x1800c2b97  lea     rbp, [rax-7E8h]
0x1800c2b9e  sub     rsp, 8D0h
0x1800c2ba5  movaps  xmmword ptr [rax-28h], xmm6
0x1800c2ba9  mov     rbx, r8
0x1800c2bac  mov     r14d, edx
0x1800c2baf  mov     rdi, rcx
0x1800c2bb2  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800c2bba  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800c2bc2  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800c2bc6  call    cs:__imp_QueryPerformanceCounter
0x1800c2bcc  mov     esi, [rdi+40h]
0x1800c2bcf  test    esi, esi
0x1800c2bd1  jns     short loc_1800C2BF5
0x1800c2bd3  mov     rcx, [rbp+7E8h]; this
0x1800c2bda  mov     r9d, esi; char *
0x1800c2bdd  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c2be4  mov     edx, 4Fh ; 'O'; void *
0x1800c2be9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c2bee  mov     eax, esi
0x1800c2bf0  jmp     loc_1800C2EAE
0x1800c2bf5  mov     ecx, 810h; cb
0x1800c2bfa  call    cs:__imp_CoTaskMemAlloc
0x1800c2c00  mov     rsi, rax
0x1800c2c03  mov     [rsp+8E0h+var_878], rax
0x1800c2c08  test    rax, rax
0x1800c2c0b  jnz     short loc_1800C2C30
0x1800c2c0d  mov     rcx, [rbp+7E8h]; this
0x1800c2c14  mov     ebx, 8007000Eh
0x1800c2c19  mov     r9d, ebx; char *
0x1800c2c1c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c2c23  lea     edx, [rax+52h]; void *
0x1800c2c26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c2c2b  jmp     loc_1800C2EAC
0x1800c2c30  mov     [rbp+7E0h+Src], 0
0x1800c2c38  mov     [rbp+7E0h+var_824], 0
0x1800c2c3f  xor     edx, edx; Val
0x1800c2c41  mov     r8d, 800h; Size
0x1800c2c47  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800c2c4b  call    memset_0
0x1800c2c50  mov     [rbp+7E0h+var_820], rbx
0x1800c2c54  mov     [rbp+7E0h+var_828], 3Fh ; '?'
0x1800c2c5b  mov     rcx, rsi; void *
0x1800c2c5e  lea     rdx, [rbp+7E0h+Src]; Src
0x1800c2c62  mov     r8d, 810h; Size
0x1800c2c68  call    memcpy_0
0x1800c2c6d  mov     rax, [rsp+8E0h+var_878]
0x1800c2c72  mov     [rax+0Ch], r14d
0x1800c2c76  lea     rax, [rbp+7E0h+arg_18]
0x1800c2c7d  mov     [rbp+7E0h+var_848], rax
0x1800c2c81  lea     rax, [rsp+8E0h+var_878]
0x1800c2c86  mov     [rbp+7E0h+var_840], rax
0x1800c2c8a  mov     [rbp+7E0h+var_838], 1
0x1800c2c8e  mov     rcx, [rdi+28h]
0x1800c2c92  mov     rax, [rcx]
0x1800c2c95  mov     r9d, 810h
0x1800c2c9b  mov     r8, [rsp+8E0h+var_878]
0x1800c2ca0  mov     edx, r14d
0x1800c2ca3  mov     rax, [rax+20h]
0x1800c2ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2cac  mov     ebx, eax
0x1800c2cae  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800c2cb2  call    cs:__imp_QueryPerformanceCounter
0x1800c2cb8  xorps   xmm6, xmm6
0x1800c2cbb  cmp     qword ptr [rdi+48h], 0
0x1800c2cc0  jz      short loc_1800C2CE4
0x1800c2cc2  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800c2cc6  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800c2cca  cvtsi2ss xmm6, rcx
0x1800c2ccf  mulss   xmm6, cs:__real@447a0000
0x1800c2cd7  xorps   xmm0, xmm0
0x1800c2cda  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800c2ce0  divss   xmm6, xmm0
0x1800c2ce4  mov     rcx, [rsp+8E0h+var_878]
0x1800c2ce9  cmp     dword ptr [rcx+8], 1
0x1800c2ced  jnz     loc_1800C2DA9
0x1800c2cf3  mov     [rsp+8E0h+var_870], 0
0x1800c2cfc  lea     rdx, [rsp+8E0h+var_870]
0x1800c2d01  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800c2d06  test    eax, eax
0x1800c2d08  js      loc_1800C2E1A
0x1800c2d0e  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800c2d13  mov     r8, rax
0x1800c2d16  mov     ecx, [rax]
0x1800c2d18  cmp     ecx, 4
0x1800c2d1b  jbe     loc_1800C2E1A
0x1800c2d21  mov     [rbp+7E0h+arg_0], ebx
0x1800c2d27  movss   [rsp+8E0h+var_868], xmm6
0x1800c2d2d  mov     [rbp+7E0h+var_860], rdi
0x1800c2d31  mov     rdx, [rsp+8E0h+var_870]
0x1800c2d36  mov     ecx, [rdx+10h]
0x1800c2d39  mov     [rsp+8E0h+var_864], ecx
0x1800c2d3d  mov     ecx, [rdx+4]
0x1800c2d40  mov     [rsp+8E0h+var_880], ecx
0x1800c2d44  mov     eax, [rdx+8]
0x1800c2d47  mov     [rsp+8E0h+var_880+4], eax
0x1800c2d4b  mov     eax, [rdx]
0x1800c2d4d  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800c2d51  lea     rax, [rbp+7E0h+arg_0]
0x1800c2d58  mov     [rsp+8E0h+var_890], rax
0x1800c2d5d  lea     rax, [rsp+8E0h+var_868]
0x1800c2d62  mov     [rsp+8E0h+var_898], rax
0x1800c2d67  lea     rax, [rbp+7E0h+var_860]
0x1800c2d6b  mov     [rsp+8E0h+var_8A0], rax
0x1800c2d70  lea     rax, [rsp+8E0h+var_864]
0x1800c2d75  mov     [rsp+8E0h+var_8A8], rax
0x1800c2d7a  lea     rax, [rsp+8E0h+var_880]
0x1800c2d7f  mov     [rsp+8E0h+var_8B0], rax
0x1800c2d84  lea     rax, [rsp+8E0h+var_880+4]
0x1800c2d89  mov     [rsp+8E0h+var_8B8], rax
0x1800c2d8e  lea     rax, [rsp+8E0h+var_870]
0x1800c2d93  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800c2d98  lea     rdx, unk_180168B88
0x1800c2d9f  mov     rcx, r8
0x1800c2da2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c2da7  jmp     short loc_1800C2E1A
0x1800c2da9  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800c2dae  mov     ecx, [rax]
0x1800c2db0  cmp     ecx, 4
0x1800c2db3  jbe     short loc_1800C2E1A
0x1800c2db5  mov     [rbp+7E0h+arg_0], ebx
0x1800c2dbb  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800c2dc1  mov     [rbp+7E0h+var_860], rdi
0x1800c2dc5  mov     rcx, [rsp+8E0h+var_878]
0x1800c2dca  mov     edx, [rcx+8]
0x1800c2dcd  mov     [rsp+8E0h+var_880+4], edx
0x1800c2dd1  mov     ecx, [rdi+30h]
0x1800c2dd4  mov     [rsp+8E0h+var_880], ecx
0x1800c2dd8  lea     rcx, [rbp+7E0h+arg_0]
0x1800c2ddf  mov     [rsp+8E0h+var_8A0], rcx
0x1800c2de4  lea     rcx, [rsp+8E0h+var_870]
0x1800c2de9  mov     [rsp+8E0h+var_8A8], rcx
0x1800c2dee  lea     rcx, [rbp+7E0h+var_860]
0x1800c2df2  mov     [rsp+8E0h+var_8B0], rcx
0x1800c2df7  lea     rcx, [rsp+8E0h+var_880+4]
0x1800c2dfc  mov     [rsp+8E0h+var_8B8], rcx
0x1800c2e01  lea     rcx, [rsp+8E0h+var_880]
0x1800c2e06  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800c2e0b  lea     rdx, unk_180168C01
0x1800c2e12  mov     rcx, rax
0x1800c2e15  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c2e1a  mov     rcx, [rbp+7E8h]; this
0x1800c2e21  test    ebx, ebx
0x1800c2e23  jns     short loc_1800C2E48
0x1800c2e25  mov     r9d, ebx; char *
0x1800c2e28  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c2e2f  mov     edx, 81h; void *
0x1800c2e34  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c2e39  mov     rax, [rdi]
0x1800c2e3c  mov     rcx, rdi
0x1800c2e3f  mov     rax, [rax+20h]
0x1800c2e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2e48  mov     ebx, [rdi+40h]
0x1800c2e4b  test    ebx, ebx
0x1800c2e4d  jns     short loc_1800C2E56
0x1800c2e4f  mov     edx, 8Ah
0x1800c2e54  jmp     short loc_1800C2E67
0x1800c2e56  mov     rcx, [rsp+8E0h+var_878]
0x1800c2e5b  mov     ebx, [rcx+4]
0x1800c2e5e  test    ebx, ebx
0x1800c2e60  jns     short loc_1800C2E7F
0x1800c2e62  mov     edx, 8Ch; void *
0x1800c2e67  mov     r9d, ebx; char *
0x1800c2e6a  mov     rcx, [rbp+7E8h]; this
0x1800c2e71  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800c2e78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c2e7d  jmp     short loc_1800C2E9D
0x1800c2e7f  mov     rdx, [rbp+7E0h+arg_20]
0x1800c2e86  call    ??$CastTo@UXvmMfGetAction@@@XvmMessage@@QEAAJPEAPEAUXvmMfGetAction@@@Z; XvmMessage::CastTo<XvmMfGetAction>(XvmMfGetAction * *)
0x1800c2e8b  mov     ebx, eax
0x1800c2e8d  test    eax, eax
0x1800c2e8f  jns     short loc_1800C2E9B
0x1800c2e91  mov     r9d, eax
0x1800c2e94  mov     edx, 8Dh
0x1800c2e99  jmp     short loc_1800C2E6A
0x1800c2e9b  xor     ebx, ebx
0x1800c2e9d  mov     rcx, [rbp+7E0h+arg_18]
0x1800c2ea4  mov     rax, [rsp+8E0h+var_878]
0x1800c2ea9  mov     [rcx], rax
0x1800c2eac  mov     eax, ebx
0x1800c2eae  lea     r11, [rsp+8E0h+var_10]
0x1800c2eb6  mov     rbx, [r11+28h]
0x1800c2eba  mov     rsi, [r11+30h]
0x1800c2ebe  movaps  xmm6, xmmword ptr [r11-10h]
0x1800c2ec3  mov     rsp, r11
0x1800c2ec6  pop     r14
0x1800c2ec8  pop     rdi
0x1800c2ec9  pop     rbp
0x1800c2eca  retn
```
