# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StopActivity(void)

- ea: `0x140015d40`
- end: `0x140015f64`
- name: `?StopActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000177c`
- `0x1400023e0`
- `0x140002f8c`
- `0x14000e620`
- `0x140011aa0`
- `0x140015d40`
- `0x14001c16c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140015f05`
- `KERNEL32!GetCurrentThreadId` at `0x140015f05`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StopActivity(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *this)
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
    v5 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v8 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v7, v5) )
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
        (__int64)&byte_14002637F,
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
    v11 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
    v12 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v7, v8) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      v28 = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v30 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (__int64)&byte_140025837,
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
0x140015d40  push    rbp
0x140015d42  push    rbx
0x140015d43  push    rdi
0x140015d44  lea     rbp, [rsp-47h]
0x140015d49  sub     rsp, 100h
0x140015d50  mov     rdi, [rcx+110h]
0x140015d57  mov     rbx, rcx
0x140015d5a  mov     eax, [rdi+48h]
0x140015d5d  test    eax, eax
0x140015d5f  jns     loc_140015EDB
0x140015d65  add     rdi, 50h ; 'P'
0x140015d69  cmp     eax, [rdi+8]
0x140015d6c  jnz     loc_140015EDB
0x140015d72  test    rdi, rdi
0x140015d75  jz      loc_140015EDB
0x140015d7b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140015d80  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x140015d85  mov     r9, rax
0x140015d88  mov     ecx, [rax]
0x140015d8a  cmp     ecx, 5
0x140015d8d  jbe     loc_140015F52
0x140015d93  mov     rdx, 400000000000h
0x140015d9d  mov     rcx, rax
0x140015da0  call    _tlgKeywordOn
0x140015da5  test    al, al
0x140015da7  jz      loc_140015F52
0x140015dad  mov     rax, [rdi+70h]
0x140015db1  lea     rdx, byte_14002637F
0x140015db8  mov     rcx, [rdi+78h]
0x140015dbc  mov     r8, [rbx+110h]
0x140015dc3  mov     [rbp+57h+var_60], rax
0x140015dc7  add     r8, 8
0x140015dcb  mov     eax, [rdi+68h]
0x140015dce  mov     [rbp+57h+arg_0], eax
0x140015dd1  mov     rax, [rdi+60h]
0x140015dd5  mov     [rbp+57h+var_58], rax
0x140015dd9  mov     rax, [rdi+58h]
0x140015ddd  mov     [rbp+57h+var_50], rax
0x140015de1  mov     eax, [rdi+50h]
0x140015de4  mov     [rbp+57h+arg_8], eax
0x140015de7  mov     rax, [rdi+48h]
0x140015deb  mov     [rbp+57h+var_48], rax
0x140015def  mov     eax, [rdi+20h]
0x140015df2  mov     dword ptr [rbp+57h+arg_10], eax
0x140015df5  mov     rax, [rdi+18h]
0x140015df9  mov     [rbp+57h+var_40], rax
0x140015dfd  mov     eax, [rdi]
0x140015dff  mov     [rbp+57h+arg_18], eax
0x140015e02  mov     rax, [rdi+80h]
0x140015e09  mov     [rbp+57h+var_38], rax
0x140015e0d  mov     eax, [rdi+40h]
0x140015e10  mov     [rbp+57h+var_70], eax
0x140015e13  mov     rax, [rdi+38h]
0x140015e17  mov     [rbp+57h+var_30], rax
0x140015e1b  mov     eax, [rdi+8]
0x140015e1e  mov     [rbp+57h+var_6C], eax
0x140015e21  lea     rax, [rbp+57h+var_68]
0x140015e25  mov     [rsp+110h+var_78], rax
0x140015e2d  lea     rax, [rbp+57h+var_60]
0x140015e31  mov     [rsp+110h+var_80], rax
0x140015e39  lea     rax, [rbp+57h+arg_0]
0x140015e3d  mov     [rsp+110h+var_88], rax
0x140015e45  lea     rax, [rbp+57h+var_58]
0x140015e49  mov     [rsp+110h+var_90], rax
0x140015e51  lea     rax, [rbp+57h+var_50]
0x140015e55  mov     [rsp+110h+var_98], rax
0x140015e5a  lea     rax, [rbp+57h+arg_8]
0x140015e5e  mov     [rsp+110h+var_A0], rax
0x140015e63  lea     rax, [rbp+57h+var_48]
0x140015e67  mov     [rsp+110h+var_A8], rax
0x140015e6c  lea     rax, [rbp+57h+arg_10]
0x140015e70  mov     [rsp+110h+var_B0], rax
0x140015e75  lea     rax, [rbp+57h+var_40]
0x140015e79  mov     [rsp+110h+var_B8], rax
0x140015e7e  lea     rax, [rbp+57h+arg_18]
0x140015e82  mov     [rsp+110h+var_C0], rax
0x140015e87  lea     rax, [rbp+57h+var_38]
0x140015e8b  mov     [rsp+110h+var_C8], rax
0x140015e90  lea     rax, [rbp+57h+var_70]
0x140015e94  mov     [rsp+110h+var_D0], rax
0x140015e99  lea     rax, [rbp+57h+var_30]
0x140015e9d  mov     [rsp+110h+var_D8], rax
0x140015ea2  lea     rax, [rbp+57h+var_6C]
0x140015ea6  mov     [rsp+110h+var_E0], rax
0x140015eab  lea     rax, [rbp+57h+var_28]
0x140015eaf  mov     [rsp+110h+var_E8], rax
0x140015eb4  lea     rax, [rbp+57h+var_20]
0x140015eb8  mov     [rbp+57h+var_68], rcx
0x140015ebc  mov     rcx, r9
0x140015ebf  mov     [rsp+110h+var_F0], rax
0x140015ec4  mov     [rbp+57h+var_28], 1000000h
0x140015ecc  mov     [rbp+57h+var_20], 0
0x140015ed4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140015ed9  jmp     short loc_140015F52
0x140015edb  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140015ee0  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x140015ee5  mov     rdi, rax
0x140015ee8  mov     ecx, [rax]
0x140015eea  cmp     ecx, 5
0x140015eed  jbe     short loc_140015F52
0x140015eef  mov     rdx, 400000000000h
0x140015ef9  mov     rcx, rax
0x140015efc  call    _tlgKeywordOn
0x140015f01  test    al, al
0x140015f03  jz      short loc_140015F52
0x140015f05  call    cs:__imp_GetCurrentThreadId
0x140015f0b  mov     r8, [rbx+110h]
0x140015f12  lea     rdx, byte_140025837
0x140015f19  mov     [rbp+57h+arg_0], eax
0x140015f1c  mov     rcx, rdi
0x140015f1f  mov     eax, [r8+48h]
0x140015f23  add     r8, 8
0x140015f27  mov     [rbp+57h+arg_8], eax
0x140015f2a  lea     rax, [rbp+57h+arg_0]
0x140015f2e  mov     [rsp+110h+var_E0], rax
0x140015f33  lea     rax, [rbp+57h+arg_8]
0x140015f37  mov     [rsp+110h+var_E8], rax
0x140015f3c  lea     rax, [rbp+57h+arg_10]
0x140015f40  mov     [rsp+110h+var_F0], rax
0x140015f45  mov     [rbp+57h+arg_10], 0
0x140015f4d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140015f52  mov     rcx, rbx
0x140015f55  add     rsp, 100h
0x140015f5c  pop     rdi
0x140015f5d  pop     rbx
0x140015f5e  pop     rbp
0x140015f5f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
