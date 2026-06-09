# CGuestXvmAudioObject::SendAndValidateResponse<XvmSetMasterVolume>(uint,XvmSetMasterVolume,XvmMessage * *,XvmSetMasterVolume * *)

- ea: `0x1800bf200`
- end: `0x1800bf55a`
- name: `??$SendAndValidateResponse@UXvmSetMasterVolume@@@CGuestXvmAudioObject@@QEAAJIUXvmSetMasterVolume@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `858`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c25b0`
- `0x1800c2680`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2e28`
- `0x1800bf200`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bf242`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bf341`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bf242`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bf341`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf276`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf276`

## string_xrefs

- `0x1800bf259`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bf298`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bf4b7`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bf500`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmSetMasterVolume>(__int64 a1, unsigned int a2, __int64 a3, ...)
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
    v32 = 22;
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
            (unsigned int)&unk_1801689FC,
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
          (unsigned int)&unk_180168A75,
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
        v18 = XvmMessage::CastTo<XvmSetMasterVolume>(v21, v40, v12);
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
0x1800bf200  mov     rax, rsp
0x1800bf203  mov     [rax+10h], rbx
0x1800bf207  mov     [rax+18h], rsi
0x1800bf20b  mov     [rax+20h], r9
0x1800bf20f  push    rbp
0x1800bf210  push    rdi
0x1800bf211  push    r14
0x1800bf213  lea     rbp, [rax-7E8h]
0x1800bf21a  sub     rsp, 8D0h
0x1800bf221  movaps  xmmword ptr [rax-28h], xmm6
0x1800bf225  mov     rsi, r8
0x1800bf228  mov     r14d, edx
0x1800bf22b  mov     rbx, rcx
0x1800bf22e  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bf236  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800bf23e  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800bf242  call    cs:__imp_QueryPerformanceCounter
0x1800bf248  mov     edi, [rbx+40h]
0x1800bf24b  test    edi, edi
0x1800bf24d  jns     short loc_1800BF271
0x1800bf24f  mov     rcx, [rbp+7E8h]; this
0x1800bf256  mov     r9d, edi; char *
0x1800bf259  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bf260  mov     edx, 4Fh ; 'O'; void *
0x1800bf265  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf26a  mov     eax, edi
0x1800bf26c  jmp     loc_1800BF53D
0x1800bf271  mov     ecx, 810h; cb
0x1800bf276  call    cs:__imp_CoTaskMemAlloc
0x1800bf27c  mov     rdi, rax
0x1800bf27f  mov     [rsp+8E0h+var_878], rax
0x1800bf284  test    rax, rax
0x1800bf287  jnz     short loc_1800BF2AC
0x1800bf289  mov     rcx, [rbp+7E8h]; this
0x1800bf290  mov     ebx, 8007000Eh
0x1800bf295  mov     r9d, ebx; char *
0x1800bf298  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bf29f  lea     edx, [rax+52h]; void *
0x1800bf2a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf2a7  jmp     loc_1800BF53B
0x1800bf2ac  mov     [rbp+7E0h+Src], 0
0x1800bf2b4  mov     [rbp+7E0h+var_824], 0
0x1800bf2bb  xor     edx, edx; Val
0x1800bf2bd  mov     r8d, 800h; Size
0x1800bf2c3  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bf2c7  call    memset_0
0x1800bf2cc  mov     rax, [rsi]
0x1800bf2cf  mov     [rbp+7E0h+var_820], rax
0x1800bf2d3  movsd   xmm0, qword ptr [rsi+8]
0x1800bf2d8  movsd   [rbp+7E0h+var_818], xmm0
0x1800bf2dd  mov     eax, [rsi+10h]
0x1800bf2e0  mov     [rbp+7E0h+var_810], eax
0x1800bf2e3  mov     [rbp+7E0h+var_828], 16h
0x1800bf2ea  mov     rcx, rdi; void *
0x1800bf2ed  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bf2f1  mov     r8d, 810h; Size
0x1800bf2f7  call    memcpy_0
0x1800bf2fc  mov     rax, [rsp+8E0h+var_878]
0x1800bf301  mov     [rax+0Ch], r14d
0x1800bf305  lea     rax, [rbp+7E0h+arg_18]
0x1800bf30c  mov     [rbp+7E0h+var_848], rax
0x1800bf310  lea     rax, [rsp+8E0h+var_878]
0x1800bf315  mov     [rbp+7E0h+var_840], rax
0x1800bf319  mov     [rbp+7E0h+var_838], 1
0x1800bf31d  mov     rcx, [rbx+28h]
0x1800bf321  mov     rax, [rcx]
0x1800bf324  mov     r9d, 810h
0x1800bf32a  mov     r8, [rsp+8E0h+var_878]
0x1800bf32f  mov     edx, r14d
0x1800bf332  mov     rax, [rax+20h]
0x1800bf336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf33b  mov     edi, eax
0x1800bf33d  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800bf341  call    cs:__imp_QueryPerformanceCounter
0x1800bf347  xorps   xmm6, xmm6
0x1800bf34a  cmp     qword ptr [rbx+48h], 0
0x1800bf34f  jz      short loc_1800BF373
0x1800bf351  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800bf355  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800bf359  cvtsi2ss xmm6, rcx
0x1800bf35e  mulss   xmm6, cs:__real@447a0000
0x1800bf366  xorps   xmm0, xmm0
0x1800bf369  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800bf36f  divss   xmm6, xmm0
0x1800bf373  mov     rcx, [rsp+8E0h+var_878]
0x1800bf378  cmp     dword ptr [rcx+8], 1
0x1800bf37c  jnz     loc_1800BF438
0x1800bf382  mov     [rsp+8E0h+var_870], 0
0x1800bf38b  lea     rdx, [rsp+8E0h+var_870]
0x1800bf390  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bf395  test    eax, eax
0x1800bf397  js      loc_1800BF4A9
0x1800bf39d  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bf3a2  mov     r8, rax
0x1800bf3a5  mov     ecx, [rax]
0x1800bf3a7  cmp     ecx, 4
0x1800bf3aa  jbe     loc_1800BF4A9
0x1800bf3b0  mov     [rbp+7E0h+arg_0], edi
0x1800bf3b6  movss   [rsp+8E0h+var_868], xmm6
0x1800bf3bc  mov     [rbp+7E0h+var_860], rbx
0x1800bf3c0  mov     rdx, [rsp+8E0h+var_870]
0x1800bf3c5  mov     ecx, [rdx+10h]
0x1800bf3c8  mov     [rsp+8E0h+var_864], ecx
0x1800bf3cc  mov     ecx, [rdx+4]
0x1800bf3cf  mov     [rsp+8E0h+var_880], ecx
0x1800bf3d3  mov     eax, [rdx+8]
0x1800bf3d6  mov     [rsp+8E0h+var_880+4], eax
0x1800bf3da  mov     eax, [rdx]
0x1800bf3dc  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800bf3e0  lea     rax, [rbp+7E0h+arg_0]
0x1800bf3e7  mov     [rsp+8E0h+var_890], rax
0x1800bf3ec  lea     rax, [rsp+8E0h+var_868]
0x1800bf3f1  mov     [rsp+8E0h+var_898], rax
0x1800bf3f6  lea     rax, [rbp+7E0h+var_860]
0x1800bf3fa  mov     [rsp+8E0h+var_8A0], rax
0x1800bf3ff  lea     rax, [rsp+8E0h+var_864]
0x1800bf404  mov     [rsp+8E0h+var_8A8], rax
0x1800bf409  lea     rax, [rsp+8E0h+var_880]
0x1800bf40e  mov     [rsp+8E0h+var_8B0], rax
0x1800bf413  lea     rax, [rsp+8E0h+var_880+4]
0x1800bf418  mov     [rsp+8E0h+var_8B8], rax
0x1800bf41d  lea     rax, [rsp+8E0h+var_870]
0x1800bf422  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bf427  lea     rdx, unk_1801689FC
0x1800bf42e  mov     rcx, r8
0x1800bf431  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bf436  jmp     short loc_1800BF4A9
0x1800bf438  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bf43d  mov     ecx, [rax]
0x1800bf43f  cmp     ecx, 4
0x1800bf442  jbe     short loc_1800BF4A9
0x1800bf444  mov     [rbp+7E0h+arg_0], edi
0x1800bf44a  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bf450  mov     [rbp+7E0h+var_860], rbx
0x1800bf454  mov     rcx, [rsp+8E0h+var_878]
0x1800bf459  mov     edx, [rcx+8]
0x1800bf45c  mov     [rsp+8E0h+var_880+4], edx
0x1800bf460  mov     ecx, [rbx+30h]
0x1800bf463  mov     [rsp+8E0h+var_880], ecx
0x1800bf467  lea     rcx, [rbp+7E0h+arg_0]
0x1800bf46e  mov     [rsp+8E0h+var_8A0], rcx
0x1800bf473  lea     rcx, [rsp+8E0h+var_870]
0x1800bf478  mov     [rsp+8E0h+var_8A8], rcx
0x1800bf47d  lea     rcx, [rbp+7E0h+var_860]
0x1800bf481  mov     [rsp+8E0h+var_8B0], rcx
0x1800bf486  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bf48b  mov     [rsp+8E0h+var_8B8], rcx
0x1800bf490  lea     rcx, [rsp+8E0h+var_880]
0x1800bf495  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bf49a  lea     rdx, unk_180168A75
0x1800bf4a1  mov     rcx, rax
0x1800bf4a4  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bf4a9  mov     rcx, [rbp+7E8h]; this
0x1800bf4b0  test    edi, edi
0x1800bf4b2  jns     short loc_1800BF4D7
0x1800bf4b4  mov     r9d, edi; char *
0x1800bf4b7  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bf4be  mov     edx, 81h; void *
0x1800bf4c3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bf4c8  mov     rax, [rbx]
0x1800bf4cb  mov     rcx, rbx
0x1800bf4ce  mov     rax, [rax+20h]
0x1800bf4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf4d7  mov     ebx, [rbx+40h]
0x1800bf4da  test    ebx, ebx
0x1800bf4dc  jns     short loc_1800BF4E5
0x1800bf4de  mov     edx, 8Ah
0x1800bf4e3  jmp     short loc_1800BF4F6
0x1800bf4e5  mov     rcx, [rsp+8E0h+var_878]
0x1800bf4ea  mov     ebx, [rcx+4]
0x1800bf4ed  test    ebx, ebx
0x1800bf4ef  jns     short loc_1800BF50E
0x1800bf4f1  mov     edx, 8Ch; void *
0x1800bf4f6  mov     r9d, ebx; char *
0x1800bf4f9  mov     rcx, [rbp+7E8h]; this
0x1800bf500  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bf507  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf50c  jmp     short loc_1800BF52C
0x1800bf50e  mov     rdx, [rbp+7E0h+arg_20]
0x1800bf515  call    ??$CastTo@UXvmSetMasterVolume@@@XvmMessage@@QEAAJPEAPEAUXvmSetMasterVolume@@@Z; XvmMessage::CastTo<XvmSetMasterVolume>(XvmSetMasterVolume * *)
0x1800bf51a  mov     ebx, eax
0x1800bf51c  test    eax, eax
0x1800bf51e  jns     short loc_1800BF52A
0x1800bf520  mov     r9d, eax
0x1800bf523  mov     edx, 8Dh
0x1800bf528  jmp     short loc_1800BF4F9
0x1800bf52a  xor     ebx, ebx
0x1800bf52c  mov     rcx, [rbp+7E0h+arg_18]
0x1800bf533  mov     rax, [rsp+8E0h+var_878]
0x1800bf538  mov     [rcx], rax
0x1800bf53b  mov     eax, ebx
0x1800bf53d  lea     r11, [rsp+8E0h+var_10]
0x1800bf545  mov     rbx, [r11+28h]
0x1800bf549  mov     rsi, [r11+30h]
0x1800bf54d  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bf552  mov     rsp, r11
0x1800bf555  pop     r14
0x1800bf557  pop     rdi
0x1800bf558  pop     rbp
0x1800bf559  retn
```
