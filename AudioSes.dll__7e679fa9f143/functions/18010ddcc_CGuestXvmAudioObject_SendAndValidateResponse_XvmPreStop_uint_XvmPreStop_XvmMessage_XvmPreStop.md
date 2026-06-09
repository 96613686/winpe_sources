# CGuestXvmAudioObject::SendAndValidateResponse<XvmPreStop>(uint,XvmPreStop,XvmMessage * *,XvmPreStop * *)

- ea: `0x18010ddcc`
- end: `0x18010e112`
- name: `??$SendAndValidateResponse@UXvmPreStop@@@CGuestXvmAudioObject@@QEAAJIUXvmPreStop@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18010eb9c`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x180102278`
- `0x18010ddcc`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010de0e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010def9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010de0e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010def9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010de42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010de42`

## string_xrefs

- `0x18010de25`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18010de64`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18010e06f`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18010e0b8`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmPreStop>(__int64 a1, unsigned int a2, char a3, ...)
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
    v32 = 69;
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
            (unsigned int)&unk_180172B30,
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
          (unsigned int)&unk_180172AE3,
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
        v18 = XvmMessage::CastTo<XvmPreStop>(v21, v39, v12);
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
0x18010ddcc  mov     rax, rsp
0x18010ddcf  mov     [rax+10h], rbx
0x18010ddd3  mov     [rax+18h], rsi
0x18010ddd7  mov     [rax+20h], r9
0x18010dddb  push    rbp
0x18010dddc  push    rdi
0x18010dddd  push    r14
0x18010dddf  lea     rbp, [rax-7E8h]
0x18010dde6  sub     rsp, 8D0h
0x18010dded  movaps  xmmword ptr [rax-28h], xmm6
0x18010ddf1  mov     bl, r8b
0x18010ddf4  mov     r14d, edx
0x18010ddf7  mov     rdi, rcx
0x18010ddfa  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x18010de02  mov     qword ptr [rbp+7E0h+var_858], 0
0x18010de0a  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x18010de0e  call    cs:__imp_QueryPerformanceCounter
0x18010de14  mov     esi, [rdi+40h]
0x18010de17  test    esi, esi
0x18010de19  jns     short loc_18010DE3D
0x18010de1b  mov     rcx, [rbp+7E8h]; this
0x18010de22  mov     r9d, esi; char *
0x18010de25  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010de2c  mov     edx, 4Fh ; 'O'; void *
0x18010de31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010de36  mov     eax, esi
0x18010de38  jmp     loc_18010E0F5
0x18010de3d  mov     ecx, 810h; cb
0x18010de42  call    cs:__imp_CoTaskMemAlloc
0x18010de48  mov     rsi, rax
0x18010de4b  mov     [rsp+8E0h+var_878], rax
0x18010de50  test    rax, rax
0x18010de53  jnz     short loc_18010DE78
0x18010de55  mov     rcx, [rbp+7E8h]; this
0x18010de5c  mov     ebx, 8007000Eh
0x18010de61  mov     r9d, ebx; char *
0x18010de64  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010de6b  lea     edx, [rax+52h]; void *
0x18010de6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010de73  jmp     loc_18010E0F3
0x18010de78  mov     [rbp+7E0h+Src], 0
0x18010de80  mov     [rbp+7E0h+var_824], 0
0x18010de87  xor     edx, edx; Val
0x18010de89  mov     r8d, 800h; Size
0x18010de8f  lea     rcx, [rbp+7E0h+var_820]; void *
0x18010de93  call    memset_0
0x18010de98  mov     [rbp+7E0h+var_820], bl
0x18010de9b  mov     [rbp+7E0h+var_828], 45h ; 'E'
0x18010dea2  mov     rcx, rsi; void *
0x18010dea5  lea     rdx, [rbp+7E0h+Src]; Src
0x18010dea9  mov     r8d, 810h; Size
0x18010deaf  call    memcpy_0
0x18010deb4  mov     rax, [rsp+8E0h+var_878]
0x18010deb9  mov     [rax+0Ch], r14d
0x18010debd  lea     rax, [rbp+7E0h+arg_18]
0x18010dec4  mov     [rbp+7E0h+var_848], rax
0x18010dec8  lea     rax, [rsp+8E0h+var_878]
0x18010decd  mov     [rbp+7E0h+var_840], rax
0x18010ded1  mov     [rbp+7E0h+var_838], 1
0x18010ded5  mov     rcx, [rdi+28h]
0x18010ded9  mov     rax, [rcx]
0x18010dedc  mov     r9d, 810h
0x18010dee2  mov     r8, [rsp+8E0h+var_878]
0x18010dee7  mov     edx, r14d
0x18010deea  mov     rax, [rax+20h]
0x18010deee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010def3  mov     ebx, eax
0x18010def5  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x18010def9  call    cs:__imp_QueryPerformanceCounter
0x18010deff  xorps   xmm6, xmm6
0x18010df02  cmp     qword ptr [rdi+48h], 0
0x18010df07  jz      short loc_18010DF2B
0x18010df09  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x18010df0d  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x18010df11  cvtsi2ss xmm6, rcx
0x18010df16  mulss   xmm6, cs:__real@447a0000
0x18010df1e  xorps   xmm0, xmm0
0x18010df21  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x18010df27  divss   xmm6, xmm0
0x18010df2b  mov     rcx, [rsp+8E0h+var_878]
0x18010df30  cmp     dword ptr [rcx+8], 1
0x18010df34  jnz     loc_18010DFF0
0x18010df3a  mov     [rsp+8E0h+var_870], 0
0x18010df43  lea     rdx, [rsp+8E0h+var_870]
0x18010df48  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x18010df4d  test    eax, eax
0x18010df4f  js      loc_18010E061
0x18010df55  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x18010df5a  mov     r8, rax
0x18010df5d  mov     ecx, [rax]
0x18010df5f  cmp     ecx, 4
0x18010df62  jbe     loc_18010E061
0x18010df68  mov     [rbp+7E0h+arg_0], ebx
0x18010df6e  movss   [rsp+8E0h+var_868], xmm6
0x18010df74  mov     [rbp+7E0h+var_860], rdi
0x18010df78  mov     rdx, [rsp+8E0h+var_870]
0x18010df7d  mov     ecx, [rdx+10h]
0x18010df80  mov     [rsp+8E0h+var_864], ecx
0x18010df84  mov     ecx, [rdx+4]
0x18010df87  mov     [rsp+8E0h+var_880], ecx
0x18010df8b  mov     eax, [rdx+8]
0x18010df8e  mov     [rsp+8E0h+var_880+4], eax
0x18010df92  mov     eax, [rdx]
0x18010df94  mov     dword ptr [rsp+8E0h+var_870], eax
0x18010df98  lea     rax, [rbp+7E0h+arg_0]
0x18010df9f  mov     [rsp+8E0h+var_890], rax
0x18010dfa4  lea     rax, [rsp+8E0h+var_868]
0x18010dfa9  mov     [rsp+8E0h+var_898], rax
0x18010dfae  lea     rax, [rbp+7E0h+var_860]
0x18010dfb2  mov     [rsp+8E0h+var_8A0], rax
0x18010dfb7  lea     rax, [rsp+8E0h+var_864]
0x18010dfbc  mov     [rsp+8E0h+var_8A8], rax
0x18010dfc1  lea     rax, [rsp+8E0h+var_880]
0x18010dfc6  mov     [rsp+8E0h+var_8B0], rax
0x18010dfcb  lea     rax, [rsp+8E0h+var_880+4]
0x18010dfd0  mov     [rsp+8E0h+var_8B8], rax
0x18010dfd5  lea     rax, [rsp+8E0h+var_870]
0x18010dfda  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x18010dfdf  lea     rdx, unk_180172B30
0x18010dfe6  mov     rcx, r8
0x18010dfe9  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18010dfee  jmp     short loc_18010E061
0x18010dff0  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x18010dff5  mov     ecx, [rax]
0x18010dff7  cmp     ecx, 4
0x18010dffa  jbe     short loc_18010E061
0x18010dffc  mov     [rbp+7E0h+arg_0], ebx
0x18010e002  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x18010e008  mov     [rbp+7E0h+var_860], rdi
0x18010e00c  mov     rcx, [rsp+8E0h+var_878]
0x18010e011  mov     edx, [rcx+8]
0x18010e014  mov     [rsp+8E0h+var_880+4], edx
0x18010e018  mov     ecx, [rdi+30h]
0x18010e01b  mov     [rsp+8E0h+var_880], ecx
0x18010e01f  lea     rcx, [rbp+7E0h+arg_0]
0x18010e026  mov     [rsp+8E0h+var_8A0], rcx
0x18010e02b  lea     rcx, [rsp+8E0h+var_870]
0x18010e030  mov     [rsp+8E0h+var_8A8], rcx
0x18010e035  lea     rcx, [rbp+7E0h+var_860]
0x18010e039  mov     [rsp+8E0h+var_8B0], rcx
0x18010e03e  lea     rcx, [rsp+8E0h+var_880+4]
0x18010e043  mov     [rsp+8E0h+var_8B8], rcx
0x18010e048  lea     rcx, [rsp+8E0h+var_880]
0x18010e04d  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x18010e052  lea     rdx, unk_180172AE3
0x18010e059  mov     rcx, rax
0x18010e05c  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18010e061  mov     rcx, [rbp+7E8h]; this
0x18010e068  test    ebx, ebx
0x18010e06a  jns     short loc_18010E08F
0x18010e06c  mov     r9d, ebx; char *
0x18010e06f  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010e076  mov     edx, 81h; void *
0x18010e07b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010e080  mov     rax, [rdi]
0x18010e083  mov     rcx, rdi
0x18010e086  mov     rax, [rax+20h]
0x18010e08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010e08f  mov     ebx, [rdi+40h]
0x18010e092  test    ebx, ebx
0x18010e094  jns     short loc_18010E09D
0x18010e096  mov     edx, 8Ah
0x18010e09b  jmp     short loc_18010E0AE
0x18010e09d  mov     rcx, [rsp+8E0h+var_878]
0x18010e0a2  mov     ebx, [rcx+4]
0x18010e0a5  test    ebx, ebx
0x18010e0a7  jns     short loc_18010E0C6
0x18010e0a9  mov     edx, 8Ch; void *
0x18010e0ae  mov     r9d, ebx; char *
0x18010e0b1  mov     rcx, [rbp+7E8h]; this
0x18010e0b8  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010e0bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010e0c4  jmp     short loc_18010E0E4
0x18010e0c6  mov     rdx, [rbp+7E0h+arg_20]
0x18010e0cd  call    ??$CastTo@UXvmPreStop@@@XvmMessage@@QEAAJPEAPEAUXvmPreStop@@@Z; XvmMessage::CastTo<XvmPreStop>(XvmPreStop * *)
0x18010e0d2  mov     ebx, eax
0x18010e0d4  test    eax, eax
0x18010e0d6  jns     short loc_18010E0E2
0x18010e0d8  mov     r9d, eax
0x18010e0db  mov     edx, 8Dh
0x18010e0e0  jmp     short loc_18010E0B1
0x18010e0e2  xor     ebx, ebx
0x18010e0e4  mov     rcx, [rbp+7E0h+arg_18]
0x18010e0eb  mov     rax, [rsp+8E0h+var_878]
0x18010e0f0  mov     [rcx], rax
0x18010e0f3  mov     eax, ebx
0x18010e0f5  lea     r11, [rsp+8E0h+var_10]
0x18010e0fd  mov     rbx, [r11+28h]
0x18010e101  mov     rsi, [r11+30h]
0x18010e105  movaps  xmm6, xmmword ptr [r11-10h]
0x18010e10a  mov     rsp, r11
0x18010e10d  pop     r14
0x18010e10f  pop     rdi
0x18010e110  pop     rbp
0x18010e111  retn
```
