# LUATelemetry::FinishPackageActivationActivity::StopActivity(void)

- ea: `0x180037a90`
- end: `0x180037c9d`
- name: `?StopActivity@FinishPackageActivationActivity@LUATelemetry@@MEAAXXZ`
- size: `525`
- prototype: `void __fastcall(LUATelemetry::FinishPackageActivationActivity *__hidden this)`
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
- `0x180037a90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037c3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037c3a`

## pseudocode

```c
void __fastcall LUATelemetry::FinishPackageActivationActivity::StopActivity(
        LUATelemetry::FinishPackageActivationActivity *this)
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
        byte_180051DC3,
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
        byte_180052B78,
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
0x180037a90  push    rbp
0x180037a92  push    rbx
0x180037a93  push    rdi
0x180037a94  lea     rbp, [rsp-47h]
0x180037a99  sub     rsp, 100h
0x180037aa0  mov     rbx, rcx
0x180037aa3  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x180037aa8  mov     rdi, rax
0x180037aab  mov     rcx, rbx
0x180037aae  test    rax, rax
0x180037ab1  jz      loc_180037C12
0x180037ab7  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180037abc  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180037ac1  mov     r9, rax
0x180037ac4  cmp     dword ptr [rax], 5
0x180037ac7  jbe     loc_180037C8B
0x180037acd  mov     rdx, 200000000000h
0x180037ad7  mov     rcx, rax
0x180037ada  call    _tlgKeywordOn
0x180037adf  test    al, al
0x180037ae1  jz      loc_180037C8B
0x180037ae7  mov     rax, [rdi+70h]
0x180037aeb  mov     rcx, [rdi+78h]
0x180037aef  and     [rbp+57h+var_18], 0
0x180037af4  mov     [rbp+57h+var_58], rax
0x180037af8  mov     eax, [rdi+68h]
0x180037afb  mov     [rbp+57h+arg_8], eax
0x180037afe  mov     rax, [rdi+60h]
0x180037b02  mov     [rbp+57h+var_50], rax
0x180037b06  mov     rax, [rdi+58h]
0x180037b0a  mov     [rbp+57h+var_48], rax
0x180037b0e  mov     eax, [rdi+50h]
0x180037b11  mov     [rbp+57h+arg_10], eax
0x180037b14  mov     rax, [rdi+48h]
0x180037b18  mov     [rbp+57h+var_40], rax
0x180037b1c  mov     eax, [rdi+20h]
0x180037b1f  mov     dword ptr [rbp+57h+arg_18], eax
0x180037b22  mov     rax, [rdi+18h]
0x180037b26  mov     [rbp+57h+var_38], rax
0x180037b2a  mov     eax, [rdi]
0x180037b2c  mov     [rbp+57h+var_70], eax
0x180037b2f  mov     rax, [rdi+80h]
0x180037b36  mov     [rbp+57h+var_30], rax
0x180037b3a  mov     eax, [rdi+40h]
0x180037b3d  mov     [rbp+57h+var_6C], eax
0x180037b40  mov     rax, [rdi+38h]
0x180037b44  mov     [rbp+57h+var_28], rax
0x180037b48  mov     eax, [rdi+8]
0x180037b4b  mov     [rbp+57h+var_60], rcx
0x180037b4f  mov     rcx, rbx
0x180037b52  mov     [rbp+57h+var_68], eax
0x180037b55  mov     [rbp+57h+var_20], 1000000h
0x180037b5d  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180037b62  lea     rcx, [rbp+57h+var_60]
0x180037b66  mov     r8, rax
0x180037b69  mov     [rsp+110h+var_78], rcx
0x180037b71  lea     rdx, byte_180051DC3
0x180037b78  lea     rcx, [rbp+57h+var_58]
0x180037b7c  mov     [rsp+110h+var_80], rcx
0x180037b84  lea     rcx, [rbp+57h+arg_8]
0x180037b88  mov     [rsp+110h+var_88], rcx
0x180037b90  lea     rcx, [rbp+57h+var_50]
0x180037b94  mov     [rsp+110h+var_90], rcx
0x180037b9c  lea     rcx, [rbp+57h+var_48]
0x180037ba0  mov     [rsp+110h+var_98], rcx
0x180037ba5  lea     rcx, [rbp+57h+arg_10]
0x180037ba9  mov     [rsp+110h+var_A0], rcx
0x180037bae  lea     rcx, [rbp+57h+var_40]
0x180037bb2  mov     [rsp+110h+var_A8], rcx
0x180037bb7  lea     rcx, [rbp+57h+arg_18]
0x180037bbb  mov     [rsp+110h+var_B0], rcx
0x180037bc0  lea     rcx, [rbp+57h+var_38]
0x180037bc4  mov     [rsp+110h+var_B8], rcx
0x180037bc9  lea     rcx, [rbp+57h+var_70]
0x180037bcd  mov     [rsp+110h+var_C0], rcx
0x180037bd2  lea     rcx, [rbp+57h+var_30]
0x180037bd6  mov     [rsp+110h+var_C8], rcx
0x180037bdb  lea     rcx, [rbp+57h+var_6C]
0x180037bdf  mov     [rsp+110h+var_D0], rcx
0x180037be4  lea     rcx, [rbp+57h+var_28]
0x180037be8  mov     [rsp+110h+var_D8], rcx
0x180037bed  lea     rcx, [rbp+57h+var_68]
0x180037bf1  mov     [rsp+110h+var_E0], rcx
0x180037bf6  lea     rcx, [rbp+57h+var_20]
0x180037bfa  mov     [rsp+110h+var_E8], rcx
0x180037bff  lea     rcx, [rbp+57h+var_18]
0x180037c03  mov     [rsp+110h+var_F0], rcx
0x180037c08  mov     rcx, r9
0x180037c0b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180037c10  jmp     short loc_180037C8B
0x180037c12  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180037c17  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180037c1c  mov     rdi, rax
0x180037c1f  cmp     dword ptr [rax], 5
0x180037c22  jbe     short loc_180037C8B
0x180037c24  mov     rdx, 200000000000h
0x180037c2e  mov     rcx, rax
0x180037c31  call    _tlgKeywordOn
0x180037c36  test    al, al
0x180037c38  jz      short loc_180037C8B
0x180037c3a  call    cs:__imp_GetCurrentThreadId
0x180037c41  nop     dword ptr [rax+rax+00h]
0x180037c46  mov     rcx, rbx
0x180037c49  mov     [rbp+57h+arg_8], eax
0x180037c4c  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x180037c51  and     [rbp+57h+arg_18], 0
0x180037c56  mov     [rbp+57h+arg_10], eax
0x180037c59  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180037c5e  lea     rcx, [rbp+57h+arg_8]
0x180037c62  mov     r8, rax
0x180037c65  mov     [rsp+110h+var_E0], rcx
0x180037c6a  lea     rdx, byte_180052B78
0x180037c71  lea     rcx, [rbp+57h+arg_10]
0x180037c75  mov     [rsp+110h+var_E8], rcx
0x180037c7a  lea     rcx, [rbp+57h+arg_18]
0x180037c7e  mov     [rsp+110h+var_F0], rcx
0x180037c83  mov     rcx, rdi
0x180037c86  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180037c8b  mov     rcx, rbx
0x180037c8e  add     rsp, 100h
0x180037c95  pop     rdi
0x180037c96  pop     rbx
0x180037c97  pop     rbp
0x180037c98  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
