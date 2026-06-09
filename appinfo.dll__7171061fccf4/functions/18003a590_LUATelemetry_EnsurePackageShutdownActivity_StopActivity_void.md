# LUATelemetry::EnsurePackageShutdownActivity::StopActivity(void)

- ea: `0x18003a590`
- end: `0x18003a7b4`
- name: `?StopActivity@EnsurePackageShutdownActivity@LUATelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(LUATelemetry::EnsurePackageShutdownActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000be18`
- `0x18000f168`
- `0x180010658`
- `0x180011fd0`
- `0x18001b03c`
- `0x18001b23c`
- `0x18003a590`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a755`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a755`

## pseudocode

```c
void __fastcall LUATelemetry::EnsurePackageShutdownActivity::StopActivity(
        LUATelemetry::EnsurePackageShutdownActivity *this)
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
    v5 = LUATelemetry::Provider();
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
        (unsigned __int8 *)byte_18005611F,
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
    v9 = LUATelemetry::Provider();
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
        (unsigned __int8 *)word_180055572,
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
0x18003a590  push    rbp
0x18003a592  push    rbx
0x18003a593  push    rdi
0x18003a594  lea     rbp, [rsp-47h]
0x18003a599  sub     rsp, 100h
0x18003a5a0  mov     rdi, [rcx+110h]
0x18003a5a7  mov     rbx, rcx
0x18003a5aa  mov     eax, [rdi+48h]
0x18003a5ad  test    eax, eax
0x18003a5af  jns     loc_18003A72B
0x18003a5b5  add     rdi, 50h ; 'P'
0x18003a5b9  cmp     eax, [rdi+8]
0x18003a5bc  jnz     loc_18003A72B
0x18003a5c2  test    rdi, rdi
0x18003a5c5  jz      loc_18003A72B
0x18003a5cb  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003a5d0  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18003a5d5  mov     r9, rax
0x18003a5d8  mov     ecx, [rax]
0x18003a5da  cmp     ecx, 5
0x18003a5dd  jbe     loc_18003A7A2
0x18003a5e3  mov     rdx, 200000000000h
0x18003a5ed  mov     rcx, rax
0x18003a5f0  call    _tlgKeywordOn
0x18003a5f5  test    al, al
0x18003a5f7  jz      loc_18003A7A2
0x18003a5fd  mov     rax, [rdi+70h]
0x18003a601  lea     rdx, byte_18005611F
0x18003a608  mov     rcx, [rdi+78h]
0x18003a60c  mov     r8, [rbx+110h]
0x18003a613  mov     [rbp+57h+var_60], rax
0x18003a617  add     r8, 8
0x18003a61b  mov     eax, [rdi+68h]
0x18003a61e  mov     [rbp+57h+arg_0], eax
0x18003a621  mov     rax, [rdi+60h]
0x18003a625  mov     [rbp+57h+var_58], rax
0x18003a629  mov     rax, [rdi+58h]
0x18003a62d  mov     [rbp+57h+var_50], rax
0x18003a631  mov     eax, [rdi+50h]
0x18003a634  mov     [rbp+57h+arg_8], eax
0x18003a637  mov     rax, [rdi+48h]
0x18003a63b  mov     [rbp+57h+var_48], rax
0x18003a63f  mov     eax, [rdi+20h]
0x18003a642  mov     dword ptr [rbp+57h+arg_10], eax
0x18003a645  mov     rax, [rdi+18h]
0x18003a649  mov     [rbp+57h+var_40], rax
0x18003a64d  mov     eax, [rdi]
0x18003a64f  mov     [rbp+57h+arg_18], eax
0x18003a652  mov     rax, [rdi+80h]
0x18003a659  mov     [rbp+57h+var_38], rax
0x18003a65d  mov     eax, [rdi+40h]
0x18003a660  mov     [rbp+57h+var_70], eax
0x18003a663  mov     rax, [rdi+38h]
0x18003a667  mov     [rbp+57h+var_30], rax
0x18003a66b  mov     eax, [rdi+8]
0x18003a66e  mov     [rbp+57h+var_6C], eax
0x18003a671  lea     rax, [rbp+57h+var_68]
0x18003a675  mov     [rsp+110h+var_78], rax
0x18003a67d  lea     rax, [rbp+57h+var_60]
0x18003a681  mov     [rsp+110h+var_80], rax
0x18003a689  lea     rax, [rbp+57h+arg_0]
0x18003a68d  mov     [rsp+110h+var_88], rax
0x18003a695  lea     rax, [rbp+57h+var_58]
0x18003a699  mov     [rsp+110h+var_90], rax
0x18003a6a1  lea     rax, [rbp+57h+var_50]
0x18003a6a5  mov     [rsp+110h+var_98], rax
0x18003a6aa  lea     rax, [rbp+57h+arg_8]
0x18003a6ae  mov     [rsp+110h+var_A0], rax
0x18003a6b3  lea     rax, [rbp+57h+var_48]
0x18003a6b7  mov     [rsp+110h+var_A8], rax
0x18003a6bc  lea     rax, [rbp+57h+arg_10]
0x18003a6c0  mov     [rsp+110h+var_B0], rax
0x18003a6c5  lea     rax, [rbp+57h+var_40]
0x18003a6c9  mov     [rsp+110h+var_B8], rax
0x18003a6ce  lea     rax, [rbp+57h+arg_18]
0x18003a6d2  mov     [rsp+110h+var_C0], rax
0x18003a6d7  lea     rax, [rbp+57h+var_38]
0x18003a6db  mov     [rsp+110h+var_C8], rax
0x18003a6e0  lea     rax, [rbp+57h+var_70]
0x18003a6e4  mov     [rsp+110h+var_D0], rax
0x18003a6e9  lea     rax, [rbp+57h+var_30]
0x18003a6ed  mov     [rsp+110h+var_D8], rax
0x18003a6f2  lea     rax, [rbp+57h+var_6C]
0x18003a6f6  mov     [rsp+110h+var_E0], rax
0x18003a6fb  lea     rax, [rbp+57h+var_28]
0x18003a6ff  mov     [rsp+110h+var_E8], rax
0x18003a704  lea     rax, [rbp+57h+var_20]
0x18003a708  mov     [rbp+57h+var_68], rcx
0x18003a70c  mov     rcx, r9
0x18003a70f  mov     [rsp+110h+var_F0], rax
0x18003a714  mov     [rbp+57h+var_28], 1000000h
0x18003a71c  mov     [rbp+57h+var_20], 0
0x18003a724  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003a729  jmp     short loc_18003A7A2
0x18003a72b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003a730  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18003a735  mov     rdi, rax
0x18003a738  mov     ecx, [rax]
0x18003a73a  cmp     ecx, 5
0x18003a73d  jbe     short loc_18003A7A2
0x18003a73f  mov     rdx, 200000000000h
0x18003a749  mov     rcx, rax
0x18003a74c  call    _tlgKeywordOn
0x18003a751  test    al, al
0x18003a753  jz      short loc_18003A7A2
0x18003a755  call    cs:__imp_GetCurrentThreadId
0x18003a75b  mov     r8, [rbx+110h]
0x18003a762  lea     rdx, word_180055572
0x18003a769  mov     [rbp+57h+arg_0], eax
0x18003a76c  mov     rcx, rdi
0x18003a76f  mov     eax, [r8+48h]
0x18003a773  add     r8, 8
0x18003a777  mov     [rbp+57h+arg_8], eax
0x18003a77a  lea     rax, [rbp+57h+arg_0]
0x18003a77e  mov     [rsp+110h+var_E0], rax
0x18003a783  lea     rax, [rbp+57h+arg_8]
0x18003a787  mov     [rsp+110h+var_E8], rax
0x18003a78c  lea     rax, [rbp+57h+arg_10]
0x18003a790  mov     [rsp+110h+var_F0], rax
0x18003a795  mov     [rbp+57h+arg_10], 0
0x18003a79d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003a7a2  mov     rcx, rbx
0x18003a7a5  add     rsp, 100h
0x18003a7ac  pop     rdi
0x18003a7ad  pop     rbx
0x18003a7ae  pop     rbp
0x18003a7af  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
