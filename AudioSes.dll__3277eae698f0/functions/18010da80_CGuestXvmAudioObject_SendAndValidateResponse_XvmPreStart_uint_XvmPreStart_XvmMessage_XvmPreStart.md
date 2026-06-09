# CGuestXvmAudioObject::SendAndValidateResponse<XvmPreStart>(uint,XvmPreStart,XvmMessage * *,XvmPreStart * *)

- ea: `0x18010da80`
- end: `0x18010ddc6`
- name: `??$SendAndValidateResponse@UXvmPreStart@@@CGuestXvmAudioObject@@QEAAJIUXvmPreStart@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `838`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18010ea9c`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x180102230`
- `0x18010da80`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010dac2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010dbad`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010dac2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18010dbad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010daf6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18010daf6`

## string_xrefs

- `0x18010dad9`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18010db18`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18010dd23`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x18010dd6c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmPreStart>(__int64 a1, unsigned int a2, char a3, ...)
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
    v32 = 68;
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
            (unsigned int)byte_180172BA9,
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
          (unsigned int)&dword_180172B5C,
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
        v18 = XvmMessage::CastTo<XvmPreStart>(v21, v39, v12);
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
0x18010da80  mov     rax, rsp
0x18010da83  mov     [rax+10h], rbx
0x18010da87  mov     [rax+18h], rsi
0x18010da8b  mov     [rax+20h], r9
0x18010da8f  push    rbp
0x18010da90  push    rdi
0x18010da91  push    r14
0x18010da93  lea     rbp, [rax-7E8h]
0x18010da9a  sub     rsp, 8D0h
0x18010daa1  movaps  xmmword ptr [rax-28h], xmm6
0x18010daa5  mov     bl, r8b
0x18010daa8  mov     r14d, edx
0x18010daab  mov     rdi, rcx
0x18010daae  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x18010dab6  mov     qword ptr [rbp+7E0h+var_858], 0
0x18010dabe  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x18010dac2  call    cs:__imp_QueryPerformanceCounter
0x18010dac8  mov     esi, [rdi+40h]
0x18010dacb  test    esi, esi
0x18010dacd  jns     short loc_18010DAF1
0x18010dacf  mov     rcx, [rbp+7E8h]; this
0x18010dad6  mov     r9d, esi; char *
0x18010dad9  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010dae0  mov     edx, 4Fh ; 'O'; void *
0x18010dae5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010daea  mov     eax, esi
0x18010daec  jmp     loc_18010DDA9
0x18010daf1  mov     ecx, 810h; cb
0x18010daf6  call    cs:__imp_CoTaskMemAlloc
0x18010dafc  mov     rsi, rax
0x18010daff  mov     [rsp+8E0h+var_878], rax
0x18010db04  test    rax, rax
0x18010db07  jnz     short loc_18010DB2C
0x18010db09  mov     rcx, [rbp+7E8h]; this
0x18010db10  mov     ebx, 8007000Eh
0x18010db15  mov     r9d, ebx; char *
0x18010db18  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010db1f  lea     edx, [rax+52h]; void *
0x18010db22  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010db27  jmp     loc_18010DDA7
0x18010db2c  mov     [rbp+7E0h+Src], 0
0x18010db34  mov     [rbp+7E0h+var_824], 0
0x18010db3b  xor     edx, edx; Val
0x18010db3d  mov     r8d, 800h; Size
0x18010db43  lea     rcx, [rbp+7E0h+var_820]; void *
0x18010db47  call    memset_0
0x18010db4c  mov     [rbp+7E0h+var_820], bl
0x18010db4f  mov     [rbp+7E0h+var_828], 44h ; 'D'
0x18010db56  mov     rcx, rsi; void *
0x18010db59  lea     rdx, [rbp+7E0h+Src]; Src
0x18010db5d  mov     r8d, 810h; Size
0x18010db63  call    memcpy_0
0x18010db68  mov     rax, [rsp+8E0h+var_878]
0x18010db6d  mov     [rax+0Ch], r14d
0x18010db71  lea     rax, [rbp+7E0h+arg_18]
0x18010db78  mov     [rbp+7E0h+var_848], rax
0x18010db7c  lea     rax, [rsp+8E0h+var_878]
0x18010db81  mov     [rbp+7E0h+var_840], rax
0x18010db85  mov     [rbp+7E0h+var_838], 1
0x18010db89  mov     rcx, [rdi+28h]
0x18010db8d  mov     rax, [rcx]
0x18010db90  mov     r9d, 810h
0x18010db96  mov     r8, [rsp+8E0h+var_878]
0x18010db9b  mov     edx, r14d
0x18010db9e  mov     rax, [rax+20h]
0x18010dba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010dba7  mov     ebx, eax
0x18010dba9  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x18010dbad  call    cs:__imp_QueryPerformanceCounter
0x18010dbb3  xorps   xmm6, xmm6
0x18010dbb6  cmp     qword ptr [rdi+48h], 0
0x18010dbbb  jz      short loc_18010DBDF
0x18010dbbd  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x18010dbc1  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x18010dbc5  cvtsi2ss xmm6, rcx
0x18010dbca  mulss   xmm6, cs:__real@447a0000
0x18010dbd2  xorps   xmm0, xmm0
0x18010dbd5  cvtsi2ss xmm0, qword ptr [rdi+48h]
0x18010dbdb  divss   xmm6, xmm0
0x18010dbdf  mov     rcx, [rsp+8E0h+var_878]
0x18010dbe4  cmp     dword ptr [rcx+8], 1
0x18010dbe8  jnz     loc_18010DCA4
0x18010dbee  mov     [rsp+8E0h+var_870], 0
0x18010dbf7  lea     rdx, [rsp+8E0h+var_870]
0x18010dbfc  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x18010dc01  test    eax, eax
0x18010dc03  js      loc_18010DD15
0x18010dc09  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x18010dc0e  mov     r8, rax
0x18010dc11  mov     ecx, [rax]
0x18010dc13  cmp     ecx, 4
0x18010dc16  jbe     loc_18010DD15
0x18010dc1c  mov     [rbp+7E0h+arg_0], ebx
0x18010dc22  movss   [rsp+8E0h+var_868], xmm6
0x18010dc28  mov     [rbp+7E0h+var_860], rdi
0x18010dc2c  mov     rdx, [rsp+8E0h+var_870]
0x18010dc31  mov     ecx, [rdx+10h]
0x18010dc34  mov     [rsp+8E0h+var_864], ecx
0x18010dc38  mov     ecx, [rdx+4]
0x18010dc3b  mov     [rsp+8E0h+var_880], ecx
0x18010dc3f  mov     eax, [rdx+8]
0x18010dc42  mov     [rsp+8E0h+var_880+4], eax
0x18010dc46  mov     eax, [rdx]
0x18010dc48  mov     dword ptr [rsp+8E0h+var_870], eax
0x18010dc4c  lea     rax, [rbp+7E0h+arg_0]
0x18010dc53  mov     [rsp+8E0h+var_890], rax
0x18010dc58  lea     rax, [rsp+8E0h+var_868]
0x18010dc5d  mov     [rsp+8E0h+var_898], rax
0x18010dc62  lea     rax, [rbp+7E0h+var_860]
0x18010dc66  mov     [rsp+8E0h+var_8A0], rax
0x18010dc6b  lea     rax, [rsp+8E0h+var_864]
0x18010dc70  mov     [rsp+8E0h+var_8A8], rax
0x18010dc75  lea     rax, [rsp+8E0h+var_880]
0x18010dc7a  mov     [rsp+8E0h+var_8B0], rax
0x18010dc7f  lea     rax, [rsp+8E0h+var_880+4]
0x18010dc84  mov     [rsp+8E0h+var_8B8], rax
0x18010dc89  lea     rax, [rsp+8E0h+var_870]
0x18010dc8e  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x18010dc93  lea     rdx, byte_180172BA9
0x18010dc9a  mov     rcx, r8
0x18010dc9d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18010dca2  jmp     short loc_18010DD15
0x18010dca4  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x18010dca9  mov     ecx, [rax]
0x18010dcab  cmp     ecx, 4
0x18010dcae  jbe     short loc_18010DD15
0x18010dcb0  mov     [rbp+7E0h+arg_0], ebx
0x18010dcb6  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x18010dcbc  mov     [rbp+7E0h+var_860], rdi
0x18010dcc0  mov     rcx, [rsp+8E0h+var_878]
0x18010dcc5  mov     edx, [rcx+8]
0x18010dcc8  mov     [rsp+8E0h+var_880+4], edx
0x18010dccc  mov     ecx, [rdi+30h]
0x18010dccf  mov     [rsp+8E0h+var_880], ecx
0x18010dcd3  lea     rcx, [rbp+7E0h+arg_0]
0x18010dcda  mov     [rsp+8E0h+var_8A0], rcx
0x18010dcdf  lea     rcx, [rsp+8E0h+var_870]
0x18010dce4  mov     [rsp+8E0h+var_8A8], rcx
0x18010dce9  lea     rcx, [rbp+7E0h+var_860]
0x18010dced  mov     [rsp+8E0h+var_8B0], rcx
0x18010dcf2  lea     rcx, [rsp+8E0h+var_880+4]
0x18010dcf7  mov     [rsp+8E0h+var_8B8], rcx
0x18010dcfc  lea     rcx, [rsp+8E0h+var_880]
0x18010dd01  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x18010dd06  lea     rdx, dword_180172B5C
0x18010dd0d  mov     rcx, rax
0x18010dd10  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18010dd15  mov     rcx, [rbp+7E8h]; this
0x18010dd1c  test    ebx, ebx
0x18010dd1e  jns     short loc_18010DD43
0x18010dd20  mov     r9d, ebx; char *
0x18010dd23  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010dd2a  mov     edx, 81h; void *
0x18010dd2f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18010dd34  mov     rax, [rdi]
0x18010dd37  mov     rcx, rdi
0x18010dd3a  mov     rax, [rax+20h]
0x18010dd3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010dd43  mov     ebx, [rdi+40h]
0x18010dd46  test    ebx, ebx
0x18010dd48  jns     short loc_18010DD51
0x18010dd4a  mov     edx, 8Ah
0x18010dd4f  jmp     short loc_18010DD62
0x18010dd51  mov     rcx, [rsp+8E0h+var_878]
0x18010dd56  mov     ebx, [rcx+4]
0x18010dd59  test    ebx, ebx
0x18010dd5b  jns     short loc_18010DD7A
0x18010dd5d  mov     edx, 8Ch; void *
0x18010dd62  mov     r9d, ebx; char *
0x18010dd65  mov     rcx, [rbp+7E8h]; this
0x18010dd6c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x18010dd73  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010dd78  jmp     short loc_18010DD98
0x18010dd7a  mov     rdx, [rbp+7E0h+arg_20]
0x18010dd81  call    ??$CastTo@UXvmPreStart@@@XvmMessage@@QEAAJPEAPEAUXvmPreStart@@@Z; XvmMessage::CastTo<XvmPreStart>(XvmPreStart * *)
0x18010dd86  mov     ebx, eax
0x18010dd88  test    eax, eax
0x18010dd8a  jns     short loc_18010DD96
0x18010dd8c  mov     r9d, eax
0x18010dd8f  mov     edx, 8Dh
0x18010dd94  jmp     short loc_18010DD65
0x18010dd96  xor     ebx, ebx
0x18010dd98  mov     rcx, [rbp+7E0h+arg_18]
0x18010dd9f  mov     rax, [rsp+8E0h+var_878]
0x18010dda4  mov     [rcx], rax
0x18010dda7  mov     eax, ebx
0x18010dda9  lea     r11, [rsp+8E0h+var_10]
0x18010ddb1  mov     rbx, [r11+28h]
0x18010ddb5  mov     rsi, [r11+30h]
0x18010ddb9  movaps  xmm6, xmmword ptr [r11-10h]
0x18010ddbe  mov     rsp, r11
0x18010ddc1  pop     r14
0x18010ddc3  pop     rdi
0x18010ddc4  pop     rbp
0x18010ddc5  retn
```
