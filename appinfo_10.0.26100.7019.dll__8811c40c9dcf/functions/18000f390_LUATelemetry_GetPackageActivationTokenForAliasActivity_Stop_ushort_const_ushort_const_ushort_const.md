# LUATelemetry::GetPackageActivationTokenForAliasActivity::Stop(ushort const *,ushort const *,ushort const *)

- ea: `0x18000f390`
- end: `0x18000f62a`
- name: `?Stop@GetPackageActivationTokenForAliasActivity@LUATelemetry@@QEAAXPEBG00@Z`
- size: `666`
- prototype: `void __fastcall(LUATelemetry::GetPackageActivationTokenForAliasActivity *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180028aa4`

## callees

- `0x180002b5c`
- `0x18000cb30`
- `0x18000eeac`
- `0x18000f390`
- `0x180018ac0`
- `0x180018af8`
- `0x180018b1c`
- `0x180020fe0`
- `0x18003396c`
- `0x180033b5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f597`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f597`

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
  __int64 v12; // r9
  int v13; // eax
  int v14; // r9d
  const struct _tlgProvider_t *v15; // rax
  const struct _tlgProvider_t *v16; // rdi
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rax
  int Result; // [rsp+C0h] [rbp-80h] BYREF
  DWORD CurrentThreadId; // [rsp+C4h] [rbp-7Ch] BYREF
  int v24; // [rsp+C8h] [rbp-78h] BYREF
  int v25; // [rsp+CCh] [rbp-74h] BYREF
  int v26; // [rsp+D0h] [rbp-70h] BYREF
  int v27; // [rsp+D4h] [rbp-6Ch] BYREF
  __int64 v28; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v29; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v30; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v31; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v32; // [rsp+F8h] [rbp-48h] BYREF
  const unsigned __int16 *v33; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v34; // [rsp+108h] [rbp-38h] BYREF
  __int64 v35; // [rsp+110h] [rbp-30h] BYREF
  __int64 v36; // [rsp+118h] [rbp-28h] BYREF
  __int64 v37; // [rsp+120h] [rbp-20h] BYREF
  __int64 v38; // [rsp+128h] [rbp-18h] BYREF
  __int64 v39; // [rsp+130h] [rbp-10h] BYREF
  __int64 v40; // [rsp+138h] [rbp-8h] BYREF

  FailureInfo = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo();
  if ( FailureInfo )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v9 = LUATelemetry::Provider();
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x200000000000LL) )
    {
      v35 = *(_QWORD *)(FailureInfo + 120);
      v36 = *(_QWORD *)(FailureInfo + 112);
      v24 = *(_DWORD *)(FailureInfo + 104);
      v37 = *(_QWORD *)(FailureInfo + 96);
      v38 = *(_QWORD *)(FailureInfo + 88);
      v25 = *(_DWORD *)(FailureInfo + 80);
      v39 = *(_QWORD *)(FailureInfo + 72);
      v26 = *(_DWORD *)(FailureInfo + 32);
      v40 = *(_QWORD *)(FailureInfo + 24);
      v27 = *(_DWORD *)FailureInfo;
      v28 = *(_QWORD *)(FailureInfo + 128);
      Result = *(_DWORD *)(FailureInfo + 64);
      v29 = *(const unsigned __int16 **)(FailureInfo + 56);
      CurrentThreadId = *(_DWORD *)(FailureInfo + 8);
      v32 = a4;
      v33 = a3;
      v34 = a2;
      v30 = 0x1000000;
      v31 = 0;
      v13 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
              this,
              v10,
              v11,
              v12);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v14,
        (unsigned int)&unk_180050191,
        v13,
        v14,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&CurrentThreadId,
        (__int64)&v29,
        (__int64)&Result,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v40,
        (__int64)&v26,
        (__int64)&v39,
        (__int64)&v25,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)&v24,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v32);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v15 = LUATelemetry::Provider();
    v16 = v15;
    if ( *(_DWORD *)v15 > 5u && (unsigned __int8)tlgKeywordOn(v15, 0x200000000000LL) )
    {
      v31 = a4;
      v30 = (__int64)a3;
      v29 = a2;
      CurrentThreadId = GetCurrentThreadId();
      Result = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(this);
      v28 = 0;
      v21 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
              v18,
              v17,
              v19,
              v20);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v16,
        &unk_180050402,
        v21);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18000f390  mov     [rsp-18h+arg_0], rbx
0x18000f395  mov     [rsp-18h+arg_8], rsi
0x18000f39a  mov     [rsp-18h+arg_10], rdi
0x18000f39f  push    rbp
0x18000f3a0  push    r14
0x18000f3a2  push    r15
0x18000f3a4  mov     rbp, rsp
0x18000f3a7  sub     rsp, 140h
0x18000f3ae  mov     rsi, r9
0x18000f3b1  mov     r14, r8
0x18000f3b4  mov     r15, rdx
0x18000f3b7  mov     rbx, rcx
0x18000f3ba  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x18000f3bf  mov     rdi, rax
0x18000f3c2  mov     rcx, rbx
0x18000f3c5  test    rax, rax
0x18000f3c8  jz      loc_18000F55F
0x18000f3ce  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f3d3  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18000f3d8  mov     r9, rax
0x18000f3db  cmp     dword ptr [rax], 5
0x18000f3de  jbe     loc_18000F606
0x18000f3e4  mov     rdx, 200000000000h
0x18000f3ee  mov     rcx, rax
0x18000f3f1  call    _tlgKeywordOn
0x18000f3f6  test    al, al
0x18000f3f8  jz      loc_18000F606
0x18000f3fe  mov     rax, [rdi+78h]
0x18000f402  mov     rcx, rbx
0x18000f405  mov     [rbp+var_30], rax
0x18000f409  mov     rax, [rdi+70h]
0x18000f40d  mov     [rbp+var_28], rax
0x18000f411  mov     eax, [rdi+68h]
0x18000f414  mov     [rbp+var_78], eax
0x18000f417  mov     rax, [rdi+60h]
0x18000f41b  mov     [rbp+var_20], rax
0x18000f41f  mov     rax, [rdi+58h]
0x18000f423  mov     [rbp+var_18], rax
0x18000f427  mov     eax, [rdi+50h]
0x18000f42a  mov     [rbp+var_74], eax
0x18000f42d  mov     rax, [rdi+48h]
0x18000f431  mov     [rbp+var_10], rax
0x18000f435  mov     eax, [rdi+20h]
0x18000f438  mov     [rbp+var_70], eax
0x18000f43b  mov     rax, [rdi+18h]
0x18000f43f  mov     [rbp+var_8], rax
0x18000f443  mov     eax, [rdi]
0x18000f445  mov     [rbp+var_6C], eax
0x18000f448  mov     rax, [rdi+80h]
0x18000f44f  mov     [rbp+var_68], rax
0x18000f453  mov     eax, [rdi+40h]
0x18000f456  mov     [rbp+var_80], eax
0x18000f459  mov     rax, [rdi+38h]
0x18000f45d  mov     [rbp+var_60], rax
0x18000f461  mov     eax, [rdi+8]
0x18000f464  mov     [rbp+var_7C], eax
0x18000f467  mov     [rbp+var_48], rsi
0x18000f46b  mov     [rbp+var_40], r14
0x18000f46f  mov     [rbp+var_38], r15
0x18000f473  mov     [rbp+var_58], 1000000h
0x18000f47b  mov     [rbp+var_50], 0
0x18000f483  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000f488  lea     rcx, [rbp+var_48]
0x18000f48c  mov     r8, rax
0x18000f48f  mov     [rsp+140h+var_90], rcx
0x18000f497  lea     rdx, unk_180050191
0x18000f49e  lea     rcx, [rbp+var_40]
0x18000f4a2  mov     [rsp+140h+var_98], rcx
0x18000f4aa  lea     rcx, [rbp+var_38]
0x18000f4ae  mov     [rsp+140h+var_A0], rcx
0x18000f4b6  lea     rcx, [rbp+var_30]
0x18000f4ba  mov     [rsp+140h+var_A8], rcx
0x18000f4c2  lea     rcx, [rbp+var_28]
0x18000f4c6  mov     [rsp+140h+var_B0], rcx
0x18000f4ce  lea     rcx, [rbp+var_78]
0x18000f4d2  mov     [rsp+140h+var_B8], rcx
0x18000f4da  lea     rcx, [rbp+var_20]
0x18000f4de  mov     [rsp+140h+var_C0], rcx
0x18000f4e6  lea     rcx, [rbp+var_18]
0x18000f4ea  mov     [rsp+140h+var_C8], rcx
0x18000f4ef  lea     rcx, [rbp+var_74]
0x18000f4f3  mov     [rsp+140h+var_D0], rcx
0x18000f4f8  lea     rcx, [rbp+var_10]
0x18000f4fc  mov     [rsp+140h+var_D8], rcx
0x18000f501  lea     rcx, [rbp+var_70]
0x18000f505  mov     [rsp+140h+var_E0], rcx
0x18000f50a  lea     rcx, [rbp+var_8]
0x18000f50e  mov     [rsp+140h+var_E8], rcx
0x18000f513  lea     rcx, [rbp+var_6C]
0x18000f517  mov     [rsp+140h+var_F0], rcx
0x18000f51c  lea     rcx, [rbp+var_68]
0x18000f520  mov     [rsp+140h+var_F8], rcx
0x18000f525  lea     rcx, [rbp+var_80]
0x18000f529  mov     [rsp+140h+var_100], rcx
0x18000f52e  lea     rcx, [rbp+var_60]
0x18000f532  mov     [rsp+140h+var_108], rcx
0x18000f537  lea     rcx, [rbp+var_7C]
0x18000f53b  mov     [rsp+140h+var_110], rcx
0x18000f540  lea     rcx, [rbp+var_58]
0x18000f544  mov     [rsp+140h+var_118], rcx
0x18000f549  lea     rcx, [rbp+var_50]
0x18000f54d  mov     [rsp+140h+var_120], rcx
0x18000f552  mov     rcx, r9
0x18000f555  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000f55a  jmp     loc_18000F606
0x18000f55f  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f564  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18000f569  mov     rdi, rax
0x18000f56c  cmp     dword ptr [rax], 5
0x18000f56f  jbe     loc_18000F606
0x18000f575  mov     rdx, 200000000000h
0x18000f57f  mov     rcx, rax
0x18000f582  call    _tlgKeywordOn
0x18000f587  test    al, al
0x18000f589  jz      short loc_18000F606
0x18000f58b  mov     [rbp+var_50], rsi
0x18000f58f  mov     [rbp+var_58], r14
0x18000f593  mov     [rbp+var_60], r15
0x18000f597  call    cs:__imp_GetCurrentThreadId
0x18000f59e  nop     dword ptr [rax+rax+00h]
0x18000f5a3  mov     rcx, rbx
0x18000f5a6  mov     [rbp+var_7C], eax
0x18000f5a9  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x18000f5ae  mov     [rbp+var_80], eax
0x18000f5b1  mov     [rbp+var_68], 0
0x18000f5b9  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000f5be  lea     rcx, [rbp+var_50]
0x18000f5c2  mov     r8, rax
0x18000f5c5  mov     [rsp+140h+var_F8], rcx
0x18000f5ca  lea     rdx, unk_180050402
0x18000f5d1  lea     rcx, [rbp+var_58]
0x18000f5d5  mov     [rsp+140h+var_100], rcx
0x18000f5da  lea     rcx, [rbp+var_60]
0x18000f5de  mov     [rsp+140h+var_108], rcx
0x18000f5e3  lea     rcx, [rbp+var_7C]
0x18000f5e7  mov     [rsp+140h+var_110], rcx
0x18000f5ec  lea     rcx, [rbp+var_80]
0x18000f5f0  mov     [rsp+140h+var_118], rcx
0x18000f5f5  lea     rcx, [rbp+var_68]
0x18000f5f9  mov     [rsp+140h+var_120], rcx
0x18000f5fe  mov     rcx, rdi
0x18000f601  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000f606  mov     rcx, rbx
0x18000f609  lea     r11, [rsp+140h+var_s0]
0x18000f611  mov     rbx, [r11+20h]
0x18000f615  mov     rsi, [r11+28h]
0x18000f619  mov     rdi, [r11+30h]
0x18000f61d  mov     rsp, r11
0x18000f620  pop     r15
0x18000f622  pop     r14
0x18000f624  pop     rbp
0x18000f625  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
