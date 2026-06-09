# CredUIBrokerTelemetry::BrokerForAppContainersActivity::StopActivity(void)

- ea: `0x1400158e0`
- end: `0x140015b04`
- name: `?StopActivity@BrokerForAppContainersActivity@CredUIBrokerTelemetry@@MEAAXXZ`
- size: `548`
- prototype: `void __fastcall(CredUIBrokerTelemetry::BrokerForAppContainersActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000177c`
- `0x1400023e0`
- `0x140002f8c`
- `0x14000e620`
- `0x140011a40`
- `0x1400158e0`
- `0x14001c16c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140015aa5`
- `KERNEL32!GetCurrentThreadId` at `0x140015aa5`

## pseudocode

```c
void __fastcall CredUIBrokerTelemetry::BrokerForAppContainersActivity::StopActivity(
        CredUIBrokerTelemetry::BrokerForAppContainersActivity *this)
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
        (__int64)&byte_14002569F,
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
        (__int64)byte_140025041,
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
0x1400158e0  push    rbp
0x1400158e2  push    rbx
0x1400158e3  push    rdi
0x1400158e4  lea     rbp, [rsp-47h]
0x1400158e9  sub     rsp, 100h
0x1400158f0  mov     rdi, [rcx+110h]
0x1400158f7  mov     rbx, rcx
0x1400158fa  mov     eax, [rdi+48h]
0x1400158fd  test    eax, eax
0x1400158ff  jns     loc_140015A7B
0x140015905  add     rdi, 50h ; 'P'
0x140015909  cmp     eax, [rdi+8]
0x14001590c  jnz     loc_140015A7B
0x140015912  test    rdi, rdi
0x140015915  jz      loc_140015A7B
0x14001591b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140015920  call    ?Provider@CredUIBrokerLogging@@SAPEBU_tlgProvider_t@@XZ; CredUIBrokerLogging::Provider(void)
0x140015925  mov     r9, rax
0x140015928  mov     ecx, [rax]
0x14001592a  cmp     ecx, 5
0x14001592d  jbe     loc_140015AF2
0x140015933  mov     rdx, 200000000000h
0x14001593d  mov     rcx, rax
0x140015940  call    _tlgKeywordOn
0x140015945  test    al, al
0x140015947  jz      loc_140015AF2
0x14001594d  mov     rax, [rdi+70h]
0x140015951  lea     rdx, byte_14002569F
0x140015958  mov     rcx, [rdi+78h]
0x14001595c  mov     r8, [rbx+110h]
0x140015963  mov     [rbp+57h+var_60], rax
0x140015967  add     r8, 8
0x14001596b  mov     eax, [rdi+68h]
0x14001596e  mov     [rbp+57h+arg_0], eax
0x140015971  mov     rax, [rdi+60h]
0x140015975  mov     [rbp+57h+var_58], rax
0x140015979  mov     rax, [rdi+58h]
0x14001597d  mov     [rbp+57h+var_50], rax
0x140015981  mov     eax, [rdi+50h]
0x140015984  mov     [rbp+57h+arg_8], eax
0x140015987  mov     rax, [rdi+48h]
0x14001598b  mov     [rbp+57h+var_48], rax
0x14001598f  mov     eax, [rdi+20h]
0x140015992  mov     dword ptr [rbp+57h+arg_10], eax
0x140015995  mov     rax, [rdi+18h]
0x140015999  mov     [rbp+57h+var_40], rax
0x14001599d  mov     eax, [rdi]
0x14001599f  mov     [rbp+57h+arg_18], eax
0x1400159a2  mov     rax, [rdi+80h]
0x1400159a9  mov     [rbp+57h+var_38], rax
0x1400159ad  mov     eax, [rdi+40h]
0x1400159b0  mov     [rbp+57h+var_70], eax
0x1400159b3  mov     rax, [rdi+38h]
0x1400159b7  mov     [rbp+57h+var_30], rax
0x1400159bb  mov     eax, [rdi+8]
0x1400159be  mov     [rbp+57h+var_6C], eax
0x1400159c1  lea     rax, [rbp+57h+var_68]
0x1400159c5  mov     [rsp+110h+var_78], rax
0x1400159cd  lea     rax, [rbp+57h+var_60]
0x1400159d1  mov     [rsp+110h+var_80], rax
0x1400159d9  lea     rax, [rbp+57h+arg_0]
0x1400159dd  mov     [rsp+110h+var_88], rax
0x1400159e5  lea     rax, [rbp+57h+var_58]
0x1400159e9  mov     [rsp+110h+var_90], rax
0x1400159f1  lea     rax, [rbp+57h+var_50]
0x1400159f5  mov     [rsp+110h+var_98], rax
0x1400159fa  lea     rax, [rbp+57h+arg_8]
0x1400159fe  mov     [rsp+110h+var_A0], rax
0x140015a03  lea     rax, [rbp+57h+var_48]
0x140015a07  mov     [rsp+110h+var_A8], rax
0x140015a0c  lea     rax, [rbp+57h+arg_10]
0x140015a10  mov     [rsp+110h+var_B0], rax
0x140015a15  lea     rax, [rbp+57h+var_40]
0x140015a19  mov     [rsp+110h+var_B8], rax
0x140015a1e  lea     rax, [rbp+57h+arg_18]
0x140015a22  mov     [rsp+110h+var_C0], rax
0x140015a27  lea     rax, [rbp+57h+var_38]
0x140015a2b  mov     [rsp+110h+var_C8], rax
0x140015a30  lea     rax, [rbp+57h+var_70]
0x140015a34  mov     [rsp+110h+var_D0], rax
0x140015a39  lea     rax, [rbp+57h+var_30]
0x140015a3d  mov     [rsp+110h+var_D8], rax
0x140015a42  lea     rax, [rbp+57h+var_6C]
0x140015a46  mov     [rsp+110h+var_E0], rax
0x140015a4b  lea     rax, [rbp+57h+var_28]
0x140015a4f  mov     [rsp+110h+var_E8], rax
0x140015a54  lea     rax, [rbp+57h+var_20]
0x140015a58  mov     [rbp+57h+var_68], rcx
0x140015a5c  mov     rcx, r9
0x140015a5f  mov     [rsp+110h+var_F0], rax
0x140015a64  mov     [rbp+57h+var_28], 1000000h
0x140015a6c  mov     [rbp+57h+var_20], 0
0x140015a74  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140015a79  jmp     short loc_140015AF2
0x140015a7b  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140015a80  call    ?Provider@CredUIBrokerLogging@@SAPEBU_tlgProvider_t@@XZ; CredUIBrokerLogging::Provider(void)
0x140015a85  mov     rdi, rax
0x140015a88  mov     ecx, [rax]
0x140015a8a  cmp     ecx, 5
0x140015a8d  jbe     short loc_140015AF2
0x140015a8f  mov     rdx, 200000000000h
0x140015a99  mov     rcx, rax
0x140015a9c  call    _tlgKeywordOn
0x140015aa1  test    al, al
0x140015aa3  jz      short loc_140015AF2
0x140015aa5  call    cs:__imp_GetCurrentThreadId
0x140015aab  mov     r8, [rbx+110h]
0x140015ab2  lea     rdx, byte_140025041
0x140015ab9  mov     [rbp+57h+arg_0], eax
0x140015abc  mov     rcx, rdi
0x140015abf  mov     eax, [r8+48h]
0x140015ac3  add     r8, 8
0x140015ac7  mov     [rbp+57h+arg_8], eax
0x140015aca  lea     rax, [rbp+57h+arg_0]
0x140015ace  mov     [rsp+110h+var_E0], rax
0x140015ad3  lea     rax, [rbp+57h+arg_8]
0x140015ad7  mov     [rsp+110h+var_E8], rax
0x140015adc  lea     rax, [rbp+57h+arg_10]
0x140015ae0  mov     [rsp+110h+var_F0], rax
0x140015ae5  mov     [rbp+57h+arg_10], 0
0x140015aed  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140015af2  mov     rcx, rbx
0x140015af5  add     rsp, 100h
0x140015afc  pop     rdi
0x140015afd  pop     rbx
0x140015afe  pop     rbp
0x140015aff  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
