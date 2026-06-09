# LUATelemetry::GetPackageActivationTokenForSxS::Stop(ushort const *,ulong)

- ea: `0x18000f760`
- end: `0x18000f9d6`
- name: `?Stop@GetPackageActivationTokenForSxS@LUATelemetry@@QEAAXPEBGK@Z`
- size: `630`
- prototype: `void __fastcall(LUATelemetry::GetPackageActivationTokenForSxS *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180032ad0`

## callees

- `0x180002534`
- `0x18000cb30`
- `0x18000f760`
- `0x18001058c`
- `0x180018d70`
- `0x180018da8`
- `0x180018dcc`
- `0x18001fd6c`
- `0x180033cdc`
- `0x180033ecc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f951`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f951`

## pseudocode

```c
void __fastcall LUATelemetry::GetPackageActivationTokenForSxS::Stop(
        LUATelemetry::GetPackageActivationTokenForSxS *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 FailureInfo; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // r9
  __int64 v11; // rcx
  DWORD v12; // eax
  int v13; // eax
  int v14; // r9d
  const struct _tlgProvider_t *v15; // rdi
  __int64 v16; // rcx
  int v17; // eax
  int v18; // r9d
  int Result; // [rsp+B0h] [rbp-80h] BYREF
  DWORD CurrentThreadId; // [rsp+B4h] [rbp-7Ch] BYREF
  int v21; // [rsp+B8h] [rbp-78h] BYREF
  int v22; // [rsp+BCh] [rbp-74h] BYREF
  int v23; // [rsp+C0h] [rbp-70h] BYREF
  int v24; // [rsp+C4h] [rbp-6Ch] BYREF
  __int64 v25; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v26; // [rsp+D0h] [rbp-60h] BYREF
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
      v12 = *(_DWORD *)(FailureInfo + 8);
      v28 = v11;
      CurrentThreadId = v12;
      v36 = a3;
      v27 = a2;
      v25 = 0x1000000;
      v26 = 0;
      v13 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(this);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v14,
        (unsigned int)&unk_180053725,
        v13,
        v14,
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
    v15 = LUATelemetry::Provider();
    if ( *(_DWORD *)v15 > 5u
      && (*((_QWORD *)v15 + 2) & 0x200000000000LL) != 0
      && (*((_QWORD *)v15 + 3) & 0x200000000000LL) == *((_QWORD *)v15 + 3) )
    {
      v36 = a3;
      v26 = a2;
      CurrentThreadId = GetCurrentThreadId();
      Result = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(this);
      v25 = 0;
      v17 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(v16);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v15,
        (unsigned int)&unk_180053291,
        v17,
        v18,
        (__int64)&v25,
        (__int64)&Result,
        (__int64)&CurrentThreadId,
        (__int64)&v26,
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
0x18000f760  mov     [rsp-8+arg_0], rbx
0x18000f765  mov     [rsp-8+arg_8], rsi
0x18000f76a  push    rbp
0x18000f76b  push    rdi
0x18000f76c  push    r14
0x18000f76e  lea     rbp, [rsp+10h]
0x18000f773  sub     rsp, 120h
0x18000f77a  mov     esi, r8d
0x18000f77d  mov     r14, rdx
0x18000f780  mov     rbx, rcx
0x18000f783  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x18000f788  mov     rdi, rax
0x18000f78b  mov     rcx, rbx
0x18000f78e  test    rax, rax
0x18000f791  jz      loc_18000F917
0x18000f797  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f79c  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18000f7a1  mov     r9, rax
0x18000f7a4  cmp     dword ptr [rax], 5
0x18000f7a7  jbe     loc_18000F9B7
0x18000f7ad  mov     rdx, 200000000000h
0x18000f7b7  mov     rcx, rax
0x18000f7ba  call    _tlgKeywordOn
0x18000f7bf  test    al, al
0x18000f7c1  jz      loc_18000F9B7
0x18000f7c7  mov     rax, [rdi+70h]
0x18000f7cb  mov     rcx, [rdi+78h]
0x18000f7cf  mov     [rbp+var_48], rax
0x18000f7d3  mov     eax, [rdi+68h]
0x18000f7d6  mov     [rbp+var_78], eax
0x18000f7d9  mov     rax, [rdi+60h]
0x18000f7dd  mov     [rbp+var_40], rax
0x18000f7e1  mov     rax, [rdi+58h]
0x18000f7e5  mov     [rbp+var_38], rax
0x18000f7e9  mov     eax, [rdi+50h]
0x18000f7ec  mov     [rbp+var_74], eax
0x18000f7ef  mov     rax, [rdi+48h]
0x18000f7f3  mov     [rbp+var_30], rax
0x18000f7f7  mov     eax, [rdi+20h]
0x18000f7fa  mov     [rbp+var_70], eax
0x18000f7fd  mov     rax, [rdi+18h]
0x18000f801  mov     [rbp+var_28], rax
0x18000f805  mov     eax, [rdi]
0x18000f807  mov     [rbp+var_6C], eax
0x18000f80a  mov     rax, [rdi+80h]
0x18000f811  mov     [rbp+var_20], rax
0x18000f815  mov     eax, [rdi+40h]
0x18000f818  mov     [rbp+var_80], eax
0x18000f81b  mov     rax, [rdi+38h]
0x18000f81f  mov     [rbp+var_18], rax
0x18000f823  mov     eax, [rdi+8]
0x18000f826  mov     [rbp+var_50], rcx
0x18000f82a  mov     rcx, rbx
0x18000f82d  mov     [rbp+var_7C], eax
0x18000f830  mov     [rbp+arg_18], esi
0x18000f833  mov     [rbp+var_58], r14
0x18000f837  mov     [rbp+var_68], 1000000h
0x18000f83f  mov     [rbp+var_60], 0
0x18000f847  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000f84c  lea     rcx, [rbp+arg_18]
0x18000f850  mov     r8, rax
0x18000f853  mov     [rsp+130h+var_88], rcx
0x18000f85b  lea     rdx, unk_180053725
0x18000f862  lea     rcx, [rbp+var_58]
0x18000f866  mov     [rsp+130h+var_90], rcx
0x18000f86e  lea     rcx, [rbp+var_50]
0x18000f872  mov     [rsp+130h+var_98], rcx
0x18000f87a  lea     rcx, [rbp+var_48]
0x18000f87e  mov     [rsp+130h+var_A0], rcx
0x18000f886  lea     rcx, [rbp+var_78]
0x18000f88a  mov     [rsp+130h+var_A8], rcx
0x18000f892  lea     rcx, [rbp+var_40]
0x18000f896  mov     [rsp+130h+var_B0], rcx
0x18000f89e  lea     rcx, [rbp+var_38]
0x18000f8a2  mov     [rsp+130h+var_B8], rcx
0x18000f8a7  lea     rcx, [rbp+var_74]
0x18000f8ab  mov     [rsp+130h+var_C0], rcx
0x18000f8b0  lea     rcx, [rbp+var_30]
0x18000f8b4  mov     [rsp+130h+var_C8], rcx
0x18000f8b9  lea     rcx, [rbp+var_70]
0x18000f8bd  mov     [rsp+130h+var_D0], rcx
0x18000f8c2  lea     rcx, [rbp+var_28]
0x18000f8c6  mov     [rsp+130h+var_D8], rcx
0x18000f8cb  lea     rcx, [rbp+var_6C]
0x18000f8cf  mov     [rsp+130h+var_E0], rcx
0x18000f8d4  lea     rcx, [rbp+var_20]
0x18000f8d8  mov     [rsp+130h+var_E8], rcx
0x18000f8dd  lea     rcx, [rbp+var_80]
0x18000f8e1  mov     [rsp+130h+var_F0], rcx
0x18000f8e6  lea     rcx, [rbp+var_18]
0x18000f8ea  mov     [rsp+130h+var_F8], rcx
0x18000f8ef  lea     rcx, [rbp+var_7C]
0x18000f8f3  mov     [rsp+130h+var_100], rcx
0x18000f8f8  lea     rcx, [rbp+var_68]
0x18000f8fc  mov     [rsp+130h+var_108], rcx
0x18000f901  lea     rcx, [rbp+var_60]
0x18000f905  mov     [rsp+130h+var_110], rcx
0x18000f90a  mov     rcx, r9
0x18000f90d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645664@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000f912  jmp     loc_18000F9B7
0x18000f917  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f91c  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18000f921  mov     rdi, rax
0x18000f924  cmp     dword ptr [rax], 5
0x18000f927  jbe     loc_18000F9B7
0x18000f92d  mov     rax, 200000000000h
0x18000f937  test    [rdi+10h], rax
0x18000f93b  jz      short loc_18000F9B7
0x18000f93d  mov     rcx, [rdi+18h]
0x18000f941  and     rcx, rax
0x18000f944  cmp     rcx, [rdi+18h]
0x18000f948  jnz     short loc_18000F9B7
0x18000f94a  mov     [rbp+arg_18], esi
0x18000f94d  mov     [rbp+var_60], r14
0x18000f951  call    cs:__imp_GetCurrentThreadId
0x18000f958  nop     dword ptr [rax+rax+00h]
0x18000f95d  mov     rcx, rbx
0x18000f960  mov     [rbp+var_7C], eax
0x18000f963  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x18000f968  mov     [rbp+var_80], eax
0x18000f96b  mov     [rbp+var_68], 0
0x18000f973  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000f978  lea     rcx, [rbp+arg_18]
0x18000f97c  mov     r8, rax
0x18000f97f  mov     [rsp+130h+var_F0], rcx
0x18000f984  lea     rdx, unk_180053291
0x18000f98b  lea     rcx, [rbp+var_60]
0x18000f98f  mov     [rsp+130h+var_F8], rcx
0x18000f994  lea     rcx, [rbp+var_7C]
0x18000f998  mov     [rsp+130h+var_100], rcx
0x18000f99d  lea     rcx, [rbp+var_80]
0x18000f9a1  mov     [rsp+130h+var_108], rcx
0x18000f9a6  lea     rcx, [rbp+var_68]
0x18000f9aa  mov     [rsp+130h+var_110], rcx
0x18000f9af  mov     rcx, rdi
0x18000f9b2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000f9b7  mov     rcx, rbx
0x18000f9ba  lea     r11, [rsp+130h+var_10]
0x18000f9c2  mov     rbx, [r11+20h]
0x18000f9c6  mov     rsi, [r11+28h]
0x18000f9ca  mov     rsp, r11
0x18000f9cd  pop     r14
0x18000f9cf  pop     rdi
0x18000f9d0  pop     rbp
0x18000f9d1  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
