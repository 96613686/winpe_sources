# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StopActivity(void)

- ea: `0x18003ae50`
- end: `0x18003b074`
- name: `?StopActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *__hidden this)`
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
- `0x18003ae50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b015`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b015`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StopActivity(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *this)
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
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
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
        (unsigned __int8 *)&word_18005543E,
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
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      v26 = CurrentThreadId;
      v27 = *(_DWORD *)(v12 + 72);
      v28 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned __int8 *)&dword_180054BEC,
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
0x18003ae50  push    rbp
0x18003ae52  push    rbx
0x18003ae53  push    rdi
0x18003ae54  lea     rbp, [rsp-47h]
0x18003ae59  sub     rsp, 100h
0x18003ae60  mov     rdi, [rcx+110h]
0x18003ae67  mov     rbx, rcx
0x18003ae6a  mov     eax, [rdi+48h]
0x18003ae6d  test    eax, eax
0x18003ae6f  jns     loc_18003AFEB
0x18003ae75  add     rdi, 50h ; 'P'
0x18003ae79  cmp     eax, [rdi+8]
0x18003ae7c  jnz     loc_18003AFEB
0x18003ae82  test    rdi, rdi
0x18003ae85  jz      loc_18003AFEB
0x18003ae8b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003ae90  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18003ae95  mov     r9, rax
0x18003ae98  mov     ecx, [rax]
0x18003ae9a  cmp     ecx, 5
0x18003ae9d  jbe     loc_18003B062
0x18003aea3  mov     rdx, 400000000000h
0x18003aead  mov     rcx, rax
0x18003aeb0  call    _tlgKeywordOn
0x18003aeb5  test    al, al
0x18003aeb7  jz      loc_18003B062
0x18003aebd  mov     rax, [rdi+70h]
0x18003aec1  lea     rdx, word_18005543E
0x18003aec8  mov     rcx, [rdi+78h]
0x18003aecc  mov     r8, [rbx+110h]
0x18003aed3  mov     [rbp+57h+var_60], rax
0x18003aed7  add     r8, 8
0x18003aedb  mov     eax, [rdi+68h]
0x18003aede  mov     [rbp+57h+arg_0], eax
0x18003aee1  mov     rax, [rdi+60h]
0x18003aee5  mov     [rbp+57h+var_58], rax
0x18003aee9  mov     rax, [rdi+58h]
0x18003aeed  mov     [rbp+57h+var_50], rax
0x18003aef1  mov     eax, [rdi+50h]
0x18003aef4  mov     [rbp+57h+arg_8], eax
0x18003aef7  mov     rax, [rdi+48h]
0x18003aefb  mov     [rbp+57h+var_48], rax
0x18003aeff  mov     eax, [rdi+20h]
0x18003af02  mov     dword ptr [rbp+57h+arg_10], eax
0x18003af05  mov     rax, [rdi+18h]
0x18003af09  mov     [rbp+57h+var_40], rax
0x18003af0d  mov     eax, [rdi]
0x18003af0f  mov     [rbp+57h+arg_18], eax
0x18003af12  mov     rax, [rdi+80h]
0x18003af19  mov     [rbp+57h+var_38], rax
0x18003af1d  mov     eax, [rdi+40h]
0x18003af20  mov     [rbp+57h+var_70], eax
0x18003af23  mov     rax, [rdi+38h]
0x18003af27  mov     [rbp+57h+var_30], rax
0x18003af2b  mov     eax, [rdi+8]
0x18003af2e  mov     [rbp+57h+var_6C], eax
0x18003af31  lea     rax, [rbp+57h+var_68]
0x18003af35  mov     [rsp+110h+var_78], rax
0x18003af3d  lea     rax, [rbp+57h+var_60]
0x18003af41  mov     [rsp+110h+var_80], rax
0x18003af49  lea     rax, [rbp+57h+arg_0]
0x18003af4d  mov     [rsp+110h+var_88], rax
0x18003af55  lea     rax, [rbp+57h+var_58]
0x18003af59  mov     [rsp+110h+var_90], rax
0x18003af61  lea     rax, [rbp+57h+var_50]
0x18003af65  mov     [rsp+110h+var_98], rax
0x18003af6a  lea     rax, [rbp+57h+arg_8]
0x18003af6e  mov     [rsp+110h+var_A0], rax
0x18003af73  lea     rax, [rbp+57h+var_48]
0x18003af77  mov     [rsp+110h+var_A8], rax
0x18003af7c  lea     rax, [rbp+57h+arg_10]
0x18003af80  mov     [rsp+110h+var_B0], rax
0x18003af85  lea     rax, [rbp+57h+var_40]
0x18003af89  mov     [rsp+110h+var_B8], rax
0x18003af8e  lea     rax, [rbp+57h+arg_18]
0x18003af92  mov     [rsp+110h+var_C0], rax
0x18003af97  lea     rax, [rbp+57h+var_38]
0x18003af9b  mov     [rsp+110h+var_C8], rax
0x18003afa0  lea     rax, [rbp+57h+var_70]
0x18003afa4  mov     [rsp+110h+var_D0], rax
0x18003afa9  lea     rax, [rbp+57h+var_30]
0x18003afad  mov     [rsp+110h+var_D8], rax
0x18003afb2  lea     rax, [rbp+57h+var_6C]
0x18003afb6  mov     [rsp+110h+var_E0], rax
0x18003afbb  lea     rax, [rbp+57h+var_28]
0x18003afbf  mov     [rsp+110h+var_E8], rax
0x18003afc4  lea     rax, [rbp+57h+var_20]
0x18003afc8  mov     [rbp+57h+var_68], rcx
0x18003afcc  mov     rcx, r9
0x18003afcf  mov     [rsp+110h+var_F0], rax
0x18003afd4  mov     [rbp+57h+var_28], 1000000h
0x18003afdc  mov     [rbp+57h+var_20], 0
0x18003afe4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18003afe9  jmp     short loc_18003B062
0x18003afeb  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18003aff0  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18003aff5  mov     rdi, rax
0x18003aff8  mov     ecx, [rax]
0x18003affa  cmp     ecx, 5
0x18003affd  jbe     short loc_18003B062
0x18003afff  mov     rdx, 400000000000h
0x18003b009  mov     rcx, rax
0x18003b00c  call    _tlgKeywordOn
0x18003b011  test    al, al
0x18003b013  jz      short loc_18003B062
0x18003b015  call    cs:__imp_GetCurrentThreadId
0x18003b01b  mov     r8, [rbx+110h]
0x18003b022  lea     rdx, dword_180054BEC
0x18003b029  mov     [rbp+57h+arg_0], eax
0x18003b02c  mov     rcx, rdi
0x18003b02f  mov     eax, [r8+48h]
0x18003b033  add     r8, 8
0x18003b037  mov     [rbp+57h+arg_8], eax
0x18003b03a  lea     rax, [rbp+57h+arg_0]
0x18003b03e  mov     [rsp+110h+var_E0], rax
0x18003b043  lea     rax, [rbp+57h+arg_8]
0x18003b047  mov     [rsp+110h+var_E8], rax
0x18003b04c  lea     rax, [rbp+57h+arg_10]
0x18003b050  mov     [rsp+110h+var_F0], rax
0x18003b055  mov     [rbp+57h+arg_10], 0
0x18003b05d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003b062  mov     rcx, rbx
0x18003b065  add     rsp, 100h
0x18003b06c  pop     rdi
0x18003b06d  pop     rbx
0x18003b06e  pop     rbp
0x18003b06f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
