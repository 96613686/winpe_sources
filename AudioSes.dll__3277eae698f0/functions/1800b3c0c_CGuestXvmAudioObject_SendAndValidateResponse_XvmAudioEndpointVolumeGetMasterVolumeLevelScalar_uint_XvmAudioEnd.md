# CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetMasterVolumeLevelScalar>(uint,XvmAudioEndpointVolumeGetMasterVolumeLevelScalar,XvmMessage * *,XvmAudioEndpointVolumeGetMasterVolumeLevelScalar * *)

- ea: `0x1800b3c0c`
- end: `0x1800b3f47`
- name: `??$SendAndValidateResponse@UXvmAudioEndpointVolumeGetMasterVolumeLevelScalar@@@CGuestXvmAudioObject@@QEAAJIUXvmAudioEndpointVolumeGetMasterVolumeLevelScalar@@PEAPEAUXvmMessage@@PEAPEAU1@@Z`
- size: `827`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b6f00`

## callees

- `0x1800029bc`
- `0x180002b6c`
- `0x180010a90`
- `0x18007731c`
- `0x180079754`
- `0x180088ce8`
- `0x18008ac99`
- `0x180095600`
- `0x1800a5d68`
- `0x1800b3c0c`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b3c4a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b3d37`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b3c4a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800b3d37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b3c7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800b3c7e`

## string_xrefs

- `0x1800b3c61`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b3ca0`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b3ea9`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`
- `0x1800b3ef2`: `avcore\audiocore\CrossVmCommon\CrossVmGuest.h`

## pseudocode

```c
__int64 CGuestXvmAudioObject::SendAndValidateResponse<XvmAudioEndpointVolumeGetMasterVolumeLevelScalar>(
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
  int MasterVolumeLevel; // eax
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
    v32 = 85;
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
            (unsigned int)word_18016704A,
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
          (unsigned int)&byte_180166F37,
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
        MasterVolumeLevel = XvmMessage::CastTo<XvmAudioEndpointVolumeGetMasterVolumeLevelScalar>(v20, v39, v11);
        v8 = MasterVolumeLevel;
        if ( MasterVolumeLevel >= 0 )
        {
          v8 = 0;
          goto LABEL_24;
        }
        v16 = (unsigned int)MasterVolumeLevel;
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
0x1800b3c0c  mov     rax, rsp
0x1800b3c0f  mov     [rax+10h], rbx
0x1800b3c13  mov     [rax+20h], r9
0x1800b3c17  push    rbp
0x1800b3c18  push    rsi
0x1800b3c19  push    rdi
0x1800b3c1a  lea     rbp, [rax-7F8h]
0x1800b3c21  sub     rsp, 8E0h
0x1800b3c28  movaps  xmmword ptr [rax-28h], xmm6
0x1800b3c2c  mov     esi, edx
0x1800b3c2e  mov     rbx, rcx
0x1800b3c31  mov     [rsp+8F0h+var_878], r8d
0x1800b3c36  mov     qword ptr [rbp+7F0h+PerformanceCount], 0
0x1800b3c3e  mov     qword ptr [rbp+7F0h+var_860], 0
0x1800b3c46  lea     rcx, [rbp+7F0h+PerformanceCount]; lpPerformanceCount
0x1800b3c4a  call    cs:__imp_QueryPerformanceCounter
0x1800b3c50  mov     edi, [rbx+40h]
0x1800b3c53  test    edi, edi
0x1800b3c55  jns     short loc_1800B3C79
0x1800b3c57  mov     rcx, [rbp+7F8h]; this
0x1800b3c5e  mov     r9d, edi; char *
0x1800b3c61  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b3c68  mov     edx, 4Fh ; 'O'; void *
0x1800b3c6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3c72  mov     eax, edi
0x1800b3c74  jmp     loc_1800B3F2F
0x1800b3c79  mov     ecx, 810h; cb
0x1800b3c7e  call    cs:__imp_CoTaskMemAlloc
0x1800b3c84  mov     rdi, rax
0x1800b3c87  mov     [rsp+8F0h+var_888], rax
0x1800b3c8c  test    rax, rax
0x1800b3c8f  jnz     short loc_1800B3CB4
0x1800b3c91  mov     rcx, [rbp+7F8h]; this
0x1800b3c98  mov     ebx, 8007000Eh
0x1800b3c9d  mov     r9d, ebx; char *
0x1800b3ca0  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b3ca7  lea     edx, [rax+52h]; void *
0x1800b3caa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3caf  jmp     loc_1800B3F2D
0x1800b3cb4  mov     [rbp+7F0h+Src], 0
0x1800b3cbc  mov     [rbp+7F0h+var_824], 0
0x1800b3cc3  xor     edx, edx; Val
0x1800b3cc5  mov     r8d, 800h; Size
0x1800b3ccb  lea     rcx, [rbp+7F0h+var_820]; void *
0x1800b3ccf  call    memset_0
0x1800b3cd4  mov     eax, [rsp+8F0h+var_878]
0x1800b3cd8  mov     [rbp+7F0h+var_820], eax
0x1800b3cdb  mov     [rbp+7F0h+var_828], 55h ; 'U'
0x1800b3ce2  mov     rcx, rdi; void *
0x1800b3ce5  lea     rdx, [rbp+7F0h+Src]; Src
0x1800b3ce9  mov     r8d, 810h; Size
0x1800b3cef  call    memcpy_0
0x1800b3cf4  mov     rax, [rsp+8F0h+var_888]
0x1800b3cf9  mov     [rax+0Ch], esi
0x1800b3cfc  lea     rax, [rbp+7F0h+arg_18]
0x1800b3d03  mov     [rbp+7F0h+var_850], rax
0x1800b3d07  lea     rax, [rsp+8F0h+var_888]
0x1800b3d0c  mov     [rbp+7F0h+var_848], rax
0x1800b3d10  mov     [rbp+7F0h+var_840], 1
0x1800b3d14  mov     rcx, [rbx+28h]
0x1800b3d18  mov     rax, [rcx]
0x1800b3d1b  mov     r9d, 810h
0x1800b3d21  mov     r8, [rsp+8F0h+var_888]
0x1800b3d26  mov     edx, esi
0x1800b3d28  mov     rax, [rax+20h]
0x1800b3d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3d31  mov     edi, eax
0x1800b3d33  lea     rcx, [rbp+7F0h+var_860]; lpPerformanceCount
0x1800b3d37  call    cs:__imp_QueryPerformanceCounter
0x1800b3d3d  xorps   xmm6, xmm6
0x1800b3d40  cmp     qword ptr [rbx+48h], 0
0x1800b3d45  jz      short loc_1800B3D69
0x1800b3d47  mov     rcx, qword ptr [rbp+7F0h+var_860]
0x1800b3d4b  sub     rcx, qword ptr [rbp+7F0h+PerformanceCount]
0x1800b3d4f  cvtsi2ss xmm6, rcx
0x1800b3d54  mulss   xmm6, cs:__real@447a0000
0x1800b3d5c  xorps   xmm0, xmm0
0x1800b3d5f  cvtsi2ss xmm0, qword ptr [rbx+48h]
0x1800b3d65  divss   xmm6, xmm0
0x1800b3d69  mov     rcx, [rsp+8F0h+var_888]
0x1800b3d6e  cmp     dword ptr [rcx+8], 1
0x1800b3d72  jnz     loc_1800B3E2A
0x1800b3d78  mov     [rsp+8F0h+var_880], 0
0x1800b3d81  lea     rdx, [rsp+8F0h+var_880]
0x1800b3d86  call    ??$CastTo@UXvmActivateProxyAudioObject@@@XvmMessage@@QEAAJPEAPEAUXvmActivateProxyAudioObject@@@Z; XvmMessage::CastTo<XvmActivateProxyAudioObject>(XvmActivateProxyAudioObject * *)
0x1800b3d8b  test    eax, eax
0x1800b3d8d  js      loc_1800B3E9B
0x1800b3d93  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b3d98  mov     r8, rax
0x1800b3d9b  mov     ecx, [rax]
0x1800b3d9d  cmp     ecx, 4
0x1800b3da0  jbe     loc_1800B3E9B
0x1800b3da6  mov     [rbp+7F0h+arg_0], edi
0x1800b3dac  movss   [rbp+7F0h+var_870], xmm6
0x1800b3db1  mov     [rbp+7F0h+var_868], rbx
0x1800b3db5  mov     rdx, [rsp+8F0h+var_880]
0x1800b3dba  mov     ecx, [rdx+10h]
0x1800b3dbd  mov     [rbp+7F0h+var_86C], ecx
0x1800b3dc0  mov     ecx, [rdx+4]
0x1800b3dc3  mov     [rsp+8F0h+var_890], ecx
0x1800b3dc7  mov     eax, [rdx+8]
0x1800b3dca  mov     [rsp+8F0h+var_890+4], eax
0x1800b3dce  mov     eax, [rdx]
0x1800b3dd0  mov     dword ptr [rsp+8F0h+var_880], eax
0x1800b3dd4  lea     rax, [rbp+7F0h+arg_0]
0x1800b3ddb  mov     [rsp+8F0h+var_8A0], rax
0x1800b3de0  lea     rax, [rbp+7F0h+var_870]
0x1800b3de4  mov     [rsp+8F0h+var_8A8], rax
0x1800b3de9  lea     rax, [rbp+7F0h+var_868]
0x1800b3ded  mov     [rsp+8F0h+var_8B0], rax
0x1800b3df2  lea     rax, [rbp+7F0h+var_86C]
0x1800b3df6  mov     [rsp+8F0h+var_8B8], rax
0x1800b3dfb  lea     rax, [rsp+8F0h+var_890]
0x1800b3e00  mov     [rsp+8F0h+var_8C0], rax
0x1800b3e05  lea     rax, [rsp+8F0h+var_890+4]
0x1800b3e0a  mov     [rsp+8F0h+var_8C8], rax
0x1800b3e0f  lea     rax, [rsp+8F0h+var_880]
0x1800b3e14  mov     qword ptr [rsp+8F0h+var_8D0], rax
0x1800b3e19  lea     rdx, word_18016704A
0x1800b3e20  mov     rcx, r8
0x1800b3e23  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@333AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b3e28  jmp     short loc_1800B3E9B
0x1800b3e2a  call    ?Provider@GuestXvmAudioObjectTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; GuestXvmAudioObjectTelemetryProvider::Provider(void)
0x1800b3e2f  mov     ecx, [rax]
0x1800b3e31  cmp     ecx, 4
0x1800b3e34  jbe     short loc_1800B3E9B
0x1800b3e36  mov     [rbp+7F0h+arg_0], edi
0x1800b3e3c  movss   dword ptr [rsp+8F0h+var_880], xmm6
0x1800b3e42  mov     [rbp+7F0h+var_868], rbx
0x1800b3e46  mov     rcx, [rsp+8F0h+var_888]
0x1800b3e4b  mov     edx, [rcx+8]
0x1800b3e4e  mov     [rsp+8F0h+var_890+4], edx
0x1800b3e52  mov     ecx, [rbx+30h]
0x1800b3e55  mov     [rsp+8F0h+var_890], ecx
0x1800b3e59  lea     rcx, [rbp+7F0h+arg_0]
0x1800b3e60  mov     [rsp+8F0h+var_8B0], rcx
0x1800b3e65  lea     rcx, [rsp+8F0h+var_880]
0x1800b3e6a  mov     [rsp+8F0h+var_8B8], rcx
0x1800b3e6f  lea     rcx, [rbp+7F0h+var_868]
0x1800b3e73  mov     [rsp+8F0h+var_8C0], rcx
0x1800b3e78  lea     rcx, [rsp+8F0h+var_890+4]
0x1800b3e7d  mov     [rsp+8F0h+var_8C8], rcx
0x1800b3e82  lea     rcx, [rsp+8F0h+var_890]
0x1800b3e87  mov     qword ptr [rsp+8F0h+var_8D0], rcx; int
0x1800b3e8c  lea     rdx, byte_180166F37
0x1800b3e93  mov     rcx, rax
0x1800b3e96  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByVal@$07@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByVal@$07@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b3e9b  mov     rcx, [rbp+7F8h]; this
0x1800b3ea2  test    edi, edi
0x1800b3ea4  jns     short loc_1800B3EC9
0x1800b3ea6  mov     r9d, edi; char *
0x1800b3ea9  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b3eb0  mov     edx, 81h; void *
0x1800b3eb5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b3eba  mov     rax, [rbx]
0x1800b3ebd  mov     rcx, rbx
0x1800b3ec0  mov     rax, [rax+20h]
0x1800b3ec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3ec9  mov     ebx, [rbx+40h]
0x1800b3ecc  test    ebx, ebx
0x1800b3ece  jns     short loc_1800B3ED7
0x1800b3ed0  mov     edx, 8Ah
0x1800b3ed5  jmp     short loc_1800B3EE8
0x1800b3ed7  mov     rcx, [rsp+8F0h+var_888]
0x1800b3edc  mov     ebx, [rcx+4]
0x1800b3edf  test    ebx, ebx
0x1800b3ee1  jns     short loc_1800B3F00
0x1800b3ee3  mov     edx, 8Ch; void *
0x1800b3ee8  mov     r9d, ebx; char *
0x1800b3eeb  mov     rcx, [rbp+7F8h]; this
0x1800b3ef2  lea     r8, aAvcoreAudiocor_13; "avcore\\audiocore\\CrossVmCommon\\Cross"...
0x1800b3ef9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3efe  jmp     short loc_1800B3F1E
0x1800b3f00  mov     rdx, [rbp+7F0h+arg_20]
0x1800b3f07  call    ??$CastTo@UXvmAudioEndpointVolumeGetMasterVolumeLevelScalar@@@XvmMessage@@QEAAJPEAPEAUXvmAudioEndpointVolumeGetMasterVolumeLevelScalar@@@Z; XvmMessage::CastTo<XvmAudioEndpointVolumeGetMasterVolumeLevelScalar>(XvmAudioEndpointVolumeGetMasterVolumeLevelScalar * *)
0x1800b3f0c  mov     ebx, eax
0x1800b3f0e  test    eax, eax
0x1800b3f10  jns     short loc_1800B3F1C
0x1800b3f12  mov     r9d, eax
0x1800b3f15  mov     edx, 8Dh
0x1800b3f1a  jmp     short loc_1800B3EEB
0x1800b3f1c  xor     ebx, ebx
0x1800b3f1e  mov     rcx, [rbp+7F0h+arg_18]
0x1800b3f25  mov     rax, [rsp+8F0h+var_888]
0x1800b3f2a  mov     [rcx], rax
0x1800b3f2d  mov     eax, ebx
0x1800b3f2f  lea     r11, [rsp+8F0h+var_10]
0x1800b3f37  mov     rbx, [r11+28h]
0x1800b3f3b  movaps  xmm6, xmmword ptr [r11-10h]
0x1800b3f40  mov     rsp, r11
0x1800b3f43  pop     rdi
0x1800b3f44  pop     rsi
0x1800b3f45  pop     rbp
0x1800b3f46  retn
```
