# IsoEnvBrokerTelemetry::UnregisterObjectsActivity::StopActivity(void)

- ea: `0x180062640`
- end: `0x1800628c4`
- name: `?StopActivity@UnregisterObjectsActivity@IsoEnvBrokerTelemetry@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(IsoEnvBrokerTelemetry::UnregisterObjectsActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001098`
- `0x18000176c`
- `0x180011d64`
- `0x18006019c`
- `0x18006075c`
- `0x180062640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006269a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006282c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006269a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18006282c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062864`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062864`

## pseudocode

```c
void __fastcall IsoEnvBrokerTelemetry::UnregisterObjectsActivity::StopActivity(
        IsoEnvBrokerTelemetry::UnregisterObjectsActivity *this)
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
        (__int64)byte_1800ABB85,
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
        (__int64)byte_1800ABB2B,
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
0x180062640  push    rbp
0x180062642  push    rbx
0x180062643  push    rdi
0x180062644  lea     rbp, [rsp-47h]
0x180062649  sub     rsp, 100h
0x180062650  mov     rdi, [rcx+110h]
0x180062657  mov     rbx, rcx
0x18006265a  mov     eax, [rdi+48h]
0x18006265d  test    eax, eax
0x18006265f  jns     loc_18006280D
0x180062665  add     rdi, 50h ; 'P'
0x180062669  cmp     eax, [rdi+8]
0x18006266c  jnz     loc_18006280D
0x180062672  test    rdi, rdi
0x180062675  jz      loc_18006280D
0x18006267b  lea     rdx, [rbp+57h+SRWLock]
0x18006267f  call    ?LockExclusive@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180062684  mov     rax, [rbx+110h]
0x18006268b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18006268f  mov     dword ptr [rax], 2
0x180062695  test    rcx, rcx
0x180062698  jz      short loc_1800626A0
0x18006269a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800626a0  call    ?Instance@IsoEnvBrokerLogging@@KAPEAV1@XZ; IsoEnvBrokerLogging::Instance(void)
0x1800626a5  mov     r9, [rax+8]
0x1800626a9  mov     eax, [r9]
0x1800626ac  cmp     eax, 5
0x1800626af  jbe     loc_1800628B2
0x1800626b5  mov     rdx, [r9+18h]
0x1800626b9  mov     rcx, 200000000000h
0x1800626c3  mov     rax, [r9+10h]
0x1800626c7  test    rcx, rax
0x1800626ca  jz      loc_1800628B2
0x1800626d0  mov     rax, rdx
0x1800626d3  and     rax, rcx
0x1800626d6  cmp     rax, rdx
0x1800626d9  jnz     loc_1800628B2
0x1800626df  mov     rax, [rdi+78h]
0x1800626e3  lea     rdx, byte_1800ABB85
0x1800626ea  mov     r8, [rbx+110h]
0x1800626f1  mov     rcx, r9
0x1800626f4  mov     [rbp+57h+var_68], rax
0x1800626f8  add     r8, 8
0x1800626fc  mov     rax, [rdi+70h]
0x180062700  mov     [rbp+57h+var_60], rax
0x180062704  mov     eax, [rdi+68h]
0x180062707  mov     dword ptr [rbp+57h+SRWLock], eax
0x18006270a  mov     rax, [rdi+60h]
0x18006270e  mov     [rbp+57h+var_58], rax
0x180062712  mov     rax, [rdi+58h]
0x180062716  mov     [rbp+57h+var_50], rax
0x18006271a  mov     eax, [rdi+50h]
0x18006271d  mov     [rbp+57h+arg_8], eax
0x180062720  mov     rax, [rdi+48h]
0x180062724  mov     [rbp+57h+var_48], rax
0x180062728  mov     eax, [rdi+20h]
0x18006272b  mov     dword ptr [rbp+57h+arg_10], eax
0x18006272e  mov     rax, [rdi+18h]
0x180062732  mov     [rbp+57h+var_40], rax
0x180062736  mov     eax, [rdi]
0x180062738  mov     [rbp+57h+arg_18], eax
0x18006273b  mov     rax, [rdi+80h]
0x180062742  mov     [rbp+57h+var_38], rax
0x180062746  mov     eax, [rdi+40h]
0x180062749  mov     [rbp+57h+var_70], eax
0x18006274c  mov     rax, [rdi+38h]
0x180062750  mov     [rbp+57h+var_30], rax
0x180062754  mov     eax, [rdi+8]
0x180062757  mov     [rbp+57h+var_6C], eax
0x18006275a  mov     eax, 1000000h
0x18006275f  mov     [rbp+57h+var_28], rax
0x180062763  mov     [rbp+57h+var_20], rax
0x180062767  lea     rax, [rbp+57h+var_68]
0x18006276b  mov     [rsp+110h+var_78], rax
0x180062773  lea     rax, [rbp+57h+var_60]
0x180062777  mov     [rsp+110h+var_80], rax
0x18006277f  lea     rax, [rbp+57h+SRWLock]
0x180062783  mov     [rsp+110h+var_88], rax
0x18006278b  lea     rax, [rbp+57h+var_58]
0x18006278f  mov     [rsp+110h+var_90], rax
0x180062797  lea     rax, [rbp+57h+var_50]
0x18006279b  mov     [rsp+110h+var_98], rax
0x1800627a0  lea     rax, [rbp+57h+arg_8]
0x1800627a4  mov     [rsp+110h+var_A0], rax
0x1800627a9  lea     rax, [rbp+57h+var_48]
0x1800627ad  mov     [rsp+110h+var_A8], rax
0x1800627b2  lea     rax, [rbp+57h+arg_10]
0x1800627b6  mov     [rsp+110h+var_B0], rax
0x1800627bb  lea     rax, [rbp+57h+var_40]
0x1800627bf  mov     [rsp+110h+var_B8], rax
0x1800627c4  lea     rax, [rbp+57h+arg_18]
0x1800627c8  mov     [rsp+110h+var_C0], rax
0x1800627cd  lea     rax, [rbp+57h+var_38]
0x1800627d1  mov     [rsp+110h+var_C8], rax
0x1800627d6  lea     rax, [rbp+57h+var_70]
0x1800627da  mov     [rsp+110h+var_D0], rax
0x1800627df  lea     rax, [rbp+57h+var_30]
0x1800627e3  mov     [rsp+110h+var_D8], rax
0x1800627e8  lea     rax, [rbp+57h+var_6C]
0x1800627ec  mov     [rsp+110h+var_E0], rax
0x1800627f1  lea     rax, [rbp+57h+var_28]
0x1800627f5  mov     [rsp+110h+var_E8], rax
0x1800627fa  lea     rax, [rbp+57h+var_20]
0x1800627fe  mov     [rsp+110h+var_F0], rax
0x180062803  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x180062808  jmp     loc_1800628B2
0x18006280d  lea     rdx, [rbp+57h+SRWLock]
0x180062811  call    ?LockExclusive@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180062816  mov     rax, [rbx+110h]
0x18006281d  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180062821  mov     dword ptr [rax], 2
0x180062827  test    rcx, rcx
0x18006282a  jz      short loc_180062832
0x18006282c  call    cs:__imp_ReleaseSRWLockExclusive
0x180062832  call    ?Instance@IsoEnvBrokerLogging@@KAPEAV1@XZ; IsoEnvBrokerLogging::Instance(void)
0x180062837  mov     rdi, [rax+8]
0x18006283b  mov     eax, [rdi]
0x18006283d  cmp     eax, 5
0x180062840  jbe     short loc_1800628B2
0x180062842  mov     rdx, [rdi+18h]
0x180062846  mov     rcx, 200000000000h
0x180062850  mov     rax, [rdi+10h]
0x180062854  test    rcx, rax
0x180062857  jz      short loc_1800628B2
0x180062859  mov     rax, rdx
0x18006285c  and     rax, rcx
0x18006285f  cmp     rax, rdx
0x180062862  jnz     short loc_1800628B2
0x180062864  call    cs:__imp_GetCurrentThreadId
0x18006286a  mov     r8, [rbx+110h]
0x180062871  lea     rdx, byte_1800ABB2B
0x180062878  mov     dword ptr [rbp+57h+SRWLock], eax
0x18006287b  mov     rcx, rdi
0x18006287e  mov     eax, [r8+48h]
0x180062882  add     r8, 8
0x180062886  mov     [rbp+57h+arg_8], eax
0x180062889  mov     eax, 1000000h
0x18006288e  mov     [rbp+57h+arg_10], rax
0x180062892  lea     rax, [rbp+57h+SRWLock]
0x180062896  mov     [rsp+110h+var_E0], rax
0x18006289b  lea     rax, [rbp+57h+arg_8]
0x18006289f  mov     [rsp+110h+var_E8], rax
0x1800628a4  lea     rax, [rbp+57h+arg_10]
0x1800628a8  mov     [rsp+110h+var_F0], rax
0x1800628ad  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800628b2  mov     rcx, rbx
0x1800628b5  add     rsp, 100h
0x1800628bc  pop     rdi
0x1800628bd  pop     rbx
0x1800628be  pop     rbp
0x1800628bf  jmp     ?IgnoreCurrentThread@?$ActivityBase@VIsoEnvBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IsoEnvBrokerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
