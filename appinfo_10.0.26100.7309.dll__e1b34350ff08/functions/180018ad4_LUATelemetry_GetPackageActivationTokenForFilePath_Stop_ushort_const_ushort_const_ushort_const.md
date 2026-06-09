# LUATelemetry::GetPackageActivationTokenForFilePath::Stop(ushort const *,ushort const *,ushort const *)

- ea: `0x180018ad4`
- end: `0x180018d68`
- name: `?Stop@GetPackageActivationTokenForFilePath@LUATelemetry@@QEAAXPEBG00@Z`
- size: `660`
- prototype: `void __fastcall(LUATelemetry::GetPackageActivationTokenForFilePath *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800286a4`

## callees

- `0x180002b5c`
- `0x18000cb30`
- `0x18000efd8`
- `0x180018ad4`
- `0x180018d70`
- `0x180018da8`
- `0x180018dcc`
- `0x18001fd6c`
- `0x180033a1c`
- `0x180033c0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018cd8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018cd8`

## pseudocode

```c
void __fastcall LUATelemetry::GetPackageActivationTokenForFilePath::Stop(
        LUATelemetry::GetPackageActivationTokenForFilePath *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 FailureInfo; // rdi
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rax
  int v14; // eax
  int v15; // r9d
  const struct _tlgProvider_t *v16; // rax
  const struct _tlgProvider_t *v17; // rdi
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rax
  int Result; // [rsp+C0h] [rbp-80h] BYREF
  DWORD CurrentThreadId; // [rsp+C4h] [rbp-7Ch] BYREF
  int v25; // [rsp+C8h] [rbp-78h] BYREF
  int v26; // [rsp+CCh] [rbp-74h] BYREF
  int v27; // [rsp+D0h] [rbp-70h] BYREF
  int v28; // [rsp+D4h] [rbp-6Ch] BYREF
  __int64 v29; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v30; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v31; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v32; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v33; // [rsp+F8h] [rbp-48h] BYREF
  const unsigned __int16 *v34; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v35; // [rsp+108h] [rbp-38h] BYREF
  __int64 v36; // [rsp+110h] [rbp-30h] BYREF
  __int64 v37; // [rsp+118h] [rbp-28h] BYREF
  __int64 v38; // [rsp+120h] [rbp-20h] BYREF
  __int64 v39; // [rsp+128h] [rbp-18h] BYREF
  __int64 v40; // [rsp+130h] [rbp-10h] BYREF
  __int64 v41; // [rsp+138h] [rbp-8h] BYREF

  FailureInfo = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo();
  if ( FailureInfo )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v9 = LUATelemetry::Provider();
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x200000000000LL) )
    {
      v13 = *(_QWORD *)(FailureInfo + 120);
      v32 = 0;
      v36 = v13;
      v37 = *(_QWORD *)(FailureInfo + 112);
      v25 = *(_DWORD *)(FailureInfo + 104);
      v38 = *(_QWORD *)(FailureInfo + 96);
      v39 = *(_QWORD *)(FailureInfo + 88);
      v26 = *(_DWORD *)(FailureInfo + 80);
      v40 = *(_QWORD *)(FailureInfo + 72);
      v27 = *(_DWORD *)(FailureInfo + 32);
      v41 = *(_QWORD *)(FailureInfo + 24);
      v28 = *(_DWORD *)FailureInfo;
      v29 = *(_QWORD *)(FailureInfo + 128);
      Result = *(_DWORD *)(FailureInfo + 64);
      v30 = *(const unsigned __int16 **)(FailureInfo + 56);
      CurrentThreadId = *(_DWORD *)(FailureInfo + 8);
      v33 = a4;
      v34 = a3;
      v35 = a2;
      v31 = 0x1000000;
      v14 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
              this,
              v10,
              v11,
              v12);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v15,
        (unsigned int)&unk_180051F7C,
        v14,
        v15,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&CurrentThreadId,
        (__int64)&v30,
        (__int64)&Result,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v41,
        (__int64)&v27,
        (__int64)&v40,
        (__int64)&v26,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)&v25,
        (__int64)&v37,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v33);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v16 = LUATelemetry::Provider();
    v17 = v16;
    if ( *(_DWORD *)v16 > 5u && (unsigned __int8)tlgKeywordOn(v16, 0x200000000000LL) )
    {
      v32 = a4;
      v31 = (__int64)a3;
      v30 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v29 = 0;
      Result = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(this);
      v22 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
              v19,
              v18,
              v20,
              v21);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v17,
        &unk_1800522A6,
        v22);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x180018ad4  mov     [rsp-18h+arg_0], rbx
0x180018ad9  mov     [rsp-18h+arg_8], rsi
0x180018ade  mov     [rsp-18h+arg_10], rdi
0x180018ae3  push    rbp
0x180018ae4  push    r14
0x180018ae6  push    r15
0x180018ae8  mov     rbp, rsp
0x180018aeb  sub     rsp, 140h
0x180018af2  mov     rsi, r9
0x180018af5  mov     r14, r8
0x180018af8  mov     r15, rdx
0x180018afb  mov     rbx, rcx
0x180018afe  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x180018b03  mov     rdi, rax
0x180018b06  mov     rcx, rbx
0x180018b09  test    rax, rax
0x180018b0c  jz      loc_180018CA0
0x180018b12  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180018b17  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180018b1c  mov     r9, rax
0x180018b1f  cmp     dword ptr [rax], 5
0x180018b22  jbe     loc_180018D44
0x180018b28  mov     rdx, 200000000000h
0x180018b32  mov     rcx, rax
0x180018b35  call    _tlgKeywordOn
0x180018b3a  test    al, al
0x180018b3c  jz      loc_180018D44
0x180018b42  mov     rax, [rdi+78h]
0x180018b46  mov     rcx, rbx
0x180018b49  and     [rbp+var_50], 0
0x180018b4e  mov     [rbp+var_30], rax
0x180018b52  mov     rax, [rdi+70h]
0x180018b56  mov     [rbp+var_28], rax
0x180018b5a  mov     eax, [rdi+68h]
0x180018b5d  mov     [rbp+var_78], eax
0x180018b60  mov     rax, [rdi+60h]
0x180018b64  mov     [rbp+var_20], rax
0x180018b68  mov     rax, [rdi+58h]
0x180018b6c  mov     [rbp+var_18], rax
0x180018b70  mov     eax, [rdi+50h]
0x180018b73  mov     [rbp+var_74], eax
0x180018b76  mov     rax, [rdi+48h]
0x180018b7a  mov     [rbp+var_10], rax
0x180018b7e  mov     eax, [rdi+20h]
0x180018b81  mov     [rbp+var_70], eax
0x180018b84  mov     rax, [rdi+18h]
0x180018b88  mov     [rbp+var_8], rax
0x180018b8c  mov     eax, [rdi]
0x180018b8e  mov     [rbp+var_6C], eax
0x180018b91  mov     rax, [rdi+80h]
0x180018b98  mov     [rbp+var_68], rax
0x180018b9c  mov     eax, [rdi+40h]
0x180018b9f  mov     [rbp+var_80], eax
0x180018ba2  mov     rax, [rdi+38h]
0x180018ba6  mov     [rbp+var_60], rax
0x180018baa  mov     eax, [rdi+8]
0x180018bad  mov     [rbp+var_7C], eax
0x180018bb0  mov     [rbp+var_48], rsi
0x180018bb4  mov     [rbp+var_40], r14
0x180018bb8  mov     [rbp+var_38], r15
0x180018bbc  mov     [rbp+var_58], 1000000h
0x180018bc4  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180018bc9  lea     rcx, [rbp+var_48]
0x180018bcd  mov     r8, rax
0x180018bd0  mov     [rsp+140h+var_90], rcx
0x180018bd8  lea     rdx, unk_180051F7C
0x180018bdf  lea     rcx, [rbp+var_40]
0x180018be3  mov     [rsp+140h+var_98], rcx
0x180018beb  lea     rcx, [rbp+var_38]
0x180018bef  mov     [rsp+140h+var_A0], rcx
0x180018bf7  lea     rcx, [rbp+var_30]
0x180018bfb  mov     [rsp+140h+var_A8], rcx
0x180018c03  lea     rcx, [rbp+var_28]
0x180018c07  mov     [rsp+140h+var_B0], rcx
0x180018c0f  lea     rcx, [rbp+var_78]
0x180018c13  mov     [rsp+140h+var_B8], rcx
0x180018c1b  lea     rcx, [rbp+var_20]
0x180018c1f  mov     [rsp+140h+var_C0], rcx
0x180018c27  lea     rcx, [rbp+var_18]
0x180018c2b  mov     [rsp+140h+var_C8], rcx
0x180018c30  lea     rcx, [rbp+var_74]
0x180018c34  mov     [rsp+140h+var_D0], rcx
0x180018c39  lea     rcx, [rbp+var_10]
0x180018c3d  mov     [rsp+140h+var_D8], rcx
0x180018c42  lea     rcx, [rbp+var_70]
0x180018c46  mov     [rsp+140h+var_E0], rcx
0x180018c4b  lea     rcx, [rbp+var_8]
0x180018c4f  mov     [rsp+140h+var_E8], rcx
0x180018c54  lea     rcx, [rbp+var_6C]
0x180018c58  mov     [rsp+140h+var_F0], rcx
0x180018c5d  lea     rcx, [rbp+var_68]
0x180018c61  mov     [rsp+140h+var_F8], rcx
0x180018c66  lea     rcx, [rbp+var_80]
0x180018c6a  mov     [rsp+140h+var_100], rcx
0x180018c6f  lea     rcx, [rbp+var_60]
0x180018c73  mov     [rsp+140h+var_108], rcx
0x180018c78  lea     rcx, [rbp+var_7C]
0x180018c7c  mov     [rsp+140h+var_110], rcx
0x180018c81  lea     rcx, [rbp+var_58]
0x180018c85  mov     [rsp+140h+var_118], rcx
0x180018c8a  lea     rcx, [rbp+var_50]
0x180018c8e  mov     [rsp+140h+var_120], rcx
0x180018c93  mov     rcx, r9
0x180018c96  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180018c9b  jmp     loc_180018D44
0x180018ca0  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180018ca5  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180018caa  mov     rdi, rax
0x180018cad  cmp     dword ptr [rax], 5
0x180018cb0  jbe     loc_180018D44
0x180018cb6  mov     rdx, 200000000000h
0x180018cc0  mov     rcx, rax
0x180018cc3  call    _tlgKeywordOn
0x180018cc8  test    al, al
0x180018cca  jz      short loc_180018D44
0x180018ccc  mov     [rbp+var_50], rsi
0x180018cd0  mov     [rbp+var_58], r14
0x180018cd4  mov     [rbp+var_60], r15
0x180018cd8  call    cs:__imp_GetCurrentThreadId
0x180018cdf  nop     dword ptr [rax+rax+00h]
0x180018ce4  mov     rcx, rbx
0x180018ce7  mov     [rbp+var_7C], eax
0x180018cea  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x180018cef  and     [rbp+var_68], 0
0x180018cf4  mov     [rbp+var_80], eax
0x180018cf7  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180018cfc  lea     rcx, [rbp+var_50]
0x180018d00  mov     r8, rax
0x180018d03  mov     [rsp+140h+var_F8], rcx
0x180018d08  lea     rdx, unk_1800522A6
0x180018d0f  lea     rcx, [rbp+var_58]
0x180018d13  mov     [rsp+140h+var_100], rcx
0x180018d18  lea     rcx, [rbp+var_60]
0x180018d1c  mov     [rsp+140h+var_108], rcx
0x180018d21  lea     rcx, [rbp+var_7C]
0x180018d25  mov     [rsp+140h+var_110], rcx
0x180018d2a  lea     rcx, [rbp+var_80]
0x180018d2e  mov     [rsp+140h+var_118], rcx
0x180018d33  lea     rcx, [rbp+var_68]
0x180018d37  mov     [rsp+140h+var_120], rcx
0x180018d3c  mov     rcx, rdi
0x180018d3f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180018d44  mov     rcx, rbx
0x180018d47  lea     r11, [rsp+140h+var_s0]
0x180018d4f  mov     rbx, [r11+20h]
0x180018d53  mov     rsi, [r11+28h]
0x180018d57  mov     rdi, [r11+30h]
0x180018d5b  mov     rsp, r11
0x180018d5e  pop     r15
0x180018d60  pop     r14
0x180018d62  pop     rbp
0x180018d63  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
