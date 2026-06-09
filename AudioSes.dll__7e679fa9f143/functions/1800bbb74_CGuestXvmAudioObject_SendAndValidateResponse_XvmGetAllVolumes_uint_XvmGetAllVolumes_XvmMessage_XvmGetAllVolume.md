# CGuestXvmAudioObject::SendAndValidateResponse<XvmGetAllVolumes>(uint,XvmGetAllVolumes,XvmMessage * *,XvmGetAllVolumes * *)

- ea: `0x1800bbb74`
- end: `0x1800bbf2d`
- name: `??$SendAndValidateResponse@UXvmGetAllVolumes@@@CGuestXvmAudioObject@@QEAAJIUXvmGetAllVolumes@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `953`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800bfb60`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a2778`
- `0x1800bbb74`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bbbb6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bbd14`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bbbb6`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800bbd14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bbbea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bbbea`

## string_xrefs

- `0x1800bbbcd`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bbc0c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bbe8a`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800bbed3`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmGetAllVolumes>(__int64 a1, unsigned int a2, _OWORD *a3, ...)
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
  int All; // eax
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
  _OWORD v34[11]; // [rsp+C8h] [rbp-40h] BYREF
  _OWORD v35[118]; // [rsp+178h] [rbp+70h]
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
    v34[3] = a3[3];
    v34[4] = a3[4];
    v34[5] = a3[5];
    v34[6] = a3[6];
    v34[7] = a3[7];
    v34[8] = a3[8];
    v34[9] = a3[9];
    v34[10] = a3[10];
    v35[0] = a3[11];
    *(_OWORD *)((char *)v35 + 12) = *(_OWORD *)((char *)a3 + 188);
    v32 = 20;
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
            (unsigned int)&unk_1801683CC,
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
          (unsigned int)&unk_180168445,
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
        All = XvmMessage::CastTo<XvmGetAllVolumes>(v21, v40, v12);
        v9 = All;
        if ( All >= 0 )
        {
          v9 = 0;
          goto LABEL_24;
        }
        v17 = (unsigned int)All;
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
0x1800bbb74  mov     rax, rsp
0x1800bbb77  mov     [rax+10h], rbx
0x1800bbb7b  mov     [rax+18h], rsi
0x1800bbb7f  mov     [rax+20h], r9
0x1800bbb83  push    rbp
0x1800bbb84  push    rdi
0x1800bbb85  push    r14
0x1800bbb87  lea     rbp, [rax-7E8h]
0x1800bbb8e  sub     rsp, 8D0h
0x1800bbb95  movaps  xmmword ptr [rax-28h], xmm6
0x1800bbb99  mov     rsi, r8
0x1800bbb9c  mov     r14d, edx
0x1800bbb9f  mov     rbx, rcx
0x1800bbba2  mov     qword ptr [rbp+7E0h+PerformanceCount], 0
0x1800bbbaa  mov     qword ptr [rbp+7E0h+var_858], 0
0x1800bbbb2  lea     rcx, [rbp+7E0h+PerformanceCount]; lpPerformanceCount
0x1800bbbb6  call    cs:__imp_QueryPerformanceCounter
0x1800bbbbc  mov     edi, [rbx+40h]
0x1800bbbbf  test    edi, edi
0x1800bbbc1  jns     short loc_1800BBBE5
0x1800bbbc3  mov     rcx, [rbp+7E8h]; this
0x1800bbbca  mov     r9d, edi; char *
0x1800bbbcd  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bbbd4  mov     edx, 4Fh ; 'O'; void *
0x1800bbbd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbbde  mov     eax, edi
0x1800bbbe0  jmp     loc_1800BBF10
0x1800bbbe5  mov     ecx, 810h; cb
0x1800bbbea  call    cs:__imp_CoTaskMemAlloc
0x1800bbbf0  mov     rdi, rax
0x1800bbbf3  mov     [rsp+8E0h+var_878], rax
0x1800bbbf8  test    rax, rax
0x1800bbbfb  jnz     short loc_1800BBC20
0x1800bbbfd  mov     rcx, [rbp+7E8h]; this
0x1800bbc04  mov     ebx, 8007000Eh
0x1800bbc09  mov     r9d, ebx; char *
0x1800bbc0c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bbc13  lea     edx, [rax+52h]; void *
0x1800bbc16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbc1b  jmp     loc_1800BBF0E
0x1800bbc20  mov     [rbp+7E0h+Src], 0
0x1800bbc28  mov     [rbp+7E0h+var_824], 0
0x1800bbc2f  xor     edx, edx; Val
0x1800bbc31  mov     r8d, 800h; Size
0x1800bbc37  lea     rcx, [rbp+7E0h+var_820]; void *
0x1800bbc3b  call    memset_0
0x1800bbc40  movups  xmm0, xmmword ptr [rsi]
0x1800bbc43  movups  [rbp+7E0h+var_820], xmm0
0x1800bbc47  movups  xmm1, xmmword ptr [rsi+10h]
0x1800bbc4b  movups  [rbp+7E0h+var_810], xmm1
0x1800bbc4f  movups  xmm0, xmmword ptr [rsi+20h]
0x1800bbc53  movups  [rbp+7E0h+var_800], xmm0
0x1800bbc57  movups  xmm1, xmmword ptr [rsi+30h]
0x1800bbc5b  movups  [rbp+7E0h+var_7F0], xmm1
0x1800bbc5f  movups  xmm0, xmmword ptr [rsi+40h]
0x1800bbc63  movups  [rbp+7E0h+var_7E0], xmm0
0x1800bbc67  movups  xmm1, xmmword ptr [rsi+50h]
0x1800bbc6b  movups  [rbp+7E0h+var_7D0], xmm1
0x1800bbc6f  movups  xmm0, xmmword ptr [rsi+60h]
0x1800bbc73  movups  [rbp+7E0h+var_7C0], xmm0
0x1800bbc77  movups  xmm1, xmmword ptr [rsi+70h]
0x1800bbc7b  movups  [rbp+7E0h+var_7B0], xmm1
0x1800bbc7f  movups  xmm0, xmmword ptr [rsi+80h]
0x1800bbc86  movups  [rbp+7E0h+var_7A0], xmm0
0x1800bbc8a  movups  xmm1, xmmword ptr [rsi+90h]
0x1800bbc91  movups  [rbp+7E0h+var_790], xmm1
0x1800bbc95  movups  xmm0, xmmword ptr [rsi+0A0h]
0x1800bbc9c  movups  [rbp+7E0h+var_780], xmm0
0x1800bbca0  movups  xmm1, xmmword ptr [rsi+0B0h]
0x1800bbca7  movups  [rbp+7E0h+var_770], xmm1
0x1800bbcab  movups  xmm0, xmmword ptr [rsi+0BCh]
0x1800bbcb2  movups  [rbp+7E0h+var_770+0Ch], xmm0
0x1800bbcb6  mov     [rbp+7E0h+var_828], 14h
0x1800bbcbd  mov     rcx, rdi; void *
0x1800bbcc0  lea     rdx, [rbp+7E0h+Src]; Src
0x1800bbcc4  mov     r8d, 810h; Size
0x1800bbcca  call    memcpy_0
0x1800bbccf  mov     rax, [rsp+8E0h+var_878]
0x1800bbcd4  mov     [rax+0Ch], r14d
0x1800bbcd8  lea     rax, [rbp+7E0h+arg_18]
0x1800bbcdf  mov     [rbp+7E0h+var_848], rax
0x1800bbce3  lea     rax, [rsp+8E0h+var_878]
0x1800bbce8  mov     [rbp+7E0h+var_840], rax
0x1800bbcec  mov     [rbp+7E0h+var_838], 1
0x1800bbcf0  mov     rcx, [rbx+28h]
0x1800bbcf4  mov     rax, [rcx]
0x1800bbcf7  mov     r9d, 810h
0x1800bbcfd  mov     r8, [rsp+8E0h+var_878]
0x1800bbd02  mov     edx, r14d
0x1800bbd05  mov     rax, [rax+20h]
0x1800bbd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbd0e  mov     edi, eax
0x1800bbd10  lea     rcx, [rbp+7E0h+var_858]; lpPerformanceCount
0x1800bbd14  call    cs:__imp_QueryPerformanceCounter
0x1800bbd1a  xorps   xmm6, xmm6
0x1800bbd1d  cmp     qword ptr [rbx+48h], 0
0x1800bbd22  jz      short loc_1800BBD46
0x1800bbd24  mov     rcx, qword ptr [rbp+7E0h+var_858]
0x1800bbd28  sub     rcx, qword ptr [rbp+7E0h+PerformanceCount]
0x1800bbd2c  cvtsi2ss xmm6, rcx
0x1800bbd31  mulss   xmm6, cs:__real@447a0000
0x1800bbd39  xorps   xmm0, xmm0
0x1800bbd3c  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800bbd42  divss   xmm6, xmm0
0x1800bbd46  mov     rcx, [rsp+8E0h+var_878]
0x1800bbd4b  cmp     dword ptr [rcx+8], 1
0x1800bbd4f  jnz     loc_1800BBE0B
0x1800bbd55  mov     [rsp+8E0h+var_870], 0
0x1800bbd5e  lea     rdx, [rsp+8E0h+var_870]
0x1800bbd63  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800bbd68  test    eax, eax
0x1800bbd6a  js      loc_1800BBE7C
0x1800bbd70  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bbd75  mov     r8, rax
0x1800bbd78  mov     ecx, [rax]
0x1800bbd7a  cmp     ecx, 4
0x1800bbd7d  jbe     loc_1800BBE7C
0x1800bbd83  mov     [rbp+7E0h+arg_0], edi
0x1800bbd89  movss   [rsp+8E0h+var_868], xmm6
0x1800bbd8f  mov     [rbp+7E0h+var_860], rbx
0x1800bbd93  mov     rdx, [rsp+8E0h+var_870]
0x1800bbd98  mov     ecx, [rdx+10h]
0x1800bbd9b  mov     [rsp+8E0h+var_864], ecx
0x1800bbd9f  mov     ecx, [rdx+4]
0x1800bbda2  mov     [rsp+8E0h+var_880], ecx
0x1800bbda6  mov     eax, [rdx+8]
0x1800bbda9  mov     [rsp+8E0h+var_880+4], eax
0x1800bbdad  mov     eax, [rdx]
0x1800bbdaf  mov     dword ptr [rsp+8E0h+var_870], eax
0x1800bbdb3  lea     rax, [rbp+7E0h+arg_0]
0x1800bbdba  mov     [rsp+8E0h+var_890], rax
0x1800bbdbf  lea     rax, [rsp+8E0h+var_868]
0x1800bbdc4  mov     [rsp+8E0h+var_898], rax
0x1800bbdc9  lea     rax, [rbp+7E0h+var_860]
0x1800bbdcd  mov     [rsp+8E0h+var_8A0], rax
0x1800bbdd2  lea     rax, [rsp+8E0h+var_864]
0x1800bbdd7  mov     [rsp+8E0h+var_8A8], rax
0x1800bbddc  lea     rax, [rsp+8E0h+var_880]
0x1800bbde1  mov     [rsp+8E0h+var_8B0], rax
0x1800bbde6  lea     rax, [rsp+8E0h+var_880+4]
0x1800bbdeb  mov     [rsp+8E0h+var_8B8], rax
0x1800bbdf0  lea     rax, [rsp+8E0h+var_870]
0x1800bbdf5  mov     qword ptr [rsp+8E0h+var_8C0], rax
0x1800bbdfa  lea     rdx, unk_1801683CC
0x1800bbe01  mov     rcx, r8
0x1800bbe04  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bbe09  jmp     short loc_1800BBE7C
0x1800bbe0b  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800bbe10  mov     ecx, [rax]
0x1800bbe12  cmp     ecx, 4
0x1800bbe15  jbe     short loc_1800BBE7C
0x1800bbe17  mov     [rbp+7E0h+arg_0], edi
0x1800bbe1d  movss   dword ptr [rsp+8E0h+var_870], xmm6
0x1800bbe23  mov     [rbp+7E0h+var_860], rbx
0x1800bbe27  mov     rcx, [rsp+8E0h+var_878]
0x1800bbe2c  mov     edx, [rcx+8]
0x1800bbe2f  mov     [rsp+8E0h+var_880+4], edx
0x1800bbe33  mov     ecx, [rbx+30h]
0x1800bbe36  mov     [rsp+8E0h+var_880], ecx
0x1800bbe3a  lea     rcx, [rbp+7E0h+arg_0]
0x1800bbe41  mov     [rsp+8E0h+var_8A0], rcx
0x1800bbe46  lea     rcx, [rsp+8E0h+var_870]
0x1800bbe4b  mov     [rsp+8E0h+var_8A8], rcx
0x1800bbe50  lea     rcx, [rbp+7E0h+var_860]
0x1800bbe54  mov     [rsp+8E0h+var_8B0], rcx
0x1800bbe59  lea     rcx, [rsp+8E0h+var_880+4]
0x1800bbe5e  mov     [rsp+8E0h+var_8B8], rcx
0x1800bbe63  lea     rcx, [rsp+8E0h+var_880]
0x1800bbe68  mov     qword ptr [rsp+8E0h+var_8C0], rcx; int
0x1800bbe6d  lea     rdx, unk_180168445
0x1800bbe74  mov     rcx, rax
0x1800bbe77  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800bbe7c  mov     rcx, [rbp+7E8h]; this
0x1800bbe83  test    edi, edi
0x1800bbe85  jns     short loc_1800BBEAA
0x1800bbe87  mov     r9d, edi; char *
0x1800bbe8a  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bbe91  mov     edx, 81h; void *
0x1800bbe96  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800bbe9b  mov     rax, [rbx]
0x1800bbe9e  mov     rcx, rbx
0x1800bbea1  mov     rax, [rax+20h]
0x1800bbea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbeaa  mov     ebx, [rbx+40h]
0x1800bbead  test    ebx, ebx
0x1800bbeaf  jns     short loc_1800BBEB8
0x1800bbeb1  mov     edx, 8Ah
0x1800bbeb6  jmp     short loc_1800BBEC9
0x1800bbeb8  mov     rcx, [rsp+8E0h+var_878]
0x1800bbebd  mov     ebx, [rcx+4]
0x1800bbec0  test    ebx, ebx
0x1800bbec2  jns     short loc_1800BBEE1
0x1800bbec4  mov     edx, 8Ch; void *
0x1800bbec9  mov     r9d, ebx; char *
0x1800bbecc  mov     rcx, [rbp+7E8h]; this
0x1800bbed3  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800bbeda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbedf  jmp     short loc_1800BBEFF
0x1800bbee1  mov     rdx, [rbp+7E0h+arg_20]
0x1800bbee8  call    ??$CastTo@UXvmGetAllVolumes@@@XvmMessage@@QEAAJPEAPEAUXvmGetAllVolumes@@@Z; XvmMessage::CastTo<XvmGetAllVolumes>(XvmGetAllVolumes * *)
0x1800bbeed  mov     ebx, eax
0x1800bbeef  test    eax, eax
0x1800bbef1  jns     short loc_1800BBEFD
0x1800bbef3  mov     r9d, eax
0x1800bbef6  mov     edx, 8Dh
0x1800bbefb  jmp     short loc_1800BBECC
0x1800bbefd  xor     ebx, ebx
0x1800bbeff  mov     rcx, [rbp+7E0h+arg_18]
0x1800bbf06  mov     rax, [rsp+8E0h+var_878]
0x1800bbf0b  mov     [rcx], rax
0x1800bbf0e  mov     eax, ebx
0x1800bbf10  lea     r11, [rsp+8E0h+var_10]
0x1800bbf18  mov     rbx, [r11+28h]
0x1800bbf1c  mov     rsi, [r11+30h]
0x1800bbf20  movaps  xmm6, xmmword ptr [r11-10h]
0x1800bbf25  mov     rsp, r11
0x1800bbf28  pop     r14
0x1800bbf2a  pop     rdi
0x1800bbf2b  pop     rbp
0x1800bbf2c  retn
```
