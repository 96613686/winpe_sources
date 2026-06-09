# EffectPack::ResetDeviceFormat(void)

- ea: `0x180144adc`
- end: `0x180144d9f`
- name: `?ResetDeviceFormat@EffectPack@@QEAAJXZ`
- size: `707`
- prototype: `__int64 __fastcall(EffectPack *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180119a00`
- `0x1801447e0`

## callees

- `0x180005a7c`
- `0x180008a2c`
- `0x18001280c`
- `0x1800202b0`
- `0x18002240c`
- `0x1800413e0`
- `0x180041440`
- `0x180072e10`
- `0x18008a0f4`
- `0x1800cbfcc`
- `0x1800cd8d0`
- `0x180144adc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144bf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144cf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144d3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144d53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144d6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144d7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144bf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144cf2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144d3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144d53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144d6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144d7e`

## string_xrefs

- `0x180144bd9`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180144c30`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180144ccf`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180144d20`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EffectPack::ResetDeviceFormat(EffectPack *this)
{
  int v2; // r8d
  int v3; // r9d
  int DeviceFormatAndSpatialSettings; // esi
  __int64 v5; // rdx
  void *v6; // rcx
  int v8; // eax
  struct tWAVEFORMATEX *v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  struct tWAVEFORMATEX *v12; // rcx
  void *v13; // rcx
  struct tWAVEFORMATEX *v14; // rcx
  void *v15; // rcx
  int v16; // [rsp+20h] [rbp-39h]
  int v17; // [rsp+20h] [rbp-39h]
  int v18; // [rsp+20h] [rbp-39h]
  int v19; // [rsp+20h] [rbp-39h]
  LPVOID pv; // [rsp+40h] [rbp-19h] BYREF
  struct tWAVEFORMATEX *v21; // [rsp+48h] [rbp-11h] BYREF
  struct _GUID v22; // [rsp+50h] [rbp-9h] BYREF
  struct _GUID v23; // [rsp+60h] [rbp+7h] BYREF
  char v24; // [rsp+70h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( **((_DWORD **)this + 265) > 4u && (unsigned __int8)tlgKeywordOn(*((_QWORD *)this + 265), 16) )
  {
    v21 = *(struct tWAVEFORMATEX **)(*((_QWORD *)this + 198) + 48LL);
    v23 = *(struct _GUID *)*((_QWORD *)this + 196);
    *(_QWORD *)&v22.Data1 = &v23;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
      v2,
      (unsigned int)byte_1801AB069,
      v2,
      v3,
      (__int64)&v22,
      (__int64)&v21);
  }
  v22 = GUID_00000000_0000_0000_0000_000000000000;
  EffectPack::GetDefaultConnectorProcessingModeConfiguration(this, eHostProcessConnector, &v22, 0, 0);
  pv = 0;
  *(_QWORD *)&v23.Data1 = &pv;
  *(_QWORD *)v23.Data4 = 0;
  v24 = 1;
  DeviceFormatAndSpatialSettings = EffectPack::GetDeviceFormatAndSpatialSettings(
                                     (CEndpointCharacteristics **)this,
                                     eHostProcessConnector,
                                     0,
                                     (struct tWAVEFORMATEX **)v23.Data4,
                                     0,
                                     0,
                                     0);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v23);
  if ( DeviceFormatAndSpatialSettings < 0 )
  {
    v5 = 9139;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)DeviceFormatAndSpatialSettings,
      v16);
LABEL_7:
    v6 = pv;
    pv = 0;
    if ( v6 )
      CoTaskMemFree(v6);
    return (unsigned int)DeviceFormatAndSpatialSettings;
  }
  v23 = v22;
  v8 = EffectPack::ConfirmDeviceFormat(
         (CEndpointCharacteristics **)this,
         (const struct tWAVEFORMATEX *)pv,
         &v23,
         eHostProcessConnector,
         0);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x23B6,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v8,
      v17);
    DeviceFormatAndSpatialSettings = EffectPack::SetDeviceFormatAndSpatialSettings(this, eHostProcessConnector, 0, 0, 0);
    if ( DeviceFormatAndSpatialSettings < 0 )
    {
      v5 = 9146;
      goto LABEL_6;
    }
    DeviceFormatAndSpatialSettings = CEndpointCharacteristics::ClearMixFormatCache(*((_QWORD *)this + 198), 0);
    if ( DeviceFormatAndSpatialSettings < 0 )
    {
      v5 = 9149;
      goto LABEL_6;
    }
    v21 = 0;
    *(_QWORD *)&v23.Data1 = &v21;
    *(_QWORD *)v23.Data4 = 0;
    v24 = 1;
    DeviceFormatAndSpatialSettings = EffectPack::GetDeviceFormatAndSpatialSettings(
                                       (CEndpointCharacteristics **)this,
                                       eHostProcessConnector,
                                       1,
                                       (struct tWAVEFORMATEX **)v23.Data4,
                                       0,
                                       0,
                                       0);
    wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v23);
    if ( DeviceFormatAndSpatialSettings < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23C1,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)(unsigned int)DeviceFormatAndSpatialSettings,
        v18);
      v9 = v21;
      v21 = 0;
      if ( v9 )
        CoTaskMemFree(v9);
      goto LABEL_7;
    }
    v10 = EffectPack::SetDeviceFormatAndSpatialSettings(this, eHostProcessConnector, v21, 0, 0);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23C4,
        (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
        (const char *)(unsigned int)v10,
        v19);
      v12 = v21;
      v21 = 0;
      if ( v12 )
        CoTaskMemFree(v12);
      v13 = pv;
      pv = 0;
      if ( v13 )
        CoTaskMemFree(v13);
      return v11;
    }
    v14 = v21;
    v21 = 0;
    if ( v14 )
      CoTaskMemFree(v14);
  }
  v15 = pv;
  pv = 0;
  if ( v15 )
    CoTaskMemFree(v15);
  return 0;
}

```

## disassembly

```asm
0x180144adc  push    rbp
0x180144ade  push    rbx
0x180144adf  push    rsi
0x180144ae0  push    r14
0x180144ae2  lea     rbp, [rsp-3Fh]
0x180144ae7  sub     rsp, 98h
0x180144aee  mov     rax, cs:__security_cookie
0x180144af5  xor     rax, rsp
0x180144af8  mov     [rbp+57h+var_30], rax
0x180144afc  mov     rbx, rcx
0x180144aff  mov     r8, [rcx+848h]
0x180144b06  mov     eax, [r8]
0x180144b09  xor     r14d, r14d
0x180144b0c  cmp     eax, 4
0x180144b0f  jbe     short loc_180144B68
0x180144b11  lea     edx, [r14+10h]
0x180144b15  mov     rcx, r8
0x180144b18  call    _tlgKeywordOn
0x180144b1d  test    al, al
0x180144b1f  jz      short loc_180144B68
0x180144b21  mov     rax, [rbx+630h]
0x180144b28  mov     rcx, [rax+30h]
0x180144b2c  mov     [rbp+57h+var_68], rcx
0x180144b30  mov     rax, [rbx+620h]
0x180144b37  movups  xmm0, xmmword ptr [rax]
0x180144b3a  movdqu  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x180144b3f  lea     rax, [rbp+57h+var_50]
0x180144b43  mov     qword ptr [rbp+57h+var_60.Data1], rax
0x180144b47  lea     rax, [rbp+57h+var_68]
0x180144b4b  mov     [rsp+0B0h+var_88], rax
0x180144b50  lea     rax, [rbp+57h+var_60]
0x180144b54  mov     [rsp+0B0h+var_90], rax
0x180144b59  lea     rdx, byte_1801AB069
0x180144b60  mov     rcx, r8
0x180144b63  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &)
0x180144b68  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180144b6f  movdqu  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x180144b74  mov     [rsp+0B0h+var_90], r14; struct _GUID *
0x180144b79  xor     r9d, r9d; struct _GUID *
0x180144b7c  lea     r8, [rbp+57h+var_60]; struct _GUID *
0x180144b80  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180144b82  mov     rcx, rbx; this
0x180144b85  call    ?GetDefaultConnectorProcessingModeConfiguration@EffectPack@@QEAAXW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAU_GUID@@11@Z; EffectPack::GetDefaultConnectorProcessingModeConfiguration(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID *,_GUID *,_GUID *)
0x180144b8a  mov     [rbp+57h+pv], r14
0x180144b8e  lea     rax, [rbp+57h+pv]
0x180144b92  mov     qword ptr [rbp+57h+var_50.Data1], rax
0x180144b96  mov     qword ptr [rbp+57h+var_50.Data4], r14
0x180144b9a  mov     [rbp+57h+var_40], 1
0x180144b9e  mov     [rsp+0B0h+var_80], r14; pv
0x180144ba3  mov     [rsp+0B0h+var_88], r14; unsigned int *
0x180144ba8  mov     [rsp+0B0h+var_90], r14; int
0x180144bad  lea     r9, [rbp+57h+var_50.Data4]; struct tWAVEFORMATEX **
0x180144bb1  xor     r8d, r8d; int
0x180144bb4  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180144bb6  mov     rcx, rbx; this
0x180144bb9  call    ?GetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@HPEAPEAUtWAVEFORMATEX@@PEAPEAUSpatialAudioSettings@@PEAIPEAPEAUSpatialAudioEncoderDescriptor@@@Z; EffectPack::GetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int,tWAVEFORMATEX * *,SpatialAudioSettings * *,uint *,SpatialAudioEncoderDescriptor * *)
0x180144bbe  mov     esi, eax
0x180144bc0  lea     rcx, [rbp+57h+var_50]
0x180144bc4  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180144bc9  test    esi, esi
0x180144bcb  jns     short loc_180144C00
0x180144bcd  mov     edx, 23B3h; void *
0x180144bd2  mov     rcx, [rbp+5Fh]; this
0x180144bd6  mov     r9d, esi; char *
0x180144bd9  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180144be0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180144be5  nop
0x180144be6  mov     rcx, [rbp+57h+pv]; pv
0x180144bea  mov     [rbp+57h+pv], r14
0x180144bee  test    rcx, rcx
0x180144bf1  jz      short loc_180144BF9
0x180144bf3  call    cs:__imp_CoTaskMemFree
0x180144bf9  mov     eax, esi
0x180144bfb  jmp     loc_180144D86
0x180144c00  movaps  xmm0, xmmword ptr [rbp+57h+var_60.Data1]
0x180144c04  movdqa  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x180144c09  mov     dword ptr [rsp+0B0h+var_90], r14d; int
0x180144c0e  xor     r9d, r9d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180144c11  lea     r8, [rbp+57h+var_50]; struct _GUID *
0x180144c15  mov     rdx, [rbp+57h+pv]; struct tWAVEFORMATEX *
0x180144c19  mov     rcx, rbx; this
0x180144c1c  call    ?ConfirmDeviceFormat@EffectPack@@AEAAJPEBUtWAVEFORMATEX@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@H@Z; EffectPack::ConfirmDeviceFormat(tWAVEFORMATEX const *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int)
0x180144c21  mov     rcx, [rbp+5Fh]; this
0x180144c25  test    eax, eax
0x180144c27  jns     loc_180144D71
0x180144c2d  mov     r9d, eax; char *
0x180144c30  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180144c37  mov     edx, 23B6h; void *
0x180144c3c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180144c41  mov     byte ptr [rsp+0B0h+var_90], r14b; bool
0x180144c46  xor     r9d, r9d; struct SpatialAudioSettings *
0x180144c49  xor     r8d, r8d; struct tWAVEFORMATEX *
0x180144c4c  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180144c4e  mov     rcx, rbx; this
0x180144c51  call    ?SetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@PEBUSpatialAudioSettings@@_N@Z; EffectPack::SetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,SpatialAudioSettings const *,bool)
0x180144c56  mov     esi, eax
0x180144c58  test    eax, eax
0x180144c5a  jns     short loc_180144C66
0x180144c5c  mov     edx, 23BAh
0x180144c61  jmp     loc_180144BD2
0x180144c66  xor     edx, edx
0x180144c68  mov     rcx, [rbx+630h]
0x180144c6f  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x180144c74  mov     esi, eax
0x180144c76  test    eax, eax
0x180144c78  jns     short loc_180144C84
0x180144c7a  mov     edx, 23BDh
0x180144c7f  jmp     loc_180144BD2
0x180144c84  mov     [rbp+57h+var_68], r14
0x180144c88  lea     rax, [rbp+57h+var_68]
0x180144c8c  mov     qword ptr [rbp+57h+var_50.Data1], rax
0x180144c90  mov     qword ptr [rbp+57h+var_50.Data4], r14
0x180144c94  mov     [rbp+57h+var_40], 1
0x180144c98  mov     [rsp+0B0h+var_80], r14; pv
0x180144c9d  mov     [rsp+0B0h+var_88], r14; unsigned int *
0x180144ca2  mov     [rsp+0B0h+var_90], r14; int
0x180144ca7  lea     r9, [rbp+57h+var_50.Data4]; struct tWAVEFORMATEX **
0x180144cab  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180144cad  lea     r8d, [rdx+1]; int
0x180144cb1  mov     rcx, rbx; this
0x180144cb4  call    ?GetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@HPEAPEAUtWAVEFORMATEX@@PEAPEAUSpatialAudioSettings@@PEAIPEAPEAUSpatialAudioEncoderDescriptor@@@Z; EffectPack::GetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int,tWAVEFORMATEX * *,SpatialAudioSettings * *,uint *,SpatialAudioEncoderDescriptor * *)
0x180144cb9  mov     esi, eax
0x180144cbb  lea     rcx, [rbp+57h+var_50]
0x180144cbf  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180144cc4  test    esi, esi
0x180144cc6  jns     short loc_180144CFD
0x180144cc8  mov     rcx, [rbp+5Fh]; this
0x180144ccc  mov     r9d, esi; char *
0x180144ccf  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180144cd6  mov     edx, 23C1h; void *
0x180144cdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180144ce0  nop
0x180144ce1  mov     rcx, [rbp+57h+var_68]; pv
0x180144ce5  mov     [rbp+57h+var_68], r14
0x180144ce9  test    rcx, rcx
0x180144cec  jz      loc_180144BE6
0x180144cf2  call    cs:__imp_CoTaskMemFree
0x180144cf8  jmp     loc_180144BE6
0x180144cfd  mov     byte ptr [rsp+0B0h+var_90], r14b; int
0x180144d02  xor     r9d, r9d; struct SpatialAudioSettings *
0x180144d05  mov     r8, [rbp+57h+var_68]; struct tWAVEFORMATEX *
0x180144d09  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180144d0b  mov     rcx, rbx; this
0x180144d0e  call    ?SetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@PEBUSpatialAudioSettings@@_N@Z; EffectPack::SetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,SpatialAudioSettings const *,bool)
0x180144d13  mov     ebx, eax
0x180144d15  test    eax, eax
0x180144d17  jns     short loc_180144D5D
0x180144d19  mov     rcx, [rbp+5Fh]; this
0x180144d1d  mov     r9d, eax; char *
0x180144d20  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180144d27  mov     edx, 23C4h; void *
0x180144d2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180144d31  nop
0x180144d32  mov     rcx, [rbp+57h+var_68]; pv
0x180144d36  mov     [rbp+57h+var_68], r14
0x180144d3a  test    rcx, rcx
0x180144d3d  jz      short loc_180144D46
0x180144d3f  call    cs:__imp_CoTaskMemFree
0x180144d45  nop
0x180144d46  mov     rcx, [rbp+57h+pv]; pv
0x180144d4a  mov     [rbp+57h+pv], r14
0x180144d4e  test    rcx, rcx
0x180144d51  jz      short loc_180144D59
0x180144d53  call    cs:__imp_CoTaskMemFree
0x180144d59  mov     eax, ebx
0x180144d5b  jmp     short loc_180144D86
0x180144d5d  mov     rcx, [rbp+57h+var_68]; pv
0x180144d61  mov     [rbp+57h+var_68], r14
0x180144d65  test    rcx, rcx
0x180144d68  jz      short loc_180144D71
0x180144d6a  call    cs:__imp_CoTaskMemFree
0x180144d70  nop
0x180144d71  mov     rcx, [rbp+57h+pv]; pv
0x180144d75  mov     [rbp+57h+pv], r14
0x180144d79  test    rcx, rcx
0x180144d7c  jz      short loc_180144D84
0x180144d7e  call    cs:__imp_CoTaskMemFree
0x180144d84  xor     eax, eax
0x180144d86  mov     rcx, [rbp+57h+var_30]
0x180144d8a  xor     rcx, rsp; StackCookie
0x180144d8d  call    __security_check_cookie
0x180144d92  add     rsp, 98h
0x180144d99  pop     r14
0x180144d9b  pop     rsi
0x180144d9c  pop     rbx
0x180144d9d  pop     rbp
0x180144d9e  retn
```
