# CGuestXvmAudioObject::SendAndValidateResponse<XvmStart>(uint,XvmStart,XvmMessage * *,XvmStart * *)

- ea: `0x1800ae5b8`
- end: `0x1800ae8fe`
- name: `??$SendAndValidateResponse@UXvmStart@@@CGuestXvmAudioObject@@QEAAJIUXvmStart@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180081ef0`
- `0x1800b1690`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2f00`
- `0x1800ae5b8`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ae5fa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ae6e5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ae5fa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ae6e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ae62e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ae62e`

## string_xrefs

- `0x1800ae611`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ae650`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ae85b`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ae8a4`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmStart>(__int64 a1, unsigned int a2, char a3, ...)
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
    v32 = 7;
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
            (unsigned int)&unk_1801662F1,
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
          (unsigned int)&unk_1801661DE,
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
        v18 = XvmMessage::CastTo<XvmStart>(v21, v39, v12);
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
0x1800ae5b8  mov     rax, rsp
0x1800ae5bb  mov     [rax+10h], rbx
0x1800ae5bf  mov     [rax+18h], rsi
0x1800ae5c3  mov     [rax+20h], r9
0x1800ae5c7  push    rbp
0x1800ae5c8  push    rdi
0x1800ae5c9  push    r14
0x1800ae5cb  lea     rbp, [rax-7E8h]
0x1800ae5d2  sub     rsp, 8D0h
0x1800ae5d9  movaps  xmmword ptr [rax-28h], xmm6
0x1800ae5dd  mov     bl, r8b
0x1800ae5e0  mov     r14d, edx
0x1800ae5e3  mov     rdi, rcx
0x1800ae5e6  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800ae5ee  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800ae5f6  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800ae5fa  call    cs:__imp_QueryPerformanceCounter
0x1800ae600  mov     esi, [rdi+40h]
0x1800ae603  test    esi, esi
0x1800ae605  jns     short loc_1800AE629
0x1800ae607  mov     rcx, [rbp+7E8h]; this
0x1800ae60e  mov     r9d, esi; char *
0x1800ae611  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ae618  mov     edx, 4Fh ; 'O'; void *
0x1800ae61d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae622  mov     eax, esi
0x1800ae624  jmp     loc_1800AE8E1
0x1800ae629  mov     ecx, 810h; cb
0x1800ae62e  call    cs:__imp_CoTaskMemAlloc
0x1800ae634  mov     rsi, rax
0x1800ae637  mov     [rsp+8E0h+var_878], rax
0x1800ae63c  test    rax, rax
0x1800ae63f  jnz     short loc_1800AE664
0x1800ae641  mov     rcx, [rbp+7E8h]; this
0x1800ae648  mov     ebx, 8007000Eh
0x1800ae64d  mov     r9d, ebx; char *
0x1800ae650  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ae657  lea     edx, [rax+52h]; void *
0x1800ae65a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae65f  jmp     loc_1800AE8DF
0x1800ae664  mov     [rbp+7E0h+Src], 0
0x1800ae66c  mov     [rbp+7E0h+var_824], 0
0x1800ae673  xor     edx, edx; Val
0x1800ae675  mov     r8d, 800h; Size
0x1800ae67b  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800ae67f  call    memset_0
0x1800ae684  mov     [rbp+7E0h+var_820], bl
0x1800ae687  mov     [rbp+7E0h+var_828], 7
0x1800ae68e  mov     rcx, rsi; void *
0x1800ae691  lea     rdx, [rbp+7E0h+Src]; Src
0x1800ae695  mov     r8d, 810h; Size
0x1800ae69b  call    memcpy_0
0x1800ae6a0  mov     rax, [rsp+8E0h+var_878]
0x1800ae6a5  mov     [rax+0Ch], r14d
0x1800ae6a9  lea     rax, [rbp+7E0h+arg_18]
0x1800ae6b0  mov     [rbp+7E0h+var_848], rax
0x1800ae6b4  lea     rax, [rsp+8E0h+var_878]
0x1800ae6b9  mov     [rbp+7E0h+var_840], rax
0x1800ae6bd  mov     [rbp+7E0h+var_838], 1
0x1800ae6c1  mov     rcx, [rdi+28h]
0x1800ae6c5  mov     rax, [rcx]
0x1800ae6c8  mov     r9d, 810h
0x1800ae6ce  mov     r8, [rsp+8E0h+var_878]
0x1800ae6d3  mov     edx, r14d
0x1800ae6d6  mov     rax, [rax+20h]
0x1800ae6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae6df  mov     ebx, eax
0x1800ae6e1  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800ae6e5  call    cs:__imp_QueryPerformanceCounter
0x1800ae6eb  xorps   xmm6, xmm6
0x1800ae6ee  cmp     qword ptr [rdi+48h], 0
0x1800ae6f3  jz      short loc_1800AE717
0x1800ae6f5  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800ae6f9  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800ae6fd  cvtsi2ss xmm6, rcx
0x1800ae702  mulss   xmm6, cs:__real@447a0000
0x1800ae70a  xorps   xmm0, xmm0
0x1800ae70d  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800ae713  divss   xmm6, xmm0
0x1800ae717  mov     rcx, [rsp+8E0h+var_878]
0x1800ae71c  cmp     dword ptr [rcx+8], 1
0x1800ae720  jnz     loc_1800AE7DC
0x1800ae726  mov     [rsp+8E0h+var_870], 0
0x1800ae72f  lea     rdx, [rsp+8E0h+var_870]
0x1800ae734  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800ae739  test    eax, eax
0x1800ae73b  js      loc_1800AE84D
0x1800ae741  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ae746  mov     r8, rax
0x1800ae749  mov     ecx, [rax]
0x1800ae74b  cmp     ecx, 4
0x1800ae74e  jbe     loc_1800AE84D
0x1800ae754  mov     [rbp+7E0h+arg_0], ebx
0x1800ae75a  movss   [rsp+8E0h+var_868], xmm6
0x1800ae760  mov     [rbp+7E0h+var_860], rdi
0x1800ae764  mov     rdx, [rsp+8E0h+var_870]
0x1800ae769  mov     ecx, [rdx+10h]
0x1800ae76c  mov     [rsp+8E0h+var_864], ecx
0x1800ae770  mov     ecx, [rdx+4]
0x1800ae773  mov     [rsp+8E0h+var_880], ecx
0x1800ae777  mov     eax, [rdx+8]
0x1800ae77a  mov     [rsp+8E0h+var_880+4], eax
0x1800ae77e  mov     eax, [rdx]
0x1800ae780  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800ae784  lea     rax, [rbp+7E0h+arg_0]
0x1800ae78b  mov     [rsp+8E0h+var_890], rax
0x1800ae790  lea     rax, [rsp+8E0h+var_868]
0x1800ae795  mov     [rsp+8E0h+var_898], rax
0x1800ae79a  lea     rax, [rbp+7E0h+var_860]
0x1800ae79e  mov     [rsp+8E0h+var_8A0], rax
0x1800ae7a3  lea     rax, [rsp+8E0h+var_864]
0x1800ae7a8  mov     [rsp+8E0h+var_8A8], rax
0x1800ae7ad  lea     rax, [rsp+8E0h+var_880]
0x1800ae7b2  mov     [rsp+8E0h+var_8B0], rax
0x1800ae7b7  lea     rax, [rsp+8E0h+var_880+4]
0x1800ae7bc  mov     [rsp+8E0h+var_8B8], rax
0x1800ae7c1  lea     rax, [rsp+8E0h+var_870]
0x1800ae7c6  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800ae7cb  lea     rdx, unk_1801662F1
0x1800ae7d2  mov     rcx, r8
0x1800ae7d5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ae7da  jmp     short loc_1800AE84D
0x1800ae7dc  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ae7e1  mov     ecx, [rax]
0x1800ae7e3  cmp     ecx, 4
0x1800ae7e6  jbe     short loc_1800AE84D
0x1800ae7e8  mov     [rbp+7E0h+arg_0], ebx
0x1800ae7ee  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800ae7f4  mov     [rbp+7E0h+var_860], rdi
0x1800ae7f8  mov     rcx, [rsp+8E0h+var_878]
0x1800ae7fd  mov     edx, [rcx+8]
0x1800ae800  mov     [rsp+8E0h+var_880+4], edx
0x1800ae804  mov     ecx, [rdi+30h]
0x1800ae807  mov     [rsp+8E0h+var_880], ecx
0x1800ae80b  lea     rcx, [rbp+7E0h+arg_0]
0x1800ae812  mov     [rsp+8E0h+var_8A0], rcx
0x1800ae817  lea     rcx, [rsp+8E0h+var_870]
0x1800ae81c  mov     [rsp+8E0h+var_8A8], rcx
0x1800ae821  lea     rcx, [rbp+7E0h+var_860]
0x1800ae825  mov     [rsp+8E0h+var_8B0], rcx
0x1800ae82a  lea     rcx, [rsp+8E0h+var_880+4]
0x1800ae82f  mov     [rsp+8E0h+var_8B8], rcx
0x1800ae834  lea     rcx, [rsp+8E0h+var_880]
0x1800ae839  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800ae83e  lea     rdx, unk_1801661DE
0x1800ae845  mov     rcx, rax
0x1800ae848  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ae84d  mov     rcx, [rbp+7E8h]; this
0x1800ae854  test    ebx, ebx
0x1800ae856  jns     short loc_1800AE87B
0x1800ae858  mov     r9d, ebx; char *
0x1800ae85b  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ae862  mov     edx, 81h; void *
0x1800ae867  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ae86c  mov     rax, [rdi]
0x1800ae86f  mov     rcx, rdi
0x1800ae872  mov     rax, [rax+20h]
0x1800ae876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae87b  mov     ebx, [rdi+40h]
0x1800ae87e  test    ebx, ebx
0x1800ae880  jns     short loc_1800AE889
0x1800ae882  mov     edx, 8Ah
0x1800ae887  jmp     short loc_1800AE89A
0x1800ae889  mov     rcx, [rsp+8E0h+var_878]
0x1800ae88e  mov     ebx, [rcx+4]
0x1800ae891  test    ebx, ebx
0x1800ae893  jns     short loc_1800AE8B2
0x1800ae895  mov     edx, 8Ch; void *
0x1800ae89a  mov     r9d, ebx; char *
0x1800ae89d  mov     rcx, [rbp+7E8h]; this
0x1800ae8a4  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ae8ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae8b0  jmp     short loc_1800AE8D0
0x1800ae8b2  mov     rdx, [rbp+7E0h+arg_20]
0x1800ae8b9  call    ??$CastTo@UXvmStart@@@XvmMessage@@QEAAJPEAPEAUXvmStart@@@Z; XvmMessage::CastTo<XvmStart>(XvmStart * *)
0x1800ae8be  mov     ebx, eax
0x1800ae8c0  test    eax, eax
0x1800ae8c2  jns     short loc_1800AE8CE
0x1800ae8c4  mov     r9d, eax
0x1800ae8c7  mov     edx, 8Dh
0x1800ae8cc  jmp     short loc_1800AE89D
0x1800ae8ce  xor     ebx, ebx
0x1800ae8d0  mov     rcx, [rbp+7E0h+arg_18]
0x1800ae8d7  mov     rax, [rsp+8E0h+var_878]
0x1800ae8dc  mov     [rcx], rax
0x1800ae8df  mov     eax, ebx
0x1800ae8e1  lea     r11, [rsp+8E0h+var_10]
0x1800ae8e9  mov     rbx, [r11+28h]
0x1800ae8ed  mov     rsi, [r11+30h]
0x1800ae8f1  movaps  xmm6, xmmword ptr [r11-10h]
0x1800ae8f6  mov     rsp, r11
0x1800ae8f9  pop     r14
0x1800ae8fb  pop     rdi
0x1800ae8fc  pop     rbp
0x1800ae8fd  retn
```
