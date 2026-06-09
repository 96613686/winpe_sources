# TelemetryLogger::SessionManagerBrokerGetPackageSet::Stop(winrt::hstring const &)

- ea: `0x1800674e4`
- end: `0x1800678a2`
- name: `?Stop@SessionManagerBrokerGetPackageSet@TelemetryLogger@@QEAAXAEBUhstring@winrt@@@Z`
- size: `958`
- prototype: `void __fastcall(TelemetryLogger::SessionManagerBrokerGetPackageSet *__hidden this, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800606f0`

## callees

- `0x1800017dc`
- `0x180002a34`
- `0x180004ca0`
- `0x180017790`
- `0x1800625bc`
- `0x1800674e4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067560`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067718`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067560`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067718`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067775`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067827`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067775`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067827`

## string_xrefs

- `0x180067845`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TelemetryLogger::SessionManagerBrokerGetPackageSet::Stop(
        TelemetryLogger::SessionManagerBrokerGetPackageSet *this,
        const struct winrt::hstring *a2)
{
  __int64 v4; // rdi
  int v5; // eax
  int *v6; // rdi
  __int64 v7; // r9
  __int64 v8; // r14
  const wchar_t *v9; // r14
  int v10; // esi
  __int64 v11; // r15
  const wchar_t *v12; // rdi
  __int64 v13; // r8
  __int64 v14; // rsi
  char *v15; // rbx
  __int64 *v16; // rcx
  __int64 v17; // rax
  int v18; // [rsp+B0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+B8h] [rbp-78h] BYREF
  PSRWLOCK v20; // [rsp+C0h] [rbp-70h] BYREF
  int v21; // [rsp+C8h] [rbp-68h] BYREF
  int v22; // [rsp+CCh] [rbp-64h] BYREF
  int v23; // [rsp+D0h] [rbp-60h] BYREF
  int v24; // [rsp+D4h] [rbp-5Ch] BYREF
  const wchar_t *v25; // [rsp+D8h] [rbp-58h] BYREF
  const wchar_t *v26; // [rsp+E0h] [rbp-50h] BYREF
  const wchar_t *v27; // [rsp+E8h] [rbp-48h] BYREF
  const wchar_t *v28; // [rsp+F0h] [rbp-40h] BYREF
  const wchar_t *v29; // [rsp+F8h] [rbp-38h] BYREF
  const wchar_t *v30; // [rsp+100h] [rbp-30h] BYREF
  const wchar_t *v31; // [rsp+108h] [rbp-28h] BYREF
  const wchar_t *v32; // [rsp+110h] [rbp-20h] BYREF
  const wchar_t *v33; // [rsp+118h] [rbp-18h] BYREF
  __int64 v34; // [rsp+120h] [rbp-10h] BYREF
  _BYTE v35[32]; // [rsp+130h] [rbp+0h] BYREF
  PSRWLOCK *v36; // [rsp+150h] [rbp+20h]
  __int64 v37; // [rsp+158h] [rbp+28h]
  int *v38; // [rsp+160h] [rbp+30h]
  __int64 v39; // [rsp+168h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+170h] [rbp+40h]
  __int64 v41; // [rsp+178h] [rbp+48h]
  const wchar_t *v42; // [rsp+180h] [rbp+50h]
  int v43; // [rsp+188h] [rbp+58h]
  int v44; // [rsp+18Ch] [rbp+5Ch]
  void *retaddr; // [rsp+1C8h] [rbp+98h]

  v4 = *((_QWORD *)this + 34);
  v5 = *(_DWORD *)(v4 + 72);
  if ( v5 < 0 && (v6 = (int *)(v4 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v7 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v7 > 5u
      && (*(_QWORD *)(v7 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v7 + 24) & 0x200000000000LL) == *(_QWORD *)(v7 + 24) )
    {
      v8 = *(_QWORD *)a2;
      if ( v8 )
        v9 = *(const wchar_t **)(v8 + 16);
      else
        v9 = &pszText;
      v25 = v9;
      v26 = (const wchar_t *)*((_QWORD *)v6 + 15);
      v27 = (const wchar_t *)*((_QWORD *)v6 + 14);
      v21 = v6[26];
      v28 = (const wchar_t *)*((_QWORD *)v6 + 12);
      v29 = (const wchar_t *)*((_QWORD *)v6 + 11);
      v22 = v6[20];
      v30 = (const wchar_t *)*((_QWORD *)v6 + 9);
      v23 = v6[8];
      v31 = (const wchar_t *)*((_QWORD *)v6 + 3);
      v24 = *v6;
      v32 = (const wchar_t *)*((_QWORD *)v6 + 16);
      v18 = v6[16];
      v33 = (const wchar_t *)*((_QWORD *)v6 + 7);
      LODWORD(SRWLock) = v6[2];
      v34 = 0x1000000;
      v20 = (PSRWLOCK)0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        v7,
        (__int64)byte_18009DBB9,
        *((_QWORD *)this + 34) + 8LL,
        v7,
        (__int64)&v20,
        (__int64)&v34,
        (__int64)&SRWLock,
        &v33,
        (__int64)&v18,
        &v32,
        (__int64)&v24,
        &v31,
        (__int64)&v23,
        &v30,
        (__int64)&v22,
        &v29,
        &v28,
        (__int64)&v21,
        &v27,
        &v26,
        &v25);
    }
  }
  else
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v20);
    v10 = 2;
    **((_DWORD **)this + 34) = 2;
    if ( v20 )
      ReleaseSRWLockExclusive(v20);
    v11 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v11 > 5u
      && (*(_QWORD *)(v11 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v11 + 24) & 0x200000000000LL) == *(_QWORD *)(v11 + 24) )
    {
      if ( *(_QWORD *)a2 )
        v12 = *(const wchar_t **)(*(_QWORD *)a2 + 16LL);
      else
        v12 = &pszText;
      LODWORD(SRWLock) = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v18 = *(_DWORD *)(v13 + 72);
      v20 = (PSRWLOCK)0x1000000;
      if ( v12 )
      {
        v14 = -1;
        do
          ++v14;
        while ( v12[v14] );
        v10 = 2 * v14 + 2;
      }
      else
      {
        v12 = &pszText;
      }
      v42 = v12;
      v43 = v10;
      v44 = 0;
      p_SRWLock = &SRWLock;
      v41 = 4;
      v38 = &v18;
      v39 = 4;
      v36 = &v20;
      v37 = 8;
      tlgWriteTransfer_EventWriteTransfer(v11, &dword_18009DAB4, v13 + 8, 0, 6, v35);
    }
  }
  if ( *((_DWORD *)this + 78) )
  {
    v15 = (char *)this + 288;
    if ( *((_DWORD *)v15 + 6) != GetCurrentThreadId() )
    {
      if ( wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
    }
    *((_DWORD *)v15 + 6) = 0;
    v16 = *(__int64 **)v15;
    while ( 1 )
    {
      v17 = *v16;
      if ( !*v16 )
        break;
      if ( (char *)v17 == v15 )
      {
        *v16 = *((_QWORD *)v15 + 2);
        break;
      }
      v16 = (__int64 *)(v17 + 16);
      *(_QWORD *)v15 = v17 + 16;
    }
    *(_QWORD *)v15 = 0;
  }
}

```

## disassembly

```asm
0x1800674e4  mov     [rsp-8+arg_8], rbx
0x1800674e9  mov     [rsp-8+arg_10], rsi
0x1800674ee  push    rbp
0x1800674ef  push    rdi
0x1800674f0  push    r12
0x1800674f2  push    r14
0x1800674f4  push    r15
0x1800674f6  lea     rbp, [rsp-70h]
0x1800674fb  sub     rsp, 1A0h
0x180067502  mov     rax, cs:__security_cookie
0x180067509  xor     rax, rsp
0x18006750c  mov     [rbp+90h+var_30], rax
0x180067510  mov     r14, rdx
0x180067513  mov     rbx, rcx
0x180067516  mov     rdi, [rcx+110h]
0x18006751d  mov     eax, [rdi+48h]
0x180067520  xor     r12d, r12d
0x180067523  test    eax, eax
0x180067525  jns     loc_1800676F8
0x18006752b  add     rdi, 50h ; 'P'
0x18006752f  cmp     eax, [rdi+8]
0x180067532  jnz     loc_1800676F8
0x180067538  test    rdi, rdi
0x18006753b  jz      loc_1800676F8
0x180067541  lea     rdx, [rbp+90h+SRWLock]
0x180067545  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006754a  mov     rax, [rbx+110h]
0x180067551  mov     dword ptr [rax], 2
0x180067557  mov     rcx, [rbp+90h+SRWLock]; SRWLock
0x18006755b  test    rcx, rcx
0x18006755e  jz      short loc_180067566
0x180067560  call    cs:__imp_ReleaseSRWLockExclusive
0x180067566  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18006756b  mov     r9, [rax+8]
0x18006756f  mov     eax, [r9]
0x180067572  cmp     eax, 5
0x180067575  jbe     loc_180067817
0x18006757b  mov     rdx, [r9+18h]
0x18006757f  mov     rax, [r9+10h]
0x180067583  mov     rcx, 200000000000h
0x18006758d  test    rcx, rax
0x180067590  jz      loc_180067817
0x180067596  mov     rax, rdx
0x180067599  and     rax, rcx
0x18006759c  cmp     rax, rdx
0x18006759f  jnz     loc_180067817
0x1800675a5  mov     r14, [r14]
0x1800675a8  test    r14, r14
0x1800675ab  jz      short loc_1800675B3
0x1800675ad  mov     r14, [r14+10h]
0x1800675b1  jmp     short loc_1800675BA
0x1800675b3  lea     r14, pszText
0x1800675ba  mov     [rbp+90h+var_E8], r14
0x1800675be  mov     rax, [rdi+78h]
0x1800675c2  mov     [rbp+90h+var_E0], rax
0x1800675c6  mov     rax, [rdi+70h]
0x1800675ca  mov     [rbp+90h+var_D8], rax
0x1800675ce  mov     eax, [rdi+68h]
0x1800675d1  mov     [rbp+90h+var_F8], eax
0x1800675d4  mov     rax, [rdi+60h]
0x1800675d8  mov     [rbp+90h+var_D0], rax
0x1800675dc  mov     rax, [rdi+58h]
0x1800675e0  mov     [rbp+90h+var_C8], rax
0x1800675e4  mov     eax, [rdi+50h]
0x1800675e7  mov     [rbp+90h+var_F4], eax
0x1800675ea  mov     rax, [rdi+48h]
0x1800675ee  mov     [rbp+90h+var_C0], rax
0x1800675f2  mov     eax, [rdi+20h]
0x1800675f5  mov     [rbp+90h+var_F0], eax
0x1800675f8  mov     rax, [rdi+18h]
0x1800675fc  mov     [rbp+90h+var_B8], rax
0x180067600  mov     eax, [rdi]
0x180067602  mov     [rbp+90h+var_EC], eax
0x180067605  mov     rax, [rdi+80h]
0x18006760c  mov     [rbp+90h+var_B0], rax
0x180067610  mov     eax, [rdi+40h]
0x180067613  mov     [rbp+90h+var_110], eax
0x180067616  mov     rax, [rdi+38h]
0x18006761a  mov     [rbp+90h+var_A8], rax
0x18006761e  mov     eax, [rdi+8]
0x180067621  mov     dword ptr [rbp+90h+SRWLock], eax
0x180067624  mov     eax, 1000000h
0x180067629  mov     [rbp+90h+var_A0], rax
0x18006762d  mov     [rbp+90h+var_100], rax
0x180067631  mov     r8, [rbx+110h]
0x180067638  add     r8, 8
0x18006763c  lea     rax, [rbp+90h+var_E8]
0x180067640  mov     [rsp+1C0h+var_120], rax
0x180067648  lea     rax, [rbp+90h+var_E0]
0x18006764c  mov     [rsp+1C0h+var_128], rax
0x180067654  lea     rax, [rbp+90h+var_D8]
0x180067658  mov     [rsp+1C0h+var_130], rax
0x180067660  lea     rax, [rbp+90h+var_F8]
0x180067664  mov     [rsp+1C0h+var_138], rax
0x18006766c  lea     rax, [rbp+90h+var_D0]
0x180067670  mov     [rsp+1C0h+var_140], rax
0x180067678  lea     rax, [rbp+90h+var_C8]
0x18006767c  mov     [rsp+1C0h+var_148], rax
0x180067681  lea     rax, [rbp+90h+var_F4]
0x180067685  mov     [rsp+1C0h+var_150], rax
0x18006768a  lea     rax, [rbp+90h+var_C0]
0x18006768e  mov     [rsp+1C0h+var_158], rax
0x180067693  lea     rax, [rbp+90h+var_F0]
0x180067697  mov     [rsp+1C0h+var_160], rax
0x18006769c  lea     rax, [rbp+90h+var_B8]
0x1800676a0  mov     [rsp+1C0h+var_168], rax
0x1800676a5  lea     rax, [rbp+90h+var_EC]
0x1800676a9  mov     [rsp+1C0h+var_170], rax
0x1800676ae  lea     rax, [rbp+90h+var_B0]
0x1800676b2  mov     [rsp+1C0h+var_178], rax
0x1800676b7  lea     rax, [rbp+90h+var_110]
0x1800676bb  mov     [rsp+1C0h+var_180], rax
0x1800676c0  lea     rax, [rbp+90h+var_A8]
0x1800676c4  mov     [rsp+1C0h+var_188], rax
0x1800676c9  lea     rax, [rbp+90h+SRWLock]
0x1800676cd  mov     [rsp+1C0h+var_190], rax
0x1800676d2  lea     rax, [rbp+90h+var_A0]
0x1800676d6  mov     [rsp+1C0h+var_198], rax
0x1800676db  lea     rax, [rbp+90h+var_100]
0x1800676df  mov     [rsp+1C0h+var_1A0], rax
0x1800676e4  lea     rdx, byte_18009DBB9
0x1800676eb  mov     rcx, r9
0x1800676ee  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x1800676f3  jmp     loc_180067817
0x1800676f8  lea     rdx, [rbp+90h+var_100]
0x1800676fc  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180067701  mov     rax, [rbx+110h]
0x180067708  mov     esi, 2
0x18006770d  mov     [rax], esi
0x18006770f  mov     rcx, [rbp+90h+var_100]; SRWLock
0x180067713  test    rcx, rcx
0x180067716  jz      short loc_18006771E
0x180067718  call    cs:__imp_ReleaseSRWLockExclusive
0x18006771e  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180067723  mov     r15, [rax+8]
0x180067727  mov     eax, [r15]
0x18006772a  cmp     eax, 5
0x18006772d  jbe     loc_180067817
0x180067733  mov     rdx, [r15+18h]
0x180067737  mov     rax, [r15+10h]
0x18006773b  mov     rcx, 200000000000h
0x180067745  test    rcx, rax
0x180067748  jz      loc_180067817
0x18006774e  mov     rax, rdx
0x180067751  and     rax, rcx
0x180067754  cmp     rax, rdx
0x180067757  jnz     loc_180067817
0x18006775d  mov     rdi, [r14]
0x180067760  lea     r14, pszText
0x180067767  test    rdi, rdi
0x18006776a  jz      short loc_180067772
0x18006776c  mov     rdi, [rdi+10h]
0x180067770  jmp     short loc_180067775
0x180067772  mov     rdi, r14
0x180067775  call    cs:__imp_GetCurrentThreadId
0x18006777b  mov     dword ptr [rbp+90h+SRWLock], eax
0x18006777e  mov     r8, [rbx+110h]
0x180067785  mov     eax, [r8+48h]
0x180067789  mov     [rbp+90h+var_110], eax
0x18006778c  mov     eax, 1000000h
0x180067791  mov     [rbp+90h+var_100], rax
0x180067795  test    rdi, rdi
0x180067798  jz      short loc_1800677B1
0x18006779a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18006779e  inc     rsi
0x1800677a1  cmp     [rdi+rsi*2], r12w
0x1800677a6  jnz     short loc_18006779E
0x1800677a8  lea     esi, ds:2[rsi*2]
0x1800677af  jmp     short loc_1800677B4
0x1800677b1  mov     rdi, r14
0x1800677b4  mov     [rbp+90h+var_40], rdi
0x1800677b8  mov     [rbp+90h+var_38], esi
0x1800677bb  mov     [rbp+90h+var_34], r12d
0x1800677bf  lea     rax, [rbp+90h+SRWLock]
0x1800677c3  mov     [rbp+90h+var_50], rax
0x1800677c7  mov     [rbp+90h+var_48], 4
0x1800677cf  lea     rax, [rbp+90h+var_110]
0x1800677d3  mov     [rbp+90h+var_60], rax
0x1800677d7  mov     [rbp+90h+var_58], 4
0x1800677df  lea     rax, [rbp+90h+var_100]
0x1800677e3  mov     [rbp+90h+var_70], rax
0x1800677e7  mov     [rbp+90h+var_68], 8
0x1800677ef  add     r8, 8
0x1800677f3  lea     rax, [rbp+90h+var_90]
0x1800677f7  mov     [rsp+1C0h+var_198], rax
0x1800677fc  mov     dword ptr [rsp+1C0h+var_1A0], 6
0x180067804  xor     r9d, r9d
0x180067807  lea     rdx, dword_18009DAB4
0x18006780e  mov     rcx, r15
0x180067811  call    _tlgWriteTransfer_EventWriteTransfer
0x180067816  nop
0x180067817  cmp     [rbx+138h], r12d
0x18006781e  jz      short loc_18006787A
0x180067820  add     rbx, 120h
0x180067827  call    cs:__imp_GetCurrentThreadId
0x18006782d  cmp     [rbx+18h], eax
0x180067830  jz      short loc_180067851
0x180067832  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x180067839  test    rax, rax
0x18006783c  jz      short loc_180067851
0x18006783e  mov     rdx, [rbp+98h]
0x180067845  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x18006784c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067851  mov     [rbx+18h], r12d
0x180067855  mov     rcx, [rbx]
0x180067858  jmp     short loc_180067866
0x18006785a  cmp     rax, rbx
0x18006785d  jz      short loc_180067870
0x18006785f  lea     rcx, [rax+10h]
0x180067863  mov     [rbx], rcx
0x180067866  mov     rax, [rcx]
0x180067869  test    rax, rax
0x18006786c  jnz     short loc_18006785A
0x18006786e  jmp     short loc_180067877
0x180067870  mov     rax, [rbx+10h]
0x180067874  mov     [rcx], rax
0x180067877  mov     [rbx], r12
0x18006787a  mov     rcx, [rbp+90h+var_30]
0x18006787e  xor     rcx, rsp; StackCookie
0x180067881  call    __security_check_cookie
0x180067886  lea     r11, [rsp+1C0h+var_20]
0x18006788e  mov     rbx, [r11+38h]
0x180067892  mov     rsi, [r11+40h]
0x180067896  mov     rsp, r11
0x180067899  pop     r15
0x18006789b  pop     r14
0x18006789d  pop     r12
0x18006789f  pop     rdi
0x1800678a0  pop     rbp
0x1800678a1  retn
```
