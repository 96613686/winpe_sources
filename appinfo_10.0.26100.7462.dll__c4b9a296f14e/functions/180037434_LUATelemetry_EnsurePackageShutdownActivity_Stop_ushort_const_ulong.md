# LUATelemetry::EnsurePackageShutdownActivity::Stop(ushort const *,ulong)

- ea: `0x180037434`
- end: `0x18003769d`
- name: `?Stop@EnsurePackageShutdownActivity@LUATelemetry@@QEAAXPEBGK@Z`
- size: `617`
- prototype: `void __fastcall(LUATelemetry::EnsurePackageShutdownActivity *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18002d054`

## callees

- `0x180002534`
- `0x18000cb30`
- `0x18001058c`
- `0x180018d70`
- `0x180018da8`
- `0x180018dcc`
- `0x18001fd6c`
- `0x180033cdc`
- `0x180033ecc`
- `0x180037434`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003761b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003761b`

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
  const struct _tlgProvider_t *v10; // r9
  __int64 v11; // rax
  int v12; // eax
  int v13; // r9d
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdi
  __int64 v16; // rcx
  const GUID *v17; // rax
  __int64 v18; // r9
  int Result; // [rsp+B0h] [rbp-80h] BYREF
  DWORD CurrentThreadId; // [rsp+B4h] [rbp-7Ch] BYREF
  int v21; // [rsp+B8h] [rbp-78h] BYREF
  int v22; // [rsp+BCh] [rbp-74h] BYREF
  int v23; // [rsp+C0h] [rbp-70h] BYREF
  int v24; // [rsp+C4h] [rbp-6Ch] BYREF
  __int64 v25; // [rsp+C8h] [rbp-68h] BYREF
  const wchar_t *v26; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v27; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v28; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v29; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v30; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v31; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v32; // [rsp+100h] [rbp-30h] BYREF
  __int64 v33; // [rsp+108h] [rbp-28h] BYREF
  __int64 v34; // [rsp+110h] [rbp-20h] BYREF
  __int64 v35; // [rsp+118h] [rbp-18h] BYREF
  int v36; // [rsp+158h] [rbp+28h] BYREF

  FailureInfo = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo();
  if ( FailureInfo )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v7 = LUATelemetry::Provider();
    v10 = v7;
    if ( *(_DWORD *)v7 > 5u && (unsigned __int8)tlgKeywordOn(v7, 0x200000000000LL) )
    {
      v11 = *(_QWORD *)(FailureInfo + 120);
      v26 = 0;
      v28 = v11;
      v29 = *(_QWORD *)(FailureInfo + 112);
      v21 = *(_DWORD *)(FailureInfo + 104);
      v30 = *(_QWORD *)(FailureInfo + 96);
      v31 = *(_QWORD *)(FailureInfo + 88);
      v22 = *(_DWORD *)(FailureInfo + 80);
      v32 = *(_QWORD *)(FailureInfo + 72);
      v23 = *(_DWORD *)(FailureInfo + 32);
      v33 = *(_QWORD *)(FailureInfo + 24);
      v24 = *(_DWORD *)FailureInfo;
      v34 = *(_QWORD *)(FailureInfo + 128);
      Result = *(_DWORD *)(FailureInfo + 64);
      v35 = *(_QWORD *)(FailureInfo + 56);
      CurrentThreadId = *(_DWORD *)(FailureInfo + 8);
      v36 = a3;
      v27 = a2;
      v25 = 0x1000000;
      v12 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(this);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)&unk_180054227,
        v12,
        v13,
        (__int64)&v26,
        (__int64)&v25,
        (__int64)&CurrentThreadId,
        (__int64)&v35,
        (__int64)&Result,
        (__int64)&v34,
        (__int64)&v24,
        (__int64)&v33,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v21,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v36);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v14 = LUATelemetry::Provider();
    v15 = (__int64)v14;
    if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 0x200000000000LL) )
    {
      v36 = a3;
      v26 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v25 = 0;
      Result = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(this);
      v17 = (const GUID *)wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(v16);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v15,
        byte_180053B67,
        v17,
        v18,
        (__int64)&v25,
        (__int64)&Result,
        (__int64)&CurrentThreadId,
        &v26,
        (__int64)&v36);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v8,
    v9,
    v10);
}

```

## disassembly

```asm
0x180037434  mov     [rsp-8+arg_0], rbx
0x180037439  mov     [rsp-8+arg_8], rsi
0x18003743e  push    rbp
0x18003743f  push    rdi
0x180037440  push    r14
0x180037442  lea     rbp, [rsp+10h]
0x180037447  sub     rsp, 120h
0x18003744e  mov     esi, r8d
0x180037451  mov     r14, rdx
0x180037454  mov     rbx, rcx
0x180037457  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x18003745c  mov     rdi, rax
0x18003745f  mov     rcx, rbx
0x180037462  test    rax, rax
0x180037465  jz      loc_1800375E8
0x18003746b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180037470  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180037475  mov     r9, rax
0x180037478  cmp     dword ptr [rax], 5
0x18003747b  jbe     loc_18003767E
0x180037481  mov     rdx, 200000000000h
0x18003748b  mov     rcx, rax
0x18003748e  call    _tlgKeywordOn
0x180037493  test    al, al
0x180037495  jz      loc_18003767E
0x18003749b  mov     rax, [rdi+78h]
0x18003749f  mov     rcx, rbx
0x1800374a2  and     [rbp+var_60], 0
0x1800374a7  mov     [rbp+var_50], rax
0x1800374ab  mov     rax, [rdi+70h]
0x1800374af  mov     [rbp+var_48], rax
0x1800374b3  mov     eax, [rdi+68h]
0x1800374b6  mov     [rbp+var_78], eax
0x1800374b9  mov     rax, [rdi+60h]
0x1800374bd  mov     [rbp+var_40], rax
0x1800374c1  mov     rax, [rdi+58h]
0x1800374c5  mov     [rbp+var_38], rax
0x1800374c9  mov     eax, [rdi+50h]
0x1800374cc  mov     [rbp+var_74], eax
0x1800374cf  mov     rax, [rdi+48h]
0x1800374d3  mov     [rbp+var_30], rax
0x1800374d7  mov     eax, [rdi+20h]
0x1800374da  mov     [rbp+var_70], eax
0x1800374dd  mov     rax, [rdi+18h]
0x1800374e1  mov     [rbp+var_28], rax
0x1800374e5  mov     eax, [rdi]
0x1800374e7  mov     [rbp+var_6C], eax
0x1800374ea  mov     rax, [rdi+80h]
0x1800374f1  mov     [rbp+var_20], rax
0x1800374f5  mov     eax, [rdi+40h]
0x1800374f8  mov     [rbp+var_80], eax
0x1800374fb  mov     rax, [rdi+38h]
0x1800374ff  mov     [rbp+var_18], rax
0x180037503  mov     eax, [rdi+8]
0x180037506  mov     [rbp+var_7C], eax
0x180037509  mov     [rbp+arg_18], esi
0x18003750c  mov     [rbp+var_58], r14
0x180037510  mov     [rbp+var_68], 1000000h
0x180037518  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18003751d  lea     rcx, [rbp+arg_18]
0x180037521  mov     r8, rax
0x180037524  mov     [rsp+130h+var_88], rcx
0x18003752c  lea     rdx, unk_180054227
0x180037533  lea     rcx, [rbp+var_58]
0x180037537  mov     [rsp+130h+var_90], rcx
0x18003753f  lea     rcx, [rbp+var_50]
0x180037543  mov     [rsp+130h+var_98], rcx
0x18003754b  lea     rcx, [rbp+var_48]
0x18003754f  mov     [rsp+130h+var_A0], rcx
0x180037557  lea     rcx, [rbp+var_78]
0x18003755b  mov     [rsp+130h+var_A8], rcx
0x180037563  lea     rcx, [rbp+var_40]
0x180037567  mov     [rsp+130h+var_B0], rcx
0x18003756f  lea     rcx, [rbp+var_38]
0x180037573  mov     [rsp+130h+var_B8], rcx
0x180037578  lea     rcx, [rbp+var_74]
0x18003757c  mov     [rsp+130h+var_C0], rcx
0x180037581  lea     rcx, [rbp+var_30]
0x180037585  mov     [rsp+130h+var_C8], rcx
0x18003758a  lea     rcx, [rbp+var_70]
0x18003758e  mov     [rsp+130h+var_D0], rcx
0x180037593  lea     rcx, [rbp+var_28]
0x180037597  mov     [rsp+130h+var_D8], rcx
0x18003759c  lea     rcx, [rbp+var_6C]
0x1800375a0  mov     [rsp+130h+var_E0], rcx
0x1800375a5  lea     rcx, [rbp+var_20]
0x1800375a9  mov     [rsp+130h+var_E8], rcx
0x1800375ae  lea     rcx, [rbp+var_80]
0x1800375b2  mov     [rsp+130h+var_F0], rcx
0x1800375b7  lea     rcx, [rbp+var_18]
0x1800375bb  mov     [rsp+130h+var_F8], rcx
0x1800375c0  lea     rcx, [rbp+var_7C]
0x1800375c4  mov     [rsp+130h+var_100], rcx
0x1800375c9  lea     rcx, [rbp+var_68]
0x1800375cd  mov     [rsp+130h+var_108], rcx
0x1800375d2  lea     rcx, [rbp+var_60]
0x1800375d6  mov     [rsp+130h+var_110], rcx
0x1800375db  mov     rcx, r9
0x1800375de  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645664@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800375e3  jmp     loc_18003767E
0x1800375e8  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800375ed  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x1800375f2  mov     rdi, rax
0x1800375f5  cmp     dword ptr [rax], 5
0x1800375f8  jbe     loc_18003767E
0x1800375fe  mov     rdx, 200000000000h
0x180037608  mov     rcx, rax
0x18003760b  call    _tlgKeywordOn
0x180037610  test    al, al
0x180037612  jz      short loc_18003767E
0x180037614  mov     [rbp+arg_18], esi
0x180037617  mov     [rbp+var_60], r14
0x18003761b  call    cs:__imp_GetCurrentThreadId
0x180037622  nop     dword ptr [rax+rax+00h]
0x180037627  mov     rcx, rbx
0x18003762a  mov     [rbp+var_7C], eax
0x18003762d  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x180037632  and     [rbp+var_68], 0
0x180037637  mov     [rbp+var_80], eax
0x18003763a  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18003763f  lea     rcx, [rbp+arg_18]
0x180037643  mov     r8, rax
0x180037646  mov     [rsp+130h+var_F0], rcx
0x18003764b  lea     rdx, byte_180053B67
0x180037652  lea     rcx, [rbp+var_60]
0x180037656  mov     [rsp+130h+var_F8], rcx
0x18003765b  lea     rcx, [rbp+var_7C]
0x18003765f  mov     [rsp+130h+var_100], rcx
0x180037664  lea     rcx, [rbp+var_80]
0x180037668  mov     [rsp+130h+var_108], rcx
0x18003766d  lea     rcx, [rbp+var_68]
0x180037671  mov     [rsp+130h+var_110], rcx
0x180037676  mov     rcx, rdi
0x180037679  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18003767e  mov     rcx, rbx
0x180037681  lea     r11, [rsp+130h+var_10]
0x180037689  mov     rbx, [r11+20h]
0x18003768d  mov     rsi, [r11+28h]
0x180037691  mov     rsp, r11
0x180037694  pop     r14
0x180037696  pop     rdi
0x180037697  pop     rbp
0x180037698  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
