# CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeSetMasterVolumeLevelScalar>(uint,XvmAudioEndpointVolumeSetMasterVolumeLevelScalar,XvmMessage * *,XvmAudioEndpointVolumeSetMasterVolumeLevelScalar * *)

- ea: `0x1800b59f4`
- end: `0x1800b5d4e`
- name: `??$SendAndValidateResponse@UXvmAudioEndpointVolumeSetMasterVolumeLevelScalar@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeSetMasterVolumeLevelScalar@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `858`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b76e0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a5ff0`
- `0x1800b59f4`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b5a36`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b5b35`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b5a36`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b5b35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5a6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5a6a`

## string_xrefs

- `0x1800b5a4d`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b5a8c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b5cab`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b5cf4`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeSetMasterVolumeLevelScalar>(
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
  _QWORD v34[2]; // [rsp+C8h] [rbp-40h] BYREF
  int v35; // [rsp+D8h] [rbp-30h]
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
    v35 = *(_DWORD *)(a3 + 16);
    v32 = 83;
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
            (unsigned int)&unk_18016713C,
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
          (unsigned int)&unk_1801671B5,
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
        v18 = XvmMessage::CastTo<XvmAudioEndpointVolumeSetMasterVolumeLevelScalar>(v21, v40, v12);
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
0x1800b59f4  mov     rax, rsp
0x1800b59f7  mov     [rax+10h], rbx
0x1800b59fb  mov     [rax+18h], rsi
0x1800b59ff  mov     [rax+20h], r9
0x1800b5a03  push    rbp
0x1800b5a04  push    rdi
0x1800b5a05  push    r14
0x1800b5a07  lea     rbp, [rax-7E8h]
0x1800b5a0e  sub     rsp, 8D0h
0x1800b5a15  movaps  xmmword ptr [rax-28h], xmm6
0x1800b5a19  mov     rsi, r8
0x1800b5a1c  mov     r14d, edx
0x1800b5a1f  mov     rbx, rcx
0x1800b5a22  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800b5a2a  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800b5a32  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800b5a36  call    cs:__imp_QueryPerformanceCounter
0x1800b5a3c  mov     edi, [rbx+40h]
0x1800b5a3f  test    edi, edi
0x1800b5a41  jns     short loc_1800B5A65
0x1800b5a43  mov     rcx, [rbp+7E8h]; this
0x1800b5a4a  mov     r9d, edi; char *
0x1800b5a4d  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b5a54  mov     edx, 4Fh ; 'O'; void *
0x1800b5a59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5a5e  mov     eax, edi
0x1800b5a60  jmp     loc_1800B5D31
0x1800b5a65  mov     ecx, 810h; cb
0x1800b5a6a  call    cs:__imp_CoTaskMemAlloc
0x1800b5a70  mov     rdi, rax
0x1800b5a73  mov     [rsp+8E0h+var_878], rax
0x1800b5a78  test    rax, rax
0x1800b5a7b  jnz     short loc_1800B5AA0
0x1800b5a7d  mov     rcx, [rbp+7E8h]; this
0x1800b5a84  mov     ebx, 8007000Eh
0x1800b5a89  mov     r9d, ebx; char *
0x1800b5a8c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b5a93  lea     edx, [rax+52h]; void *
0x1800b5a96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5a9b  jmp     loc_1800B5D2F
0x1800b5aa0  mov     [rbp+7E0h+Src], 0
0x1800b5aa8  mov     [rbp+7E0h+var_824], 0
0x1800b5aaf  xor     edx, edx; Val
0x1800b5ab1  mov     r8d, 800h; Size
0x1800b5ab7  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800b5abb  call    memset_0
0x1800b5ac0  mov     rax, [rsi]
0x1800b5ac3  mov     [rbp+7E0h+var_820], rax
0x1800b5ac7  movsd   xmm0, qword ptr [rsi+8]
0x1800b5acc  movsd   [rbp+7E0h+var_818], xmm0
0x1800b5ad1  mov     eax, [rsi+10h]
0x1800b5ad4  mov     [rbp+7E0h+var_810], eax
0x1800b5ad7  mov     [rbp+7E0h+var_828], 53h ; 'S'
0x1800b5ade  mov     rcx, rdi; void *
0x1800b5ae1  lea     rdx, [rbp+7E0h+Src]; Src
0x1800b5ae5  mov     r8d, 810h; Size
0x1800b5aeb  call    memcpy_0
0x1800b5af0  mov     rax, [rsp+8E0h+var_878]
0x1800b5af5  mov     [rax+0Ch], r14d
0x1800b5af9  lea     rax, [rbp+7E0h+arg_18]
0x1800b5b00  mov     [rbp+7E0h+var_848], rax
0x1800b5b04  lea     rax, [rsp+8E0h+var_878]
0x1800b5b09  mov     [rbp+7E0h+var_840], rax
0x1800b5b0d  mov     [rbp+7E0h+var_838], 1
0x1800b5b11  mov     rcx, [rbx+28h]
0x1800b5b15  mov     rax, [rcx]
0x1800b5b18  mov     r9d, 810h
0x1800b5b1e  mov     r8, [rsp+8E0h+var_878]
0x1800b5b23  mov     edx, r14d
0x1800b5b26  mov     rax, [rax+20h]
0x1800b5b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5b2f  mov     edi, eax
0x1800b5b31  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800b5b35  call    cs:__imp_QueryPerformanceCounter
0x1800b5b3b  xorps   xmm6, xmm6
0x1800b5b3e  cmp     qword ptr [rbx+48h], 0
0x1800b5b43  jz      short loc_1800B5B67
0x1800b5b45  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800b5b49  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800b5b4d  cvtsi2ss xmm6, rcx
0x1800b5b52  mulss   xmm6, cs:__real@447a0000
0x1800b5b5a  xorps   xmm0, xmm0
0x1800b5b5d  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800b5b63  divss   xmm6, xmm0
0x1800b5b67  mov     rcx, [rsp+8E0h+var_878]
0x1800b5b6c  cmp     dword ptr [rcx+8], 1
0x1800b5b70  jnz     loc_1800B5C2C
0x1800b5b76  mov     [rsp+8E0h+var_870], 0
0x1800b5b7f  lea     rdx, [rsp+8E0h+var_870]
0x1800b5b84  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b5b89  test    eax, eax
0x1800b5b8b  js      loc_1800B5C9D
0x1800b5b91  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b5b96  mov     r8, rax
0x1800b5b99  mov     ecx, [rax]
0x1800b5b9b  cmp     ecx, 4
0x1800b5b9e  jbe     loc_1800B5C9D
0x1800b5ba4  mov     [rbp+7E0h+arg_0], edi
0x1800b5baa  movss   [rsp+8E0h+var_868], xmm6
0x1800b5bb0  mov     [rbp+7E0h+var_860], rbx
0x1800b5bb4  mov     rdx, [rsp+8E0h+var_870]
0x1800b5bb9  mov     ecx, [rdx+10h]
0x1800b5bbc  mov     [rsp+8E0h+var_864], ecx
0x1800b5bc0  mov     ecx, [rdx+4]
0x1800b5bc3  mov     [rsp+8E0h+var_880], ecx
0x1800b5bc7  mov     eax, [rdx+8]
0x1800b5bca  mov     [rsp+8E0h+var_880+4], eax
0x1800b5bce  mov     eax, [rdx]
0x1800b5bd0  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800b5bd4  lea     rax, [rbp+7E0h+arg_0]
0x1800b5bdb  mov     [rsp+8E0h+var_890], rax
0x1800b5be0  lea     rax, [rsp+8E0h+var_868]
0x1800b5be5  mov     [rsp+8E0h+var_898], rax
0x1800b5bea  lea     rax, [rbp+7E0h+var_860]
0x1800b5bee  mov     [rsp+8E0h+var_8A0], rax
0x1800b5bf3  lea     rax, [rsp+8E0h+var_864]
0x1800b5bf8  mov     [rsp+8E0h+var_8A8], rax
0x1800b5bfd  lea     rax, [rsp+8E0h+var_880]
0x1800b5c02  mov     [rsp+8E0h+var_8B0], rax
0x1800b5c07  lea     rax, [rsp+8E0h+var_880+4]
0x1800b5c0c  mov     [rsp+8E0h+var_8B8], rax
0x1800b5c11  lea     rax, [rsp+8E0h+var_870]
0x1800b5c16  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800b5c1b  lea     rdx, unk_18016713C
0x1800b5c22  mov     rcx, r8
0x1800b5c25  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b5c2a  jmp     short loc_1800B5C9D
0x1800b5c2c  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b5c31  mov     ecx, [rax]
0x1800b5c33  cmp     ecx, 4
0x1800b5c36  jbe     short loc_1800B5C9D
0x1800b5c38  mov     [rbp+7E0h+arg_0], edi
0x1800b5c3e  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800b5c44  mov     [rbp+7E0h+var_860], rbx
0x1800b5c48  mov     rcx, [rsp+8E0h+var_878]
0x1800b5c4d  mov     edx, [rcx+8]
0x1800b5c50  mov     [rsp+8E0h+var_880+4], edx
0x1800b5c54  mov     ecx, [rbx+30h]
0x1800b5c57  mov     [rsp+8E0h+var_880], ecx
0x1800b5c5b  lea     rcx, [rbp+7E0h+arg_0]
0x1800b5c62  mov     [rsp+8E0h+var_8A0], rcx
0x1800b5c67  lea     rcx, [rsp+8E0h+var_870]
0x1800b5c6c  mov     [rsp+8E0h+var_8A8], rcx
0x1800b5c71  lea     rcx, [rbp+7E0h+var_860]
0x1800b5c75  mov     [rsp+8E0h+var_8B0], rcx
0x1800b5c7a  lea     rcx, [rsp+8E0h+var_880+4]
0x1800b5c7f  mov     [rsp+8E0h+var_8B8], rcx
0x1800b5c84  lea     rcx, [rsp+8E0h+var_880]
0x1800b5c89  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800b5c8e  lea     rdx, unk_1801671B5
0x1800b5c95  mov     rcx, rax
0x1800b5c98  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b5c9d  mov     rcx, [rbp+7E8h]; this
0x1800b5ca4  test    edi, edi
0x1800b5ca6  jns     short loc_1800B5CCB
0x1800b5ca8  mov     r9d, edi; char *
0x1800b5cab  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b5cb2  mov     edx, 81h; void *
0x1800b5cb7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b5cbc  mov     rax, [rbx]
0x1800b5cbf  mov     rcx, rbx
0x1800b5cc2  mov     rax, [rax+20h]
0x1800b5cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5ccb  mov     ebx, [rbx+40h]
0x1800b5cce  test    ebx, ebx
0x1800b5cd0  jns     short loc_1800B5CD9
0x1800b5cd2  mov     edx, 8Ah
0x1800b5cd7  jmp     short loc_1800B5CEA
0x1800b5cd9  mov     rcx, [rsp+8E0h+var_878]
0x1800b5cde  mov     ebx, [rcx+4]
0x1800b5ce1  test    ebx, ebx
0x1800b5ce3  jns     short loc_1800B5D02
0x1800b5ce5  mov     edx, 8Ch; void *
0x1800b5cea  mov     r9d, ebx; char *
0x1800b5ced  mov     rcx, [rbp+7E8h]; this
0x1800b5cf4  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b5cfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5d00  jmp     short loc_1800B5D20
0x1800b5d02  mov     rdx, [rbp+7E0h+arg_20]
0x1800b5d09  call    ??$CastTo@UXvmAudioEndpointVolumeSetMasterVolumeLevelScalar@@@XvmMessage@@QEAAJPEAPEAUXvmAudioEndpointVolumeSetMasterVolumeLevelScalar@@@Z; XvmMessage::CastTo<XvmAudioEndpointVolumeSetMasterVolumeLevelScalar>(XvmAudioEndpointVolumeSetMasterVolumeLevelScalar * *)
0x1800b5d0e  mov     ebx, eax
0x1800b5d10  test    eax, eax
0x1800b5d12  jns     short loc_1800B5D1E
0x1800b5d14  mov     r9d, eax
0x1800b5d17  mov     edx, 8Dh
0x1800b5d1c  jmp     short loc_1800B5CED
0x1800b5d1e  xor     ebx, ebx
0x1800b5d20  mov     rcx, [rbp+7E0h+arg_18]
0x1800b5d27  mov     rax, [rsp+8E0h+var_878]
0x1800b5d2c  mov     [rcx], rax
0x1800b5d2f  mov     eax, ebx
0x1800b5d31  lea     r11, [rsp+8E0h+var_10]
0x1800b5d39  mov     rbx, [r11+28h]
0x1800b5d3d  mov     rsi, [r11+30h]
0x1800b5d41  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b5d46  mov     rsp, r11
0x1800b5d49  pop     r14
0x1800b5d4b  pop     rdi
0x1800b5d4c  pop     rbp
0x1800b5d4d  retn
```
