# CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeRegisterControlChanged>(uint,XvmAudioEndpointVolumeRegisterControlChanged,XvmMessage * *,XvmAudioEndpointVolumeRegisterControlChanged * *)

- ea: `0x1800b4c90`
- end: `0x1800b4fd6`
- name: `??$SendAndValidateResponse@UXvmAudioEndpointVolumeRegisterControlChanged@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeRegisterControlChanged@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800817a0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a5ed0`
- `0x1800b4c90`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b4cd2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b4dbd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b4cd2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b4dbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4d06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b4d06`

## string_xrefs

- `0x1800b4ce9`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b4d28`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b4f33`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b4f7c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeRegisterControlChanged>(
        __int64 a1,
        unsigned int a2,
        char a3,
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
  _BYTE v34[2064]; // [rsp+C8h] [rbp-40h] BYREF
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
    v32 = 79;
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
            (unsigned int)byte_18016762D,
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
          (unsigned int)&byte_180167567,
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
        v18 = XvmMessage::CastTo<XvmAudioEndpointVolumeRegisterControlChanged>(v21, v39, v12);
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
0x1800b4c90  mov     rax, rsp
0x1800b4c93  mov     [rax+10h], rbx
0x1800b4c97  mov     [rax+18h], rsi
0x1800b4c9b  mov     [rax+20h], r9
0x1800b4c9f  push    rbp
0x1800b4ca0  push    rdi
0x1800b4ca1  push    r14
0x1800b4ca3  lea     rbp, [rax-7E8h]
0x1800b4caa  sub     rsp, 8D0h
0x1800b4cb1  movaps  xmmword ptr [rax-28h], xmm6
0x1800b4cb5  mov     bl, r8b
0x1800b4cb8  mov     r14d, edx
0x1800b4cbb  mov     rdi, rcx
0x1800b4cbe  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800b4cc6  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800b4cce  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800b4cd2  call    cs:__imp_QueryPerformanceCounter
0x1800b4cd8  mov     esi, [rdi+40h]
0x1800b4cdb  test    esi, esi
0x1800b4cdd  jns     short loc_1800B4D01
0x1800b4cdf  mov     rcx, [rbp+7E8h]; this
0x1800b4ce6  mov     r9d, esi; char *
0x1800b4ce9  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b4cf0  mov     edx, 4Fh ; 'O'; void *
0x1800b4cf5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4cfa  mov     eax, esi
0x1800b4cfc  jmp     loc_1800B4FB9
0x1800b4d01  mov     ecx, 810h; cb
0x1800b4d06  call    cs:__imp_CoTaskMemAlloc
0x1800b4d0c  mov     rsi, rax
0x1800b4d0f  mov     [rsp+8E0h+var_878], rax
0x1800b4d14  test    rax, rax
0x1800b4d17  jnz     short loc_1800B4D3C
0x1800b4d19  mov     rcx, [rbp+7E8h]; this
0x1800b4d20  mov     ebx, 8007000Eh
0x1800b4d25  mov     r9d, ebx; char *
0x1800b4d28  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b4d2f  lea     edx, [rax+52h]; void *
0x1800b4d32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4d37  jmp     loc_1800B4FB7
0x1800b4d3c  mov     [rbp+7E0h+Src], 0
0x1800b4d44  mov     [rbp+7E0h+var_824], 0
0x1800b4d4b  xor     edx, edx; Val
0x1800b4d4d  mov     r8d, 800h; Size
0x1800b4d53  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800b4d57  call    memset_0
0x1800b4d5c  mov     [rbp+7E0h+var_820], bl
0x1800b4d5f  mov     [rbp+7E0h+var_828], 4Fh ; 'O'
0x1800b4d66  mov     rcx, rsi; void *
0x1800b4d69  lea     rdx, [rbp+7E0h+Src]; Src
0x1800b4d6d  mov     r8d, 810h; Size
0x1800b4d73  call    memcpy_0
0x1800b4d78  mov     rax, [rsp+8E0h+var_878]
0x1800b4d7d  mov     [rax+0Ch], r14d
0x1800b4d81  lea     rax, [rbp+7E0h+arg_18]
0x1800b4d88  mov     [rbp+7E0h+var_848], rax
0x1800b4d8c  lea     rax, [rsp+8E0h+var_878]
0x1800b4d91  mov     [rbp+7E0h+var_840], rax
0x1800b4d95  mov     [rbp+7E0h+var_838], 1
0x1800b4d99  mov     rcx, [rdi+28h]
0x1800b4d9d  mov     rax, [rcx]
0x1800b4da0  mov     r9d, 810h
0x1800b4da6  mov     r8, [rsp+8E0h+var_878]
0x1800b4dab  mov     edx, r14d
0x1800b4dae  mov     rax, [rax+20h]
0x1800b4db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4db7  mov     ebx, eax
0x1800b4db9  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800b4dbd  call    cs:__imp_QueryPerformanceCounter
0x1800b4dc3  xorps   xmm6, xmm6
0x1800b4dc6  cmp     qword ptr [rdi+48h], 0
0x1800b4dcb  jz      short loc_1800B4DEF
0x1800b4dcd  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800b4dd1  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800b4dd5  cvtsi2ss xmm6, rcx
0x1800b4dda  mulss   xmm6, cs:__real@447a0000
0x1800b4de2  xorps   xmm0, xmm0
0x1800b4de5  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800b4deb  divss   xmm6, xmm0
0x1800b4def  mov     rcx, [rsp+8E0h+var_878]
0x1800b4df4  cmp     dword ptr [rcx+8], 1
0x1800b4df8  jnz     loc_1800B4EB4
0x1800b4dfe  mov     [rsp+8E0h+var_870], 0
0x1800b4e07  lea     rdx, [rsp+8E0h+var_870]
0x1800b4e0c  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b4e11  test    eax, eax
0x1800b4e13  js      loc_1800B4F25
0x1800b4e19  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b4e1e  mov     r8, rax
0x1800b4e21  mov     ecx, [rax]
0x1800b4e23  cmp     ecx, 4
0x1800b4e26  jbe     loc_1800B4F25
0x1800b4e2c  mov     [rbp+7E0h+arg_0], ebx
0x1800b4e32  movss   [rsp+8E0h+var_868], xmm6
0x1800b4e38  mov     [rbp+7E0h+var_860], rdi
0x1800b4e3c  mov     rdx, [rsp+8E0h+var_870]
0x1800b4e41  mov     ecx, [rdx+10h]
0x1800b4e44  mov     [rsp+8E0h+var_864], ecx
0x1800b4e48  mov     ecx, [rdx+4]
0x1800b4e4b  mov     [rsp+8E0h+var_880], ecx
0x1800b4e4f  mov     eax, [rdx+8]
0x1800b4e52  mov     [rsp+8E0h+var_880+4], eax
0x1800b4e56  mov     eax, [rdx]
0x1800b4e58  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800b4e5c  lea     rax, [rbp+7E0h+arg_0]
0x1800b4e63  mov     [rsp+8E0h+var_890], rax
0x1800b4e68  lea     rax, [rsp+8E0h+var_868]
0x1800b4e6d  mov     [rsp+8E0h+var_898], rax
0x1800b4e72  lea     rax, [rbp+7E0h+var_860]
0x1800b4e76  mov     [rsp+8E0h+var_8A0], rax
0x1800b4e7b  lea     rax, [rsp+8E0h+var_864]
0x1800b4e80  mov     [rsp+8E0h+var_8A8], rax
0x1800b4e85  lea     rax, [rsp+8E0h+var_880]
0x1800b4e8a  mov     [rsp+8E0h+var_8B0], rax
0x1800b4e8f  lea     rax, [rsp+8E0h+var_880+4]
0x1800b4e94  mov     [rsp+8E0h+var_8B8], rax
0x1800b4e99  lea     rax, [rsp+8E0h+var_870]
0x1800b4e9e  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800b4ea3  lea     rdx, byte_18016762D
0x1800b4eaa  mov     rcx, r8
0x1800b4ead  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b4eb2  jmp     short loc_1800B4F25
0x1800b4eb4  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b4eb9  mov     ecx, [rax]
0x1800b4ebb  cmp     ecx, 4
0x1800b4ebe  jbe     short loc_1800B4F25
0x1800b4ec0  mov     [rbp+7E0h+arg_0], ebx
0x1800b4ec6  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800b4ecc  mov     [rbp+7E0h+var_860], rdi
0x1800b4ed0  mov     rcx, [rsp+8E0h+var_878]
0x1800b4ed5  mov     edx, [rcx+8]
0x1800b4ed8  mov     [rsp+8E0h+var_880+4], edx
0x1800b4edc  mov     ecx, [rdi+30h]
0x1800b4edf  mov     [rsp+8E0h+var_880], ecx
0x1800b4ee3  lea     rcx, [rbp+7E0h+arg_0]
0x1800b4eea  mov     [rsp+8E0h+var_8A0], rcx
0x1800b4eef  lea     rcx, [rsp+8E0h+var_870]
0x1800b4ef4  mov     [rsp+8E0h+var_8A8], rcx
0x1800b4ef9  lea     rcx, [rbp+7E0h+var_860]
0x1800b4efd  mov     [rsp+8E0h+var_8B0], rcx
0x1800b4f02  lea     rcx, [rsp+8E0h+var_880+4]
0x1800b4f07  mov     [rsp+8E0h+var_8B8], rcx
0x1800b4f0c  lea     rcx, [rsp+8E0h+var_880]
0x1800b4f11  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800b4f16  lea     rdx, byte_180167567
0x1800b4f1d  mov     rcx, rax
0x1800b4f20  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b4f25  mov     rcx, [rbp+7E8h]; this
0x1800b4f2c  test    ebx, ebx
0x1800b4f2e  jns     short loc_1800B4F53
0x1800b4f30  mov     r9d, ebx; char *
0x1800b4f33  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b4f3a  mov     edx, 81h; void *
0x1800b4f3f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b4f44  mov     rax, [rdi]
0x1800b4f47  mov     rcx, rdi
0x1800b4f4a  mov     rax, [rax+20h]
0x1800b4f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4f53  mov     ebx, [rdi+40h]
0x1800b4f56  test    ebx, ebx
0x1800b4f58  jns     short loc_1800B4F61
0x1800b4f5a  mov     edx, 8Ah
0x1800b4f5f  jmp     short loc_1800B4F72
0x1800b4f61  mov     rcx, [rsp+8E0h+var_878]
0x1800b4f66  mov     ebx, [rcx+4]
0x1800b4f69  test    ebx, ebx
0x1800b4f6b  jns     short loc_1800B4F8A
0x1800b4f6d  mov     edx, 8Ch; void *
0x1800b4f72  mov     r9d, ebx; char *
0x1800b4f75  mov     rcx, [rbp+7E8h]; this
0x1800b4f7c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b4f83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b4f88  jmp     short loc_1800B4FA8
0x1800b4f8a  mov     rdx, [rbp+7E0h+arg_20]
0x1800b4f91  call    ??$CastTo@UXvmAudioEndpointVolumeRegisterControlChanged@@@XvmMessage@@QEAAJPEAPEAUXvmAudioEndpointVolumeRegisterControlChanged@@@Z; XvmMessage::CastTo<XvmAudioEndpointVolumeRegisterControlChanged>(XvmAudioEndpointVolumeRegisterControlChanged * *)
0x1800b4f96  mov     ebx, eax
0x1800b4f98  test    eax, eax
0x1800b4f9a  jns     short loc_1800B4FA6
0x1800b4f9c  mov     r9d, eax
0x1800b4f9f  mov     edx, 8Dh
0x1800b4fa4  jmp     short loc_1800B4F75
0x1800b4fa6  xor     ebx, ebx
0x1800b4fa8  mov     rcx, [rbp+7E0h+arg_18]
0x1800b4faf  mov     rax, [rsp+8E0h+var_878]
0x1800b4fb4  mov     [rcx], rax
0x1800b4fb7  mov     eax, ebx
0x1800b4fb9  lea     r11, [rsp+8E0h+var_10]
0x1800b4fc1  mov     rbx, [r11+28h]
0x1800b4fc5  mov     rsi, [r11+30h]
0x1800b4fc9  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b4fce  mov     rsp, r11
0x1800b4fd1  pop     r14
0x1800b4fd3  pop     rdi
0x1800b4fd4  pop     rbp
0x1800b4fd5  retn
```
