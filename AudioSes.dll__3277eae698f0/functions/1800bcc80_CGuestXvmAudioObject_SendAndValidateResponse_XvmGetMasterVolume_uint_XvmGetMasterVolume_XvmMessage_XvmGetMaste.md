# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetMasterVolume>(uint,XvmGetMasterVolume,XvmMessage * *,XvmGetMasterVolume * *)

- ea: `0x1800bcc80`
- end: `0x1800bcfbb`
- name: `??$SendAndValidateResponse@UXvmGetMasterVolume@@@CGuestXvmAudioObject@@QEAAJIUXvmGetMasterVolume@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `827`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c0890`
- `0x1800c0990`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a29b0`
- `0x1800bcc80`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bccbe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bcdab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bccbe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bcdab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bccf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bccf2`

## string_xrefs

- `0x1800bccd5`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bcd14`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bcf1d`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bcf66`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetMasterVolume>(__int64 a1, unsigned int a2, int a3, ...)
{
  int v5; // edi
  _DWORD *v7; // rdi
  int v8; // ebx
  int v9; // edi
  float v10; // xmm6_4
  const struct _tlgProvider_t *v11; // r8
  int v12; // r9d
  const struct _tlgProvider_t *v13; // rax
  int v14; // r9d
  __int64 v15; // rdx
  unsigned __int64 v16; // r9
  int Master; // eax
  int v18; // [rsp+28h] [rbp-E0h]
  int v19[2]; // [rsp+68h] [rbp-A0h] BYREF
  _DWORD *v20; // [rsp+70h] [rbp-98h] BYREF
  _DWORD *v21; // [rsp+78h] [rbp-90h] BYREF
  int v22; // [rsp+80h] [rbp-88h]
  float v23; // [rsp+88h] [rbp-80h] BYREF
  int v24; // [rsp+8Ch] [rbp-7Ch] BYREF
  __int64 v25; // [rsp+90h] [rbp-78h] BYREF
  LARGE_INTEGER v26; // [rsp+98h] [rbp-70h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+A0h] [rbp-68h] BYREF
  va_list v28; // [rsp+A8h] [rbp-60h]
  _DWORD **v29; // [rsp+B0h] [rbp-58h]
  char v30; // [rsp+B8h] [rbp-50h]
  __int64 Src; // [rsp+C8h] [rbp-40h] BYREF
  int v32; // [rsp+D0h] [rbp-38h]
  int v33; // [rsp+D4h] [rbp-34h]
  _DWORD v34[516]; // [rsp+D8h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+900h] [rbp+7F8h]
  int v36; // [rsp+908h] [rbp+800h] BYREF
  _QWORD *v37; // [rsp+920h] [rbp+818h] BYREF
  va_list va; // [rsp+920h] [rbp+818h]
  __int64 v39; // [rsp+928h] [rbp+820h]
  va_list va1; // [rsp+930h] [rbp+828h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v37 = va_arg(va1, _QWORD *);
  v39 = va_arg(va1, _QWORD);
  v22 = a3;
  PerformanceCount.QuadPart = 0;
  v26.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v5 = *(_DWORD *)(a1 + 64);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
      (const char *)(unsigned int)v5,
      v18);
    return (unsigned int)v5;
  }
  v7 = CoTaskMemAlloc(0x810u);
  v20 = v7;
  if ( v7 )
  {
    Src = 0;
    v33 = 0;
    memset_0(v34, 0, 0x800u);
    v34[0] = v22;
    v32 = 21;
    memcpy_0(v7, &Src, 0x810u);
    v20[3] = a2;
    va_copy(v28, va);
    v29 = &v20;
    v30 = 1;
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _DWORD *, __int64))(**(_QWORD **)(a1 + 40) + 32LL))(
           *(_QWORD *)(a1 + 40),
           a2,
           v20,
           2064);
    QueryPerformanceCounter(&v26);
    v10 = 0.0;
    if ( *(_QWORD *)(a1 + 72) )
      v10 = (float)((float)(v26.LowPart - PerformanceCount.LowPart) * 1000.0) / (float)(int)*(_QWORD *)(a1 + 72);
    if ( v20[2] == 1 )
    {
      v21 = 0;
      if ( (int)XvmMessage::CastTo<XvmActivateProxyAudioObject>(v20, &v21) >= 0 )
      {
        v11 = GuestXvmAudioObjectTelemetryProvider::Provider();
        if ( *(_DWORD *)v11 > 4u )
        {
          v36 = v9;
          v23 = v10;
          v25 = a1;
          v24 = v21[4];
          v19[0] = v21[1];
          v19[1] = v21[2];
          LODWORD(v21) = *v21;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v11,
            (unsigned int)&word_180168936,
            (_DWORD)v11,
            v12,
            (__int64)&v21,
            (__int64)&v19[1],
            (__int64)v19,
            (__int64)&v24,
            (__int64)&v25,
            (__int64)&v23,
            (__int64)&v36);
        }
      }
    }
    else
    {
      v13 = GuestXvmAudioObjectTelemetryProvider::Provider();
      if ( *(_DWORD *)v13 > 4u )
      {
        v36 = v9;
        *(float *)&v21 = v10;
        v25 = a1;
        v19[1] = v20[2];
        v19[0] = *(_DWORD *)(a1 + 48);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v13,
          (unsigned int)&byte_1801689AF,
          (_DWORD)v11,
          v14,
          (__int64)v19,
          (__int64)&v19[1],
          (__int64)&v25,
          (__int64)&v21,
          (__int64)&v36);
      }
    }
    if ( v9 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
        (const char *)(unsigned int)v9,
        v18);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
    }
    v8 = *(_DWORD *)(a1 + 64);
    if ( v8 >= 0 )
    {
      v8 = v20[1];
      if ( v8 >= 0 )
      {
        Master = XvmMessage::CastTo<XvmGetMasterVolume>(v20, v39, v11);
        v8 = Master;
        if ( Master >= 0 )
        {
          v8 = 0;
          goto LABEL_24;
        }
        v16 = (unsigned int)Master;
        v15 = 141;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
          (const char *)v16,
          v18);
LABEL_24:
        *v37 = v20;
        return (unsigned int)v8;
      }
      v15 = 140;
    }
    else
    {
      v15 = 138;
    }
    v16 = (unsigned int)v8;
    goto LABEL_20;
  }
  v8 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x52,
    (unsigned int)"avcore\\audiocore\\CrossVmCommon\\CrossVmGuest.h",
    (const char *)0x8007000ELL,
    v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800bcc80  mov     rax, rsp
0x1800bcc83  mov     [rax+10h], rbx
0x1800bcc87  mov     [rax+20h], r9
0x1800bcc8b  push    rbp
0x1800bcc8c  push    rsi
0x1800bcc8d  push    rdi
0x1800bcc8e  lea     rbp, [rax-7F8h]
0x1800bcc95  sub     rsp, 8E0h
0x1800bcc9c  movaps  xmmword ptr [rax-28h], xmm6
0x1800bcca0  mov     esi, edx
0x1800bcca2  mov     rbx, rcx
0x1800bcca5  mov     [rsp+8F0h+var_878], r8d
0x1800bccaa  mov     qword ptr [rbp+7F0h+PerformanceCount], 0
0x1800bccb2  mov     qword ptr [rbp+7F0h+var_860], 0
0x1800bccba  lea     rcx, [rbp+7F0h+PerformanceCount]; lpPerformanceCount
0x1800bccbe  call    cs:__imp_QueryPerformanceCounter
0x1800bccc4  mov     edi, [rbx+40h]
0x1800bccc7  test    edi, edi
0x1800bccc9  jns     short loc_1800BCCED
0x1800bcccb  mov     rcx, [rbp+7F8h]; this
0x1800bccd2  mov     r9d, edi; char *
0x1800bccd5  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bccdc  mov     edx, 4Fh ; 'O'; void *
0x1800bcce1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcce6  mov     eax, edi
0x1800bcce8  jmp     loc_1800BCFA3
0x1800bcced  mov     ecx, 810h; cb
0x1800bccf2  call    cs:__imp_CoTaskMemAlloc
0x1800bccf8  mov     rdi, rax
0x1800bccfb  mov     [rsp+8F0h+var_888], rax
0x1800bcd00  test    rax, rax
0x1800bcd03  jnz     short loc_1800BCD28
0x1800bcd05  mov     rcx, [rbp+7F8h]; this
0x1800bcd0c  mov     ebx, 8007000Eh
0x1800bcd11  mov     r9d, ebx; char *
0x1800bcd14  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bcd1b  lea     edx, [rax+52h]; void *
0x1800bcd1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcd23  jmp     loc_1800BCFA1
0x1800bcd28  mov     [rbp+7F0h+Src], 0
0x1800bcd30  mov     [rbp+7F0h+var_824], 0
0x1800bcd37  xor     edx, edx; Val
0x1800bcd39  mov     r8d, 800h; Size
0x1800bcd3f  lea     rcx, [rbp+7F0h+var_820]; void *
0x1800bcd43  call    memset_0
0x1800bcd48  mov     eax, [rsp+8F0h+var_878]
0x1800bcd4c  mov     [rbp+7F0h+var_820], eax
0x1800bcd4f  mov     [rbp+7F0h+var_828], 15h
0x1800bcd56  mov     rcx, rdi; void *
0x1800bcd59  lea     rdx, [rbp+7F0h+Src]; Src
0x1800bcd5d  mov     r8d, 810h; Size
0x1800bcd63  call    memcpy_0
0x1800bcd68  mov     rax, [rsp+8F0h+var_888]
0x1800bcd6d  mov     [rax+0Ch], esi
0x1800bcd70  lea     rax, [rbp+7F0h+arg_18]
0x1800bcd77  mov     [rbp+7F0h+var_850], rax
0x1800bcd7b  lea     rax, [rsp+8F0h+var_888]
0x1800bcd80  mov     [rbp+7F0h+var_848], rax
0x1800bcd84  mov     [rbp+7F0h+var_840], 1
0x1800bcd88  mov     rcx, [rbx+28h]
0x1800bcd8c  mov     rax, [rcx]
0x1800bcd8f  mov     r9d, 810h
0x1800bcd95  mov     r8, [rsp+8F0h+var_888]
0x1800bcd9a  mov     edx, esi
0x1800bcd9c  mov     rax, [rax+20h]
0x1800bcda0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcda5  mov     edi, eax
0x1800bcda7  lea     rcx, [rbp+7F0h+var_860]; lpPerformanceCount
0x1800bcdab  call    cs:__imp_QueryPerformanceCounter
0x1800bcdb1  xorps   xmm6, xmm6
0x1800bcdb4  cmp     qword ptr [rbx+48h], 0
0x1800bcdb9  jz      short loc_1800BCDDD
0x1800bcdbb  mov     rcx, qword ptr [rbp+7F0h+var_860]
0x1800bcdbf  sub     rcx, qword ptr [rbp+7F0h+PerformanceCount]
0x1800bcdc3  cvtsi2ss xmm6, rcx
0x1800bcdc8  mulss   xmm6, cs:__real@447a0000
0x1800bcdd0  xorps   xmm0, xmm0
0x1800bcdd3  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800bcdd9  divss   xmm6, xmm0
0x1800bcddd  mov     rcx, [rsp+8F0h+var_888]
0x1800bcde2  cmp     dword ptr [rcx+8], 1
0x1800bcde6  jnz     loc_1800BCE9E
0x1800bcdec  mov     [rsp+8F0h+var_880], 0
0x1800bcdf5  lea     rdx, [rsp+8F0h+var_880]
0x1800bcdfa  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bcdff  test    eax, eax
0x1800bce01  js      loc_1800BCF0F
0x1800bce07  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bce0c  mov     r8, rax
0x1800bce0f  mov     ecx, [rax]
0x1800bce11  cmp     ecx, 4
0x1800bce14  jbe     loc_1800BCF0F
0x1800bce1a  mov     [rbp+7F0h+arg_0], edi
0x1800bce20  movss   [rbp+7F0h+var_870], xmm6
0x1800bce25  mov     [rbp+7F0h+var_868], rbx
0x1800bce29  mov     rdx, [rsp+8F0h+var_880]
0x1800bce2e  mov     ecx, [rdx+10h]
0x1800bce31  mov     [rbp+7F0h+var_86C], ecx
0x1800bce34  mov     ecx, [rdx+4]
0x1800bce37  mov     [rsp+8F0h+var_890], ecx
0x1800bce3b  mov     eax, [rdx+8]
0x1800bce3e  mov     [rsp+8F0h+var_890+4], eax
0x1800bce42  mov     eax, [rdx]
0x1800bce44  mov     dword ptr [rsp+8F0h+var_880], eax
0x1800bce48  lea     rax, [rbp+7F0h+arg_0]
0x1800bce4f  mov     [rsp+8F0h+var_8A0], rax
0x1800bce54  lea     rax, [rbp+7F0h+var_870]
0x1800bce58  mov     [rsp+8F0h+var_8A8], rax
0x1800bce5d  lea     rax, [rbp+7F0h+var_868]
0x1800bce61  mov     [rsp+8F0h+var_8B0], rax
0x1800bce66  lea     rax, [rbp+7F0h+var_86C]
0x1800bce6a  mov     [rsp+8F0h+var_8B8], rax
0x1800bce6f  lea     rax, [rsp+8F0h+var_890]
0x1800bce74  mov     [rsp+8F0h+var_8C0], rax
0x1800bce79  lea     rax, [rsp+8F0h+var_890+4]
0x1800bce7e  mov     [rsp+8F0h+var_8C8], rax
0x1800bce83  lea     rax, [rsp+8F0h+var_880]
0x1800bce88  mov     qword ptr [rsp+8F0h+var_8D0], rax
0x1800bce8d  lea     rdx, word_180168936
0x1800bce94  mov     rcx, r8
0x1800bce97  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bce9c  jmp     short loc_1800BCF0F
0x1800bce9e  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bcea3  mov     ecx, [rax]
0x1800bcea5  cmp     ecx, 4
0x1800bcea8  jbe     short loc_1800BCF0F
0x1800bceaa  mov     [rbp+7F0h+arg_0], edi
0x1800bceb0  movss   dword ptr [rsp+8F0h+var_880], xmm6
0x1800bceb6  mov     [rbp+7F0h+var_868], rbx
0x1800bceba  mov     rcx, [rsp+8F0h+var_888]
0x1800bcebf  mov     edx, [rcx+8]
0x1800bcec2  mov     [rsp+8F0h+var_890+4], edx
0x1800bcec6  mov     ecx, [rbx+30h]
0x1800bcec9  mov     [rsp+8F0h+var_890], ecx
0x1800bcecd  lea     rcx, [rbp+7F0h+arg_0]
0x1800bced4  mov     [rsp+8F0h+var_8B0], rcx
0x1800bced9  lea     rcx, [rsp+8F0h+var_880]
0x1800bcede  mov     [rsp+8F0h+var_8B8], rcx
0x1800bcee3  lea     rcx, [rbp+7F0h+var_868]
0x1800bcee7  mov     [rsp+8F0h+var_8C0], rcx
0x1800bceec  lea     rcx, [rsp+8F0h+var_890+4]
0x1800bcef1  mov     [rsp+8F0h+var_8C8], rcx
0x1800bcef6  lea     rcx, [rsp+8F0h+var_890]
0x1800bcefb  mov     qword ptr [rsp+8F0h+var_8D0], rcx; int
0x1800bcf00  lea     rdx, byte_1801689AF
0x1800bcf07  mov     rcx, rax
0x1800bcf0a  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bcf0f  mov     rcx, [rbp+7F8h]; this
0x1800bcf16  test    edi, edi
0x1800bcf18  jns     short loc_1800BCF3D
0x1800bcf1a  mov     r9d, edi; char *
0x1800bcf1d  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bcf24  mov     edx, 81h; void *
0x1800bcf29  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bcf2e  mov     rax, [rbx]
0x1800bcf31  mov     rcx, rbx
0x1800bcf34  mov     rax, [rax+20h]
0x1800bcf38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bcf3d  mov     ebx, [rbx+40h]
0x1800bcf40  test    ebx, ebx
0x1800bcf42  jns     short loc_1800BCF4B
0x1800bcf44  mov     edx, 8Ah
0x1800bcf49  jmp     short loc_1800BCF5C
0x1800bcf4b  mov     rcx, [rsp+8F0h+var_888]
0x1800bcf50  mov     ebx, [rcx+4]
0x1800bcf53  test    ebx, ebx
0x1800bcf55  jns     short loc_1800BCF74
0x1800bcf57  mov     edx, 8Ch; void *
0x1800bcf5c  mov     r9d, ebx; char *
0x1800bcf5f  mov     rcx, [rbp+7F8h]; this
0x1800bcf66  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bcf6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bcf72  jmp     short loc_1800BCF92
0x1800bcf74  mov     rdx, [rbp+7F0h+arg_20]
0x1800bcf7b  call    ??$CastTo@UXvmGetMasterVolume@@@XvmMessage@@QEAAJPEAPEAUXvmGetMasterVolume@@@Z; XvmMessage::CastTo<XvmGetMasterVolume>(XvmGetMasterVolume * *)
0x1800bcf80  mov     ebx, eax
0x1800bcf82  test    eax, eax
0x1800bcf84  jns     short loc_1800BCF90
0x1800bcf86  mov     r9d, eax
0x1800bcf89  mov     edx, 8Dh
0x1800bcf8e  jmp     short loc_1800BCF5F
0x1800bcf90  xor     ebx, ebx
0x1800bcf92  mov     rcx, [rbp+7F0h+arg_18]
0x1800bcf99  mov     rax, [rsp+8F0h+var_888]
0x1800bcf9e  mov     [rcx], rax
0x1800bcfa1  mov     eax, ebx
0x1800bcfa3  lea     r11, [rsp+8F0h+var_10]
0x1800bcfab  mov     rbx, [r11+28h]
0x1800bcfaf  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bcfb4  mov     rsp, r11
0x1800bcfb7  pop     rdi
0x1800bcfb8  pop     rsi
0x1800bcfb9  pop     rbp
0x1800bcfba  retn
```
