# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetMixFormat>(uint,XvmGetMixFormat,XvmMessage * *,XvmGetMixFormat * *)

- ea: `0x1800ac3ec`
- end: `0x1800ac758`
- name: `??$SendAndValidateResponse@UXvmGetMixFormat@@@CGuestXvmAudioObject@@QEAAJIUXvmGetMixFormat@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `876`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800afba0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a29f8`
- `0x1800ac3ec`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ac42e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ac53f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ac42e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ac53f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ac462`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ac462`

## string_xrefs

- `0x1800ac445`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ac484`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ac6b5`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ac6fe`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetMixFormat>(__int64 a1, unsigned int a2, __int64 a3, ...)
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
  int Mix; // eax
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
  _OWORD v34[4]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v35; // [rsp+108h] [rbp+0h]
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
    v34[0] = *(_OWORD *)a3;
    v34[1] = *(_OWORD *)(a3 + 16);
    v34[2] = *(_OWORD *)(a3 + 32);
    v34[3] = *(_OWORD *)(a3 + 48);
    v35 = *(_QWORD *)(a3 + 64);
    v32 = 2;
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
            (unsigned int)byte_180166609,
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
          (unsigned int)&word_1801664F6,
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
        Mix = XvmMessage::CastTo<XvmGetMixFormat>(v21, v40, v12);
        v9 = Mix;
        if ( Mix >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)Mix;
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
0x1800ac3ec  mov     rax, rsp
0x1800ac3ef  mov     [rax+10h], rbx
0x1800ac3f3  mov     [rax+18h], rsi
0x1800ac3f7  mov     [rax+20h], r9
0x1800ac3fb  push    rbp
0x1800ac3fc  push    rdi
0x1800ac3fd  push    r14
0x1800ac3ff  lea     rbp, [rax-7E8h]
0x1800ac406  sub     rsp, 8D0h
0x1800ac40d  movaps  xmmword ptr [rax-28h], xmm6
0x1800ac411  mov     rsi, r8
0x1800ac414  mov     r14d, edx
0x1800ac417  mov     rbx, rcx
0x1800ac41a  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800ac422  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800ac42a  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800ac42e  call    cs:__imp_QueryPerformanceCounter
0x1800ac434  mov     edi, [rbx+40h]
0x1800ac437  test    edi, edi
0x1800ac439  jns     short loc_1800AC45D
0x1800ac43b  mov     rcx, [rbp+7E8h]; this
0x1800ac442  mov     r9d, edi; char *
0x1800ac445  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ac44c  mov     edx, 4Fh ; 'O'; void *
0x1800ac451  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac456  mov     eax, edi
0x1800ac458  jmp     loc_1800AC73B
0x1800ac45d  mov     ecx, 810h; cb
0x1800ac462  call    cs:__imp_CoTaskMemAlloc
0x1800ac468  mov     rdi, rax
0x1800ac46b  mov     [rsp+8E0h+var_878], rax
0x1800ac470  test    rax, rax
0x1800ac473  jnz     short loc_1800AC498
0x1800ac475  mov     rcx, [rbp+7E8h]; this
0x1800ac47c  mov     ebx, 8007000Eh
0x1800ac481  mov     r9d, ebx; char *
0x1800ac484  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ac48b  lea     edx, [rax+52h]; void *
0x1800ac48e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac493  jmp     loc_1800AC739
0x1800ac498  mov     [rbp+7E0h+Src], 0
0x1800ac4a0  mov     [rbp+7E0h+var_824], 0
0x1800ac4a7  xor     edx, edx; Val
0x1800ac4a9  mov     r8d, 800h; Size
0x1800ac4af  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800ac4b3  call    memset_0
0x1800ac4b8  movups  xmm0, xmmword ptr [rsi]
0x1800ac4bb  movaps  [rbp+7E0h+var_820], xmm0
0x1800ac4bf  movups  xmm1, xmmword ptr [rsi+10h]
0x1800ac4c3  movaps  [rbp+7E0h+var_810], xmm1
0x1800ac4c7  movups  xmm0, xmmword ptr [rsi+20h]
0x1800ac4cb  movaps  [rbp+7E0h+var_800], xmm0
0x1800ac4cf  movups  xmm1, xmmword ptr [rsi+30h]
0x1800ac4d3  movaps  [rbp+7E0h+var_7F0], xmm1
0x1800ac4d7  movsd   xmm0, qword ptr [rsi+40h]
0x1800ac4dc  movsd   [rbp+7E0h+var_7E0], xmm0
0x1800ac4e1  mov     [rbp+7E0h+var_828], 2
0x1800ac4e8  mov     rcx, rdi; void *
0x1800ac4eb  lea     rdx, [rbp+7E0h+Src]; Src
0x1800ac4ef  mov     r8d, 810h; Size
0x1800ac4f5  call    memcpy_0
0x1800ac4fa  mov     rax, [rsp+8E0h+var_878]
0x1800ac4ff  mov     [rax+0Ch], r14d
0x1800ac503  lea     rax, [rbp+7E0h+arg_18]
0x1800ac50a  mov     [rbp+7E0h+var_848], rax
0x1800ac50e  lea     rax, [rsp+8E0h+var_878]
0x1800ac513  mov     [rbp+7E0h+var_840], rax
0x1800ac517  mov     [rbp+7E0h+var_838], 1
0x1800ac51b  mov     rcx, [rbx+28h]
0x1800ac51f  mov     rax, [rcx]
0x1800ac522  mov     r9d, 810h
0x1800ac528  mov     r8, [rsp+8E0h+var_878]
0x1800ac52d  mov     edx, r14d
0x1800ac530  mov     rax, [rax+20h]
0x1800ac534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac539  mov     edi, eax
0x1800ac53b  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800ac53f  call    cs:__imp_QueryPerformanceCounter
0x1800ac545  xorps   xmm6, xmm6
0x1800ac548  cmp     qword ptr [rbx+48h], 0
0x1800ac54d  jz      short loc_1800AC571
0x1800ac54f  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800ac553  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800ac557  cvtsi2ss xmm6, rcx
0x1800ac55c  mulss   xmm6, cs:__real@447a0000
0x1800ac564  xorps   xmm0, xmm0
0x1800ac567  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800ac56d  divss   xmm6, xmm0
0x1800ac571  mov     rcx, [rsp+8E0h+var_878]
0x1800ac576  cmp     dword ptr [rcx+8], 1
0x1800ac57a  jnz     loc_1800AC636
0x1800ac580  mov     [rsp+8E0h+var_870], 0
0x1800ac589  lea     rdx, [rsp+8E0h+var_870]
0x1800ac58e  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800ac593  test    eax, eax
0x1800ac595  js      loc_1800AC6A7
0x1800ac59b  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ac5a0  mov     r8, rax
0x1800ac5a3  mov     ecx, [rax]
0x1800ac5a5  cmp     ecx, 4
0x1800ac5a8  jbe     loc_1800AC6A7
0x1800ac5ae  mov     [rbp+7E0h+arg_0], edi
0x1800ac5b4  movss   [rsp+8E0h+var_868], xmm6
0x1800ac5ba  mov     [rbp+7E0h+var_860], rbx
0x1800ac5be  mov     rdx, [rsp+8E0h+var_870]
0x1800ac5c3  mov     ecx, [rdx+10h]
0x1800ac5c6  mov     [rsp+8E0h+var_864], ecx
0x1800ac5ca  mov     ecx, [rdx+4]
0x1800ac5cd  mov     [rsp+8E0h+var_880], ecx
0x1800ac5d1  mov     eax, [rdx+8]
0x1800ac5d4  mov     [rsp+8E0h+var_880+4], eax
0x1800ac5d8  mov     eax, [rdx]
0x1800ac5da  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800ac5de  lea     rax, [rbp+7E0h+arg_0]
0x1800ac5e5  mov     [rsp+8E0h+var_890], rax
0x1800ac5ea  lea     rax, [rsp+8E0h+var_868]
0x1800ac5ef  mov     [rsp+8E0h+var_898], rax
0x1800ac5f4  lea     rax, [rbp+7E0h+var_860]
0x1800ac5f8  mov     [rsp+8E0h+var_8A0], rax
0x1800ac5fd  lea     rax, [rsp+8E0h+var_864]
0x1800ac602  mov     [rsp+8E0h+var_8A8], rax
0x1800ac607  lea     rax, [rsp+8E0h+var_880]
0x1800ac60c  mov     [rsp+8E0h+var_8B0], rax
0x1800ac611  lea     rax, [rsp+8E0h+var_880+4]
0x1800ac616  mov     [rsp+8E0h+var_8B8], rax
0x1800ac61b  lea     rax, [rsp+8E0h+var_870]
0x1800ac620  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800ac625  lea     rdx, byte_180166609
0x1800ac62c  mov     rcx, r8
0x1800ac62f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ac634  jmp     short loc_1800AC6A7
0x1800ac636  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ac63b  mov     ecx, [rax]
0x1800ac63d  cmp     ecx, 4
0x1800ac640  jbe     short loc_1800AC6A7
0x1800ac642  mov     [rbp+7E0h+arg_0], edi
0x1800ac648  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800ac64e  mov     [rbp+7E0h+var_860], rbx
0x1800ac652  mov     rcx, [rsp+8E0h+var_878]
0x1800ac657  mov     edx, [rcx+8]
0x1800ac65a  mov     [rsp+8E0h+var_880+4], edx
0x1800ac65e  mov     ecx, [rbx+30h]
0x1800ac661  mov     [rsp+8E0h+var_880], ecx
0x1800ac665  lea     rcx, [rbp+7E0h+arg_0]
0x1800ac66c  mov     [rsp+8E0h+var_8A0], rcx
0x1800ac671  lea     rcx, [rsp+8E0h+var_870]
0x1800ac676  mov     [rsp+8E0h+var_8A8], rcx
0x1800ac67b  lea     rcx, [rbp+7E0h+var_860]
0x1800ac67f  mov     [rsp+8E0h+var_8B0], rcx
0x1800ac684  lea     rcx, [rsp+8E0h+var_880+4]
0x1800ac689  mov     [rsp+8E0h+var_8B8], rcx
0x1800ac68e  lea     rcx, [rsp+8E0h+var_880]
0x1800ac693  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800ac698  lea     rdx, word_1801664F6
0x1800ac69f  mov     rcx, rax
0x1800ac6a2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ac6a7  mov     rcx, [rbp+7E8h]; this
0x1800ac6ae  test    edi, edi
0x1800ac6b0  jns     short loc_1800AC6D5
0x1800ac6b2  mov     r9d, edi; char *
0x1800ac6b5  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ac6bc  mov     edx, 81h; void *
0x1800ac6c1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ac6c6  mov     rax, [rbx]
0x1800ac6c9  mov     rcx, rbx
0x1800ac6cc  mov     rax, [rax+20h]
0x1800ac6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ac6d5  mov     ebx, [rbx+40h]
0x1800ac6d8  test    ebx, ebx
0x1800ac6da  jns     short loc_1800AC6E3
0x1800ac6dc  mov     edx, 8Ah
0x1800ac6e1  jmp     short loc_1800AC6F4
0x1800ac6e3  mov     rcx, [rsp+8E0h+var_878]
0x1800ac6e8  mov     ebx, [rcx+4]
0x1800ac6eb  test    ebx, ebx
0x1800ac6ed  jns     short loc_1800AC70C
0x1800ac6ef  mov     edx, 8Ch; void *
0x1800ac6f4  mov     r9d, ebx; char *
0x1800ac6f7  mov     rcx, [rbp+7E8h]; this
0x1800ac6fe  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ac705  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ac70a  jmp     short loc_1800AC72A
0x1800ac70c  mov     rdx, [rbp+7E0h+arg_20]
0x1800ac713  call    ??$CastTo@UXvmGetMixFormat@@@XvmMessage@@QEAAJPEAPEAUXvmGetMixFormat@@@Z; XvmMessage::CastTo<XvmGetMixFormat>(XvmGetMixFormat * *)
0x1800ac718  mov     ebx, eax
0x1800ac71a  test    eax, eax
0x1800ac71c  jns     short loc_1800AC728
0x1800ac71e  mov     r9d, eax
0x1800ac721  mov     edx, 8Dh
0x1800ac726  jmp     short loc_1800AC6F7
0x1800ac728  xor     ebx, ebx
0x1800ac72a  mov     rcx, [rbp+7E0h+arg_18]
0x1800ac731  mov     rax, [rsp+8E0h+var_878]
0x1800ac736  mov     [rcx], rax
0x1800ac739  mov     eax, ebx
0x1800ac73b  lea     r11, [rsp+8E0h+var_10]
0x1800ac743  mov     rbx, [r11+28h]
0x1800ac747  mov     rsi, [r11+30h]
0x1800ac74b  movaps  xmm6, xmmword ptr [r11-10h]
0x1800ac750  mov     rsp, r11
0x1800ac753  pop     r14
0x1800ac755  pop     rdi
0x1800ac756  pop     rbp
0x1800ac757  retn
```
