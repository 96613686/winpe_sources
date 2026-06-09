# CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeSetMasterVolumeLevel>(uint,XvmAudioEndpointVolumeSetMasterVolumeLevel,XvmMessage * *,XvmAudioEndpointVolumeSetMasterVolumeLevel * *)

- ea: `0x1800b5694`
- end: `0x1800b59ee`
- name: `??$SendAndValidateResponse@UXvmAudioEndpointVolumeSetMasterVolumeLevel@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeSetMasterVolumeLevel@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `858`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b7610`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a5fa8`
- `0x1800b5694`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b56d6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b57d5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b56d6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b57d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b570a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b570a`

## string_xrefs

- `0x1800b56ed`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b572c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b594b`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b5994`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeSetMasterVolumeLevel>(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
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
  _QWORD v34[2]; // [rsp+C8h] [rbp-40h] BYREF
  int v35; // [rsp+D8h] [rbp-30h]
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
    v34[0] = *(_QWORD *)a3;
    v34[1] = *(_QWORD *)(a3 + 8);
    v35 = *(_DWORD *)(a3 + 16);
    v32 = 82;
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
            (unsigned int)&dword_18016729C,
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
          (unsigned int)byte_180167189,
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
        v18 = XvmMessage::CastTo<XvmAudioEndpointVolumeSetMasterVolumeLevel>(v21, v40, v12);
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
0x1800b5694  mov     rax, rsp
0x1800b5697  mov     [rax+10h], rbx
0x1800b569b  mov     [rax+18h], rsi
0x1800b569f  mov     [rax+20h], r9
0x1800b56a3  push    rbp
0x1800b56a4  push    rdi
0x1800b56a5  push    r14
0x1800b56a7  lea     rbp, [rax-7E8h]
0x1800b56ae  sub     rsp, 8D0h
0x1800b56b5  movaps  xmmword ptr [rax-28h], xmm6
0x1800b56b9  mov     rsi, r8
0x1800b56bc  mov     r14d, edx
0x1800b56bf  mov     rbx, rcx
0x1800b56c2  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800b56ca  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800b56d2  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800b56d6  call    cs:__imp_QueryPerformanceCounter
0x1800b56dc  mov     edi, [rbx+40h]
0x1800b56df  test    edi, edi
0x1800b56e1  jns     short loc_1800B5705
0x1800b56e3  mov     rcx, [rbp+7E8h]; this
0x1800b56ea  mov     r9d, edi; char *
0x1800b56ed  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b56f4  mov     edx, 4Fh ; 'O'; void *
0x1800b56f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b56fe  mov     eax, edi
0x1800b5700  jmp     loc_1800B59D1
0x1800b5705  mov     ecx, 810h; cb
0x1800b570a  call    cs:__imp_CoTaskMemAlloc
0x1800b5710  mov     rdi, rax
0x1800b5713  mov     [rsp+8E0h+var_878], rax
0x1800b5718  test    rax, rax
0x1800b571b  jnz     short loc_1800B5740
0x1800b571d  mov     rcx, [rbp+7E8h]; this
0x1800b5724  mov     ebx, 8007000Eh
0x1800b5729  mov     r9d, ebx; char *
0x1800b572c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b5733  lea     edx, [rax+52h]; void *
0x1800b5736  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b573b  jmp     loc_1800B59CF
0x1800b5740  mov     [rbp+7E0h+Src], 0
0x1800b5748  mov     [rbp+7E0h+var_824], 0
0x1800b574f  xor     edx, edx; Val
0x1800b5751  mov     r8d, 800h; Size
0x1800b5757  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800b575b  call    memset_0
0x1800b5760  mov     rax, [rsi]
0x1800b5763  mov     [rbp+7E0h+var_820], rax
0x1800b5767  movsd   xmm0, qword ptr [rsi+8]
0x1800b576c  movsd   [rbp+7E0h+var_818], xmm0
0x1800b5771  mov     eax, [rsi+10h]
0x1800b5774  mov     [rbp+7E0h+var_810], eax
0x1800b5777  mov     [rbp+7E0h+var_828], 52h ; 'R'
0x1800b577e  mov     rcx, rdi; void *
0x1800b5781  lea     rdx, [rbp+7E0h+Src]; Src
0x1800b5785  mov     r8d, 810h; Size
0x1800b578b  call    memcpy_0
0x1800b5790  mov     rax, [rsp+8E0h+var_878]
0x1800b5795  mov     [rax+0Ch], r14d
0x1800b5799  lea     rax, [rbp+7E0h+arg_18]
0x1800b57a0  mov     [rbp+7E0h+var_848], rax
0x1800b57a4  lea     rax, [rsp+8E0h+var_878]
0x1800b57a9  mov     [rbp+7E0h+var_840], rax
0x1800b57ad  mov     [rbp+7E0h+var_838], 1
0x1800b57b1  mov     rcx, [rbx+28h]
0x1800b57b5  mov     rax, [rcx]
0x1800b57b8  mov     r9d, 810h
0x1800b57be  mov     r8, [rsp+8E0h+var_878]
0x1800b57c3  mov     edx, r14d
0x1800b57c6  mov     rax, [rax+20h]
0x1800b57ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b57cf  mov     edi, eax
0x1800b57d1  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800b57d5  call    cs:__imp_QueryPerformanceCounter
0x1800b57db  xorps   xmm6, xmm6
0x1800b57de  cmp     qword ptr [rbx+48h], 0
0x1800b57e3  jz      short loc_1800B5807
0x1800b57e5  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800b57e9  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800b57ed  cvtsi2ss xmm6, rcx
0x1800b57f2  mulss   xmm6, cs:__real@447a0000
0x1800b57fa  xorps   xmm0, xmm0
0x1800b57fd  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800b5803  divss   xmm6, xmm0
0x1800b5807  mov     rcx, [rsp+8E0h+var_878]
0x1800b580c  cmp     dword ptr [rcx+8], 1
0x1800b5810  jnz     loc_1800B58CC
0x1800b5816  mov     [rsp+8E0h+var_870], 0
0x1800b581f  lea     rdx, [rsp+8E0h+var_870]
0x1800b5824  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b5829  test    eax, eax
0x1800b582b  js      loc_1800B593D
0x1800b5831  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b5836  mov     r8, rax
0x1800b5839  mov     ecx, [rax]
0x1800b583b  cmp     ecx, 4
0x1800b583e  jbe     loc_1800B593D
0x1800b5844  mov     [rbp+7E0h+arg_0], edi
0x1800b584a  movss   [rsp+8E0h+var_868], xmm6
0x1800b5850  mov     [rbp+7E0h+var_860], rbx
0x1800b5854  mov     rdx, [rsp+8E0h+var_870]
0x1800b5859  mov     ecx, [rdx+10h]
0x1800b585c  mov     [rsp+8E0h+var_864], ecx
0x1800b5860  mov     ecx, [rdx+4]
0x1800b5863  mov     [rsp+8E0h+var_880], ecx
0x1800b5867  mov     eax, [rdx+8]
0x1800b586a  mov     [rsp+8E0h+var_880+4], eax
0x1800b586e  mov     eax, [rdx]
0x1800b5870  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800b5874  lea     rax, [rbp+7E0h+arg_0]
0x1800b587b  mov     [rsp+8E0h+var_890], rax
0x1800b5880  lea     rax, [rsp+8E0h+var_868]
0x1800b5885  mov     [rsp+8E0h+var_898], rax
0x1800b588a  lea     rax, [rbp+7E0h+var_860]
0x1800b588e  mov     [rsp+8E0h+var_8A0], rax
0x1800b5893  lea     rax, [rsp+8E0h+var_864]
0x1800b5898  mov     [rsp+8E0h+var_8A8], rax
0x1800b589d  lea     rax, [rsp+8E0h+var_880]
0x1800b58a2  mov     [rsp+8E0h+var_8B0], rax
0x1800b58a7  lea     rax, [rsp+8E0h+var_880+4]
0x1800b58ac  mov     [rsp+8E0h+var_8B8], rax
0x1800b58b1  lea     rax, [rsp+8E0h+var_870]
0x1800b58b6  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800b58bb  lea     rdx, dword_18016729C
0x1800b58c2  mov     rcx, r8
0x1800b58c5  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b58ca  jmp     short loc_1800B593D
0x1800b58cc  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b58d1  mov     ecx, [rax]
0x1800b58d3  cmp     ecx, 4
0x1800b58d6  jbe     short loc_1800B593D
0x1800b58d8  mov     [rbp+7E0h+arg_0], edi
0x1800b58de  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800b58e4  mov     [rbp+7E0h+var_860], rbx
0x1800b58e8  mov     rcx, [rsp+8E0h+var_878]
0x1800b58ed  mov     edx, [rcx+8]
0x1800b58f0  mov     [rsp+8E0h+var_880+4], edx
0x1800b58f4  mov     ecx, [rbx+30h]
0x1800b58f7  mov     [rsp+8E0h+var_880], ecx
0x1800b58fb  lea     rcx, [rbp+7E0h+arg_0]
0x1800b5902  mov     [rsp+8E0h+var_8A0], rcx
0x1800b5907  lea     rcx, [rsp+8E0h+var_870]
0x1800b590c  mov     [rsp+8E0h+var_8A8], rcx
0x1800b5911  lea     rcx, [rbp+7E0h+var_860]
0x1800b5915  mov     [rsp+8E0h+var_8B0], rcx
0x1800b591a  lea     rcx, [rsp+8E0h+var_880+4]
0x1800b591f  mov     [rsp+8E0h+var_8B8], rcx
0x1800b5924  lea     rcx, [rsp+8E0h+var_880]
0x1800b5929  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800b592e  lea     rdx, byte_180167189
0x1800b5935  mov     rcx, rax
0x1800b5938  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b593d  mov     rcx, [rbp+7E8h]; this
0x1800b5944  test    edi, edi
0x1800b5946  jns     short loc_1800B596B
0x1800b5948  mov     r9d, edi; char *
0x1800b594b  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b5952  mov     edx, 81h; void *
0x1800b5957  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b595c  mov     rax, [rbx]
0x1800b595f  mov     rcx, rbx
0x1800b5962  mov     rax, [rax+20h]
0x1800b5966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b596b  mov     ebx, [rbx+40h]
0x1800b596e  test    ebx, ebx
0x1800b5970  jns     short loc_1800B5979
0x1800b5972  mov     edx, 8Ah
0x1800b5977  jmp     short loc_1800B598A
0x1800b5979  mov     rcx, [rsp+8E0h+var_878]
0x1800b597e  mov     ebx, [rcx+4]
0x1800b5981  test    ebx, ebx
0x1800b5983  jns     short loc_1800B59A2
0x1800b5985  mov     edx, 8Ch; void *
0x1800b598a  mov     r9d, ebx; char *
0x1800b598d  mov     rcx, [rbp+7E8h]; this
0x1800b5994  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b599b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b59a0  jmp     short loc_1800B59C0
0x1800b59a2  mov     rdx, [rbp+7E0h+arg_20]
0x1800b59a9  call    ??$CastTo@UXvmAudioEndpointVolumeSetMasterVolumeLevel@@@XvmMessage@@QEAAJPEAPEAUXvmAudioEndpointVolumeSetMasterVolumeLevel@@@Z; XvmMessage::CastTo<XvmAudioEndpointVolumeSetMasterVolumeLevel>(XvmAudioEndpointVolumeSetMasterVolumeLevel * *)
0x1800b59ae  mov     ebx, eax
0x1800b59b0  test    eax, eax
0x1800b59b2  jns     short loc_1800B59BE
0x1800b59b4  mov     r9d, eax
0x1800b59b7  mov     edx, 8Dh
0x1800b59bc  jmp     short loc_1800B598D
0x1800b59be  xor     ebx, ebx
0x1800b59c0  mov     rcx, [rbp+7E0h+arg_18]
0x1800b59c7  mov     rax, [rsp+8E0h+var_878]
0x1800b59cc  mov     [rcx], rax
0x1800b59cf  mov     eax, ebx
0x1800b59d1  lea     r11, [rsp+8E0h+var_10]
0x1800b59d9  mov     rbx, [r11+28h]
0x1800b59dd  mov     rsi, [r11+30h]
0x1800b59e1  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b59e6  mov     rsp, r11
0x1800b59e9  pop     r14
0x1800b59eb  pop     rdi
0x1800b59ec  pop     rbp
0x1800b59ed  retn
```
