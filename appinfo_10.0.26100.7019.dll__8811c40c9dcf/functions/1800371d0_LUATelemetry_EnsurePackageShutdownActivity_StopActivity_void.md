# LUATelemetry::EnsurePackageShutdownActivity::StopActivity(void)

- ea: `0x1800371d0`
- end: `0x1800373dd`
- name: `?StopActivity@EnsurePackageShutdownActivity@LUATelemetry@@MEAAXXZ`
- size: `525`
- prototype: `void __fastcall(LUATelemetry::EnsurePackageShutdownActivity *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x18000c7d0`
- `0x18000cb30`
- `0x180010e4c`
- `0x180018ac0`
- `0x180018af8`
- `0x180018b1c`
- `0x180020fe0`
- `0x18003396c`
- `0x180033b5c`
- `0x1800371d0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003737a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003737a`

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
        byte_180050722,
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
        byte_18004FB75,
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
0x1800371d0  push    rbp
0x1800371d2  push    rbx
0x1800371d3  push    rdi
0x1800371d4  lea     rbp, [rsp-47h]
0x1800371d9  sub     rsp, 100h
0x1800371e0  mov     rbx, rcx
0x1800371e3  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x1800371e8  mov     rdi, rax
0x1800371eb  mov     rcx, rbx
0x1800371ee  test    rax, rax
0x1800371f1  jz      loc_180037352
0x1800371f7  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800371fc  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180037201  mov     r9, rax
0x180037204  cmp     dword ptr [rax], 5
0x180037207  jbe     loc_1800373CB
0x18003720d  mov     rdx, 200000000000h
0x180037217  mov     rcx, rax
0x18003721a  call    _tlgKeywordOn
0x18003721f  test    al, al
0x180037221  jz      loc_1800373CB
0x180037227  mov     rax, [rdi+70h]
0x18003722b  mov     rcx, [rdi+78h]
0x18003722f  and     [rbp+57h+var_18], 0
0x180037234  mov     [rbp+57h+var_58], rax
0x180037238  mov     eax, [rdi+68h]
0x18003723b  mov     [rbp+57h+arg_8], eax
0x18003723e  mov     rax, [rdi+60h]
0x180037242  mov     [rbp+57h+var_50], rax
0x180037246  mov     rax, [rdi+58h]
0x18003724a  mov     [rbp+57h+var_48], rax
0x18003724e  mov     eax, [rdi+50h]
0x180037251  mov     [rbp+57h+arg_10], eax
0x180037254  mov     rax, [rdi+48h]
0x180037258  mov     [rbp+57h+var_40], rax
0x18003725c  mov     eax, [rdi+20h]
0x18003725f  mov     dword ptr [rbp+57h+arg_18], eax
0x180037262  mov     rax, [rdi+18h]
0x180037266  mov     [rbp+57h+var_38], rax
0x18003726a  mov     eax, [rdi]
0x18003726c  mov     [rbp+57h+var_70], eax
0x18003726f  mov     rax, [rdi+80h]
0x180037276  mov     [rbp+57h+var_30], rax
0x18003727a  mov     eax, [rdi+40h]
0x18003727d  mov     [rbp+57h+var_6C], eax
0x180037280  mov     rax, [rdi+38h]
0x180037284  mov     [rbp+57h+var_28], rax
0x180037288  mov     eax, [rdi+8]
0x18003728b  mov     [rbp+57h+var_60], rcx
0x18003728f  mov     rcx, rbx
0x180037292  mov     [rbp+57h+var_68], eax
0x180037295  mov     [rbp+57h+var_20], 1000000h
0x18003729d  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x1800372a2  lea     rcx, [rbp+57h+var_60]
0x1800372a6  mov     r8, rax
0x1800372a9  mov     [rsp+110h+var_78], rcx
0x1800372b1  lea     rdx, byte_180050722
0x1800372b8  lea     rcx, [rbp+57h+var_58]
0x1800372bc  mov     [rsp+110h+var_80], rcx
0x1800372c4  lea     rcx, [rbp+57h+arg_8]
0x1800372c8  mov     [rsp+110h+var_88], rcx
0x1800372d0  lea     rcx, [rbp+57h+var_50]
0x1800372d4  mov     [rsp+110h+var_90], rcx
0x1800372dc  lea     rcx, [rbp+57h+var_48]
0x1800372e0  mov     [rsp+110h+var_98], rcx
0x1800372e5  lea     rcx, [rbp+57h+arg_10]
0x1800372e9  mov     [rsp+110h+var_A0], rcx
0x1800372ee  lea     rcx, [rbp+57h+var_40]
0x1800372f2  mov     [rsp+110h+var_A8], rcx
0x1800372f7  lea     rcx, [rbp+57h+arg_18]
0x1800372fb  mov     [rsp+110h+var_B0], rcx
0x180037300  lea     rcx, [rbp+57h+var_38]
0x180037304  mov     [rsp+110h+var_B8], rcx
0x180037309  lea     rcx, [rbp+57h+var_70]
0x18003730d  mov     [rsp+110h+var_C0], rcx
0x180037312  lea     rcx, [rbp+57h+var_30]
0x180037316  mov     [rsp+110h+var_C8], rcx
0x18003731b  lea     rcx, [rbp+57h+var_6C]
0x18003731f  mov     [rsp+110h+var_D0], rcx
0x180037324  lea     rcx, [rbp+57h+var_28]
0x180037328  mov     [rsp+110h+var_D8], rcx
0x18003732d  lea     rcx, [rbp+57h+var_68]
0x180037331  mov     [rsp+110h+var_E0], rcx
0x180037336  lea     rcx, [rbp+57h+var_20]
0x18003733a  mov     [rsp+110h+var_E8], rcx
0x18003733f  lea     rcx, [rbp+57h+var_18]
0x180037343  mov     [rsp+110h+var_F0], rcx
0x180037348  mov     rcx, r9
0x18003734b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180037350  jmp     short loc_1800373CB
0x180037352  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180037357  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18003735c  mov     rdi, rax
0x18003735f  cmp     dword ptr [rax], 5
0x180037362  jbe     short loc_1800373CB
0x180037364  mov     rdx, 200000000000h
0x18003736e  mov     rcx, rax
0x180037371  call    _tlgKeywordOn
0x180037376  test    al, al
0x180037378  jz      short loc_1800373CB
0x18003737a  call    cs:__imp_GetCurrentThreadId
0x180037381  nop     dword ptr [rax+rax+00h]
0x180037386  mov     rcx, rbx
0x180037389  mov     [rbp+57h+arg_8], eax
0x18003738c  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x180037391  and     [rbp+57h+arg_18], 0
0x180037396  mov     [rbp+57h+arg_10], eax
0x180037399  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18003739e  lea     rcx, [rbp+57h+arg_8]
0x1800373a2  mov     r8, rax
0x1800373a5  mov     [rsp+110h+var_E0], rcx
0x1800373aa  lea     rdx, byte_18004FB75
0x1800373b1  lea     rcx, [rbp+57h+arg_10]
0x1800373b5  mov     [rsp+110h+var_E8], rcx
0x1800373ba  lea     rcx, [rbp+57h+arg_18]
0x1800373be  mov     [rsp+110h+var_F0], rcx
0x1800373c3  mov     rcx, rdi
0x1800373c6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800373cb  mov     rcx, rbx
0x1800373ce  add     rsp, 100h
0x1800373d5  pop     rdi
0x1800373d6  pop     rbx
0x1800373d7  pop     rbp
0x1800373d8  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
