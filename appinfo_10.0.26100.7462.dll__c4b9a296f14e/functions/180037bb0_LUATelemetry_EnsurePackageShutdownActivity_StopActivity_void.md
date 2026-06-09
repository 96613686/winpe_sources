# LUATelemetry::EnsurePackageShutdownActivity::StopActivity(void)

- ea: `0x180037bb0`
- end: `0x180037dbd`
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
- `0x180033cdc`
- `0x180033ecc`
- `0x180037bb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037d5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037d5a`

## pseudocode

```c
void __fastcall LUATelemetry::EnsurePackageShutdownActivity::StopActivity(
        LUATelemetry::EnsurePackageShutdownActivity *this)
{
  __int64 FailureInfo; // rdi
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  const struct _tlgProvider_t *v6; // r9
  const unsigned __int16 *v7; // rax
  const wchar_t *v8; // rcx
  const GUID *v9; // rax
  __int64 v10; // r9
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  int Result; // eax
  __int64 v14; // rcx
  const GUID *v15; // rax
  __int64 v16; // r9
  int v17; // [rsp+A0h] [rbp-19h] BYREF
  int v18; // [rsp+A4h] [rbp-15h] BYREF
  int v19; // [rsp+A8h] [rbp-11h] BYREF
  const wchar_t *v20; // [rsp+B0h] [rbp-9h] BYREF
  const unsigned __int16 *v21; // [rsp+B8h] [rbp-1h] BYREF
  const wchar_t *v22; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v23; // [rsp+C8h] [rbp+Fh] BYREF
  const unsigned __int16 *v24; // [rsp+D0h] [rbp+17h] BYREF
  const wchar_t *v25; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v26; // [rsp+E0h] [rbp+27h] BYREF
  const unsigned __int16 *v27; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v28; // [rsp+F0h] [rbp+37h] BYREF
  _QWORD v29[3]; // [rsp+F8h] [rbp+3Fh] BYREF
  DWORD CurrentThreadId; // [rsp+128h] [rbp+6Fh] BYREF
  int v31; // [rsp+130h] [rbp+77h] BYREF
  __int64 v32; // [rsp+138h] [rbp+7Fh] BYREF

  FailureInfo = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo();
  if ( FailureInfo )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v3 = LUATelemetry::Provider();
    v6 = v3;
    if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x200000000000LL) )
    {
      v7 = *(const unsigned __int16 **)(FailureInfo + 112);
      v8 = *(const wchar_t **)(FailureInfo + 120);
      v29[0] = 0;
      v21 = v7;
      CurrentThreadId = *(_DWORD *)(FailureInfo + 104);
      v22 = *(const wchar_t **)(FailureInfo + 96);
      v23 = *(const unsigned __int16 **)(FailureInfo + 88);
      v31 = *(_DWORD *)(FailureInfo + 80);
      v24 = *(const unsigned __int16 **)(FailureInfo + 72);
      LODWORD(v32) = *(_DWORD *)(FailureInfo + 32);
      v25 = *(const wchar_t **)(FailureInfo + 24);
      v17 = *(_DWORD *)FailureInfo;
      v26 = *(const unsigned __int16 **)(FailureInfo + 128);
      v18 = *(_DWORD *)(FailureInfo + 64);
      v27 = *(const unsigned __int16 **)(FailureInfo + 56);
      LODWORD(v7) = *(_DWORD *)(FailureInfo + 8);
      v20 = v8;
      v19 = (int)v7;
      v28 = 0x1000000;
      v9 = (const GUID *)wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(this);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v10,
        byte_180052AAA,
        v9,
        v10,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v19,
        &v27,
        (__int64)&v18,
        &v26,
        (__int64)&v17,
        &v25,
        (__int64)&v32,
        &v24,
        (__int64)&v31,
        &v23,
        &v22,
        (__int64)&CurrentThreadId,
        &v21,
        &v20);
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
      v32 = 0;
      v31 = Result;
      v15 = (const GUID *)wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(v14);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        byte_1800541C9,
        v15,
        v16,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&CurrentThreadId);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v4,
    v5,
    v6);
}

```

## disassembly

```asm
0x180037bb0  push    rbp
0x180037bb2  push    rbx
0x180037bb3  push    rdi
0x180037bb4  lea     rbp, [rsp-47h]
0x180037bb9  sub     rsp, 100h
0x180037bc0  mov     rbx, rcx
0x180037bc3  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x180037bc8  mov     rdi, rax
0x180037bcb  mov     rcx, rbx
0x180037bce  test    rax, rax
0x180037bd1  jz      loc_180037D32
0x180037bd7  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180037bdc  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180037be1  mov     r9, rax
0x180037be4  cmp     dword ptr [rax], 5
0x180037be7  jbe     loc_180037DAB
0x180037bed  mov     rdx, 200000000000h
0x180037bf7  mov     rcx, rax
0x180037bfa  call    _tlgKeywordOn
0x180037bff  test    al, al
0x180037c01  jz      loc_180037DAB
0x180037c07  mov     rax, [rdi+70h]
0x180037c0b  mov     rcx, [rdi+78h]
0x180037c0f  and     [rbp+57h+var_18], 0
0x180037c14  mov     [rbp+57h+var_58], rax
0x180037c18  mov     eax, [rdi+68h]
0x180037c1b  mov     [rbp+57h+arg_8], eax
0x180037c1e  mov     rax, [rdi+60h]
0x180037c22  mov     [rbp+57h+var_50], rax
0x180037c26  mov     rax, [rdi+58h]
0x180037c2a  mov     [rbp+57h+var_48], rax
0x180037c2e  mov     eax, [rdi+50h]
0x180037c31  mov     [rbp+57h+arg_10], eax
0x180037c34  mov     rax, [rdi+48h]
0x180037c38  mov     [rbp+57h+var_40], rax
0x180037c3c  mov     eax, [rdi+20h]
0x180037c3f  mov     dword ptr [rbp+57h+arg_18], eax
0x180037c42  mov     rax, [rdi+18h]
0x180037c46  mov     [rbp+57h+var_38], rax
0x180037c4a  mov     eax, [rdi]
0x180037c4c  mov     [rbp+57h+var_70], eax
0x180037c4f  mov     rax, [rdi+80h]
0x180037c56  mov     [rbp+57h+var_30], rax
0x180037c5a  mov     eax, [rdi+40h]
0x180037c5d  mov     [rbp+57h+var_6C], eax
0x180037c60  mov     rax, [rdi+38h]
0x180037c64  mov     [rbp+57h+var_28], rax
0x180037c68  mov     eax, [rdi+8]
0x180037c6b  mov     [rbp+57h+var_60], rcx
0x180037c6f  mov     rcx, rbx
0x180037c72  mov     [rbp+57h+var_68], eax
0x180037c75  mov     [rbp+57h+var_20], 1000000h
0x180037c7d  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180037c82  lea     rcx, [rbp+57h+var_60]
0x180037c86  mov     r8, rax
0x180037c89  mov     [rsp+110h+var_78], rcx
0x180037c91  lea     rdx, byte_180052AAA
0x180037c98  lea     rcx, [rbp+57h+var_58]
0x180037c9c  mov     [rsp+110h+var_80], rcx
0x180037ca4  lea     rcx, [rbp+57h+arg_8]
0x180037ca8  mov     [rsp+110h+var_88], rcx
0x180037cb0  lea     rcx, [rbp+57h+var_50]
0x180037cb4  mov     [rsp+110h+var_90], rcx
0x180037cbc  lea     rcx, [rbp+57h+var_48]
0x180037cc0  mov     [rsp+110h+var_98], rcx
0x180037cc5  lea     rcx, [rbp+57h+arg_10]
0x180037cc9  mov     [rsp+110h+var_A0], rcx
0x180037cce  lea     rcx, [rbp+57h+var_40]
0x180037cd2  mov     [rsp+110h+var_A8], rcx
0x180037cd7  lea     rcx, [rbp+57h+arg_18]
0x180037cdb  mov     [rsp+110h+var_B0], rcx
0x180037ce0  lea     rcx, [rbp+57h+var_38]
0x180037ce4  mov     [rsp+110h+var_B8], rcx
0x180037ce9  lea     rcx, [rbp+57h+var_70]
0x180037ced  mov     [rsp+110h+var_C0], rcx
0x180037cf2  lea     rcx, [rbp+57h+var_30]
0x180037cf6  mov     [rsp+110h+var_C8], rcx
0x180037cfb  lea     rcx, [rbp+57h+var_6C]
0x180037cff  mov     [rsp+110h+var_D0], rcx
0x180037d04  lea     rcx, [rbp+57h+var_28]
0x180037d08  mov     [rsp+110h+var_D8], rcx
0x180037d0d  lea     rcx, [rbp+57h+var_68]
0x180037d11  mov     [rsp+110h+var_E0], rcx
0x180037d16  lea     rcx, [rbp+57h+var_20]
0x180037d1a  mov     [rsp+110h+var_E8], rcx
0x180037d1f  lea     rcx, [rbp+57h+var_18]
0x180037d23  mov     [rsp+110h+var_F0], rcx
0x180037d28  mov     rcx, r9
0x180037d2b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180037d30  jmp     short loc_180037DAB
0x180037d32  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180037d37  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180037d3c  mov     rdi, rax
0x180037d3f  cmp     dword ptr [rax], 5
0x180037d42  jbe     short loc_180037DAB
0x180037d44  mov     rdx, 200000000000h
0x180037d4e  mov     rcx, rax
0x180037d51  call    _tlgKeywordOn
0x180037d56  test    al, al
0x180037d58  jz      short loc_180037DAB
0x180037d5a  call    cs:__imp_GetCurrentThreadId
0x180037d61  nop     dword ptr [rax+rax+00h]
0x180037d66  mov     rcx, rbx
0x180037d69  mov     [rbp+57h+arg_8], eax
0x180037d6c  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x180037d71  and     [rbp+57h+arg_18], 0
0x180037d76  mov     [rbp+57h+arg_10], eax
0x180037d79  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180037d7e  lea     rcx, [rbp+57h+arg_8]
0x180037d82  mov     r8, rax
0x180037d85  mov     [rsp+110h+var_E0], rcx
0x180037d8a  lea     rdx, byte_1800541C9
0x180037d91  lea     rcx, [rbp+57h+arg_10]
0x180037d95  mov     [rsp+110h+var_E8], rcx
0x180037d9a  lea     rcx, [rbp+57h+arg_18]
0x180037d9e  mov     [rsp+110h+var_F0], rcx
0x180037da3  mov     rcx, rdi
0x180037da6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180037dab  mov     rcx, rbx
0x180037dae  add     rsp, 100h
0x180037db5  pop     rdi
0x180037db6  pop     rbx
0x180037db7  pop     rbp
0x180037db8  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
