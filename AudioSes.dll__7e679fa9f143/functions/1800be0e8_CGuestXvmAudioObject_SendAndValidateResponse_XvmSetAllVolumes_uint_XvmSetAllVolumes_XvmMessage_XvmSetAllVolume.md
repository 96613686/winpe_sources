# CGuestXvmAudioObject::SendAndValidateResponse<XvmSetAllVolumes>(uint,XvmSetAllVolumes,XvmMessage * *,XvmSetAllVolumes * *)

- ea: `0x1800be0e8`
- end: `0x1800be4a1`
- name: `??$SendAndValidateResponse@UXvmSetAllVolumes@@@CGuestXvmAudioObject@@QEAAJIUXvmSetAllVolumes@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `953`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c1ba0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2d28`
- `0x1800be0e8`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800be12a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800be288`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800be12a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800be288`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be15e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be15e`

## string_xrefs

- `0x1800be141`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800be180`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800be3fe`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800be447`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmSetAllVolumes>(__int64 a1, unsigned int a2, _OWORD *a3, ...)
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
  _OWORD v34[11]; // [rsp+C8h] [rbp-40h] BYREF
  _OWORD v35[118]; // [rsp+178h] [rbp+70h]
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
    v34[0] = *a3;
    v34[1] = a3[1];
    v34[2] = a3[2];
    v34[3] = a3[3];
    v34[4] = a3[4];
    v34[5] = a3[5];
    v34[6] = a3[6];
    v34[7] = a3[7];
    v34[8] = a3[8];
    v34[9] = a3[9];
    v34[10] = a3[10];
    v35[0] = a3[11];
    *(_OWORD *)((char *)v35 + 12) = *(_OWORD *)((char *)a3 + 188);
    v32 = 19;
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
            (unsigned int)&unk_180168492,
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
          (unsigned int)&unk_18016850B,
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
        v18 = XvmMessage::CastTo<XvmSetAllVolumes>(v21, v40, v12);
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
0x1800be0e8  mov     rax, rsp
0x1800be0eb  mov     [rax+10h], rbx
0x1800be0ef  mov     [rax+18h], rsi
0x1800be0f3  mov     [rax+20h], r9
0x1800be0f7  push    rbp
0x1800be0f8  push    rdi
0x1800be0f9  push    r14
0x1800be0fb  lea     rbp, [rax-7E8h]
0x1800be102  sub     rsp, 8D0h
0x1800be109  movaps  xmmword ptr [rax-28h], xmm6
0x1800be10d  mov     rsi, r8
0x1800be110  mov     r14d, edx
0x1800be113  mov     rbx, rcx
0x1800be116  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800be11e  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800be126  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800be12a  call    cs:__imp_QueryPerformanceCounter
0x1800be130  mov     edi, [rbx+40h]
0x1800be133  test    edi, edi
0x1800be135  jns     short loc_1800BE159
0x1800be137  mov     rcx, [rbp+7E8h]; this
0x1800be13e  mov     r9d, edi; char *
0x1800be141  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800be148  mov     edx, 4Fh ; 'O'; void *
0x1800be14d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be152  mov     eax, edi
0x1800be154  jmp     loc_1800BE484
0x1800be159  mov     ecx, 810h; cb
0x1800be15e  call    cs:__imp_CoTaskMemAlloc
0x1800be164  mov     rdi, rax
0x1800be167  mov     [rsp+8E0h+var_878], rax
0x1800be16c  test    rax, rax
0x1800be16f  jnz     short loc_1800BE194
0x1800be171  mov     rcx, [rbp+7E8h]; this
0x1800be178  mov     ebx, 8007000Eh
0x1800be17d  mov     r9d, ebx; char *
0x1800be180  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800be187  lea     edx, [rax+52h]; void *
0x1800be18a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be18f  jmp     loc_1800BE482
0x1800be194  mov     [rbp+7E0h+Src], 0
0x1800be19c  mov     [rbp+7E0h+var_824], 0
0x1800be1a3  xor     edx, edx; Val
0x1800be1a5  mov     r8d, 800h; Size
0x1800be1ab  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800be1af  call    memset_0
0x1800be1b4  movups  xmm0, xmmword ptr [rsi]
0x1800be1b7  movups  [rbp+7E0h+var_820], xmm0
0x1800be1bb  movups  xmm1, xmmword ptr [rsi+10h]
0x1800be1bf  movups  [rbp+7E0h+var_810], xmm1
0x1800be1c3  movups  xmm0, xmmword ptr [rsi+20h]
0x1800be1c7  movups  [rbp+7E0h+var_800], xmm0
0x1800be1cb  movups  xmm1, xmmword ptr [rsi+30h]
0x1800be1cf  movups  [rbp+7E0h+var_7F0], xmm1
0x1800be1d3  movups  xmm0, xmmword ptr [rsi+40h]
0x1800be1d7  movups  [rbp+7E0h+var_7E0], xmm0
0x1800be1db  movups  xmm1, xmmword ptr [rsi+50h]
0x1800be1df  movups  [rbp+7E0h+var_7D0], xmm1
0x1800be1e3  movups  xmm0, xmmword ptr [rsi+60h]
0x1800be1e7  movups  [rbp+7E0h+var_7C0], xmm0
0x1800be1eb  movups  xmm1, xmmword ptr [rsi+70h]
0x1800be1ef  movups  [rbp+7E0h+var_7B0], xmm1
0x1800be1f3  movups  xmm0, xmmword ptr [rsi+80h]
0x1800be1fa  movups  [rbp+7E0h+var_7A0], xmm0
0x1800be1fe  movups  xmm1, xmmword ptr [rsi+90h]
0x1800be205  movups  [rbp+7E0h+var_790], xmm1
0x1800be209  movups  xmm0, xmmword ptr [rsi+0A0h]
0x1800be210  movups  [rbp+7E0h+var_780], xmm0
0x1800be214  movups  xmm1, xmmword ptr [rsi+0B0h]
0x1800be21b  movups  [rbp+7E0h+var_770], xmm1
0x1800be21f  movups  xmm0, xmmword ptr [rsi+0BCh]
0x1800be226  movups  [rbp+7E0h+var_770+0Ch], xmm0
0x1800be22a  mov     [rbp+7E0h+var_828], 13h
0x1800be231  mov     rcx, rdi; void *
0x1800be234  lea     rdx, [rbp+7E0h+Src]; Src
0x1800be238  mov     r8d, 810h; Size
0x1800be23e  call    memcpy_0
0x1800be243  mov     rax, [rsp+8E0h+var_878]
0x1800be248  mov     [rax+0Ch], r14d
0x1800be24c  lea     rax, [rbp+7E0h+arg_18]
0x1800be253  mov     [rbp+7E0h+var_848], rax
0x1800be257  lea     rax, [rsp+8E0h+var_878]
0x1800be25c  mov     [rbp+7E0h+var_840], rax
0x1800be260  mov     [rbp+7E0h+var_838], 1
0x1800be264  mov     rcx, [rbx+28h]
0x1800be268  mov     rax, [rcx]
0x1800be26b  mov     r9d, 810h
0x1800be271  mov     r8, [rsp+8E0h+var_878]
0x1800be276  mov     edx, r14d
0x1800be279  mov     rax, [rax+20h]
0x1800be27d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be282  mov     edi, eax
0x1800be284  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800be288  call    cs:__imp_QueryPerformanceCounter
0x1800be28e  xorps   xmm6, xmm6
0x1800be291  cmp     qword ptr [rbx+48h], 0
0x1800be296  jz      short loc_1800BE2BA
0x1800be298  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800be29c  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800be2a0  cvtsi2ss xmm6, rcx
0x1800be2a5  mulss   xmm6, cs:__real@447a0000
0x1800be2ad  xorps   xmm0, xmm0
0x1800be2b0  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800be2b6  divss   xmm6, xmm0
0x1800be2ba  mov     rcx, [rsp+8E0h+var_878]
0x1800be2bf  cmp     dword ptr [rcx+8], 1
0x1800be2c3  jnz     loc_1800BE37F
0x1800be2c9  mov     [rsp+8E0h+var_870], 0
0x1800be2d2  lea     rdx, [rsp+8E0h+var_870]
0x1800be2d7  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800be2dc  test    eax, eax
0x1800be2de  js      loc_1800BE3F0
0x1800be2e4  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800be2e9  mov     r8, rax
0x1800be2ec  mov     ecx, [rax]
0x1800be2ee  cmp     ecx, 4
0x1800be2f1  jbe     loc_1800BE3F0
0x1800be2f7  mov     [rbp+7E0h+arg_0], edi
0x1800be2fd  movss   [rsp+8E0h+var_868], xmm6
0x1800be303  mov     [rbp+7E0h+var_860], rbx
0x1800be307  mov     rdx, [rsp+8E0h+var_870]
0x1800be30c  mov     ecx, [rdx+10h]
0x1800be30f  mov     [rsp+8E0h+var_864], ecx
0x1800be313  mov     ecx, [rdx+4]
0x1800be316  mov     [rsp+8E0h+var_880], ecx
0x1800be31a  mov     eax, [rdx+8]
0x1800be31d  mov     [rsp+8E0h+var_880+4], eax
0x1800be321  mov     eax, [rdx]
0x1800be323  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800be327  lea     rax, [rbp+7E0h+arg_0]
0x1800be32e  mov     [rsp+8E0h+var_890], rax
0x1800be333  lea     rax, [rsp+8E0h+var_868]
0x1800be338  mov     [rsp+8E0h+var_898], rax
0x1800be33d  lea     rax, [rbp+7E0h+var_860]
0x1800be341  mov     [rsp+8E0h+var_8A0], rax
0x1800be346  lea     rax, [rsp+8E0h+var_864]
0x1800be34b  mov     [rsp+8E0h+var_8A8], rax
0x1800be350  lea     rax, [rsp+8E0h+var_880]
0x1800be355  mov     [rsp+8E0h+var_8B0], rax
0x1800be35a  lea     rax, [rsp+8E0h+var_880+4]
0x1800be35f  mov     [rsp+8E0h+var_8B8], rax
0x1800be364  lea     rax, [rsp+8E0h+var_870]
0x1800be369  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800be36e  lea     rdx, unk_180168492
0x1800be375  mov     rcx, r8
0x1800be378  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800be37d  jmp     short loc_1800BE3F0
0x1800be37f  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800be384  mov     ecx, [rax]
0x1800be386  cmp     ecx, 4
0x1800be389  jbe     short loc_1800BE3F0
0x1800be38b  mov     [rbp+7E0h+arg_0], edi
0x1800be391  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800be397  mov     [rbp+7E0h+var_860], rbx
0x1800be39b  mov     rcx, [rsp+8E0h+var_878]
0x1800be3a0  mov     edx, [rcx+8]
0x1800be3a3  mov     [rsp+8E0h+var_880+4], edx
0x1800be3a7  mov     ecx, [rbx+30h]
0x1800be3aa  mov     [rsp+8E0h+var_880], ecx
0x1800be3ae  lea     rcx, [rbp+7E0h+arg_0]
0x1800be3b5  mov     [rsp+8E0h+var_8A0], rcx
0x1800be3ba  lea     rcx, [rsp+8E0h+var_870]
0x1800be3bf  mov     [rsp+8E0h+var_8A8], rcx
0x1800be3c4  lea     rcx, [rbp+7E0h+var_860]
0x1800be3c8  mov     [rsp+8E0h+var_8B0], rcx
0x1800be3cd  lea     rcx, [rsp+8E0h+var_880+4]
0x1800be3d2  mov     [rsp+8E0h+var_8B8], rcx
0x1800be3d7  lea     rcx, [rsp+8E0h+var_880]
0x1800be3dc  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800be3e1  lea     rdx, unk_18016850B
0x1800be3e8  mov     rcx, rax
0x1800be3eb  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800be3f0  mov     rcx, [rbp+7E8h]; this
0x1800be3f7  test    edi, edi
0x1800be3f9  jns     short loc_1800BE41E
0x1800be3fb  mov     r9d, edi; char *
0x1800be3fe  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800be405  mov     edx, 81h; void *
0x1800be40a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800be40f  mov     rax, [rbx]
0x1800be412  mov     rcx, rbx
0x1800be415  mov     rax, [rax+20h]
0x1800be419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be41e  mov     ebx, [rbx+40h]
0x1800be421  test    ebx, ebx
0x1800be423  jns     short loc_1800BE42C
0x1800be425  mov     edx, 8Ah
0x1800be42a  jmp     short loc_1800BE43D
0x1800be42c  mov     rcx, [rsp+8E0h+var_878]
0x1800be431  mov     ebx, [rcx+4]
0x1800be434  test    ebx, ebx
0x1800be436  jns     short loc_1800BE455
0x1800be438  mov     edx, 8Ch; void *
0x1800be43d  mov     r9d, ebx; char *
0x1800be440  mov     rcx, [rbp+7E8h]; this
0x1800be447  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800be44e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be453  jmp     short loc_1800BE473
0x1800be455  mov     rdx, [rbp+7E0h+arg_20]
0x1800be45c  call    ??$CastTo@UXvmSetAllVolumes@@@XvmMessage@@QEAAJPEAPEAUXvmSetAllVolumes@@@Z; XvmMessage::CastTo<XvmSetAllVolumes>(XvmSetAllVolumes * *)
0x1800be461  mov     ebx, eax
0x1800be463  test    eax, eax
0x1800be465  jns     short loc_1800BE471
0x1800be467  mov     r9d, eax
0x1800be46a  mov     edx, 8Dh
0x1800be46f  jmp     short loc_1800BE440
0x1800be471  xor     ebx, ebx
0x1800be473  mov     rcx, [rbp+7E0h+arg_18]
0x1800be47a  mov     rax, [rsp+8E0h+var_878]
0x1800be47f  mov     [rcx], rax
0x1800be482  mov     eax, ebx
0x1800be484  lea     r11, [rsp+8E0h+var_10]
0x1800be48c  mov     rbx, [r11+28h]
0x1800be490  mov     rsi, [r11+30h]
0x1800be494  movaps  xmm6, xmmword ptr [r11-10h]
0x1800be499  mov     rsp, r11
0x1800be49c  pop     r14
0x1800be49e  pop     rdi
0x1800be49f  pop     rbp
0x1800be4a0  retn
```
