# LUATelemetry::EnsurePackageShutdownActivity::Stop(ushort const *,ulong)

- ea: `0x180036a54`
- end: `0x180036cbd`
- name: `?Stop@EnsurePackageShutdownActivity@LUATelemetry@@QEAAXPEBGK@Z`
- size: `617`
- prototype: `void __fastcall(LUATelemetry::EnsurePackageShutdownActivity *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18002e5a4`

## callees

- `0x180002534`
- `0x18000cb30`
- `0x180010450`
- `0x180018ac0`
- `0x180018af8`
- `0x180018b1c`
- `0x180020fe0`
- `0x18003396c`
- `0x180033b5c`
- `0x180036a54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036c3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036c3b`

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
        (unsigned int)&unk_18004FBD3,
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
        byte_18004F579,
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
0x180036a54  mov     [rsp-8+arg_0], rbx
0x180036a59  mov     [rsp-8+arg_8], rsi
0x180036a5e  push    rbp
0x180036a5f  push    rdi
0x180036a60  push    r14
0x180036a62  lea     rbp, [rsp+10h]
0x180036a67  sub     rsp, 120h
0x180036a6e  mov     esi, r8d
0x180036a71  mov     r14, rdx
0x180036a74  mov     rbx, rcx
0x180036a77  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x180036a7c  mov     rdi, rax
0x180036a7f  mov     rcx, rbx
0x180036a82  test    rax, rax
0x180036a85  jz      loc_180036C08
0x180036a8b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180036a90  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180036a95  mov     r9, rax
0x180036a98  cmp     dword ptr [rax], 5
0x180036a9b  jbe     loc_180036C9E
0x180036aa1  mov     rdx, 200000000000h
0x180036aab  mov     rcx, rax
0x180036aae  call    _tlgKeywordOn
0x180036ab3  test    al, al
0x180036ab5  jz      loc_180036C9E
0x180036abb  mov     rax, [rdi+78h]
0x180036abf  mov     rcx, rbx
0x180036ac2  and     [rbp+var_60], 0
0x180036ac7  mov     [rbp+var_50], rax
0x180036acb  mov     rax, [rdi+70h]
0x180036acf  mov     [rbp+var_48], rax
0x180036ad3  mov     eax, [rdi+68h]
0x180036ad6  mov     [rbp+var_78], eax
0x180036ad9  mov     rax, [rdi+60h]
0x180036add  mov     [rbp+var_40], rax
0x180036ae1  mov     rax, [rdi+58h]
0x180036ae5  mov     [rbp+var_38], rax
0x180036ae9  mov     eax, [rdi+50h]
0x180036aec  mov     [rbp+var_74], eax
0x180036aef  mov     rax, [rdi+48h]
0x180036af3  mov     [rbp+var_30], rax
0x180036af7  mov     eax, [rdi+20h]
0x180036afa  mov     [rbp+var_70], eax
0x180036afd  mov     rax, [rdi+18h]
0x180036b01  mov     [rbp+var_28], rax
0x180036b05  mov     eax, [rdi]
0x180036b07  mov     [rbp+var_6C], eax
0x180036b0a  mov     rax, [rdi+80h]
0x180036b11  mov     [rbp+var_20], rax
0x180036b15  mov     eax, [rdi+40h]
0x180036b18  mov     [rbp+var_80], eax
0x180036b1b  mov     rax, [rdi+38h]
0x180036b1f  mov     [rbp+var_18], rax
0x180036b23  mov     eax, [rdi+8]
0x180036b26  mov     [rbp+var_7C], eax
0x180036b29  mov     [rbp+arg_18], esi
0x180036b2c  mov     [rbp+var_58], r14
0x180036b30  mov     [rbp+var_68], 1000000h
0x180036b38  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180036b3d  lea     rcx, [rbp+arg_18]
0x180036b41  mov     r8, rax
0x180036b44  mov     [rsp+130h+var_88], rcx
0x180036b4c  lea     rdx, unk_18004FBD3
0x180036b53  lea     rcx, [rbp+var_58]
0x180036b57  mov     [rsp+130h+var_90], rcx
0x180036b5f  lea     rcx, [rbp+var_50]
0x180036b63  mov     [rsp+130h+var_98], rcx
0x180036b6b  lea     rcx, [rbp+var_48]
0x180036b6f  mov     [rsp+130h+var_A0], rcx
0x180036b77  lea     rcx, [rbp+var_78]
0x180036b7b  mov     [rsp+130h+var_A8], rcx
0x180036b83  lea     rcx, [rbp+var_40]
0x180036b87  mov     [rsp+130h+var_B0], rcx
0x180036b8f  lea     rcx, [rbp+var_38]
0x180036b93  mov     [rsp+130h+var_B8], rcx
0x180036b98  lea     rcx, [rbp+var_74]
0x180036b9c  mov     [rsp+130h+var_C0], rcx
0x180036ba1  lea     rcx, [rbp+var_30]
0x180036ba5  mov     [rsp+130h+var_C8], rcx
0x180036baa  lea     rcx, [rbp+var_70]
0x180036bae  mov     [rsp+130h+var_D0], rcx
0x180036bb3  lea     rcx, [rbp+var_28]
0x180036bb7  mov     [rsp+130h+var_D8], rcx
0x180036bbc  lea     rcx, [rbp+var_6C]
0x180036bc0  mov     [rsp+130h+var_E0], rcx
0x180036bc5  lea     rcx, [rbp+var_20]
0x180036bc9  mov     [rsp+130h+var_E8], rcx
0x180036bce  lea     rcx, [rbp+var_80]
0x180036bd2  mov     [rsp+130h+var_F0], rcx
0x180036bd7  lea     rcx, [rbp+var_18]
0x180036bdb  mov     [rsp+130h+var_F8], rcx
0x180036be0  lea     rcx, [rbp+var_7C]
0x180036be4  mov     [rsp+130h+var_100], rcx
0x180036be9  lea     rcx, [rbp+var_68]
0x180036bed  mov     [rsp+130h+var_108], rcx
0x180036bf2  lea     rcx, [rbp+var_60]
0x180036bf6  mov     [rsp+130h+var_110], rcx
0x180036bfb  mov     rcx, r9
0x180036bfe  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645664@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180036c03  jmp     loc_180036C9E
0x180036c08  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180036c0d  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x180036c12  mov     rdi, rax
0x180036c15  cmp     dword ptr [rax], 5
0x180036c18  jbe     loc_180036C9E
0x180036c1e  mov     rdx, 200000000000h
0x180036c28  mov     rcx, rax
0x180036c2b  call    _tlgKeywordOn
0x180036c30  test    al, al
0x180036c32  jz      short loc_180036C9E
0x180036c34  mov     [rbp+arg_18], esi
0x180036c37  mov     [rbp+var_60], r14
0x180036c3b  call    cs:__imp_GetCurrentThreadId
0x180036c42  nop     dword ptr [rax+rax+00h]
0x180036c47  mov     rcx, rbx
0x180036c4a  mov     [rbp+var_7C], eax
0x180036c4d  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x180036c52  and     [rbp+var_68], 0
0x180036c57  mov     [rbp+var_80], eax
0x180036c5a  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x180036c5f  lea     rcx, [rbp+arg_18]
0x180036c63  mov     r8, rax
0x180036c66  mov     [rsp+130h+var_F0], rcx
0x180036c6b  lea     rdx, byte_18004F579
0x180036c72  lea     rcx, [rbp+var_60]
0x180036c76  mov     [rsp+130h+var_F8], rcx
0x180036c7b  lea     rcx, [rbp+var_7C]
0x180036c7f  mov     [rsp+130h+var_100], rcx
0x180036c84  lea     rcx, [rbp+var_80]
0x180036c88  mov     [rsp+130h+var_108], rcx
0x180036c8d  lea     rcx, [rbp+var_68]
0x180036c91  mov     [rsp+130h+var_110], rcx
0x180036c96  mov     rcx, rdi
0x180036c99  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180036c9e  mov     rcx, rbx
0x180036ca1  lea     r11, [rsp+130h+var_10]
0x180036ca9  mov     rbx, [r11+20h]
0x180036cad  mov     rsi, [r11+28h]
0x180036cb1  mov     rsp, r11
0x180036cb4  pop     r14
0x180036cb6  pop     rdi
0x180036cb7  pop     rbp
0x180036cb8  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
