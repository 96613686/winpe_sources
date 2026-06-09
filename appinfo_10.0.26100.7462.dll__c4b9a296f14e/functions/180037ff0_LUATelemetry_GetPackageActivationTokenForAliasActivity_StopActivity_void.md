# LUATelemetry::GetPackageActivationTokenForAliasActivity::StopActivity(void)

- ea: `0x180037ff0`
- end: `0x1800381fd`
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
- `0x180033cdc`
- `0x180033ecc`
- `0x180037ff0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003819a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003819a`

## pseudocode

```c
void __fastcall LUATelemetry::GetPackageActivationTokenForAliasActivity::StopActivity(
        LUATelemetry::GetPackageActivationTokenForAliasActivity *this)
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
  int v12; // edi
  int Result; // eax
  __int64 v14; // rcx
  int v15; // eax
  int v16; // r9d
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
        byte_180052105,
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
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      Result = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(this);
      v32 = 0;
      v31 = Result;
      v15 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(v14);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)&unk_180053E10,
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
0x180037ff0  push    rbp
0x180037ff2  push    rbx
0x180037ff3  push    rdi
0x180037ff4  lea     rbp, [rsp-47h]
0x180037ff9  sub     rsp, 100h
0x180038000  mov     rbx, rcx
0x180038003  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x180038008  mov     rdi, rax
0x18003800b  mov     rcx, rbx
0x18003800e  test    rax, rax
0x180038011  jz      loc_180038172
0x180038017  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003801c  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180038021  mov     r9, rax
0x180038024  cmp     dword ptr [rax], 5
0x180038027  jbe     loc_1800381EB
0x18003802d  mov     rdx, 200000000000h
0x180038037  mov     rcx, rax
0x18003803a  call    _tlgKeywordOn
0x18003803f  test    al, al
0x180038041  jz      loc_1800381EB
0x180038047  mov     rax, [rdi+70h]
0x18003804b  mov     rcx, [rdi+78h]
0x18003804f  and     [rbp+57h+var_18], 0
0x180038054  mov     [rbp+57h+var_58], rax
0x180038058  mov     eax, [rdi+68h]
0x18003805b  mov     [rbp+57h+arg_8], eax
0x18003805e  mov     rax, [rdi+60h]
0x180038062  mov     [rbp+57h+var_50], rax
0x180038066  mov     rax, [rdi+58h]
0x18003806a  mov     [rbp+57h+var_48], rax
0x18003806e  mov     eax, [rdi+50h]
0x180038071  mov     [rbp+57h+arg_10], eax
0x180038074  mov     rax, [rdi+48h]
0x180038078  mov     [rbp+57h+var_40], rax
0x18003807c  mov     eax, [rdi+20h]
0x18003807f  mov     dword ptr [rbp+57h+arg_18], eax
0x180038082  mov     rax, [rdi+18h]
0x180038086  mov     [rbp+57h+var_38], rax
0x18003808a  mov     eax, [rdi]
0x18003808c  mov     [rbp+57h+var_70], eax
0x18003808f  mov     rax, [rdi+80h]
0x180038096  mov     [rbp+57h+var_30], rax
0x18003809a  mov     eax, [rdi+40h]
0x18003809d  mov     [rbp+57h+var_6C], eax
0x1800380a0  mov     rax, [rdi+38h]
0x1800380a4  mov     [rbp+57h+var_28], rax
0x1800380a8  mov     eax, [rdi+8]
0x1800380ab  mov     [rbp+57h+var_60], rcx
0x1800380af  mov     rcx, rbx
0x1800380b2  mov     [rbp+57h+var_68], eax
0x1800380b5  mov     [rbp+57h+var_20], 1000000h
0x1800380bd  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x1800380c2  lea     rcx, [rbp+57h+var_60]
0x1800380c6  mov     r8, rax
0x1800380c9  mov     [rsp+110h+var_78], rcx
0x1800380d1  lea     rdx, byte_180052105
0x1800380d8  lea     rcx, [rbp+57h+var_58]
0x1800380dc  mov     [rsp+110h+var_80], rcx
0x1800380e4  lea     rcx, [rbp+57h+arg_8]
0x1800380e8  mov     [rsp+110h+var_88], rcx
0x1800380f0  lea     rcx, [rbp+57h+var_50]
0x1800380f4  mov     [rsp+110h+var_90], rcx
0x1800380fc  lea     rcx, [rbp+57h+var_48]
0x180038100  mov     [rsp+110h+var_98], rcx
0x180038105  lea     rcx, [rbp+57h+arg_10]
0x180038109  mov     [rsp+110h+var_A0], rcx
0x18003810e  lea     rcx, [rbp+57h+var_40]
0x180038112  mov     [rsp+110h+var_A8], rcx
0x180038117  lea     rcx, [rbp+57h+arg_18]
0x18003811b  mov     [rsp+110h+var_B0], rcx
0x180038120  lea     rcx, [rbp+57h+var_38]
0x180038124  mov     [rsp+110h+var_B8], rcx
0x180038129  lea     rcx, [rbp+57h+var_70]
0x18003812d  mov     [rsp+110h+var_C0], rcx
0x180038132  lea     rcx, [rbp+57h+var_30]
0x180038136  mov     [rsp+110h+var_C8], rcx
0x18003813b  lea     rcx, [rbp+57h+var_6C]
0x18003813f  mov     [rsp+110h+var_D0], rcx
0x180038144  lea     rcx, [rbp+57h+var_28]
0x180038148  mov     [rsp+110h+var_D8], rcx
0x18003814d  lea     rcx, [rbp+57h+var_68]
0x180038151  mov     [rsp+110h+var_E0], rcx
0x180038156  lea     rcx, [rbp+57h+var_20]
0x18003815a  mov     [rsp+110h+var_E8], rcx
0x18003815f  lea     rcx, [rbp+57h+var_18]
0x180038163  mov     [rsp+110h+var_F0], rcx
0x180038168  mov     rcx, r9
0x18003816b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180038170  jmp     short loc_1800381EB
0x180038172  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180038177  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18003817c  mov     rdi, rax
0x18003817f  cmp     dword ptr [rax], 5
0x180038182  jbe     short loc_1800381EB
0x180038184  mov     rdx, 200000000000h
0x18003818e  mov     rcx, rax
0x180038191  call    _tlgKeywordOn
0x180038196  test    al, al
0x180038198  jz      short loc_1800381EB
0x18003819a  call    cs:__imp_GetCurrentThreadId
0x1800381a1  nop     dword ptr [rax+rax+00h]
0x1800381a6  mov     rcx, rbx
0x1800381a9  mov     [rbp+57h+arg_8], eax
0x1800381ac  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x1800381b1  and     [rbp+57h+arg_18], 0
0x1800381b6  mov     [rbp+57h+arg_10], eax
0x1800381b9  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x1800381be  lea     rcx, [rbp+57h+arg_8]
0x1800381c2  mov     r8, rax
0x1800381c5  mov     [rsp+110h+var_E0], rcx
0x1800381ca  lea     rdx, unk_180053E10
0x1800381d1  lea     rcx, [rbp+57h+arg_10]
0x1800381d5  mov     [rsp+110h+var_E8], rcx
0x1800381da  lea     rcx, [rbp+57h+arg_18]
0x1800381de  mov     [rsp+110h+var_F0], rcx
0x1800381e3  mov     rcx, rdi
0x1800381e6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800381eb  mov     rcx, rbx
0x1800381ee  add     rsp, 100h
0x1800381f5  pop     rdi
0x1800381f6  pop     rbx
0x1800381f7  pop     rbp
0x1800381f8  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
