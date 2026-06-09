# LUATelemetry::GetPackageActivationTokenForAliasActivity::Stop(ushort const *,ushort const *,ushort const *)

- ea: `0x18000f4c0`
- end: `0x18000f75a`
- name: `?Stop@GetPackageActivationTokenForAliasActivity@LUATelemetry@@QEAAXPEBG00@Z`
- size: `666`
- prototype: `void __fastcall(LUATelemetry::GetPackageActivationTokenForAliasActivity *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180027c34`

## callees

- `0x180002b5c`
- `0x18000cb30`
- `0x18000efd8`
- `0x18000f4c0`
- `0x180018d70`
- `0x180018da8`
- `0x180018dcc`
- `0x18001fd6c`
- `0x180033cdc`
- `0x180033ecc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f6c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f6c7`

## pseudocode

```c
void __fastcall LUATelemetry::GetPackageActivationTokenForAliasActivity::Stop(
        LUATelemetry::GetPackageActivationTokenForAliasActivity *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 FailureInfo; // rdi
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // r9
  int v13; // eax
  int v14; // r9d
  const struct _tlgProvider_t *v15; // rax
  const struct _tlgProvider_t *v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // rax
  int Result; // [rsp+C0h] [rbp-80h] BYREF
  DWORD CurrentThreadId; // [rsp+C4h] [rbp-7Ch] BYREF
  int v21; // [rsp+C8h] [rbp-78h] BYREF
  int v22; // [rsp+CCh] [rbp-74h] BYREF
  int v23; // [rsp+D0h] [rbp-70h] BYREF
  int v24; // [rsp+D4h] [rbp-6Ch] BYREF
  __int64 v25; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v26; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v27; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v28; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v29; // [rsp+F8h] [rbp-48h] BYREF
  const unsigned __int16 *v30; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v31; // [rsp+108h] [rbp-38h] BYREF
  __int64 v32; // [rsp+110h] [rbp-30h] BYREF
  __int64 v33; // [rsp+118h] [rbp-28h] BYREF
  __int64 v34; // [rsp+120h] [rbp-20h] BYREF
  __int64 v35; // [rsp+128h] [rbp-18h] BYREF
  __int64 v36; // [rsp+130h] [rbp-10h] BYREF
  __int64 v37; // [rsp+138h] [rbp-8h] BYREF

  FailureInfo = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo();
  if ( FailureInfo )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v9 = LUATelemetry::Provider();
    v12 = v9;
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x200000000000LL) )
    {
      v32 = *(_QWORD *)(FailureInfo + 120);
      v33 = *(_QWORD *)(FailureInfo + 112);
      v21 = *(_DWORD *)(FailureInfo + 104);
      v34 = *(_QWORD *)(FailureInfo + 96);
      v35 = *(_QWORD *)(FailureInfo + 88);
      v22 = *(_DWORD *)(FailureInfo + 80);
      v36 = *(_QWORD *)(FailureInfo + 72);
      v23 = *(_DWORD *)(FailureInfo + 32);
      v37 = *(_QWORD *)(FailureInfo + 24);
      v24 = *(_DWORD *)FailureInfo;
      v25 = *(_QWORD *)(FailureInfo + 128);
      Result = *(_DWORD *)(FailureInfo + 64);
      v26 = *(const unsigned __int16 **)(FailureInfo + 56);
      CurrentThreadId = *(_DWORD *)(FailureInfo + 8);
      v29 = a4;
      v30 = a3;
      v31 = a2;
      v27 = 0x1000000;
      v28 = 0;
      v13 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(this);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v14,
        (unsigned int)&unk_180052519,
        v13,
        v14,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&CurrentThreadId,
        (__int64)&v26,
        (__int64)&Result,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v37,
        (__int64)&v23,
        (__int64)&v36,
        (__int64)&v22,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v21,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v15 = LUATelemetry::Provider();
    v16 = v15;
    if ( *(_DWORD *)v15 > 5u && (unsigned __int8)tlgKeywordOn(v15, 0x200000000000LL) )
    {
      v28 = a4;
      v27 = (__int64)a3;
      v26 = a2;
      CurrentThreadId = GetCurrentThreadId();
      Result = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(this);
      v25 = 0;
      v18 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(v17);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v16,
        &unk_18005278A,
        v18);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v10,
    v11,
    v12);
}

```

## disassembly

```asm
0x18000f4c0  mov     [rsp-18h+arg_0], rbx
0x18000f4c5  mov     [rsp-18h+arg_8], rsi
0x18000f4ca  mov     [rsp-18h+arg_10], rdi
0x18000f4cf  push    rbp
0x18000f4d0  push    r14
0x18000f4d2  push    r15
0x18000f4d4  mov     rbp, rsp
0x18000f4d7  sub     rsp, 140h
0x18000f4de  mov     rsi, r9
0x18000f4e1  mov     r14, r8
0x18000f4e4  mov     r15, rdx
0x18000f4e7  mov     rbx, rcx
0x18000f4ea  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x18000f4ef  mov     rdi, rax
0x18000f4f2  mov     rcx, rbx
0x18000f4f5  test    rax, rax
0x18000f4f8  jz      loc_18000F68F
0x18000f4fe  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f503  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18000f508  mov     r9, rax
0x18000f50b  cmp     dword ptr [rax], 5
0x18000f50e  jbe     loc_18000F736
0x18000f514  mov     rdx, 200000000000h
0x18000f51e  mov     rcx, rax
0x18000f521  call    _tlgKeywordOn
0x18000f526  test    al, al
0x18000f528  jz      loc_18000F736
0x18000f52e  mov     rax, [rdi+78h]
0x18000f532  mov     rcx, rbx
0x18000f535  mov     [rbp+var_30], rax
0x18000f539  mov     rax, [rdi+70h]
0x18000f53d  mov     [rbp+var_28], rax
0x18000f541  mov     eax, [rdi+68h]
0x18000f544  mov     [rbp+var_78], eax
0x18000f547  mov     rax, [rdi+60h]
0x18000f54b  mov     [rbp+var_20], rax
0x18000f54f  mov     rax, [rdi+58h]
0x18000f553  mov     [rbp+var_18], rax
0x18000f557  mov     eax, [rdi+50h]
0x18000f55a  mov     [rbp+var_74], eax
0x18000f55d  mov     rax, [rdi+48h]
0x18000f561  mov     [rbp+var_10], rax
0x18000f565  mov     eax, [rdi+20h]
0x18000f568  mov     [rbp+var_70], eax
0x18000f56b  mov     rax, [rdi+18h]
0x18000f56f  mov     [rbp+var_8], rax
0x18000f573  mov     eax, [rdi]
0x18000f575  mov     [rbp+var_6C], eax
0x18000f578  mov     rax, [rdi+80h]
0x18000f57f  mov     [rbp+var_68], rax
0x18000f583  mov     eax, [rdi+40h]
0x18000f586  mov     [rbp+var_80], eax
0x18000f589  mov     rax, [rdi+38h]
0x18000f58d  mov     [rbp+var_60], rax
0x18000f591  mov     eax, [rdi+8]
0x18000f594  mov     [rbp+var_7C], eax
0x18000f597  mov     [rbp+var_48], rsi
0x18000f59b  mov     [rbp+var_40], r14
0x18000f59f  mov     [rbp+var_38], r15
0x18000f5a3  mov     [rbp+var_58], 1000000h
0x18000f5ab  mov     [rbp+var_50], 0
0x18000f5b3  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000f5b8  lea     rcx, [rbp+var_48]
0x18000f5bc  mov     r8, rax
0x18000f5bf  mov     [rsp+140h+var_90], rcx
0x18000f5c7  lea     rdx, unk_180052519
0x18000f5ce  lea     rcx, [rbp+var_40]
0x18000f5d2  mov     [rsp+140h+var_98], rcx
0x18000f5da  lea     rcx, [rbp+var_38]
0x18000f5de  mov     [rsp+140h+var_A0], rcx
0x18000f5e6  lea     rcx, [rbp+var_30]
0x18000f5ea  mov     [rsp+140h+var_A8], rcx
0x18000f5f2  lea     rcx, [rbp+var_28]
0x18000f5f6  mov     [rsp+140h+var_B0], rcx
0x18000f5fe  lea     rcx, [rbp+var_78]
0x18000f602  mov     [rsp+140h+var_B8], rcx
0x18000f60a  lea     rcx, [rbp+var_20]
0x18000f60e  mov     [rsp+140h+var_C0], rcx
0x18000f616  lea     rcx, [rbp+var_18]
0x18000f61a  mov     [rsp+140h+var_C8], rcx
0x18000f61f  lea     rcx, [rbp+var_74]
0x18000f623  mov     [rsp+140h+var_D0], rcx
0x18000f628  lea     rcx, [rbp+var_10]
0x18000f62c  mov     [rsp+140h+var_D8], rcx
0x18000f631  lea     rcx, [rbp+var_70]
0x18000f635  mov     [rsp+140h+var_E0], rcx
0x18000f63a  lea     rcx, [rbp+var_8]
0x18000f63e  mov     [rsp+140h+var_E8], rcx
0x18000f643  lea     rcx, [rbp+var_6C]
0x18000f647  mov     [rsp+140h+var_F0], rcx
0x18000f64c  lea     rcx, [rbp+var_68]
0x18000f650  mov     [rsp+140h+var_F8], rcx
0x18000f655  lea     rcx, [rbp+var_80]
0x18000f659  mov     [rsp+140h+var_100], rcx
0x18000f65e  lea     rcx, [rbp+var_60]
0x18000f662  mov     [rsp+140h+var_108], rcx
0x18000f667  lea     rcx, [rbp+var_7C]
0x18000f66b  mov     [rsp+140h+var_110], rcx
0x18000f670  lea     rcx, [rbp+var_58]
0x18000f674  mov     [rsp+140h+var_118], rcx
0x18000f679  lea     rcx, [rbp+var_50]
0x18000f67d  mov     [rsp+140h+var_120], rcx
0x18000f682  mov     rcx, r9
0x18000f685  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000f68a  jmp     loc_18000F736
0x18000f68f  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f694  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18000f699  mov     rdi, rax
0x18000f69c  cmp     dword ptr [rax], 5
0x18000f69f  jbe     loc_18000F736
0x18000f6a5  mov     rdx, 200000000000h
0x18000f6af  mov     rcx, rax
0x18000f6b2  call    _tlgKeywordOn
0x18000f6b7  test    al, al
0x18000f6b9  jz      short loc_18000F736
0x18000f6bb  mov     [rbp+var_50], rsi
0x18000f6bf  mov     [rbp+var_58], r14
0x18000f6c3  mov     [rbp+var_60], r15
0x18000f6c7  call    cs:__imp_GetCurrentThreadId
0x18000f6ce  nop     dword ptr [rax+rax+00h]
0x18000f6d3  mov     rcx, rbx
0x18000f6d6  mov     [rbp+var_7C], eax
0x18000f6d9  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x18000f6de  mov     [rbp+var_80], eax
0x18000f6e1  mov     [rbp+var_68], 0
0x18000f6e9  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000f6ee  lea     rcx, [rbp+var_50]
0x18000f6f2  mov     r8, rax
0x18000f6f5  mov     [rsp+140h+var_F8], rcx
0x18000f6fa  lea     rdx, unk_18005278A
0x18000f701  lea     rcx, [rbp+var_58]
0x18000f705  mov     [rsp+140h+var_100], rcx
0x18000f70a  lea     rcx, [rbp+var_60]
0x18000f70e  mov     [rsp+140h+var_108], rcx
0x18000f713  lea     rcx, [rbp+var_7C]
0x18000f717  mov     [rsp+140h+var_110], rcx
0x18000f71c  lea     rcx, [rbp+var_80]
0x18000f720  mov     [rsp+140h+var_118], rcx
0x18000f725  lea     rcx, [rbp+var_68]
0x18000f729  mov     [rsp+140h+var_120], rcx
0x18000f72e  mov     rcx, rdi
0x18000f731  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000f736  mov     rcx, rbx
0x18000f739  lea     r11, [rsp+140h+var_s0]
0x18000f741  mov     rbx, [r11+20h]
0x18000f745  mov     rsi, [r11+28h]
0x18000f749  mov     rdi, [r11+30h]
0x18000f74d  mov     rsp, r11
0x18000f750  pop     r15
0x18000f752  pop     r14
0x18000f754  pop     rbp
0x18000f755  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
