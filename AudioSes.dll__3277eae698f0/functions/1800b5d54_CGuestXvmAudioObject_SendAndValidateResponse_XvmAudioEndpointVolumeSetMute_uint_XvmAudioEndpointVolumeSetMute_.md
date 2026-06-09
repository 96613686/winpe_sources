# CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeSetMute>(uint,XvmAudioEndpointVolumeSetMute,XvmMessage * *,XvmAudioEndpointVolumeSetMute * *)

- ea: `0x1800b5d54`
- end: `0x1800b60ae`
- name: `??$SendAndValidateResponse@UXvmAudioEndpointVolumeSetMute@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeSetMute@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `858`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b77b0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a6038`
- `0x1800b5d54`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b5d96`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b5e95`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b5d96`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b5e95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5dca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b5dca`

## string_xrefs

- `0x1800b5dad`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b5dec`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b600b`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b6054`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeSetMute>(
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
  char v35; // [rsp+D8h] [rbp-30h]
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
    v35 = *(_BYTE *)(a3 + 16);
    v32 = 90;
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
            (unsigned int)&dword_180166C6C,
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
          (unsigned int)byte_180166B59,
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
        v18 = XvmMessage::CastTo<XvmAudioEndpointVolumeSetMute>(v21, v40, v12);
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
0x1800b5d54  mov     rax, rsp
0x1800b5d57  mov     [rax+10h], rbx
0x1800b5d5b  mov     [rax+18h], rsi
0x1800b5d5f  mov     [rax+20h], r9
0x1800b5d63  push    rbp
0x1800b5d64  push    rdi
0x1800b5d65  push    r14
0x1800b5d67  lea     rbp, [rax-7E8h]
0x1800b5d6e  sub     rsp, 8D0h
0x1800b5d75  movaps  xmmword ptr [rax-28h], xmm6
0x1800b5d79  mov     rsi, r8
0x1800b5d7c  mov     r14d, edx
0x1800b5d7f  mov     rbx, rcx
0x1800b5d82  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800b5d8a  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800b5d92  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800b5d96  call    cs:__imp_QueryPerformanceCounter
0x1800b5d9c  mov     edi, [rbx+40h]
0x1800b5d9f  test    edi, edi
0x1800b5da1  jns     short loc_1800B5DC5
0x1800b5da3  mov     rcx, [rbp+7E8h]; this
0x1800b5daa  mov     r9d, edi; char *
0x1800b5dad  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b5db4  mov     edx, 4Fh ; 'O'; void *
0x1800b5db9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5dbe  mov     eax, edi
0x1800b5dc0  jmp     loc_1800B6091
0x1800b5dc5  mov     ecx, 810h; cb
0x1800b5dca  call    cs:__imp_CoTaskMemAlloc
0x1800b5dd0  mov     rdi, rax
0x1800b5dd3  mov     [rsp+8E0h+var_878], rax
0x1800b5dd8  test    rax, rax
0x1800b5ddb  jnz     short loc_1800B5E00
0x1800b5ddd  mov     rcx, [rbp+7E8h]; this
0x1800b5de4  mov     ebx, 8007000Eh
0x1800b5de9  mov     r9d, ebx; char *
0x1800b5dec  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b5df3  lea     edx, [rax+52h]; void *
0x1800b5df6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5dfb  jmp     loc_1800B608F
0x1800b5e00  mov     [rbp+7E0h+Src], 0
0x1800b5e08  mov     [rbp+7E0h+var_824], 0
0x1800b5e0f  xor     edx, edx; Val
0x1800b5e11  mov     r8d, 800h; Size
0x1800b5e17  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800b5e1b  call    memset_0
0x1800b5e20  mov     rax, [rsi]
0x1800b5e23  mov     [rbp+7E0h+var_820], rax
0x1800b5e27  movsd   xmm0, qword ptr [rsi+8]
0x1800b5e2c  movsd   [rbp+7E0h+var_818], xmm0
0x1800b5e31  mov     al, [rsi+10h]
0x1800b5e34  mov     [rbp+7E0h+var_810], al
0x1800b5e37  mov     [rbp+7E0h+var_828], 5Ah ; 'Z'
0x1800b5e3e  mov     rcx, rdi; void *
0x1800b5e41  lea     rdx, [rbp+7E0h+Src]; Src
0x1800b5e45  mov     r8d, 810h; Size
0x1800b5e4b  call    memcpy_0
0x1800b5e50  mov     rax, [rsp+8E0h+var_878]
0x1800b5e55  mov     [rax+0Ch], r14d
0x1800b5e59  lea     rax, [rbp+7E0h+arg_18]
0x1800b5e60  mov     [rbp+7E0h+var_848], rax
0x1800b5e64  lea     rax, [rsp+8E0h+var_878]
0x1800b5e69  mov     [rbp+7E0h+var_840], rax
0x1800b5e6d  mov     [rbp+7E0h+var_838], 1
0x1800b5e71  mov     rcx, [rbx+28h]
0x1800b5e75  mov     rax, [rcx]
0x1800b5e78  mov     r9d, 810h
0x1800b5e7e  mov     r8, [rsp+8E0h+var_878]
0x1800b5e83  mov     edx, r14d
0x1800b5e86  mov     rax, [rax+20h]
0x1800b5e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5e8f  mov     edi, eax
0x1800b5e91  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800b5e95  call    cs:__imp_QueryPerformanceCounter
0x1800b5e9b  xorps   xmm6, xmm6
0x1800b5e9e  cmp     qword ptr [rbx+48h], 0
0x1800b5ea3  jz      short loc_1800B5EC7
0x1800b5ea5  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800b5ea9  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800b5ead  cvtsi2ss xmm6, rcx
0x1800b5eb2  mulss   xmm6, cs:__real@447a0000
0x1800b5eba  xorps   xmm0, xmm0
0x1800b5ebd  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800b5ec3  divss   xmm6, xmm0
0x1800b5ec7  mov     rcx, [rsp+8E0h+var_878]
0x1800b5ecc  cmp     dword ptr [rcx+8], 1
0x1800b5ed0  jnz     loc_1800B5F8C
0x1800b5ed6  mov     [rsp+8E0h+var_870], 0
0x1800b5edf  lea     rdx, [rsp+8E0h+var_870]
0x1800b5ee4  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b5ee9  test    eax, eax
0x1800b5eeb  js      loc_1800B5FFD
0x1800b5ef1  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b5ef6  mov     r8, rax
0x1800b5ef9  mov     ecx, [rax]
0x1800b5efb  cmp     ecx, 4
0x1800b5efe  jbe     loc_1800B5FFD
0x1800b5f04  mov     [rbp+7E0h+arg_0], edi
0x1800b5f0a  movss   [rsp+8E0h+var_868], xmm6
0x1800b5f10  mov     [rbp+7E0h+var_860], rbx
0x1800b5f14  mov     rdx, [rsp+8E0h+var_870]
0x1800b5f19  mov     ecx, [rdx+10h]
0x1800b5f1c  mov     [rsp+8E0h+var_864], ecx
0x1800b5f20  mov     ecx, [rdx+4]
0x1800b5f23  mov     [rsp+8E0h+var_880], ecx
0x1800b5f27  mov     eax, [rdx+8]
0x1800b5f2a  mov     [rsp+8E0h+var_880+4], eax
0x1800b5f2e  mov     eax, [rdx]
0x1800b5f30  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800b5f34  lea     rax, [rbp+7E0h+arg_0]
0x1800b5f3b  mov     [rsp+8E0h+var_890], rax
0x1800b5f40  lea     rax, [rsp+8E0h+var_868]
0x1800b5f45  mov     [rsp+8E0h+var_898], rax
0x1800b5f4a  lea     rax, [rbp+7E0h+var_860]
0x1800b5f4e  mov     [rsp+8E0h+var_8A0], rax
0x1800b5f53  lea     rax, [rsp+8E0h+var_864]
0x1800b5f58  mov     [rsp+8E0h+var_8A8], rax
0x1800b5f5d  lea     rax, [rsp+8E0h+var_880]
0x1800b5f62  mov     [rsp+8E0h+var_8B0], rax
0x1800b5f67  lea     rax, [rsp+8E0h+var_880+4]
0x1800b5f6c  mov     [rsp+8E0h+var_8B8], rax
0x1800b5f71  lea     rax, [rsp+8E0h+var_870]
0x1800b5f76  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800b5f7b  lea     rdx, dword_180166C6C
0x1800b5f82  mov     rcx, r8
0x1800b5f85  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b5f8a  jmp     short loc_1800B5FFD
0x1800b5f8c  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b5f91  mov     ecx, [rax]
0x1800b5f93  cmp     ecx, 4
0x1800b5f96  jbe     short loc_1800B5FFD
0x1800b5f98  mov     [rbp+7E0h+arg_0], edi
0x1800b5f9e  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800b5fa4  mov     [rbp+7E0h+var_860], rbx
0x1800b5fa8  mov     rcx, [rsp+8E0h+var_878]
0x1800b5fad  mov     edx, [rcx+8]
0x1800b5fb0  mov     [rsp+8E0h+var_880+4], edx
0x1800b5fb4  mov     ecx, [rbx+30h]
0x1800b5fb7  mov     [rsp+8E0h+var_880], ecx
0x1800b5fbb  lea     rcx, [rbp+7E0h+arg_0]
0x1800b5fc2  mov     [rsp+8E0h+var_8A0], rcx
0x1800b5fc7  lea     rcx, [rsp+8E0h+var_870]
0x1800b5fcc  mov     [rsp+8E0h+var_8A8], rcx
0x1800b5fd1  lea     rcx, [rbp+7E0h+var_860]
0x1800b5fd5  mov     [rsp+8E0h+var_8B0], rcx
0x1800b5fda  lea     rcx, [rsp+8E0h+var_880+4]
0x1800b5fdf  mov     [rsp+8E0h+var_8B8], rcx
0x1800b5fe4  lea     rcx, [rsp+8E0h+var_880]
0x1800b5fe9  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800b5fee  lea     rdx, byte_180166B59
0x1800b5ff5  mov     rcx, rax
0x1800b5ff8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b5ffd  mov     rcx, [rbp+7E8h]; this
0x1800b6004  test    edi, edi
0x1800b6006  jns     short loc_1800B602B
0x1800b6008  mov     r9d, edi; char *
0x1800b600b  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b6012  mov     edx, 81h; void *
0x1800b6017  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b601c  mov     rax, [rbx]
0x1800b601f  mov     rcx, rbx
0x1800b6022  mov     rax, [rax+20h]
0x1800b6026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b602b  mov     ebx, [rbx+40h]
0x1800b602e  test    ebx, ebx
0x1800b6030  jns     short loc_1800B6039
0x1800b6032  mov     edx, 8Ah
0x1800b6037  jmp     short loc_1800B604A
0x1800b6039  mov     rcx, [rsp+8E0h+var_878]
0x1800b603e  mov     ebx, [rcx+4]
0x1800b6041  test    ebx, ebx
0x1800b6043  jns     short loc_1800B6062
0x1800b6045  mov     edx, 8Ch; void *
0x1800b604a  mov     r9d, ebx; char *
0x1800b604d  mov     rcx, [rbp+7E8h]; this
0x1800b6054  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b605b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6060  jmp     short loc_1800B6080
0x1800b6062  mov     rdx, [rbp+7E0h+arg_20]
0x1800b6069  call    ??$CastTo@UXvmAudioEndpointVolumeSetMute@@@XvmMessage@@QEAAJPEAPEAUXvmAudioEndpointVolumeSetMute@@@Z; XvmMessage::CastTo<XvmAudioEndpointVolumeSetMute>(XvmAudioEndpointVolumeSetMute * *)
0x1800b606e  mov     ebx, eax
0x1800b6070  test    eax, eax
0x1800b6072  jns     short loc_1800B607E
0x1800b6074  mov     r9d, eax
0x1800b6077  mov     edx, 8Dh
0x1800b607c  jmp     short loc_1800B604D
0x1800b607e  xor     ebx, ebx
0x1800b6080  mov     rcx, [rbp+7E0h+arg_18]
0x1800b6087  mov     rax, [rsp+8E0h+var_878]
0x1800b608c  mov     [rcx], rax
0x1800b608f  mov     eax, ebx
0x1800b6091  lea     r11, [rsp+8E0h+var_10]
0x1800b6099  mov     rbx, [r11+28h]
0x1800b609d  mov     rsi, [r11+30h]
0x1800b60a1  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b60a6  mov     rsp, r11
0x1800b60a9  pop     r14
0x1800b60ab  pop     rdi
0x1800b60ac  pop     rbp
0x1800b60ad  retn
```
