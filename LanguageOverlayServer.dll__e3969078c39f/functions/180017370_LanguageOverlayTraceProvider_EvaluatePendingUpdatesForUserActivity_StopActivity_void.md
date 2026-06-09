# LanguageOverlayTraceProvider::EvaluatePendingUpdatesForUserActivity::StopActivity(void)

- ea: `0x180017370`
- end: `0x180017603`
- name: `?StopActivity@EvaluatePendingUpdatesForUserActivity@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::EvaluatePendingUpdatesForUserActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x180017370`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800173ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001755f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800173ca`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001755f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017597`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017597`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::EvaluatePendingUpdatesForUserActivity::StopActivity(
        LanguageOverlayTraceProvider::EvaluatePendingUpdatesForUserActivity *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // r9
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // [rsp+A0h] [rbp-19h] BYREF
  int v10; // [rsp+A4h] [rbp-15h] BYREF
  const int *v11; // [rsp+A8h] [rbp-11h] BYREF
  const unsigned __int16 *v12; // [rsp+B0h] [rbp-9h] BYREF
  const int *v13; // [rsp+B8h] [rbp-1h] BYREF
  const unsigned __int16 *v14; // [rsp+C0h] [rbp+7h] BYREF
  const unsigned __int16 *v15; // [rsp+C8h] [rbp+Fh] BYREF
  const int *v16; // [rsp+D0h] [rbp+17h] BYREF
  const unsigned __int16 *v17; // [rsp+D8h] [rbp+1Fh] BYREF
  const unsigned __int16 *v18; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v19; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v20[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v22; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v23; // [rsp+130h] [rbp+77h] BYREF
  int v24; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = *((_QWORD *)LanguageOverlayTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v5 > 5u
      && (*(_QWORD *)(v5 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v5 + 24) & 0x400000000000LL) == *(_QWORD *)(v5 + 24) )
    {
      v11 = (const int *)*((_QWORD *)v4 + 15);
      v12 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v13 = (const int *)*((_QWORD *)v4 + 12);
      v14 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v22 = v4[20];
      v15 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      LODWORD(v23) = v4[8];
      v16 = (const int *)*((_QWORD *)v4 + 3);
      v24 = *v4;
      v17 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v9 = v4[16];
      v18 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v10 = v4[2];
      v19 = 0x1000000;
      v20[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v5,
        (__int64)byte_180077379,
        *((_QWORD *)this + 34) + 8LL,
        v5,
        (__int64)v20,
        (__int64)&v19,
        (__int64)&v10,
        &v18,
        (__int64)&v9,
        &v17,
        (__int64)&v24,
        &v16,
        (__int64)&v23,
        &v15,
        (__int64)&v22,
        &v14,
        &v13,
        (__int64)&SRWLock,
        &v12,
        &v11);
    }
  }
  else
  {
    wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v6 = *((_QWORD *)LanguageOverlayTraceProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      LODWORD(SRWLock) = GetCurrentThreadId();
      v7 = *((_QWORD *)this + 34);
      v22 = *(_DWORD *)(v7 + 72);
      v23 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)byte_180077313,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::EvaluatePendingUpdatesForUserActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x180017370  push    rbp
0x180017372  push    rbx
0x180017373  push    rdi
0x180017374  lea     rbp, [rsp-47h]
0x180017379  sub     rsp, 100h
0x180017380  mov     rbx, rcx
0x180017383  mov     rdi, [rcx+110h]
0x18001738a  mov     eax, [rdi+48h]
0x18001738d  test    eax, eax
0x18001738f  jns     loc_180017540
0x180017395  add     rdi, 50h ; 'P'
0x180017399  cmp     eax, [rdi+8]
0x18001739c  jnz     loc_180017540
0x1800173a2  test    rdi, rdi
0x1800173a5  jz      loc_180017540
0x1800173ab  lea     rdx, [rbp+57h+SRWLock]
0x1800173af  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800173b4  mov     rax, [rbx+110h]
0x1800173bb  mov     dword ptr [rax], 2
0x1800173c1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800173c5  test    rcx, rcx
0x1800173c8  jz      short loc_1800173D0
0x1800173ca  call    cs:__imp_ReleaseSRWLockExclusive
0x1800173d0  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x1800173d5  mov     r9, [rax+8]
0x1800173d9  mov     eax, [r9]
0x1800173dc  cmp     eax, 5
0x1800173df  jbe     loc_1800175E5
0x1800173e5  mov     rdx, [r9+18h]
0x1800173e9  mov     rax, [r9+10h]
0x1800173ed  mov     rcx, 400000000000h
0x1800173f7  test    rcx, rax
0x1800173fa  jz      loc_1800175E5
0x180017400  mov     rax, rdx
0x180017403  and     rax, rcx
0x180017406  cmp     rax, rdx
0x180017409  jnz     loc_1800175E5
0x18001740f  mov     rax, [rdi+78h]
0x180017413  mov     [rbp+57h+var_68], rax
0x180017417  mov     rax, [rdi+70h]
0x18001741b  mov     [rbp+57h+var_60], rax
0x18001741f  mov     eax, [rdi+68h]
0x180017422  mov     dword ptr [rbp+57h+SRWLock], eax
0x180017425  mov     rax, [rdi+60h]
0x180017429  mov     [rbp+57h+var_58], rax
0x18001742d  mov     rax, [rdi+58h]
0x180017431  mov     [rbp+57h+var_50], rax
0x180017435  mov     eax, [rdi+50h]
0x180017438  mov     [rbp+57h+arg_8], eax
0x18001743b  mov     rax, [rdi+48h]
0x18001743f  mov     [rbp+57h+var_48], rax
0x180017443  mov     eax, [rdi+20h]
0x180017446  mov     dword ptr [rbp+57h+arg_10], eax
0x180017449  mov     rax, [rdi+18h]
0x18001744d  mov     [rbp+57h+var_40], rax
0x180017451  mov     eax, [rdi]
0x180017453  mov     [rbp+57h+arg_18], eax
0x180017456  mov     rax, [rdi+80h]
0x18001745d  mov     [rbp+57h+var_38], rax
0x180017461  mov     eax, [rdi+40h]
0x180017464  mov     [rbp+57h+var_70], eax
0x180017467  mov     rax, [rdi+38h]
0x18001746b  mov     [rbp+57h+var_30], rax
0x18001746f  mov     eax, [rdi+8]
0x180017472  mov     [rbp+57h+var_6C], eax
0x180017475  mov     [rbp+57h+var_28], 1000000h
0x18001747d  mov     [rbp+57h+var_20], 0
0x180017485  mov     r8, [rbx+110h]
0x18001748c  add     r8, 8
0x180017490  lea     rax, [rbp+57h+var_68]
0x180017494  mov     [rsp+110h+var_78], rax
0x18001749c  lea     rax, [rbp+57h+var_60]
0x1800174a0  mov     [rsp+110h+var_80], rax
0x1800174a8  lea     rax, [rbp+57h+SRWLock]
0x1800174ac  mov     [rsp+110h+var_88], rax
0x1800174b4  lea     rax, [rbp+57h+var_58]
0x1800174b8  mov     [rsp+110h+var_90], rax
0x1800174c0  lea     rax, [rbp+57h+var_50]
0x1800174c4  mov     [rsp+110h+var_98], rax
0x1800174c9  lea     rax, [rbp+57h+arg_8]
0x1800174cd  mov     [rsp+110h+var_A0], rax
0x1800174d2  lea     rax, [rbp+57h+var_48]
0x1800174d6  mov     [rsp+110h+var_A8], rax
0x1800174db  lea     rax, [rbp+57h+arg_10]
0x1800174df  mov     [rsp+110h+var_B0], rax
0x1800174e4  lea     rax, [rbp+57h+var_40]
0x1800174e8  mov     [rsp+110h+var_B8], rax
0x1800174ed  lea     rax, [rbp+57h+arg_18]
0x1800174f1  mov     [rsp+110h+var_C0], rax
0x1800174f6  lea     rax, [rbp+57h+var_38]
0x1800174fa  mov     [rsp+110h+var_C8], rax
0x1800174ff  lea     rax, [rbp+57h+var_70]
0x180017503  mov     [rsp+110h+var_D0], rax
0x180017508  lea     rax, [rbp+57h+var_30]
0x18001750c  mov     [rsp+110h+var_D8], rax
0x180017511  lea     rax, [rbp+57h+var_6C]
0x180017515  mov     [rsp+110h+var_E0], rax
0x18001751a  lea     rax, [rbp+57h+var_28]
0x18001751e  mov     [rsp+110h+var_E8], rax
0x180017523  lea     rax, [rbp+57h+var_20]
0x180017527  mov     [rsp+110h+var_F0], rax
0x18001752c  lea     rdx, byte_180077379
0x180017533  mov     rcx, r9
0x180017536  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001753b  jmp     loc_1800175E5
0x180017540  lea     rdx, [rbp+57h+SRWLock]
0x180017544  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180017549  mov     rax, [rbx+110h]
0x180017550  mov     dword ptr [rax], 2
0x180017556  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001755a  test    rcx, rcx
0x18001755d  jz      short loc_180017565
0x18001755f  call    cs:__imp_ReleaseSRWLockExclusive
0x180017565  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18001756a  mov     rdi, [rax+8]
0x18001756e  mov     eax, [rdi]
0x180017570  cmp     eax, 5
0x180017573  jbe     short loc_1800175E5
0x180017575  mov     rdx, [rdi+18h]
0x180017579  mov     rax, [rdi+10h]
0x18001757d  mov     rcx, 400000000000h
0x180017587  test    rcx, rax
0x18001758a  jz      short loc_1800175E5
0x18001758c  mov     rax, rdx
0x18001758f  and     rax, rcx
0x180017592  cmp     rax, rdx
0x180017595  jnz     short loc_1800175E5
0x180017597  call    cs:__imp_GetCurrentThreadId
0x18001759d  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800175a0  mov     r8, [rbx+110h]
0x1800175a7  mov     eax, [r8+48h]
0x1800175ab  mov     [rbp+57h+arg_8], eax
0x1800175ae  mov     [rbp+57h+arg_10], 0
0x1800175b6  add     r8, 8
0x1800175ba  lea     rax, [rbp+57h+SRWLock]
0x1800175be  mov     [rsp+110h+var_E0], rax
0x1800175c3  lea     rax, [rbp+57h+arg_8]
0x1800175c7  mov     [rsp+110h+var_E8], rax
0x1800175cc  lea     rax, [rbp+57h+arg_10]
0x1800175d0  mov     [rsp+110h+var_F0], rax
0x1800175d5  lea     rdx, byte_180077313
0x1800175dc  mov     rcx, rdi
0x1800175df  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800175e4  nop
0x1800175e5  lea     rcx, [rbx+120h]; this
0x1800175ec  cmp     dword ptr [rcx+18h], 0
0x1800175f0  jz      short loc_1800175F8
0x1800175f2  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800175f7  nop
0x1800175f8  add     rsp, 100h
0x1800175ff  pop     rdi
0x180017600  pop     rbx
0x180017601  pop     rbp
0x180017602  retn
```
