# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StopActivity(void)

- ea: `0x180038430`
- end: `0x180038656`
- name: `?StopActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@MEAAXXZ`
- size: `550`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting`

## callees

- `0x18000c7d0`
- `0x18000cb30`
- `0x180010c48`
- `0x180010f8c`
- `0x180018d70`
- `0x180035a98`
- `0x180038430`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800385f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800385f4`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StopActivity(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *this)
{
  int *v1; // rax
  int v3; // ecx
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  const unsigned __int16 *v7; // rax
  const wchar_t *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // eax
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  const wchar_t *v18; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v19; // [rsp+B0h] [rbp-9h] BYREF
  const wchar_t *v20; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v21; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v22; // [rsp+C8h] [rbp+Fh] BYREF
  const wchar_t *v23; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = (int *)*((_QWORD *)this + 34);
  v3 = v1[18];
  if ( v3 >= 0 || v3 != v1[22] || (v4 = v1 + 20, v1 == (int *)-80LL) )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v10 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v11 = (__int64)v10;
    if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v14 = *(_DWORD *)(v13 + 72);
      v30 = 0;
      v29 = v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        byte_18005397B,
        (const GUID *)(v13 + 8),
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(this);
    v5 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    {
      v7 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v8 = (const wchar_t *)*((_QWORD *)v4 + 15);
      v9 = *((_QWORD *)this + 34);
      v27[0] = 0;
      v19 = v7;
      v28 = v4[26];
      v20 = (const wchar_t *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (const wchar_t *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v26 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v6,
        byte_180054095,
        (const GUID *)(v9 + 8),
        v6,
        (__int64)v27,
        (__int64)&v26,
        (__int64)&v17,
        &v25,
        (__int64)&v16,
        &v24,
        (__int64)&v31,
        &v23,
        (__int64)&v30,
        &v22,
        (__int64)&v29,
        &v21,
        &v20,
        (__int64)&v28,
        &v19,
        &v18);
    }
  }
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180038430  push    rbp
0x180038432  push    rbx
0x180038433  push    rdi
0x180038434  lea     rbp, [rsp-47h]
0x180038439  sub     rsp, 100h
0x180038440  mov     rax, [rcx+110h]
0x180038447  mov     rbx, rcx
0x18003844a  mov     ecx, [rax+48h]
0x18003844d  test    ecx, ecx
0x18003844f  jns     loc_1800385C9
0x180038455  cmp     ecx, [rax+58h]
0x180038458  jnz     loc_1800385C9
0x18003845e  lea     rdi, [rax+50h]
0x180038462  test    rdi, rdi
0x180038465  jz      loc_1800385C9
0x18003846b  mov     rcx, rbx
0x18003846e  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180038473  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180038478  mov     r9, rax
0x18003847b  cmp     dword ptr [rax], 5
0x18003847e  jbe     loc_180038644
0x180038484  mov     rdx, 400000000000h
0x18003848e  mov     rcx, rax
0x180038491  call    _tlgKeywordOn
0x180038496  test    al, al
0x180038498  jz      loc_180038644
0x18003849e  mov     rax, [rdi+70h]
0x1800384a2  lea     rdx, byte_180054095
0x1800384a9  mov     rcx, [rdi+78h]
0x1800384ad  mov     r8, [rbx+110h]
0x1800384b4  and     [rbp+57h+var_20], 0
0x1800384b9  add     r8, 8
0x1800384bd  mov     [rbp+57h+var_60], rax
0x1800384c1  mov     eax, [rdi+68h]
0x1800384c4  mov     [rbp+57h+arg_0], eax
0x1800384c7  mov     rax, [rdi+60h]
0x1800384cb  mov     [rbp+57h+var_58], rax
0x1800384cf  mov     rax, [rdi+58h]
0x1800384d3  mov     [rbp+57h+var_50], rax
0x1800384d7  mov     eax, [rdi+50h]
0x1800384da  mov     [rbp+57h+arg_8], eax
0x1800384dd  mov     rax, [rdi+48h]
0x1800384e1  mov     [rbp+57h+var_48], rax
0x1800384e5  mov     eax, [rdi+20h]
0x1800384e8  mov     dword ptr [rbp+57h+arg_10], eax
0x1800384eb  mov     rax, [rdi+18h]
0x1800384ef  mov     [rbp+57h+var_40], rax
0x1800384f3  mov     eax, [rdi]
0x1800384f5  mov     [rbp+57h+arg_18], eax
0x1800384f8  mov     rax, [rdi+80h]
0x1800384ff  mov     [rbp+57h+var_38], rax
0x180038503  mov     eax, [rdi+40h]
0x180038506  mov     [rbp+57h+var_70], eax
0x180038509  mov     rax, [rdi+38h]
0x18003850d  mov     [rbp+57h+var_30], rax
0x180038511  mov     eax, [rdi+8]
0x180038514  mov     [rbp+57h+var_6C], eax
0x180038517  lea     rax, [rbp+57h+var_68]
0x18003851b  mov     [rsp+110h+var_78], rax
0x180038523  lea     rax, [rbp+57h+var_60]
0x180038527  mov     [rsp+110h+var_80], rax
0x18003852f  lea     rax, [rbp+57h+arg_0]
0x180038533  mov     [rsp+110h+var_88], rax
0x18003853b  lea     rax, [rbp+57h+var_58]
0x18003853f  mov     [rsp+110h+var_90], rax
0x180038547  lea     rax, [rbp+57h+var_50]
0x18003854b  mov     [rsp+110h+var_98], rax
0x180038550  lea     rax, [rbp+57h+arg_8]
0x180038554  mov     [rsp+110h+var_A0], rax
0x180038559  lea     rax, [rbp+57h+var_48]
0x18003855d  mov     [rsp+110h+var_A8], rax
0x180038562  lea     rax, [rbp+57h+arg_10]
0x180038566  mov     [rsp+110h+var_B0], rax
0x18003856b  lea     rax, [rbp+57h+var_40]
0x18003856f  mov     [rsp+110h+var_B8], rax
0x180038574  lea     rax, [rbp+57h+arg_18]
0x180038578  mov     [rsp+110h+var_C0], rax
0x18003857d  lea     rax, [rbp+57h+var_38]
0x180038581  mov     [rsp+110h+var_C8], rax
0x180038586  lea     rax, [rbp+57h+var_70]
0x18003858a  mov     [rsp+110h+var_D0], rax
0x18003858f  lea     rax, [rbp+57h+var_30]
0x180038593  mov     [rsp+110h+var_D8], rax
0x180038598  lea     rax, [rbp+57h+var_6C]
0x18003859c  mov     [rsp+110h+var_E0], rax
0x1800385a1  lea     rax, [rbp+57h+var_28]
0x1800385a5  mov     [rsp+110h+var_E8], rax
0x1800385aa  lea     rax, [rbp+57h+var_20]
0x1800385ae  mov     [rbp+57h+var_68], rcx
0x1800385b2  mov     rcx, r9
0x1800385b5  mov     [rsp+110h+var_F0], rax
0x1800385ba  mov     [rbp+57h+var_28], 1000000h
0x1800385c2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800385c7  jmp     short loc_180038644
0x1800385c9  mov     rcx, rbx
0x1800385cc  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800385d1  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x1800385d6  mov     rdi, rax
0x1800385d9  cmp     dword ptr [rax], 5
0x1800385dc  jbe     short loc_180038644
0x1800385de  mov     rdx, 400000000000h
0x1800385e8  mov     rcx, rax
0x1800385eb  call    _tlgKeywordOn
0x1800385f0  test    al, al
0x1800385f2  jz      short loc_180038644
0x1800385f4  call    cs:__imp_GetCurrentThreadId
0x1800385fb  nop     dword ptr [rax+rax+00h]
0x180038600  mov     r8, [rbx+110h]
0x180038607  lea     rdx, byte_18005397B
0x18003860e  mov     [rbp+57h+arg_0], eax
0x180038611  mov     rcx, rdi
0x180038614  mov     eax, [r8+48h]
0x180038618  add     r8, 8
0x18003861c  and     [rbp+57h+arg_10], 0
0x180038621  mov     [rbp+57h+arg_8], eax
0x180038624  lea     rax, [rbp+57h+arg_0]
0x180038628  mov     [rsp+110h+var_E0], rax
0x18003862d  lea     rax, [rbp+57h+arg_8]
0x180038631  mov     [rsp+110h+var_E8], rax
0x180038636  lea     rax, [rbp+57h+arg_10]
0x18003863a  mov     [rsp+110h+var_F0], rax
0x18003863f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180038644  mov     rcx, rbx
0x180038647  add     rsp, 100h
0x18003864e  pop     rdi
0x18003864f  pop     rbx
0x180038650  pop     rbp
0x180038651  jmp     ?IgnoreCurrentThread@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
