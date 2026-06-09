# CGuestXvmAudioObject::SendAndValidateResponse<XvmPreReset>(uint,XvmPreReset,XvmMessage * *,XvmPreReset * *)

- ea: `0x18010d734`
- end: `0x18010da7a`
- name: `??$SendAndValidateResponse@UXvmPreReset@@@CGuestXvmAudioObject@@QEAAJIUXvmPreReset@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18010e9a0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1801021e8`
- `0x18010d734`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010d776`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010d861`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010d776`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010d861`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010d7aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010d7aa`

## string_xrefs

- `0x18010d78d`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18010d7cc`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18010d9d7`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18010da20`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmPreReset>(__int64 a1, unsigned int a2, char a3, ...)
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
    v32 = 70;
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
            (unsigned int)&unk_180172D35,
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
          (unsigned int)&unk_180172CE8,
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
        v18 = XvmMessage::CastTo<XvmPreReset>(v21, v39, v12);
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
0x18010d734  mov     rax, rsp
0x18010d737  mov     [rax+10h], rbx
0x18010d73b  mov     [rax+18h], rsi
0x18010d73f  mov     [rax+20h], r9
0x18010d743  push    rbp
0x18010d744  push    rdi
0x18010d745  push    r14
0x18010d747  lea     rbp, [rax-7E8h]
0x18010d74e  sub     rsp, 8D0h
0x18010d755  movaps  xmmword ptr [rax-28h], xmm6
0x18010d759  mov     bl, r8b
0x18010d75c  mov     r14d, edx
0x18010d75f  mov     rdi, rcx
0x18010d762  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x18010d76a  mov     qword ptr [rbp+7E0h+var_858], 0
0x18010d772  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x18010d776  call    cs:__imp_QueryPerformanceCounter
0x18010d77c  mov     esi, [rdi+40h]
0x18010d77f  test    esi, esi
0x18010d781  jns     short loc_18010D7A5
0x18010d783  mov     rcx, [rbp+7E8h]; this
0x18010d78a  mov     r9d, esi; char *
0x18010d78d  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010d794  mov     edx, 4Fh ; 'O'; void *
0x18010d799  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d79e  mov     eax, esi
0x18010d7a0  jmp     loc_18010DA5D
0x18010d7a5  mov     ecx, 810h; cb
0x18010d7aa  call    cs:__imp_CoTaskMemAlloc
0x18010d7b0  mov     rsi, rax
0x18010d7b3  mov     [rsp+8E0h+var_878], rax
0x18010d7b8  test    rax, rax
0x18010d7bb  jnz     short loc_18010D7E0
0x18010d7bd  mov     rcx, [rbp+7E8h]; this
0x18010d7c4  mov     ebx, 8007000Eh
0x18010d7c9  mov     r9d, ebx; char *
0x18010d7cc  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010d7d3  lea     edx, [rax+52h]; void *
0x18010d7d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010d7db  jmp     loc_18010DA5B
0x18010d7e0  mov     [rbp+7E0h+Src], 0
0x18010d7e8  mov     [rbp+7E0h+var_824], 0
0x18010d7ef  xor     edx, edx; Val
0x18010d7f1  mov     r8d, 800h; Size
0x18010d7f7  lea     rcx, [rbp+7E0h+var_820]; void *
0x18010d7fb  call    memset_0
0x18010d800  mov     [rbp+7E0h+var_820], bl
0x18010d803  mov     [rbp+7E0h+var_828], 46h ; 'F'
0x18010d80a  mov     rcx, rsi; void *
0x18010d80d  lea     rdx, [rbp+7E0h+Src]; Src
0x18010d811  mov     r8d, 810h; Size
0x18010d817  call    memcpy_0
0x18010d81c  mov     rax, [rsp+8E0h+var_878]
0x18010d821  mov     [rax+0Ch], r14d
0x18010d825  lea     rax, [rbp+7E0h+arg_18]
0x18010d82c  mov     [rbp+7E0h+var_848], rax
0x18010d830  lea     rax, [rsp+8E0h+var_878]
0x18010d835  mov     [rbp+7E0h+var_840], rax
0x18010d839  mov     [rbp+7E0h+var_838], 1
0x18010d83d  mov     rcx, [rdi+28h]
0x18010d841  mov     rax, [rcx]
0x18010d844  mov     r9d, 810h
0x18010d84a  mov     r8, [rsp+8E0h+var_878]
0x18010d84f  mov     edx, r14d
0x18010d852  mov     rax, [rax+20h]
0x18010d856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d85b  mov     ebx, eax
0x18010d85d  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x18010d861  call    cs:__imp_QueryPerformanceCounter
0x18010d867  xorps   xmm6, xmm6
0x18010d86a  cmp     qword ptr [rdi+48h], 0
0x18010d86f  jz      short loc_18010D893
0x18010d871  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x18010d875  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x18010d879  cvtsi2ss xmm6, rcx
0x18010d87e  mulss   xmm6, cs:__real@447a0000
0x18010d886  xorps   xmm0, xmm0
0x18010d889  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x18010d88f  divss   xmm6, xmm0
0x18010d893  mov     rcx, [rsp+8E0h+var_878]
0x18010d898  cmp     dword ptr [rcx+8], 1
0x18010d89c  jnz     loc_18010D958
0x18010d8a2  mov     [rsp+8E0h+var_870], 0
0x18010d8ab  lea     rdx, [rsp+8E0h+var_870]
0x18010d8b0  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x18010d8b5  test    eax, eax
0x18010d8b7  js      loc_18010D9C9
0x18010d8bd  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x18010d8c2  mov     r8, rax
0x18010d8c5  mov     ecx, [rax]
0x18010d8c7  cmp     ecx, 4
0x18010d8ca  jbe     loc_18010D9C9
0x18010d8d0  mov     [rbp+7E0h+arg_0], ebx
0x18010d8d6  movss   [rsp+8E0h+var_868], xmm6
0x18010d8dc  mov     [rbp+7E0h+var_860], rdi
0x18010d8e0  mov     rdx, [rsp+8E0h+var_870]
0x18010d8e5  mov     ecx, [rdx+10h]
0x18010d8e8  mov     [rsp+8E0h+var_864], ecx
0x18010d8ec  mov     ecx, [rdx+4]
0x18010d8ef  mov     [rsp+8E0h+var_880], ecx
0x18010d8f3  mov     eax, [rdx+8]
0x18010d8f6  mov     [rsp+8E0h+var_880+4], eax
0x18010d8fa  mov     eax, [rdx]
0x18010d8fc  mov     dword ptr [rsp+8E0h+var_870], eax
0x18010d900  lea     rax, [rbp+7E0h+arg_0]
0x18010d907  mov     [rsp+8E0h+var_890], rax
0x18010d90c  lea     rax, [rsp+8E0h+var_868]
0x18010d911  mov     [rsp+8E0h+var_898], rax
0x18010d916  lea     rax, [rbp+7E0h+var_860]
0x18010d91a  mov     [rsp+8E0h+var_8A0], rax
0x18010d91f  lea     rax, [rsp+8E0h+var_864]
0x18010d924  mov     [rsp+8E0h+var_8A8], rax
0x18010d929  lea     rax, [rsp+8E0h+var_880]
0x18010d92e  mov     [rsp+8E0h+var_8B0], rax
0x18010d933  lea     rax, [rsp+8E0h+var_880+4]
0x18010d938  mov     [rsp+8E0h+var_8B8], rax
0x18010d93d  lea     rax, [rsp+8E0h+var_870]
0x18010d942  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x18010d947  lea     rdx, unk_180172D35
0x18010d94e  mov     rcx, r8
0x18010d951  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18010d956  jmp     short loc_18010D9C9
0x18010d958  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x18010d95d  mov     ecx, [rax]
0x18010d95f  cmp     ecx, 4
0x18010d962  jbe     short loc_18010D9C9
0x18010d964  mov     [rbp+7E0h+arg_0], ebx
0x18010d96a  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x18010d970  mov     [rbp+7E0h+var_860], rdi
0x18010d974  mov     rcx, [rsp+8E0h+var_878]
0x18010d979  mov     edx, [rcx+8]
0x18010d97c  mov     [rsp+8E0h+var_880+4], edx
0x18010d980  mov     ecx, [rdi+30h]
0x18010d983  mov     [rsp+8E0h+var_880], ecx
0x18010d987  lea     rcx, [rbp+7E0h+arg_0]
0x18010d98e  mov     [rsp+8E0h+var_8A0], rcx
0x18010d993  lea     rcx, [rsp+8E0h+var_870]
0x18010d998  mov     [rsp+8E0h+var_8A8], rcx
0x18010d99d  lea     rcx, [rbp+7E0h+var_860]
0x18010d9a1  mov     [rsp+8E0h+var_8B0], rcx
0x18010d9a6  lea     rcx, [rsp+8E0h+var_880+4]
0x18010d9ab  mov     [rsp+8E0h+var_8B8], rcx
0x18010d9b0  lea     rcx, [rsp+8E0h+var_880]
0x18010d9b5  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x18010d9ba  lea     rdx, unk_180172CE8
0x18010d9c1  mov     rcx, rax
0x18010d9c4  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18010d9c9  mov     rcx, [rbp+7E8h]; this
0x18010d9d0  test    ebx, ebx
0x18010d9d2  jns     short loc_18010D9F7
0x18010d9d4  mov     r9d, ebx; char *
0x18010d9d7  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010d9de  mov     edx, 81h; void *
0x18010d9e3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010d9e8  mov     rax, [rdi]
0x18010d9eb  mov     rcx, rdi
0x18010d9ee  mov     rax, [rax+20h]
0x18010d9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010d9f7  mov     ebx, [rdi+40h]
0x18010d9fa  test    ebx, ebx
0x18010d9fc  jns     short loc_18010DA05
0x18010d9fe  mov     edx, 8Ah
0x18010da03  jmp     short loc_18010DA16
0x18010da05  mov     rcx, [rsp+8E0h+var_878]
0x18010da0a  mov     ebx, [rcx+4]
0x18010da0d  test    ebx, ebx
0x18010da0f  jns     short loc_18010DA2E
0x18010da11  mov     edx, 8Ch; void *
0x18010da16  mov     r9d, ebx; char *
0x18010da19  mov     rcx, [rbp+7E8h]; this
0x18010da20  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010da27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010da2c  jmp     short loc_18010DA4C
0x18010da2e  mov     rdx, [rbp+7E0h+arg_20]
0x18010da35  call    ??$CastTo@UXvmPreReset@@@XvmMessage@@QEAAJPEAPEAUXvmPreReset@@@Z; XvmMessage::CastTo<XvmPreReset>(XvmPreReset * *)
0x18010da3a  mov     ebx, eax
0x18010da3c  test    eax, eax
0x18010da3e  jns     short loc_18010DA4A
0x18010da40  mov     r9d, eax
0x18010da43  mov     edx, 8Dh
0x18010da48  jmp     short loc_18010DA19
0x18010da4a  xor     ebx, ebx
0x18010da4c  mov     rcx, [rbp+7E0h+arg_18]
0x18010da53  mov     rax, [rsp+8E0h+var_878]
0x18010da58  mov     [rcx], rax
0x18010da5b  mov     eax, ebx
0x18010da5d  lea     r11, [rsp+8E0h+var_10]
0x18010da65  mov     rbx, [r11+28h]
0x18010da69  mov     rsi, [r11+30h]
0x18010da6d  movaps  xmm6, xmmword ptr [r11-10h]
0x18010da72  mov     rsp, r11
0x18010da75  pop     r14
0x18010da77  pop     rdi
0x18010da78  pop     rbp
0x18010da79  retn
```
