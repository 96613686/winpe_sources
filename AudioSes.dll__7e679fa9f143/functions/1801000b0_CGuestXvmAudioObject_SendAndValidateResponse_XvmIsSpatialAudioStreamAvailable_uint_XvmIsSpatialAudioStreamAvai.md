# CGuestXvmAudioObject::SendAndValidateResponse<XvmIsSpatialAudioStreamAvailable>(uint,XvmIsSpatialAudioStreamAvailable,XvmMessage * *,XvmIsSpatialAudioStreamAvailable * *)

- ea: `0x1801000b0`
- end: `0x18010040c`
- name: `??$SendAndValidateResponse@UXvmIsSpatialAudioStreamAvailable@@@CGuestXvmAudioObject@@QEAAJIUXvmIsSpatialAudioStreamAvailable@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `860`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180101c00`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800fa2bc`
- `0x1801000b0`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801000f2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801001f3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801000f2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801001f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180100126`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180100126`

## string_xrefs

- `0x180100109`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x180100148`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x180100369`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1801003b2`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmIsSpatialAudioStreamAvailable>(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
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
  int IsSpatialAudioStream; // eax
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
  __int64 v34; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v35; // [rsp+D0h] [rbp-38h]
  __int64 v36; // [rsp+E0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+8F0h] [rbp+7E8h]
  int v38; // [rsp+8F8h] [rbp+7F0h] BYREF
  _QWORD *v39; // [rsp+910h] [rbp+808h] BYREF
  va_list va; // [rsp+910h] [rbp+808h]
  __int64 v41; // [rsp+918h] [rbp+810h]
  va_list va1; // [rsp+920h] [rbp+818h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v39 = va_arg(va1, _QWORD *);
  v41 = va_arg(va1, _QWORD);
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
    memset_0(&v34, 0, 0x800u);
    v34 = *a3;
    v35 = *(_OWORD *)(a3 + 1);
    v36 = a3[3];
    v32 = 53;
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
          v38 = v10;
          v23 = v11;
          v25 = a1;
          v24 = v22[4];
          v20[0] = v22[1];
          v20[1] = v22[2];
          LODWORD(v22) = *v22;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v12,
            (unsigned int)&unk_180171003,
            (_DWORD)v12,
            v13,
            (__int64)&v22,
            (__int64)&v20[1],
            (__int64)v20,
            (__int64)&v24,
            (__int64)&v25,
            (__int64)&v23,
            (__int64)&v38);
        }
      }
    }
    else
    {
      v14 = GuestXvmAudioObjectTelemetryProvider::Provider();
      if ( *(_DWORD *)v14 > 4u )
      {
        v38 = v10;
        *(float *)&v22 = v11;
        v25 = a1;
        v20[1] = v21[2];
        v20[0] = *(_DWORD *)(a1 + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v14,
          (unsigned int)&unk_180170C9E,
          (_DWORD)v12,
          v15,
          (__int64)v20,
          (__int64)&v20[1],
          (__int64)&v25,
          (__int64)&v22,
          (__int64)&v38);
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
        IsSpatialAudioStream = XvmMessage::CastTo<XvmIsSpatialAudioStreamAvailable>(v21, v41, v12);
        v9 = IsSpatialAudioStream;
        if ( IsSpatialAudioStream >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)IsSpatialAudioStream;
        v16 = 141;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
          (const char *)v17,
          v19);
LABEL_24:
        *v39 = v21;
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
0x1801000b0  mov     rax, rsp
0x1801000b3  mov     [rax+10h], rbx
0x1801000b7  mov     [rax+18h], rsi
0x1801000bb  mov     [rax+20h], r9
0x1801000bf  push    rbp
0x1801000c0  push    rdi
0x1801000c1  push    r14
0x1801000c3  lea     rbp, [rax-7E8h]
0x1801000ca  sub     rsp, 8D0h
0x1801000d1  movaps  xmmword ptr [rax-28h], xmm6
0x1801000d5  mov     rsi, r8
0x1801000d8  mov     r14d, edx
0x1801000db  mov     rbx, rcx
0x1801000de  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1801000e6  mov     qword ptr [rbp+7E0h+var_858], 0
0x1801000ee  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1801000f2  call    cs:__imp_QueryPerformanceCounter
0x1801000f8  mov     edi, [rbx+40h]
0x1801000fb  test    edi, edi
0x1801000fd  jns     short loc_180100121
0x1801000ff  mov     rcx, [rbp+7E8h]; this
0x180100106  mov     r9d, edi; char *
0x180100109  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180100110  mov     edx, 4Fh ; 'O'; void *
0x180100115  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010011a  mov     eax, edi
0x18010011c  jmp     loc_1801003EF
0x180100121  mov     ecx, 810h; cb
0x180100126  call    cs:__imp_CoTaskMemAlloc
0x18010012c  mov     rdi, rax
0x18010012f  mov     [rsp+8E0h+var_878], rax
0x180100134  test    rax, rax
0x180100137  jnz     short loc_18010015C
0x180100139  mov     rcx, [rbp+7E8h]; this
0x180100140  mov     ebx, 8007000Eh
0x180100145  mov     r9d, ebx; char *
0x180100148  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010014f  lea     edx, [rax+52h]; void *
0x180100152  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180100157  jmp     loc_1801003ED
0x18010015c  mov     [rbp+7E0h+Src], 0
0x180100164  mov     [rbp+7E0h+var_824], 0
0x18010016b  xor     edx, edx; Val
0x18010016d  mov     r8d, 800h; Size
0x180100173  lea     rcx, [rbp+7E0h+var_820]; void *
0x180100177  call    memset_0
0x18010017c  mov     rax, [rsi]
0x18010017f  mov     [rbp+7E0h+var_820], rax
0x180100183  movups  xmm0, xmmword ptr [rsi+8]
0x180100187  movups  [rbp+7E0h+var_818], xmm0
0x18010018b  movsd   xmm1, qword ptr [rsi+18h]
0x180100190  movsd   [rbp+7E0h+var_808], xmm1
0x180100195  mov     [rbp+7E0h+var_828], 35h ; '5'
0x18010019c  mov     rcx, rdi; void *
0x18010019f  lea     rdx, [rbp+7E0h+Src]; Src
0x1801001a3  mov     r8d, 810h; Size
0x1801001a9  call    memcpy_0
0x1801001ae  mov     rax, [rsp+8E0h+var_878]
0x1801001b3  mov     [rax+0Ch], r14d
0x1801001b7  lea     rax, [rbp+7E0h+arg_18]
0x1801001be  mov     [rbp+7E0h+var_848], rax
0x1801001c2  lea     rax, [rsp+8E0h+var_878]
0x1801001c7  mov     [rbp+7E0h+var_840], rax
0x1801001cb  mov     [rbp+7E0h+var_838], 1
0x1801001cf  mov     rcx, [rbx+28h]
0x1801001d3  mov     rax, [rcx]
0x1801001d6  mov     r9d, 810h
0x1801001dc  mov     r8, [rsp+8E0h+var_878]
0x1801001e1  mov     edx, r14d
0x1801001e4  mov     rax, [rax+20h]
0x1801001e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801001ed  mov     edi, eax
0x1801001ef  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1801001f3  call    cs:__imp_QueryPerformanceCounter
0x1801001f9  xorps   xmm6, xmm6
0x1801001fc  cmp     qword ptr [rbx+48h], 0
0x180100201  jz      short loc_180100225
0x180100203  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x180100207  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x18010020b  cvtsi2ss xmm6, rcx
0x180100210  mulss   xmm6, cs:__real@447a0000
0x180100218  xorps   xmm0, xmm0
0x18010021b  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x180100221  divss   xmm6, xmm0
0x180100225  mov     rcx, [rsp+8E0h+var_878]
0x18010022a  cmp     dword ptr [rcx+8], 1
0x18010022e  jnz     loc_1801002EA
0x180100234  mov     [rsp+8E0h+var_870], 0
0x18010023d  lea     rdx, [rsp+8E0h+var_870]
0x180100242  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x180100247  test    eax, eax
0x180100249  js      loc_18010035B
0x18010024f  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x180100254  mov     r8, rax
0x180100257  mov     ecx, [rax]
0x180100259  cmp     ecx, 4
0x18010025c  jbe     loc_18010035B
0x180100262  mov     [rbp+7E0h+arg_0], edi
0x180100268  movss   [rsp+8E0h+var_868], xmm6
0x18010026e  mov     [rbp+7E0h+var_860], rbx
0x180100272  mov     rdx, [rsp+8E0h+var_870]
0x180100277  mov     ecx, [rdx+10h]
0x18010027a  mov     [rsp+8E0h+var_864], ecx
0x18010027e  mov     ecx, [rdx+4]
0x180100281  mov     [rsp+8E0h+var_880], ecx
0x180100285  mov     eax, [rdx+8]
0x180100288  mov     [rsp+8E0h+var_880+4], eax
0x18010028c  mov     eax, [rdx]
0x18010028e  mov     dword ptr [rsp+8E0h+var_870], eax
0x180100292  lea     rax, [rbp+7E0h+arg_0]
0x180100299  mov     [rsp+8E0h+var_890], rax
0x18010029e  lea     rax, [rsp+8E0h+var_868]
0x1801002a3  mov     [rsp+8E0h+var_898], rax
0x1801002a8  lea     rax, [rbp+7E0h+var_860]
0x1801002ac  mov     [rsp+8E0h+var_8A0], rax
0x1801002b1  lea     rax, [rsp+8E0h+var_864]
0x1801002b6  mov     [rsp+8E0h+var_8A8], rax
0x1801002bb  lea     rax, [rsp+8E0h+var_880]
0x1801002c0  mov     [rsp+8E0h+var_8B0], rax
0x1801002c5  lea     rax, [rsp+8E0h+var_880+4]
0x1801002ca  mov     [rsp+8E0h+var_8B8], rax
0x1801002cf  lea     rax, [rsp+8E0h+var_870]
0x1801002d4  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1801002d9  lea     rdx, unk_180171003
0x1801002e0  mov     rcx, r8
0x1801002e3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1801002e8  jmp     short loc_18010035B
0x1801002ea  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1801002ef  mov     ecx, [rax]
0x1801002f1  cmp     ecx, 4
0x1801002f4  jbe     short loc_18010035B
0x1801002f6  mov     [rbp+7E0h+arg_0], edi
0x1801002fc  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x180100302  mov     [rbp+7E0h+var_860], rbx
0x180100306  mov     rcx, [rsp+8E0h+var_878]
0x18010030b  mov     edx, [rcx+8]
0x18010030e  mov     [rsp+8E0h+var_880+4], edx
0x180100312  mov     ecx, [rbx+30h]
0x180100315  mov     [rsp+8E0h+var_880], ecx
0x180100319  lea     rcx, [rbp+7E0h+arg_0]
0x180100320  mov     [rsp+8E0h+var_8A0], rcx
0x180100325  lea     rcx, [rsp+8E0h+var_870]
0x18010032a  mov     [rsp+8E0h+var_8A8], rcx
0x18010032f  lea     rcx, [rbp+7E0h+var_860]
0x180100333  mov     [rsp+8E0h+var_8B0], rcx
0x180100338  lea     rcx, [rsp+8E0h+var_880+4]
0x18010033d  mov     [rsp+8E0h+var_8B8], rcx
0x180100342  lea     rcx, [rsp+8E0h+var_880]
0x180100347  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x18010034c  lea     rdx, unk_180170C9E
0x180100353  mov     rcx, rax
0x180100356  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18010035b  mov     rcx, [rbp+7E8h]; this
0x180100362  test    edi, edi
0x180100364  jns     short loc_180100389
0x180100366  mov     r9d, edi; char *
0x180100369  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x180100370  mov     edx, 81h; void *
0x180100375  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010037a  mov     rax, [rbx]
0x18010037d  mov     rcx, rbx
0x180100380  mov     rax, [rax+20h]
0x180100384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180100389  mov     ebx, [rbx+40h]
0x18010038c  test    ebx, ebx
0x18010038e  jns     short loc_180100397
0x180100390  mov     edx, 8Ah
0x180100395  jmp     short loc_1801003A8
0x180100397  mov     rcx, [rsp+8E0h+var_878]
0x18010039c  mov     ebx, [rcx+4]
0x18010039f  test    ebx, ebx
0x1801003a1  jns     short loc_1801003C0
0x1801003a3  mov     edx, 8Ch; void *
0x1801003a8  mov     r9d, ebx; char *
0x1801003ab  mov     rcx, [rbp+7E8h]; this
0x1801003b2  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1801003b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801003be  jmp     short loc_1801003DE
0x1801003c0  mov     rdx, [rbp+7E0h+arg_20]
0x1801003c7  call    ??$CastTo@UXvmIsSpatialAudioStreamAvailable@@@XvmMessage@@QEAAJPEAPEAUXvmIsSpatialAudioStreamAvailable@@@Z; XvmMessage::CastTo<XvmIsSpatialAudioStreamAvailable>(XvmIsSpatialAudioStreamAvailable * *)
0x1801003cc  mov     ebx, eax
0x1801003ce  test    eax, eax
0x1801003d0  jns     short loc_1801003DC
0x1801003d2  mov     r9d, eax
0x1801003d5  mov     edx, 8Dh
0x1801003da  jmp     short loc_1801003AB
0x1801003dc  xor     ebx, ebx
0x1801003de  mov     rcx, [rbp+7E0h+arg_18]
0x1801003e5  mov     rax, [rsp+8E0h+var_878]
0x1801003ea  mov     [rcx], rax
0x1801003ed  mov     eax, ebx
0x1801003ef  lea     r11, [rsp+8E0h+var_10]
0x1801003f7  mov     rbx, [r11+28h]
0x1801003fb  mov     rsi, [r11+30h]
0x1801003ff  movaps  xmm6, xmmword ptr [r11-10h]
0x180100404  mov     rsp, r11
0x180100407  pop     r14
0x180100409  pop     rdi
0x18010040a  pop     rbp
0x18010040b  retn
```
