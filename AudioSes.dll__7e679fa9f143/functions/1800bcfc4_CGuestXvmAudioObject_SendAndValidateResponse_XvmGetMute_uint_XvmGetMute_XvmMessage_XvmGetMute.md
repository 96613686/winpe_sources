# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetMute>(uint,XvmGetMute,XvmMessage * *,XvmGetMute * *)

- ea: `0x1800bcfc4`
- end: `0x1800bd30a`
- name: `??$SendAndValidateResponse@UXvmGetMute@@@CGuestXvmAudioObject@@QEAAJIUXvmGetMute@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c0a90`
- `0x1800c0b80`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2a70`
- `0x1800bcfc4`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd006`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd0f1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd006`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bd0f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bd03a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bd03a`

## string_xrefs

- `0x1800bd01d`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bd05c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bd267`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bd2b0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetMute>(__int64 a1, unsigned int a2, char a3, ...)
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
    v32 = 23;
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
            (unsigned int)&unk_1801687AA,
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
          (unsigned int)&unk_180168823,
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
        v18 = XvmMessage::CastTo<XvmGetMute>(v21, v39, v12);
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
0x1800bcfc4  mov     rax, rsp
0x1800bcfc7  mov     [rax+10h], rbx
0x1800bcfcb  mov     [rax+18h], rsi
0x1800bcfcf  mov     [rax+20h], r9
0x1800bcfd3  push    rbp
0x1800bcfd4  push    rdi
0x1800bcfd5  push    r14
0x1800bcfd7  lea     rbp, [rax-7E8h]
0x1800bcfde  sub     rsp, 8D0h
0x1800bcfe5  movaps  xmmword ptr [rax-28h], xmm6
0x1800bcfe9  mov     bl, r8b
0x1800bcfec  mov     r14d, edx
0x1800bcfef  mov     rdi, rcx
0x1800bcff2  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bcffa  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800bd002  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800bd006  call    cs:__imp_QueryPerformanceCounter
0x1800bd00c  mov     esi, [rdi+40h]
0x1800bd00f  test    esi, esi
0x1800bd011  jns     short loc_1800BD035
0x1800bd013  mov     rcx, [rbp+7E8h]; this
0x1800bd01a  mov     r9d, esi; char *
0x1800bd01d  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bd024  mov     edx, 4Fh ; 'O'; void *
0x1800bd029  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd02e  mov     eax, esi
0x1800bd030  jmp     loc_1800BD2ED
0x1800bd035  mov     ecx, 810h; cb
0x1800bd03a  call    cs:__imp_CoTaskMemAlloc
0x1800bd040  mov     rsi, rax
0x1800bd043  mov     [rsp+8E0h+var_878], rax
0x1800bd048  test    rax, rax
0x1800bd04b  jnz     short loc_1800BD070
0x1800bd04d  mov     rcx, [rbp+7E8h]; this
0x1800bd054  mov     ebx, 8007000Eh
0x1800bd059  mov     r9d, ebx; char *
0x1800bd05c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bd063  lea     edx, [rax+52h]; void *
0x1800bd066  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd06b  jmp     loc_1800BD2EB
0x1800bd070  mov     [rbp+7E0h+Src], 0
0x1800bd078  mov     [rbp+7E0h+var_824], 0
0x1800bd07f  xor     edx, edx; Val
0x1800bd081  mov     r8d, 800h; Size
0x1800bd087  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bd08b  call    memset_0
0x1800bd090  mov     [rbp+7E0h+var_820], bl
0x1800bd093  mov     [rbp+7E0h+var_828], 17h
0x1800bd09a  mov     rcx, rsi; void *
0x1800bd09d  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bd0a1  mov     r8d, 810h; Size
0x1800bd0a7  call    memcpy_0
0x1800bd0ac  mov     rax, [rsp+8E0h+var_878]
0x1800bd0b1  mov     [rax+0Ch], r14d
0x1800bd0b5  lea     rax, [rbp+7E0h+arg_18]
0x1800bd0bc  mov     [rbp+7E0h+var_848], rax
0x1800bd0c0  lea     rax, [rsp+8E0h+var_878]
0x1800bd0c5  mov     [rbp+7E0h+var_840], rax
0x1800bd0c9  mov     [rbp+7E0h+var_838], 1
0x1800bd0cd  mov     rcx, [rdi+28h]
0x1800bd0d1  mov     rax, [rcx]
0x1800bd0d4  mov     r9d, 810h
0x1800bd0da  mov     r8, [rsp+8E0h+var_878]
0x1800bd0df  mov     edx, r14d
0x1800bd0e2  mov     rax, [rax+20h]
0x1800bd0e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd0eb  mov     ebx, eax
0x1800bd0ed  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800bd0f1  call    cs:__imp_QueryPerformanceCounter
0x1800bd0f7  xorps   xmm6, xmm6
0x1800bd0fa  cmp     qword ptr [rdi+48h], 0
0x1800bd0ff  jz      short loc_1800BD123
0x1800bd101  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800bd105  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800bd109  cvtsi2ss xmm6, rcx
0x1800bd10e  mulss   xmm6, cs:__real@447a0000
0x1800bd116  xorps   xmm0, xmm0
0x1800bd119  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800bd11f  divss   xmm6, xmm0
0x1800bd123  mov     rcx, [rsp+8E0h+var_878]
0x1800bd128  cmp     dword ptr [rcx+8], 1
0x1800bd12c  jnz     loc_1800BD1E8
0x1800bd132  mov     [rsp+8E0h+var_870], 0
0x1800bd13b  lea     rdx, [rsp+8E0h+var_870]
0x1800bd140  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bd145  test    eax, eax
0x1800bd147  js      loc_1800BD259
0x1800bd14d  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bd152  mov     r8, rax
0x1800bd155  mov     ecx, [rax]
0x1800bd157  cmp     ecx, 4
0x1800bd15a  jbe     loc_1800BD259
0x1800bd160  mov     [rbp+7E0h+arg_0], ebx
0x1800bd166  movss   [rsp+8E0h+var_868], xmm6
0x1800bd16c  mov     [rbp+7E0h+var_860], rdi
0x1800bd170  mov     rdx, [rsp+8E0h+var_870]
0x1800bd175  mov     ecx, [rdx+10h]
0x1800bd178  mov     [rsp+8E0h+var_864], ecx
0x1800bd17c  mov     ecx, [rdx+4]
0x1800bd17f  mov     [rsp+8E0h+var_880], ecx
0x1800bd183  mov     eax, [rdx+8]
0x1800bd186  mov     [rsp+8E0h+var_880+4], eax
0x1800bd18a  mov     eax, [rdx]
0x1800bd18c  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800bd190  lea     rax, [rbp+7E0h+arg_0]
0x1800bd197  mov     [rsp+8E0h+var_890], rax
0x1800bd19c  lea     rax, [rsp+8E0h+var_868]
0x1800bd1a1  mov     [rsp+8E0h+var_898], rax
0x1800bd1a6  lea     rax, [rbp+7E0h+var_860]
0x1800bd1aa  mov     [rsp+8E0h+var_8A0], rax
0x1800bd1af  lea     rax, [rsp+8E0h+var_864]
0x1800bd1b4  mov     [rsp+8E0h+var_8A8], rax
0x1800bd1b9  lea     rax, [rsp+8E0h+var_880]
0x1800bd1be  mov     [rsp+8E0h+var_8B0], rax
0x1800bd1c3  lea     rax, [rsp+8E0h+var_880+4]
0x1800bd1c8  mov     [rsp+8E0h+var_8B8], rax
0x1800bd1cd  lea     rax, [rsp+8E0h+var_870]
0x1800bd1d2  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bd1d7  lea     rdx, unk_1801687AA
0x1800bd1de  mov     rcx, r8
0x1800bd1e1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bd1e6  jmp     short loc_1800BD259
0x1800bd1e8  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bd1ed  mov     ecx, [rax]
0x1800bd1ef  cmp     ecx, 4
0x1800bd1f2  jbe     short loc_1800BD259
0x1800bd1f4  mov     [rbp+7E0h+arg_0], ebx
0x1800bd1fa  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bd200  mov     [rbp+7E0h+var_860], rdi
0x1800bd204  mov     rcx, [rsp+8E0h+var_878]
0x1800bd209  mov     edx, [rcx+8]
0x1800bd20c  mov     [rsp+8E0h+var_880+4], edx
0x1800bd210  mov     ecx, [rdi+30h]
0x1800bd213  mov     [rsp+8E0h+var_880], ecx
0x1800bd217  lea     rcx, [rbp+7E0h+arg_0]
0x1800bd21e  mov     [rsp+8E0h+var_8A0], rcx
0x1800bd223  lea     rcx, [rsp+8E0h+var_870]
0x1800bd228  mov     [rsp+8E0h+var_8A8], rcx
0x1800bd22d  lea     rcx, [rbp+7E0h+var_860]
0x1800bd231  mov     [rsp+8E0h+var_8B0], rcx
0x1800bd236  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bd23b  mov     [rsp+8E0h+var_8B8], rcx
0x1800bd240  lea     rcx, [rsp+8E0h+var_880]
0x1800bd245  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bd24a  lea     rdx, unk_180168823
0x1800bd251  mov     rcx, rax
0x1800bd254  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bd259  mov     rcx, [rbp+7E8h]; this
0x1800bd260  test    ebx, ebx
0x1800bd262  jns     short loc_1800BD287
0x1800bd264  mov     r9d, ebx; char *
0x1800bd267  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bd26e  mov     edx, 81h; void *
0x1800bd273  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bd278  mov     rax, [rdi]
0x1800bd27b  mov     rcx, rdi
0x1800bd27e  mov     rax, [rax+20h]
0x1800bd282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd287  mov     ebx, [rdi+40h]
0x1800bd28a  test    ebx, ebx
0x1800bd28c  jns     short loc_1800BD295
0x1800bd28e  mov     edx, 8Ah
0x1800bd293  jmp     short loc_1800BD2A6
0x1800bd295  mov     rcx, [rsp+8E0h+var_878]
0x1800bd29a  mov     ebx, [rcx+4]
0x1800bd29d  test    ebx, ebx
0x1800bd29f  jns     short loc_1800BD2BE
0x1800bd2a1  mov     edx, 8Ch; void *
0x1800bd2a6  mov     r9d, ebx; char *
0x1800bd2a9  mov     rcx, [rbp+7E8h]; this
0x1800bd2b0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bd2b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bd2bc  jmp     short loc_1800BD2DC
0x1800bd2be  mov     rdx, [rbp+7E0h+arg_20]
0x1800bd2c5  call    ??$CastTo@UXvmGetMute@@@XvmMessage@@QEAAJPEAPEAUXvmGetMute@@@Z; XvmMessage::CastTo<XvmGetMute>(XvmGetMute * *)
0x1800bd2ca  mov     ebx, eax
0x1800bd2cc  test    eax, eax
0x1800bd2ce  jns     short loc_1800BD2DA
0x1800bd2d0  mov     r9d, eax
0x1800bd2d3  mov     edx, 8Dh
0x1800bd2d8  jmp     short loc_1800BD2A9
0x1800bd2da  xor     ebx, ebx
0x1800bd2dc  mov     rcx, [rbp+7E0h+arg_18]
0x1800bd2e3  mov     rax, [rsp+8E0h+var_878]
0x1800bd2e8  mov     [rcx], rax
0x1800bd2eb  mov     eax, ebx
0x1800bd2ed  lea     r11, [rsp+8E0h+var_10]
0x1800bd2f5  mov     rbx, [r11+28h]
0x1800bd2f9  mov     rsi, [r11+30h]
0x1800bd2fd  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bd302  mov     rsp, r11
0x1800bd305  pop     r14
0x1800bd307  pop     rdi
0x1800bd308  pop     rbp
0x1800bd309  retn
```
