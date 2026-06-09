# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetMaxFrameCount>(uint,XvmGetMaxFrameCount,XvmMessage * *,XvmGetMaxFrameCount * *)

- ea: `0x1800fefb0`
- end: `0x1800ff31a`
- name: `??$SendAndValidateResponse@UXvmGetMaxFrameCount@@@CGuestXvmAudioObject@@QEAAJIUXvmGetMaxFrameCount@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `874`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180101200`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800fa0c0`
- `0x1800fefb0`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800feff2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ff101`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800feff2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800ff101`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ff026`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ff026`

## string_xrefs

- `0x1800ff009`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ff048`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ff277`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800ff2c0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetMaxFrameCount>(
        __int64 a1,
        unsigned int a2,
        _OWORD *a3,
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
  int MaxFrame; // eax
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
  _OWORD v34[3]; // [rsp+C8h] [rbp-40h] BYREF
  _OWORD v35[126]; // [rsp+F8h] [rbp-10h]
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
    v34[0] = *a3;
    v34[1] = a3[1];
    v34[2] = a3[2];
    v35[0] = a3[3];
    *(_OWORD *)((char *)v35 + 12) = *(_OWORD *)((char *)a3 + 60);
    v32 = 51;
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
            (unsigned int)&byte_180170E77,
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
          (unsigned int)word_180170E2A,
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
        MaxFrame = XvmMessage::CastTo<XvmGetMaxFrameCount>(v21, v40, v12);
        v9 = MaxFrame;
        if ( MaxFrame >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)MaxFrame;
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
0x1800fefb0  mov     rax, rsp
0x1800fefb3  mov     [rax+10h], rbx
0x1800fefb7  mov     [rax+18h], rsi
0x1800fefbb  mov     [rax+20h], r9
0x1800fefbf  push    rbp
0x1800fefc0  push    rdi
0x1800fefc1  push    r14
0x1800fefc3  lea     rbp, [rax-7E8h]
0x1800fefca  sub     rsp, 8D0h
0x1800fefd1  movaps  xmmword ptr [rax-28h], xmm6
0x1800fefd5  mov     rsi, r8
0x1800fefd8  mov     r14d, edx
0x1800fefdb  mov     rbx, rcx
0x1800fefde  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800fefe6  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800fefee  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800feff2  call    cs:__imp_QueryPerformanceCounter
0x1800feff8  mov     edi, [rbx+40h]
0x1800feffb  test    edi, edi
0x1800feffd  jns     short loc_1800FF021
0x1800fefff  mov     rcx, [rbp+7E8h]; this
0x1800ff006  mov     r9d, edi; char *
0x1800ff009  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ff010  mov     edx, 4Fh ; 'O'; void *
0x1800ff015  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ff01a  mov     eax, edi
0x1800ff01c  jmp     loc_1800FF2FD
0x1800ff021  mov     ecx, 810h; cb
0x1800ff026  call    cs:__imp_CoTaskMemAlloc
0x1800ff02c  mov     rdi, rax
0x1800ff02f  mov     [rsp+8E0h+var_878], rax
0x1800ff034  test    rax, rax
0x1800ff037  jnz     short loc_1800FF05C
0x1800ff039  mov     rcx, [rbp+7E8h]; this
0x1800ff040  mov     ebx, 8007000Eh
0x1800ff045  mov     r9d, ebx; char *
0x1800ff048  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ff04f  lea     edx, [rax+52h]; void *
0x1800ff052  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ff057  jmp     loc_1800FF2FB
0x1800ff05c  mov     [rbp+7E0h+Src], 0
0x1800ff064  mov     [rbp+7E0h+var_824], 0
0x1800ff06b  xor     edx, edx; Val
0x1800ff06d  mov     r8d, 800h; Size
0x1800ff073  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800ff077  call    memset_0
0x1800ff07c  movups  xmm0, xmmword ptr [rsi]
0x1800ff07f  movaps  [rbp+7E0h+var_820], xmm0
0x1800ff083  movups  xmm1, xmmword ptr [rsi+10h]
0x1800ff087  movaps  [rbp+7E0h+var_810], xmm1
0x1800ff08b  movups  xmm0, xmmword ptr [rsi+20h]
0x1800ff08f  movaps  [rbp+7E0h+var_800], xmm0
0x1800ff093  movups  xmm1, xmmword ptr [rsi+30h]
0x1800ff097  movaps  [rbp+7E0h+var_7F0], xmm1
0x1800ff09b  movups  xmm0, xmmword ptr [rsi+3Ch]
0x1800ff09f  movups  [rbp+7E0h+var_7F0+0Ch], xmm0
0x1800ff0a3  mov     [rbp+7E0h+var_828], 33h ; '3'
0x1800ff0aa  mov     rcx, rdi; void *
0x1800ff0ad  lea     rdx, [rbp+7E0h+Src]; Src
0x1800ff0b1  mov     r8d, 810h; Size
0x1800ff0b7  call    memcpy_0
0x1800ff0bc  mov     rax, [rsp+8E0h+var_878]
0x1800ff0c1  mov     [rax+0Ch], r14d
0x1800ff0c5  lea     rax, [rbp+7E0h+arg_18]
0x1800ff0cc  mov     [rbp+7E0h+var_848], rax
0x1800ff0d0  lea     rax, [rsp+8E0h+var_878]
0x1800ff0d5  mov     [rbp+7E0h+var_840], rax
0x1800ff0d9  mov     [rbp+7E0h+var_838], 1
0x1800ff0dd  mov     rcx, [rbx+28h]
0x1800ff0e1  mov     rax, [rcx]
0x1800ff0e4  mov     r9d, 810h
0x1800ff0ea  mov     r8, [rsp+8E0h+var_878]
0x1800ff0ef  mov     edx, r14d
0x1800ff0f2  mov     rax, [rax+20h]
0x1800ff0f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff0fb  mov     edi, eax
0x1800ff0fd  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800ff101  call    cs:__imp_QueryPerformanceCounter
0x1800ff107  xorps   xmm6, xmm6
0x1800ff10a  cmp     qword ptr [rbx+48h], 0
0x1800ff10f  jz      short loc_1800FF133
0x1800ff111  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800ff115  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800ff119  cvtsi2ss xmm6, rcx
0x1800ff11e  mulss   xmm6, cs:__real@447a0000
0x1800ff126  xorps   xmm0, xmm0
0x1800ff129  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800ff12f  divss   xmm6, xmm0
0x1800ff133  mov     rcx, [rsp+8E0h+var_878]
0x1800ff138  cmp     dword ptr [rcx+8], 1
0x1800ff13c  jnz     loc_1800FF1F8
0x1800ff142  mov     [rsp+8E0h+var_870], 0
0x1800ff14b  lea     rdx, [rsp+8E0h+var_870]
0x1800ff150  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800ff155  test    eax, eax
0x1800ff157  js      loc_1800FF269
0x1800ff15d  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ff162  mov     r8, rax
0x1800ff165  mov     ecx, [rax]
0x1800ff167  cmp     ecx, 4
0x1800ff16a  jbe     loc_1800FF269
0x1800ff170  mov     [rbp+7E0h+arg_0], edi
0x1800ff176  movss   [rsp+8E0h+var_868], xmm6
0x1800ff17c  mov     [rbp+7E0h+var_860], rbx
0x1800ff180  mov     rdx, [rsp+8E0h+var_870]
0x1800ff185  mov     ecx, [rdx+10h]
0x1800ff188  mov     [rsp+8E0h+var_864], ecx
0x1800ff18c  mov     ecx, [rdx+4]
0x1800ff18f  mov     [rsp+8E0h+var_880], ecx
0x1800ff193  mov     eax, [rdx+8]
0x1800ff196  mov     [rsp+8E0h+var_880+4], eax
0x1800ff19a  mov     eax, [rdx]
0x1800ff19c  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800ff1a0  lea     rax, [rbp+7E0h+arg_0]
0x1800ff1a7  mov     [rsp+8E0h+var_890], rax
0x1800ff1ac  lea     rax, [rsp+8E0h+var_868]
0x1800ff1b1  mov     [rsp+8E0h+var_898], rax
0x1800ff1b6  lea     rax, [rbp+7E0h+var_860]
0x1800ff1ba  mov     [rsp+8E0h+var_8A0], rax
0x1800ff1bf  lea     rax, [rsp+8E0h+var_864]
0x1800ff1c4  mov     [rsp+8E0h+var_8A8], rax
0x1800ff1c9  lea     rax, [rsp+8E0h+var_880]
0x1800ff1ce  mov     [rsp+8E0h+var_8B0], rax
0x1800ff1d3  lea     rax, [rsp+8E0h+var_880+4]
0x1800ff1d8  mov     [rsp+8E0h+var_8B8], rax
0x1800ff1dd  lea     rax, [rsp+8E0h+var_870]
0x1800ff1e2  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800ff1e7  lea     rdx, byte_180170E77
0x1800ff1ee  mov     rcx, r8
0x1800ff1f1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ff1f6  jmp     short loc_1800FF269
0x1800ff1f8  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800ff1fd  mov     ecx, [rax]
0x1800ff1ff  cmp     ecx, 4
0x1800ff202  jbe     short loc_1800FF269
0x1800ff204  mov     [rbp+7E0h+arg_0], edi
0x1800ff20a  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800ff210  mov     [rbp+7E0h+var_860], rbx
0x1800ff214  mov     rcx, [rsp+8E0h+var_878]
0x1800ff219  mov     edx, [rcx+8]
0x1800ff21c  mov     [rsp+8E0h+var_880+4], edx
0x1800ff220  mov     ecx, [rbx+30h]
0x1800ff223  mov     [rsp+8E0h+var_880], ecx
0x1800ff227  lea     rcx, [rbp+7E0h+arg_0]
0x1800ff22e  mov     [rsp+8E0h+var_8A0], rcx
0x1800ff233  lea     rcx, [rsp+8E0h+var_870]
0x1800ff238  mov     [rsp+8E0h+var_8A8], rcx
0x1800ff23d  lea     rcx, [rbp+7E0h+var_860]
0x1800ff241  mov     [rsp+8E0h+var_8B0], rcx
0x1800ff246  lea     rcx, [rsp+8E0h+var_880+4]
0x1800ff24b  mov     [rsp+8E0h+var_8B8], rcx
0x1800ff250  lea     rcx, [rsp+8E0h+var_880]
0x1800ff255  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800ff25a  lea     rdx, word_180170E2A
0x1800ff261  mov     rcx, rax
0x1800ff264  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800ff269  mov     rcx, [rbp+7E8h]; this
0x1800ff270  test    edi, edi
0x1800ff272  jns     short loc_1800FF297
0x1800ff274  mov     r9d, edi; char *
0x1800ff277  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ff27e  mov     edx, 81h; void *
0x1800ff283  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ff288  mov     rax, [rbx]
0x1800ff28b  mov     rcx, rbx
0x1800ff28e  mov     rax, [rax+20h]
0x1800ff292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ff297  mov     ebx, [rbx+40h]
0x1800ff29a  test    ebx, ebx
0x1800ff29c  jns     short loc_1800FF2A5
0x1800ff29e  mov     edx, 8Ah
0x1800ff2a3  jmp     short loc_1800FF2B6
0x1800ff2a5  mov     rcx, [rsp+8E0h+var_878]
0x1800ff2aa  mov     ebx, [rcx+4]
0x1800ff2ad  test    ebx, ebx
0x1800ff2af  jns     short loc_1800FF2CE
0x1800ff2b1  mov     edx, 8Ch; void *
0x1800ff2b6  mov     r9d, ebx; char *
0x1800ff2b9  mov     rcx, [rbp+7E8h]; this
0x1800ff2c0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800ff2c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ff2cc  jmp     short loc_1800FF2EC
0x1800ff2ce  mov     rdx, [rbp+7E0h+arg_20]
0x1800ff2d5  call    ??$CastTo@UXvmGetMaxFrameCount@@@XvmMessage@@QEAAJPEAPEAUXvmGetMaxFrameCount@@@Z; XvmMessage::CastTo<XvmGetMaxFrameCount>(XvmGetMaxFrameCount * *)
0x1800ff2da  mov     ebx, eax
0x1800ff2dc  test    eax, eax
0x1800ff2de  jns     short loc_1800FF2EA
0x1800ff2e0  mov     r9d, eax
0x1800ff2e3  mov     edx, 8Dh
0x1800ff2e8  jmp     short loc_1800FF2B9
0x1800ff2ea  xor     ebx, ebx
0x1800ff2ec  mov     rcx, [rbp+7E0h+arg_18]
0x1800ff2f3  mov     rax, [rsp+8E0h+var_878]
0x1800ff2f8  mov     [rcx], rax
0x1800ff2fb  mov     eax, ebx
0x1800ff2fd  lea     r11, [rsp+8E0h+var_10]
0x1800ff305  mov     rbx, [r11+28h]
0x1800ff309  mov     rsi, [r11+30h]
0x1800ff30d  movaps  xmm6, xmmword ptr [r11-10h]
0x1800ff312  mov     rsp, r11
0x1800ff315  pop     r14
0x1800ff317  pop     rdi
0x1800ff318  pop     rbp
0x1800ff319  retn
```
