# DeriveStreamGroupParametersForStream(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,SYSTEM_AUDIO_STREAM_TYPE,__int64,_GUID,_GUID,bool,bool,tWAVEFORMATEX const *,MODE_PARAMS const *,IAudioStreamInfo *,std::unique_ptr<StreamGroupParams,std::default_delete<StreamGroupParams>> &)

- ea: `0x180078e2c`
- end: `0x18007925a`
- name: `?DeriveStreamGroupParametersForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4SYSTEM_AUDIO_STREAM_TYPE@@_JU_GUID@@4_N5PEBUtWAVEFORMATEX@@PEBUMODE_PARAMS@@PEAUIAudioStreamInfo@@AEAV?$unique_ptr@UStreamGroupParams@@U?$default_delete@UStreamGroupParams@@@std@@@std@@@Z`
- size: `1070`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180073490`
- `0x1800c0154`

## callees

- `0x180002d70`
- `0x180008a2c`
- `0x18000cba0`
- `0x18000df74`
- `0x18000e284`
- `0x18000e2a4`
- `0x18000e314`
- `0x18000e474`
- `0x18000e4d0`
- `0x18001280c`
- `0x18001b520`
- `0x18001e9a0`
- `0x18003d040`
- `0x180051d48`
- `0x18005b3cc`
- `0x180068c70`
- `0x180078e2c`
- `0x1800cddac`
- `0x1800ce774`
- `0x1800e5234`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078f87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079011`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079034`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007922b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180078f87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079011`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079034`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007922b`

## string_xrefs

- `0x180078f11`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180078f60`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180078fe2`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180079191`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeriveStreamGroupParametersForStream(
        CEndpointCharacteristics **a1,
        enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        struct _GUID *a6,
        unsigned __int8 a7,
        unsigned __int8 a8,
        struct tWAVEFORMATEX *Src,
        __int64 a10,
        _QWORD *a11,
        StreamGroupParams **a12)
{
  _DWORD *v14; // rbx
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rax
  CEndpointCharacteristics *v18; // rbx
  int EndpointId; // eax
  int v20; // ebx
  char v21; // r12
  void *v22; // rcx
  StreamGroupParams *v23; // rax
  StreamGroupParams *v24; // rbx
  StreamGroupParams *v25; // rdi
  unsigned __int16 *v26; // rbx
  LPVOID v27; // rbx
  __int64 v28; // r8
  unsigned __int8 v29; // bl
  __int64 v30; // rdx
  __int64 *v31; // rbx
  _DWORD *v32; // r15
  int v33; // r8d
  int v34; // r9d
  StreamGroupParams *v35; // rdx
  void *v36; // rcx
  int v38; // [rsp+20h] [rbp-79h]
  unsigned __int8 v39; // [rsp+40h] [rbp-59h] BYREF
  char v40[7]; // [rsp+41h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-51h] BYREF
  __int64 v42; // [rsp+50h] [rbp-49h] BYREF
  __int64 v43; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int16 *v44; // [rsp+60h] [rbp-39h] BYREF
  int v45[2]; // [rsp+68h] [rbp-31h] BYREF
  struct _GUID v46; // [rsp+70h] [rbp-29h] BYREF
  char v47; // [rsp+80h] [rbp-19h]
  __int64 v48; // [rsp+90h] [rbp-9h]
  StreamGroupParams **v49; // [rsp+98h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+3Fh]

  v48 = a4;
  LODWORD(v42) = a3;
  v49 = a12;
  v14 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
  if ( *v14 > 4u )
  {
    if ( a11 )
      v17 = (*(__int64 (__fastcall **)(_QWORD *))(*a11 + 80LL))(a11);
    else
      v17 = 0;
    v43 = v17;
    v40[0] = a8;
    v39 = a7;
    *(_QWORD *)v45 = a6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
      (_DWORD)v14,
      (unsigned int)&word_1801A365E,
      v15,
      v16,
      (__int64)v45,
      (__int64)&v39,
      (__int64)v40,
      (__int64)&v43);
  }
  v44 = 0;
  v18 = *a1;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v44,
    0);
  EndpointId = CEndpointCharacteristics::GetEndpointId(v18, &v44);
  v20 = EndpointId;
  if ( EndpointId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BB,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)EndpointId,
      v38);
    goto LABEL_39;
  }
  pv = 0;
  *(_QWORD *)&v46.Data1 = &pv;
  *(_QWORD *)v46.Data4 = 0;
  v21 = 1;
  v47 = 1;
  v20 = CloneWaveFormat(Src, (struct tWAVEFORMATEX **)v46.Data4);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v46);
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BE,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)(unsigned int)v20,
      v38);
LABEL_10:
    v22 = pv;
    pv = 0;
    goto LABEL_11;
  }
  v23 = (StreamGroupParams *)operator new[](0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v24 = v23;
  *(_QWORD *)&v46.Data1 = v23;
  if ( v23 )
  {
    memset_0(v23, 0, 0x60u);
    v25 = StreamGroupParams::StreamGroupParams(v24);
  }
  else
  {
    v25 = 0;
  }
  v43 = (__int64)v25;
  if ( !v25 )
  {
    v20 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C1,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
      (const char *)0x8007000ELL,
      v38);
    std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v43);
    goto LABEL_10;
  }
  v26 = v44;
  v44 = 0;
  CoTaskMemFree(*(LPVOID *)v25);
  *(_QWORD *)v25 = v26;
  *((_BYTE *)v25 + 49) = a2 == eKeywordDetectorConnector;
  v27 = pv;
  pv = 0;
  CoTaskMemFree(*((LPVOID *)v25 + 2));
  *((_QWORD *)v25 + 2) = v27;
  *((_QWORD *)v25 + 3) = v48;
  *((struct _GUID *)v25 + 2) = *a6;
  *((_BYTE *)v25 + 48) = a7;
  v29 = a8;
  *((_BYTE *)v25 + 50) = a8;
  *((_DWORD *)v25 + 2) = v42;
  if ( a11 )
  {
    v46 = *a6;
    if ( EffectPack::CanProcessingModeBeParameterized(a1[1], &v46, a2) )
    {
      v30 = a11[74];
      if ( v30 )
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v42,
          v30,
          -1);
        v31 = (__int64 *)((char *)v25 + 80);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          (char *)v25 + 80,
          &v42);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v42);
        if ( !*((_QWORD *)v25 + 10) )
        {
          v20 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3D3,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\audioresourcemanager.cpp",
            (const char *)0x8007000ELL,
            v38);
          std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v43);
          v22 = pv;
          pv = 0;
LABEL_11:
          if ( v22 )
            CoTaskMemFree(v22);
          goto LABEL_39;
        }
      }
      else
      {
        v31 = (__int64 *)((char *)v25 + 80);
      }
      if ( !a10 || !*(_DWORD *)(*(_QWORD *)(a10 + 8) + 60LL) )
        v21 = 0;
      *((_BYTE *)v25 + 88) = v21;
      std::vector<CProcessingModeParameters::AudioEffectState>::operator=((char *)v25 + 56, a11 + 71);
      v32 = (_DWORD *)*((_QWORD *)AudioSrvTelemetryProvider::Instance() + 1);
      if ( *v32 > 4u )
      {
        *(_QWORD *)v45 = 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)v25 + 8) - *((_QWORD *)v25 + 7)) >> 2);
        v39 = *((_BYTE *)v25 + 88);
        v42 = *v31;
        *(_QWORD *)&v46.Data1 = (*(__int64 (__fastcall **)(_QWORD *))(*a11 + 80LL))(a11);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
          (_DWORD)v32,
          (unsigned int)&unk_1801A35E0,
          v33,
          v34,
          (__int64)&v46,
          (__int64)&v42,
          (__int64)&v39,
          (__int64)v45);
      }
      v29 = a8;
    }
  }
  v43 = 0;
  v35 = *v49;
  *v49 = v25;
  if ( v35 )
    std::default_delete<StreamGroupParams>::operator()();
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Idd(*((_QWORD *)WPP_GLOBAL_Control + 2), a7, v28, v48, a7, v29);
  }
  std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(&v43);
  v36 = pv;
  pv = 0;
  if ( v36 )
    CoTaskMemFree(v36);
  v20 = 0;
LABEL_39:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v44);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180078e2c  mov     [rsp-8+arg_10], rbx
0x180078e31  push    rbp
0x180078e32  push    rsi
0x180078e33  push    rdi
0x180078e34  push    r12
0x180078e36  push    r13
0x180078e38  push    r14
0x180078e3a  push    r15
0x180078e3c  lea     rbp, [rsp-7]
0x180078e41  sub     rsp, 0A0h
0x180078e48  mov     [rbp+37h+var_40], r9
0x180078e4c  mov     dword ptr [rbp+37h+var_80], r8d
0x180078e50  mov     r13d, edx
0x180078e53  mov     r15, rcx
0x180078e56  mov     r14, [rbp+37h+arg_28]
0x180078e5a  mov     rdi, [rbp+37h+Src]
0x180078e61  mov     rsi, [rbp+37h+arg_50]
0x180078e68  mov     rax, [rbp+37h+arg_58]
0x180078e6f  mov     [rbp+37h+var_38], rax
0x180078e73  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180078e78  mov     rbx, [rax+8]
0x180078e7c  mov     eax, [rbx]
0x180078e7e  xor     r12d, r12d
0x180078e81  cmp     eax, 4
0x180078e84  jbe     short loc_180078EE6
0x180078e86  test    rsi, rsi
0x180078e89  jz      short loc_180078E9C
0x180078e8b  mov     rax, [rsi]
0x180078e8e  mov     rcx, rsi
0x180078e91  mov     rax, [rax+50h]
0x180078e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078e9a  jmp     short loc_180078E9F
0x180078e9c  mov     rax, r12
0x180078e9f  mov     [rbp+37h+var_78], rax
0x180078ea3  mov     al, [rbp+37h+arg_38]
0x180078ea6  mov     [rbp+37h+var_8F], al
0x180078ea9  mov     dl, [rbp+37h+arg_30]
0x180078eac  mov     [rbp+37h+var_90], dl
0x180078eaf  mov     qword ptr [rbp+37h+var_68], r14
0x180078eb3  lea     rax, [rbp+37h+var_78]
0x180078eb7  mov     [rsp+0D0h+var_98], rax
0x180078ebc  lea     rax, [rbp+37h+var_8F]
0x180078ec0  mov     [rsp+0D0h+var_A0], rax
0x180078ec5  lea     rax, [rbp+37h+var_90]
0x180078ec9  mov     [rsp+0D0h+var_A8], rax
0x180078ece  lea     rax, [rbp+37h+var_68]
0x180078ed2  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x180078ed7  lea     rdx, word_1801A365E
0x180078ede  mov     rcx, rbx
0x180078ee1  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$00@@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$00@@4AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x180078ee6  mov     [rbp+37h+var_70], r12
0x180078eea  mov     rbx, [r15]
0x180078eed  xor     edx, edx
0x180078eef  lea     rcx, [rbp+37h+var_70]
0x180078ef3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180078ef8  lea     rdx, [rbp+37h+var_70]; unsigned __int16 **
0x180078efc  mov     rcx, rbx; this
0x180078eff  call    ?GetEndpointId@CEndpointCharacteristics@@QEAAJPEAPEAG@Z; CEndpointCharacteristics::GetEndpointId(ushort * *)
0x180078f04  mov     ebx, eax
0x180078f06  test    eax, eax
0x180078f08  jns     short loc_180078F27
0x180078f0a  mov     rcx, [rbp+3Fh]; this
0x180078f0e  mov     r9d, eax; char *
0x180078f11  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180078f18  mov     edx, 3BBh; void *
0x180078f1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078f22  jmp     loc_180079234
0x180078f27  mov     [rbp+37h+pv], r12
0x180078f2b  lea     rax, [rbp+37h+pv]
0x180078f2f  mov     qword ptr [rbp+37h+var_60.Data1], rax
0x180078f33  mov     qword ptr [rbp+37h+var_60.Data4], r12
0x180078f37  mov     r12b, 1
0x180078f3a  mov     [rbp+37h+var_50], r12b
0x180078f3e  lea     rdx, [rbp+37h+var_60.Data4]; struct tWAVEFORMATEX **
0x180078f42  mov     rcx, rdi; Src
0x180078f45  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x180078f4a  mov     ebx, eax
0x180078f4c  lea     rcx, [rbp+37h+var_60]
0x180078f50  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180078f55  test    ebx, ebx
0x180078f57  jns     short loc_180078F92
0x180078f59  mov     rcx, [rbp+3Fh]; this
0x180078f5d  mov     r9d, ebx; char *
0x180078f60  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180078f67  mov     edx, 3BEh; void *
0x180078f6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078f71  nop
0x180078f72  mov     rcx, [rbp+37h+pv]; pv
0x180078f76  mov     [rbp+37h+pv], 0
0x180078f7e  test    rcx, rcx
0x180078f81  jz      loc_180079234
0x180078f87  call    cs:__imp_CoTaskMemFree
0x180078f8d  jmp     loc_180079234
0x180078f92  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180078f99  mov     edi, 60h ; '`'
0x180078f9e  mov     ecx, edi; unsigned __int64
0x180078fa0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180078fa5  mov     rbx, rax
0x180078fa8  mov     qword ptr [rbp+37h+var_60.Data1], rax
0x180078fac  test    rax, rax
0x180078faf  jz      short loc_180078FCB
0x180078fb1  mov     r8d, edi; Size
0x180078fb4  xor     edx, edx; Val
0x180078fb6  mov     rcx, rax; void *
0x180078fb9  call    memset_0
0x180078fbe  mov     rcx, rbx; this
0x180078fc1  call    ??0StreamGroupParams@@QEAA@XZ; StreamGroupParams::StreamGroupParams(void)
0x180078fc6  mov     rdi, rax
0x180078fc9  jmp     short loc_180078FCD
0x180078fcb  xor     edi, edi
0x180078fcd  mov     [rbp+37h+var_78], rdi
0x180078fd1  test    rdi, rdi
0x180078fd4  jnz     short loc_180079002
0x180078fd6  mov     rcx, [rbp+3Fh]; this
0x180078fda  mov     ebx, 8007000Eh
0x180078fdf  mov     r9d, ebx; char *
0x180078fe2  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180078fe9  mov     edx, 3C1h; void *
0x180078fee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180078ff3  nop
0x180078ff4  lea     rcx, [rbp+37h+var_78]
0x180078ff8  call    ??1?$unique_ptr@UStreamGroupParams@@U?$default_delete@UStreamGroupParams@@@std@@@std@@QEAA@XZ; std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(void)
0x180078ffd  jmp     loc_180078F72
0x180079002  mov     rbx, [rbp+37h+var_70]
0x180079006  mov     [rbp+37h+var_70], 0
0x18007900e  mov     rcx, [rdi]; pv
0x180079011  call    cs:__imp_CoTaskMemFree
0x180079017  mov     [rdi], rbx
0x18007901a  cmp     r13d, 3
0x18007901e  setz    al
0x180079021  mov     [rdi+31h], al
0x180079024  mov     rbx, [rbp+37h+pv]
0x180079028  mov     [rbp+37h+pv], 0
0x180079030  mov     rcx, [rdi+10h]; pv
0x180079034  call    cs:__imp_CoTaskMemFree
0x18007903a  mov     [rdi+10h], rbx
0x18007903e  mov     rax, [rbp+37h+var_40]
0x180079042  mov     [rdi+18h], rax
0x180079046  movups  xmm0, xmmword ptr [r14]
0x18007904a  movdqu  xmmword ptr [rdi+20h], xmm0
0x18007904f  mov     al, [rbp+37h+arg_30]
0x180079052  mov     [rdi+30h], al
0x180079055  mov     bl, [rbp+37h+arg_38]
0x180079058  mov     [rdi+32h], bl
0x18007905b  mov     eax, dword ptr [rbp+37h+var_80]
0x18007905e  mov     [rdi+8], eax
0x180079061  test    rsi, rsi
0x180079064  jz      loc_1800791BA
0x18007906a  movups  xmm0, xmmword ptr [r14]
0x18007906e  movdqu  xmmword ptr [rbp+37h+var_60.Data1], xmm0
0x180079073  mov     r8d, r13d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180079076  lea     rdx, [rbp+37h+var_60]; struct _GUID
0x18007907a  mov     rcx, [r15+8]; this
0x18007907e  call    ?CanProcessingModeBeParameterized@EffectPack@@QEAA_NU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::CanProcessingModeBeParameterized(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x180079083  xor     r13d, r13d
0x180079086  test    al, al
0x180079088  jz      loc_1800791BD
0x18007908e  lea     r15, [rsi+238h]
0x180079095  mov     rdx, [r15+18h]
0x180079099  test    rdx, rdx
0x18007909c  jnz     loc_180079156
0x1800790a2  lea     rbx, [rdi+50h]
0x1800790a6  mov     rax, [rbp+37h+arg_48]
0x1800790ad  test    rax, rax
0x1800790b0  jz      short loc_1800790BC
0x1800790b2  mov     rax, [rax+8]
0x1800790b6  cmp     [rax+3Ch], r13d
0x1800790ba  jnz     short loc_1800790BF
0x1800790bc  mov     r12b, r13b
0x1800790bf  mov     [rdi+58h], r12b
0x1800790c3  mov     rdx, r15
0x1800790c6  lea     rcx, [rdi+38h]
0x1800790ca  call    ??4?$vector@UAudioEffectState@CProcessingModeParameters@@V?$allocator@UAudioEffectState@CProcessingModeParameters@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<CProcessingModeParameters::AudioEffectState>::operator=(std::vector<CProcessingModeParameters::AudioEffectState> const &)
0x1800790cf  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800790d4  mov     r15, [rax+8]
0x1800790d8  mov     eax, [r15]
0x1800790db  cmp     eax, 4
0x1800790de  jbe     short loc_180079151
0x1800790e0  mov     rax, [rdi+40h]
0x1800790e4  sub     rax, [rdi+38h]
0x1800790e8  sar     rax, 2
0x1800790ec  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x1800790f6  imul    rax, rcx
0x1800790fa  mov     qword ptr [rbp+37h+var_68], rax
0x1800790fe  mov     al, [rdi+58h]
0x180079101  mov     [rbp+37h+var_90], al
0x180079104  mov     rax, [rbx]
0x180079107  mov     [rbp+37h+var_80], rax
0x18007910b  mov     rax, [rsi]
0x18007910e  mov     rcx, rsi
0x180079111  mov     rax, [rax+50h]
0x180079115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007911a  mov     qword ptr [rbp+37h+var_60.Data1], rax
0x18007911e  lea     rax, [rbp+37h+var_68]
0x180079122  mov     [rsp+0D0h+var_98], rax
0x180079127  lea     rax, [rbp+37h+var_90]
0x18007912b  mov     [rsp+0D0h+var_A0], rax
0x180079130  lea     rax, [rbp+37h+var_80]
0x180079134  mov     [rsp+0D0h+var_A8], rax
0x180079139  lea     rax, [rbp+37h+var_60]
0x18007913d  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180079142  lea     rdx, unk_1801A35E0
0x180079149  mov     rcx, r15
0x18007914c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x180079151  mov     bl, [rbp+37h+arg_38]
0x180079154  jmp     short loc_1800791BD
0x180079156  or      r8, 0FFFFFFFFFFFFFFFFh
0x18007915a  lea     rcx, [rbp+37h+var_80]
0x18007915e  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180079163  lea     rbx, [rdi+50h]
0x180079167  lea     rdx, [rbp+37h+var_80]
0x18007916b  mov     rcx, rbx
0x18007916e  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x180079173  lea     rcx, [rbp+37h+var_80]
0x180079177  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18007917c  cmp     [rbx], r13
0x18007917f  jnz     loc_1800790A6
0x180079185  mov     rcx, [rbp+3Fh]; this
0x180079189  mov     ebx, 8007000Eh
0x18007918e  mov     r9d, ebx; char *
0x180079191  lea     r8, aAvcoreAudiocor_75; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180079198  mov     edx, 3D3h; void *
0x18007919d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800791a2  nop
0x1800791a3  lea     rcx, [rbp+37h+var_78]
0x1800791a7  call    ??1?$unique_ptr@UStreamGroupParams@@U?$default_delete@UStreamGroupParams@@@std@@@std@@QEAA@XZ; std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(void)
0x1800791ac  nop
0x1800791ad  mov     rcx, [rbp+37h+pv]
0x1800791b1  mov     [rbp+37h+pv], r13
0x1800791b5  jmp     loc_180078F7E
0x1800791ba  xor     r13d, r13d
0x1800791bd  mov     [rbp+37h+var_78], r13
0x1800791c1  mov     rax, [rbp+37h+var_38]
0x1800791c5  mov     rdx, [rax]
0x1800791c8  mov     [rax], rdi
0x1800791cb  test    rdx, rdx
0x1800791ce  jz      short loc_1800791D5
0x1800791d0  call    ??R?$default_delete@UStreamGroupParams@@@std@@QEBAXPEAUStreamGroupParams@@@Z; std::default_delete<StreamGroupParams>::operator()(StreamGroupParams *)
0x1800791d5  lea     rax, WPP_GLOBAL_Control
0x1800791dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800791e3  cmp     rcx, rax
0x1800791e6  jz      short loc_180079214
0x1800791e8  test    dword ptr [rcx+1Ch], 100h
0x1800791ef  jz      short loc_180079214
0x1800791f1  cmp     byte ptr [rcx+19h], 4
0x1800791f5  jb      short loc_180079214
0x1800791f7  movzx   eax, bl
0x1800791fa  movzx   edx, [rbp+37h+arg_30]
0x1800791fe  mov     dword ptr [rsp+0D0h+var_A8], eax
0x180079202  mov     [rsp+0D0h+var_B0], edx
0x180079206  mov     r9, [rbp+37h+var_40]
0x18007920a  mov     rcx, [rcx+10h]
0x18007920e  call    WPP_SF_Idd
0x180079213  nop
0x180079214  lea     rcx, [rbp+37h+var_78]
0x180079218  call    ??1?$unique_ptr@UStreamGroupParams@@U?$default_delete@UStreamGroupParams@@@std@@@std@@QEAA@XZ; std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(void)
0x18007921d  nop
0x18007921e  mov     rcx, [rbp+37h+pv]; pv
0x180079222  mov     [rbp+37h+pv], r13
0x180079226  test    rcx, rcx
0x180079229  jz      short loc_180079231
0x18007922b  call    cs:__imp_CoTaskMemFree
0x180079231  mov     ebx, r13d
0x180079234  lea     rcx, [rbp+37h+var_70]
0x180079238  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18007923d  mov     eax, ebx
0x18007923f  mov     rbx, [rsp+0D0h+arg_10]
0x180079247  add     rsp, 0A0h
0x18007924e  pop     r15
0x180079250  pop     r14
0x180079252  pop     r13
0x180079254  pop     r12
0x180079256  pop     rdi
0x180079257  pop     rsi
0x180079258  pop     rbp
0x180079259  retn
```
