# LUATelemetry::EnsurePackageShutdownActivity::Stop(ushort const *,ulong)

- ea: `0x1800370f4`
- end: `0x18003735d`
- name: `?Stop@EnsurePackageShutdownActivity@LUATelemetry@@QEAAXPEBGK@Z`
- size: `617`
- prototype: `void __fastcall(LUATelemetry::EnsurePackageShutdownActivity *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18002cf84`

## callees

- `0x180002534`
- `0x18000cb30`
- `0x18001058c`
- `0x180018d70`
- `0x180018da8`
- `0x180018dcc`
- `0x18001fd6c`
- `0x180033a1c`
- `0x180033c0c`
- `0x1800370f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800372db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800372db`

## pseudocode

```c
void __fastcall LUATelemetry::EnsurePackageShutdownActivity::Stop(
        LUATelemetry::EnsurePackageShutdownActivity *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 FailureInfo; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rax
  int v12; // eax
  int v13; // r9d
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  const GUID *v20; // rax
  __int64 v21; // r9
  int Result; // [rsp+B0h] [rbp-80h] BYREF
  DWORD CurrentThreadId; // [rsp+B4h] [rbp-7Ch] BYREF
  int v24; // [rsp+B8h] [rbp-78h] BYREF
  int v25; // [rsp+BCh] [rbp-74h] BYREF
  int v26; // [rsp+C0h] [rbp-70h] BYREF
  int v27; // [rsp+C4h] [rbp-6Ch] BYREF
  __int64 v28; // [rsp+C8h] [rbp-68h] BYREF
  const wchar_t *v29; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v30; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v31; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v32; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v33; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v34; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v35; // [rsp+100h] [rbp-30h] BYREF
  __int64 v36; // [rsp+108h] [rbp-28h] BYREF
  __int64 v37; // [rsp+110h] [rbp-20h] BYREF
  __int64 v38; // [rsp+118h] [rbp-18h] BYREF
  int v39; // [rsp+158h] [rbp+28h] BYREF

  FailureInfo = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo();
  if ( FailureInfo )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v7 = LUATelemetry::Provider();
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL) )
    {
      v11 = *(_QWORD *)(FailureInfo + 120);
      v29 = 0;
      v31 = v11;
      v32 = *(_QWORD *)(FailureInfo + 112);
      v24 = *(_DWORD *)(FailureInfo + 104);
      v33 = *(_QWORD *)(FailureInfo + 96);
      v34 = *(_QWORD *)(FailureInfo + 88);
      v25 = *(_DWORD *)(FailureInfo + 80);
      v35 = *(_QWORD *)(FailureInfo + 72);
      v26 = *(_DWORD *)(FailureInfo + 32);
      v36 = *(_QWORD *)(FailureInfo + 24);
      v27 = *(_DWORD *)FailureInfo;
      v37 = *(_QWORD *)(FailureInfo + 128);
      Result = *(_DWORD *)(FailureInfo + 64);
      v38 = *(_QWORD *)(FailureInfo + 56);
      CurrentThreadId = *(_DWORD *)(FailureInfo + 8);
      v39 = a3;
      v30 = a2;
      v28 = 0x1000000;
      v12 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
              this,
              v8,
              v9,
              v10);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)&unk_1800531BA,
        v12,
        v13,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&CurrentThreadId,
        (__int64)&v38,
        (__int64)&Result,
        (__int64)&v37,
        (__int64)&v27,
        (__int64)&v36,
        (__int64)&v26,
        (__int64)&v35,
        (__int64)&v25,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v24,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v39);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v14 = LUATelemetry::Provider();
    v15 = (__int64)v14;
    if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 0x200000000000LL) )
    {
      v39 = a3;
      v29 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v28 = 0;
      Result = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(this);
      v20 = (const GUID *)wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
                            v17,
                            v16,
                            v18,
                            v19);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v15,
        byte_180052AFA,
        v20,
        v21,
        (__int64)&v28,
        (__int64)&Result,
        (__int64)&CurrentThreadId,
        &v29,
        (__int64)&v39);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x1800370f4  mov     [rsp-8+arg_0], rbx
0x1800370f9  mov     [rsp-8+arg_8], rsi
0x1800370fe  push    rbp
0x1800370ff  push    rdi
0x180037100  push    r14
0x180037102  lea     rbp, [rsp+10h]
0x180037107  sub     rsp, 120h
0x18003710e  mov     esi, r8d
0x180037111  mov     r14, rdx
0x180037114  mov     rbx, rcx
0x180037117  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x18003711c  mov     rdi, rax
0x18003711f  mov     rcx, rbx
0x180037122  test    rax, rax
0x180037125  jz      loc_1800372A8
0x18003712b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180037130  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180037135  mov     r9, rax
0x180037138  cmp     dword ptr [rax], 5
0x18003713b  jbe     loc_18003733E
0x180037141  mov     rdx, 200000000000h
0x18003714b  mov     rcx, rax
0x18003714e  call    _tlgKeywordOn
0x180037153  test    al, al
0x180037155  jz      loc_18003733E
0x18003715b  mov     rax, [rdi+78h]
0x18003715f  mov     rcx, rbx
0x180037162  and     [rbp+var_60], 0
0x180037167  mov     [rbp+var_50], rax
0x18003716b  mov     rax, [rdi+70h]
0x18003716f  mov     [rbp+var_48], rax
0x180037173  mov     eax, [rdi+68h]
0x180037176  mov     [rbp+var_78], eax
0x180037179  mov     rax, [rdi+60h]
0x18003717d  mov     [rbp+var_40], rax
0x180037181  mov     rax, [rdi+58h]
0x180037185  mov     [rbp+var_38], rax
0x180037189  mov     eax, [rdi+50h]
0x18003718c  mov     [rbp+var_74], eax
0x18003718f  mov     rax, [rdi+48h]
0x180037193  mov     [rbp+var_30], rax
0x180037197  mov     eax, [rdi+20h]
0x18003719a  mov     [rbp+var_70], eax
0x18003719d  mov     rax, [rdi+18h]
0x1800371a1  mov     [rbp+var_28], rax
0x1800371a5  mov     eax, [rdi]
0x1800371a7  mov     [rbp+var_6C], eax
0x1800371aa  mov     rax, [rdi+80h]
0x1800371b1  mov     [rbp+var_20], rax
0x1800371b5  mov     eax, [rdi+40h]
0x1800371b8  mov     [rbp+var_80], eax
0x1800371bb  mov     rax, [rdi+38h]
0x1800371bf  mov     [rbp+var_18], rax
0x1800371c3  mov     eax, [rdi+8]
0x1800371c6  mov     [rbp+var_7C], eax
0x1800371c9  mov     [rbp+arg_18], esi
0x1800371cc  mov     [rbp+var_58], r14
0x1800371d0  mov     [rbp+var_68], 1000000h
0x1800371d8  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x1800371dd  lea     rcx, [rbp+arg_18]
0x1800371e1  mov     r8, rax
0x1800371e4  mov     [rsp+130h+var_88], rcx
0x1800371ec  lea     rdx, unk_1800531BA
0x1800371f3  lea     rcx, [rbp+var_58]
0x1800371f7  mov     [rsp+130h+var_90], rcx
0x1800371ff  lea     rcx, [rbp+var_50]
0x180037203  mov     [rsp+130h+var_98], rcx
0x18003720b  lea     rcx, [rbp+var_48]
0x18003720f  mov     [rsp+130h+var_A0], rcx
0x180037217  lea     rcx, [rbp+var_78]
0x18003721b  mov     [rsp+130h+var_A8], rcx
0x180037223  lea     rcx, [rbp+var_40]
0x180037227  mov     [rsp+130h+var_B0], rcx
0x18003722f  lea     rcx, [rbp+var_38]
0x180037233  mov     [rsp+130h+var_B8], rcx
0x180037238  lea     rcx, [rbp+var_74]
0x18003723c  mov     [rsp+130h+var_C0], rcx
0x180037241  lea     rcx, [rbp+var_30]
0x180037245  mov     [rsp+130h+var_C8], rcx
0x18003724a  lea     rcx, [rbp+var_70]
0x18003724e  mov     [rsp+130h+var_D0], rcx
0x180037253  lea     rcx, [rbp+var_28]
0x180037257  mov     [rsp+130h+var_D8], rcx
0x18003725c  lea     rcx, [rbp+var_6C]
0x180037260  mov     [rsp+130h+var_E0], rcx
0x180037265  lea     rcx, [rbp+var_20]
0x180037269  mov     [rsp+130h+var_E8], rcx
0x18003726e  lea     rcx, [rbp+var_80]
0x180037272  mov     [rsp+130h+var_F0], rcx
0x180037277  lea     rcx, [rbp+var_18]
0x18003727b  mov     [rsp+130h+var_F8], rcx
0x180037280  lea     rcx, [rbp+var_7C]
0x180037284  mov     [rsp+130h+var_100], rcx
0x180037289  lea     rcx, [rbp+var_68]
0x18003728d  mov     [rsp+130h+var_108], rcx
0x180037292  lea     rcx, [rbp+var_60]
0x180037296  mov     [rsp+130h+var_110], rcx
0x18003729b  mov     rcx, r9
0x18003729e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645664@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800372a3  jmp     loc_18003733E
0x1800372a8  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800372ad  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x1800372b2  mov     rdi, rax
0x1800372b5  cmp     dword ptr [rax], 5
0x1800372b8  jbe     loc_18003733E
0x1800372be  mov     rdx, 200000000000h
0x1800372c8  mov     rcx, rax
0x1800372cb  call    _tlgKeywordOn
0x1800372d0  test    al, al
0x1800372d2  jz      short loc_18003733E
0x1800372d4  mov     [rbp+arg_18], esi
0x1800372d7  mov     [rbp+var_60], r14
0x1800372db  call    cs:__imp_GetCurrentThreadId
0x1800372e2  nop     dword ptr [rax+rax+00h]
0x1800372e7  mov     rcx, rbx
0x1800372ea  mov     [rbp+var_7C], eax
0x1800372ed  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x1800372f2  and     [rbp+var_68], 0
0x1800372f7  mov     [rbp+var_80], eax
0x1800372fa  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x1800372ff  lea     rcx, [rbp+arg_18]
0x180037303  mov     r8, rax
0x180037306  mov     [rsp+130h+var_F0], rcx
0x18003730b  lea     rdx, byte_180052AFA
0x180037312  lea     rcx, [rbp+var_60]
0x180037316  mov     [rsp+130h+var_F8], rcx
0x18003731b  lea     rcx, [rbp+var_7C]
0x18003731f  mov     [rsp+130h+var_100], rcx
0x180037324  lea     rcx, [rbp+var_80]
0x180037328  mov     [rsp+130h+var_108], rcx
0x18003732d  lea     rcx, [rbp+var_68]
0x180037331  mov     [rsp+130h+var_110], rcx
0x180037336  mov     rcx, rdi
0x180037339  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003733e  mov     rcx, rbx
0x180037341  lea     r11, [rsp+130h+var_10]
0x180037349  mov     rbx, [r11+20h]
0x18003734d  mov     rsi, [r11+28h]
0x180037351  mov     rsp, r11
0x180037354  pop     r14
0x180037356  pop     rdi
0x180037357  pop     rbp
0x180037358  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
