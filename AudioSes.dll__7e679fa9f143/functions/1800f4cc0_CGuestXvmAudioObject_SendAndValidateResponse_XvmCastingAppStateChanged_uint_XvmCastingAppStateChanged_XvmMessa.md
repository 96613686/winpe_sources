# CGuestXvmAudioObject::SendAndValidateResponse<XvmCastingAppStateChanged>(uint,XvmCastingAppStateChanged,XvmMessage * *,XvmCastingAppStateChanged * *)

- ea: `0x1800f4cc0`
- end: `0x1800f5006`
- name: `??$SendAndValidateResponse@UXvmCastingAppStateChanged@@@CGuestXvmAudioObject@@QEAAJIUXvmCastingAppStateChanged@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005eae0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800f4b70`
- `0x1800f4cc0`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f4d02`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f4ded`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f4d02`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f4ded`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f4d36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800f4d36`

## string_xrefs

- `0x1800f4d19`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800f4d58`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800f4f63`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800f4fac`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmCastingAppStateChanged>(
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
    v32 = 101;
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
            (unsigned int)&unk_180170566,
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
          (unsigned int)&unk_18017038D,
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
        v18 = XvmMessage::CastTo<XvmCastingAppStateChanged>(v21, v39, v12);
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
0x1800f4cc0  mov     rax, rsp
0x1800f4cc3  mov     [rax+10h], rbx
0x1800f4cc7  mov     [rax+18h], rsi
0x1800f4ccb  mov     [rax+20h], r9
0x1800f4ccf  push    rbp
0x1800f4cd0  push    rdi
0x1800f4cd1  push    r14
0x1800f4cd3  lea     rbp, [rax-7E8h]
0x1800f4cda  sub     rsp, 8D0h
0x1800f4ce1  movaps  xmmword ptr [rax-28h], xmm6
0x1800f4ce5  mov     ebx, r8d
0x1800f4ce8  mov     r14d, edx
0x1800f4ceb  mov     rdi, rcx
0x1800f4cee  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800f4cf6  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800f4cfe  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800f4d02  call    cs:__imp_QueryPerformanceCounter
0x1800f4d08  mov     esi, [rdi+40h]
0x1800f4d0b  test    esi, esi
0x1800f4d0d  jns     short loc_1800F4D31
0x1800f4d0f  mov     rcx, [rbp+7E8h]; this
0x1800f4d16  mov     r9d, esi; char *
0x1800f4d19  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800f4d20  mov     edx, 4Fh ; 'O'; void *
0x1800f4d25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f4d2a  mov     eax, esi
0x1800f4d2c  jmp     loc_1800F4FE9
0x1800f4d31  mov     ecx, 810h; cb
0x1800f4d36  call    cs:__imp_CoTaskMemAlloc
0x1800f4d3c  mov     rsi, rax
0x1800f4d3f  mov     [rsp+8E0h+var_878], rax
0x1800f4d44  test    rax, rax
0x1800f4d47  jnz     short loc_1800F4D6C
0x1800f4d49  mov     rcx, [rbp+7E8h]; this
0x1800f4d50  mov     ebx, 8007000Eh
0x1800f4d55  mov     r9d, ebx; char *
0x1800f4d58  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800f4d5f  lea     edx, [rax+52h]; void *
0x1800f4d62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f4d67  jmp     loc_1800F4FE7
0x1800f4d6c  mov     [rbp+7E0h+Src], 0
0x1800f4d74  mov     [rbp+7E0h+var_824], 0
0x1800f4d7b  xor     edx, edx; Val
0x1800f4d7d  mov     r8d, 800h; Size
0x1800f4d83  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800f4d87  call    memset_0
0x1800f4d8c  mov     [rbp+7E0h+var_820], ebx
0x1800f4d8f  mov     [rbp+7E0h+var_828], 65h ; 'e'
0x1800f4d96  mov     rcx, rsi; void *
0x1800f4d99  lea     rdx, [rbp+7E0h+Src]; Src
0x1800f4d9d  mov     r8d, 810h; Size
0x1800f4da3  call    memcpy_0
0x1800f4da8  mov     rax, [rsp+8E0h+var_878]
0x1800f4dad  mov     [rax+0Ch], r14d
0x1800f4db1  lea     rax, [rbp+7E0h+arg_18]
0x1800f4db8  mov     [rbp+7E0h+var_848], rax
0x1800f4dbc  lea     rax, [rsp+8E0h+var_878]
0x1800f4dc1  mov     [rbp+7E0h+var_840], rax
0x1800f4dc5  mov     [rbp+7E0h+var_838], 1
0x1800f4dc9  mov     rcx, [rdi+28h]
0x1800f4dcd  mov     rax, [rcx]
0x1800f4dd0  mov     r9d, 810h
0x1800f4dd6  mov     r8, [rsp+8E0h+var_878]
0x1800f4ddb  mov     edx, r14d
0x1800f4dde  mov     rax, [rax+20h]
0x1800f4de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4de7  mov     ebx, eax
0x1800f4de9  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800f4ded  call    cs:__imp_QueryPerformanceCounter
0x1800f4df3  xorps   xmm6, xmm6
0x1800f4df6  cmp     qword ptr [rdi+48h], 0
0x1800f4dfb  jz      short loc_1800F4E1F
0x1800f4dfd  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800f4e01  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800f4e05  cvtsi2ss xmm6, rcx
0x1800f4e0a  mulss   xmm6, cs:__real@447a0000
0x1800f4e12  xorps   xmm0, xmm0
0x1800f4e15  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800f4e1b  divss   xmm6, xmm0
0x1800f4e1f  mov     rcx, [rsp+8E0h+var_878]
0x1800f4e24  cmp     dword ptr [rcx+8], 1
0x1800f4e28  jnz     loc_1800F4EE4
0x1800f4e2e  mov     [rsp+8E0h+var_870], 0
0x1800f4e37  lea     rdx, [rsp+8E0h+var_870]
0x1800f4e3c  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800f4e41  test    eax, eax
0x1800f4e43  js      loc_1800F4F55
0x1800f4e49  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800f4e4e  mov     r8, rax
0x1800f4e51  mov     ecx, [rax]
0x1800f4e53  cmp     ecx, 4
0x1800f4e56  jbe     loc_1800F4F55
0x1800f4e5c  mov     [rbp+7E0h+arg_0], ebx
0x1800f4e62  movss   [rsp+8E0h+var_868], xmm6
0x1800f4e68  mov     [rbp+7E0h+var_860], rdi
0x1800f4e6c  mov     rdx, [rsp+8E0h+var_870]
0x1800f4e71  mov     ecx, [rdx+10h]
0x1800f4e74  mov     [rsp+8E0h+var_864], ecx
0x1800f4e78  mov     ecx, [rdx+4]
0x1800f4e7b  mov     [rsp+8E0h+var_880], ecx
0x1800f4e7f  mov     eax, [rdx+8]
0x1800f4e82  mov     [rsp+8E0h+var_880+4], eax
0x1800f4e86  mov     eax, [rdx]
0x1800f4e88  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800f4e8c  lea     rax, [rbp+7E0h+arg_0]
0x1800f4e93  mov     [rsp+8E0h+var_890], rax
0x1800f4e98  lea     rax, [rsp+8E0h+var_868]
0x1800f4e9d  mov     [rsp+8E0h+var_898], rax
0x1800f4ea2  lea     rax, [rbp+7E0h+var_860]
0x1800f4ea6  mov     [rsp+8E0h+var_8A0], rax
0x1800f4eab  lea     rax, [rsp+8E0h+var_864]
0x1800f4eb0  mov     [rsp+8E0h+var_8A8], rax
0x1800f4eb5  lea     rax, [rsp+8E0h+var_880]
0x1800f4eba  mov     [rsp+8E0h+var_8B0], rax
0x1800f4ebf  lea     rax, [rsp+8E0h+var_880+4]
0x1800f4ec4  mov     [rsp+8E0h+var_8B8], rax
0x1800f4ec9  lea     rax, [rsp+8E0h+var_870]
0x1800f4ece  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800f4ed3  lea     rdx, unk_180170566
0x1800f4eda  mov     rcx, r8
0x1800f4edd  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800f4ee2  jmp     short loc_1800F4F55
0x1800f4ee4  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800f4ee9  mov     ecx, [rax]
0x1800f4eeb  cmp     ecx, 4
0x1800f4eee  jbe     short loc_1800F4F55
0x1800f4ef0  mov     [rbp+7E0h+arg_0], ebx
0x1800f4ef6  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800f4efc  mov     [rbp+7E0h+var_860], rdi
0x1800f4f00  mov     rcx, [rsp+8E0h+var_878]
0x1800f4f05  mov     edx, [rcx+8]
0x1800f4f08  mov     [rsp+8E0h+var_880+4], edx
0x1800f4f0c  mov     ecx, [rdi+30h]
0x1800f4f0f  mov     [rsp+8E0h+var_880], ecx
0x1800f4f13  lea     rcx, [rbp+7E0h+arg_0]
0x1800f4f1a  mov     [rsp+8E0h+var_8A0], rcx
0x1800f4f1f  lea     rcx, [rsp+8E0h+var_870]
0x1800f4f24  mov     [rsp+8E0h+var_8A8], rcx
0x1800f4f29  lea     rcx, [rbp+7E0h+var_860]
0x1800f4f2d  mov     [rsp+8E0h+var_8B0], rcx
0x1800f4f32  lea     rcx, [rsp+8E0h+var_880+4]
0x1800f4f37  mov     [rsp+8E0h+var_8B8], rcx
0x1800f4f3c  lea     rcx, [rsp+8E0h+var_880]
0x1800f4f41  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800f4f46  lea     rdx, unk_18017038D
0x1800f4f4d  mov     rcx, rax
0x1800f4f50  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800f4f55  mov     rcx, [rbp+7E8h]; this
0x1800f4f5c  test    ebx, ebx
0x1800f4f5e  jns     short loc_1800F4F83
0x1800f4f60  mov     r9d, ebx; char *
0x1800f4f63  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800f4f6a  mov     edx, 81h; void *
0x1800f4f6f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f4f74  mov     rax, [rdi]
0x1800f4f77  mov     rcx, rdi
0x1800f4f7a  mov     rax, [rax+20h]
0x1800f4f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4f83  mov     ebx, [rdi+40h]
0x1800f4f86  test    ebx, ebx
0x1800f4f88  jns     short loc_1800F4F91
0x1800f4f8a  mov     edx, 8Ah
0x1800f4f8f  jmp     short loc_1800F4FA2
0x1800f4f91  mov     rcx, [rsp+8E0h+var_878]
0x1800f4f96  mov     ebx, [rcx+4]
0x1800f4f99  test    ebx, ebx
0x1800f4f9b  jns     short loc_1800F4FBA
0x1800f4f9d  mov     edx, 8Ch; void *
0x1800f4fa2  mov     r9d, ebx; char *
0x1800f4fa5  mov     rcx, [rbp+7E8h]; this
0x1800f4fac  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800f4fb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f4fb8  jmp     short loc_1800F4FD8
0x1800f4fba  mov     rdx, [rbp+7E0h+arg_20]
0x1800f4fc1  call    ??$CastTo@UXvmCastingAppStateChanged@@@XvmMessage@@QEAAJPEAPEAUXvmCastingAppStateChanged@@@Z; XvmMessage::CastTo<XvmCastingAppStateChanged>(XvmCastingAppStateChanged * *)
0x1800f4fc6  mov     ebx, eax
0x1800f4fc8  test    eax, eax
0x1800f4fca  jns     short loc_1800F4FD6
0x1800f4fcc  mov     r9d, eax
0x1800f4fcf  mov     edx, 8Dh
0x1800f4fd4  jmp     short loc_1800F4FA5
0x1800f4fd6  xor     ebx, ebx
0x1800f4fd8  mov     rcx, [rbp+7E0h+arg_18]
0x1800f4fdf  mov     rax, [rsp+8E0h+var_878]
0x1800f4fe4  mov     [rcx], rax
0x1800f4fe7  mov     eax, ebx
0x1800f4fe9  lea     r11, [rsp+8E0h+var_10]
0x1800f4ff1  mov     rbx, [r11+28h]
0x1800f4ff5  mov     rsi, [r11+30h]
0x1800f4ff9  movaps  xmm6, xmmword ptr [r11-10h]
0x1800f4ffe  mov     rsp, r11
0x1800f5001  pop     r14
0x1800f5003  pop     rdi
0x1800f5004  pop     rbp
0x1800f5005  retn
```
