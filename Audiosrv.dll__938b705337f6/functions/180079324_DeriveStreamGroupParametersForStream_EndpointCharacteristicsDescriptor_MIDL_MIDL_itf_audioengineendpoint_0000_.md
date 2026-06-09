# DeriveStreamGroupParametersForStream(EndpointCharacteristicsDescriptor *,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,SYSTEM_AUDIO_STREAM_TYPE,__int64,_GUID,_GUID,bool,bool,tWAVEFORMATEX const *,MODE_PARAMS const *,IAudioStreamInfo *,std::unique_ptr<StreamGroupParams,std::default_delete<StreamGroupParams>> &)

- ea: `0x180079324`
- end: `0x180079752`
- name: `?DeriveStreamGroupParametersForStream@@YAJPEAUEndpointCharacteristicsDescriptor@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@W4SYSTEM_AUDIO_STREAM_TYPE@@_JU_GUID@@4_N5PEBUtWAVEFORMATEX@@PEBUMODE_PARAMS@@PEAUIAudioStreamInfo@@AEAV?$unique_ptr@UStreamGroupParams@@U?$default_delete@UStreamGroupParams@@@std@@@std@@@Z`
- size: `1070`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180073990`
- `0x1800c1ca4`

## callees

- `0x180002b64`
- `0x1800088dc`
- `0x18000ca50`
- `0x18000de24`
- `0x18000e134`
- `0x18000e154`
- `0x18000e1c4`
- `0x18000e324`
- `0x18000e380`
- `0x1800126bc`
- `0x18001b3d0`
- `0x18001e850`
- `0x18003cee0`
- `0x1800521d8`
- `0x18005b85c`
- `0x180069100`
- `0x180079324`
- `0x1800cfd9c`
- `0x1800d0764`
- `0x1800e59b4`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007947f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079509`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007952c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007947f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079509`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007952c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180079723`

## string_xrefs

- `0x180079409`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180079458`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x1800794da`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`
- `0x180079689`: `avcore\audiocore\server\audiosrv\dll\audioresourcemanager.cpp`

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
      (unsigned int)&unk_1801A241B,
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
          (unsigned int)&unk_1801A239D,
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
0x180079324  mov     [rsp-8+arg_10], rbx
0x180079329  push    rbp
0x18007932a  push    rsi
0x18007932b  push    rdi
0x18007932c  push    r12
0x18007932e  push    r13
0x180079330  push    r14
0x180079332  push    r15
0x180079334  lea     rbp, [rsp-7]
0x180079339  sub     rsp, 0A0h
0x180079340  mov     [rbp+37h+var_40], r9
0x180079344  mov     dword ptr [rbp+37h+var_80], r8d
0x180079348  mov     r13d, edx
0x18007934b  mov     r15, rcx
0x18007934e  mov     r14, [rbp+37h+arg_28]
0x180079352  mov     rdi, [rbp+37h+Src]
0x180079359  mov     rsi, [rbp+37h+arg_50]
0x180079360  mov     rax, [rbp+37h+arg_58]
0x180079367  mov     [rbp+37h+var_38], rax
0x18007936b  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180079370  mov     rbx, [rax+8]
0x180079374  mov     eax, [rbx]
0x180079376  xor     r12d, r12d
0x180079379  cmp     eax, 4
0x18007937c  jbe     short loc_1800793DE
0x18007937e  test    rsi, rsi
0x180079381  jz      short loc_180079394
0x180079383  mov     rax, [rsi]
0x180079386  mov     rcx, rsi
0x180079389  mov     rax, [rax+50h]
0x18007938d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079392  jmp     short loc_180079397
0x180079394  mov     rax, r12
0x180079397  mov     [rbp+37h+var_78], rax
0x18007939b  mov     al, [rbp+37h+arg_38]
0x18007939e  mov     [rbp+37h+var_8F], al
0x1800793a1  mov     dl, [rbp+37h+arg_30]
0x1800793a4  mov     [rbp+37h+var_90], dl
0x1800793a7  mov     qword ptr [rbp+37h+var_68], r14
0x1800793ab  lea     rax, [rbp+37h+var_78]
0x1800793af  mov     [rsp+0D0h+var_98], rax
0x1800793b4  lea     rax, [rbp+37h+var_8F]
0x1800793b8  mov     [rsp+0D0h+var_A0], rax
0x1800793bd  lea     rax, [rbp+37h+var_90]
0x1800793c1  mov     [rsp+0D0h+var_A8], rax
0x1800793c6  lea     rax, [rbp+37h+var_68]
0x1800793ca  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x1800793cf  lea     rdx, unk_1801A241B
0x1800793d6  mov     rcx, rbx
0x1800793d9  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$00@@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$00@@4AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x1800793de  mov     [rbp+37h+var_70], r12
0x1800793e2  mov     rbx, [r15]
0x1800793e5  xor     edx, edx
0x1800793e7  lea     rcx, [rbp+37h+var_70]
0x1800793eb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800793f0  lea     rdx, [rbp+37h+var_70]; unsigned __int16 **
0x1800793f4  mov     rcx, rbx; this
0x1800793f7  call    ?GetEndpointId@CEndpointCharacteristics@@QEAAJPEAPEAG@Z; CEndpointCharacteristics::GetEndpointId(ushort * *)
0x1800793fc  mov     ebx, eax
0x1800793fe  test    eax, eax
0x180079400  jns     short loc_18007941F
0x180079402  mov     rcx, [rbp+3Fh]; this
0x180079406  mov     r9d, eax; char *
0x180079409  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180079410  mov     edx, 3BBh; void *
0x180079415  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007941a  jmp     loc_18007972C
0x18007941f  mov     [rbp+37h+pv], r12
0x180079423  lea     rax, [rbp+37h+pv]
0x180079427  mov     qword ptr [rbp+37h+var_60.Data1], rax
0x18007942b  mov     qword ptr [rbp+37h+var_60.Data4], r12
0x18007942f  mov     r12b, 1
0x180079432  mov     [rbp+37h+var_50], r12b
0x180079436  lea     rdx, [rbp+37h+var_60.Data4]; struct tWAVEFORMATEX **
0x18007943a  mov     rcx, rdi; Src
0x18007943d  call    ?CloneWaveFormat@@YAJPEBUtWAVEFORMATEX@@PEAPEAU1@@Z; CloneWaveFormat(tWAVEFORMATEX const *,tWAVEFORMATEX * *)
0x180079442  mov     ebx, eax
0x180079444  lea     rcx, [rbp+37h+var_60]
0x180079448  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18007944d  test    ebx, ebx
0x18007944f  jns     short loc_18007948A
0x180079451  mov     rcx, [rbp+3Fh]; this
0x180079455  mov     r9d, ebx; char *
0x180079458  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18007945f  mov     edx, 3BEh; void *
0x180079464  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180079469  nop
0x18007946a  mov     rcx, [rbp+37h+pv]; pv
0x18007946e  mov     [rbp+37h+pv], 0
0x180079476  test    rcx, rcx
0x180079479  jz      loc_18007972C
0x18007947f  call    cs:__imp_CoTaskMemFree
0x180079485  jmp     loc_18007972C
0x18007948a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180079491  mov     edi, 60h ; '`'
0x180079496  mov     ecx, edi; unsigned __int64
0x180079498  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18007949d  mov     rbx, rax
0x1800794a0  mov     qword ptr [rbp+37h+var_60.Data1], rax
0x1800794a4  test    rax, rax
0x1800794a7  jz      short loc_1800794C3
0x1800794a9  mov     r8d, edi; Size
0x1800794ac  xor     edx, edx; Val
0x1800794ae  mov     rcx, rax; void *
0x1800794b1  call    memset_0
0x1800794b6  mov     rcx, rbx; this
0x1800794b9  call    ??0StreamGroupParams@@QEAA@XZ; StreamGroupParams::StreamGroupParams(void)
0x1800794be  mov     rdi, rax
0x1800794c1  jmp     short loc_1800794C5
0x1800794c3  xor     edi, edi
0x1800794c5  mov     [rbp+37h+var_78], rdi
0x1800794c9  test    rdi, rdi
0x1800794cc  jnz     short loc_1800794FA
0x1800794ce  mov     rcx, [rbp+3Fh]; this
0x1800794d2  mov     ebx, 8007000Eh
0x1800794d7  mov     r9d, ebx; char *
0x1800794da  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800794e1  mov     edx, 3C1h; void *
0x1800794e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800794eb  nop
0x1800794ec  lea     rcx, [rbp+37h+var_78]
0x1800794f0  call    ??1?$unique_ptr@UStreamGroupParams@@U?$default_delete@UStreamGroupParams@@@std@@@std@@QEAA@XZ; std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(void)
0x1800794f5  jmp     loc_18007946A
0x1800794fa  mov     rbx, [rbp+37h+var_70]
0x1800794fe  mov     [rbp+37h+var_70], 0
0x180079506  mov     rcx, [rdi]; pv
0x180079509  call    cs:__imp_CoTaskMemFree
0x18007950f  mov     [rdi], rbx
0x180079512  cmp     r13d, 3
0x180079516  setz    al
0x180079519  mov     [rdi+31h], al
0x18007951c  mov     rbx, [rbp+37h+pv]
0x180079520  mov     [rbp+37h+pv], 0
0x180079528  mov     rcx, [rdi+10h]; pv
0x18007952c  call    cs:__imp_CoTaskMemFree
0x180079532  mov     [rdi+10h], rbx
0x180079536  mov     rax, [rbp+37h+var_40]
0x18007953a  mov     [rdi+18h], rax
0x18007953e  movups  xmm0, xmmword ptr [r14]
0x180079542  movdqu  xmmword ptr [rdi+20h], xmm0
0x180079547  mov     al, [rbp+37h+arg_30]
0x18007954a  mov     [rdi+30h], al
0x18007954d  mov     bl, [rbp+37h+arg_38]
0x180079550  mov     [rdi+32h], bl
0x180079553  mov     eax, dword ptr [rbp+37h+var_80]
0x180079556  mov     [rdi+8], eax
0x180079559  test    rsi, rsi
0x18007955c  jz      loc_1800796B2
0x180079562  movups  xmm0, xmmword ptr [r14]
0x180079566  movdqu  xmmword ptr [rbp+37h+var_60.Data1], xmm0
0x18007956b  mov     r8d, r13d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18007956e  lea     rdx, [rbp+37h+var_60]; struct _GUID
0x180079572  mov     rcx, [r15+8]; this
0x180079576  call    ?CanProcessingModeBeParameterized@EffectPack@@QEAA_NU_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@@Z; EffectPack::CanProcessingModeBeParameterized(_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001)
0x18007957b  xor     r13d, r13d
0x18007957e  test    al, al
0x180079580  jz      loc_1800796B5
0x180079586  lea     r15, [rsi+238h]
0x18007958d  mov     rdx, [r15+18h]
0x180079591  test    rdx, rdx
0x180079594  jnz     loc_18007964E
0x18007959a  lea     rbx, [rdi+50h]
0x18007959e  mov     rax, [rbp+37h+arg_48]
0x1800795a5  test    rax, rax
0x1800795a8  jz      short loc_1800795B4
0x1800795aa  mov     rax, [rax+8]
0x1800795ae  cmp     [rax+3Ch], r13d
0x1800795b2  jnz     short loc_1800795B7
0x1800795b4  mov     r12b, r13b
0x1800795b7  mov     [rdi+58h], r12b
0x1800795bb  mov     rdx, r15
0x1800795be  lea     rcx, [rdi+38h]
0x1800795c2  call    ??4?$vector@UAudioEffectState@CProcessingModeParameters@@V?$allocator@UAudioEffectState@CProcessingModeParameters@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<CProcessingModeParameters::AudioEffectState>::operator=(std::vector<CProcessingModeParameters::AudioEffectState> const &)
0x1800795c7  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1800795cc  mov     r15, [rax+8]
0x1800795d0  mov     eax, [r15]
0x1800795d3  cmp     eax, 4
0x1800795d6  jbe     short loc_180079649
0x1800795d8  mov     rax, [rdi+40h]
0x1800795dc  sub     rax, [rdi+38h]
0x1800795e0  sar     rax, 2
0x1800795e4  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x1800795ee  imul    rax, rcx
0x1800795f2  mov     qword ptr [rbp+37h+var_68], rax
0x1800795f6  mov     al, [rdi+58h]
0x1800795f9  mov     [rbp+37h+var_90], al
0x1800795fc  mov     rax, [rbx]
0x1800795ff  mov     [rbp+37h+var_80], rax
0x180079603  mov     rax, [rsi]
0x180079606  mov     rcx, rsi
0x180079609  mov     rax, [rax+50h]
0x18007960d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079612  mov     qword ptr [rbp+37h+var_60.Data1], rax
0x180079616  lea     rax, [rbp+37h+var_68]
0x18007961a  mov     [rsp+0D0h+var_98], rax
0x18007961f  lea     rax, [rbp+37h+var_90]
0x180079623  mov     [rsp+0D0h+var_A0], rax
0x180079628  lea     rax, [rbp+37h+var_80]
0x18007962c  mov     [rsp+0D0h+var_A8], rax
0x180079631  lea     rax, [rbp+37h+var_60]
0x180079635  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18007963a  lea     rdx, unk_1801A239D
0x180079641  mov     rcx, r15
0x180079644  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x180079649  mov     bl, [rbp+37h+arg_38]
0x18007964c  jmp     short loc_1800796B5
0x18007964e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180079652  lea     rcx, [rbp+37h+var_80]
0x180079656  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18007965b  lea     rbx, [rdi+50h]
0x18007965f  lea     rdx, [rbp+37h+var_80]
0x180079663  mov     rcx, rbx
0x180079666  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18007966b  lea     rcx, [rbp+37h+var_80]
0x18007966f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180079674  cmp     [rbx], r13
0x180079677  jnz     loc_18007959E
0x18007967d  mov     rcx, [rbp+3Fh]; this
0x180079681  mov     ebx, 8007000Eh
0x180079686  mov     r9d, ebx; char *
0x180079689  lea     r8, aAvcoreAudiocor_74; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180079690  mov     edx, 3D3h; void *
0x180079695  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007969a  nop
0x18007969b  lea     rcx, [rbp+37h+var_78]
0x18007969f  call    ??1?$unique_ptr@UStreamGroupParams@@U?$default_delete@UStreamGroupParams@@@std@@@std@@QEAA@XZ; std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(void)
0x1800796a4  nop
0x1800796a5  mov     rcx, [rbp+37h+pv]
0x1800796a9  mov     [rbp+37h+pv], r13
0x1800796ad  jmp     loc_180079476
0x1800796b2  xor     r13d, r13d
0x1800796b5  mov     [rbp+37h+var_78], r13
0x1800796b9  mov     rax, [rbp+37h+var_38]
0x1800796bd  mov     rdx, [rax]
0x1800796c0  mov     [rax], rdi
0x1800796c3  test    rdx, rdx
0x1800796c6  jz      short loc_1800796CD
0x1800796c8  call    ??R?$default_delete@UStreamGroupParams@@@std@@QEBAXPEAUStreamGroupParams@@@Z; std::default_delete<StreamGroupParams>::operator()(StreamGroupParams *)
0x1800796cd  lea     rax, WPP_GLOBAL_Control
0x1800796d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800796db  cmp     rcx, rax
0x1800796de  jz      short loc_18007970C
0x1800796e0  test    dword ptr [rcx+1Ch], 100h
0x1800796e7  jz      short loc_18007970C
0x1800796e9  cmp     byte ptr [rcx+19h], 4
0x1800796ed  jb      short loc_18007970C
0x1800796ef  movzx   eax, bl
0x1800796f2  movzx   edx, [rbp+37h+arg_30]
0x1800796f6  mov     dword ptr [rsp+0D0h+var_A8], eax
0x1800796fa  mov     [rsp+0D0h+var_B0], edx
0x1800796fe  mov     r9, [rbp+37h+var_40]
0x180079702  mov     rcx, [rcx+10h]
0x180079706  call    WPP_SF_Idd
0x18007970b  nop
0x18007970c  lea     rcx, [rbp+37h+var_78]
0x180079710  call    ??1?$unique_ptr@UStreamGroupParams@@U?$default_delete@UStreamGroupParams@@@std@@@std@@QEAA@XZ; std::unique_ptr<StreamGroupParams>::~unique_ptr<StreamGroupParams>(void)
0x180079715  nop
0x180079716  mov     rcx, [rbp+37h+pv]; pv
0x18007971a  mov     [rbp+37h+pv], r13
0x18007971e  test    rcx, rcx
0x180079721  jz      short loc_180079729
0x180079723  call    cs:__imp_CoTaskMemFree
0x180079729  mov     ebx, r13d
0x18007972c  lea     rcx, [rbp+37h+var_70]
0x180079730  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180079735  mov     eax, ebx
0x180079737  mov     rbx, [rsp+0D0h+arg_10]
0x18007973f  add     rsp, 0A0h
0x180079746  pop     r15
0x180079748  pop     r14
0x18007974a  pop     r13
0x18007974c  pop     r12
0x18007974e  pop     rdi
0x18007974f  pop     rsi
0x180079750  pop     rbp
0x180079751  retn
```
