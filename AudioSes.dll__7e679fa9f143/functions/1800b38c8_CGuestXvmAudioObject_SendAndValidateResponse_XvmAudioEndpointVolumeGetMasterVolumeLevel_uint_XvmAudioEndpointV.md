# CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetMasterVolumeLevel>(uint,XvmAudioEndpointVolumeGetMasterVolumeLevel,XvmMessage * *,XvmAudioEndpointVolumeGetMasterVolumeLevel * *)

- ea: `0x1800b38c8`
- end: `0x1800b3c03`
- name: `??$SendAndValidateResponse@UXvmAudioEndpointVolumeGetMasterVolumeLevel@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeGetMasterVolumeLevel@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `827`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b6e00`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a5d20`
- `0x1800b38c8`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b3906`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b39f3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b3906`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b39f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b393a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b393a`

## string_xrefs

- `0x1800b391d`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b395c`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b3b65`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b3bae`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetMasterVolumeLevel>(
        __int64 a1,
        unsigned int a2,
        int a3,
        ...)
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
  int MasterVolume; // eax
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
    v32 = 84;
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
            (unsigned int)&unk_180167076,
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
          (unsigned int)&unk_1801670EF,
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
        MasterVolume = XvmMessage::CastTo<XvmAudioEndpointVolumeGetMasterVolumeLevel>(v20, v39, v11);
        v8 = MasterVolume;
        if ( MasterVolume >= 0 )
        {
          v8 = 0;
          goto LABEL_24;
        }
        v16 = (unsigned int)MasterVolume;
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
0x1800b38c8  mov     rax, rsp
0x1800b38cb  mov     [rax+10h], rbx
0x1800b38cf  mov     [rax+20h], r9
0x1800b38d3  push    rbp
0x1800b38d4  push    rsi
0x1800b38d5  push    rdi
0x1800b38d6  lea     rbp, [rax-7F8h]
0x1800b38dd  sub     rsp, 8E0h
0x1800b38e4  movaps  xmmword ptr [rax-28h], xmm6
0x1800b38e8  mov     esi, edx
0x1800b38ea  mov     rbx, rcx
0x1800b38ed  mov     [rsp+8F0h+var_878], r8d
0x1800b38f2  mov     qword ptr [rbp+7F0h+PerformanceCount], 0
0x1800b38fa  mov     qword ptr [rbp+7F0h+var_860], 0
0x1800b3902  lea     rcx, [rbp+7F0h+PerformanceCount]; lpPerformanceCount
0x1800b3906  call    cs:__imp_QueryPerformanceCounter
0x1800b390c  mov     edi, [rbx+40h]
0x1800b390f  test    edi, edi
0x1800b3911  jns     short loc_1800B3935
0x1800b3913  mov     rcx, [rbp+7F8h]; this
0x1800b391a  mov     r9d, edi; char *
0x1800b391d  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b3924  mov     edx, 4Fh ; 'O'; void *
0x1800b3929  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b392e  mov     eax, edi
0x1800b3930  jmp     loc_1800B3BEB
0x1800b3935  mov     ecx, 810h; cb
0x1800b393a  call    cs:__imp_CoTaskMemAlloc
0x1800b3940  mov     rdi, rax
0x1800b3943  mov     [rsp+8F0h+var_888], rax
0x1800b3948  test    rax, rax
0x1800b394b  jnz     short loc_1800B3970
0x1800b394d  mov     rcx, [rbp+7F8h]; this
0x1800b3954  mov     ebx, 8007000Eh
0x1800b3959  mov     r9d, ebx; char *
0x1800b395c  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b3963  lea     edx, [rax+52h]; void *
0x1800b3966  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b396b  jmp     loc_1800B3BE9
0x1800b3970  mov     [rbp+7F0h+Src], 0
0x1800b3978  mov     [rbp+7F0h+var_824], 0
0x1800b397f  xor     edx, edx; Val
0x1800b3981  mov     r8d, 800h; Size
0x1800b3987  lea     rcx, [rbp+7F0h+var_820]; void *
0x1800b398b  call    memset_0
0x1800b3990  mov     eax, [rsp+8F0h+var_878]
0x1800b3994  mov     [rbp+7F0h+var_820], eax
0x1800b3997  mov     [rbp+7F0h+var_828], 54h ; 'T'
0x1800b399e  mov     rcx, rdi; void *
0x1800b39a1  lea     rdx, [rbp+7F0h+Src]; Src
0x1800b39a5  mov     r8d, 810h; Size
0x1800b39ab  call    memcpy_0
0x1800b39b0  mov     rax, [rsp+8F0h+var_888]
0x1800b39b5  mov     [rax+0Ch], esi
0x1800b39b8  lea     rax, [rbp+7F0h+arg_18]
0x1800b39bf  mov     [rbp+7F0h+var_850], rax
0x1800b39c3  lea     rax, [rsp+8F0h+var_888]
0x1800b39c8  mov     [rbp+7F0h+var_848], rax
0x1800b39cc  mov     [rbp+7F0h+var_840], 1
0x1800b39d0  mov     rcx, [rbx+28h]
0x1800b39d4  mov     rax, [rcx]
0x1800b39d7  mov     r9d, 810h
0x1800b39dd  mov     r8, [rsp+8F0h+var_888]
0x1800b39e2  mov     edx, esi
0x1800b39e4  mov     rax, [rax+20h]
0x1800b39e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b39ed  mov     edi, eax
0x1800b39ef  lea     rcx, [rbp+7F0h+var_860]; lpPerformanceCount
0x1800b39f3  call    cs:__imp_QueryPerformanceCounter
0x1800b39f9  xorps   xmm6, xmm6
0x1800b39fc  cmp     qword ptr [rbx+48h], 0
0x1800b3a01  jz      short loc_1800B3A25
0x1800b3a03  mov     rcx, qword ptr [rbp+7F0h+var_860]
0x1800b3a07  sub     rcx, qword ptr [rbp+7F0h+PerformanceCount]
0x1800b3a0b  cvtsi2ss xmm6, rcx
0x1800b3a10  mulss   xmm6, cs:__real@447a0000
0x1800b3a18  xorps   xmm0, xmm0
0x1800b3a1b  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800b3a21  divss   xmm6, xmm0
0x1800b3a25  mov     rcx, [rsp+8F0h+var_888]
0x1800b3a2a  cmp     dword ptr [rcx+8], 1
0x1800b3a2e  jnz     loc_1800B3AE6
0x1800b3a34  mov     [rsp+8F0h+var_880], 0
0x1800b3a3d  lea     rdx, [rsp+8F0h+var_880]
0x1800b3a42  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b3a47  test    eax, eax
0x1800b3a49  js      loc_1800B3B57
0x1800b3a4f  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b3a54  mov     r8, rax
0x1800b3a57  mov     ecx, [rax]
0x1800b3a59  cmp     ecx, 4
0x1800b3a5c  jbe     loc_1800B3B57
0x1800b3a62  mov     [rbp+7F0h+arg_0], edi
0x1800b3a68  movss   [rbp+7F0h+var_870], xmm6
0x1800b3a6d  mov     [rbp+7F0h+var_868], rbx
0x1800b3a71  mov     rdx, [rsp+8F0h+var_880]
0x1800b3a76  mov     ecx, [rdx+10h]
0x1800b3a79  mov     [rbp+7F0h+var_86C], ecx
0x1800b3a7c  mov     ecx, [rdx+4]
0x1800b3a7f  mov     [rsp+8F0h+var_890], ecx
0x1800b3a83  mov     eax, [rdx+8]
0x1800b3a86  mov     [rsp+8F0h+var_890+4], eax
0x1800b3a8a  mov     eax, [rdx]
0x1800b3a8c  mov     dword ptr [rsp+8F0h+var_880], eax
0x1800b3a90  lea     rax, [rbp+7F0h+arg_0]
0x1800b3a97  mov     [rsp+8F0h+var_8A0], rax
0x1800b3a9c  lea     rax, [rbp+7F0h+var_870]
0x1800b3aa0  mov     [rsp+8F0h+var_8A8], rax
0x1800b3aa5  lea     rax, [rbp+7F0h+var_868]
0x1800b3aa9  mov     [rsp+8F0h+var_8B0], rax
0x1800b3aae  lea     rax, [rbp+7F0h+var_86C]
0x1800b3ab2  mov     [rsp+8F0h+var_8B8], rax
0x1800b3ab7  lea     rax, [rsp+8F0h+var_890]
0x1800b3abc  mov     [rsp+8F0h+var_8C0], rax
0x1800b3ac1  lea     rax, [rsp+8F0h+var_890+4]
0x1800b3ac6  mov     [rsp+8F0h+var_8C8], rax
0x1800b3acb  lea     rax, [rsp+8F0h+var_880]
0x1800b3ad0  mov     qword ptr [rsp+8F0h+var_8D0], rax
0x1800b3ad5  lea     rdx, unk_180167076
0x1800b3adc  mov     rcx, r8
0x1800b3adf  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b3ae4  jmp     short loc_1800B3B57
0x1800b3ae6  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b3aeb  mov     ecx, [rax]
0x1800b3aed  cmp     ecx, 4
0x1800b3af0  jbe     short loc_1800B3B57
0x1800b3af2  mov     [rbp+7F0h+arg_0], edi
0x1800b3af8  movss   dword ptr [rsp+8F0h+var_880], xmm6
0x1800b3afe  mov     [rbp+7F0h+var_868], rbx
0x1800b3b02  mov     rcx, [rsp+8F0h+var_888]
0x1800b3b07  mov     edx, [rcx+8]
0x1800b3b0a  mov     [rsp+8F0h+var_890+4], edx
0x1800b3b0e  mov     ecx, [rbx+30h]
0x1800b3b11  mov     [rsp+8F0h+var_890], ecx
0x1800b3b15  lea     rcx, [rbp+7F0h+arg_0]
0x1800b3b1c  mov     [rsp+8F0h+var_8B0], rcx
0x1800b3b21  lea     rcx, [rsp+8F0h+var_880]
0x1800b3b26  mov     [rsp+8F0h+var_8B8], rcx
0x1800b3b2b  lea     rcx, [rbp+7F0h+var_868]
0x1800b3b2f  mov     [rsp+8F0h+var_8C0], rcx
0x1800b3b34  lea     rcx, [rsp+8F0h+var_890+4]
0x1800b3b39  mov     [rsp+8F0h+var_8C8], rcx
0x1800b3b3e  lea     rcx, [rsp+8F0h+var_890]
0x1800b3b43  mov     qword ptr [rsp+8F0h+var_8D0], rcx; int
0x1800b3b48  lea     rdx, unk_1801670EF
0x1800b3b4f  mov     rcx, rax
0x1800b3b52  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b3b57  mov     rcx, [rbp+7F8h]; this
0x1800b3b5e  test    edi, edi
0x1800b3b60  jns     short loc_1800B3B85
0x1800b3b62  mov     r9d, edi; char *
0x1800b3b65  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b3b6c  mov     edx, 81h; void *
0x1800b3b71  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b3b76  mov     rax, [rbx]
0x1800b3b79  mov     rcx, rbx
0x1800b3b7c  mov     rax, [rax+20h]
0x1800b3b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3b85  mov     ebx, [rbx+40h]
0x1800b3b88  test    ebx, ebx
0x1800b3b8a  jns     short loc_1800B3B93
0x1800b3b8c  mov     edx, 8Ah
0x1800b3b91  jmp     short loc_1800B3BA4
0x1800b3b93  mov     rcx, [rsp+8F0h+var_888]
0x1800b3b98  mov     ebx, [rcx+4]
0x1800b3b9b  test    ebx, ebx
0x1800b3b9d  jns     short loc_1800B3BBC
0x1800b3b9f  mov     edx, 8Ch; void *
0x1800b3ba4  mov     r9d, ebx; char *
0x1800b3ba7  mov     rcx, [rbp+7F8h]; this
0x1800b3bae  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b3bb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3bba  jmp     short loc_1800B3BDA
0x1800b3bbc  mov     rdx, [rbp+7F0h+arg_20]
0x1800b3bc3  call    ??$CastTo@UXvmAudioEndpointVolumeGetMasterVolumeLevel@@@XvmMessage@@QEAAJPEAPEAUXvmAudioEndpointVolumeGetMasterVolumeLevel@@@Z; XvmMessage::CastTo<XvmAudioEndpointVolumeGetMasterVolumeLevel>(XvmAudioEndpointVolumeGetMasterVolumeLevel * *)
0x1800b3bc8  mov     ebx, eax
0x1800b3bca  test    eax, eax
0x1800b3bcc  jns     short loc_1800B3BD8
0x1800b3bce  mov     r9d, eax
0x1800b3bd1  mov     edx, 8Dh
0x1800b3bd6  jmp     short loc_1800B3BA7
0x1800b3bd8  xor     ebx, ebx
0x1800b3bda  mov     rcx, [rbp+7F0h+arg_18]
0x1800b3be1  mov     rax, [rsp+8F0h+var_888]
0x1800b3be6  mov     [rcx], rax
0x1800b3be9  mov     eax, ebx
0x1800b3beb  lea     r11, [rsp+8F0h+var_10]
0x1800b3bf3  mov     rbx, [r11+28h]
0x1800b3bf7  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b3bfc  mov     rsp, r11
0x1800b3bff  pop     rdi
0x1800b3c00  pop     rsi
0x1800b3c01  pop     rbp
0x1800b3c02  retn
```
