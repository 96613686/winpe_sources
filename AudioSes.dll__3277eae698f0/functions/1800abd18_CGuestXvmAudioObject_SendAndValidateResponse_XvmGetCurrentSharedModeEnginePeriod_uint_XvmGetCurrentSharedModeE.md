# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetCurrentSharedModeEnginePeriod>(uint,XvmGetCurrentSharedModeEnginePeriod,XvmMessage * *,XvmGetCurrentSharedModeEnginePeriod * *)

- ea: `0x1800abd18`
- end: `0x1800ac082`
- name: `??$SendAndValidateResponse@UXvmGetCurrentSharedModeEnginePeriod@@@CGuestXvmAudioObject@@QEAAJIUXvmGetCurrentSharedModeEnginePeriod@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `874`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800af630`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a28f0`
- `0x1800abd18`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800abd5a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800abe69`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800abd5a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800abe69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800abd8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800abd8e`

## string_xrefs

- `0x1800abd71`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800abdb0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800abfdf`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ac028`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetCurrentSharedModeEnginePeriod>(
        __int64 a1,
        unsigned int a2,
        _OWORD *a3,
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
  int CurrentSharedModeEngine; // eax
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
  _OWORD v34[3]; // [rsp+C8h] [rbp-40h] BYREF
  _OWORD v35[126]; // [rsp+F8h] [rbp-10h]
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
    v35[0] = a3[3];
    *(_OWORD *)((char *)v35 + 12) = *(_OWORD *)((char *)a3 + 60);
    v32 = 14;
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
            (unsigned int)&byte_180165D87,
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
          (unsigned int)&dword_180165C74,
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
        CurrentSharedModeEngine = XvmMessage::CastTo<XvmGetCurrentSharedModeEnginePeriod>(v21, v40, v12);
        v9 = CurrentSharedModeEngine;
        if ( CurrentSharedModeEngine >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)CurrentSharedModeEngine;
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
0x1800abd18  mov     rax, rsp
0x1800abd1b  mov     [rax+10h], rbx
0x1800abd1f  mov     [rax+18h], rsi
0x1800abd23  mov     [rax+20h], r9
0x1800abd27  push    rbp
0x1800abd28  push    rdi
0x1800abd29  push    r14
0x1800abd2b  lea     rbp, [rax-7E8h]
0x1800abd32  sub     rsp, 8D0h
0x1800abd39  movaps  xmmword ptr [rax-28h], xmm6
0x1800abd3d  mov     rsi, r8
0x1800abd40  mov     r14d, edx
0x1800abd43  mov     rbx, rcx
0x1800abd46  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800abd4e  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800abd56  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800abd5a  call    cs:__imp_QueryPerformanceCounter
0x1800abd60  mov     edi, [rbx+40h]
0x1800abd63  test    edi, edi
0x1800abd65  jns     short loc_1800ABD89
0x1800abd67  mov     rcx, [rbp+7E8h]; this
0x1800abd6e  mov     r9d, edi; char *
0x1800abd71  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800abd78  mov     edx, 4Fh ; 'O'; void *
0x1800abd7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800abd82  mov     eax, edi
0x1800abd84  jmp     loc_1800AC065
0x1800abd89  mov     ecx, 810h; cb
0x1800abd8e  call    cs:__imp_CoTaskMemAlloc
0x1800abd94  mov     rdi, rax
0x1800abd97  mov     [rsp+8E0h+var_878], rax
0x1800abd9c  test    rax, rax
0x1800abd9f  jnz     short loc_1800ABDC4
0x1800abda1  mov     rcx, [rbp+7E8h]; this
0x1800abda8  mov     ebx, 8007000Eh
0x1800abdad  mov     r9d, ebx; char *
0x1800abdb0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800abdb7  lea     edx, [rax+52h]; void *
0x1800abdba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800abdbf  jmp     loc_1800AC063
0x1800abdc4  mov     [rbp+7E0h+Src], 0
0x1800abdcc  mov     [rbp+7E0h+var_824], 0
0x1800abdd3  xor     edx, edx; Val
0x1800abdd5  mov     r8d, 800h; Size
0x1800abddb  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800abddf  call    memset_0
0x1800abde4  movups  xmm0, xmmword ptr [rsi]
0x1800abde7  movaps  [rbp+7E0h+var_820], xmm0
0x1800abdeb  movups  xmm1, xmmword ptr [rsi+10h]
0x1800abdef  movaps  [rbp+7E0h+var_810], xmm1
0x1800abdf3  movups  xmm0, xmmword ptr [rsi+20h]
0x1800abdf7  movaps  [rbp+7E0h+var_800], xmm0
0x1800abdfb  movups  xmm1, xmmword ptr [rsi+30h]
0x1800abdff  movaps  [rbp+7E0h+var_7F0], xmm1
0x1800abe03  movups  xmm0, xmmword ptr [rsi+3Ch]
0x1800abe07  movups  [rbp+7E0h+var_7F0+0Ch], xmm0
0x1800abe0b  mov     [rbp+7E0h+var_828], 0Eh
0x1800abe12  mov     rcx, rdi; void *
0x1800abe15  lea     rdx, [rbp+7E0h+Src]; Src
0x1800abe19  mov     r8d, 810h; Size
0x1800abe1f  call    memcpy_0
0x1800abe24  mov     rax, [rsp+8E0h+var_878]
0x1800abe29  mov     [rax+0Ch], r14d
0x1800abe2d  lea     rax, [rbp+7E0h+arg_18]
0x1800abe34  mov     [rbp+7E0h+var_848], rax
0x1800abe38  lea     rax, [rsp+8E0h+var_878]
0x1800abe3d  mov     [rbp+7E0h+var_840], rax
0x1800abe41  mov     [rbp+7E0h+var_838], 1
0x1800abe45  mov     rcx, [rbx+28h]
0x1800abe49  mov     rax, [rcx]
0x1800abe4c  mov     r9d, 810h
0x1800abe52  mov     r8, [rsp+8E0h+var_878]
0x1800abe57  mov     edx, r14d
0x1800abe5a  mov     rax, [rax+20h]
0x1800abe5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abe63  mov     edi, eax
0x1800abe65  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800abe69  call    cs:__imp_QueryPerformanceCounter
0x1800abe6f  xorps   xmm6, xmm6
0x1800abe72  cmp     qword ptr [rbx+48h], 0
0x1800abe77  jz      short loc_1800ABE9B
0x1800abe79  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800abe7d  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800abe81  cvtsi2ss xmm6, rcx
0x1800abe86  mulss   xmm6, cs:__real@447a0000
0x1800abe8e  xorps   xmm0, xmm0
0x1800abe91  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800abe97  divss   xmm6, xmm0
0x1800abe9b  mov     rcx, [rsp+8E0h+var_878]
0x1800abea0  cmp     dword ptr [rcx+8], 1
0x1800abea4  jnz     loc_1800ABF60
0x1800abeaa  mov     [rsp+8E0h+var_870], 0
0x1800abeb3  lea     rdx, [rsp+8E0h+var_870]
0x1800abeb8  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800abebd  test    eax, eax
0x1800abebf  js      loc_1800ABFD1
0x1800abec5  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800abeca  mov     r8, rax
0x1800abecd  mov     ecx, [rax]
0x1800abecf  cmp     ecx, 4
0x1800abed2  jbe     loc_1800ABFD1
0x1800abed8  mov     [rbp+7E0h+arg_0], edi
0x1800abede  movss   [rsp+8E0h+var_868], xmm6
0x1800abee4  mov     [rbp+7E0h+var_860], rbx
0x1800abee8  mov     rdx, [rsp+8E0h+var_870]
0x1800abeed  mov     ecx, [rdx+10h]
0x1800abef0  mov     [rsp+8E0h+var_864], ecx
0x1800abef4  mov     ecx, [rdx+4]
0x1800abef7  mov     [rsp+8E0h+var_880], ecx
0x1800abefb  mov     eax, [rdx+8]
0x1800abefe  mov     [rsp+8E0h+var_880+4], eax
0x1800abf02  mov     eax, [rdx]
0x1800abf04  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800abf08  lea     rax, [rbp+7E0h+arg_0]
0x1800abf0f  mov     [rsp+8E0h+var_890], rax
0x1800abf14  lea     rax, [rsp+8E0h+var_868]
0x1800abf19  mov     [rsp+8E0h+var_898], rax
0x1800abf1e  lea     rax, [rbp+7E0h+var_860]
0x1800abf22  mov     [rsp+8E0h+var_8A0], rax
0x1800abf27  lea     rax, [rsp+8E0h+var_864]
0x1800abf2c  mov     [rsp+8E0h+var_8A8], rax
0x1800abf31  lea     rax, [rsp+8E0h+var_880]
0x1800abf36  mov     [rsp+8E0h+var_8B0], rax
0x1800abf3b  lea     rax, [rsp+8E0h+var_880+4]
0x1800abf40  mov     [rsp+8E0h+var_8B8], rax
0x1800abf45  lea     rax, [rsp+8E0h+var_870]
0x1800abf4a  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800abf4f  lea     rdx, byte_180165D87
0x1800abf56  mov     rcx, r8
0x1800abf59  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800abf5e  jmp     short loc_1800ABFD1
0x1800abf60  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800abf65  mov     ecx, [rax]
0x1800abf67  cmp     ecx, 4
0x1800abf6a  jbe     short loc_1800ABFD1
0x1800abf6c  mov     [rbp+7E0h+arg_0], edi
0x1800abf72  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800abf78  mov     [rbp+7E0h+var_860], rbx
0x1800abf7c  mov     rcx, [rsp+8E0h+var_878]
0x1800abf81  mov     edx, [rcx+8]
0x1800abf84  mov     [rsp+8E0h+var_880+4], edx
0x1800abf88  mov     ecx, [rbx+30h]
0x1800abf8b  mov     [rsp+8E0h+var_880], ecx
0x1800abf8f  lea     rcx, [rbp+7E0h+arg_0]
0x1800abf96  mov     [rsp+8E0h+var_8A0], rcx
0x1800abf9b  lea     rcx, [rsp+8E0h+var_870]
0x1800abfa0  mov     [rsp+8E0h+var_8A8], rcx
0x1800abfa5  lea     rcx, [rbp+7E0h+var_860]
0x1800abfa9  mov     [rsp+8E0h+var_8B0], rcx
0x1800abfae  lea     rcx, [rsp+8E0h+var_880+4]
0x1800abfb3  mov     [rsp+8E0h+var_8B8], rcx
0x1800abfb8  lea     rcx, [rsp+8E0h+var_880]
0x1800abfbd  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800abfc2  lea     rdx, dword_180165C74
0x1800abfc9  mov     rcx, rax
0x1800abfcc  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800abfd1  mov     rcx, [rbp+7E8h]; this
0x1800abfd8  test    edi, edi
0x1800abfda  jns     short loc_1800ABFFF
0x1800abfdc  mov     r9d, edi; char *
0x1800abfdf  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800abfe6  mov     edx, 81h; void *
0x1800abfeb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800abff0  mov     rax, [rbx]
0x1800abff3  mov     rcx, rbx
0x1800abff6  mov     rax, [rax+20h]
0x1800abffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800abfff  mov     ebx, [rbx+40h]
0x1800ac002  test    ebx, ebx
0x1800ac004  jns     short loc_1800AC00D
0x1800ac006  mov     edx, 8Ah
0x1800ac00b  jmp     short loc_1800AC01E
0x1800ac00d  mov     rcx, [rsp+8E0h+var_878]
0x1800ac012  mov     ebx, [rcx+4]
0x1800ac015  test    ebx, ebx
0x1800ac017  jns     short loc_1800AC036
0x1800ac019  mov     edx, 8Ch; void *
0x1800ac01e  mov     r9d, ebx; char *
0x1800ac021  mov     rcx, [rbp+7E8h]; this
0x1800ac028  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ac02f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac034  jmp     short loc_1800AC054
0x1800ac036  mov     rdx, [rbp+7E0h+arg_20]
0x1800ac03d  call    ??$CastTo@UXvmGetCurrentSharedModeEnginePeriod@@@XvmMessage@@QEAAJPEAPEAUXvmGetCurrentSharedModeEnginePeriod@@@Z; XvmMessage::CastTo<XvmGetCurrentSharedModeEnginePeriod>(XvmGetCurrentSharedModeEnginePeriod * *)
0x1800ac042  mov     ebx, eax
0x1800ac044  test    eax, eax
0x1800ac046  jns     short loc_1800AC052
0x1800ac048  mov     r9d, eax
0x1800ac04b  mov     edx, 8Dh
0x1800ac050  jmp     short loc_1800AC021
0x1800ac052  xor     ebx, ebx
0x1800ac054  mov     rcx, [rbp+7E0h+arg_18]
0x1800ac05b  mov     rax, [rsp+8E0h+var_878]
0x1800ac060  mov     [rcx], rax
0x1800ac063  mov     eax, ebx
0x1800ac065  lea     r11, [rsp+8E0h+var_10]
0x1800ac06d  mov     rbx, [r11+28h]
0x1800ac071  mov     rsi, [r11+30h]
0x1800ac075  movaps  xmm6, xmmword ptr [r11-10h]
0x1800ac07a  mov     rsp, r11
0x1800ac07d  pop     r14
0x1800ac07f  pop     rdi
0x1800ac080  pop     rbp
0x1800ac081  retn
```
