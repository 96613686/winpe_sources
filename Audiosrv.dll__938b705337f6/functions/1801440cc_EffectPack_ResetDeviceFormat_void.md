# EffectPack::ResetDeviceFormat(void)

- ea: `0x1801440cc`
- end: `0x18014438f`
- name: `?ResetDeviceFormat@EffectPack@@QEAAJXZ`
- size: `707`
- prototype: `__int64 __fastcall(EffectPack *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801197b0`
- `0x180143dd0`

## callees

- `0x180005870`
- `0x1800088dc`
- `0x1800126bc`
- `0x180020160`
- `0x1800222bc`
- `0x1800412c8`
- `0x180041328`
- `0x180073310`
- `0x18008a5f4`
- `0x1800cdfbc`
- `0x1800cf8c0`
- `0x1801440cc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801441e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801442e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014432f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014435a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014436e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801441e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801442e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014432f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014435a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18014436e`

## string_xrefs

- `0x1801441c9`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180144220`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x1801442bf`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180144310`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

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
      (unsigned int)&unk_1801A9796,
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
                                     this,
                                     eHostProcessConnector,
                                     0,
                                     (struct tWAVEFORMATEX **)v23.Data4,
                                     0,
                                     0,
                                     0);
  wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v23);
  if ( DeviceFormatAndSpatialSettings < 0 )
  {
    v5 = 9140;
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
  v8 = EffectPack::ConfirmDeviceFormat(this, (const struct tWAVEFORMATEX *)pv, &v23, eHostProcessConnector, 0);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x23B7,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v8,
      v17);
    DeviceFormatAndSpatialSettings = EffectPack::SetDeviceFormatAndSpatialSettings(this, eHostProcessConnector, 0, 0, 0);
    if ( DeviceFormatAndSpatialSettings < 0 )
    {
      v5 = 9147;
      goto LABEL_6;
    }
    DeviceFormatAndSpatialSettings = CEndpointCharacteristics::ClearMixFormatCache(*((_QWORD *)this + 198), 0);
    if ( DeviceFormatAndSpatialSettings < 0 )
    {
      v5 = 9150;
      goto LABEL_6;
    }
    v21 = 0;
    *(_QWORD *)&v23.Data1 = &v21;
    *(_QWORD *)v23.Data4 = 0;
    v24 = 1;
    DeviceFormatAndSpatialSettings = EffectPack::GetDeviceFormatAndSpatialSettings(
                                       this,
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
        (void *)0x23C2,
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
        (void *)0x23C5,
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
0x1801440cc  push    rbp
0x1801440ce  push    rbx
0x1801440cf  push    rsi
0x1801440d0  push    r14
0x1801440d2  lea     rbp, [rsp-3Fh]
0x1801440d7  sub     rsp, 98h
0x1801440de  mov     rax, cs:__security_cookie
0x1801440e5  xor     rax, rsp
0x1801440e8  mov     [rbp+57h+var_30], rax
0x1801440ec  mov     rbx, rcx
0x1801440ef  mov     r8, [rcx+848h]
0x1801440f6  mov     eax, [r8]
0x1801440f9  xor     r14d, r14d
0x1801440fc  cmp     eax, 4
0x1801440ff  jbe     short loc_180144158
0x180144101  lea     edx, [r14+10h]
0x180144105  mov     rcx, r8
0x180144108  call    _tlgKeywordOn
0x18014410d  test    al, al
0x18014410f  jz      short loc_180144158
0x180144111  mov     rax, [rbx+630h]
0x180144118  mov     rcx, [rax+30h]
0x18014411c  mov     [rbp+57h+var_68], rcx
0x180144120  mov     rax, [rbx+620h]
0x180144127  movups  xmm0, xmmword ptr [rax]
0x18014412a  movdqu  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x18014412f  lea     rax, [rbp+57h+var_50]
0x180144133  mov     qword ptr [rbp+57h+var_60.Data1], rax
0x180144137  lea     rax, [rbp+57h+var_68]
0x18014413b  mov     [rsp+0B0h+var_88], rax
0x180144140  lea     rax, [rbp+57h+var_60]
0x180144144  mov     [rsp+0B0h+var_90], rax
0x180144149  lea     rdx, unk_1801A9796
0x180144150  mov     rcx, r8
0x180144153  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &)
0x180144158  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18014415f  movdqu  xmmword ptr [rbp+57h+var_60.Data1], xmm0
0x180144164  mov     [rsp+0B0h+var_90], r14; struct _GUID *
0x180144169  xor     r9d, r9d; struct _GUID *
0x18014416c  lea     r8, [rbp+57h+var_60]; struct _GUID *
0x180144170  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180144172  mov     rcx, rbx; this
0x180144175  call    ?GetDefaultConnectorProcessingModeConfiguration@EffectPack@@QEAAXW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEAU_GUID@@11@Z; EffectPack::GetDefaultConnectorProcessingModeConfiguration(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID *,_GUID *,_GUID *)
0x18014417a  mov     [rbp+57h+pv], r14
0x18014417e  lea     rax, [rbp+57h+pv]
0x180144182  mov     qword ptr [rbp+57h+var_50.Data1], rax
0x180144186  mov     qword ptr [rbp+57h+var_50.Data4], r14
0x18014418a  mov     [rbp+57h+var_40], 1
0x18014418e  mov     [rsp+0B0h+var_80], r14; pv
0x180144193  mov     [rsp+0B0h+var_88], r14; unsigned int *
0x180144198  mov     [rsp+0B0h+var_90], r14; int
0x18014419d  lea     r9, [rbp+57h+var_50.Data4]; struct tWAVEFORMATEX **
0x1801441a1  xor     r8d, r8d; int
0x1801441a4  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1801441a6  mov     rcx, rbx; this
0x1801441a9  call    ?GetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@HPEAPEAUtWAVEFORMATEX@@PEAPEAUSpatialAudioSettings@@PEAIPEAPEAUSpatialAudioEncoderDescriptor@@@Z; EffectPack::GetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int,tWAVEFORMATEX * *,SpatialAudioSettings * *,uint *,SpatialAudioEncoderDescriptor * *)
0x1801441ae  mov     esi, eax
0x1801441b0  lea     rcx, [rbp+57h+var_50]
0x1801441b4  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1801441b9  test    esi, esi
0x1801441bb  jns     short loc_1801441F0
0x1801441bd  mov     edx, 23B4h; void *
0x1801441c2  mov     rcx, [rbp+5Fh]; this
0x1801441c6  mov     r9d, esi; char *
0x1801441c9  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x1801441d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801441d5  nop
0x1801441d6  mov     rcx, [rbp+57h+pv]; pv
0x1801441da  mov     [rbp+57h+pv], r14
0x1801441de  test    rcx, rcx
0x1801441e1  jz      short loc_1801441E9
0x1801441e3  call    cs:__imp_CoTaskMemFree
0x1801441e9  mov     eax, esi
0x1801441eb  jmp     loc_180144376
0x1801441f0  movaps  xmm0, xmmword ptr [rbp+57h+var_60.Data1]
0x1801441f4  movdqa  xmmword ptr [rbp+57h+var_50.Data1], xmm0
0x1801441f9  mov     dword ptr [rsp+0B0h+var_90], r14d; int
0x1801441fe  xor     r9d, r9d; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x180144201  lea     r8, [rbp+57h+var_50]; struct _GUID *
0x180144205  mov     rdx, [rbp+57h+pv]; struct tWAVEFORMATEX *
0x180144209  mov     rcx, rbx; this
0x18014420c  call    ?ConfirmDeviceFormat@EffectPack@@AEAAJPEBUtWAVEFORMATEX@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@H@Z; EffectPack::ConfirmDeviceFormat(tWAVEFORMATEX const *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int)
0x180144211  mov     rcx, [rbp+5Fh]; this
0x180144215  test    eax, eax
0x180144217  jns     loc_180144361
0x18014421d  mov     r9d, eax; char *
0x180144220  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180144227  mov     edx, 23B7h; void *
0x18014422c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180144231  mov     byte ptr [rsp+0B0h+var_90], r14b; bool
0x180144236  xor     r9d, r9d; struct SpatialAudioSettings *
0x180144239  xor     r8d, r8d; struct tWAVEFORMATEX *
0x18014423c  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18014423e  mov     rcx, rbx; this
0x180144241  call    ?SetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@PEBUSpatialAudioSettings@@_N@Z; EffectPack::SetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,SpatialAudioSettings const *,bool)
0x180144246  mov     esi, eax
0x180144248  test    eax, eax
0x18014424a  jns     short loc_180144256
0x18014424c  mov     edx, 23BBh
0x180144251  jmp     loc_1801441C2
0x180144256  xor     edx, edx
0x180144258  mov     rcx, [rbx+630h]
0x18014425f  call    ?ClearMixFormatCache@CEndpointCharacteristics@@QEAAJW4CMFC_OPTIONS@@@Z; CEndpointCharacteristics::ClearMixFormatCache(CMFC_OPTIONS)
0x180144264  mov     esi, eax
0x180144266  test    eax, eax
0x180144268  jns     short loc_180144274
0x18014426a  mov     edx, 23BEh
0x18014426f  jmp     loc_1801441C2
0x180144274  mov     [rbp+57h+var_68], r14
0x180144278  lea     rax, [rbp+57h+var_68]
0x18014427c  mov     qword ptr [rbp+57h+var_50.Data1], rax
0x180144280  mov     qword ptr [rbp+57h+var_50.Data4], r14
0x180144284  mov     [rbp+57h+var_40], 1
0x180144288  mov     [rsp+0B0h+var_80], r14; pv
0x18014428d  mov     [rsp+0B0h+var_88], r14; unsigned int *
0x180144292  mov     [rsp+0B0h+var_90], r14; int
0x180144297  lea     r9, [rbp+57h+var_50.Data4]; struct tWAVEFORMATEX **
0x18014429b  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x18014429d  lea     r8d, [rdx+1]; int
0x1801442a1  mov     rcx, rbx; this
0x1801442a4  call    ?GetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@HPEAPEAUtWAVEFORMATEX@@PEAPEAUSpatialAudioSettings@@PEAIPEAPEAUSpatialAudioEncoderDescriptor@@@Z; EffectPack::GetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,int,tWAVEFORMATEX * *,SpatialAudioSettings * *,uint *,SpatialAudioEncoderDescriptor * *)
0x1801442a9  mov     esi, eax
0x1801442ab  lea     rcx, [rbp+57h+var_50]
0x1801442af  call    ??1?$out_param_t@V?$unique_ptr@U_GUID@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_GUID,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x1801442b4  test    esi, esi
0x1801442b6  jns     short loc_1801442ED
0x1801442b8  mov     rcx, [rbp+5Fh]; this
0x1801442bc  mov     r9d, esi; char *
0x1801442bf  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x1801442c6  mov     edx, 23C2h; void *
0x1801442cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801442d0  nop
0x1801442d1  mov     rcx, [rbp+57h+var_68]; pv
0x1801442d5  mov     [rbp+57h+var_68], r14
0x1801442d9  test    rcx, rcx
0x1801442dc  jz      loc_1801441D6
0x1801442e2  call    cs:__imp_CoTaskMemFree
0x1801442e8  jmp     loc_1801441D6
0x1801442ed  mov     byte ptr [rsp+0B0h+var_90], r14b; int
0x1801442f2  xor     r9d, r9d; struct SpatialAudioSettings *
0x1801442f5  mov     r8, [rbp+57h+var_68]; struct tWAVEFORMATEX *
0x1801442f9  xor     edx, edx; enum __MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001
0x1801442fb  mov     rcx, rbx; this
0x1801442fe  call    ?SetDeviceFormatAndSpatialSettings@EffectPack@@QEAAJW4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@PEBUtWAVEFORMATEX@@PEBUSpatialAudioSettings@@_N@Z; EffectPack::SetDeviceFormatAndSpatialSettings(__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,tWAVEFORMATEX const *,SpatialAudioSettings const *,bool)
0x180144303  mov     ebx, eax
0x180144305  test    eax, eax
0x180144307  jns     short loc_18014434D
0x180144309  mov     rcx, [rbp+5Fh]; this
0x18014430d  mov     r9d, eax; char *
0x180144310  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180144317  mov     edx, 23C5h; void *
0x18014431c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180144321  nop
0x180144322  mov     rcx, [rbp+57h+var_68]; pv
0x180144326  mov     [rbp+57h+var_68], r14
0x18014432a  test    rcx, rcx
0x18014432d  jz      short loc_180144336
0x18014432f  call    cs:__imp_CoTaskMemFree
0x180144335  nop
0x180144336  mov     rcx, [rbp+57h+pv]; pv
0x18014433a  mov     [rbp+57h+pv], r14
0x18014433e  test    rcx, rcx
0x180144341  jz      short loc_180144349
0x180144343  call    cs:__imp_CoTaskMemFree
0x180144349  mov     eax, ebx
0x18014434b  jmp     short loc_180144376
0x18014434d  mov     rcx, [rbp+57h+var_68]; pv
0x180144351  mov     [rbp+57h+var_68], r14
0x180144355  test    rcx, rcx
0x180144358  jz      short loc_180144361
0x18014435a  call    cs:__imp_CoTaskMemFree
0x180144360  nop
0x180144361  mov     rcx, [rbp+57h+pv]; pv
0x180144365  mov     [rbp+57h+pv], r14
0x180144369  test    rcx, rcx
0x18014436c  jz      short loc_180144374
0x18014436e  call    cs:__imp_CoTaskMemFree
0x180144374  xor     eax, eax
0x180144376  mov     rcx, [rbp+57h+var_30]
0x18014437a  xor     rcx, rsp; StackCookie
0x18014437d  call    __security_check_cookie
0x180144382  add     rsp, 98h
0x180144389  pop     r14
0x18014438b  pop     rsi
0x18014438c  pop     rbx
0x18014438d  pop     rbp
0x18014438e  retn
```
