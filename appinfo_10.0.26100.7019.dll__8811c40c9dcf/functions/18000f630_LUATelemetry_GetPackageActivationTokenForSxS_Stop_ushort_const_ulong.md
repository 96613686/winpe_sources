# LUATelemetry::GetPackageActivationTokenForSxS::Stop(ushort const *,ulong)

- ea: `0x18000f630`
- end: `0x18000f8a6`
- name: `?Stop@GetPackageActivationTokenForSxS@LUATelemetry@@QEAAXPEBGK@Z`
- size: `630`
- prototype: `void __fastcall(LUATelemetry::GetPackageActivationTokenForSxS *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800327a0`

## callees

- `0x180002534`
- `0x18000cb30`
- `0x18000f630`
- `0x180010450`
- `0x180018ac0`
- `0x180018af8`
- `0x180018b1c`
- `0x180020fe0`
- `0x18003396c`
- `0x180033b5c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f821`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f821`

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
  __int64 v10; // r9
  __int64 v11; // rcx
  DWORD v12; // eax
  int v13; // eax
  int v14; // r9d
  const struct _tlgProvider_t *v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  int v20; // eax
  int v21; // r9d
  int Result; // [rsp+B0h] [rbp-80h] BYREF
  DWORD CurrentThreadId; // [rsp+B4h] [rbp-7Ch] BYREF
  int v24; // [rsp+B8h] [rbp-78h] BYREF
  int v25; // [rsp+BCh] [rbp-74h] BYREF
  int v26; // [rsp+C0h] [rbp-70h] BYREF
  int v27; // [rsp+C4h] [rbp-6Ch] BYREF
  __int64 v28; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v29; // [rsp+D0h] [rbp-60h] BYREF
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
      v12 = *(_DWORD *)(FailureInfo + 8);
      v31 = v11;
      CurrentThreadId = v12;
      v39 = a3;
      v30 = a2;
      v28 = 0x1000000;
      v29 = 0;
      v13 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
              this,
              v8,
              v9,
              v10);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v14,
        (unsigned int)&unk_18004F137,
        v13,
        v14,
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
    v15 = LUATelemetry::Provider();
    if ( *(_DWORD *)v15 > 5u
      && (*((_QWORD *)v15 + 2) & 0x200000000000LL) != 0
      && (*((_QWORD *)v15 + 3) & 0x200000000000LL) == *((_QWORD *)v15 + 3) )
    {
      v39 = a3;
      v29 = a2;
      CurrentThreadId = GetCurrentThreadId();
      Result = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(this);
      v28 = 0;
      v20 = wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(
              v17,
              v16,
              v18,
              v19);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)v15,
        (unsigned int)&unk_180050F09,
        v20,
        v21,
        (__int64)&v28,
        (__int64)&Result,
        (__int64)&CurrentThreadId,
        (__int64)&v29,
        (__int64)&v39);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18000f630  mov     [rsp-8+arg_0], rbx
0x18000f635  mov     [rsp-8+arg_8], rsi
0x18000f63a  push    rbp
0x18000f63b  push    rdi
0x18000f63c  push    r14
0x18000f63e  lea     rbp, [rsp+10h]
0x18000f643  sub     rsp, 120h
0x18000f64a  mov     esi, r8d
0x18000f64d  mov     r14, rdx
0x18000f650  mov     rbx, rcx
0x18000f653  call    ?GetFailureInfo@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAPEBUFailureInfo@2@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetFailureInfo(void)
0x18000f658  mov     rdi, rax
0x18000f65b  mov     rcx, rbx
0x18000f65e  test    rax, rax
0x18000f661  jz      loc_18000F7E7
0x18000f667  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f66c  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18000f671  mov     r9, rax
0x18000f674  cmp     dword ptr [rax], 5
0x18000f677  jbe     loc_18000F887
0x18000f67d  mov     rdx, 200000000000h
0x18000f687  mov     rcx, rax
0x18000f68a  call    _tlgKeywordOn
0x18000f68f  test    al, al
0x18000f691  jz      loc_18000F887
0x18000f697  mov     rax, [rdi+70h]
0x18000f69b  mov     rcx, [rdi+78h]
0x18000f69f  mov     [rbp+var_48], rax
0x18000f6a3  mov     eax, [rdi+68h]
0x18000f6a6  mov     [rbp+var_78], eax
0x18000f6a9  mov     rax, [rdi+60h]
0x18000f6ad  mov     [rbp+var_40], rax
0x18000f6b1  mov     rax, [rdi+58h]
0x18000f6b5  mov     [rbp+var_38], rax
0x18000f6b9  mov     eax, [rdi+50h]
0x18000f6bc  mov     [rbp+var_74], eax
0x18000f6bf  mov     rax, [rdi+48h]
0x18000f6c3  mov     [rbp+var_30], rax
0x18000f6c7  mov     eax, [rdi+20h]
0x18000f6ca  mov     [rbp+var_70], eax
0x18000f6cd  mov     rax, [rdi+18h]
0x18000f6d1  mov     [rbp+var_28], rax
0x18000f6d5  mov     eax, [rdi]
0x18000f6d7  mov     [rbp+var_6C], eax
0x18000f6da  mov     rax, [rdi+80h]
0x18000f6e1  mov     [rbp+var_20], rax
0x18000f6e5  mov     eax, [rdi+40h]
0x18000f6e8  mov     [rbp+var_80], eax
0x18000f6eb  mov     rax, [rdi+38h]
0x18000f6ef  mov     [rbp+var_18], rax
0x18000f6f3  mov     eax, [rdi+8]
0x18000f6f6  mov     [rbp+var_50], rcx
0x18000f6fa  mov     rcx, rbx
0x18000f6fd  mov     [rbp+var_7C], eax
0x18000f700  mov     [rbp+arg_18], esi
0x18000f703  mov     [rbp+var_58], r14
0x18000f707  mov     [rbp+var_68], 1000000h
0x18000f70f  mov     [rbp+var_60], 0
0x18000f717  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000f71c  lea     rcx, [rbp+arg_18]
0x18000f720  mov     r8, rax
0x18000f723  mov     [rsp+130h+var_88], rcx
0x18000f72b  lea     rdx, unk_18004F137
0x18000f732  lea     rcx, [rbp+var_58]
0x18000f736  mov     [rsp+130h+var_90], rcx
0x18000f73e  lea     rcx, [rbp+var_50]
0x18000f742  mov     [rsp+130h+var_98], rcx
0x18000f74a  lea     rcx, [rbp+var_48]
0x18000f74e  mov     [rsp+130h+var_A0], rcx
0x18000f756  lea     rcx, [rbp+var_78]
0x18000f75a  mov     [rsp+130h+var_A8], rcx
0x18000f762  lea     rcx, [rbp+var_40]
0x18000f766  mov     [rsp+130h+var_B0], rcx
0x18000f76e  lea     rcx, [rbp+var_38]
0x18000f772  mov     [rsp+130h+var_B8], rcx
0x18000f777  lea     rcx, [rbp+var_74]
0x18000f77b  mov     [rsp+130h+var_C0], rcx
0x18000f780  lea     rcx, [rbp+var_30]
0x18000f784  mov     [rsp+130h+var_C8], rcx
0x18000f789  lea     rcx, [rbp+var_70]
0x18000f78d  mov     [rsp+130h+var_D0], rcx
0x18000f792  lea     rcx, [rbp+var_28]
0x18000f796  mov     [rsp+130h+var_D8], rcx
0x18000f79b  lea     rcx, [rbp+var_6C]
0x18000f79f  mov     [rsp+130h+var_E0], rcx
0x18000f7a4  lea     rcx, [rbp+var_20]
0x18000f7a8  mov     [rsp+130h+var_E8], rcx
0x18000f7ad  lea     rcx, [rbp+var_80]
0x18000f7b1  mov     [rsp+130h+var_F0], rcx
0x18000f7b6  lea     rcx, [rbp+var_18]
0x18000f7ba  mov     [rsp+130h+var_F8], rcx
0x18000f7bf  lea     rcx, [rbp+var_7C]
0x18000f7c3  mov     [rsp+130h+var_100], rcx
0x18000f7c8  lea     rcx, [rbp+var_68]
0x18000f7cc  mov     [rsp+130h+var_108], rcx
0x18000f7d1  lea     rcx, [rbp+var_60]
0x18000f7d5  mov     [rsp+130h+var_110], rcx
0x18000f7da  mov     rcx, r9
0x18000f7dd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645664@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000f7e2  jmp     loc_18000F887
0x18000f7e7  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18000f7ec  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18000f7f1  mov     rdi, rax
0x18000f7f4  cmp     dword ptr [rax], 5
0x18000f7f7  jbe     loc_18000F887
0x18000f7fd  mov     rax, 200000000000h
0x18000f807  test    [rdi+10h], rax
0x18000f80b  jz      short loc_18000F887
0x18000f80d  mov     rcx, [rdi+18h]
0x18000f811  and     rcx, rax
0x18000f814  cmp     rcx, [rdi+18h]
0x18000f818  jnz     short loc_18000F887
0x18000f81a  mov     [rbp+arg_18], esi
0x18000f81d  mov     [rbp+var_60], r14
0x18000f821  call    cs:__imp_GetCurrentThreadId
0x18000f828  nop     dword ptr [rax+rax+00h]
0x18000f82d  mov     rcx, rbx
0x18000f830  mov     [rbp+var_7C], eax
0x18000f833  call    ?GetResult@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEBAJXZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::GetResult(void)
0x18000f838  mov     [rbp+var_80], eax
0x18000f83b  mov     [rbp+var_68], 0
0x18000f843  call    ?Id@?$ActivityBase@VLUATelemetry@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<LUATelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18000f848  lea     rcx, [rbp+arg_18]
0x18000f84c  mov     r8, rax
0x18000f84f  mov     [rsp+130h+var_F0], rcx
0x18000f854  lea     rdx, unk_180050F09
0x18000f85b  lea     rcx, [rbp+var_60]
0x18000f85f  mov     [rsp+130h+var_F8], rcx
0x18000f864  lea     rcx, [rbp+var_7C]
0x18000f868  mov     [rsp+130h+var_100], rcx
0x18000f86d  lea     rcx, [rbp+var_80]
0x18000f871  mov     [rsp+130h+var_108], rcx
0x18000f876  lea     rcx, [rbp+var_68]
0x18000f87a  mov     [rsp+130h+var_110], rcx
0x18000f87f  mov     rcx, rdi
0x18000f882  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000f887  mov     rcx, rbx
0x18000f88a  lea     r11, [rsp+130h+var_10]
0x18000f892  mov     rbx, [r11+20h]
0x18000f896  mov     rsi, [r11+28h]
0x18000f89a  mov     rsp, r11
0x18000f89d  pop     r14
0x18000f89f  pop     rdi
0x18000f8a0  pop     rbp
0x18000f8a1  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
