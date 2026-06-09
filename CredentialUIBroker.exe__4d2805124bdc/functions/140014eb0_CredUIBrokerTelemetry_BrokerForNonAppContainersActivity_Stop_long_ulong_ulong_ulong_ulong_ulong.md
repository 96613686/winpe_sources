# CredUIBrokerTelemetry::BrokerForNonAppContainersActivity::Stop(long,ulong,ulong,ulong,ulong,ulong)

- ea: `0x140014eb0`
- end: `0x1400151aa`
- name: `?Stop@BrokerForNonAppContainersActivity@CredUIBrokerTelemetry@@QEAAXJKKKKK@Z`
- size: `762`
- prototype: `void __fastcall(CredUIBrokerTelemetry::BrokerForNonAppContainersActivity *__hidden this, int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140010f10`

## callees

- `0x140001a30`
- `0x140002470`
- `0x140002f8c`
- `0x14000e620`
- `0x140011a40`
- `0x140014eb0`
- `0x14001c16c`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140015110`
- `KERNEL32!GetCurrentThreadId` at `0x140015110`

## pseudocode

```c
void __fastcall CredUIBrokerTelemetry::BrokerForNonAppContainersActivity::Stop(
        CredUIBrokerTelemetry::BrokerForNonAppContainersActivity *this,
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
        (__int64)byte_140024639,
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
        (__int64)&word_140026196,
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
0x140014eb0  push    rbp
0x140014eb2  push    rbx
0x140014eb3  push    rsi
0x140014eb4  push    rdi
0x140014eb5  push    r14
0x140014eb7  push    r15
0x140014eb9  lea     rbp, [rsp-8]
0x140014ebe  sub     rsp, 158h
0x140014ec5  mov     rdi, [rcx+110h]
0x140014ecc  mov     esi, r9d
0x140014ecf  mov     r14d, r8d
0x140014ed2  mov     r15d, edx
0x140014ed5  mov     rbx, rcx
0x140014ed8  mov     eax, [rdi+48h]
0x140014edb  test    eax, eax
0x140014edd  jns     loc_1400150C1
0x140014ee3  add     rdi, 50h ; 'P'
0x140014ee7  cmp     eax, [rdi+8]
0x140014eea  jnz     loc_1400150C1
0x140014ef0  test    rdi, rdi
0x140014ef3  jz      loc_1400150C1
0x140014ef9  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x140014efe  call    ?Provider@CredUIBrokerLogging@@SAPEBU_tlgProvider_t@@XZ; CredUIBrokerLogging::Provider(void)
0x140014f03  mov     r9, rax
0x140014f06  mov     ecx, [rax]
0x140014f08  cmp     ecx, 5
0x140014f0b  jbe     loc_140015193
0x140014f11  mov     rdx, 200000000000h
0x140014f1b  mov     rcx, rax
0x140014f1e  call    _tlgKeywordOn
0x140014f23  test    al, al
0x140014f25  jz      loc_140015193
0x140014f2b  mov     eax, [rbp+30h+arg_28]
0x140014f2e  mov     [rbp+30h+var_94], eax
0x140014f31  mov     eax, [rbp+30h+arg_20]
0x140014f34  mov     [rbp+30h+var_90], eax
0x140014f37  mov     rax, [rdi+78h]
0x140014f3b  mov     [rbp+30h+var_78], rax
0x140014f3f  mov     rax, [rdi+70h]
0x140014f43  mov     [rbp+30h+var_70], rax
0x140014f47  mov     eax, [rdi+68h]
0x140014f4a  mov     [rbp+30h+var_AC], eax
0x140014f4d  mov     rax, [rdi+60h]
0x140014f51  mov     r8, [rbx+110h]
0x140014f58  mov     ecx, [rbp+30h+arg_30]
0x140014f5b  add     r8, 8
0x140014f5f  mov     [rbp+30h+var_68], rax
0x140014f63  mov     rax, [rdi+58h]
0x140014f67  mov     [rbp+30h+var_60], rax
0x140014f6b  mov     eax, [rdi+50h]
0x140014f6e  mov     [rbp+30h+var_A8], eax
0x140014f71  mov     rax, [rdi+48h]
0x140014f75  mov     [rbp+30h+var_58], rax
0x140014f79  mov     eax, [rdi+20h]
0x140014f7c  mov     [rbp+30h+var_A4], eax
0x140014f7f  mov     rax, [rdi+18h]
0x140014f83  mov     [rbp+30h+var_50], rax
0x140014f87  mov     eax, [rdi]
0x140014f89  mov     [rbp+30h+var_A0], eax
0x140014f8c  mov     rax, [rdi+80h]
0x140014f93  mov     [rbp+30h+var_48], rax
0x140014f97  mov     eax, [rdi+40h]
0x140014f9a  mov     [rbp+30h+var_9C], eax
0x140014f9d  mov     rax, [rdi+38h]
0x140014fa1  mov     [rbp+30h+var_40], rax
0x140014fa5  mov     eax, [rdi+8]
0x140014fa8  mov     [rbp+30h+var_98], eax
0x140014fab  lea     rax, [rbp+30h+arg_0]
0x140014faf  mov     [rsp+180h+var_B8], rax
0x140014fb7  lea     rax, [rbp+30h+var_94]
0x140014fbb  mov     [rsp+180h+var_C0], rax
0x140014fc3  lea     rax, [rbp+30h+var_90]
0x140014fc7  mov     [rsp+180h+var_C8], rax
0x140014fcf  lea     rax, [rbp+30h+var_8C]
0x140014fd3  mov     [rsp+180h+var_D0], rax
0x140014fdb  lea     rax, [rbp+30h+var_88]
0x140014fdf  mov     [rsp+180h+var_D8], rax
0x140014fe7  lea     rax, [rbp+30h+var_B0]
0x140014feb  mov     [rsp+180h+var_E0], rax
0x140014ff3  lea     rax, [rbp+30h+var_78]
0x140014ff7  mov     [rsp+180h+var_E8], rax
0x140014fff  lea     rax, [rbp+30h+var_70]
0x140015003  mov     [rsp+180h+var_F0], rax
0x14001500b  lea     rax, [rbp+30h+var_AC]
0x14001500f  mov     [rsp+180h+var_F8], rax
0x140015017  lea     rax, [rbp+30h+var_68]
0x14001501b  mov     [rsp+180h+var_100], rax
0x140015023  lea     rax, [rbp+30h+var_60]
0x140015027  mov     [rsp+180h+var_108], rax
0x14001502c  lea     rax, [rbp+30h+var_A8]
0x140015030  mov     [rsp+180h+var_110], rax
0x140015035  lea     rax, [rbp+30h+var_58]
0x140015039  mov     [rsp+180h+var_118], rax
0x14001503e  lea     rax, [rbp+30h+var_A4]
0x140015042  mov     [rsp+180h+var_120], rax
0x140015047  lea     rax, [rbp+30h+var_50]
0x14001504b  mov     [rsp+180h+var_128], rax
0x140015050  lea     rax, [rbp+30h+var_A0]
0x140015054  mov     [rsp+180h+var_130], rax
0x140015059  lea     rax, [rbp+30h+var_48]
0x14001505d  mov     [rsp+180h+var_138], rax
0x140015062  lea     rax, [rbp+30h+var_9C]
0x140015066  mov     [rsp+180h+var_140], rax
0x14001506b  lea     rax, [rbp+30h+var_40]
0x14001506f  mov     [rsp+180h+var_148], rax
0x140015074  lea     rax, [rbp+30h+var_98]
0x140015078  mov     [rsp+180h+var_150], rax
0x14001507d  mov     [rbp+30h+arg_0], ecx
0x140015080  mov     [rbp+30h+var_8C], esi
0x140015083  mov     [rbp+30h+var_88], r14d
0x140015087  mov     [rbp+30h+var_B0], r15d
0x14001508b  mov     [rbp+30h+var_38], 1000000h
0x140015093  mov     [rbp+30h+var_80], 0
0x14001509b  lea     rax, [rbp+30h+var_38]
0x14001509f  mov     rcx, r9
0x1400150a2  mov     [rsp+180h+var_158], rax
0x1400150a7  lea     rdx, byte_140024639
0x1400150ae  lea     rax, [rbp+30h+var_80]
0x1400150b2  mov     [rsp+180h+var_160], rax
0x1400150b7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400150bc  jmp     loc_140015193
0x1400150c1  call    ?zInternalStop@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1400150c6  call    ?Provider@CredUIBrokerLogging@@SAPEBU_tlgProvider_t@@XZ; CredUIBrokerLogging::Provider(void)
0x1400150cb  mov     rdi, rax
0x1400150ce  mov     ecx, [rax]
0x1400150d0  cmp     ecx, 5
0x1400150d3  jbe     loc_140015193
0x1400150d9  mov     rdx, 200000000000h
0x1400150e3  mov     rcx, rax
0x1400150e6  call    _tlgKeywordOn
0x1400150eb  test    al, al
0x1400150ed  jz      loc_140015193
0x1400150f3  mov     eax, [rbp+30h+arg_28]
0x1400150f6  mov     ecx, [rbp+30h+arg_30]
0x1400150f9  mov     [rbp+30h+var_98], eax
0x1400150fc  mov     eax, [rbp+30h+arg_20]
0x1400150ff  mov     [rbp+30h+var_9C], eax
0x140015102  mov     [rbp+30h+arg_0], ecx
0x140015105  mov     [rbp+30h+var_A0], esi
0x140015108  mov     [rbp+30h+var_A4], r14d
0x14001510c  mov     [rbp+30h+var_A8], r15d
0x140015110  call    cs:__imp_GetCurrentThreadId
0x140015116  mov     r8, [rbx+110h]
0x14001511d  lea     rdx, word_140026196
0x140015124  mov     [rbp+30h+var_AC], eax
0x140015127  mov     rcx, rdi
0x14001512a  mov     eax, [r8+48h]
0x14001512e  add     r8, 8
0x140015132  mov     [rbp+30h+var_B0], eax
0x140015135  lea     rax, [rbp+30h+arg_0]
0x140015139  mov     [rsp+180h+var_120], rax
0x14001513e  lea     rax, [rbp+30h+var_98]
0x140015142  mov     [rsp+180h+var_128], rax
0x140015147  lea     rax, [rbp+30h+var_9C]
0x14001514b  mov     [rsp+180h+var_130], rax
0x140015150  lea     rax, [rbp+30h+var_A0]
0x140015154  mov     [rsp+180h+var_138], rax
0x140015159  lea     rax, [rbp+30h+var_A4]
0x14001515d  mov     [rsp+180h+var_140], rax
0x140015162  lea     rax, [rbp+30h+var_A8]
0x140015166  mov     [rsp+180h+var_148], rax
0x14001516b  lea     rax, [rbp+30h+var_AC]
0x14001516f  mov     [rsp+180h+var_150], rax
0x140015174  lea     rax, [rbp+30h+var_B0]
0x140015178  mov     [rsp+180h+var_158], rax
0x14001517d  lea     rax, [rbp+30h+var_80]
0x140015181  mov     [rsp+180h+var_160], rax
0x140015186  mov     [rbp+30h+var_80], 0
0x14001518e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140015193  mov     rcx, rbx
0x140015196  add     rsp, 158h
0x14001519d  pop     r15
0x14001519f  pop     r14
0x1400151a1  pop     rdi
0x1400151a2  pop     rsi
0x1400151a3  pop     rbx
0x1400151a4  pop     rbp
0x1400151a5  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
