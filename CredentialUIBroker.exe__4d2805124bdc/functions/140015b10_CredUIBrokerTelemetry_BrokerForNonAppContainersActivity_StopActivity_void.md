# CredUIBrokerTelemetry::BrokerForNonAppContainersActivity::StopActivity(void)

- ea: `0x140015b10`
- end: `0x140015d34`
- name: `?StopActivity@BrokerForNonAppContainersActivity@CredUIBrokerTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(CredUIBrokerTelemetry::BrokerForNonAppContainersActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000177c`
- `0x1400023e0`
- `0x140002f8c`
- `0x14000e620`
- `0x140011a40`
- `0x140015b10`
- `0x14001c16c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140015cd5`
- `KERNEL32!GetCurrentThreadId` at `0x140015cd5`

## pseudocode

```c
void __fastcall CredUIBrokerTelemetry::BrokerForNonAppContainersActivity::StopActivity(
        CredUIBrokerTelemetry::BrokerForNonAppContainersActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const unsigned __int16 *v9; // rcx
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // [rsp+A0h] [rbp-19h] BYREF
  int v17; // [rsp+A4h] [rbp-15h] BYREF
  const unsigned __int16 *v18; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v19; // [rsp+B0h] [rbp-9h] BYREF
  const unsigned __int16 *v20; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v21; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v22; // [rsp+C8h] [rbp+Fh] BYREF
  const unsigned __int16 *v23; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v25; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v27[4]; // [rsp+F0h] [rbp+37h] BYREF
  DWORD v28; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = CredUIBrokerLogging::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v7, v5) )
    {
      v9 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
      v10 = *((_QWORD *)this + 34);
      v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      v28 = v4[26];
      v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v29 = v4[20];
      v22 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v30) = v4[8];
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
      v31 = *v4;
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v16 = v4[16];
      v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v9;
      v26 = 0x1000000;
      v27[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v8,
        (__int64)word_1400259CA,
        v10 + 8,
        v8,
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
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = CredUIBrokerLogging::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)byte_1400257D5,
        v14 + 8,
        v15,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28);
    }
  }
  wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v6,
    v7,
    v8);
}

```

## disassembly

```asm
0x140015b10  push    rbp
0x140015b12  push    rbx
0x140015b13  push    rdi
0x140015b14  lea     rbp, [rsp-47h]
0x140015b19  sub     rsp, 100h
0x140015b20  mov     rdi, [rcx+110h]
0x140015b27  mov     rbx, rcx
0x140015b2a  mov     eax, [rdi+48h]
0x140015b2d  test    eax, eax
0x140015b2f  jns     loc_140015CAB
0x140015b35  add     rdi, 50h ; 'P'
0x140015b39  cmp     eax, [rdi+8]
0x140015b3c  jnz     loc_140015CAB
0x140015b42  test    rdi, rdi
0x140015b45  jz      loc_140015CAB
0x140015b4b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140015b50  call    ?Provider@CredUIBrokerLogging@@SAPEBU_tlgProvider_t@@XZ; CredUIBrokerLogging::Provider(void)
0x140015b55  mov     r9, rax
0x140015b58  mov     ecx, [rax]
0x140015b5a  cmp     ecx, 5
0x140015b5d  jbe     loc_140015D22
0x140015b63  mov     rdx, 200000000000h
0x140015b6d  mov     rcx, rax
0x140015b70  call    _tlgKeywordOn
0x140015b75  test    al, al
0x140015b77  jz      loc_140015D22
0x140015b7d  mov     rax, [rdi+70h]
0x140015b81  lea     rdx, word_1400259CA
0x140015b88  mov     rcx, [rdi+78h]
0x140015b8c  mov     r8, [rbx+110h]
0x140015b93  mov     [rbp+57h+var_60], rax
0x140015b97  add     r8, 8
0x140015b9b  mov     eax, [rdi+68h]
0x140015b9e  mov     [rbp+57h+arg_0], eax
0x140015ba1  mov     rax, [rdi+60h]
0x140015ba5  mov     [rbp+57h+var_58], rax
0x140015ba9  mov     rax, [rdi+58h]
0x140015bad  mov     [rbp+57h+var_50], rax
0x140015bb1  mov     eax, [rdi+50h]
0x140015bb4  mov     [rbp+57h+arg_8], eax
0x140015bb7  mov     rax, [rdi+48h]
0x140015bbb  mov     [rbp+57h+var_48], rax
0x140015bbf  mov     eax, [rdi+20h]
0x140015bc2  mov     dword ptr [rbp+57h+arg_10], eax
0x140015bc5  mov     rax, [rdi+18h]
0x140015bc9  mov     [rbp+57h+var_40], rax
0x140015bcd  mov     eax, [rdi]
0x140015bcf  mov     [rbp+57h+arg_18], eax
0x140015bd2  mov     rax, [rdi+80h]
0x140015bd9  mov     [rbp+57h+var_38], rax
0x140015bdd  mov     eax, [rdi+40h]
0x140015be0  mov     [rbp+57h+var_70], eax
0x140015be3  mov     rax, [rdi+38h]
0x140015be7  mov     [rbp+57h+var_30], rax
0x140015beb  mov     eax, [rdi+8]
0x140015bee  mov     [rbp+57h+var_6C], eax
0x140015bf1  lea     rax, [rbp+57h+var_68]
0x140015bf5  mov     [rsp+110h+var_78], rax
0x140015bfd  lea     rax, [rbp+57h+var_60]
0x140015c01  mov     [rsp+110h+var_80], rax
0x140015c09  lea     rax, [rbp+57h+arg_0]
0x140015c0d  mov     [rsp+110h+var_88], rax
0x140015c15  lea     rax, [rbp+57h+var_58]
0x140015c19  mov     [rsp+110h+var_90], rax
0x140015c21  lea     rax, [rbp+57h+var_50]
0x140015c25  mov     [rsp+110h+var_98], rax
0x140015c2a  lea     rax, [rbp+57h+arg_8]
0x140015c2e  mov     [rsp+110h+var_A0], rax
0x140015c33  lea     rax, [rbp+57h+var_48]
0x140015c37  mov     [rsp+110h+var_A8], rax
0x140015c3c  lea     rax, [rbp+57h+arg_10]
0x140015c40  mov     [rsp+110h+var_B0], rax
0x140015c45  lea     rax, [rbp+57h+var_40]
0x140015c49  mov     [rsp+110h+var_B8], rax
0x140015c4e  lea     rax, [rbp+57h+arg_18]
0x140015c52  mov     [rsp+110h+var_C0], rax
0x140015c57  lea     rax, [rbp+57h+var_38]
0x140015c5b  mov     [rsp+110h+var_C8], rax
0x140015c60  lea     rax, [rbp+57h+var_70]
0x140015c64  mov     [rsp+110h+var_D0], rax
0x140015c69  lea     rax, [rbp+57h+var_30]
0x140015c6d  mov     [rsp+110h+var_D8], rax
0x140015c72  lea     rax, [rbp+57h+var_6C]
0x140015c76  mov     [rsp+110h+var_E0], rax
0x140015c7b  lea     rax, [rbp+57h+var_28]
0x140015c7f  mov     [rsp+110h+var_E8], rax
0x140015c84  lea     rax, [rbp+57h+var_20]
0x140015c88  mov     [rbp+57h+var_68], rcx
0x140015c8c  mov     rcx, r9
0x140015c8f  mov     [rsp+110h+var_F0], rax
0x140015c94  mov     [rbp+57h+var_28], 1000000h
0x140015c9c  mov     [rbp+57h+var_20], 0
0x140015ca4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140015ca9  jmp     short loc_140015D22
0x140015cab  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140015cb0  call    ?Provider@CredUIBrokerLogging@@SAPEBU_tlgProvider_t@@XZ; CredUIBrokerLogging::Provider(void)
0x140015cb5  mov     rdi, rax
0x140015cb8  mov     ecx, [rax]
0x140015cba  cmp     ecx, 5
0x140015cbd  jbe     short loc_140015D22
0x140015cbf  mov     rdx, 200000000000h
0x140015cc9  mov     rcx, rax
0x140015ccc  call    _tlgKeywordOn
0x140015cd1  test    al, al
0x140015cd3  jz      short loc_140015D22
0x140015cd5  call    cs:__imp_GetCurrentThreadId
0x140015cdb  mov     r8, [rbx+110h]
0x140015ce2  lea     rdx, byte_1400257D5
0x140015ce9  mov     [rbp+57h+arg_0], eax
0x140015cec  mov     rcx, rdi
0x140015cef  mov     eax, [r8+48h]
0x140015cf3  add     r8, 8
0x140015cf7  mov     [rbp+57h+arg_8], eax
0x140015cfa  lea     rax, [rbp+57h+arg_0]
0x140015cfe  mov     [rsp+110h+var_E0], rax
0x140015d03  lea     rax, [rbp+57h+arg_8]
0x140015d07  mov     [rsp+110h+var_E8], rax
0x140015d0c  lea     rax, [rbp+57h+arg_10]
0x140015d10  mov     [rsp+110h+var_F0], rax
0x140015d15  mov     [rbp+57h+arg_10], 0
0x140015d1d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140015d22  mov     rcx, rbx
0x140015d25  add     rsp, 100h
0x140015d2c  pop     rdi
0x140015d2d  pop     rbx
0x140015d2e  pop     rbp
0x140015d2f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
