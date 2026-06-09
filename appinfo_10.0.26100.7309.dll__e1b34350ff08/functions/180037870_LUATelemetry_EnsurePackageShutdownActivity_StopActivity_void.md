# LUATelemetry::EnsurePackageShutdownActivity::StopActivity(void)

- ea: `0x180037870`
- end: `0x180037a7d`
- name: `?StopActivity@EnsurePackageShutdownActivity@LUATelemetry@@MEAAXXZ`
- size: `525`
- prototype: `void __fastcall(LUATelemetry::EnsurePackageShutdownActivity *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x18000c7d0`
- `0x18000cb30`
- `0x180010f8c`
- `0x180018d70`
- `0x180018da8`
- `0x180018dcc`
- `0x18001fd6c`
- `0x180033a1c`
- `0x180033c0c`
- `0x180037870`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037a1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037a1a`

## pseudocode

```c
void __fastcall LUATelemetry::EnsurePackageShutdownActivity::StopActivity(
        LUATelemetry::EnsurePackageShutdownActivity *this)
{
  __int64 FailureInfo; // rdi
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // r9
  const unsigned __int16 *v7; // rax
  const wchar_t *v8; // rcx
  const GUID *v9; // rax
  __int64 v10; // r9
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  int Result; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  const GUID *v18; // rax
  __int64 v19; // r9
  int v20; // [rsp+A0h] [rbp-19h] BYREF
  int v21; // [rsp+A4h] [rbp-15h] BYREF
  int v22; // [rsp+A8h] [rbp-11h] BYREF
  const wchar_t *v23; // [rsp+B0h] [rbp-9h] BYREF
  const unsigned __int16 *v24; // [rsp+B8h] [rbp-1h] BYREF
  const wchar_t *v25; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v26; // [rsp+C8h] [rbp+Fh] BYREF
  const unsigned __int16 *v27; // [rsp+D0h] [rbp+17h] BYREF
  const wchar_t *v28; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v29; // [rsp+E0h] [rbp+27h] BYREF
  const unsigned __int16 *v30; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v31; // [rsp+F0h] [rbp+37h] BYREF
  _QWORD v32[3]; // [rsp+F8h] [rbp+3Fh] BYREF
  DWORD CurrentThreadId; // [rsp+128h] [rbp+6Fh] BYREF
  int v34; // [rsp+130h] [rbp+77h] BYREF
  __int64 v35; // [rsp+138h] [rbp+7Fh] BYREF

  FailureInfo = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo();
  if ( FailureInfo )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v3 = LUATelemetry::Provider();
    if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x200000000000LL) )
    {
      v7 = *(const unsigned __int16 **)(FailureInfo + 112);
      v8 = *(const wchar_t **)(FailureInfo + 120);
      v32[0] = 0;
      v24 = v7;
      CurrentThreadId = *(_DWORD *)(FailureInfo + 104);
      v25 = *(const wchar_t **)(FailureInfo + 96);
      v26 = *(const unsigned __int16 **)(FailureInfo + 88);
      v34 = *(_DWORD *)(FailureInfo + 80);
      v27 = *(const unsigned __int16 **)(FailureInfo + 72);
      LODWORD(v35) = *(_DWORD *)(FailureInfo + 32);
      v28 = *(const wchar_t **)(FailureInfo + 24);
      v20 = *(_DWORD *)FailureInfo;
      v29 = *(const unsigned __int16 **)(FailureInfo + 128);
      v21 = *(_DWORD *)(FailureInfo + 64);
      v30 = *(const unsigned __int16 **)(FailureInfo + 56);
      LODWORD(v7) = *(_DWORD *)(FailureInfo + 8);
      v23 = v8;
      v22 = (int)v7;
      v31 = 0x1000000;
      v9 = (const GUID *)wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
                           this,
                           v4,
                           v5,
                           v6);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v10,
        byte_180051A3D,
        v9,
        v10,
        (__int64)v32,
        (__int64)&v31,
        (__int64)&v22,
        &v30,
        (__int64)&v21,
        &v29,
        (__int64)&v20,
        &v28,
        (__int64)&v35,
        &v27,
        (__int64)&v34,
        &v26,
        &v25,
        (__int64)&CurrentThreadId,
        &v24,
        &v23);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v11 = LUATelemetry::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      Result = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(this);
      v35 = 0;
      v34 = Result;
      v18 = (const GUID *)wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
                            v15,
                            v14,
                            v16,
                            v17);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        byte_18005315C,
        v18,
        v19,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&CurrentThreadId);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180037870  push    rbp
0x180037872  push    rbx
0x180037873  push    rdi
0x180037874  lea     rbp, [rsp-47h]
0x180037879  sub     rsp, 100h
0x180037880  mov     rbx, rcx
0x180037883  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x180037888  mov     rdi, rax
0x18003788b  mov     rcx, rbx
0x18003788e  test    rax, rax
0x180037891  jz      loc_1800379F2
0x180037897  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003789c  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x1800378a1  mov     r9, rax
0x1800378a4  cmp     dword ptr [rax], 5
0x1800378a7  jbe     loc_180037A6B
0x1800378ad  mov     rdx, 200000000000h
0x1800378b7  mov     rcx, rax
0x1800378ba  call    _tlgKeywordOn
0x1800378bf  test    al, al
0x1800378c1  jz      loc_180037A6B
0x1800378c7  mov     rax, [rdi+70h]
0x1800378cb  mov     rcx, [rdi+78h]
0x1800378cf  and     [rbp+57h+var_18], 0
0x1800378d4  mov     [rbp+57h+var_58], rax
0x1800378d8  mov     eax, [rdi+68h]
0x1800378db  mov     [rbp+57h+arg_8], eax
0x1800378de  mov     rax, [rdi+60h]
0x1800378e2  mov     [rbp+57h+var_50], rax
0x1800378e6  mov     rax, [rdi+58h]
0x1800378ea  mov     [rbp+57h+var_48], rax
0x1800378ee  mov     eax, [rdi+50h]
0x1800378f1  mov     [rbp+57h+arg_10], eax
0x1800378f4  mov     rax, [rdi+48h]
0x1800378f8  mov     [rbp+57h+var_40], rax
0x1800378fc  mov     eax, [rdi+20h]
0x1800378ff  mov     dword ptr [rbp+57h+arg_18], eax
0x180037902  mov     rax, [rdi+18h]
0x180037906  mov     [rbp+57h+var_38], rax
0x18003790a  mov     eax, [rdi]
0x18003790c  mov     [rbp+57h+var_70], eax
0x18003790f  mov     rax, [rdi+80h]
0x180037916  mov     [rbp+57h+var_30], rax
0x18003791a  mov     eax, [rdi+40h]
0x18003791d  mov     [rbp+57h+var_6C], eax
0x180037920  mov     rax, [rdi+38h]
0x180037924  mov     [rbp+57h+var_28], rax
0x180037928  mov     eax, [rdi+8]
0x18003792b  mov     [rbp+57h+var_60], rcx
0x18003792f  mov     rcx, rbx
0x180037932  mov     [rbp+57h+var_68], eax
0x180037935  mov     [rbp+57h+var_20], 1000000h
0x18003793d  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180037942  lea     rcx, [rbp+57h+var_60]
0x180037946  mov     r8, rax
0x180037949  mov     [rsp+110h+var_78], rcx
0x180037951  lea     rdx, byte_180051A3D
0x180037958  lea     rcx, [rbp+57h+var_58]
0x18003795c  mov     [rsp+110h+var_80], rcx
0x180037964  lea     rcx, [rbp+57h+arg_8]
0x180037968  mov     [rsp+110h+var_88], rcx
0x180037970  lea     rcx, [rbp+57h+var_50]
0x180037974  mov     [rsp+110h+var_90], rcx
0x18003797c  lea     rcx, [rbp+57h+var_48]
0x180037980  mov     [rsp+110h+var_98], rcx
0x180037985  lea     rcx, [rbp+57h+arg_10]
0x180037989  mov     [rsp+110h+var_A0], rcx
0x18003798e  lea     rcx, [rbp+57h+var_40]
0x180037992  mov     [rsp+110h+var_A8], rcx
0x180037997  lea     rcx, [rbp+57h+arg_18]
0x18003799b  mov     [rsp+110h+var_B0], rcx
0x1800379a0  lea     rcx, [rbp+57h+var_38]
0x1800379a4  mov     [rsp+110h+var_B8], rcx
0x1800379a9  lea     rcx, [rbp+57h+var_70]
0x1800379ad  mov     [rsp+110h+var_C0], rcx
0x1800379b2  lea     rcx, [rbp+57h+var_30]
0x1800379b6  mov     [rsp+110h+var_C8], rcx
0x1800379bb  lea     rcx, [rbp+57h+var_6C]
0x1800379bf  mov     [rsp+110h+var_D0], rcx
0x1800379c4  lea     rcx, [rbp+57h+var_28]
0x1800379c8  mov     [rsp+110h+var_D8], rcx
0x1800379cd  lea     rcx, [rbp+57h+var_68]
0x1800379d1  mov     [rsp+110h+var_E0], rcx
0x1800379d6  lea     rcx, [rbp+57h+var_20]
0x1800379da  mov     [rsp+110h+var_E8], rcx
0x1800379df  lea     rcx, [rbp+57h+var_18]
0x1800379e3  mov     [rsp+110h+var_F0], rcx
0x1800379e8  mov     rcx, r9
0x1800379eb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800379f0  jmp     short loc_180037A6B
0x1800379f2  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800379f7  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x1800379fc  mov     rdi, rax
0x1800379ff  cmp     dword ptr [rax], 5
0x180037a02  jbe     short loc_180037A6B
0x180037a04  mov     rdx, 200000000000h
0x180037a0e  mov     rcx, rax
0x180037a11  call    _tlgKeywordOn
0x180037a16  test    al, al
0x180037a18  jz      short loc_180037A6B
0x180037a1a  call    cs:__imp_GetCurrentThreadId
0x180037a21  nop     dword ptr [rax+rax+00h]
0x180037a26  mov     rcx, rbx
0x180037a29  mov     [rbp+57h+arg_8], eax
0x180037a2c  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x180037a31  and     [rbp+57h+arg_18], 0
0x180037a36  mov     [rbp+57h+arg_10], eax
0x180037a39  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180037a3e  lea     rcx, [rbp+57h+arg_8]
0x180037a42  mov     r8, rax
0x180037a45  mov     [rsp+110h+var_E0], rcx
0x180037a4a  lea     rdx, byte_18005315C
0x180037a51  lea     rcx, [rbp+57h+arg_10]
0x180037a55  mov     [rsp+110h+var_E8], rcx
0x180037a5a  lea     rcx, [rbp+57h+arg_18]
0x180037a5e  mov     [rsp+110h+var_F0], rcx
0x180037a63  mov     rcx, rdi
0x180037a66  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180037a6b  mov     rcx, rbx
0x180037a6e  add     rsp, 100h
0x180037a75  pop     rdi
0x180037a76  pop     rbx
0x180037a77  pop     rbp
0x180037a78  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
