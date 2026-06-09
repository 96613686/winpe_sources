# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetDisplayName>(uint,XvmGetDisplayName,XvmMessage * *,XvmGetDisplayName * *)

- ea: `0x1800bc5d0`
- end: `0x1800bc922`
- name: `??$SendAndValidateResponse@UXvmGetDisplayName@@@CGuestXvmAudioObject@@QEAAJIUXvmGetDisplayName@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `850`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c0550`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800b933c`
- `0x1800bc5d0`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bc611`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bc709`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bc611`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bc709`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bc645`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bc645`

## string_xrefs

- `0x1800bc628`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bc667`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bc87f`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bc8c8`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetDisplayName>(
        __int64 a1,
        unsigned int a2,
        const void *a3,
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
  int Display; // eax
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
    memcpy_0(v34, a3, 0x7D0u);
    v32 = 26;
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
            (unsigned int)qword_180168240,
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
          (unsigned int)byte_1801682B9,
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
        Display = XvmMessage::CastTo<XvmGetDisplayName>(v21, v39, v12);
        v9 = Display;
        if ( Display >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)Display;
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
0x1800bc5d0  mov     rax, rsp
0x1800bc5d3  mov     [rax+10h], rbx
0x1800bc5d7  mov     [rax+18h], rsi
0x1800bc5db  mov     [rax+20h], r9
0x1800bc5df  push    rbp
0x1800bc5e0  push    rdi
0x1800bc5e1  push    r14
0x1800bc5e3  lea     rbp, [rax-7E8h]
0x1800bc5ea  sub     rsp, 8D0h
0x1800bc5f1  movaps  xmmword ptr [rax-28h], xmm6
0x1800bc5f5  mov     r14, r8
0x1800bc5f8  mov     esi, edx
0x1800bc5fa  mov     rbx, rcx
0x1800bc5fd  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bc605  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800bc60d  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800bc611  call    cs:__imp_QueryPerformanceCounter
0x1800bc617  mov     edi, [rbx+40h]
0x1800bc61a  test    edi, edi
0x1800bc61c  jns     short loc_1800BC640
0x1800bc61e  mov     rcx, [rbp+7E8h]; this
0x1800bc625  mov     r9d, edi; char *
0x1800bc628  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bc62f  mov     edx, 4Fh ; 'O'; void *
0x1800bc634  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc639  mov     eax, edi
0x1800bc63b  jmp     loc_1800BC905
0x1800bc640  mov     ecx, 810h; cb
0x1800bc645  call    cs:__imp_CoTaskMemAlloc
0x1800bc64b  mov     rdi, rax
0x1800bc64e  mov     [rsp+8E0h+var_878], rax
0x1800bc653  test    rax, rax
0x1800bc656  jnz     short loc_1800BC67B
0x1800bc658  mov     rcx, [rbp+7E8h]; this
0x1800bc65f  mov     ebx, 8007000Eh
0x1800bc664  mov     r9d, ebx; char *
0x1800bc667  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bc66e  lea     edx, [rax+52h]; void *
0x1800bc671  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc676  jmp     loc_1800BC903
0x1800bc67b  mov     [rbp+7E0h+Src], 0
0x1800bc683  mov     [rbp+7E0h+var_824], 0
0x1800bc68a  xor     edx, edx; Val
0x1800bc68c  mov     r8d, 800h; Size
0x1800bc692  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bc696  call    memset_0
0x1800bc69b  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bc69f  mov     rdx, r14; Src
0x1800bc6a2  mov     r8d, 7D0h; Size
0x1800bc6a8  call    memcpy_0
0x1800bc6ad  mov     [rbp+7E0h+var_828], 1Ah
0x1800bc6b4  mov     rcx, rdi; void *
0x1800bc6b7  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bc6bb  mov     r8d, 810h; Size
0x1800bc6c1  call    memcpy_0
0x1800bc6c6  mov     rax, [rsp+8E0h+var_878]
0x1800bc6cb  mov     [rax+0Ch], esi
0x1800bc6ce  lea     rax, [rbp+7E0h+arg_18]
0x1800bc6d5  mov     [rbp+7E0h+var_848], rax
0x1800bc6d9  lea     rax, [rsp+8E0h+var_878]
0x1800bc6de  mov     [rbp+7E0h+var_840], rax
0x1800bc6e2  mov     [rbp+7E0h+var_838], 1
0x1800bc6e6  mov     rcx, [rbx+28h]
0x1800bc6ea  mov     rax, [rcx]
0x1800bc6ed  mov     r9d, 810h
0x1800bc6f3  mov     r8, [rsp+8E0h+var_878]
0x1800bc6f8  mov     edx, esi
0x1800bc6fa  mov     rax, [rax+20h]
0x1800bc6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc703  mov     edi, eax
0x1800bc705  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800bc709  call    cs:__imp_QueryPerformanceCounter
0x1800bc70f  xorps   xmm6, xmm6
0x1800bc712  cmp     qword ptr [rbx+48h], 0
0x1800bc717  jz      short loc_1800BC73B
0x1800bc719  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800bc71d  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800bc721  cvtsi2ss xmm6, rcx
0x1800bc726  mulss   xmm6, cs:__real@447a0000
0x1800bc72e  xorps   xmm0, xmm0
0x1800bc731  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800bc737  divss   xmm6, xmm0
0x1800bc73b  mov     rcx, [rsp+8E0h+var_878]
0x1800bc740  cmp     dword ptr [rcx+8], 1
0x1800bc744  jnz     loc_1800BC800
0x1800bc74a  mov     [rsp+8E0h+var_870], 0
0x1800bc753  lea     rdx, [rsp+8E0h+var_870]
0x1800bc758  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bc75d  test    eax, eax
0x1800bc75f  js      loc_1800BC871
0x1800bc765  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bc76a  mov     r8, rax
0x1800bc76d  mov     ecx, [rax]
0x1800bc76f  cmp     ecx, 4
0x1800bc772  jbe     loc_1800BC871
0x1800bc778  mov     [rbp+7E0h+arg_0], edi
0x1800bc77e  movss   [rsp+8E0h+var_868], xmm6
0x1800bc784  mov     [rbp+7E0h+var_860], rbx
0x1800bc788  mov     rdx, [rsp+8E0h+var_870]
0x1800bc78d  mov     ecx, [rdx+10h]
0x1800bc790  mov     [rsp+8E0h+var_864], ecx
0x1800bc794  mov     ecx, [rdx+4]
0x1800bc797  mov     [rsp+8E0h+var_880], ecx
0x1800bc79b  mov     eax, [rdx+8]
0x1800bc79e  mov     [rsp+8E0h+var_880+4], eax
0x1800bc7a2  mov     eax, [rdx]
0x1800bc7a4  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800bc7a8  lea     rax, [rbp+7E0h+arg_0]
0x1800bc7af  mov     [rsp+8E0h+var_890], rax
0x1800bc7b4  lea     rax, [rsp+8E0h+var_868]
0x1800bc7b9  mov     [rsp+8E0h+var_898], rax
0x1800bc7be  lea     rax, [rbp+7E0h+var_860]
0x1800bc7c2  mov     [rsp+8E0h+var_8A0], rax
0x1800bc7c7  lea     rax, [rsp+8E0h+var_864]
0x1800bc7cc  mov     [rsp+8E0h+var_8A8], rax
0x1800bc7d1  lea     rax, [rsp+8E0h+var_880]
0x1800bc7d6  mov     [rsp+8E0h+var_8B0], rax
0x1800bc7db  lea     rax, [rsp+8E0h+var_880+4]
0x1800bc7e0  mov     [rsp+8E0h+var_8B8], rax
0x1800bc7e5  lea     rax, [rsp+8E0h+var_870]
0x1800bc7ea  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bc7ef  lea     rdx, qword_180168240
0x1800bc7f6  mov     rcx, r8
0x1800bc7f9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bc7fe  jmp     short loc_1800BC871
0x1800bc800  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bc805  mov     ecx, [rax]
0x1800bc807  cmp     ecx, 4
0x1800bc80a  jbe     short loc_1800BC871
0x1800bc80c  mov     [rbp+7E0h+arg_0], edi
0x1800bc812  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bc818  mov     [rbp+7E0h+var_860], rbx
0x1800bc81c  mov     rcx, [rsp+8E0h+var_878]
0x1800bc821  mov     edx, [rcx+8]
0x1800bc824  mov     [rsp+8E0h+var_880+4], edx
0x1800bc828  mov     ecx, [rbx+30h]
0x1800bc82b  mov     [rsp+8E0h+var_880], ecx
0x1800bc82f  lea     rcx, [rbp+7E0h+arg_0]
0x1800bc836  mov     [rsp+8E0h+var_8A0], rcx
0x1800bc83b  lea     rcx, [rsp+8E0h+var_870]
0x1800bc840  mov     [rsp+8E0h+var_8A8], rcx
0x1800bc845  lea     rcx, [rbp+7E0h+var_860]
0x1800bc849  mov     [rsp+8E0h+var_8B0], rcx
0x1800bc84e  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bc853  mov     [rsp+8E0h+var_8B8], rcx
0x1800bc858  lea     rcx, [rsp+8E0h+var_880]
0x1800bc85d  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bc862  lea     rdx, byte_1801682B9
0x1800bc869  mov     rcx, rax
0x1800bc86c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bc871  mov     rcx, [rbp+7E8h]; this
0x1800bc878  test    edi, edi
0x1800bc87a  jns     short loc_1800BC89F
0x1800bc87c  mov     r9d, edi; char *
0x1800bc87f  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bc886  mov     edx, 81h; void *
0x1800bc88b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bc890  mov     rax, [rbx]
0x1800bc893  mov     rcx, rbx
0x1800bc896  mov     rax, [rax+20h]
0x1800bc89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bc89f  mov     ebx, [rbx+40h]
0x1800bc8a2  test    ebx, ebx
0x1800bc8a4  jns     short loc_1800BC8AD
0x1800bc8a6  mov     edx, 8Ah
0x1800bc8ab  jmp     short loc_1800BC8BE
0x1800bc8ad  mov     rcx, [rsp+8E0h+var_878]
0x1800bc8b2  mov     ebx, [rcx+4]
0x1800bc8b5  test    ebx, ebx
0x1800bc8b7  jns     short loc_1800BC8D6
0x1800bc8b9  mov     edx, 8Ch; void *
0x1800bc8be  mov     r9d, ebx; char *
0x1800bc8c1  mov     rcx, [rbp+7E8h]; this
0x1800bc8c8  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bc8cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc8d4  jmp     short loc_1800BC8F4
0x1800bc8d6  mov     rdx, [rbp+7E0h+arg_20]
0x1800bc8dd  call    ??$CastTo@UXvmGetDisplayName@@@XvmMessage@@QEAAJPEAPEAUXvmGetDisplayName@@@Z; XvmMessage::CastTo<XvmGetDisplayName>(XvmGetDisplayName * *)
0x1800bc8e2  mov     ebx, eax
0x1800bc8e4  test    eax, eax
0x1800bc8e6  jns     short loc_1800BC8F2
0x1800bc8e8  mov     r9d, eax
0x1800bc8eb  mov     edx, 8Dh
0x1800bc8f0  jmp     short loc_1800BC8C1
0x1800bc8f2  xor     ebx, ebx
0x1800bc8f4  mov     rcx, [rbp+7E0h+arg_18]
0x1800bc8fb  mov     rax, [rsp+8E0h+var_878]
0x1800bc900  mov     [rcx], rax
0x1800bc903  mov     eax, ebx
0x1800bc905  lea     r11, [rsp+8E0h+var_10]
0x1800bc90d  mov     rbx, [r11+28h]
0x1800bc911  mov     rsi, [r11+30h]
0x1800bc915  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bc91a  mov     rsp, r11
0x1800bc91d  pop     r14
0x1800bc91f  pop     rdi
0x1800bc920  pop     rbp
0x1800bc921  retn
```
