# LanguageOverlayTraceProvider::LogonOverlayBootstrappingForUserActivity::StopActivity(void)

- ea: `0x180017610`
- end: `0x1800178a3`
- name: `?StopActivity@LogonOverlayBootstrappingForUserActivity@LanguageOverlayTraceProvider@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(LanguageOverlayTraceProvider::LogonOverlayBootstrappingForUserActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001008`
- `0x180001a78`
- `0x1800085dc`
- `0x18000e1b8`
- `0x180010dcc`
- `0x180017610`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001766a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800177ff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001766a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800177ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017837`

## pseudocode

```c
void __fastcall LanguageOverlayTraceProvider::LogonOverlayBootstrappingForUserActivity::StopActivity(
        LanguageOverlayTraceProvider::LogonOverlayBootstrappingForUserActivity *this)
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
  __int64 v20[4]; // [rsp+F0h] [rbp+37h] BYREF
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
      v20[0] = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v5,
        (__int64)byte_180076F63,
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
      v23 = 50331648;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)word_180076EFA,
        v7 + 8,
        v8,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&SRWLock);
    }
  }
  if ( *((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StopWatching((LanguageOverlayTraceProvider::LogonOverlayBootstrappingForUserActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x180017610  push    rbp
0x180017612  push    rbx
0x180017613  push    rdi
0x180017614  lea     rbp, [rsp-47h]
0x180017619  sub     rsp, 100h
0x180017620  mov     rbx, rcx
0x180017623  mov     rdi, [rcx+110h]
0x18001762a  mov     eax, [rdi+48h]
0x18001762d  test    eax, eax
0x18001762f  jns     loc_1800177E0
0x180017635  add     rdi, 50h ; 'P'
0x180017639  cmp     eax, [rdi+8]
0x18001763c  jnz     loc_1800177E0
0x180017642  test    rdi, rdi
0x180017645  jz      loc_1800177E0
0x18001764b  lea     rdx, [rbp+57h+SRWLock]
0x18001764f  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180017654  mov     rax, [rbx+110h]
0x18001765b  mov     dword ptr [rax], 2
0x180017661  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180017665  test    rcx, rcx
0x180017668  jz      short loc_180017670
0x18001766a  call    cs:__imp_ReleaseSRWLockExclusive
0x180017670  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x180017675  mov     r9, [rax+8]
0x180017679  mov     eax, [r9]
0x18001767c  cmp     eax, 5
0x18001767f  jbe     loc_180017885
0x180017685  mov     rdx, [r9+18h]
0x180017689  mov     rax, [r9+10h]
0x18001768d  mov     rcx, 400000000000h
0x180017697  test    rcx, rax
0x18001769a  jz      loc_180017885
0x1800176a0  mov     rax, rdx
0x1800176a3  and     rax, rcx
0x1800176a6  cmp     rax, rdx
0x1800176a9  jnz     loc_180017885
0x1800176af  mov     rax, [rdi+78h]
0x1800176b3  mov     [rbp+57h+var_68], rax
0x1800176b7  mov     rax, [rdi+70h]
0x1800176bb  mov     [rbp+57h+var_60], rax
0x1800176bf  mov     eax, [rdi+68h]
0x1800176c2  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800176c5  mov     rax, [rdi+60h]
0x1800176c9  mov     [rbp+57h+var_58], rax
0x1800176cd  mov     rax, [rdi+58h]
0x1800176d1  mov     [rbp+57h+var_50], rax
0x1800176d5  mov     eax, [rdi+50h]
0x1800176d8  mov     [rbp+57h+arg_8], eax
0x1800176db  mov     rax, [rdi+48h]
0x1800176df  mov     [rbp+57h+var_48], rax
0x1800176e3  mov     eax, [rdi+20h]
0x1800176e6  mov     dword ptr [rbp+57h+arg_10], eax
0x1800176e9  mov     rax, [rdi+18h]
0x1800176ed  mov     [rbp+57h+var_40], rax
0x1800176f1  mov     eax, [rdi]
0x1800176f3  mov     [rbp+57h+arg_18], eax
0x1800176f6  mov     rax, [rdi+80h]
0x1800176fd  mov     [rbp+57h+var_38], rax
0x180017701  mov     eax, [rdi+40h]
0x180017704  mov     [rbp+57h+var_70], eax
0x180017707  mov     rax, [rdi+38h]
0x18001770b  mov     [rbp+57h+var_30], rax
0x18001770f  mov     eax, [rdi+8]
0x180017712  mov     [rbp+57h+var_6C], eax
0x180017715  mov     [rbp+57h+var_28], 1000000h
0x18001771d  mov     [rbp+57h+var_20], 3000000h
0x180017725  mov     r8, [rbx+110h]
0x18001772c  add     r8, 8
0x180017730  lea     rax, [rbp+57h+var_68]
0x180017734  mov     [rsp+110h+var_78], rax
0x18001773c  lea     rax, [rbp+57h+var_60]
0x180017740  mov     [rsp+110h+var_80], rax
0x180017748  lea     rax, [rbp+57h+SRWLock]
0x18001774c  mov     [rsp+110h+var_88], rax
0x180017754  lea     rax, [rbp+57h+var_58]
0x180017758  mov     [rsp+110h+var_90], rax
0x180017760  lea     rax, [rbp+57h+var_50]
0x180017764  mov     [rsp+110h+var_98], rax
0x180017769  lea     rax, [rbp+57h+arg_8]
0x18001776d  mov     [rsp+110h+var_A0], rax
0x180017772  lea     rax, [rbp+57h+var_48]
0x180017776  mov     [rsp+110h+var_A8], rax
0x18001777b  lea     rax, [rbp+57h+arg_10]
0x18001777f  mov     [rsp+110h+var_B0], rax
0x180017784  lea     rax, [rbp+57h+var_40]
0x180017788  mov     [rsp+110h+var_B8], rax
0x18001778d  lea     rax, [rbp+57h+arg_18]
0x180017791  mov     [rsp+110h+var_C0], rax
0x180017796  lea     rax, [rbp+57h+var_38]
0x18001779a  mov     [rsp+110h+var_C8], rax
0x18001779f  lea     rax, [rbp+57h+var_70]
0x1800177a3  mov     [rsp+110h+var_D0], rax
0x1800177a8  lea     rax, [rbp+57h+var_30]
0x1800177ac  mov     [rsp+110h+var_D8], rax
0x1800177b1  lea     rax, [rbp+57h+var_6C]
0x1800177b5  mov     [rsp+110h+var_E0], rax
0x1800177ba  lea     rax, [rbp+57h+var_28]
0x1800177be  mov     [rsp+110h+var_E8], rax
0x1800177c3  lea     rax, [rbp+57h+var_20]
0x1800177c7  mov     [rsp+110h+var_F0], rax
0x1800177cc  lea     rdx, byte_180076F63
0x1800177d3  mov     rcx, r9
0x1800177d6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800177db  jmp     loc_180017885
0x1800177e0  lea     rdx, [rbp+57h+SRWLock]
0x1800177e4  call    ?LockExclusive@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800177e9  mov     rax, [rbx+110h]
0x1800177f0  mov     dword ptr [rax], 2
0x1800177f6  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800177fa  test    rcx, rcx
0x1800177fd  jz      short loc_180017805
0x1800177ff  call    cs:__imp_ReleaseSRWLockExclusive
0x180017805  call    ?Instance@LanguageOverlayTraceProvider@@KAPEAV1@XZ; LanguageOverlayTraceProvider::Instance(void)
0x18001780a  mov     rdi, [rax+8]
0x18001780e  mov     eax, [rdi]
0x180017810  cmp     eax, 5
0x180017813  jbe     short loc_180017885
0x180017815  mov     rdx, [rdi+18h]
0x180017819  mov     rax, [rdi+10h]
0x18001781d  mov     rcx, 400000000000h
0x180017827  test    rcx, rax
0x18001782a  jz      short loc_180017885
0x18001782c  mov     rax, rdx
0x18001782f  and     rax, rcx
0x180017832  cmp     rax, rdx
0x180017835  jnz     short loc_180017885
0x180017837  call    cs:__imp_GetCurrentThreadId
0x18001783d  mov     dword ptr [rbp+57h+SRWLock], eax
0x180017840  mov     r8, [rbx+110h]
0x180017847  mov     eax, [r8+48h]
0x18001784b  mov     [rbp+57h+arg_8], eax
0x18001784e  mov     [rbp+57h+arg_10], 3000000h
0x180017856  add     r8, 8
0x18001785a  lea     rax, [rbp+57h+SRWLock]
0x18001785e  mov     [rsp+110h+var_E0], rax
0x180017863  lea     rax, [rbp+57h+arg_8]
0x180017867  mov     [rsp+110h+var_E8], rax
0x18001786c  lea     rax, [rbp+57h+arg_10]
0x180017870  mov     [rsp+110h+var_F0], rax
0x180017875  lea     rdx, word_180076EFA
0x18001787c  mov     rcx, rdi
0x18001787f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180017884  nop
0x180017885  lea     rcx, [rbx+120h]; this
0x18001788c  cmp     dword ptr [rcx+18h], 0
0x180017890  jz      short loc_180017898
0x180017892  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180017897  nop
0x180017898  add     rsp, 100h
0x18001789f  pop     rdi
0x1800178a0  pop     rbx
0x1800178a1  pop     rbp
0x1800178a2  retn
```
