# CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(uint,XvmActivateProxyAudioObject,XvmMessage * *,XvmActivateProxyAudioObject * *)

- ea: `0x1800994e8`
- end: `0x18009983a`
- name: `??$SendAndValidateResponse@UXvmActivateProxyAudioObject@@@CGuestXvmAudioObject@@QEAAJIUXvmActivateProxyAudioObject@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `850`
- prototype: ``
- caller_count: `21`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18007a6ac`
- `0x18007b2e8`
- `0x18007d4e4`
- `0x18007e38c`
- `0x18007ec6c`
- `0x18007f86c`
- `0x18007ff64`
- `0x18008015c`
- `0x180082854`
- `0x180083524`
- `0x1800868a8`
- `0x180086a8c`
- `0x180086ce4`
- `0x180086f58`
- `0x18008720c`
- `0x1800b12dc`
- `0x1800b8f30`
- `0x1800c13ac`
- `0x1800c1570`
- `0x1800c1734`
- `0x180101f90`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800994e8`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180099529`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180099621`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180099529`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180099621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009955d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009955d`

## string_xrefs

- `0x180099540`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18009957f`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x180099797`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800997e0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmActivateProxyAudioObject>(
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
  const struct _tlgProvider_t *v12; // rax
  int v13; // r9d
  const struct _tlgProvider_t *v14; // rax
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rdx
  unsigned __int64 v18; // r9
  int v19; // eax
  int v20; // [rsp+28h] [rbp-E0h]
  int v21[2]; // [rsp+68h] [rbp-A0h] BYREF
  _DWORD *v22; // [rsp+70h] [rbp-98h] BYREF
  _DWORD *v23; // [rsp+78h] [rbp-90h] BYREF
  float v24; // [rsp+80h] [rbp-88h] BYREF
  int v25; // [rsp+84h] [rbp-84h] BYREF
  __int64 v26; // [rsp+88h] [rbp-80h] BYREF
  LARGE_INTEGER v27; // [rsp+90h] [rbp-78h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+98h] [rbp-70h] BYREF
  va_list v29; // [rsp+A0h] [rbp-68h]
  _DWORD **v30; // [rsp+A8h] [rbp-60h]
  char v31; // [rsp+B0h] [rbp-58h]
  __int64 Src; // [rsp+B8h] [rbp-50h] BYREF
  int v33; // [rsp+C0h] [rbp-48h]
  int v34; // [rsp+C4h] [rbp-44h]
  _BYTE v35[2064]; // [rsp+C8h] [rbp-40h] BYREF
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
  v27.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v6 = *(_DWORD *)(a1 + 64);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
      (const char *)(unsigned int)v6,
      v20);
    return (unsigned int)v6;
  }
  v8 = CoTaskMemAlloc(0x810u);
  v22 = v8;
  if ( v8 )
  {
    Src = 0;
    v34 = 0;
    memset_0(v35, 0, 0x800u);
    memcpy_0(v35, a3, 0x614u);
    v33 = 1;
    memcpy_0(v8, &Src, 0x810u);
    v22[3] = a2;
    va_copy(v29, va);
    v30 = &v22;
    v31 = 1;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _DWORD *, __int64))(**(_QWORD **)(a1 + 40) + 32LL))(
            *(_QWORD *)(a1 + 40),
            a2,
            v22,
            2064);
    QueryPerformanceCounter(&v27);
    v11 = 0.0;
    if ( *(_QWORD *)(a1 + 72) )
      v11 = (float)((float)(v27.LowPart - PerformanceCount.LowPart) * 1000.0) / (float)(int)*(_QWORD *)(a1 + 72);
    if ( v22[2] == 1 )
    {
      v23 = 0;
      if ( (int)XvmMessage::CastTo<XvmActivateProxyAudioObject>(v22, &v23) >= 0 )
      {
        v12 = GuestXvmAudioObjectTelemetryProvider::Provider();
        if ( *(_DWORD *)v12 > 4u )
        {
          v37 = v10;
          v24 = v11;
          v26 = a1;
          v25 = v23[4];
          v21[0] = v23[1];
          v21[1] = v23[2];
          LODWORD(v23) = *v23;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v12,
            (unsigned int)&unk_1801634BB,
            (_DWORD)v12,
            v13,
            (__int64)&v23,
            (__int64)&v21[1],
            (__int64)v21,
            (__int64)&v25,
            (__int64)&v26,
            (__int64)&v24,
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
        *(float *)&v23 = v11;
        v26 = a1;
        v21[1] = v22[2];
        v21[0] = *(_DWORD *)(a1 + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v14,
          (unsigned int)&unk_18016346E,
          v15,
          v16,
          (__int64)v21,
          (__int64)&v21[1],
          (__int64)&v26,
          (__int64)&v23,
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
        v20);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    }
    v9 = *(_DWORD *)(a1 + 64);
    if ( v9 >= 0 )
    {
      v9 = v22[1];
      if ( v9 >= 0 )
      {
        v19 = XvmMessage::CastTo<XvmActivateProxyAudioObject>(v22, v40);
        v9 = v19;
        if ( v19 >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v18 = (unsigned int)v19;
        v17 = 141;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
          (const char *)v18,
          v20);
LABEL_24:
        *v38 = v22;
        return (unsigned int)v9;
      }
      v17 = 140;
    }
    else
    {
      v17 = 138;
    }
    v18 = (unsigned int)v9;
    goto LABEL_20;
  }
  v9 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x52,
    (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
    (const char *)0x8007000ELL,
    v20);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800994e8  mov     rax, rsp
0x1800994eb  mov     [rax+10h], rbx
0x1800994ef  mov     [rax+18h], rsi
0x1800994f3  mov     [rax+20h], r9
0x1800994f7  push    rbp
0x1800994f8  push    rdi
0x1800994f9  push    r14
0x1800994fb  lea     rbp, [rax-7E8h]
0x180099502  sub     rsp, 8D0h
0x180099509  movaps  xmmword ptr [rax-28h], xmm6
0x18009950d  mov     r14, r8
0x180099510  mov     esi, edx
0x180099512  mov     rbx, rcx
0x180099515  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x18009951d  mov     qword ptr [rbp+7E0h+var_858], 0
0x180099525  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x180099529  call    cs:__imp_QueryPerformanceCounter
0x18009952f  mov     edi, [rbx+40h]
0x180099532  test    edi, edi
0x180099534  jns     short loc_180099558
0x180099536  mov     rcx, [rbp+7E8h]; this
0x18009953d  mov     r9d, edi; char *
0x180099540  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180099547  mov     edx, 4Fh ; 'O'; void *
0x18009954c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099551  mov     eax, edi
0x180099553  jmp     loc_18009981D
0x180099558  mov     ecx, 810h; cb
0x18009955d  call    cs:__imp_CoTaskMemAlloc
0x180099563  mov     rdi, rax
0x180099566  mov     [rsp+8E0h+var_878], rax
0x18009956b  test    rax, rax
0x18009956e  jnz     short loc_180099593
0x180099570  mov     rcx, [rbp+7E8h]; this
0x180099577  mov     ebx, 8007000Eh
0x18009957c  mov     r9d, ebx; char *
0x18009957f  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180099586  lea     edx, [rax+52h]; void *
0x180099589  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009958e  jmp     loc_18009981B
0x180099593  mov     [rbp+7E0h+Src], 0
0x18009959b  mov     [rbp+7E0h+var_824], 0
0x1800995a2  xor     edx, edx; Val
0x1800995a4  mov     r8d, 800h; Size
0x1800995aa  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800995ae  call    memset_0
0x1800995b3  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800995b7  mov     rdx, r14; Src
0x1800995ba  mov     r8d, 614h; Size
0x1800995c0  call    memcpy_0
0x1800995c5  mov     [rbp+7E0h+var_828], 1
0x1800995cc  mov     rcx, rdi; void *
0x1800995cf  lea     rdx, [rbp+7E0h+Src]; Src
0x1800995d3  mov     r8d, 810h; Size
0x1800995d9  call    memcpy_0
0x1800995de  mov     rax, [rsp+8E0h+var_878]
0x1800995e3  mov     [rax+0Ch], esi
0x1800995e6  lea     rax, [rbp+7E0h+arg_18]
0x1800995ed  mov     [rbp+7E0h+var_848], rax
0x1800995f1  lea     rax, [rsp+8E0h+var_878]
0x1800995f6  mov     [rbp+7E0h+var_840], rax
0x1800995fa  mov     [rbp+7E0h+var_838], 1
0x1800995fe  mov     rcx, [rbx+28h]
0x180099602  mov     rax, [rcx]
0x180099605  mov     r9d, 810h
0x18009960b  mov     r8, [rsp+8E0h+var_878]
0x180099610  mov     edx, esi
0x180099612  mov     rax, [rax+20h]
0x180099616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009961b  mov     edi, eax
0x18009961d  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x180099621  call    cs:__imp_QueryPerformanceCounter
0x180099627  xorps   xmm6, xmm6
0x18009962a  cmp     qword ptr [rbx+48h], 0
0x18009962f  jz      short loc_180099653
0x180099631  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x180099635  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x180099639  cvtsi2ss xmm6, rcx
0x18009963e  mulss   xmm6, cs:__real@447a0000
0x180099646  xorps   xmm0, xmm0
0x180099649  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x18009964f  divss   xmm6, xmm0
0x180099653  mov     rcx, [rsp+8E0h+var_878]
0x180099658  cmp     dword ptr [rcx+8], 1
0x18009965c  jnz     loc_180099718
0x180099662  mov     [rsp+8E0h+var_870], 0
0x18009966b  lea     rdx, [rsp+8E0h+var_870]
0x180099670  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x180099675  test    eax, eax
0x180099677  js      loc_180099789
0x18009967d  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x180099682  mov     r8, rax
0x180099685  mov     ecx, [rax]
0x180099687  cmp     ecx, 4
0x18009968a  jbe     loc_180099789
0x180099690  mov     [rbp+7E0h+arg_0], edi
0x180099696  movss   [rsp+8E0h+var_868], xmm6
0x18009969c  mov     [rbp+7E0h+var_860], rbx
0x1800996a0  mov     rdx, [rsp+8E0h+var_870]
0x1800996a5  mov     ecx, [rdx+10h]
0x1800996a8  mov     [rsp+8E0h+var_864], ecx
0x1800996ac  mov     ecx, [rdx+4]
0x1800996af  mov     [rsp+8E0h+var_880], ecx
0x1800996b3  mov     eax, [rdx+8]
0x1800996b6  mov     [rsp+8E0h+var_880+4], eax
0x1800996ba  mov     eax, [rdx]
0x1800996bc  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800996c0  lea     rax, [rbp+7E0h+arg_0]
0x1800996c7  mov     [rsp+8E0h+var_890], rax
0x1800996cc  lea     rax, [rsp+8E0h+var_868]
0x1800996d1  mov     [rsp+8E0h+var_898], rax
0x1800996d6  lea     rax, [rbp+7E0h+var_860]
0x1800996da  mov     [rsp+8E0h+var_8A0], rax
0x1800996df  lea     rax, [rsp+8E0h+var_864]
0x1800996e4  mov     [rsp+8E0h+var_8A8], rax
0x1800996e9  lea     rax, [rsp+8E0h+var_880]
0x1800996ee  mov     [rsp+8E0h+var_8B0], rax
0x1800996f3  lea     rax, [rsp+8E0h+var_880+4]
0x1800996f8  mov     [rsp+8E0h+var_8B8], rax
0x1800996fd  lea     rax, [rsp+8E0h+var_870]
0x180099702  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x180099707  lea     rdx, unk_1801634BB
0x18009970e  mov     rcx, r8
0x180099711  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180099716  jmp     short loc_180099789
0x180099718  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x18009971d  mov     ecx, [rax]
0x18009971f  cmp     ecx, 4
0x180099722  jbe     short loc_180099789
0x180099724  mov     [rbp+7E0h+arg_0], edi
0x18009972a  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x180099730  mov     [rbp+7E0h+var_860], rbx
0x180099734  mov     rcx, [rsp+8E0h+var_878]
0x180099739  mov     edx, [rcx+8]
0x18009973c  mov     [rsp+8E0h+var_880+4], edx
0x180099740  mov     ecx, [rbx+30h]
0x180099743  mov     [rsp+8E0h+var_880], ecx
0x180099747  lea     rcx, [rbp+7E0h+arg_0]
0x18009974e  mov     [rsp+8E0h+var_8A0], rcx
0x180099753  lea     rcx, [rsp+8E0h+var_870]
0x180099758  mov     [rsp+8E0h+var_8A8], rcx
0x18009975d  lea     rcx, [rbp+7E0h+var_860]
0x180099761  mov     [rsp+8E0h+var_8B0], rcx
0x180099766  lea     rcx, [rsp+8E0h+var_880+4]
0x18009976b  mov     [rsp+8E0h+var_8B8], rcx
0x180099770  lea     rcx, [rsp+8E0h+var_880]
0x180099775  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x18009977a  lea     rdx, unk_18016346E
0x180099781  mov     rcx, rax
0x180099784  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180099789  mov     rcx, [rbp+7E8h]; this
0x180099790  test    edi, edi
0x180099792  jns     short loc_1800997B7
0x180099794  mov     r9d, edi; char *
0x180099797  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18009979e  mov     edx, 81h; void *
0x1800997a3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800997a8  mov     rax, [rbx]
0x1800997ab  mov     rcx, rbx
0x1800997ae  mov     rax, [rax+20h]
0x1800997b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800997b7  mov     ebx, [rbx+40h]
0x1800997ba  test    ebx, ebx
0x1800997bc  jns     short loc_1800997C5
0x1800997be  mov     edx, 8Ah
0x1800997c3  jmp     short loc_1800997D6
0x1800997c5  mov     rcx, [rsp+8E0h+var_878]
0x1800997ca  mov     ebx, [rcx+4]
0x1800997cd  test    ebx, ebx
0x1800997cf  jns     short loc_1800997EE
0x1800997d1  mov     edx, 8Ch; void *
0x1800997d6  mov     r9d, ebx; char *
0x1800997d9  mov     rcx, [rbp+7E8h]; this
0x1800997e0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800997e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800997ec  jmp     short loc_18009980C
0x1800997ee  mov     rdx, [rbp+7E0h+arg_20]
0x1800997f5  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800997fa  mov     ebx, eax
0x1800997fc  test    eax, eax
0x1800997fe  jns     short loc_18009980A
0x180099800  mov     r9d, eax
0x180099803  mov     edx, 8Dh
0x180099808  jmp     short loc_1800997D9
0x18009980a  xor     ebx, ebx
0x18009980c  mov     rcx, [rbp+7E0h+arg_18]
0x180099813  mov     rax, [rsp+8E0h+var_878]
0x180099818  mov     [rcx], rax
0x18009981b  mov     eax, ebx
0x18009981d  lea     r11, [rsp+8E0h+var_10]
0x180099825  mov     rbx, [r11+28h]
0x180099829  mov     rsi, [r11+30h]
0x18009982d  movaps  xmm6, xmmword ptr [r11-10h]
0x180099832  mov     rsp, r11
0x180099835  pop     r14
0x180099837  pop     rdi
0x180099838  pop     rbp
0x180099839  retn
```
