# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetState>(uint,XvmGetState,XvmMessage * *,XvmGetState * *)

- ea: `0x1800bda50`
- end: `0x1800bdd96`
- name: `??$SendAndValidateResponse@UXvmGetState@@@CGuestXvmAudioObject@@QEAAJIUXvmGetState@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c1130`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800b9528`
- `0x1800bda50`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bda92`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bdb7d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bda92`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bdb7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bdac6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bdac6`

## string_xrefs

- `0x1800bdaa9`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bdae8`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bdcf3`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bdd3c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetState>(__int64 a1, unsigned int a2, int a3, ...)
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
  _DWORD v34[516]; // [rsp+C8h] [rbp-40h] BYREF
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
    v32 = 25;
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
            (unsigned int)&word_180168306,
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
          (unsigned int)&byte_18016837F,
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
        v18 = XvmMessage::CastTo<XvmGetState>(v21, v39, v12);
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
0x1800bda50  mov     rax, rsp
0x1800bda53  mov     [rax+10h], rbx
0x1800bda57  mov     [rax+18h], rsi
0x1800bda5b  mov     [rax+20h], r9
0x1800bda5f  push    rbp
0x1800bda60  push    rdi
0x1800bda61  push    r14
0x1800bda63  lea     rbp, [rax-7E8h]
0x1800bda6a  sub     rsp, 8D0h
0x1800bda71  movaps  xmmword ptr [rax-28h], xmm6
0x1800bda75  mov     ebx, r8d
0x1800bda78  mov     r14d, edx
0x1800bda7b  mov     rdi, rcx
0x1800bda7e  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bda86  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800bda8e  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800bda92  call    cs:__imp_QueryPerformanceCounter
0x1800bda98  mov     esi, [rdi+40h]
0x1800bda9b  test    esi, esi
0x1800bda9d  jns     short loc_1800BDAC1
0x1800bda9f  mov     rcx, [rbp+7E8h]; this
0x1800bdaa6  mov     r9d, esi; char *
0x1800bdaa9  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bdab0  mov     edx, 4Fh ; 'O'; void *
0x1800bdab5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdaba  mov     eax, esi
0x1800bdabc  jmp     loc_1800BDD79
0x1800bdac1  mov     ecx, 810h; cb
0x1800bdac6  call    cs:__imp_CoTaskMemAlloc
0x1800bdacc  mov     rsi, rax
0x1800bdacf  mov     [rsp+8E0h+var_878], rax
0x1800bdad4  test    rax, rax
0x1800bdad7  jnz     short loc_1800BDAFC
0x1800bdad9  mov     rcx, [rbp+7E8h]; this
0x1800bdae0  mov     ebx, 8007000Eh
0x1800bdae5  mov     r9d, ebx; char *
0x1800bdae8  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bdaef  lea     edx, [rax+52h]; void *
0x1800bdaf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdaf7  jmp     loc_1800BDD77
0x1800bdafc  mov     [rbp+7E0h+Src], 0
0x1800bdb04  mov     [rbp+7E0h+var_824], 0
0x1800bdb0b  xor     edx, edx; Val
0x1800bdb0d  mov     r8d, 800h; Size
0x1800bdb13  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bdb17  call    memset_0
0x1800bdb1c  mov     [rbp+7E0h+var_820], ebx
0x1800bdb1f  mov     [rbp+7E0h+var_828], 19h
0x1800bdb26  mov     rcx, rsi; void *
0x1800bdb29  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bdb2d  mov     r8d, 810h; Size
0x1800bdb33  call    memcpy_0
0x1800bdb38  mov     rax, [rsp+8E0h+var_878]
0x1800bdb3d  mov     [rax+0Ch], r14d
0x1800bdb41  lea     rax, [rbp+7E0h+arg_18]
0x1800bdb48  mov     [rbp+7E0h+var_848], rax
0x1800bdb4c  lea     rax, [rsp+8E0h+var_878]
0x1800bdb51  mov     [rbp+7E0h+var_840], rax
0x1800bdb55  mov     [rbp+7E0h+var_838], 1
0x1800bdb59  mov     rcx, [rdi+28h]
0x1800bdb5d  mov     rax, [rcx]
0x1800bdb60  mov     r9d, 810h
0x1800bdb66  mov     r8, [rsp+8E0h+var_878]
0x1800bdb6b  mov     edx, r14d
0x1800bdb6e  mov     rax, [rax+20h]
0x1800bdb72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdb77  mov     ebx, eax
0x1800bdb79  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800bdb7d  call    cs:__imp_QueryPerformanceCounter
0x1800bdb83  xorps   xmm6, xmm6
0x1800bdb86  cmp     qword ptr [rdi+48h], 0
0x1800bdb8b  jz      short loc_1800BDBAF
0x1800bdb8d  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800bdb91  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800bdb95  cvtsi2ss xmm6, rcx
0x1800bdb9a  mulss   xmm6, cs:__real@447a0000
0x1800bdba2  xorps   xmm0, xmm0
0x1800bdba5  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800bdbab  divss   xmm6, xmm0
0x1800bdbaf  mov     rcx, [rsp+8E0h+var_878]
0x1800bdbb4  cmp     dword ptr [rcx+8], 1
0x1800bdbb8  jnz     loc_1800BDC74
0x1800bdbbe  mov     [rsp+8E0h+var_870], 0
0x1800bdbc7  lea     rdx, [rsp+8E0h+var_870]
0x1800bdbcc  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bdbd1  test    eax, eax
0x1800bdbd3  js      loc_1800BDCE5
0x1800bdbd9  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bdbde  mov     r8, rax
0x1800bdbe1  mov     ecx, [rax]
0x1800bdbe3  cmp     ecx, 4
0x1800bdbe6  jbe     loc_1800BDCE5
0x1800bdbec  mov     [rbp+7E0h+arg_0], ebx
0x1800bdbf2  movss   [rsp+8E0h+var_868], xmm6
0x1800bdbf8  mov     [rbp+7E0h+var_860], rdi
0x1800bdbfc  mov     rdx, [rsp+8E0h+var_870]
0x1800bdc01  mov     ecx, [rdx+10h]
0x1800bdc04  mov     [rsp+8E0h+var_864], ecx
0x1800bdc08  mov     ecx, [rdx+4]
0x1800bdc0b  mov     [rsp+8E0h+var_880], ecx
0x1800bdc0f  mov     eax, [rdx+8]
0x1800bdc12  mov     [rsp+8E0h+var_880+4], eax
0x1800bdc16  mov     eax, [rdx]
0x1800bdc18  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800bdc1c  lea     rax, [rbp+7E0h+arg_0]
0x1800bdc23  mov     [rsp+8E0h+var_890], rax
0x1800bdc28  lea     rax, [rsp+8E0h+var_868]
0x1800bdc2d  mov     [rsp+8E0h+var_898], rax
0x1800bdc32  lea     rax, [rbp+7E0h+var_860]
0x1800bdc36  mov     [rsp+8E0h+var_8A0], rax
0x1800bdc3b  lea     rax, [rsp+8E0h+var_864]
0x1800bdc40  mov     [rsp+8E0h+var_8A8], rax
0x1800bdc45  lea     rax, [rsp+8E0h+var_880]
0x1800bdc4a  mov     [rsp+8E0h+var_8B0], rax
0x1800bdc4f  lea     rax, [rsp+8E0h+var_880+4]
0x1800bdc54  mov     [rsp+8E0h+var_8B8], rax
0x1800bdc59  lea     rax, [rsp+8E0h+var_870]
0x1800bdc5e  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bdc63  lea     rdx, word_180168306
0x1800bdc6a  mov     rcx, r8
0x1800bdc6d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bdc72  jmp     short loc_1800BDCE5
0x1800bdc74  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bdc79  mov     ecx, [rax]
0x1800bdc7b  cmp     ecx, 4
0x1800bdc7e  jbe     short loc_1800BDCE5
0x1800bdc80  mov     [rbp+7E0h+arg_0], ebx
0x1800bdc86  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bdc8c  mov     [rbp+7E0h+var_860], rdi
0x1800bdc90  mov     rcx, [rsp+8E0h+var_878]
0x1800bdc95  mov     edx, [rcx+8]
0x1800bdc98  mov     [rsp+8E0h+var_880+4], edx
0x1800bdc9c  mov     ecx, [rdi+30h]
0x1800bdc9f  mov     [rsp+8E0h+var_880], ecx
0x1800bdca3  lea     rcx, [rbp+7E0h+arg_0]
0x1800bdcaa  mov     [rsp+8E0h+var_8A0], rcx
0x1800bdcaf  lea     rcx, [rsp+8E0h+var_870]
0x1800bdcb4  mov     [rsp+8E0h+var_8A8], rcx
0x1800bdcb9  lea     rcx, [rbp+7E0h+var_860]
0x1800bdcbd  mov     [rsp+8E0h+var_8B0], rcx
0x1800bdcc2  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bdcc7  mov     [rsp+8E0h+var_8B8], rcx
0x1800bdccc  lea     rcx, [rsp+8E0h+var_880]
0x1800bdcd1  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bdcd6  lea     rdx, byte_18016837F
0x1800bdcdd  mov     rcx, rax
0x1800bdce0  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bdce5  mov     rcx, [rbp+7E8h]; this
0x1800bdcec  test    ebx, ebx
0x1800bdcee  jns     short loc_1800BDD13
0x1800bdcf0  mov     r9d, ebx; char *
0x1800bdcf3  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bdcfa  mov     edx, 81h; void *
0x1800bdcff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bdd04  mov     rax, [rdi]
0x1800bdd07  mov     rcx, rdi
0x1800bdd0a  mov     rax, [rax+20h]
0x1800bdd0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bdd13  mov     ebx, [rdi+40h]
0x1800bdd16  test    ebx, ebx
0x1800bdd18  jns     short loc_1800BDD21
0x1800bdd1a  mov     edx, 8Ah
0x1800bdd1f  jmp     short loc_1800BDD32
0x1800bdd21  mov     rcx, [rsp+8E0h+var_878]
0x1800bdd26  mov     ebx, [rcx+4]
0x1800bdd29  test    ebx, ebx
0x1800bdd2b  jns     short loc_1800BDD4A
0x1800bdd2d  mov     edx, 8Ch; void *
0x1800bdd32  mov     r9d, ebx; char *
0x1800bdd35  mov     rcx, [rbp+7E8h]; this
0x1800bdd3c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bdd43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdd48  jmp     short loc_1800BDD68
0x1800bdd4a  mov     rdx, [rbp+7E0h+arg_20]
0x1800bdd51  call    ??$CastTo@UXvmGetState@@@XvmMessage@@QEAAJPEAPEAUXvmGetState@@@Z; XvmMessage::CastTo<XvmGetState>(XvmGetState * *)
0x1800bdd56  mov     ebx, eax
0x1800bdd58  test    eax, eax
0x1800bdd5a  jns     short loc_1800BDD66
0x1800bdd5c  mov     r9d, eax
0x1800bdd5f  mov     edx, 8Dh
0x1800bdd64  jmp     short loc_1800BDD35
0x1800bdd66  xor     ebx, ebx
0x1800bdd68  mov     rcx, [rbp+7E0h+arg_18]
0x1800bdd6f  mov     rax, [rsp+8E0h+var_878]
0x1800bdd74  mov     [rcx], rax
0x1800bdd77  mov     eax, ebx
0x1800bdd79  lea     r11, [rsp+8E0h+var_10]
0x1800bdd81  mov     rbx, [r11+28h]
0x1800bdd85  mov     rsi, [r11+30h]
0x1800bdd89  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bdd8e  mov     rsp, r11
0x1800bdd91  pop     r14
0x1800bdd93  pop     rdi
0x1800bdd94  pop     rbp
0x1800bdd95  retn
```
