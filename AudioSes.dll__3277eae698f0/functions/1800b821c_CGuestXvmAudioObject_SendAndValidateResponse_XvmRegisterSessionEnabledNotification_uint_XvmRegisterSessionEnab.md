# CGuestXvmAudioObject::SendAndValidateResponse<XvmRegisterSessionEnabledNotification>(uint,XvmRegisterSessionEnabledNotification,XvmMessage * *,XvmRegisterSessionEnabledNotification * *)

- ea: `0x1800b821c`
- end: `0x1800b8562`
- name: `??$SendAndValidateResponse@UXvmRegisterSessionEnabledNotification@@@CGuestXvmAudioObject@@QEAAJIUXvmRegisterSessionEnabledNotification@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180081ad0`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a6fe8`
- `0x1800b821c`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b825e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b8349`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b825e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b8349`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b8292`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b8292`

## string_xrefs

- `0x1800b8275`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b82b4`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b84bf`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b8508`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmRegisterSessionEnabledNotification>(
        __int64 a1,
        unsigned int a2,
        char a3,
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
    v32 = 121;
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
            (unsigned int)&dword_18016776C,
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
          (unsigned int)byte_1801677E5,
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
        v18 = XvmMessage::CastTo<XvmRegisterSessionEnabledNotification>(v21, v39, v12);
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
0x1800b821c  mov     rax, rsp
0x1800b821f  mov     [rax+10h], rbx
0x1800b8223  mov     [rax+18h], rsi
0x1800b8227  mov     [rax+20h], r9
0x1800b822b  push    rbp
0x1800b822c  push    rdi
0x1800b822d  push    r14
0x1800b822f  lea     rbp, [rax-7E8h]
0x1800b8236  sub     rsp, 8D0h
0x1800b823d  movaps  xmmword ptr [rax-28h], xmm6
0x1800b8241  mov     bl, r8b
0x1800b8244  mov     r14d, edx
0x1800b8247  mov     rdi, rcx
0x1800b824a  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800b8252  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800b825a  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800b825e  call    cs:__imp_QueryPerformanceCounter
0x1800b8264  mov     esi, [rdi+40h]
0x1800b8267  test    esi, esi
0x1800b8269  jns     short loc_1800B828D
0x1800b826b  mov     rcx, [rbp+7E8h]; this
0x1800b8272  mov     r9d, esi; char *
0x1800b8275  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b827c  mov     edx, 4Fh ; 'O'; void *
0x1800b8281  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8286  mov     eax, esi
0x1800b8288  jmp     loc_1800B8545
0x1800b828d  mov     ecx, 810h; cb
0x1800b8292  call    cs:__imp_CoTaskMemAlloc
0x1800b8298  mov     rsi, rax
0x1800b829b  mov     [rsp+8E0h+var_878], rax
0x1800b82a0  test    rax, rax
0x1800b82a3  jnz     short loc_1800B82C8
0x1800b82a5  mov     rcx, [rbp+7E8h]; this
0x1800b82ac  mov     ebx, 8007000Eh
0x1800b82b1  mov     r9d, ebx; char *
0x1800b82b4  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b82bb  lea     edx, [rax+52h]; void *
0x1800b82be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b82c3  jmp     loc_1800B8543
0x1800b82c8  mov     [rbp+7E0h+Src], 0
0x1800b82d0  mov     [rbp+7E0h+var_824], 0
0x1800b82d7  xor     edx, edx; Val
0x1800b82d9  mov     r8d, 800h; Size
0x1800b82df  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800b82e3  call    memset_0
0x1800b82e8  mov     [rbp+7E0h+var_820], bl
0x1800b82eb  mov     [rbp+7E0h+var_828], 79h ; 'y'
0x1800b82f2  mov     rcx, rsi; void *
0x1800b82f5  lea     rdx, [rbp+7E0h+Src]; Src
0x1800b82f9  mov     r8d, 810h; Size
0x1800b82ff  call    memcpy_0
0x1800b8304  mov     rax, [rsp+8E0h+var_878]
0x1800b8309  mov     [rax+0Ch], r14d
0x1800b830d  lea     rax, [rbp+7E0h+arg_18]
0x1800b8314  mov     [rbp+7E0h+var_848], rax
0x1800b8318  lea     rax, [rsp+8E0h+var_878]
0x1800b831d  mov     [rbp+7E0h+var_840], rax
0x1800b8321  mov     [rbp+7E0h+var_838], 1
0x1800b8325  mov     rcx, [rdi+28h]
0x1800b8329  mov     rax, [rcx]
0x1800b832c  mov     r9d, 810h
0x1800b8332  mov     r8, [rsp+8E0h+var_878]
0x1800b8337  mov     edx, r14d
0x1800b833a  mov     rax, [rax+20h]
0x1800b833e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b8343  mov     ebx, eax
0x1800b8345  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800b8349  call    cs:__imp_QueryPerformanceCounter
0x1800b834f  xorps   xmm6, xmm6
0x1800b8352  cmp     qword ptr [rdi+48h], 0
0x1800b8357  jz      short loc_1800B837B
0x1800b8359  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800b835d  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800b8361  cvtsi2ss xmm6, rcx
0x1800b8366  mulss   xmm6, cs:__real@447a0000
0x1800b836e  xorps   xmm0, xmm0
0x1800b8371  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x1800b8377  divss   xmm6, xmm0
0x1800b837b  mov     rcx, [rsp+8E0h+var_878]
0x1800b8380  cmp     dword ptr [rcx+8], 1
0x1800b8384  jnz     loc_1800B8440
0x1800b838a  mov     [rsp+8E0h+var_870], 0
0x1800b8393  lea     rdx, [rsp+8E0h+var_870]
0x1800b8398  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b839d  test    eax, eax
0x1800b839f  js      loc_1800B84B1
0x1800b83a5  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b83aa  mov     r8, rax
0x1800b83ad  mov     ecx, [rax]
0x1800b83af  cmp     ecx, 4
0x1800b83b2  jbe     loc_1800B84B1
0x1800b83b8  mov     [rbp+7E0h+arg_0], ebx
0x1800b83be  movss   [rsp+8E0h+var_868], xmm6
0x1800b83c4  mov     [rbp+7E0h+var_860], rdi
0x1800b83c8  mov     rdx, [rsp+8E0h+var_870]
0x1800b83cd  mov     ecx, [rdx+10h]
0x1800b83d0  mov     [rsp+8E0h+var_864], ecx
0x1800b83d4  mov     ecx, [rdx+4]
0x1800b83d7  mov     [rsp+8E0h+var_880], ecx
0x1800b83db  mov     eax, [rdx+8]
0x1800b83de  mov     [rsp+8E0h+var_880+4], eax
0x1800b83e2  mov     eax, [rdx]
0x1800b83e4  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800b83e8  lea     rax, [rbp+7E0h+arg_0]
0x1800b83ef  mov     [rsp+8E0h+var_890], rax
0x1800b83f4  lea     rax, [rsp+8E0h+var_868]
0x1800b83f9  mov     [rsp+8E0h+var_898], rax
0x1800b83fe  lea     rax, [rbp+7E0h+var_860]
0x1800b8402  mov     [rsp+8E0h+var_8A0], rax
0x1800b8407  lea     rax, [rsp+8E0h+var_864]
0x1800b840c  mov     [rsp+8E0h+var_8A8], rax
0x1800b8411  lea     rax, [rsp+8E0h+var_880]
0x1800b8416  mov     [rsp+8E0h+var_8B0], rax
0x1800b841b  lea     rax, [rsp+8E0h+var_880+4]
0x1800b8420  mov     [rsp+8E0h+var_8B8], rax
0x1800b8425  lea     rax, [rsp+8E0h+var_870]
0x1800b842a  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800b842f  lea     rdx, dword_18016776C
0x1800b8436  mov     rcx, r8
0x1800b8439  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b843e  jmp     short loc_1800B84B1
0x1800b8440  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b8445  mov     ecx, [rax]
0x1800b8447  cmp     ecx, 4
0x1800b844a  jbe     short loc_1800B84B1
0x1800b844c  mov     [rbp+7E0h+arg_0], ebx
0x1800b8452  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800b8458  mov     [rbp+7E0h+var_860], rdi
0x1800b845c  mov     rcx, [rsp+8E0h+var_878]
0x1800b8461  mov     edx, [rcx+8]
0x1800b8464  mov     [rsp+8E0h+var_880+4], edx
0x1800b8468  mov     ecx, [rdi+30h]
0x1800b846b  mov     [rsp+8E0h+var_880], ecx
0x1800b846f  lea     rcx, [rbp+7E0h+arg_0]
0x1800b8476  mov     [rsp+8E0h+var_8A0], rcx
0x1800b847b  lea     rcx, [rsp+8E0h+var_870]
0x1800b8480  mov     [rsp+8E0h+var_8A8], rcx
0x1800b8485  lea     rcx, [rbp+7E0h+var_860]
0x1800b8489  mov     [rsp+8E0h+var_8B0], rcx
0x1800b848e  lea     rcx, [rsp+8E0h+var_880+4]
0x1800b8493  mov     [rsp+8E0h+var_8B8], rcx
0x1800b8498  lea     rcx, [rsp+8E0h+var_880]
0x1800b849d  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800b84a2  lea     rdx, byte_1801677E5
0x1800b84a9  mov     rcx, rax
0x1800b84ac  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b84b1  mov     rcx, [rbp+7E8h]; this
0x1800b84b8  test    ebx, ebx
0x1800b84ba  jns     short loc_1800B84DF
0x1800b84bc  mov     r9d, ebx; char *
0x1800b84bf  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b84c6  mov     edx, 81h; void *
0x1800b84cb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b84d0  mov     rax, [rdi]
0x1800b84d3  mov     rcx, rdi
0x1800b84d6  mov     rax, [rax+20h]
0x1800b84da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b84df  mov     ebx, [rdi+40h]
0x1800b84e2  test    ebx, ebx
0x1800b84e4  jns     short loc_1800B84ED
0x1800b84e6  mov     edx, 8Ah
0x1800b84eb  jmp     short loc_1800B84FE
0x1800b84ed  mov     rcx, [rsp+8E0h+var_878]
0x1800b84f2  mov     ebx, [rcx+4]
0x1800b84f5  test    ebx, ebx
0x1800b84f7  jns     short loc_1800B8516
0x1800b84f9  mov     edx, 8Ch; void *
0x1800b84fe  mov     r9d, ebx; char *
0x1800b8501  mov     rcx, [rbp+7E8h]; this
0x1800b8508  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b850f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b8514  jmp     short loc_1800B8534
0x1800b8516  mov     rdx, [rbp+7E0h+arg_20]
0x1800b851d  call    ??$CastTo@UXvmRegisterSessionEnabledNotification@@@XvmMessage@@QEAAJPEAPEAUXvmRegisterSessionEnabledNotification@@@Z; XvmMessage::CastTo<XvmRegisterSessionEnabledNotification>(XvmRegisterSessionEnabledNotification * *)
0x1800b8522  mov     ebx, eax
0x1800b8524  test    eax, eax
0x1800b8526  jns     short loc_1800B8532
0x1800b8528  mov     r9d, eax
0x1800b852b  mov     edx, 8Dh
0x1800b8530  jmp     short loc_1800B8501
0x1800b8532  xor     ebx, ebx
0x1800b8534  mov     rcx, [rbp+7E0h+arg_18]
0x1800b853b  mov     rax, [rsp+8E0h+var_878]
0x1800b8540  mov     [rcx], rax
0x1800b8543  mov     eax, ebx
0x1800b8545  lea     r11, [rsp+8E0h+var_10]
0x1800b854d  mov     rbx, [r11+28h]
0x1800b8551  mov     rsi, [r11+30h]
0x1800b8555  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b855a  mov     rsp, r11
0x1800b855d  pop     r14
0x1800b855f  pop     rdi
0x1800b8560  pop     rbp
0x1800b8561  retn
```
