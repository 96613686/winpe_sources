# CGuestXvmAudioObject::SendAndValidateResponse<XvmPlayToStreamStateChanged>(uint,XvmPlayToStreamStateChanged,XvmMessage * *,XvmPlayToStreamStateChanged * *)

- ea: `0x1800f500c`
- end: `0x1800f5352`
- name: `??$SendAndValidateResponse@UXvmPlayToStreamStateChanged@@@CGuestXvmAudioObject@@QEAAJIUXvmPlayToStreamStateChanged@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f5fc0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800f4bb8`
- `0x1800f500c`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f504e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f5139`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f504e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f5139`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f5082`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f5082`

## string_xrefs

- `0x1800f5065`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800f50a4`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800f52af`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800f52f8`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmPlayToStreamStateChanged>(
        __int64 a1,
        unsigned int a2,
        int a3,
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
    v32 = 100;
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
            (unsigned int)byte_180170519,
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
          (unsigned int)word_180170592,
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
        v18 = XvmMessage::CastTo<XvmPlayToStreamStateChanged>(v21, v39, v12);
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
0x1800f500c  mov     rax, rsp
0x1800f500f  mov     [rax+10h], rbx
0x1800f5013  mov     [rax+18h], rsi
0x1800f5017  mov     [rax+20h], r9
0x1800f501b  push    rbp
0x1800f501c  push    rdi
0x1800f501d  push    r14
0x1800f501f  lea     rbp, [rax-7E8h]
0x1800f5026  sub     rsp, 8D0h
0x1800f502d  movaps  xmmword ptr [rax-28h], xmm6
0x1800f5031  mov     ebx, r8d
0x1800f5034  mov     r14d, edx
0x1800f5037  mov     rdi, rcx
0x1800f503a  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800f5042  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800f504a  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800f504e  call    cs:__imp_QueryPerformanceCounter
0x1800f5054  mov     esi, [rdi+40h]
0x1800f5057  test    esi, esi
0x1800f5059  jns     short loc_1800F507D
0x1800f505b  mov     rcx, [rbp+7E8h]; this
0x1800f5062  mov     r9d, esi; char *
0x1800f5065  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800f506c  mov     edx, 4Fh ; 'O'; void *
0x1800f5071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5076  mov     eax, esi
0x1800f5078  jmp     loc_1800F5335
0x1800f507d  mov     ecx, 810h; cb
0x1800f5082  call    cs:__imp_CoTaskMemAlloc
0x1800f5088  mov     rsi, rax
0x1800f508b  mov     [rsp+8E0h+var_878], rax
0x1800f5090  test    rax, rax
0x1800f5093  jnz     short loc_1800F50B8
0x1800f5095  mov     rcx, [rbp+7E8h]; this
0x1800f509c  mov     ebx, 8007000Eh
0x1800f50a1  mov     r9d, ebx; char *
0x1800f50a4  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800f50ab  lea     edx, [rax+52h]; void *
0x1800f50ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f50b3  jmp     loc_1800F5333
0x1800f50b8  mov     [rbp+7E0h+Src], 0
0x1800f50c0  mov     [rbp+7E0h+var_824], 0
0x1800f50c7  xor     edx, edx; Val
0x1800f50c9  mov     r8d, 800h; Size
0x1800f50cf  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800f50d3  call    memset_0
0x1800f50d8  mov     [rbp+7E0h+var_820], ebx
0x1800f50db  mov     [rbp+7E0h+var_828], 64h ; 'd'
0x1800f50e2  mov     rcx, rsi; void *
0x1800f50e5  lea     rdx, [rbp+7E0h+Src]; Src
0x1800f50e9  mov     r8d, 810h; Size
0x1800f50ef  call    memcpy_0
0x1800f50f4  mov     rax, [rsp+8E0h+var_878]
0x1800f50f9  mov     [rax+0Ch], r14d
0x1800f50fd  lea     rax, [rbp+7E0h+arg_18]
0x1800f5104  mov     [rbp+7E0h+var_848], rax
0x1800f5108  lea     rax, [rsp+8E0h+var_878]
0x1800f510d  mov     [rbp+7E0h+var_840], rax
0x1800f5111  mov     [rbp+7E0h+var_838], 1
0x1800f5115  mov     rcx, [rdi+28h]
0x1800f5119  mov     rax, [rcx]
0x1800f511c  mov     r9d, 810h
0x1800f5122  mov     r8, [rsp+8E0h+var_878]
0x1800f5127  mov     edx, r14d
0x1800f512a  mov     rax, [rax+20h]
0x1800f512e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5133  mov     ebx, eax
0x1800f5135  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800f5139  call    cs:__imp_QueryPerformanceCounter
0x1800f513f  xorps   xmm6, xmm6
0x1800f5142  cmp     qword ptr [rdi+48h], 0
0x1800f5147  jz      short loc_1800F516B
0x1800f5149  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800f514d  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800f5151  cvtsi2ss xmm6, rcx
0x1800f5156  mulss   xmm6, cs:__real@447a0000
0x1800f515e  xorps   xmm0, xmm0
0x1800f5161  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800f5167  divss   xmm6, xmm0
0x1800f516b  mov     rcx, [rsp+8E0h+var_878]
0x1800f5170  cmp     dword ptr [rcx+8], 1
0x1800f5174  jnz     loc_1800F5230
0x1800f517a  mov     [rsp+8E0h+var_870], 0
0x1800f5183  lea     rdx, [rsp+8E0h+var_870]
0x1800f5188  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800f518d  test    eax, eax
0x1800f518f  js      loc_1800F52A1
0x1800f5195  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800f519a  mov     r8, rax
0x1800f519d  mov     ecx, [rax]
0x1800f519f  cmp     ecx, 4
0x1800f51a2  jbe     loc_1800F52A1
0x1800f51a8  mov     [rbp+7E0h+arg_0], ebx
0x1800f51ae  movss   [rsp+8E0h+var_868], xmm6
0x1800f51b4  mov     [rbp+7E0h+var_860], rdi
0x1800f51b8  mov     rdx, [rsp+8E0h+var_870]
0x1800f51bd  mov     ecx, [rdx+10h]
0x1800f51c0  mov     [rsp+8E0h+var_864], ecx
0x1800f51c4  mov     ecx, [rdx+4]
0x1800f51c7  mov     [rsp+8E0h+var_880], ecx
0x1800f51cb  mov     eax, [rdx+8]
0x1800f51ce  mov     [rsp+8E0h+var_880+4], eax
0x1800f51d2  mov     eax, [rdx]
0x1800f51d4  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800f51d8  lea     rax, [rbp+7E0h+arg_0]
0x1800f51df  mov     [rsp+8E0h+var_890], rax
0x1800f51e4  lea     rax, [rsp+8E0h+var_868]
0x1800f51e9  mov     [rsp+8E0h+var_898], rax
0x1800f51ee  lea     rax, [rbp+7E0h+var_860]
0x1800f51f2  mov     [rsp+8E0h+var_8A0], rax
0x1800f51f7  lea     rax, [rsp+8E0h+var_864]
0x1800f51fc  mov     [rsp+8E0h+var_8A8], rax
0x1800f5201  lea     rax, [rsp+8E0h+var_880]
0x1800f5206  mov     [rsp+8E0h+var_8B0], rax
0x1800f520b  lea     rax, [rsp+8E0h+var_880+4]
0x1800f5210  mov     [rsp+8E0h+var_8B8], rax
0x1800f5215  lea     rax, [rsp+8E0h+var_870]
0x1800f521a  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800f521f  lea     rdx, byte_180170519
0x1800f5226  mov     rcx, r8
0x1800f5229  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800f522e  jmp     short loc_1800F52A1
0x1800f5230  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800f5235  mov     ecx, [rax]
0x1800f5237  cmp     ecx, 4
0x1800f523a  jbe     short loc_1800F52A1
0x1800f523c  mov     [rbp+7E0h+arg_0], ebx
0x1800f5242  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800f5248  mov     [rbp+7E0h+var_860], rdi
0x1800f524c  mov     rcx, [rsp+8E0h+var_878]
0x1800f5251  mov     edx, [rcx+8]
0x1800f5254  mov     [rsp+8E0h+var_880+4], edx
0x1800f5258  mov     ecx, [rdi+30h]
0x1800f525b  mov     [rsp+8E0h+var_880], ecx
0x1800f525f  lea     rcx, [rbp+7E0h+arg_0]
0x1800f5266  mov     [rsp+8E0h+var_8A0], rcx
0x1800f526b  lea     rcx, [rsp+8E0h+var_870]
0x1800f5270  mov     [rsp+8E0h+var_8A8], rcx
0x1800f5275  lea     rcx, [rbp+7E0h+var_860]
0x1800f5279  mov     [rsp+8E0h+var_8B0], rcx
0x1800f527e  lea     rcx, [rsp+8E0h+var_880+4]
0x1800f5283  mov     [rsp+8E0h+var_8B8], rcx
0x1800f5288  lea     rcx, [rsp+8E0h+var_880]
0x1800f528d  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800f5292  lea     rdx, word_180170592
0x1800f5299  mov     rcx, rax
0x1800f529c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800f52a1  mov     rcx, [rbp+7E8h]; this
0x1800f52a8  test    ebx, ebx
0x1800f52aa  jns     short loc_1800F52CF
0x1800f52ac  mov     r9d, ebx; char *
0x1800f52af  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800f52b6  mov     edx, 81h; void *
0x1800f52bb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f52c0  mov     rax, [rdi]
0x1800f52c3  mov     rcx, rdi
0x1800f52c6  mov     rax, [rax+20h]
0x1800f52ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f52cf  mov     ebx, [rdi+40h]
0x1800f52d2  test    ebx, ebx
0x1800f52d4  jns     short loc_1800F52DD
0x1800f52d6  mov     edx, 8Ah
0x1800f52db  jmp     short loc_1800F52EE
0x1800f52dd  mov     rcx, [rsp+8E0h+var_878]
0x1800f52e2  mov     ebx, [rcx+4]
0x1800f52e5  test    ebx, ebx
0x1800f52e7  jns     short loc_1800F5306
0x1800f52e9  mov     edx, 8Ch; void *
0x1800f52ee  mov     r9d, ebx; char *
0x1800f52f1  mov     rcx, [rbp+7E8h]; this
0x1800f52f8  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800f52ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5304  jmp     short loc_1800F5324
0x1800f5306  mov     rdx, [rbp+7E0h+arg_20]
0x1800f530d  call    ??$CastTo@UXvmPlayToStreamStateChanged@@@XvmMessage@@QEAAJPEAPEAUXvmPlayToStreamStateChanged@@@Z; XvmMessage::CastTo<XvmPlayToStreamStateChanged>(XvmPlayToStreamStateChanged * *)
0x1800f5312  mov     ebx, eax
0x1800f5314  test    eax, eax
0x1800f5316  jns     short loc_1800F5322
0x1800f5318  mov     r9d, eax
0x1800f531b  mov     edx, 8Dh
0x1800f5320  jmp     short loc_1800F52F1
0x1800f5322  xor     ebx, ebx
0x1800f5324  mov     rcx, [rbp+7E0h+arg_18]
0x1800f532b  mov     rax, [rsp+8E0h+var_878]
0x1800f5330  mov     [rcx], rax
0x1800f5333  mov     eax, ebx
0x1800f5335  lea     r11, [rsp+8E0h+var_10]
0x1800f533d  mov     rbx, [r11+28h]
0x1800f5341  mov     rsi, [r11+30h]
0x1800f5345  movaps  xmm6, xmmword ptr [r11-10h]
0x1800f534a  mov     rsp, r11
0x1800f534d  pop     r14
0x1800f534f  pop     rdi
0x1800f5350  pop     rbp
0x1800f5351  retn
```
