# CDependencyContainer::AddUrl(ushort const *,uchar const *,ulong)

- ea: `0x1800c8f88`
- end: `0x1800c93de`
- name: `?AddUrl@CDependencyContainer@@QEAAJPEBGPEBEK@Z`
- size: `1110`
- prototype: `int(CDependencyContainer *__hidden this, const unsigned __int16 *, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1801c9790`

## callees

- `0x180021360`
- `0x18007ec9c`
- `0x180083540`
- `0x1800838d8`
- `0x180083dc4`
- `0x1800861f8`
- `0x1800c8f88`
- `0x1800c93e4`
- `0x1800c9b40`
- `0x1800ee168`
- `0x1800eee94`
- `0x1800f05dc`
- `0x1800fa844`
- `0x18012814c`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801e13c0`
- `0x1801e1790`
- `0x1801e853c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c9118`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c9118`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c9108`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c9108`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c91a2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c91a2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c915e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800c915e`
- `ESENT!JetCommitTransaction` at `0x1800c93bd`
- `ESENT!JetCommitTransaction` at `0x1800c93bd`
- `ESENT!JetUpdate` at `0x1800c9396`
- `ESENT!JetUpdate` at `0x1800c9396`
- `ESENT!JetPrepareUpdate` at `0x1800c908d`
- `ESENT!JetPrepareUpdate` at `0x1800c927b`
- `ESENT!JetPrepareUpdate` at `0x1800c908d`
- `ESENT!JetPrepareUpdate` at `0x1800c927b`
- `ESENT!JetRollback` at `0x1800c909e`
- `ESENT!JetRollback` at `0x1800c909e`
- `ESENT!JetBeginTransaction` at `0x1800c922e`
- `ESENT!JetBeginTransaction` at `0x1800c922e`

## pseudocode

```c
__int64 __fastcall CDependencyContainer::AddUrl(
        CDependencyContainer *this,
        const unsigned __int16 *a2,
        const unsigned __int8 *a3,
        unsigned int a4)
{
  int v4; // esi
  char v5; // bl
  JET_SESID *v9; // rdi
  int v10; // edx
  int v11; // ecx
  int v12; // r8d
  RTL_SRWLOCK *v13; // r13
  int UrlOrigin; // ebx
  BOOL v15; // r12d
  CDependencyContainer *v17; // rcx
  unsigned int v18; // ebx
  CInFlightLocks *v19; // rcx
  int v20; // eax
  unsigned int v21; // r9d
  JET_ERR v22; // eax
  JET_ERR v23; // eax
  JET_ERR v24; // eax
  JET_ERR v25; // eax
  int v26; // [rsp+50h] [rbp-B0h]
  int v27; // [rsp+54h] [rbp-ACh]
  CJetContext *v28; // [rsp+58h] [rbp-A8h] BYREF
  RTL_SRWLOCK *v29; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h]
  unsigned int v31; // [rsp+70h] [rbp-90h]
  struct CInFlightEntry *v32; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v33[2]; // [rsp+80h] [rbp-80h] BYREF
  enum INTERNET_SCHEME v34; // [rsp+84h] [rbp-7Ch] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v36[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v37[524]; // [rsp+94h] [rbp-6Ch] BYREF

  v4 = 0;
  v5 = a4;
  v31 = a4;
  v28 = 0;
  v26 = 0;
  SystemTimeAsFileTime = 0;
  v9 = 0;
  v32 = 0;
  v34 = INTERNET_SCHEME_DEFAULT;
  v33[0] = 0;
  *(_DWORD *)v36 = 0;
  memset_0(v37, 0, 0x1FEu);
  v13 = (RTL_SRWLOCK *)((char *)this + 24);
  v30 = 0;
  v29 = (RTL_SRWLOCK *)((char *)this + 24);
  v27 = 0;
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_qSqd(
      1036,
      20,
      (unsigned int)&WPP_609a45caca2b3eab7507b65993ebc372_Traceguids,
      (_DWORD)this,
      (__int64)a2,
      (__int64)a3,
      v5);
  if ( !a2 )
  {
    UrlOrigin = -2147024809;
LABEL_5:
    v15 = v4;
    goto LABEL_6;
  }
  if ( !a3 )
  {
    UrlOrigin = -2147024809;
    goto LABEL_5;
  }
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  UrlOrigin = CDependencyContainer::GetUrlOrigin(v17, a2, v36, &v34, v33);
  if ( UrlOrigin < 0 )
    goto LABEL_5;
  v18 = WxComputePrefixHash(a2, 127);
  AcquireSRWLockShared((PSRWLOCK)this + 3);
  v19 = (CInFlightLocks *)*((_QWORD *)this + 5);
  v4 = 1;
  LODWORD(v30) = 1;
  v27 = 1;
  UrlOrigin = CInFlightLocks::AcquireLock(v19, v18, &v32);
  if ( UrlOrigin >= 0 )
  {
    v20 = CJetContextList::AcquireContext(*((CJetContextList **)this + 4), &v28, 0);
    v9 = (JET_SESID *)v28;
    UrlOrigin = v20;
    if ( v20 < 0
      || (UrlOrigin = CJetContext::SetCurrentIndex(v28, 1u, L"Url", v21), UrlOrigin < 0)
      || (v22 = JetBeginTransaction(v9[2]), UrlOrigin = HRESULTFromJET_ERR(v22, 1), UrlOrigin < 0) )
    {
      v15 = 0;
    }
    else
    {
      UrlOrigin = CDependencyContainer::SeekToUrl(this, (struct CJetContext *)v9, a2, 1u);
      if ( UrlOrigin < 0 )
        goto LABEL_5;
      v23 = JetPrepareUpdate(v9[2], v9[4], UrlOrigin == 0 ? 2 : 0);
      UrlOrigin = HRESULTFromJET_ERR(v23, 1);
      if ( UrlOrigin < 0 )
        goto LABEL_5;
      v26 = 1;
      UrlOrigin = CJetContext::SetStringColumn((CJetContext *)v9, 1u, a2);
      if ( UrlOrigin < 0 )
        goto LABEL_5;
      UrlOrigin = CJetContext::SetBinaryColumn((CJetContext *)v9, 2u, a3, v31);
      if ( UrlOrigin < 0 )
        goto LABEL_5;
      UrlOrigin = CJetContext::SetBasicColumn((CJetContext *)v9, 6u, &SystemTimeAsFileTime, 8u);
      if ( UrlOrigin < 0 )
        goto LABEL_5;
      UrlOrigin = CJetContext::SetStringColumn((CJetContext *)v9, 3u, v36);
      if ( UrlOrigin < 0 )
        goto LABEL_5;
      UrlOrigin = CJetContext::SetBasicColumn((CJetContext *)v9, 4u, &v34, 4u);
      if ( UrlOrigin < 0 )
        goto LABEL_5;
      UrlOrigin = CJetContext::SetBasicColumn((CJetContext *)v9, 5u, v33, 2u);
      if ( UrlOrigin < 0 )
        goto LABEL_5;
      v24 = JetUpdate(v9[2], v9[4], 0, 0, 0);
      UrlOrigin = HRESULTFromJET_ERR(v24, 1);
      if ( UrlOrigin < 0 )
        goto LABEL_5;
      v26 = 0;
      v25 = JetCommitTransaction(v9[2], 1u);
      UrlOrigin = HRESULTFromJET_ERR(v25, 1);
      v15 = UrlOrigin < 0;
    }
  }
  else
  {
    v15 = 0;
  }
LABEL_6:
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_ISS(v11, v10, v12, *((_QWORD *)this + 1), (__int64)a2, (__int64)v36);
  if ( v26 )
    JetPrepareUpdate(v9[2], v9[4], 3u);
  if ( v15 )
    JetRollback(v9[2], 0);
  if ( v9 )
    CJetContextList::ReleaseContext(*((CJetContextList **)this + 4), &v28);
  CInFlightLocks::ReleaseLock(*((CInFlightLocks **)this + 5), &v32);
  if ( v27 )
  {
    AutoSrw::UnlockShared((AutoSrw *)&v29);
    v4 = v30;
    v13 = v29;
  }
  if ( (BYTE1(xmmword_180266B60) & 0x10) != 0 )
    WPP_SF_d(1036, 22, &WPP_609a45caca2b3eab7507b65993ebc372_Traceguids, (unsigned int)UrlOrigin);
  if ( v4 )
    ReleaseSRWLockShared(v13);
  if ( HIDWORD(v30) )
    ReleaseSRWLockExclusive(v13);
  return (unsigned int)UrlOrigin;
}

```

## disassembly

```asm
0x1800c8f88  push    rbp
0x1800c8f8a  push    rbx
0x1800c8f8b  push    rsi
0x1800c8f8c  push    rdi
0x1800c8f8d  push    r12
0x1800c8f8f  push    r13
0x1800c8f91  push    r14
0x1800c8f93  push    r15
0x1800c8f95  lea     rbp, [rsp-1B8h]
0x1800c8f9d  sub     rsp, 2B8h
0x1800c8fa4  mov     rax, cs:__security_cookie
0x1800c8fab  xor     rax, rsp
0x1800c8fae  mov     [rbp+1F0h+var_50], rax
0x1800c8fb5  xor     esi, esi
0x1800c8fb7  mov     ebx, r9d
0x1800c8fba  mov     r12, r8
0x1800c8fbd  mov     [rsp+2F0h+var_280], ebx
0x1800c8fc1  mov     r15, rdx
0x1800c8fc4  mov     [rsp+2F0h+var_298], rsi
0x1800c8fc9  mov     r14, rcx
0x1800c8fcc  mov     [rsp+2F0h+var_2B0], esi
0x1800c8fd0  xor     edx, edx; Val
0x1800c8fd2  mov     [rsp+2F0h+var_2A4], esi
0x1800c8fd6  mov     r8d, 1FEh; Size
0x1800c8fdc  mov     [rsp+2F0h+var_2A0], esi
0x1800c8fe0  lea     rcx, [rbp+1F0h+var_25C]; void *
0x1800c8fe4  mov     qword ptr [rbp+1F0h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x1800c8fe8  mov     edi, esi
0x1800c8fea  mov     [rsp+2F0h+var_278], rsi
0x1800c8fef  mov     [rbp+1F0h+var_26C], esi
0x1800c8ff2  mov     [rbp+1F0h+var_270], si
0x1800c8ff6  mov     dword ptr [rbp+1F0h+var_260], esi
0x1800c8ff9  call    memset_0
0x1800c8ffe  lea     r13, [r14+18h]
0x1800c9002  mov     [rsp+2F0h+var_288], rsi
0x1800c9007  mov     [rsp+2F0h+var_290], r13
0x1800c900c  mov     [rsp+2F0h+var_29C], esi
0x1800c9010  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800c9017  jz      short loc_1800C903E
0x1800c9019  mov     [rsp+2F0h+var_2C0], ebx
0x1800c901d  lea     edx, [rsi+14h]
0x1800c9020  mov     [rsp+2F0h+var_2C8], r12
0x1800c9025  lea     r8, WPP_609a45caca2b3eab7507b65993ebc372_Traceguids
0x1800c902c  mov     ecx, 40Ch
0x1800c9031  mov     [rsp+2F0h+pcbActual], r15
0x1800c9036  mov     r9, r14
0x1800c9039  call    WPP_SF_qSqd
0x1800c903e  test    r15, r15
0x1800c9041  jnz     loc_1800C9143
0x1800c9047  mov     ebx, 80070057h
0x1800c904c  mov     [rsp+2F0h+var_2A4], 1CBh
0x1800c9054  mov     r12d, esi
0x1800c9057  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800c905e  jz      short loc_1800C9077
0x1800c9060  mov     r9, [r14+8]
0x1800c9064  lea     rax, [rbp+1F0h+var_260]
0x1800c9068  mov     [rsp+2F0h+var_2C8], rax
0x1800c906d  mov     [rsp+2F0h+pcbActual], r15
0x1800c9072  call    WPP_SF_ISS
0x1800c9077  xor     r15d, r15d
0x1800c907a  cmp     [rsp+2F0h+var_2A0], r15d
0x1800c907f  jz      short loc_1800C9093
0x1800c9081  mov     rdx, [rdi+20h]; tableid
0x1800c9085  lea     r8d, [r15+3]; prep
0x1800c9089  mov     rcx, [rdi+10h]; sesid
0x1800c908d  call    cs:__imp_JetPrepareUpdate
0x1800c9093  test    r12d, r12d
0x1800c9096  jz      short loc_1800C90A4
0x1800c9098  mov     rcx, [rdi+10h]; sesid
0x1800c909c  xor     edx, edx; grbit
0x1800c909e  call    cs:__imp_JetRollback
0x1800c90a4  test    rdi, rdi
0x1800c90a7  jz      short loc_1800C90B7
0x1800c90a9  mov     rcx, [r14+20h]; this
0x1800c90ad  lea     rdx, [rsp+2F0h+var_298]; struct CJetContext **
0x1800c90b2  call    ?ReleaseContext@CJetContextList@@QEAAXPEAPEAVCJetContext@@@Z; CJetContextList::ReleaseContext(CJetContext * *)
0x1800c90b7  mov     rcx, [r14+28h]; this
0x1800c90bb  lea     rdx, [rsp+2F0h+var_278]; struct CInFlightEntry **
0x1800c90c0  call    ?ReleaseLock@CInFlightLocks@@QEAAXPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::ReleaseLock(CInFlightEntry * *)
0x1800c90c5  cmp     [rsp+2F0h+var_29C], r15d
0x1800c90ca  jz      short loc_1800C90DF
0x1800c90cc  lea     rcx, [rsp+2F0h+var_290]; this
0x1800c90d1  call    ?UnlockShared@AutoSrw@@QEAAXXZ; AutoSrw::UnlockShared(void)
0x1800c90d6  mov     esi, dword ptr [rsp+2F0h+var_288]
0x1800c90da  mov     r13, [rsp+2F0h+var_290]
0x1800c90df  test    byte ptr cs:xmmword_180266B60+1, 10h
0x1800c90e6  jz      short loc_1800C9101
0x1800c90e8  mov     edx, 16h
0x1800c90ed  lea     r8, WPP_609a45caca2b3eab7507b65993ebc372_Traceguids
0x1800c90f4  mov     ecx, 40Ch
0x1800c90f9  mov     r9d, ebx
0x1800c90fc  call    WPP_SF_d
0x1800c9101  test    esi, esi
0x1800c9103  jz      short loc_1800C910E
0x1800c9105  mov     rcx, r13; SRWLock
0x1800c9108  call    cs:__imp_ReleaseSRWLockShared
0x1800c910e  cmp     dword ptr [rsp+2F0h+var_288+4], r15d
0x1800c9113  jz      short loc_1800C911E
0x1800c9115  mov     rcx, r13; SRWLock
0x1800c9118  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c911e  mov     eax, ebx
0x1800c9120  mov     rcx, [rbp+1F0h+var_50]
0x1800c9127  xor     rcx, rsp; StackCookie
0x1800c912a  call    __security_check_cookie
0x1800c912f  add     rsp, 2B8h
0x1800c9136  pop     r15
0x1800c9138  pop     r14
0x1800c913a  pop     r13
0x1800c913c  pop     r12
0x1800c913e  pop     rdi
0x1800c913f  pop     rsi
0x1800c9140  pop     rbx
0x1800c9141  pop     rbp
0x1800c9142  retn
0x1800c9143  test    r12, r12
0x1800c9146  jnz     short loc_1800C915A
0x1800c9148  mov     ebx, 80070057h
0x1800c914d  mov     [rsp+2F0h+var_2A4], 1CCh
0x1800c9155  jmp     loc_1800C9054
0x1800c915a  lea     rcx, [rbp+1F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800c915e  call    cs:__imp_GetSystemTimeAsFileTime
0x1800c9164  lea     rax, [rbp+1F0h+var_270]
0x1800c9168  mov     rdx, r15; unsigned __int16 *
0x1800c916b  lea     r9, [rbp+1F0h+var_26C]; enum INTERNET_SCHEME *
0x1800c916f  mov     [rsp+2F0h+pcbActual], rax; unsigned __int16 *
0x1800c9174  lea     r8, [rbp+1F0h+var_260]; unsigned __int16 *
0x1800c9178  call    ?GetUrlOrigin@CDependencyContainer@@AEAAJPEBGPEAGPEAW4INTERNET_SCHEME@@1@Z; CDependencyContainer::GetUrlOrigin(ushort const *,ushort *,INTERNET_SCHEME *,ushort *)
0x1800c917d  mov     ebx, eax
0x1800c917f  test    eax, eax
0x1800c9181  jns     short loc_1800C9190
0x1800c9183  mov     [rsp+2F0h+var_2A4], 1D3h
0x1800c918b  jmp     loc_1800C9054
0x1800c9190  mov     edx, 7Fh
0x1800c9195  mov     rcx, r15
0x1800c9198  call    WxComputePrefixHash
0x1800c919d  mov     rcx, r13; SRWLock
0x1800c91a0  mov     ebx, eax
0x1800c91a2  call    cs:__imp_AcquireSRWLockShared
0x1800c91a8  mov     rcx, [r14+28h]; this
0x1800c91ac  lea     r8, [rsp+2F0h+var_278]; struct CInFlightEntry **
0x1800c91b1  mov     esi, 1
0x1800c91b6  mov     edx, ebx; unsigned __int64
0x1800c91b8  mov     dword ptr [rsp+2F0h+var_288], esi
0x1800c91bc  mov     [rsp+2F0h+var_29C], esi
0x1800c91c0  call    ?AcquireLock@CInFlightLocks@@QEAAJ_KPEAPEAVCInFlightEntry@@@Z; CInFlightLocks::AcquireLock(unsigned __int64,CInFlightEntry * *)
0x1800c91c5  mov     ebx, eax
0x1800c91c7  test    eax, eax
0x1800c91c9  jns     short loc_1800C91DB
0x1800c91cb  mov     [rsp+2F0h+var_2A4], 1DAh
0x1800c91d3  mov     r12d, edi
0x1800c91d6  jmp     loc_1800C9057
0x1800c91db  mov     rcx, [r14+20h]; this
0x1800c91df  lea     rdx, [rsp+2F0h+var_298]; struct CJetContext **
0x1800c91e4  xor     r8d, r8d; int *
0x1800c91e7  call    ?AcquireContext@CJetContextList@@QEAAJPEAPEAVCJetContext@@PEAH@Z; CJetContextList::AcquireContext(CJetContext * *,int *)
0x1800c91ec  mov     rdi, [rsp+2F0h+var_298]
0x1800c91f1  mov     ebx, eax
0x1800c91f3  test    eax, eax
0x1800c91f5  jns     short loc_1800C9209
0x1800c91f7  mov     [rsp+2F0h+var_2A4], 1DCh
0x1800c91ff  mov     r12d, [rsp+2F0h+var_2B0]
0x1800c9204  jmp     loc_1800C9057
0x1800c9209  lea     r8, aUrl_1; "Url"
0x1800c9210  mov     edx, esi; unsigned int
0x1800c9212  mov     rcx, rdi; this
0x1800c9215  call    ?SetCurrentIndex@CJetContext@@QEAAJKPEBGK@Z; CJetContext::SetCurrentIndex(ulong,ushort const *,ulong)
0x1800c921a  mov     ebx, eax
0x1800c921c  test    eax, eax
0x1800c921e  jns     short loc_1800C922A
0x1800c9220  mov     [rsp+2F0h+var_2A4], 1E0h
0x1800c9228  jmp     short loc_1800C91FF
0x1800c922a  mov     rcx, [rdi+10h]; sesid
0x1800c922e  call    cs:__imp_JetBeginTransaction
0x1800c9234  mov     ecx, eax; int
0x1800c9236  mov     edx, esi; int
0x1800c9238  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800c923d  mov     ebx, eax
0x1800c923f  test    eax, eax
0x1800c9241  js      short loc_1800C91FF
0x1800c9243  mov     r9d, esi; unsigned int
0x1800c9246  mov     r8, r15; unsigned __int16 *
0x1800c9249  mov     rdx, rdi; struct CJetContext *
0x1800c924c  mov     rcx, r14; this
0x1800c924f  call    ?SeekToUrl@CDependencyContainer@@AEAAJPEAVCJetContext@@PEBGK@Z; CDependencyContainer::SeekToUrl(CJetContext *,ushort const *,ulong)
0x1800c9254  mov     ebx, eax
0x1800c9256  test    eax, eax
0x1800c9258  jns     short loc_1800C9267
0x1800c925a  mov     [rsp+2F0h+var_2A4], 1E8h
0x1800c9262  jmp     loc_1800C9054
0x1800c9267  mov     rdx, [rdi+20h]; tableid
0x1800c926b  neg     ebx
0x1800c926d  mov     rcx, [rdi+10h]; sesid
0x1800c9271  sbb     r8d, r8d
0x1800c9274  not     r8d
0x1800c9277  and     r8d, 2; prep
0x1800c927b  call    cs:__imp_JetPrepareUpdate
0x1800c9281  mov     ecx, eax; int
0x1800c9283  mov     edx, esi; int
0x1800c9285  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800c928a  mov     ebx, eax
0x1800c928c  test    eax, eax
0x1800c928e  js      loc_1800C9054
0x1800c9294  mov     r8, r15; unsigned __int16 *
0x1800c9297  mov     [rsp+2F0h+var_2A0], esi
0x1800c929b  mov     edx, esi; unsigned int
0x1800c929d  mov     rcx, rdi; this
0x1800c92a0  call    ?SetStringColumn@CJetContext@@QEAAJKPEBG@Z; CJetContext::SetStringColumn(ulong,ushort const *)
0x1800c92a5  mov     ebx, eax
0x1800c92a7  test    eax, eax
0x1800c92a9  jns     short loc_1800C92B8
0x1800c92ab  mov     [rsp+2F0h+var_2A4], 1F5h
0x1800c92b3  jmp     loc_1800C9054
0x1800c92b8  mov     r9d, [rsp+2F0h+var_280]; unsigned int
0x1800c92bd  mov     r8, r12; unsigned __int8 *
0x1800c92c0  mov     r12d, 2
0x1800c92c6  mov     rcx, rdi; this
0x1800c92c9  mov     edx, r12d; unsigned int
0x1800c92cc  call    ?SetBinaryColumn@CJetContext@@QEAAJKPEBEK@Z; CJetContext::SetBinaryColumn(ulong,uchar const *,ulong)
0x1800c92d1  mov     ebx, eax
0x1800c92d3  test    eax, eax
0x1800c92d5  jns     short loc_1800C92E4
0x1800c92d7  mov     [rsp+2F0h+var_2A4], 1F9h
0x1800c92df  jmp     loc_1800C9054
0x1800c92e4  mov     r9d, 8; unsigned int
0x1800c92ea  lea     r8, [rbp+1F0h+SystemTimeAsFileTime]; void *
0x1800c92ee  mov     rcx, rdi; this
0x1800c92f1  lea     edx, [r9-2]; unsigned int
0x1800c92f5  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1800c92fa  mov     ebx, eax
0x1800c92fc  test    eax, eax
0x1800c92fe  jns     short loc_1800C930D
0x1800c9300  mov     [rsp+2F0h+var_2A4], 1FDh
0x1800c9308  jmp     loc_1800C9054
0x1800c930d  lea     r8, [rbp+1F0h+var_260]; unsigned __int16 *
0x1800c9311  mov     edx, 3; unsigned int
0x1800c9316  mov     rcx, rdi; this
0x1800c9319  call    ?SetStringColumn@CJetContext@@QEAAJKPEBG@Z; CJetContext::SetStringColumn(ulong,ushort const *)
0x1800c931e  mov     ebx, eax
0x1800c9320  test    eax, eax
0x1800c9322  jns     short loc_1800C9331
0x1800c9324  mov     [rsp+2F0h+var_2A4], 200h
0x1800c932c  jmp     loc_1800C9054
0x1800c9331  mov     edx, 4; unsigned int
0x1800c9336  lea     r8, [rbp+1F0h+var_26C]; void *
0x1800c933a  mov     r9d, edx; unsigned int
0x1800c933d  mov     rcx, rdi; this
0x1800c9340  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1800c9345  mov     ebx, eax
0x1800c9347  test    eax, eax
0x1800c9349  jns     short loc_1800C9358
0x1800c934b  mov     [rsp+2F0h+var_2A4], 204h
0x1800c9353  jmp     loc_1800C9054
0x1800c9358  mov     r9d, r12d; unsigned int
0x1800c935b  lea     r8, [rbp+1F0h+var_270]; void *
0x1800c935f  mov     edx, 5; unsigned int
0x1800c9364  mov     rcx, rdi; this
0x1800c9367  call    ?SetBasicColumn@CJetContext@@QEAAJKPEAXK@Z; CJetContext::SetBasicColumn(ulong,void *,ulong)
0x1800c936c  mov     ebx, eax
0x1800c936e  test    eax, eax
0x1800c9370  jns     short loc_1800C937F
0x1800c9372  mov     [rsp+2F0h+var_2A4], 208h
0x1800c937a  jmp     loc_1800C9054
0x1800c937f  mov     rdx, [rdi+20h]; tableid
0x1800c9383  xor     r9d, r9d; cbBookmark
0x1800c9386  mov     rcx, [rdi+10h]; sesid
0x1800c938a  xor     r8d, r8d; pvBookmark
0x1800c938d  mov     [rsp+2F0h+pcbActual], 0; pcbActual
0x1800c9396  call    cs:__imp_JetUpdate
0x1800c939c  mov     ecx, eax; int
0x1800c939e  mov     edx, esi; int
0x1800c93a0  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800c93a5  mov     ebx, eax
0x1800c93a7  test    eax, eax
0x1800c93a9  js      loc_1800C9054
0x1800c93af  mov     rcx, [rdi+10h]; sesid
0x1800c93b3  mov     edx, esi; grbit
0x1800c93b5  mov     [rsp+2F0h+var_2A0], 0
0x1800c93bd  call    cs:__imp_JetCommitTransaction
0x1800c93c3  mov     ecx, eax; int
0x1800c93c5  mov     edx, esi; int
0x1800c93c7  call    ?HRESULTFromJET_ERR@@YAJJH@Z; HRESULTFromJET_ERR(long,int)
0x1800c93cc  mov     ebx, eax
0x1800c93ce  mov     r12d, esi
0x1800c93d1  xor     eax, eax
0x1800c93d3  test    ebx, ebx
0x1800c93d5  cmovns  r12d, eax
0x1800c93d9  jmp     loc_1800C9057
```
