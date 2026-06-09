# SpeechOneSettingsTelemetry::LifeTime::ActivityContainer::LifeTime::Stop(unsigned __int64)

- ea: `0x140019314`
- end: `0x140019673`
- name: `?Stop@LifeTime@ActivityContainer@1SpeechOneSettingsTelemetry@@QEAAX_K@Z`
- size: `863`
- prototype: `void __fastcall(SpeechOneSettingsTelemetry::LifeTime::ActivityContainer::LifeTime *this, RTL_SRWLOCK *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140019970`

## callees

- `0x14000176c`
- `0x140001968`
- `0x140002600`
- `0x140018050`
- `0x140018914`
- `0x140019314`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019380`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019523`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019380`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019523`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001956a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140019601`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001956a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140019601`

## string_xrefs

- `0x14001961f`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
void __fastcall SpeechOneSettingsTelemetry::LifeTime::ActivityContainer::LifeTime::Stop(
        SpeechOneSettingsTelemetry::LifeTime::ActivityContainer::LifeTime *this,
        RTL_SRWLOCK *a2)
{
  __int64 v4; // rdi
  int v5; // eax
  int *v6; // rdi
  const struct _tlgProvider_t *v7; // rax
  __int64 v8; // r9
  __int64 v9; // rax
  const struct _tlgProvider_t *v10; // rax
  const struct _tlgProvider_t *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // r8
  char *v14; // rbx
  __int64 *v15; // rcx
  __int64 v16; // rax
  int v17; // [rsp+B0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+B8h] [rbp-78h] BYREF
  PSRWLOCK v19; // [rsp+C0h] [rbp-70h] BYREF
  int v20; // [rsp+C8h] [rbp-68h] BYREF
  int v21; // [rsp+CCh] [rbp-64h] BYREF
  int v22; // [rsp+D0h] [rbp-60h] BYREF
  int v23; // [rsp+D4h] [rbp-5Ch] BYREF
  __int64 v24; // [rsp+D8h] [rbp-58h] BYREF
  RTL_SRWLOCK *v25; // [rsp+E0h] [rbp-50h] BYREF
  const size_t *v26; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v27; // [rsp+F0h] [rbp-40h] BYREF
  const size_t *v28; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v29; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v30; // [rsp+108h] [rbp-28h] BYREF
  const size_t *v31; // [rsp+110h] [rbp-20h] BYREF
  const unsigned __int16 *v32; // [rsp+118h] [rbp-18h] BYREF
  const unsigned __int16 *v33; // [rsp+120h] [rbp-10h] BYREF
  _BYTE v34[32]; // [rsp+130h] [rbp+0h] BYREF
  __int64 *v35; // [rsp+150h] [rbp+20h]
  __int64 v36; // [rsp+158h] [rbp+28h]
  int *v37; // [rsp+160h] [rbp+30h]
  __int64 v38; // [rsp+168h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+170h] [rbp+40h]
  __int64 v40; // [rsp+178h] [rbp+48h]
  PSRWLOCK *v41; // [rsp+180h] [rbp+50h]
  __int64 v42; // [rsp+188h] [rbp+58h]
  void *retaddr; // [rsp+1C8h] [rbp+98h]

  v4 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v4 + 72);
  if ( v5 < 0 && (v6 = (int *)(v4 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v7 = FlightDataRecorderActivityClass::Provider();
    v8 = (__int64)v7;
    if ( *(_DWORD *)v7 > 5u )
    {
      v9 = *((_QWORD *)v7 + 3);
      if ( (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0 && (v9 & 0x400000000000LL) == v9 )
      {
        v25 = a2;
        v26 = (const size_t *)*((_QWORD *)v6 + 15);
        v27 = (const unsigned __int16 *)*((_QWORD *)v6 + 14);
        v20 = v6[26];
        v28 = (const size_t *)*((_QWORD *)v6 + 12);
        v29 = (const unsigned __int16 *)*((_QWORD *)v6 + 11);
        v21 = v6[20];
        v30 = (const unsigned __int16 *)*((_QWORD *)v6 + 9);
        v22 = v6[8];
        v31 = (const size_t *)*((_QWORD *)v6 + 3);
        v23 = *v6;
        v32 = (const unsigned __int16 *)*((_QWORD *)v6 + 16);
        v17 = v6[16];
        v33 = (const unsigned __int16 *)*((_QWORD *)v6 + 7);
        LODWORD(SRWLock) = v6[2];
        v24 = 0x1000000;
        v19 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
          v8,
          (__int64)&byte_14002A67F,
          *((_QWORD *)this + 34) + 8LL,
          v8,
          (__int64)&v19,
          (__int64)&v24,
          (__int64)&SRWLock,
          &v33,
          (__int64)&v17,
          &v32,
          (__int64)&v23,
          &v31,
          (__int64)&v22,
          &v30,
          (__int64)&v21,
          &v29,
          &v28,
          (__int64)&v20,
          &v27,
          &v26,
          (__int64)&v25);
      }
    }
  }
  else
  {
    wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v19);
    **((_DWORD **)this + 34) = 2;
    if ( v19 )
      ReleaseSRWLockExclusive(v19);
    v10 = FlightDataRecorderActivityClass::Provider();
    v11 = v10;
    if ( *(_DWORD *)v10 > 5u )
    {
      v12 = *((_QWORD *)v10 + 3);
      if ( (*((_QWORD *)v11 + 2) & 0x400000000000LL) != 0 && (v12 & 0x400000000000LL) == v12 )
      {
        v19 = a2;
        LODWORD(SRWLock) = GetCurrentThreadId();
        v13 = *((_QWORD *)this + 34);
        v17 = *(_DWORD *)(v13 + 72);
        v24 = 0;
        v41 = &v19;
        v42 = 8;
        p_SRWLock = &SRWLock;
        v40 = 4;
        v37 = &v17;
        v38 = 4;
        v35 = &v24;
        v36 = 8;
        tlgWriteTransfer_EventWriteTransfer(v11, byte_14002A55B, v13 + 8, 0, 6, v34);
      }
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v14 = (char *)this + 288;
    if ( *((_DWORD *)v14 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v14 + 6) = 0;
    v15 = *(__int64 **)v14;
    while ( 1 )
    {
      v16 = *v15;
      if ( !*v15 )
        break;
      if ( (char *)v16 == v14 )
      {
        *v15 = *((_QWORD *)v14 + 2);
        break;
      }
      v15 = (__int64 *)(v16 + 16);
      *(_QWORD *)v14 = v16 + 16;
    }
    *(_QWORD *)v14 = 0;
  }
}

```

## disassembly

```asm
0x140019314  push    rbp
0x140019316  push    rbx
0x140019317  push    rsi
0x140019318  push    rdi
0x140019319  lea     rbp, [rsp-78h]
0x14001931e  sub     rsp, 1A8h
0x140019325  mov     rax, cs:__security_cookie
0x14001932c  xor     rax, rsp
0x14001932f  mov     [rbp+90h+var_30], rax
0x140019333  mov     rsi, rdx
0x140019336  mov     rbx, rcx
0x140019339  mov     rdi, [rcx+110h]
0x140019340  mov     eax, [rdi+48h]
0x140019343  test    eax, eax
0x140019345  jns     loc_140019504
0x14001934b  add     rdi, 50h ; 'P'
0x14001934f  cmp     eax, [rdi+8]
0x140019352  jnz     loc_140019504
0x140019358  test    rdi, rdi
0x14001935b  jz      loc_140019504
0x140019361  lea     rdx, [rbp+90h+SRWLock]
0x140019365  call    ?LockExclusive@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14001936a  mov     rax, [rbx+110h]
0x140019371  mov     dword ptr [rax], 2
0x140019377  mov     rcx, [rbp+90h+SRWLock]; SRWLock
0x14001937b  test    rcx, rcx
0x14001937e  jz      short loc_140019386
0x140019380  call    cs:__imp_ReleaseSRWLockExclusive
0x140019386  call    ?Provider@FlightDataRecorderActivityClass@@SAPEBU_tlgProvider_t@@XZ; FlightDataRecorderActivityClass::Provider(void)
0x14001938b  mov     r9, rax
0x14001938e  mov     ecx, [rax]
0x140019390  cmp     ecx, 5
0x140019393  jbe     loc_1400195F1
0x140019399  mov     rax, [rax+18h]
0x14001939d  mov     rcx, [r9+10h]
0x1400193a1  mov     rdx, 400000000000h
0x1400193ab  test    rdx, rcx
0x1400193ae  jz      loc_1400195F1
0x1400193b4  mov     rcx, rax
0x1400193b7  and     rcx, rdx
0x1400193ba  cmp     rcx, rax
0x1400193bd  jnz     loc_1400195F1
0x1400193c3  mov     [rbp+90h+var_E0], rsi
0x1400193c7  mov     rax, [rdi+78h]
0x1400193cb  mov     [rbp+90h+var_D8], rax
0x1400193cf  mov     rax, [rdi+70h]
0x1400193d3  mov     [rbp+90h+var_D0], rax
0x1400193d7  mov     eax, [rdi+68h]
0x1400193da  mov     [rbp+90h+var_F8], eax
0x1400193dd  mov     rax, [rdi+60h]
0x1400193e1  mov     [rbp+90h+var_C8], rax
0x1400193e5  mov     rax, [rdi+58h]
0x1400193e9  mov     [rbp+90h+var_C0], rax
0x1400193ed  mov     eax, [rdi+50h]
0x1400193f0  mov     [rbp+90h+var_F4], eax
0x1400193f3  mov     rax, [rdi+48h]
0x1400193f7  mov     [rbp+90h+var_B8], rax
0x1400193fb  mov     eax, [rdi+20h]
0x1400193fe  mov     [rbp+90h+var_F0], eax
0x140019401  mov     rax, [rdi+18h]
0x140019405  mov     [rbp+90h+var_B0], rax
0x140019409  mov     eax, [rdi]
0x14001940b  mov     [rbp+90h+var_EC], eax
0x14001940e  mov     rax, [rdi+80h]
0x140019415  mov     [rbp+90h+var_A8], rax
0x140019419  mov     eax, [rdi+40h]
0x14001941c  mov     [rbp+90h+var_110], eax
0x14001941f  mov     rax, [rdi+38h]
0x140019423  mov     [rbp+90h+var_A0], rax
0x140019427  mov     eax, [rdi+8]
0x14001942a  mov     dword ptr [rbp+90h+SRWLock], eax
0x14001942d  mov     [rbp+90h+var_E8], 1000000h
0x140019435  mov     [rbp+90h+var_100], 0
0x14001943d  mov     r8, [rbx+110h]
0x140019444  add     r8, 8
0x140019448  lea     rax, [rbp+90h+var_E0]
0x14001944c  mov     [rsp+1C0h+var_120], rax
0x140019454  lea     rax, [rbp+90h+var_D8]
0x140019458  mov     [rsp+1C0h+var_128], rax
0x140019460  lea     rax, [rbp+90h+var_D0]
0x140019464  mov     [rsp+1C0h+var_130], rax
0x14001946c  lea     rax, [rbp+90h+var_F8]
0x140019470  mov     [rsp+1C0h+var_138], rax
0x140019478  lea     rax, [rbp+90h+var_C8]
0x14001947c  mov     [rsp+1C0h+var_140], rax
0x140019484  lea     rax, [rbp+90h+var_C0]
0x140019488  mov     [rsp+1C0h+var_148], rax
0x14001948d  lea     rax, [rbp+90h+var_F4]
0x140019491  mov     [rsp+1C0h+var_150], rax
0x140019496  lea     rax, [rbp+90h+var_B8]
0x14001949a  mov     [rsp+1C0h+var_158], rax
0x14001949f  lea     rax, [rbp+90h+var_F0]
0x1400194a3  mov     [rsp+1C0h+var_160], rax
0x1400194a8  lea     rax, [rbp+90h+var_B0]
0x1400194ac  mov     [rsp+1C0h+var_168], rax
0x1400194b1  lea     rax, [rbp+90h+var_EC]
0x1400194b5  mov     [rsp+1C0h+var_170], rax
0x1400194ba  lea     rax, [rbp+90h+var_A8]
0x1400194be  mov     [rsp+1C0h+var_178], rax
0x1400194c3  lea     rax, [rbp+90h+var_110]
0x1400194c7  mov     [rsp+1C0h+var_180], rax
0x1400194cc  lea     rax, [rbp+90h+var_A0]
0x1400194d0  mov     [rsp+1C0h+var_188], rax
0x1400194d5  lea     rax, [rbp+90h+SRWLock]
0x1400194d9  mov     [rsp+1C0h+var_190], rax
0x1400194de  lea     rax, [rbp+90h+var_E8]
0x1400194e2  mov     [rsp+1C0h+var_198], rax
0x1400194e7  lea     rax, [rbp+90h+var_100]
0x1400194eb  mov     [rsp+1C0h+var_1A0], rax
0x1400194f0  lea     rdx, byte_14002A67F
0x1400194f7  mov     rcx, r9
0x1400194fa  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564563@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1400194ff  jmp     loc_1400195F1
0x140019504  lea     rdx, [rbp+90h+var_100]
0x140019508  call    ?LockExclusive@?$ActivityBase@VFlightDataRecorderActivityClass@@$0A@$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FlightDataRecorderActivityClass,0,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14001950d  mov     rax, [rbx+110h]
0x140019514  mov     dword ptr [rax], 2
0x14001951a  mov     rcx, [rbp+90h+var_100]; SRWLock
0x14001951e  test    rcx, rcx
0x140019521  jz      short loc_140019529
0x140019523  call    cs:__imp_ReleaseSRWLockExclusive
0x140019529  call    ?Provider@FlightDataRecorderActivityClass@@SAPEBU_tlgProvider_t@@XZ; FlightDataRecorderActivityClass::Provider(void)
0x14001952e  mov     rdi, rax
0x140019531  mov     ecx, [rax]
0x140019533  cmp     ecx, 5
0x140019536  jbe     loc_1400195F1
0x14001953c  mov     rax, [rax+18h]
0x140019540  mov     rcx, [rdi+10h]
0x140019544  mov     rdx, 400000000000h
0x14001954e  test    rdx, rcx
0x140019551  jz      loc_1400195F1
0x140019557  mov     rcx, rax
0x14001955a  and     rcx, rdx
0x14001955d  cmp     rcx, rax
0x140019560  jnz     loc_1400195F1
0x140019566  mov     [rbp+90h+var_100], rsi
0x14001956a  call    cs:__imp_GetCurrentThreadId
0x140019570  mov     dword ptr [rbp+90h+SRWLock], eax
0x140019573  mov     r8, [rbx+110h]
0x14001957a  mov     eax, [r8+48h]
0x14001957e  mov     [rbp+90h+var_110], eax
0x140019581  mov     [rbp+90h+var_E8], 0
0x140019589  lea     rax, [rbp+90h+var_100]
0x14001958d  mov     [rbp+90h+var_40], rax
0x140019591  mov     [rbp+90h+var_38], 8
0x140019599  lea     rax, [rbp+90h+SRWLock]
0x14001959d  mov     [rbp+90h+var_50], rax
0x1400195a1  mov     [rbp+90h+var_48], 4
0x1400195a9  lea     rax, [rbp+90h+var_110]
0x1400195ad  mov     [rbp+90h+var_60], rax
0x1400195b1  mov     [rbp+90h+var_58], 4
0x1400195b9  lea     rax, [rbp+90h+var_E8]
0x1400195bd  mov     [rbp+90h+var_70], rax
0x1400195c1  mov     [rbp+90h+var_68], 8
0x1400195c9  add     r8, 8
0x1400195cd  lea     rax, [rbp+90h+var_90]
0x1400195d1  mov     [rsp+1C0h+var_198], rax
0x1400195d6  mov     dword ptr [rsp+1C0h+var_1A0], 6
0x1400195de  xor     r9d, r9d
0x1400195e1  lea     rdx, byte_14002A55B
0x1400195e8  mov     rcx, rdi
0x1400195eb  call    _tlgWriteTransfer_EventWriteTransfer
0x1400195f0  nop
0x1400195f1  cmp     dword ptr [rbx+138h], 0
0x1400195f8  jz      short loc_14001965B
0x1400195fa  add     rbx, 120h
0x140019601  call    cs:__imp_GetCurrentThreadId
0x140019607  cmp     [rbx+18h], eax
0x14001960a  jz      short loc_14001962B
0x14001960c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x140019613  test    rax, rax
0x140019616  jz      short loc_14001962B
0x140019618  mov     rdx, [rbp+98h]
0x14001961f  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x140019626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001962b  mov     dword ptr [rbx+18h], 0
0x140019632  mov     rcx, [rbx]
0x140019635  jmp     short loc_140019643
0x140019637  cmp     rax, rbx
0x14001963a  jz      short loc_14001964D
0x14001963c  lea     rcx, [rax+10h]
0x140019640  mov     [rbx], rcx
0x140019643  mov     rax, [rcx]
0x140019646  test    rax, rax
0x140019649  jnz     short loc_140019637
0x14001964b  jmp     short loc_140019654
0x14001964d  mov     rax, [rbx+10h]
0x140019651  mov     [rcx], rax
0x140019654  mov     qword ptr [rbx], 0
0x14001965b  mov     rcx, [rbp+90h+var_30]
0x14001965f  xor     rcx, rsp; StackCookie
0x140019662  call    __security_check_cookie
0x140019667  add     rsp, 1A8h
0x14001966e  pop     rdi
0x14001966f  pop     rsi
0x140019670  pop     rbx
0x140019671  pop     rbp
0x140019672  retn
```
