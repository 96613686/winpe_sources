# CGuestXvmAudioObject::SendAndValidateResponse<XvmSetDisplayName>(uint,XvmSetDisplayName,XvmMessage * *,XvmSetDisplayName * *)

- ea: `0x1800be7f8`
- end: `0x1800beb4a`
- name: `??$SendAndValidateResponse@UXvmSetDisplayName@@@CGuestXvmAudioObject@@QEAAJIUXvmSetDisplayName@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `850`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c2210`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800b95b8`
- `0x1800be7f8`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800be839`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800be931`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800be839`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800be931`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be86d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be86d`

## string_xrefs

- `0x1800be850`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800be88f`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800beaa7`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800beaf0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmSetDisplayName>(
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
    memcpy_0(v34, a3, 0x7E0u);
    v32 = 27;
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
            (unsigned int)&unk_18016817A,
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
          (unsigned int)&unk_1801681F3,
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
        v18 = XvmMessage::CastTo<XvmSetDisplayName>(v21, v39, v12);
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
0x1800be7f8  mov     rax, rsp
0x1800be7fb  mov     [rax+10h], rbx
0x1800be7ff  mov     [rax+18h], rsi
0x1800be803  mov     [rax+20h], r9
0x1800be807  push    rbp
0x1800be808  push    rdi
0x1800be809  push    r14
0x1800be80b  lea     rbp, [rax-7E8h]
0x1800be812  sub     rsp, 8D0h
0x1800be819  movaps  xmmword ptr [rax-28h], xmm6
0x1800be81d  mov     r14, r8
0x1800be820  mov     esi, edx
0x1800be822  mov     rbx, rcx
0x1800be825  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800be82d  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800be835  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800be839  call    cs:__imp_QueryPerformanceCounter
0x1800be83f  mov     edi, [rbx+40h]
0x1800be842  test    edi, edi
0x1800be844  jns     short loc_1800BE868
0x1800be846  mov     rcx, [rbp+7E8h]; this
0x1800be84d  mov     r9d, edi; char *
0x1800be850  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800be857  mov     edx, 4Fh ; 'O'; void *
0x1800be85c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be861  mov     eax, edi
0x1800be863  jmp     loc_1800BEB2D
0x1800be868  mov     ecx, 810h; cb
0x1800be86d  call    cs:__imp_CoTaskMemAlloc
0x1800be873  mov     rdi, rax
0x1800be876  mov     [rsp+8E0h+var_878], rax
0x1800be87b  test    rax, rax
0x1800be87e  jnz     short loc_1800BE8A3
0x1800be880  mov     rcx, [rbp+7E8h]; this
0x1800be887  mov     ebx, 8007000Eh
0x1800be88c  mov     r9d, ebx; char *
0x1800be88f  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800be896  lea     edx, [rax+52h]; void *
0x1800be899  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be89e  jmp     loc_1800BEB2B
0x1800be8a3  mov     [rbp+7E0h+Src], 0
0x1800be8ab  mov     [rbp+7E0h+var_824], 0
0x1800be8b2  xor     edx, edx; Val
0x1800be8b4  mov     r8d, 800h; Size
0x1800be8ba  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800be8be  call    memset_0
0x1800be8c3  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800be8c7  mov     rdx, r14; Src
0x1800be8ca  mov     r8d, 7E0h; Size
0x1800be8d0  call    memcpy_0
0x1800be8d5  mov     [rbp+7E0h+var_828], 1Bh
0x1800be8dc  mov     rcx, rdi; void *
0x1800be8df  lea     rdx, [rbp+7E0h+Src]; Src
0x1800be8e3  mov     r8d, 810h; Size
0x1800be8e9  call    memcpy_0
0x1800be8ee  mov     rax, [rsp+8E0h+var_878]
0x1800be8f3  mov     [rax+0Ch], esi
0x1800be8f6  lea     rax, [rbp+7E0h+arg_18]
0x1800be8fd  mov     [rbp+7E0h+var_848], rax
0x1800be901  lea     rax, [rsp+8E0h+var_878]
0x1800be906  mov     [rbp+7E0h+var_840], rax
0x1800be90a  mov     [rbp+7E0h+var_838], 1
0x1800be90e  mov     rcx, [rbx+28h]
0x1800be912  mov     rax, [rcx]
0x1800be915  mov     r9d, 810h
0x1800be91b  mov     r8, [rsp+8E0h+var_878]
0x1800be920  mov     edx, esi
0x1800be922  mov     rax, [rax+20h]
0x1800be926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be92b  mov     edi, eax
0x1800be92d  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800be931  call    cs:__imp_QueryPerformanceCounter
0x1800be937  xorps   xmm6, xmm6
0x1800be93a  cmp     qword ptr [rbx+48h], 0
0x1800be93f  jz      short loc_1800BE963
0x1800be941  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800be945  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800be949  cvtsi2ss xmm6, rcx
0x1800be94e  mulss   xmm6, cs:__real@447a0000
0x1800be956  xorps   xmm0, xmm0
0x1800be959  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800be95f  divss   xmm6, xmm0
0x1800be963  mov     rcx, [rsp+8E0h+var_878]
0x1800be968  cmp     dword ptr [rcx+8], 1
0x1800be96c  jnz     loc_1800BEA28
0x1800be972  mov     [rsp+8E0h+var_870], 0
0x1800be97b  lea     rdx, [rsp+8E0h+var_870]
0x1800be980  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800be985  test    eax, eax
0x1800be987  js      loc_1800BEA99
0x1800be98d  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800be992  mov     r8, rax
0x1800be995  mov     ecx, [rax]
0x1800be997  cmp     ecx, 4
0x1800be99a  jbe     loc_1800BEA99
0x1800be9a0  mov     [rbp+7E0h+arg_0], edi
0x1800be9a6  movss   [rsp+8E0h+var_868], xmm6
0x1800be9ac  mov     [rbp+7E0h+var_860], rbx
0x1800be9b0  mov     rdx, [rsp+8E0h+var_870]
0x1800be9b5  mov     ecx, [rdx+10h]
0x1800be9b8  mov     [rsp+8E0h+var_864], ecx
0x1800be9bc  mov     ecx, [rdx+4]
0x1800be9bf  mov     [rsp+8E0h+var_880], ecx
0x1800be9c3  mov     eax, [rdx+8]
0x1800be9c6  mov     [rsp+8E0h+var_880+4], eax
0x1800be9ca  mov     eax, [rdx]
0x1800be9cc  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800be9d0  lea     rax, [rbp+7E0h+arg_0]
0x1800be9d7  mov     [rsp+8E0h+var_890], rax
0x1800be9dc  lea     rax, [rsp+8E0h+var_868]
0x1800be9e1  mov     [rsp+8E0h+var_898], rax
0x1800be9e6  lea     rax, [rbp+7E0h+var_860]
0x1800be9ea  mov     [rsp+8E0h+var_8A0], rax
0x1800be9ef  lea     rax, [rsp+8E0h+var_864]
0x1800be9f4  mov     [rsp+8E0h+var_8A8], rax
0x1800be9f9  lea     rax, [rsp+8E0h+var_880]
0x1800be9fe  mov     [rsp+8E0h+var_8B0], rax
0x1800bea03  lea     rax, [rsp+8E0h+var_880+4]
0x1800bea08  mov     [rsp+8E0h+var_8B8], rax
0x1800bea0d  lea     rax, [rsp+8E0h+var_870]
0x1800bea12  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bea17  lea     rdx, unk_18016817A
0x1800bea1e  mov     rcx, r8
0x1800bea21  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bea26  jmp     short loc_1800BEA99
0x1800bea28  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bea2d  mov     ecx, [rax]
0x1800bea2f  cmp     ecx, 4
0x1800bea32  jbe     short loc_1800BEA99
0x1800bea34  mov     [rbp+7E0h+arg_0], edi
0x1800bea3a  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bea40  mov     [rbp+7E0h+var_860], rbx
0x1800bea44  mov     rcx, [rsp+8E0h+var_878]
0x1800bea49  mov     edx, [rcx+8]
0x1800bea4c  mov     [rsp+8E0h+var_880+4], edx
0x1800bea50  mov     ecx, [rbx+30h]
0x1800bea53  mov     [rsp+8E0h+var_880], ecx
0x1800bea57  lea     rcx, [rbp+7E0h+arg_0]
0x1800bea5e  mov     [rsp+8E0h+var_8A0], rcx
0x1800bea63  lea     rcx, [rsp+8E0h+var_870]
0x1800bea68  mov     [rsp+8E0h+var_8A8], rcx
0x1800bea6d  lea     rcx, [rbp+7E0h+var_860]
0x1800bea71  mov     [rsp+8E0h+var_8B0], rcx
0x1800bea76  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bea7b  mov     [rsp+8E0h+var_8B8], rcx
0x1800bea80  lea     rcx, [rsp+8E0h+var_880]
0x1800bea85  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bea8a  lea     rdx, unk_1801681F3
0x1800bea91  mov     rcx, rax
0x1800bea94  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bea99  mov     rcx, [rbp+7E8h]; this
0x1800beaa0  test    edi, edi
0x1800beaa2  jns     short loc_1800BEAC7
0x1800beaa4  mov     r9d, edi; char *
0x1800beaa7  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800beaae  mov     edx, 81h; void *
0x1800beab3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800beab8  mov     rax, [rbx]
0x1800beabb  mov     rcx, rbx
0x1800beabe  mov     rax, [rax+20h]
0x1800beac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beac7  mov     ebx, [rbx+40h]
0x1800beaca  test    ebx, ebx
0x1800beacc  jns     short loc_1800BEAD5
0x1800beace  mov     edx, 8Ah
0x1800bead3  jmp     short loc_1800BEAE6
0x1800bead5  mov     rcx, [rsp+8E0h+var_878]
0x1800beada  mov     ebx, [rcx+4]
0x1800beadd  test    ebx, ebx
0x1800beadf  jns     short loc_1800BEAFE
0x1800beae1  mov     edx, 8Ch; void *
0x1800beae6  mov     r9d, ebx; char *
0x1800beae9  mov     rcx, [rbp+7E8h]; this
0x1800beaf0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800beaf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800beafc  jmp     short loc_1800BEB1C
0x1800beafe  mov     rdx, [rbp+7E0h+arg_20]
0x1800beb05  call    ??$CastTo@UXvmSetDisplayName@@@XvmMessage@@QEAAJPEAPEAUXvmSetDisplayName@@@Z; XvmMessage::CastTo<XvmSetDisplayName>(XvmSetDisplayName * *)
0x1800beb0a  mov     ebx, eax
0x1800beb0c  test    eax, eax
0x1800beb0e  jns     short loc_1800BEB1A
0x1800beb10  mov     r9d, eax
0x1800beb13  mov     edx, 8Dh
0x1800beb18  jmp     short loc_1800BEAE9
0x1800beb1a  xor     ebx, ebx
0x1800beb1c  mov     rcx, [rbp+7E0h+arg_18]
0x1800beb23  mov     rax, [rsp+8E0h+var_878]
0x1800beb28  mov     [rcx], rax
0x1800beb2b  mov     eax, ebx
0x1800beb2d  lea     r11, [rsp+8E0h+var_10]
0x1800beb35  mov     rbx, [r11+28h]
0x1800beb39  mov     rsi, [r11+30h]
0x1800beb3d  movaps  xmm6, xmmword ptr [r11-10h]
0x1800beb42  mov     rsp, r11
0x1800beb45  pop     r14
0x1800beb47  pop     rdi
0x1800beb48  pop     rbp
0x1800beb49  retn
```
