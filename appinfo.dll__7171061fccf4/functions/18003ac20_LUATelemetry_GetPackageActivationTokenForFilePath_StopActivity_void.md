# LUATelemetry::GetPackageActivationTokenForFilePath::StopActivity(void)

- ea: `0x18003ac20`
- end: `0x18003ae44`
- name: `?StopActivity@GetPackageActivationTokenForFilePath@LUATelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(LUATelemetry::GetPackageActivationTokenForFilePath *__hidden this)`
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
- `0x18003ac20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ade5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ade5`

## pseudocode

```c
void __fastcall LUATelemetry::GetPackageActivationTokenForFilePath::StopActivity(
        LUATelemetry::GetPackageActivationTokenForFilePath *this)
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
        (unsigned __int8 *)&dword_180056254,
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
        (unsigned __int8 *)&dword_1800559AC,
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
0x18003ac20  push    rbp
0x18003ac22  push    rbx
0x18003ac23  push    rdi
0x18003ac24  lea     rbp, [rsp-47h]
0x18003ac29  sub     rsp, 100h
0x18003ac30  mov     rdi, [rcx+110h]
0x18003ac37  mov     rbx, rcx
0x18003ac3a  mov     eax, [rdi+48h]
0x18003ac3d  test    eax, eax
0x18003ac3f  jns     loc_18003ADBB
0x18003ac45  add     rdi, 50h ; 'P'
0x18003ac49  cmp     eax, [rdi+8]
0x18003ac4c  jnz     loc_18003ADBB
0x18003ac52  test    rdi, rdi
0x18003ac55  jz      loc_18003ADBB
0x18003ac5b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003ac60  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18003ac65  mov     r9, rax
0x18003ac68  mov     ecx, [rax]
0x18003ac6a  cmp     ecx, 5
0x18003ac6d  jbe     loc_18003AE32
0x18003ac73  mov     rdx, 200000000000h
0x18003ac7d  mov     rcx, rax
0x18003ac80  call    _tlgKeywordOn
0x18003ac85  test    al, al
0x18003ac87  jz      loc_18003AE32
0x18003ac8d  mov     rax, [rdi+70h]
0x18003ac91  lea     rdx, dword_180056254
0x18003ac98  mov     rcx, [rdi+78h]
0x18003ac9c  mov     r8, [rbx+110h]
0x18003aca3  mov     [rbp+57h+var_60], rax
0x18003aca7  add     r8, 8
0x18003acab  mov     eax, [rdi+68h]
0x18003acae  mov     [rbp+57h+arg_0], eax
0x18003acb1  mov     rax, [rdi+60h]
0x18003acb5  mov     [rbp+57h+var_58], rax
0x18003acb9  mov     rax, [rdi+58h]
0x18003acbd  mov     [rbp+57h+var_50], rax
0x18003acc1  mov     eax, [rdi+50h]
0x18003acc4  mov     [rbp+57h+arg_8], eax
0x18003acc7  mov     rax, [rdi+48h]
0x18003accb  mov     [rbp+57h+var_48], rax
0x18003accf  mov     eax, [rdi+20h]
0x18003acd2  mov     dword ptr [rbp+57h+arg_10], eax
0x18003acd5  mov     rax, [rdi+18h]
0x18003acd9  mov     [rbp+57h+var_40], rax
0x18003acdd  mov     eax, [rdi]
0x18003acdf  mov     [rbp+57h+arg_18], eax
0x18003ace2  mov     rax, [rdi+80h]
0x18003ace9  mov     [rbp+57h+var_38], rax
0x18003aced  mov     eax, [rdi+40h]
0x18003acf0  mov     [rbp+57h+var_70], eax
0x18003acf3  mov     rax, [rdi+38h]
0x18003acf7  mov     [rbp+57h+var_30], rax
0x18003acfb  mov     eax, [rdi+8]
0x18003acfe  mov     [rbp+57h+var_6C], eax
0x18003ad01  lea     rax, [rbp+57h+var_68]
0x18003ad05  mov     [rsp+110h+var_78], rax
0x18003ad0d  lea     rax, [rbp+57h+var_60]
0x18003ad11  mov     [rsp+110h+var_80], rax
0x18003ad19  lea     rax, [rbp+57h+arg_0]
0x18003ad1d  mov     [rsp+110h+var_88], rax
0x18003ad25  lea     rax, [rbp+57h+var_58]
0x18003ad29  mov     [rsp+110h+var_90], rax
0x18003ad31  lea     rax, [rbp+57h+var_50]
0x18003ad35  mov     [rsp+110h+var_98], rax
0x18003ad3a  lea     rax, [rbp+57h+arg_8]
0x18003ad3e  mov     [rsp+110h+var_A0], rax
0x18003ad43  lea     rax, [rbp+57h+var_48]
0x18003ad47  mov     [rsp+110h+var_A8], rax
0x18003ad4c  lea     rax, [rbp+57h+arg_10]
0x18003ad50  mov     [rsp+110h+var_B0], rax
0x18003ad55  lea     rax, [rbp+57h+var_40]
0x18003ad59  mov     [rsp+110h+var_B8], rax
0x18003ad5e  lea     rax, [rbp+57h+arg_18]
0x18003ad62  mov     [rsp+110h+var_C0], rax
0x18003ad67  lea     rax, [rbp+57h+var_38]
0x18003ad6b  mov     [rsp+110h+var_C8], rax
0x18003ad70  lea     rax, [rbp+57h+var_70]
0x18003ad74  mov     [rsp+110h+var_D0], rax
0x18003ad79  lea     rax, [rbp+57h+var_30]
0x18003ad7d  mov     [rsp+110h+var_D8], rax
0x18003ad82  lea     rax, [rbp+57h+var_6C]
0x18003ad86  mov     [rsp+110h+var_E0], rax
0x18003ad8b  lea     rax, [rbp+57h+var_28]
0x18003ad8f  mov     [rsp+110h+var_E8], rax
0x18003ad94  lea     rax, [rbp+57h+var_20]
0x18003ad98  mov     [rbp+57h+var_68], rcx
0x18003ad9c  mov     rcx, r9
0x18003ad9f  mov     [rsp+110h+var_F0], rax
0x18003ada4  mov     [rbp+57h+var_28], 1000000h
0x18003adac  mov     [rbp+57h+var_20], 0
0x18003adb4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003adb9  jmp     short loc_18003AE32
0x18003adbb  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003adc0  call    ?Provider@LUATelemetry@@SAPEBU_tlgProvider_t@@XZ; LUATelemetry::Provider(void)
0x18003adc5  mov     rdi, rax
0x18003adc8  mov     ecx, [rax]
0x18003adca  cmp     ecx, 5
0x18003adcd  jbe     short loc_18003AE32
0x18003adcf  mov     rdx, 200000000000h
0x18003add9  mov     rcx, rax
0x18003addc  call    _tlgKeywordOn
0x18003ade1  test    al, al
0x18003ade3  jz      short loc_18003AE32
0x18003ade5  call    cs:__imp_GetCurrentThreadId
0x18003adeb  mov     r8, [rbx+110h]
0x18003adf2  lea     rdx, dword_1800559AC
0x18003adf9  mov     [rbp+57h+arg_0], eax
0x18003adfc  mov     rcx, rdi
0x18003adff  mov     eax, [r8+48h]
0x18003ae03  add     r8, 8
0x18003ae07  mov     [rbp+57h+arg_8], eax
0x18003ae0a  lea     rax, [rbp+57h+arg_0]
0x18003ae0e  mov     [rsp+110h+var_E0], rax
0x18003ae13  lea     rax, [rbp+57h+arg_8]
0x18003ae17  mov     [rsp+110h+var_E8], rax
0x18003ae1c  lea     rax, [rbp+57h+arg_10]
0x18003ae20  mov     [rsp+110h+var_F0], rax
0x18003ae25  mov     [rbp+57h+arg_10], 0
0x18003ae2d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003ae32  mov     rcx, rbx
0x18003ae35  add     rsp, 100h
0x18003ae3c  pop     rdi
0x18003ae3d  pop     rbx
0x18003ae3e  pop     rbp
0x18003ae3f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
