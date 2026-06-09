# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StopActivity(void)

- ea: `0x18003b080`
- end: `0x18003b2a4`
- name: `?StopActivity@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000be18`
- `0x18000f168`
- `0x180010658`
- `0x180011fd0`
- `0x18001b03c`
- `0x1800384dc`
- `0x18003b080`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b245`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b245`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StopActivity(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  const wchar_t *v7; // rcx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  int v14; // [rsp+A0h] [rbp-19h] BYREF
  int v15; // [rsp+A4h] [rbp-15h] BYREF
  const wchar_t *v16; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v17; // [rsp+B0h] [rbp-9h] BYREF
  const wchar_t *v18; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v19; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v20; // [rsp+C8h] [rbp+Fh] BYREF
  const wchar_t *v21; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v22; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v23; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v24; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v25[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v26; // [rsp+120h] [rbp+67h] BYREF
  int v27; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v28; // [rsp+130h] [rbp+77h] BYREF
  int v29; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL) )
    {
      v7 = (const wchar_t *)*((_QWORD *)v4 + 15);
      v8 = *((_QWORD *)this + 34);
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v26 = v4[26];
      v18 = (const wchar_t *)*((_QWORD *)v4 + 12);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v27 = v4[20];
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v28) = v4[8];
      v21 = (const wchar_t *)*((_QWORD *)v4 + 3);
      v29 = *v4;
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v14 = v4[16];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v15 = v4[2];
      v16 = v7;
      v24 = 0x1000000;
      v25[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v6,
        (unsigned __int8 *)byte_180056B27,
        (const GUID *)(v8 + 8),
        v6,
        (__int64)v25,
        (__int64)&v24,
        (__int64)&v15,
        &v23,
        (__int64)&v14,
        &v22,
        (__int64)&v29,
        &v21,
        (__int64)&v28,
        &v20,
        (__int64)&v27,
        &v19,
        &v18,
        (__int64)&v26,
        &v17,
        &v16);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v10 = (__int64)v9;
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x200000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v26 = CurrentThreadId;
      v27 = *(_DWORD *)(v12 + 72);
      v28 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned __int8 *)word_180055942,
        (const GUID *)(v12 + 8),
        v13,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v26);
    }
  }
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x18003b080  push    rbp
0x18003b082  push    rbx
0x18003b083  push    rdi
0x18003b084  lea     rbp, [rsp-47h]
0x18003b089  sub     rsp, 100h
0x18003b090  mov     rdi, [rcx+110h]
0x18003b097  mov     rbx, rcx
0x18003b09a  mov     eax, [rdi+48h]
0x18003b09d  test    eax, eax
0x18003b09f  jns     loc_18003B21B
0x18003b0a5  add     rdi, 50h ; 'P'
0x18003b0a9  cmp     eax, [rdi+8]
0x18003b0ac  jnz     loc_18003B21B
0x18003b0b2  test    rdi, rdi
0x18003b0b5  jz      loc_18003B21B
0x18003b0bb  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003b0c0  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18003b0c5  mov     r9, rax
0x18003b0c8  mov     ecx, [rax]
0x18003b0ca  cmp     ecx, 5
0x18003b0cd  jbe     loc_18003B292
0x18003b0d3  mov     rdx, 200000000000h
0x18003b0dd  mov     rcx, rax
0x18003b0e0  call    _tlgKeywordOn
0x18003b0e5  test    al, al
0x18003b0e7  jz      loc_18003B292
0x18003b0ed  mov     rax, [rdi+70h]
0x18003b0f1  lea     rdx, byte_180056B27
0x18003b0f8  mov     rcx, [rdi+78h]
0x18003b0fc  mov     r8, [rbx+110h]
0x18003b103  mov     [rbp+57h+var_60], rax
0x18003b107  add     r8, 8
0x18003b10b  mov     eax, [rdi+68h]
0x18003b10e  mov     [rbp+57h+arg_0], eax
0x18003b111  mov     rax, [rdi+60h]
0x18003b115  mov     [rbp+57h+var_58], rax
0x18003b119  mov     rax, [rdi+58h]
0x18003b11d  mov     [rbp+57h+var_50], rax
0x18003b121  mov     eax, [rdi+50h]
0x18003b124  mov     [rbp+57h+arg_8], eax
0x18003b127  mov     rax, [rdi+48h]
0x18003b12b  mov     [rbp+57h+var_48], rax
0x18003b12f  mov     eax, [rdi+20h]
0x18003b132  mov     dword ptr [rbp+57h+arg_10], eax
0x18003b135  mov     rax, [rdi+18h]
0x18003b139  mov     [rbp+57h+var_40], rax
0x18003b13d  mov     eax, [rdi]
0x18003b13f  mov     [rbp+57h+arg_18], eax
0x18003b142  mov     rax, [rdi+80h]
0x18003b149  mov     [rbp+57h+var_38], rax
0x18003b14d  mov     eax, [rdi+40h]
0x18003b150  mov     [rbp+57h+var_70], eax
0x18003b153  mov     rax, [rdi+38h]
0x18003b157  mov     [rbp+57h+var_30], rax
0x18003b15b  mov     eax, [rdi+8]
0x18003b15e  mov     [rbp+57h+var_6C], eax
0x18003b161  lea     rax, [rbp+57h+var_68]
0x18003b165  mov     [rsp+110h+var_78], rax
0x18003b16d  lea     rax, [rbp+57h+var_60]
0x18003b171  mov     [rsp+110h+var_80], rax
0x18003b179  lea     rax, [rbp+57h+arg_0]
0x18003b17d  mov     [rsp+110h+var_88], rax
0x18003b185  lea     rax, [rbp+57h+var_58]
0x18003b189  mov     [rsp+110h+var_90], rax
0x18003b191  lea     rax, [rbp+57h+var_50]
0x18003b195  mov     [rsp+110h+var_98], rax
0x18003b19a  lea     rax, [rbp+57h+arg_8]
0x18003b19e  mov     [rsp+110h+var_A0], rax
0x18003b1a3  lea     rax, [rbp+57h+var_48]
0x18003b1a7  mov     [rsp+110h+var_A8], rax
0x18003b1ac  lea     rax, [rbp+57h+arg_10]
0x18003b1b0  mov     [rsp+110h+var_B0], rax
0x18003b1b5  lea     rax, [rbp+57h+var_40]
0x18003b1b9  mov     [rsp+110h+var_B8], rax
0x18003b1be  lea     rax, [rbp+57h+arg_18]
0x18003b1c2  mov     [rsp+110h+var_C0], rax
0x18003b1c7  lea     rax, [rbp+57h+var_38]
0x18003b1cb  mov     [rsp+110h+var_C8], rax
0x18003b1d0  lea     rax, [rbp+57h+var_70]
0x18003b1d4  mov     [rsp+110h+var_D0], rax
0x18003b1d9  lea     rax, [rbp+57h+var_30]
0x18003b1dd  mov     [rsp+110h+var_D8], rax
0x18003b1e2  lea     rax, [rbp+57h+var_6C]
0x18003b1e6  mov     [rsp+110h+var_E0], rax
0x18003b1eb  lea     rax, [rbp+57h+var_28]
0x18003b1ef  mov     [rsp+110h+var_E8], rax
0x18003b1f4  lea     rax, [rbp+57h+var_20]
0x18003b1f8  mov     [rbp+57h+var_68], rcx
0x18003b1fc  mov     rcx, r9
0x18003b1ff  mov     [rsp+110h+var_F0], rax
0x18003b204  mov     [rbp+57h+var_28], 1000000h
0x18003b20c  mov     [rbp+57h+var_20], 0
0x18003b214  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003b219  jmp     short loc_18003B292
0x18003b21b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003b220  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18003b225  mov     rdi, rax
0x18003b228  mov     ecx, [rax]
0x18003b22a  cmp     ecx, 5
0x18003b22d  jbe     short loc_18003B292
0x18003b22f  mov     rdx, 200000000000h
0x18003b239  mov     rcx, rax
0x18003b23c  call    _tlgKeywordOn
0x18003b241  test    al, al
0x18003b243  jz      short loc_18003B292
0x18003b245  call    cs:__imp_GetCurrentThreadId
0x18003b24b  mov     r8, [rbx+110h]
0x18003b252  lea     rdx, word_180055942
0x18003b259  mov     [rbp+57h+arg_0], eax
0x18003b25c  mov     rcx, rdi
0x18003b25f  mov     eax, [r8+48h]
0x18003b263  add     r8, 8
0x18003b267  mov     [rbp+57h+arg_8], eax
0x18003b26a  lea     rax, [rbp+57h+arg_0]
0x18003b26e  mov     [rsp+110h+var_E0], rax
0x18003b273  lea     rax, [rbp+57h+arg_8]
0x18003b277  mov     [rsp+110h+var_E8], rax
0x18003b27c  lea     rax, [rbp+57h+arg_10]
0x18003b280  mov     [rsp+110h+var_F0], rax
0x18003b285  mov     [rbp+57h+arg_10], 0
0x18003b28d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003b292  mov     rcx, rbx
0x18003b295  add     rsp, 100h
0x18003b29c  pop     rdi
0x18003b29d  pop     rbx
0x18003b29e  pop     rbp
0x18003b29f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
