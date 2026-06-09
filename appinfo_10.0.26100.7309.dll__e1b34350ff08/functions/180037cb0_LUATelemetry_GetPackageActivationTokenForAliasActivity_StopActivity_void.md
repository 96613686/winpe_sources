# LUATelemetry::GetPackageActivationTokenForAliasActivity::StopActivity(void)

- ea: `0x180037cb0`
- end: `0x180037ebd`
- name: `?StopActivity@GetPackageActivationTokenForAliasActivity@LUATelemetry@@MEAAXXZ`
- size: `525`
- prototype: `void __fastcall(LUATelemetry::GetPackageActivationTokenForAliasActivity *__hidden this)`
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
- `0x180037cb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037e5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037e5a`

## pseudocode

```c
void __fastcall LUATelemetry::GetPackageActivationTokenForAliasActivity::StopActivity(
        LUATelemetry::GetPackageActivationTokenForAliasActivity *this)
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
  int v12; // edi
  int Result; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  int v18; // eax
  int v19; // r9d
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
        byte_180051098,
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
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      Result = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(this);
      v35 = 0;
      v34 = Result;
      v18 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
              v15,
              v14,
              v16,
              v17);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)&unk_180052DA3,
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
0x180037cb0  push    rbp
0x180037cb2  push    rbx
0x180037cb3  push    rdi
0x180037cb4  lea     rbp, [rsp-47h]
0x180037cb9  sub     rsp, 100h
0x180037cc0  mov     rbx, rcx
0x180037cc3  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x180037cc8  mov     rdi, rax
0x180037ccb  mov     rcx, rbx
0x180037cce  test    rax, rax
0x180037cd1  jz      loc_180037E32
0x180037cd7  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180037cdc  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180037ce1  mov     r9, rax
0x180037ce4  cmp     dword ptr [rax], 5
0x180037ce7  jbe     loc_180037EAB
0x180037ced  mov     rdx, 200000000000h
0x180037cf7  mov     rcx, rax
0x180037cfa  call    _tlgKeywordOn
0x180037cff  test    al, al
0x180037d01  jz      loc_180037EAB
0x180037d07  mov     rax, [rdi+70h]
0x180037d0b  mov     rcx, [rdi+78h]
0x180037d0f  and     [rbp+57h+var_18], 0
0x180037d14  mov     [rbp+57h+var_58], rax
0x180037d18  mov     eax, [rdi+68h]
0x180037d1b  mov     [rbp+57h+arg_8], eax
0x180037d1e  mov     rax, [rdi+60h]
0x180037d22  mov     [rbp+57h+var_50], rax
0x180037d26  mov     rax, [rdi+58h]
0x180037d2a  mov     [rbp+57h+var_48], rax
0x180037d2e  mov     eax, [rdi+50h]
0x180037d31  mov     [rbp+57h+arg_10], eax
0x180037d34  mov     rax, [rdi+48h]
0x180037d38  mov     [rbp+57h+var_40], rax
0x180037d3c  mov     eax, [rdi+20h]
0x180037d3f  mov     dword ptr [rbp+57h+arg_18], eax
0x180037d42  mov     rax, [rdi+18h]
0x180037d46  mov     [rbp+57h+var_38], rax
0x180037d4a  mov     eax, [rdi]
0x180037d4c  mov     [rbp+57h+var_70], eax
0x180037d4f  mov     rax, [rdi+80h]
0x180037d56  mov     [rbp+57h+var_30], rax
0x180037d5a  mov     eax, [rdi+40h]
0x180037d5d  mov     [rbp+57h+var_6C], eax
0x180037d60  mov     rax, [rdi+38h]
0x180037d64  mov     [rbp+57h+var_28], rax
0x180037d68  mov     eax, [rdi+8]
0x180037d6b  mov     [rbp+57h+var_60], rcx
0x180037d6f  mov     rcx, rbx
0x180037d72  mov     [rbp+57h+var_68], eax
0x180037d75  mov     [rbp+57h+var_20], 1000000h
0x180037d7d  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180037d82  lea     rcx, [rbp+57h+var_60]
0x180037d86  mov     r8, rax
0x180037d89  mov     [rsp+110h+var_78], rcx
0x180037d91  lea     rdx, byte_180051098
0x180037d98  lea     rcx, [rbp+57h+var_58]
0x180037d9c  mov     [rsp+110h+var_80], rcx
0x180037da4  lea     rcx, [rbp+57h+arg_8]
0x180037da8  mov     [rsp+110h+var_88], rcx
0x180037db0  lea     rcx, [rbp+57h+var_50]
0x180037db4  mov     [rsp+110h+var_90], rcx
0x180037dbc  lea     rcx, [rbp+57h+var_48]
0x180037dc0  mov     [rsp+110h+var_98], rcx
0x180037dc5  lea     rcx, [rbp+57h+arg_10]
0x180037dc9  mov     [rsp+110h+var_A0], rcx
0x180037dce  lea     rcx, [rbp+57h+var_40]
0x180037dd2  mov     [rsp+110h+var_A8], rcx
0x180037dd7  lea     rcx, [rbp+57h+arg_18]
0x180037ddb  mov     [rsp+110h+var_B0], rcx
0x180037de0  lea     rcx, [rbp+57h+var_38]
0x180037de4  mov     [rsp+110h+var_B8], rcx
0x180037de9  lea     rcx, [rbp+57h+var_70]
0x180037ded  mov     [rsp+110h+var_C0], rcx
0x180037df2  lea     rcx, [rbp+57h+var_30]
0x180037df6  mov     [rsp+110h+var_C8], rcx
0x180037dfb  lea     rcx, [rbp+57h+var_6C]
0x180037dff  mov     [rsp+110h+var_D0], rcx
0x180037e04  lea     rcx, [rbp+57h+var_28]
0x180037e08  mov     [rsp+110h+var_D8], rcx
0x180037e0d  lea     rcx, [rbp+57h+var_68]
0x180037e11  mov     [rsp+110h+var_E0], rcx
0x180037e16  lea     rcx, [rbp+57h+var_20]
0x180037e1a  mov     [rsp+110h+var_E8], rcx
0x180037e1f  lea     rcx, [rbp+57h+var_18]
0x180037e23  mov     [rsp+110h+var_F0], rcx
0x180037e28  mov     rcx, r9
0x180037e2b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180037e30  jmp     short loc_180037EAB
0x180037e32  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180037e37  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180037e3c  mov     rdi, rax
0x180037e3f  cmp     dword ptr [rax], 5
0x180037e42  jbe     short loc_180037EAB
0x180037e44  mov     rdx, 200000000000h
0x180037e4e  mov     rcx, rax
0x180037e51  call    _tlgKeywordOn
0x180037e56  test    al, al
0x180037e58  jz      short loc_180037EAB
0x180037e5a  call    cs:__imp_GetCurrentThreadId
0x180037e61  nop     dword ptr [rax+rax+00h]
0x180037e66  mov     rcx, rbx
0x180037e69  mov     [rbp+57h+arg_8], eax
0x180037e6c  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x180037e71  and     [rbp+57h+arg_18], 0
0x180037e76  mov     [rbp+57h+arg_10], eax
0x180037e79  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180037e7e  lea     rcx, [rbp+57h+arg_8]
0x180037e82  mov     r8, rax
0x180037e85  mov     [rsp+110h+var_E0], rcx
0x180037e8a  lea     rdx, unk_180052DA3
0x180037e91  lea     rcx, [rbp+57h+arg_10]
0x180037e95  mov     [rsp+110h+var_E8], rcx
0x180037e9a  lea     rcx, [rbp+57h+arg_18]
0x180037e9e  mov     [rsp+110h+var_F0], rcx
0x180037ea3  mov     rcx, rdi
0x180037ea6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180037eab  mov     rcx, rbx
0x180037eae  add     rsp, 100h
0x180037eb5  pop     rdi
0x180037eb6  pop     rbx
0x180037eb7  pop     rbp
0x180037eb8  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
