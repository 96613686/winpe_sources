# CredUIBrokerTelemetry::BrokerForAppContainersActivity::Stop(long,ulong,ulong,ulong,ulong,ulong)

- ea: `0x140014bb0`
- end: `0x140014eaa`
- name: `?Stop@BrokerForAppContainersActivity@CredUIBrokerTelemetry@@QEAAXJKKKKK@Z`
- size: `762`
- prototype: `void __fastcall(CredUIBrokerTelemetry::BrokerForAppContainersActivity *__hidden this, int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010da0`

## callees

- `0x140001a30`
- `0x140002470`
- `0x140002f8c`
- `0x14000e620`
- `0x140011a40`
- `0x140014bb0`
- `0x14001c16c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140014e10`
- `KERNEL32!GetCurrentThreadId` at `0x140014e10`

## pseudocode

```c
void __fastcall CredUIBrokerTelemetry::BrokerForAppContainersActivity::Stop(
        CredUIBrokerTelemetry::BrokerForAppContainersActivity *this,
        int a2,
        int a3,
        int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7)
{
  __int64 v7; // rdi
  int v12; // eax
  int *v13; // rdi
  const struct _tlgProvider_t *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // r8
  const struct _tlgProvider_t *v19; // rax
  __int64 v20; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v22; // r8
  __int64 v23; // r9
  int v24; // [rsp+D0h] [rbp-80h] BYREF
  DWORD v25; // [rsp+D4h] [rbp-7Ch] BYREF
  int v26; // [rsp+D8h] [rbp-78h] BYREF
  int v27; // [rsp+DCh] [rbp-74h] BYREF
  int v28; // [rsp+E0h] [rbp-70h] BYREF
  unsigned int v29; // [rsp+E4h] [rbp-6Ch] BYREF
  unsigned int v30; // [rsp+E8h] [rbp-68h] BYREF
  unsigned int v31; // [rsp+ECh] [rbp-64h] BYREF
  unsigned int v32; // [rsp+F0h] [rbp-60h] BYREF
  int v33; // [rsp+F4h] [rbp-5Ch] BYREF
  int v34; // [rsp+F8h] [rbp-58h] BYREF
  __int64 v35; // [rsp+100h] [rbp-50h] BYREF
  const unsigned __int16 *v36; // [rsp+108h] [rbp-48h] BYREF
  const unsigned __int16 *v37; // [rsp+110h] [rbp-40h] BYREF
  const unsigned __int16 *v38; // [rsp+118h] [rbp-38h] BYREF
  const unsigned __int16 *v39; // [rsp+120h] [rbp-30h] BYREF
  const unsigned __int16 *v40; // [rsp+128h] [rbp-28h] BYREF
  const unsigned __int16 *v41; // [rsp+130h] [rbp-20h] BYREF
  const unsigned __int16 *v42; // [rsp+138h] [rbp-18h] BYREF
  const unsigned __int16 *v43; // [rsp+140h] [rbp-10h] BYREF
  __int64 v44[7]; // [rsp+148h] [rbp-8h] BYREF
  unsigned int v45; // [rsp+190h] [rbp+40h] BYREF

  v7 = *((_QWORD *)this + 34);
  v12 = *(_DWORD *)(v7 + 72);
  if ( v12 < 0 && (v13 = (int *)(v7 + 80), v12 == v13[2]) && v13 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v14 = CredUIBrokerLogging::Provider();
    v17 = (__int64)v14;
    if ( *(_DWORD *)v14 > 5u && (unsigned __int8)tlgKeywordOn(v14, 0x200000000000LL, v16, v14) )
    {
      v31 = a6;
      v32 = a5;
      v36 = (const unsigned __int16 *)*((_QWORD *)v13 + 15);
      v37 = (const unsigned __int16 *)*((_QWORD *)v13 + 14);
      v25 = v13[26];
      v18 = *((_QWORD *)this + 34) + 8LL;
      v38 = (const unsigned __int16 *)*((_QWORD *)v13 + 12);
      v39 = (const unsigned __int16 *)*((_QWORD *)v13 + 11);
      v26 = v13[20];
      v40 = (const unsigned __int16 *)*((_QWORD *)v13 + 9);
      v27 = v13[8];
      v41 = (const unsigned __int16 *)*((_QWORD *)v13 + 3);
      v28 = *v13;
      v42 = (const unsigned __int16 *)*((_QWORD *)v13 + 16);
      v29 = v13[16];
      v43 = (const unsigned __int16 *)*((_QWORD *)v13 + 7);
      v30 = v13[2];
      v45 = a7;
      v33 = a4;
      v34 = a3;
      v24 = a2;
      v44[0] = 0x1000000;
      v35 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v17,
        (__int64)byte_140026673,
        v18,
        v17,
        (__int64)&v35,
        (__int64)v44,
        (__int64)&v30,
        &v43,
        (__int64)&v29,
        &v42,
        (__int64)&v28,
        &v41,
        (__int64)&v27,
        &v40,
        (__int64)&v26,
        &v39,
        &v38,
        (__int64)&v25,
        &v37,
        &v36,
        (__int64)&v24,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v45);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v19 = CredUIBrokerLogging::Provider();
    v20 = (__int64)v19;
    if ( *(_DWORD *)v19 > 5u && (unsigned __int8)tlgKeywordOn(v19, 0x200000000000LL, v16, v17) )
    {
      v30 = a6;
      v29 = a5;
      v45 = a7;
      v28 = a4;
      v27 = a3;
      v26 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v22 = *((_QWORD *)this + 34);
      v25 = CurrentThreadId;
      v24 = *(_DWORD *)(v22 + 72);
      v35 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v20,
        (__int64)&unk_1400250A0,
        v22 + 8,
        v23,
        (__int64)&v35,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&v26,
        (__int64)&v27,
        (__int64)&v28,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v45);
    }
  }
  wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v15,
    v16,
    v17);
}

```

## disassembly

```asm
0x140014bb0  push    rbp
0x140014bb2  push    rbx
0x140014bb3  push    rsi
0x140014bb4  push    rdi
0x140014bb5  push    r14
0x140014bb7  push    r15
0x140014bb9  lea     rbp, [rsp-8]
0x140014bbe  sub     rsp, 158h
0x140014bc5  mov     rdi, [rcx+110h]
0x140014bcc  mov     esi, r9d
0x140014bcf  mov     r14d, r8d
0x140014bd2  mov     r15d, edx
0x140014bd5  mov     rbx, rcx
0x140014bd8  mov     eax, [rdi+48h]
0x140014bdb  test    eax, eax
0x140014bdd  jns     loc_140014DC1
0x140014be3  add     rdi, 50h ; 'P'
0x140014be7  cmp     eax, [rdi+8]
0x140014bea  jnz     loc_140014DC1
0x140014bf0  test    rdi, rdi
0x140014bf3  jz      loc_140014DC1
0x140014bf9  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140014bfe  call    ?Provider@CredUIBrokerLogging@@SAPEBU_tlgProvider_t@@XZ; CredUIBrokerLogging::Provider(void)
0x140014c03  mov     r9, rax
0x140014c06  mov     ecx, [rax]
0x140014c08  cmp     ecx, 5
0x140014c0b  jbe     loc_140014E93
0x140014c11  mov     rdx, 200000000000h
0x140014c1b  mov     rcx, rax
0x140014c1e  call    _tlgKeywordOn
0x140014c23  test    al, al
0x140014c25  jz      loc_140014E93
0x140014c2b  mov     eax, [rbp+30h+arg_28]
0x140014c2e  mov     [rbp+30h+var_94], eax
0x140014c31  mov     eax, [rbp+30h+arg_20]
0x140014c34  mov     [rbp+30h+var_90], eax
0x140014c37  mov     rax, [rdi+78h]
0x140014c3b  mov     [rbp+30h+var_78], rax
0x140014c3f  mov     rax, [rdi+70h]
0x140014c43  mov     [rbp+30h+var_70], rax
0x140014c47  mov     eax, [rdi+68h]
0x140014c4a  mov     [rbp+30h+var_AC], eax
0x140014c4d  mov     rax, [rdi+60h]
0x140014c51  mov     r8, [rbx+110h]
0x140014c58  mov     ecx, [rbp+30h+arg_30]
0x140014c5b  add     r8, 8
0x140014c5f  mov     [rbp+30h+var_68], rax
0x140014c63  mov     rax, [rdi+58h]
0x140014c67  mov     [rbp+30h+var_60], rax
0x140014c6b  mov     eax, [rdi+50h]
0x140014c6e  mov     [rbp+30h+var_A8], eax
0x140014c71  mov     rax, [rdi+48h]
0x140014c75  mov     [rbp+30h+var_58], rax
0x140014c79  mov     eax, [rdi+20h]
0x140014c7c  mov     [rbp+30h+var_A4], eax
0x140014c7f  mov     rax, [rdi+18h]
0x140014c83  mov     [rbp+30h+var_50], rax
0x140014c87  mov     eax, [rdi]
0x140014c89  mov     [rbp+30h+var_A0], eax
0x140014c8c  mov     rax, [rdi+80h]
0x140014c93  mov     [rbp+30h+var_48], rax
0x140014c97  mov     eax, [rdi+40h]
0x140014c9a  mov     [rbp+30h+var_9C], eax
0x140014c9d  mov     rax, [rdi+38h]
0x140014ca1  mov     [rbp+30h+var_40], rax
0x140014ca5  mov     eax, [rdi+8]
0x140014ca8  mov     [rbp+30h+var_98], eax
0x140014cab  lea     rax, [rbp+30h+arg_0]
0x140014caf  mov     [rsp+180h+var_B8], rax
0x140014cb7  lea     rax, [rbp+30h+var_94]
0x140014cbb  mov     [rsp+180h+var_C0], rax
0x140014cc3  lea     rax, [rbp+30h+var_90]
0x140014cc7  mov     [rsp+180h+var_C8], rax
0x140014ccf  lea     rax, [rbp+30h+var_8C]
0x140014cd3  mov     [rsp+180h+var_D0], rax
0x140014cdb  lea     rax, [rbp+30h+var_88]
0x140014cdf  mov     [rsp+180h+var_D8], rax
0x140014ce7  lea     rax, [rbp+30h+var_B0]
0x140014ceb  mov     [rsp+180h+var_E0], rax
0x140014cf3  lea     rax, [rbp+30h+var_78]
0x140014cf7  mov     [rsp+180h+var_E8], rax
0x140014cff  lea     rax, [rbp+30h+var_70]
0x140014d03  mov     [rsp+180h+var_F0], rax
0x140014d0b  lea     rax, [rbp+30h+var_AC]
0x140014d0f  mov     [rsp+180h+var_F8], rax
0x140014d17  lea     rax, [rbp+30h+var_68]
0x140014d1b  mov     [rsp+180h+var_100], rax
0x140014d23  lea     rax, [rbp+30h+var_60]
0x140014d27  mov     [rsp+180h+var_108], rax
0x140014d2c  lea     rax, [rbp+30h+var_A8]
0x140014d30  mov     [rsp+180h+var_110], rax
0x140014d35  lea     rax, [rbp+30h+var_58]
0x140014d39  mov     [rsp+180h+var_118], rax
0x140014d3e  lea     rax, [rbp+30h+var_A4]
0x140014d42  mov     [rsp+180h+var_120], rax
0x140014d47  lea     rax, [rbp+30h+var_50]
0x140014d4b  mov     [rsp+180h+var_128], rax
0x140014d50  lea     rax, [rbp+30h+var_A0]
0x140014d54  mov     [rsp+180h+var_130], rax
0x140014d59  lea     rax, [rbp+30h+var_48]
0x140014d5d  mov     [rsp+180h+var_138], rax
0x140014d62  lea     rax, [rbp+30h+var_9C]
0x140014d66  mov     [rsp+180h+var_140], rax
0x140014d6b  lea     rax, [rbp+30h+var_40]
0x140014d6f  mov     [rsp+180h+var_148], rax
0x140014d74  lea     rax, [rbp+30h+var_98]
0x140014d78  mov     [rsp+180h+var_150], rax
0x140014d7d  mov     [rbp+30h+arg_0], ecx
0x140014d80  mov     [rbp+30h+var_8C], esi
0x140014d83  mov     [rbp+30h+var_88], r14d
0x140014d87  mov     [rbp+30h+var_B0], r15d
0x140014d8b  mov     [rbp+30h+var_38], 1000000h
0x140014d93  mov     [rbp+30h+var_80], 0
0x140014d9b  lea     rax, [rbp+30h+var_38]
0x140014d9f  mov     rcx, r9
0x140014da2  mov     [rsp+180h+var_158], rax
0x140014da7  lea     rdx, byte_140026673
0x140014dae  lea     rax, [rbp+30h+var_80]
0x140014db2  mov     [rsp+180h+var_160], rax
0x140014db7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140014dbc  jmp     loc_140014E93
0x140014dc1  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140014dc6  call    ?Provider@CredUIBrokerLogging@@SAPEBU_tlgProvider_t@@XZ; CredUIBrokerLogging::Provider(void)
0x140014dcb  mov     rdi, rax
0x140014dce  mov     ecx, [rax]
0x140014dd0  cmp     ecx, 5
0x140014dd3  jbe     loc_140014E93
0x140014dd9  mov     rdx, 200000000000h
0x140014de3  mov     rcx, rax
0x140014de6  call    _tlgKeywordOn
0x140014deb  test    al, al
0x140014ded  jz      loc_140014E93
0x140014df3  mov     eax, [rbp+30h+arg_28]
0x140014df6  mov     ecx, [rbp+30h+arg_30]
0x140014df9  mov     [rbp+30h+var_98], eax
0x140014dfc  mov     eax, [rbp+30h+arg_20]
0x140014dff  mov     [rbp+30h+var_9C], eax
0x140014e02  mov     [rbp+30h+arg_0], ecx
0x140014e05  mov     [rbp+30h+var_A0], esi
0x140014e08  mov     [rbp+30h+var_A4], r14d
0x140014e0c  mov     [rbp+30h+var_A8], r15d
0x140014e10  call    cs:__imp_GetCurrentThreadId
0x140014e16  mov     r8, [rbx+110h]
0x140014e1d  lea     rdx, unk_1400250A0
0x140014e24  mov     [rbp+30h+var_AC], eax
0x140014e27  mov     rcx, rdi
0x140014e2a  mov     eax, [r8+48h]
0x140014e2e  add     r8, 8
0x140014e32  mov     [rbp+30h+var_B0], eax
0x140014e35  lea     rax, [rbp+30h+arg_0]
0x140014e39  mov     [rsp+180h+var_120], rax
0x140014e3e  lea     rax, [rbp+30h+var_98]
0x140014e42  mov     [rsp+180h+var_128], rax
0x140014e47  lea     rax, [rbp+30h+var_9C]
0x140014e4b  mov     [rsp+180h+var_130], rax
0x140014e50  lea     rax, [rbp+30h+var_A0]
0x140014e54  mov     [rsp+180h+var_138], rax
0x140014e59  lea     rax, [rbp+30h+var_A4]
0x140014e5d  mov     [rsp+180h+var_140], rax
0x140014e62  lea     rax, [rbp+30h+var_A8]
0x140014e66  mov     [rsp+180h+var_148], rax
0x140014e6b  lea     rax, [rbp+30h+var_AC]
0x140014e6f  mov     [rsp+180h+var_150], rax
0x140014e74  lea     rax, [rbp+30h+var_B0]
0x140014e78  mov     [rsp+180h+var_158], rax
0x140014e7d  lea     rax, [rbp+30h+var_80]
0x140014e81  mov     [rsp+180h+var_160], rax
0x140014e86  mov     [rbp+30h+var_80], 0
0x140014e8e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140014e93  mov     rcx, rbx
0x140014e96  add     rsp, 158h
0x140014e9d  pop     r15
0x140014e9f  pop     r14
0x140014ea1  pop     rdi
0x140014ea2  pop     rsi
0x140014ea3  pop     rbx
0x140014ea4  pop     rbp
0x140014ea5  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
