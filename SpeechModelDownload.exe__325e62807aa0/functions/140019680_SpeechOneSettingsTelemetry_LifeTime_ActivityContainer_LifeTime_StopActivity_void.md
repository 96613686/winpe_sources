# SpeechOneSettingsTelemetry::LifeTime::ActivityContainer::LifeTime::StopActivity(void)

- ea: `0x140019680`
- end: `0x140019967`
- name: `?StopActivity@LifeTime@ActivityContainer@1SpeechOneSettingsTelemetry@@MEAAXXZ`
- size: `743`
- prototype: `void __fastcall(SpeechOneSettingsTelemetry::LifeTime::ActivityContainer::LifeTime *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x140001008`
- `0x140001360`
- `0x140018050`
- `0x140018914`
- `0x140019680`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400196da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001986d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400196da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001986d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400198a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140019905`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400198a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140019905`

## string_xrefs

- `0x140019920`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall SpeechOneSettingsTelemetry::LifeTime::ActivityContainer::LifeTime::StopActivity(
        SpeechOneSettingsTelemetry::LifeTime::ActivityContainer::LifeTime *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  char *v12; // rbx
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // [rsp+A0h] [rbp-19h] BYREF
  int v16; // [rsp+A4h] [rbp-15h] BYREF
  const size_t *v17; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v18; // [rsp+B0h] [rbp-9h] BYREF
  const size_t *v19; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp+Fh] BYREF
  const size_t *v22; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v25; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v26[4]; // [rsp+F0h] [rbp+37h] BYREF
  void *retaddr; // [rsp+118h] [rbp+5Fh]
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v29; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v30; // [rsp+130h] [rbp+77h] BYREF
  int v31; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = FlightDataRecorderActivityClass::Provider();
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0 && (v7 & 0x400000000000LL) == v7 )
      {
        v17 = (const size_t *)*((_QWORD *)v4 + 15);
        v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v19 = (const size_t *)*((_QWORD *)v4 + 12);
        v20 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v29 = v4[20];
        v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        LODWORD(v30) = v4[8];
        v22 = (const size_t *)*((_QWORD *)v4 + 3);
        v31 = *v4;
        v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v15 = v4[16];
        v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        v16 = v4[2];
        v25 = 0x1000000;
        v26[0] = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (__int64)word_14002A852,
          *((_QWORD *)this + 34) + 8LL,
          v6,
          (__int64)v26,
          (__int64)&v25,
          (__int64)&v16,
          &v24,
          (__int64)&v15,
          &v23,
          (__int64)&v31,
          &v22,
          (__int64)&v30,
          &v21,
          (__int64)&v29,
          &v20,
          &v19,
          (__int64)&SRWLock,
          &v18,
          &v17);
      }
    }
  }
  else
  {
    wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v8 = FlightDataRecorderActivityClass::Provider();
    v9 = (__int64)v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v29 = *(_DWORD *)(v11 + 72);
        v30 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v9,
          (__int64)&byte_14002A5AF,
          v11 + 8,
          0,
          (__int64)&v30,
          (__int64)&v29,
          (__int64)&SRWLock);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v12 = (char *)this + 288;
    if ( *((_DWORD *)v12 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v12 + 6) = 0;
    v13 = *(__int64 **)v12;
    while ( 1 )
    {
      v14 = *v13;
      if ( !*v13 )
        break;
      if ( (char *)v14 == v12 )
      {
        *v13 = *((_QWORD *)v12 + 2);
        break;
      }
      v13 = (__int64 *)(v14 + 16);
      *(_QWORD *)v12 = v14 + 16;
    }
    *(_QWORD *)v12 = 0;
  }
}

```

## disassembly

```asm
0x140019680  push    rbp
0x140019682  push    rbx
0x140019683  push    rdi
0x140019684  lea     rbp, [rsp-47h]
0x140019689  sub     rsp, 100h
0x140019690  mov     rbx, rcx
0x140019693  mov     rdi, [rcx+110h]
0x14001969a  mov     eax, [rdi+48h]
0x14001969d  test    eax, eax
0x14001969f  jns     loc_14001984E
0x1400196a5  add     rdi, 50h ; 'P'
0x1400196a9  cmp     eax, [rdi+8]
0x1400196ac  jnz     loc_14001984E
0x1400196b2  test    rdi, rdi
0x1400196b5  jz      loc_14001984E
0x1400196bb  lea     rdx, [rbp+57h+SRWLock]
0x1400196bf  call    ?LockExclusive@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1400196c4  mov     rax, [rbx+110h]
0x1400196cb  mov     dword ptr [rax], 2
0x1400196d1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1400196d5  test    rcx, rcx
0x1400196d8  jz      short loc_1400196E0
0x1400196da  call    cs:__imp_ReleaseSRWLockExclusive
0x1400196e0  call    ?Provider@FlightDataRecorderActivityClass@@SAPEBU_tlgProvider_t@@XZ; FlightDataRecorderActivityClass::Provider(void)
0x1400196e5  mov     r9, rax
0x1400196e8  mov     ecx, [rax]
0x1400196ea  cmp     ecx, 5
0x1400196ed  jbe     loc_1400198F5
0x1400196f3  mov     rax, [rax+18h]
0x1400196f7  mov     rcx, [r9+10h]
0x1400196fb  mov     rdx, 400000000000h
0x140019705  test    rdx, rcx
0x140019708  jz      loc_1400198F5
0x14001970e  mov     rcx, rax
0x140019711  and     rcx, rdx
0x140019714  cmp     rcx, rax
0x140019717  jnz     loc_1400198F5
0x14001971d  mov     rax, [rdi+78h]
0x140019721  mov     [rbp+57h+var_68], rax
0x140019725  mov     rax, [rdi+70h]
0x140019729  mov     [rbp+57h+var_60], rax
0x14001972d  mov     eax, [rdi+68h]
0x140019730  mov     dword ptr [rbp+57h+SRWLock], eax
0x140019733  mov     rax, [rdi+60h]
0x140019737  mov     [rbp+57h+var_58], rax
0x14001973b  mov     rax, [rdi+58h]
0x14001973f  mov     [rbp+57h+var_50], rax
0x140019743  mov     eax, [rdi+50h]
0x140019746  mov     [rbp+57h+arg_8], eax
0x140019749  mov     rax, [rdi+48h]
0x14001974d  mov     [rbp+57h+var_48], rax
0x140019751  mov     eax, [rdi+20h]
0x140019754  mov     dword ptr [rbp+57h+arg_10], eax
0x140019757  mov     rax, [rdi+18h]
0x14001975b  mov     [rbp+57h+var_40], rax
0x14001975f  mov     eax, [rdi]
0x140019761  mov     [rbp+57h+arg_18], eax
0x140019764  mov     rax, [rdi+80h]
0x14001976b  mov     [rbp+57h+var_38], rax
0x14001976f  mov     eax, [rdi+40h]
0x140019772  mov     [rbp+57h+var_70], eax
0x140019775  mov     rax, [rdi+38h]
0x140019779  mov     [rbp+57h+var_30], rax
0x14001977d  mov     eax, [rdi+8]
0x140019780  mov     [rbp+57h+var_6C], eax
0x140019783  mov     [rbp+57h+var_28], 1000000h
0x14001978b  mov     [rbp+57h+var_20], 0
0x140019793  mov     r8, [rbx+110h]
0x14001979a  add     r8, 8
0x14001979e  lea     rax, [rbp+57h+var_68]
0x1400197a2  mov     [rsp+110h+var_78], rax
0x1400197aa  lea     rax, [rbp+57h+var_60]
0x1400197ae  mov     [rsp+110h+var_80], rax
0x1400197b6  lea     rax, [rbp+57h+SRWLock]
0x1400197ba  mov     [rsp+110h+var_88], rax
0x1400197c2  lea     rax, [rbp+57h+var_58]
0x1400197c6  mov     [rsp+110h+var_90], rax
0x1400197ce  lea     rax, [rbp+57h+var_50]
0x1400197d2  mov     [rsp+110h+var_98], rax
0x1400197d7  lea     rax, [rbp+57h+arg_8]
0x1400197db  mov     [rsp+110h+var_A0], rax
0x1400197e0  lea     rax, [rbp+57h+var_48]
0x1400197e4  mov     [rsp+110h+var_A8], rax
0x1400197e9  lea     rax, [rbp+57h+arg_10]
0x1400197ed  mov     [rsp+110h+var_B0], rax
0x1400197f2  lea     rax, [rbp+57h+var_40]
0x1400197f6  mov     [rsp+110h+var_B8], rax
0x1400197fb  lea     rax, [rbp+57h+arg_18]
0x1400197ff  mov     [rsp+110h+var_C0], rax
0x140019804  lea     rax, [rbp+57h+var_38]
0x140019808  mov     [rsp+110h+var_C8], rax
0x14001980d  lea     rax, [rbp+57h+var_70]
0x140019811  mov     [rsp+110h+var_D0], rax
0x140019816  lea     rax, [rbp+57h+var_30]
0x14001981a  mov     [rsp+110h+var_D8], rax
0x14001981f  lea     rax, [rbp+57h+var_6C]
0x140019823  mov     [rsp+110h+var_E0], rax
0x140019828  lea     rax, [rbp+57h+var_28]
0x14001982c  mov     [rsp+110h+var_E8], rax
0x140019831  lea     rax, [rbp+57h+var_20]
0x140019835  mov     [rsp+110h+var_F0], rax
0x14001983a  lea     rdx, word_14002A852
0x140019841  mov     rcx, r9
0x140019844  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140019849  jmp     loc_1400198F5
0x14001984e  lea     rdx, [rbp+57h+SRWLock]
0x140019852  call    ?LockExclusive@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140019857  mov     rax, [rbx+110h]
0x14001985e  mov     dword ptr [rax], 2
0x140019864  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x140019868  test    rcx, rcx
0x14001986b  jz      short loc_140019873
0x14001986d  call    cs:__imp_ReleaseSRWLockExclusive
0x140019873  call    ?Provider@FlightDataRecorderActivityClass@@SAPEBU_tlgProvider_t@@XZ; FlightDataRecorderActivityClass::Provider(void)
0x140019878  mov     rdi, rax
0x14001987b  mov     ecx, [rax]
0x14001987d  cmp     ecx, 5
0x140019880  jbe     short loc_1400198F5
0x140019882  mov     rax, [rax+18h]
0x140019886  mov     rcx, [rdi+10h]
0x14001988a  mov     rdx, 400000000000h
0x140019894  test    rdx, rcx
0x140019897  jz      short loc_1400198F5
0x140019899  mov     rcx, rax
0x14001989c  and     rcx, rdx
0x14001989f  cmp     rcx, rax
0x1400198a2  jnz     short loc_1400198F5
0x1400198a4  call    cs:__imp_GetCurrentThreadId
0x1400198aa  mov     dword ptr [rbp+57h+SRWLock], eax
0x1400198ad  mov     r8, [rbx+110h]
0x1400198b4  mov     eax, [r8+48h]
0x1400198b8  mov     [rbp+57h+arg_8], eax
0x1400198bb  mov     [rbp+57h+arg_10], 0
0x1400198c3  add     r8, 8
0x1400198c7  lea     rax, [rbp+57h+SRWLock]
0x1400198cb  mov     [rsp+110h+var_E0], rax
0x1400198d0  lea     rax, [rbp+57h+arg_8]
0x1400198d4  mov     [rsp+110h+var_E8], rax
0x1400198d9  lea     rax, [rbp+57h+arg_10]
0x1400198dd  mov     [rsp+110h+var_F0], rax
0x1400198e2  xor     r9d, r9d
0x1400198e5  lea     rdx, byte_14002A5AF
0x1400198ec  mov     rcx, rdi
0x1400198ef  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400198f4  nop
0x1400198f5  cmp     dword ptr [rbx+138h], 0
0x1400198fc  jz      short loc_14001995C
0x1400198fe  add     rbx, 120h
0x140019905  call    cs:__imp_GetCurrentThreadId
0x14001990b  cmp     [rbx+18h], eax
0x14001990e  jz      short loc_14001992C
0x140019910  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140019917  test    rax, rax
0x14001991a  jz      short loc_14001992C
0x14001991c  mov     rdx, [rbp+5Fh]
0x140019920  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140019927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001992c  mov     dword ptr [rbx+18h], 0
0x140019933  mov     rcx, [rbx]
0x140019936  jmp     short loc_140019944
0x140019938  cmp     rax, rbx
0x14001993b  jz      short loc_14001994E
0x14001993d  lea     rcx, [rax+10h]
0x140019941  mov     [rbx], rcx
0x140019944  mov     rax, [rcx]
0x140019947  test    rax, rax
0x14001994a  jnz     short loc_140019938
0x14001994c  jmp     short loc_140019955
0x14001994e  mov     rax, [rbx+10h]
0x140019952  mov     [rcx], rax
0x140019955  mov     qword ptr [rbx], 0
0x14001995c  add     rsp, 100h
0x140019963  pop     rdi
0x140019964  pop     rbx
0x140019965  pop     rbp
0x140019966  retn
```
