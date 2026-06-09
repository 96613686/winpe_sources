# CGuestXvmAudioObject::SendAndValidateResponse<XvmSetMute>(uint,XvmSetMute,XvmMessage * *,XvmSetMute * *)

- ea: `0x1800bf560`
- end: `0x1800bf8ba`
- name: `??$SendAndValidateResponse@UXvmSetMute@@@CGuestXvmAudioObject@@QEAAJIUXvmSetMute@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `858`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c2750`
- `0x1800c2820`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2e70`
- `0x1800bf560`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bf5a2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bf6a1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bf5a2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bf6a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf5d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf5d6`

## string_xrefs

- `0x1800bf5b9`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bf5f8`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bf817`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bf860`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmSetMute>(__int64 a1, unsigned int a2, __int64 a3, ...)
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
    v32 = 24;
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
            (unsigned int)qword_180168870,
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
          (unsigned int)byte_1801688E9,
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
        v18 = XvmMessage::CastTo<XvmSetMute>(v21, v40, v12);
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
0x1800bf560  mov     rax, rsp
0x1800bf563  mov     [rax+10h], rbx
0x1800bf567  mov     [rax+18h], rsi
0x1800bf56b  mov     [rax+20h], r9
0x1800bf56f  push    rbp
0x1800bf570  push    rdi
0x1800bf571  push    r14
0x1800bf573  lea     rbp, [rax-7E8h]
0x1800bf57a  sub     rsp, 8D0h
0x1800bf581  movaps  xmmword ptr [rax-28h], xmm6
0x1800bf585  mov     rsi, r8
0x1800bf588  mov     r14d, edx
0x1800bf58b  mov     rbx, rcx
0x1800bf58e  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bf596  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800bf59e  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800bf5a2  call    cs:__imp_QueryPerformanceCounter
0x1800bf5a8  mov     edi, [rbx+40h]
0x1800bf5ab  test    edi, edi
0x1800bf5ad  jns     short loc_1800BF5D1
0x1800bf5af  mov     rcx, [rbp+7E8h]; this
0x1800bf5b6  mov     r9d, edi; char *
0x1800bf5b9  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bf5c0  mov     edx, 4Fh ; 'O'; void *
0x1800bf5c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf5ca  mov     eax, edi
0x1800bf5cc  jmp     loc_1800BF89D
0x1800bf5d1  mov     ecx, 810h; cb
0x1800bf5d6  call    cs:__imp_CoTaskMemAlloc
0x1800bf5dc  mov     rdi, rax
0x1800bf5df  mov     [rsp+8E0h+var_878], rax
0x1800bf5e4  test    rax, rax
0x1800bf5e7  jnz     short loc_1800BF60C
0x1800bf5e9  mov     rcx, [rbp+7E8h]; this
0x1800bf5f0  mov     ebx, 8007000Eh
0x1800bf5f5  mov     r9d, ebx; char *
0x1800bf5f8  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bf5ff  lea     edx, [rax+52h]; void *
0x1800bf602  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf607  jmp     loc_1800BF89B
0x1800bf60c  mov     [rbp+7E0h+Src], 0
0x1800bf614  mov     [rbp+7E0h+var_824], 0
0x1800bf61b  xor     edx, edx; Val
0x1800bf61d  mov     r8d, 800h; Size
0x1800bf623  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bf627  call    memset_0
0x1800bf62c  mov     rax, [rsi]
0x1800bf62f  mov     [rbp+7E0h+var_820], rax
0x1800bf633  movsd   xmm0, qword ptr [rsi+8]
0x1800bf638  movsd   [rbp+7E0h+var_818], xmm0
0x1800bf63d  mov     al, [rsi+10h]
0x1800bf640  mov     [rbp+7E0h+var_810], al
0x1800bf643  mov     [rbp+7E0h+var_828], 18h
0x1800bf64a  mov     rcx, rdi; void *
0x1800bf64d  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bf651  mov     r8d, 810h; Size
0x1800bf657  call    memcpy_0
0x1800bf65c  mov     rax, [rsp+8E0h+var_878]
0x1800bf661  mov     [rax+0Ch], r14d
0x1800bf665  lea     rax, [rbp+7E0h+arg_18]
0x1800bf66c  mov     [rbp+7E0h+var_848], rax
0x1800bf670  lea     rax, [rsp+8E0h+var_878]
0x1800bf675  mov     [rbp+7E0h+var_840], rax
0x1800bf679  mov     [rbp+7E0h+var_838], 1
0x1800bf67d  mov     rcx, [rbx+28h]
0x1800bf681  mov     rax, [rcx]
0x1800bf684  mov     r9d, 810h
0x1800bf68a  mov     r8, [rsp+8E0h+var_878]
0x1800bf68f  mov     edx, r14d
0x1800bf692  mov     rax, [rax+20h]
0x1800bf696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf69b  mov     edi, eax
0x1800bf69d  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800bf6a1  call    cs:__imp_QueryPerformanceCounter
0x1800bf6a7  xorps   xmm6, xmm6
0x1800bf6aa  cmp     qword ptr [rbx+48h], 0
0x1800bf6af  jz      short loc_1800BF6D3
0x1800bf6b1  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800bf6b5  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800bf6b9  cvtsi2ss xmm6, rcx
0x1800bf6be  mulss   xmm6, cs:__real@447a0000
0x1800bf6c6  xorps   xmm0, xmm0
0x1800bf6c9  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800bf6cf  divss   xmm6, xmm0
0x1800bf6d3  mov     rcx, [rsp+8E0h+var_878]
0x1800bf6d8  cmp     dword ptr [rcx+8], 1
0x1800bf6dc  jnz     loc_1800BF798
0x1800bf6e2  mov     [rsp+8E0h+var_870], 0
0x1800bf6eb  lea     rdx, [rsp+8E0h+var_870]
0x1800bf6f0  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bf6f5  test    eax, eax
0x1800bf6f7  js      loc_1800BF809
0x1800bf6fd  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bf702  mov     r8, rax
0x1800bf705  mov     ecx, [rax]
0x1800bf707  cmp     ecx, 4
0x1800bf70a  jbe     loc_1800BF809
0x1800bf710  mov     [rbp+7E0h+arg_0], edi
0x1800bf716  movss   [rsp+8E0h+var_868], xmm6
0x1800bf71c  mov     [rbp+7E0h+var_860], rbx
0x1800bf720  mov     rdx, [rsp+8E0h+var_870]
0x1800bf725  mov     ecx, [rdx+10h]
0x1800bf728  mov     [rsp+8E0h+var_864], ecx
0x1800bf72c  mov     ecx, [rdx+4]
0x1800bf72f  mov     [rsp+8E0h+var_880], ecx
0x1800bf733  mov     eax, [rdx+8]
0x1800bf736  mov     [rsp+8E0h+var_880+4], eax
0x1800bf73a  mov     eax, [rdx]
0x1800bf73c  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800bf740  lea     rax, [rbp+7E0h+arg_0]
0x1800bf747  mov     [rsp+8E0h+var_890], rax
0x1800bf74c  lea     rax, [rsp+8E0h+var_868]
0x1800bf751  mov     [rsp+8E0h+var_898], rax
0x1800bf756  lea     rax, [rbp+7E0h+var_860]
0x1800bf75a  mov     [rsp+8E0h+var_8A0], rax
0x1800bf75f  lea     rax, [rsp+8E0h+var_864]
0x1800bf764  mov     [rsp+8E0h+var_8A8], rax
0x1800bf769  lea     rax, [rsp+8E0h+var_880]
0x1800bf76e  mov     [rsp+8E0h+var_8B0], rax
0x1800bf773  lea     rax, [rsp+8E0h+var_880+4]
0x1800bf778  mov     [rsp+8E0h+var_8B8], rax
0x1800bf77d  lea     rax, [rsp+8E0h+var_870]
0x1800bf782  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bf787  lea     rdx, qword_180168870
0x1800bf78e  mov     rcx, r8
0x1800bf791  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bf796  jmp     short loc_1800BF809
0x1800bf798  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bf79d  mov     ecx, [rax]
0x1800bf79f  cmp     ecx, 4
0x1800bf7a2  jbe     short loc_1800BF809
0x1800bf7a4  mov     [rbp+7E0h+arg_0], edi
0x1800bf7aa  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bf7b0  mov     [rbp+7E0h+var_860], rbx
0x1800bf7b4  mov     rcx, [rsp+8E0h+var_878]
0x1800bf7b9  mov     edx, [rcx+8]
0x1800bf7bc  mov     [rsp+8E0h+var_880+4], edx
0x1800bf7c0  mov     ecx, [rbx+30h]
0x1800bf7c3  mov     [rsp+8E0h+var_880], ecx
0x1800bf7c7  lea     rcx, [rbp+7E0h+arg_0]
0x1800bf7ce  mov     [rsp+8E0h+var_8A0], rcx
0x1800bf7d3  lea     rcx, [rsp+8E0h+var_870]
0x1800bf7d8  mov     [rsp+8E0h+var_8A8], rcx
0x1800bf7dd  lea     rcx, [rbp+7E0h+var_860]
0x1800bf7e1  mov     [rsp+8E0h+var_8B0], rcx
0x1800bf7e6  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bf7eb  mov     [rsp+8E0h+var_8B8], rcx
0x1800bf7f0  lea     rcx, [rsp+8E0h+var_880]
0x1800bf7f5  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bf7fa  lea     rdx, byte_1801688E9
0x1800bf801  mov     rcx, rax
0x1800bf804  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bf809  mov     rcx, [rbp+7E8h]; this
0x1800bf810  test    edi, edi
0x1800bf812  jns     short loc_1800BF837
0x1800bf814  mov     r9d, edi; char *
0x1800bf817  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bf81e  mov     edx, 81h; void *
0x1800bf823  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bf828  mov     rax, [rbx]
0x1800bf82b  mov     rcx, rbx
0x1800bf82e  mov     rax, [rax+20h]
0x1800bf832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf837  mov     ebx, [rbx+40h]
0x1800bf83a  test    ebx, ebx
0x1800bf83c  jns     short loc_1800BF845
0x1800bf83e  mov     edx, 8Ah
0x1800bf843  jmp     short loc_1800BF856
0x1800bf845  mov     rcx, [rsp+8E0h+var_878]
0x1800bf84a  mov     ebx, [rcx+4]
0x1800bf84d  test    ebx, ebx
0x1800bf84f  jns     short loc_1800BF86E
0x1800bf851  mov     edx, 8Ch; void *
0x1800bf856  mov     r9d, ebx; char *
0x1800bf859  mov     rcx, [rbp+7E8h]; this
0x1800bf860  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bf867  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf86c  jmp     short loc_1800BF88C
0x1800bf86e  mov     rdx, [rbp+7E0h+arg_20]
0x1800bf875  call    ??$CastTo@UXvmSetMute@@@XvmMessage@@QEAAJPEAPEAUXvmSetMute@@@Z; XvmMessage::CastTo<XvmSetMute>(XvmSetMute * *)
0x1800bf87a  mov     ebx, eax
0x1800bf87c  test    eax, eax
0x1800bf87e  jns     short loc_1800BF88A
0x1800bf880  mov     r9d, eax
0x1800bf883  mov     edx, 8Dh
0x1800bf888  jmp     short loc_1800BF859
0x1800bf88a  xor     ebx, ebx
0x1800bf88c  mov     rcx, [rbp+7E0h+arg_18]
0x1800bf893  mov     rax, [rsp+8E0h+var_878]
0x1800bf898  mov     [rcx], rax
0x1800bf89b  mov     eax, ebx
0x1800bf89d  lea     r11, [rsp+8E0h+var_10]
0x1800bf8a5  mov     rbx, [r11+28h]
0x1800bf8a9  mov     rsi, [r11+30h]
0x1800bf8ad  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bf8b2  mov     rsp, r11
0x1800bf8b5  pop     r14
0x1800bf8b7  pop     rdi
0x1800bf8b8  pop     rbp
0x1800bf8b9  retn
```
