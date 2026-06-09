# LUATelemetry::GetPackageActivationTokenForFilePath::StopActivity(void)

- ea: `0x180038210`
- end: `0x18003841d`
- name: `?StopActivity@GetPackageActivationTokenForFilePath@LUATelemetry@@MEAAXXZ`
- size: `525`
- prototype: `void __fastcall(LUATelemetry::GetPackageActivationTokenForFilePath *__hidden this)`
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
- `0x180038210`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800383ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800383ba`

## pseudocode

```c
void __fastcall LUATelemetry::GetPackageActivationTokenForFilePath::StopActivity(
        LUATelemetry::GetPackageActivationTokenForFilePath *this)
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
        byte_180052BDF,
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
        (unsigned int)&unk_180052337,
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
0x180038210  push    rbp
0x180038212  push    rbx
0x180038213  push    rdi
0x180038214  lea     rbp, [rsp-47h]
0x180038219  sub     rsp, 100h
0x180038220  mov     rbx, rcx
0x180038223  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x180038228  mov     rdi, rax
0x18003822b  mov     rcx, rbx
0x18003822e  test    rax, rax
0x180038231  jz      loc_180038392
0x180038237  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003823c  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180038241  mov     r9, rax
0x180038244  cmp     dword ptr [rax], 5
0x180038247  jbe     loc_18003840B
0x18003824d  mov     rdx, 200000000000h
0x180038257  mov     rcx, rax
0x18003825a  call    _tlgKeywordOn
0x18003825f  test    al, al
0x180038261  jz      loc_18003840B
0x180038267  mov     rax, [rdi+70h]
0x18003826b  mov     rcx, [rdi+78h]
0x18003826f  and     [rbp+57h+var_18], 0
0x180038274  mov     [rbp+57h+var_58], rax
0x180038278  mov     eax, [rdi+68h]
0x18003827b  mov     [rbp+57h+arg_8], eax
0x18003827e  mov     rax, [rdi+60h]
0x180038282  mov     [rbp+57h+var_50], rax
0x180038286  mov     rax, [rdi+58h]
0x18003828a  mov     [rbp+57h+var_48], rax
0x18003828e  mov     eax, [rdi+50h]
0x180038291  mov     [rbp+57h+arg_10], eax
0x180038294  mov     rax, [rdi+48h]
0x180038298  mov     [rbp+57h+var_40], rax
0x18003829c  mov     eax, [rdi+20h]
0x18003829f  mov     dword ptr [rbp+57h+arg_18], eax
0x1800382a2  mov     rax, [rdi+18h]
0x1800382a6  mov     [rbp+57h+var_38], rax
0x1800382aa  mov     eax, [rdi]
0x1800382ac  mov     [rbp+57h+var_70], eax
0x1800382af  mov     rax, [rdi+80h]
0x1800382b6  mov     [rbp+57h+var_30], rax
0x1800382ba  mov     eax, [rdi+40h]
0x1800382bd  mov     [rbp+57h+var_6C], eax
0x1800382c0  mov     rax, [rdi+38h]
0x1800382c4  mov     [rbp+57h+var_28], rax
0x1800382c8  mov     eax, [rdi+8]
0x1800382cb  mov     [rbp+57h+var_60], rcx
0x1800382cf  mov     rcx, rbx
0x1800382d2  mov     [rbp+57h+var_68], eax
0x1800382d5  mov     [rbp+57h+var_20], 1000000h
0x1800382dd  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x1800382e2  lea     rcx, [rbp+57h+var_60]
0x1800382e6  mov     r8, rax
0x1800382e9  mov     [rsp+110h+var_78], rcx
0x1800382f1  lea     rdx, byte_180052BDF
0x1800382f8  lea     rcx, [rbp+57h+var_58]
0x1800382fc  mov     [rsp+110h+var_80], rcx
0x180038304  lea     rcx, [rbp+57h+arg_8]
0x180038308  mov     [rsp+110h+var_88], rcx
0x180038310  lea     rcx, [rbp+57h+var_50]
0x180038314  mov     [rsp+110h+var_90], rcx
0x18003831c  lea     rcx, [rbp+57h+var_48]
0x180038320  mov     [rsp+110h+var_98], rcx
0x180038325  lea     rcx, [rbp+57h+arg_10]
0x180038329  mov     [rsp+110h+var_A0], rcx
0x18003832e  lea     rcx, [rbp+57h+var_40]
0x180038332  mov     [rsp+110h+var_A8], rcx
0x180038337  lea     rcx, [rbp+57h+arg_18]
0x18003833b  mov     [rsp+110h+var_B0], rcx
0x180038340  lea     rcx, [rbp+57h+var_38]
0x180038344  mov     [rsp+110h+var_B8], rcx
0x180038349  lea     rcx, [rbp+57h+var_70]
0x18003834d  mov     [rsp+110h+var_C0], rcx
0x180038352  lea     rcx, [rbp+57h+var_30]
0x180038356  mov     [rsp+110h+var_C8], rcx
0x18003835b  lea     rcx, [rbp+57h+var_6C]
0x18003835f  mov     [rsp+110h+var_D0], rcx
0x180038364  lea     rcx, [rbp+57h+var_28]
0x180038368  mov     [rsp+110h+var_D8], rcx
0x18003836d  lea     rcx, [rbp+57h+var_68]
0x180038371  mov     [rsp+110h+var_E0], rcx
0x180038376  lea     rcx, [rbp+57h+var_20]
0x18003837a  mov     [rsp+110h+var_E8], rcx
0x18003837f  lea     rcx, [rbp+57h+var_18]
0x180038383  mov     [rsp+110h+var_F0], rcx
0x180038388  mov     rcx, r9
0x18003838b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180038390  jmp     short loc_18003840B
0x180038392  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180038397  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18003839c  mov     rdi, rax
0x18003839f  cmp     dword ptr [rax], 5
0x1800383a2  jbe     short loc_18003840B
0x1800383a4  mov     rdx, 200000000000h
0x1800383ae  mov     rcx, rax
0x1800383b1  call    _tlgKeywordOn
0x1800383b6  test    al, al
0x1800383b8  jz      short loc_18003840B
0x1800383ba  call    cs:__imp_GetCurrentThreadId
0x1800383c1  nop     dword ptr [rax+rax+00h]
0x1800383c6  mov     rcx, rbx
0x1800383c9  mov     [rbp+57h+arg_8], eax
0x1800383cc  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x1800383d1  and     [rbp+57h+arg_18], 0
0x1800383d6  mov     [rbp+57h+arg_10], eax
0x1800383d9  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x1800383de  lea     rcx, [rbp+57h+arg_8]
0x1800383e2  mov     r8, rax
0x1800383e5  mov     [rsp+110h+var_E0], rcx
0x1800383ea  lea     rdx, unk_180052337
0x1800383f1  lea     rcx, [rbp+57h+arg_10]
0x1800383f5  mov     [rsp+110h+var_E8], rcx
0x1800383fa  lea     rcx, [rbp+57h+arg_18]
0x1800383fe  mov     [rsp+110h+var_F0], rcx
0x180038403  mov     rcx, rdi
0x180038406  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003840b  mov     rcx, rbx
0x18003840e  add     rsp, 100h
0x180038415  pop     rdi
0x180038416  pop     rbx
0x180038417  pop     rbp
0x180038418  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
