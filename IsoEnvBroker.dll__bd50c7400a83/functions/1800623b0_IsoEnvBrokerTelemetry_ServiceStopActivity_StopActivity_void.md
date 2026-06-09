# IsoEnvBrokerTelemetry::ServiceStopActivity::StopActivity(void)

- ea: `0x1800623b0`
- end: `0x180062634`
- name: `?StopActivity@ServiceStopActivity@IsoEnvBrokerTelemetry@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(IsoEnvBrokerTelemetry::ServiceStopActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001098`
- `0x18000176c`
- `0x180011d64`
- `0x18006019c`
- `0x18006075c`
- `0x1800623b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006240a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006259c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006240a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006259c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800625d4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800625d4`

## pseudocode

```c
void __fastcall IsoEnvBrokerTelemetry::ServiceStopActivity::StopActivity(
        IsoEnvBrokerTelemetry::ServiceStopActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r8
  RTL_SRWLOCK *v8; // rcx
  __int64 v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  const WCHAR *v15; // [rsp+A8h] [rbp-11h] BYREF
  const wchar_t *v16; // [rsp+B0h] [rbp-9h] BYREF
  const WCHAR *v17; // [rsp+B8h] [rbp-1h] BYREF
  const wchar_t *v18; // [rsp+C0h] [rbp+7h] BYREF
  const wchar_t *v19; // [rsp+C8h] [rbp+Fh] BYREF
  const WCHAR *v20; // [rsp+D0h] [rbp+17h] BYREF
  const wchar_t *v21; // [rsp+D8h] [rbp+1Fh] BYREF
  const wchar_t *v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = *((_QWORD *)IsoEnvBrokerLogging::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x200000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      v7 = *((_QWORD *)this + 34);
      v15 = (const WCHAR *)*((_QWORD *)v4 + 15);
      v16 = (const wchar_t *)*((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v17 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v18 = (const wchar_t *)*((_QWORD *)v4 + 11);
      v26 = v4[20];
      v19 = (const wchar_t *)*((_QWORD *)v4 + 9);
      LODWORD(v27) = v4[8];
      v20 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v28 = *v4;
      v21 = (const wchar_t *)*((_QWORD *)v4 + 16);
      v13 = v4[16];
      v22 = (const wchar_t *)*((_QWORD *)v4 + 7);
      v14 = v4[2];
      v23 = 0x1000000;
      v24[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
        v6,
        (__int64)byte_1800ABF2B,
        v7 + 8,
        v6,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v14,
        &v22,
        (__int64)&v13,
        &v21,
        (__int64)&v28,
        &v20,
        (__int64)&v27,
        &v19,
        (__int64)&v26,
        &v18,
        &v17,
        (__int64)&SRWLock,
        &v16,
        &v15);
    }
  }
  else
  {
    wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v8 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    v9 = *((_QWORD *)IsoEnvBrokerLogging::Instance() + 1);
    if ( *(_DWORD *)v9 > 5u
      && (*(_QWORD *)(v9 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x200000000000LL) == *(_QWORD *)(v9 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v26 = *(_DWORD *)(v11 + 72);
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (__int64)&byte_1800ABED7,
        v11 + 8,
        v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800623b0  push    rbp
0x1800623b2  push    rbx
0x1800623b3  push    rdi
0x1800623b4  lea     rbp, [rsp-47h]
0x1800623b9  sub     rsp, 100h
0x1800623c0  mov     rdi, [rcx+110h]
0x1800623c7  mov     rbx, rcx
0x1800623ca  mov     eax, [rdi+48h]
0x1800623cd  test    eax, eax
0x1800623cf  jns     loc_18006257D
0x1800623d5  add     rdi, 50h ; 'P'
0x1800623d9  cmp     eax, [rdi+8]
0x1800623dc  jnz     loc_18006257D
0x1800623e2  test    rdi, rdi
0x1800623e5  jz      loc_18006257D
0x1800623eb  lea     rdx, [rbp+57h+SRWLock]
0x1800623ef  call    ?LockExclusive@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800623f4  mov     rax, [rbx+110h]
0x1800623fb  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800623ff  mov     dword ptr [rax], 2
0x180062405  test    rcx, rcx
0x180062408  jz      short loc_180062410
0x18006240a  call    cs:__imp_ReleaseSRWLockExclusive
0x180062410  call    ?Instance@IsoEnvBrokerLogging@@KAPEAV1@XZ; IsoEnvBrokerLogging::Instance(void)
0x180062415  mov     r9, [rax+8]
0x180062419  mov     eax, [r9]
0x18006241c  cmp     eax, 5
0x18006241f  jbe     loc_180062622
0x180062425  mov     rdx, [r9+18h]
0x180062429  mov     rcx, 200000000000h
0x180062433  mov     rax, [r9+10h]
0x180062437  test    rcx, rax
0x18006243a  jz      loc_180062622
0x180062440  mov     rax, rdx
0x180062443  and     rax, rcx
0x180062446  cmp     rax, rdx
0x180062449  jnz     loc_180062622
0x18006244f  mov     rax, [rdi+78h]
0x180062453  lea     rdx, byte_1800ABF2B
0x18006245a  mov     r8, [rbx+110h]
0x180062461  mov     rcx, r9
0x180062464  mov     [rbp+57h+var_68], rax
0x180062468  add     r8, 8
0x18006246c  mov     rax, [rdi+70h]
0x180062470  mov     [rbp+57h+var_60], rax
0x180062474  mov     eax, [rdi+68h]
0x180062477  mov     dword ptr [rbp+57h+SRWLock], eax
0x18006247a  mov     rax, [rdi+60h]
0x18006247e  mov     [rbp+57h+var_58], rax
0x180062482  mov     rax, [rdi+58h]
0x180062486  mov     [rbp+57h+var_50], rax
0x18006248a  mov     eax, [rdi+50h]
0x18006248d  mov     [rbp+57h+arg_8], eax
0x180062490  mov     rax, [rdi+48h]
0x180062494  mov     [rbp+57h+var_48], rax
0x180062498  mov     eax, [rdi+20h]
0x18006249b  mov     dword ptr [rbp+57h+arg_10], eax
0x18006249e  mov     rax, [rdi+18h]
0x1800624a2  mov     [rbp+57h+var_40], rax
0x1800624a6  mov     eax, [rdi]
0x1800624a8  mov     [rbp+57h+arg_18], eax
0x1800624ab  mov     rax, [rdi+80h]
0x1800624b2  mov     [rbp+57h+var_38], rax
0x1800624b6  mov     eax, [rdi+40h]
0x1800624b9  mov     [rbp+57h+var_70], eax
0x1800624bc  mov     rax, [rdi+38h]
0x1800624c0  mov     [rbp+57h+var_30], rax
0x1800624c4  mov     eax, [rdi+8]
0x1800624c7  mov     [rbp+57h+var_6C], eax
0x1800624ca  mov     eax, 1000000h
0x1800624cf  mov     [rbp+57h+var_28], rax
0x1800624d3  mov     [rbp+57h+var_20], rax
0x1800624d7  lea     rax, [rbp+57h+var_68]
0x1800624db  mov     [rsp+110h+var_78], rax
0x1800624e3  lea     rax, [rbp+57h+var_60]
0x1800624e7  mov     [rsp+110h+var_80], rax
0x1800624ef  lea     rax, [rbp+57h+SRWLock]
0x1800624f3  mov     [rsp+110h+var_88], rax
0x1800624fb  lea     rax, [rbp+57h+var_58]
0x1800624ff  mov     [rsp+110h+var_90], rax
0x180062507  lea     rax, [rbp+57h+var_50]
0x18006250b  mov     [rsp+110h+var_98], rax
0x180062510  lea     rax, [rbp+57h+arg_8]
0x180062514  mov     [rsp+110h+var_A0], rax
0x180062519  lea     rax, [rbp+57h+var_48]
0x18006251d  mov     [rsp+110h+var_A8], rax
0x180062522  lea     rax, [rbp+57h+arg_10]
0x180062526  mov     [rsp+110h+var_B0], rax
0x18006252b  lea     rax, [rbp+57h+var_40]
0x18006252f  mov     [rsp+110h+var_B8], rax
0x180062534  lea     rax, [rbp+57h+arg_18]
0x180062538  mov     [rsp+110h+var_C0], rax
0x18006253d  lea     rax, [rbp+57h+var_38]
0x180062541  mov     [rsp+110h+var_C8], rax
0x180062546  lea     rax, [rbp+57h+var_70]
0x18006254a  mov     [rsp+110h+var_D0], rax
0x18006254f  lea     rax, [rbp+57h+var_30]
0x180062553  mov     [rsp+110h+var_D8], rax
0x180062558  lea     rax, [rbp+57h+var_6C]
0x18006255c  mov     [rsp+110h+var_E0], rax
0x180062561  lea     rax, [rbp+57h+var_28]
0x180062565  mov     [rsp+110h+var_E8], rax
0x18006256a  lea     rax, [rbp+57h+var_20]
0x18006256e  mov     [rsp+110h+var_F0], rax
0x180062573  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180062578  jmp     loc_180062622
0x18006257d  lea     rdx, [rbp+57h+SRWLock]
0x180062581  call    ?LockExclusive@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180062586  mov     rax, [rbx+110h]
0x18006258d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180062591  mov     dword ptr [rax], 2
0x180062597  test    rcx, rcx
0x18006259a  jz      short loc_1800625A2
0x18006259c  call    cs:__imp_ReleaseSRWLockExclusive
0x1800625a2  call    ?Instance@IsoEnvBrokerLogging@@KAPEAV1@XZ; IsoEnvBrokerLogging::Instance(void)
0x1800625a7  mov     rdi, [rax+8]
0x1800625ab  mov     eax, [rdi]
0x1800625ad  cmp     eax, 5
0x1800625b0  jbe     short loc_180062622
0x1800625b2  mov     rdx, [rdi+18h]
0x1800625b6  mov     rcx, 200000000000h
0x1800625c0  mov     rax, [rdi+10h]
0x1800625c4  test    rcx, rax
0x1800625c7  jz      short loc_180062622
0x1800625c9  mov     rax, rdx
0x1800625cc  and     rax, rcx
0x1800625cf  cmp     rax, rdx
0x1800625d2  jnz     short loc_180062622
0x1800625d4  call    cs:__imp_GetCurrentThreadId
0x1800625da  mov     r8, [rbx+110h]
0x1800625e1  lea     rdx, byte_1800ABED7
0x1800625e8  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800625eb  mov     rcx, rdi
0x1800625ee  mov     eax, [r8+48h]
0x1800625f2  add     r8, 8
0x1800625f6  mov     [rbp+57h+arg_8], eax
0x1800625f9  mov     eax, 1000000h
0x1800625fe  mov     [rbp+57h+arg_10], rax
0x180062602  lea     rax, [rbp+57h+SRWLock]
0x180062606  mov     [rsp+110h+var_E0], rax
0x18006260b  lea     rax, [rbp+57h+arg_8]
0x18006260f  mov     [rsp+110h+var_E8], rax
0x180062614  lea     rax, [rbp+57h+arg_10]
0x180062618  mov     [rsp+110h+var_F0], rax
0x18006261d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180062622  mov     rcx, rbx
0x180062625  add     rsp, 100h
0x18006262c  pop     rdi
0x18006262d  pop     rbx
0x18006262e  pop     rbp
0x18006262f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
