# TelemetryLogger::SessionManagerBrokerIsAvailable::Stop(winrt::hstring const &,bool,char const *)

- ea: `0x1800678a8`
- end: `0x180067c7e`
- name: `?Stop@SessionManagerBrokerIsAvailable@TelemetryLogger@@QEAAXAEBUhstring@winrt@@_NPEBD@Z`
- size: `982`
- prototype: `void __fastcall(TelemetryLogger::SessionManagerBrokerIsAvailable *__hidden this, const struct winrt::hstring *, bool, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800619f0`

## callees

- `0x1800017dc`
- `0x180002d20`
- `0x180004ca0`
- `0x180017790`
- `0x180061660`
- `0x1800625bc`
- `0x1800678a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067928`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067b11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067928`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067b11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067b87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067b87`

## pseudocode

```c
void __fastcall TelemetryLogger::SessionManagerBrokerIsAvailable::Stop(
        TelemetryLogger::SessionManagerBrokerIsAvailable *this,
        const struct winrt::hstring *a2,
        char a3,
        const wchar_t *a4)
{
  __int64 v4; // rsi
  int v9; // eax
  int *v10; // rsi
  RTL_SRWLOCK *v11; // rcx
  __int64 v12; // r9
  __int64 v13; // r15
  const wchar_t *v14; // r15
  __int64 v15; // r8
  int v16; // r14d
  RTL_SRWLOCK *v17; // rcx
  __int64 v18; // r12
  __int64 v19; // rsi
  const wchar_t *v20; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v22; // r8
  __int64 v23; // rcx
  __int64 v24; // rax
  _BYTE v25[4]; // [rsp+C0h] [rbp-80h] BYREF
  int v26; // [rsp+C4h] [rbp-7Ch] BYREF
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK v28; // [rsp+D0h] [rbp-70h] BYREF
  int v29; // [rsp+D8h] [rbp-68h] BYREF
  int v30; // [rsp+DCh] [rbp-64h] BYREF
  int v31; // [rsp+E0h] [rbp-60h] BYREF
  int v32; // [rsp+E4h] [rbp-5Ch] BYREF
  const wchar_t *v33; // [rsp+E8h] [rbp-58h] BYREF
  const wchar_t *v34; // [rsp+F0h] [rbp-50h] BYREF
  const wchar_t *v35; // [rsp+F8h] [rbp-48h] BYREF
  const wchar_t *v36; // [rsp+100h] [rbp-40h] BYREF
  const wchar_t *v37; // [rsp+108h] [rbp-38h] BYREF
  const wchar_t *v38; // [rsp+110h] [rbp-30h] BYREF
  const wchar_t *v39; // [rsp+118h] [rbp-28h] BYREF
  const wchar_t *v40; // [rsp+120h] [rbp-20h] BYREF
  const wchar_t *v41; // [rsp+128h] [rbp-18h] BYREF
  const wchar_t *v42; // [rsp+130h] [rbp-10h] BYREF
  __int64 v43; // [rsp+138h] [rbp-8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v44; // [rsp+140h] [rbp+0h] BYREF
  PSRWLOCK *v45; // [rsp+160h] [rbp+20h]
  __int64 v46; // [rsp+168h] [rbp+28h]
  int *v47; // [rsp+170h] [rbp+30h]
  __int64 v48; // [rsp+178h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+180h] [rbp+40h]
  __int64 v50; // [rsp+188h] [rbp+48h]
  const wchar_t *v51; // [rsp+190h] [rbp+50h]
  int v52; // [rsp+198h] [rbp+58h]
  int v53; // [rsp+19Ch] [rbp+5Ch]
  _BYTE *v54; // [rsp+1A0h] [rbp+60h]
  __int64 v55; // [rsp+1A8h] [rbp+68h]
  const wchar_t *v56; // [rsp+1B0h] [rbp+70h]
  int v57; // [rsp+1B8h] [rbp+78h]
  int v58; // [rsp+1BCh] [rbp+7Ch]

  v4 = *((_QWORD *)this + 34);
  v9 = *(_DWORD *)(v4 + 72);
  if ( v9 < 0 && (v10 = (int *)(v4 + 80), v9 == v10[2]) && v10 )
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v11 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v11 )
      ReleaseSRWLockExclusive(v11);
    v12 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v12 > 5u
      && (*(_QWORD *)(v12 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v12 + 24) & 0x400000000000LL) == *(_QWORD *)(v12 + 24) )
    {
      v25[0] = a3;
      v13 = *(_QWORD *)a2;
      if ( !a4 )
        a4 = (const wchar_t *)"Unknown";
      v33 = a4;
      if ( v13 )
        v14 = *(const wchar_t **)(v13 + 16);
      else
        v14 = &pszText;
      v35 = (const wchar_t *)*((_QWORD *)v10 + 15);
      v36 = (const wchar_t *)*((_QWORD *)v10 + 14);
      v29 = v10[26];
      v15 = *((_QWORD *)this + 34);
      v37 = (const wchar_t *)*((_QWORD *)v10 + 12);
      v38 = (const wchar_t *)*((_QWORD *)v10 + 11);
      v30 = v10[20];
      v39 = (const wchar_t *)*((_QWORD *)v10 + 9);
      v31 = v10[8];
      v40 = (const wchar_t *)*((_QWORD *)v10 + 3);
      v32 = *v10;
      v41 = (const wchar_t *)*((_QWORD *)v10 + 16);
      v26 = v10[16];
      v42 = (const wchar_t *)*((_QWORD *)v10 + 7);
      LODWORD(SRWLock) = v10[2];
      v43 = 0x1000000;
      v28 = (PSRWLOCK)0x1000000;
      v34 = v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<char>>(
        v12,
        (__int64)byte_18009D721,
        v15 + 8,
        v12,
        (__int64)&v28,
        (__int64)&v43,
        (__int64)&SRWLock,
        &v42,
        (__int64)&v26,
        &v41,
        (__int64)&v32,
        &v40,
        (__int64)&v31,
        &v39,
        (__int64)&v30,
        &v38,
        &v37,
        (__int64)&v29,
        &v36,
        &v35,
        &v34,
        (__int64)v25,
        &v33);
    }
  }
  else
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v28);
    v16 = 2;
    v17 = v28;
    **((_DWORD **)this + 34) = 2;
    if ( v17 )
      ReleaseSRWLockExclusive(v17);
    v18 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v18 > 5u
      && (*(_QWORD *)(v18 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v18 + 24) & 0x400000000000LL) == *(_QWORD *)(v18 + 24) )
    {
      v19 = *(_QWORD *)a2;
      v25[0] = a3;
      if ( !a4 )
        a4 = (const wchar_t *)"Unknown";
      if ( v19 )
        v20 = *(const wchar_t **)(v19 + 16);
      else
        v20 = &pszText;
      CurrentThreadId = GetCurrentThreadId();
      v22 = *((_QWORD *)this + 34);
      v23 = -1;
      LODWORD(SRWLock) = CurrentThreadId;
      v26 = *(_DWORD *)(v22 + 72);
      v28 = (PSRWLOCK)0x1000000;
      v24 = -1;
      do
        ++v24;
      while ( *((_BYTE *)a4 + v24) );
      v56 = a4;
      v57 = v24 + 1;
      v54 = v25;
      v58 = 0;
      v55 = 1;
      if ( v20 )
      {
        do
          ++v23;
        while ( v20[v23] );
        v16 = 2 * v23 + 2;
      }
      else
      {
        v20 = &pszText;
      }
      v51 = v20;
      p_SRWLock = &SRWLock;
      v52 = v16;
      v47 = &v26;
      v53 = 0;
      v45 = &v28;
      v50 = 4;
      v48 = 4;
      v46 = 8;
      tlgWriteTransfer_EventWriteTransfer(v18, (unsigned __int8 *)byte_18009D55D, (const GUID *)(v22 + 8), 0, 8u, &v44);
    }
  }
  wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800678a8  push    rbp
0x1800678aa  push    rbx
0x1800678ab  push    rsi
0x1800678ac  push    rdi
0x1800678ad  push    r12
0x1800678af  push    r13
0x1800678b1  push    r14
0x1800678b3  push    r15
0x1800678b5  lea     rbp, [rsp-98h]
0x1800678bd  sub     rsp, 1D8h
0x1800678c4  mov     rax, cs:__security_cookie
0x1800678cb  xor     rax, rsp
0x1800678ce  mov     [rbp+0D0h+var_50], rax
0x1800678d5  mov     rsi, [rcx+110h]
0x1800678dc  mov     rbx, r9
0x1800678df  mov     r15b, r8b
0x1800678e2  mov     r13, rdx
0x1800678e5  mov     rdi, rcx
0x1800678e8  mov     eax, [rsi+48h]
0x1800678eb  test    eax, eax
0x1800678ed  jns     loc_180067AEF
0x1800678f3  add     rsi, 50h ; 'P'
0x1800678f7  cmp     eax, [rsi+8]
0x1800678fa  jnz     loc_180067AEF
0x180067900  test    rsi, rsi
0x180067903  jz      loc_180067AEF
0x180067909  lea     rdx, [rbp+0D0h+SRWLock]
0x18006790d  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180067912  mov     rax, [rdi+110h]
0x180067919  mov     rcx, [rbp+0D0h+SRWLock]; SRWLock
0x18006791d  mov     dword ptr [rax], 2
0x180067923  test    rcx, rcx
0x180067926  jz      short loc_18006792E
0x180067928  call    cs:__imp_ReleaseSRWLockExclusive
0x18006792e  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180067933  mov     r9, [rax+8]
0x180067937  mov     eax, [r9]
0x18006793a  cmp     eax, 5
0x18006793d  jbe     loc_180067C53
0x180067943  mov     rdx, [r9+18h]
0x180067947  mov     rcx, 400000000000h
0x180067951  mov     rax, [r9+10h]
0x180067955  test    rcx, rax
0x180067958  jz      loc_180067C53
0x18006795e  mov     rax, rdx
0x180067961  and     rax, rcx
0x180067964  cmp     rax, rdx
0x180067967  jnz     loc_180067C53
0x18006796d  test    rbx, rbx
0x180067970  mov     [rbp+0D0h+var_150], r15b
0x180067974  mov     r15, [r13+0]
0x180067978  lea     rax, aUnknown; "Unknown"
0x18006797f  cmovz   rbx, rax
0x180067983  mov     [rbp+0D0h+var_128], rbx
0x180067987  test    r15, r15
0x18006798a  jz      short loc_180067992
0x18006798c  mov     r15, [r15+10h]
0x180067990  jmp     short loc_180067999
0x180067992  lea     r15, pszText
0x180067999  mov     rax, [rsi+78h]
0x18006799d  lea     rdx, byte_18009D721
0x1800679a4  mov     [rbp+0D0h+var_118], rax
0x1800679a8  mov     rcx, r9
0x1800679ab  mov     rax, [rsi+70h]
0x1800679af  mov     [rbp+0D0h+var_110], rax
0x1800679b3  mov     eax, [rsi+68h]
0x1800679b6  mov     [rbp+0D0h+var_138], eax
0x1800679b9  mov     rax, [rsi+60h]
0x1800679bd  mov     r8, [rdi+110h]
0x1800679c4  mov     [rbp+0D0h+var_108], rax
0x1800679c8  add     r8, 8
0x1800679cc  mov     rax, [rsi+58h]
0x1800679d0  mov     [rbp+0D0h+var_100], rax
0x1800679d4  mov     eax, [rsi+50h]
0x1800679d7  mov     [rbp+0D0h+var_134], eax
0x1800679da  mov     rax, [rsi+48h]
0x1800679de  mov     [rbp+0D0h+var_F8], rax
0x1800679e2  mov     eax, [rsi+20h]
0x1800679e5  mov     [rbp+0D0h+var_130], eax
0x1800679e8  mov     rax, [rsi+18h]
0x1800679ec  mov     [rbp+0D0h+var_F0], rax
0x1800679f0  mov     eax, [rsi]
0x1800679f2  mov     [rbp+0D0h+var_12C], eax
0x1800679f5  mov     rax, [rsi+80h]
0x1800679fc  mov     [rbp+0D0h+var_E8], rax
0x180067a00  mov     eax, [rsi+40h]
0x180067a03  mov     [rbp+0D0h+var_14C], eax
0x180067a06  mov     rax, [rsi+38h]
0x180067a0a  mov     [rbp+0D0h+var_E0], rax
0x180067a0e  mov     eax, [rsi+8]
0x180067a11  mov     dword ptr [rbp+0D0h+SRWLock], eax
0x180067a14  mov     eax, 1000000h
0x180067a19  mov     [rbp+0D0h+var_D8], rax
0x180067a1d  mov     [rbp+0D0h+var_140], rax
0x180067a21  lea     rax, [rbp+0D0h+var_128]
0x180067a25  mov     [rsp+210h+var_160], rax
0x180067a2d  lea     rax, [rbp+0D0h+var_150]
0x180067a31  mov     [rsp+210h+var_168], rax
0x180067a39  lea     rax, [rbp+0D0h+var_120]
0x180067a3d  mov     [rsp+210h+var_170], rax
0x180067a45  lea     rax, [rbp+0D0h+var_118]
0x180067a49  mov     [rsp+210h+var_178], rax
0x180067a51  lea     rax, [rbp+0D0h+var_110]
0x180067a55  mov     [rsp+210h+var_180], rax
0x180067a5d  lea     rax, [rbp+0D0h+var_138]
0x180067a61  mov     [rsp+210h+var_188], rax
0x180067a69  lea     rax, [rbp+0D0h+var_108]
0x180067a6d  mov     [rsp+210h+var_190], rax
0x180067a75  lea     rax, [rbp+0D0h+var_100]
0x180067a79  mov     [rsp+210h+var_198], rax
0x180067a7e  lea     rax, [rbp+0D0h+var_134]
0x180067a82  mov     [rsp+210h+var_1A0], rax
0x180067a87  lea     rax, [rbp+0D0h+var_F8]
0x180067a8b  mov     [rsp+210h+var_1A8], rax
0x180067a90  lea     rax, [rbp+0D0h+var_130]
0x180067a94  mov     [rsp+210h+var_1B0], rax
0x180067a99  lea     rax, [rbp+0D0h+var_F0]
0x180067a9d  mov     [rsp+210h+var_1B8], rax
0x180067aa2  lea     rax, [rbp+0D0h+var_12C]
0x180067aa6  mov     [rsp+210h+var_1C0], rax
0x180067aab  lea     rax, [rbp+0D0h+var_E8]
0x180067aaf  mov     [rsp+210h+var_1C8], rax
0x180067ab4  lea     rax, [rbp+0D0h+var_14C]
0x180067ab8  mov     [rsp+210h+var_1D0], rax
0x180067abd  lea     rax, [rbp+0D0h+var_E0]
0x180067ac1  mov     [rsp+210h+var_1D8], rax
0x180067ac6  lea     rax, [rbp+0D0h+SRWLock]
0x180067aca  mov     [rsp+210h+var_1E0], rax
0x180067acf  lea     rax, [rbp+0D0h+var_D8]
0x180067ad3  mov     [rsp+210h+var_1E8], rax
0x180067ad8  lea     rax, [rbp+0D0h+var_140]
0x180067adc  mov     [rsp+210h+var_1F0], rax
0x180067ae1  mov     [rbp+0D0h+var_120], r15
0x180067ae5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U?$_tlgWrapperByVal@$00@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564566AEBU?$_tlgWrapperByVal@$00@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<char> const &)
0x180067aea  jmp     loc_180067C53
0x180067aef  lea     rdx, [rbp+0D0h+var_140]
0x180067af3  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180067af8  mov     rax, [rdi+110h]
0x180067aff  mov     r14d, 2
0x180067b05  mov     rcx, [rbp+0D0h+var_140]; SRWLock
0x180067b09  mov     [rax], r14d
0x180067b0c  test    rcx, rcx
0x180067b0f  jz      short loc_180067B17
0x180067b11  call    cs:__imp_ReleaseSRWLockExclusive
0x180067b17  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180067b1c  mov     r12, [rax+8]
0x180067b20  mov     eax, [r12]
0x180067b24  cmp     eax, 5
0x180067b27  jbe     loc_180067C53
0x180067b2d  mov     rdx, [r12+18h]
0x180067b32  mov     rcx, 400000000000h
0x180067b3c  mov     rax, [r12+10h]
0x180067b41  test    rcx, rax
0x180067b44  jz      loc_180067C53
0x180067b4a  mov     rax, rdx
0x180067b4d  and     rax, rcx
0x180067b50  cmp     rax, rdx
0x180067b53  jnz     loc_180067C53
0x180067b59  mov     rsi, [r13+0]
0x180067b5d  lea     rax, aUnknown; "Unknown"
0x180067b64  test    rbx, rbx
0x180067b67  mov     [rbp+0D0h+var_150], r15b
0x180067b6b  lea     r15, pszText
0x180067b72  cmovz   rbx, rax
0x180067b76  xor     r13d, r13d
0x180067b79  test    rsi, rsi
0x180067b7c  jz      short loc_180067B84
0x180067b7e  mov     rsi, [rsi+10h]
0x180067b82  jmp     short loc_180067B87
0x180067b84  mov     rsi, r15
0x180067b87  call    cs:__imp_GetCurrentThreadId
0x180067b8d  mov     r8, [rdi+110h]
0x180067b94  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180067b98  mov     dword ptr [rbp+0D0h+SRWLock], eax
0x180067b9b  mov     eax, [r8+48h]
0x180067b9f  mov     [rbp+0D0h+var_14C], eax
0x180067ba2  mov     eax, 1000000h
0x180067ba7  mov     [rbp+0D0h+var_140], rax
0x180067bab  mov     rax, rcx
0x180067bae  inc     rax
0x180067bb1  cmp     [rbx+rax], r13b
0x180067bb5  jnz     short loc_180067BAE
0x180067bb7  inc     eax
0x180067bb9  mov     [rbp+0D0h+var_60], rbx
0x180067bbd  mov     [rbp+0D0h+var_58], eax
0x180067bc0  lea     rax, [rbp+0D0h+var_150]
0x180067bc4  mov     [rbp+0D0h+var_70], rax
0x180067bc8  mov     [rbp+0D0h+var_54], r13d
0x180067bcc  mov     [rbp+0D0h+var_68], 1
0x180067bd4  test    rsi, rsi
0x180067bd7  jz      short loc_180067BED
0x180067bd9  inc     rcx
0x180067bdc  cmp     [rsi+rcx*2], r13w
0x180067be1  jnz     short loc_180067BD9
0x180067be3  lea     r14d, ds:2[rcx*2]
0x180067beb  jmp     short loc_180067BF0
0x180067bed  mov     rsi, r15
0x180067bf0  lea     rax, [rbp+0D0h+SRWLock]
0x180067bf4  mov     [rbp+0D0h+var_80], rsi
0x180067bf8  mov     [rbp+0D0h+var_90], rax
0x180067bfc  lea     rdx, byte_18009D55D
0x180067c03  lea     rax, [rbp+0D0h+var_14C]
0x180067c07  mov     [rbp+0D0h+var_78], r14d
0x180067c0b  mov     [rbp+0D0h+var_A0], rax
0x180067c0f  add     r8, 8
0x180067c13  lea     rax, [rbp+0D0h+var_140]
0x180067c17  mov     [rbp+0D0h+var_74], r13d
0x180067c1b  mov     [rbp+0D0h+var_B0], rax
0x180067c1f  xor     r9d, r9d
0x180067c22  lea     rax, [rbp+0D0h+var_D0]
0x180067c26  mov     [rbp+0D0h+var_88], 4
0x180067c2e  mov     [rsp+210h+var_1E8], rax
0x180067c33  mov     rcx, r12
0x180067c36  mov     dword ptr [rsp+210h+var_1F0], 8
0x180067c3e  mov     [rbp+0D0h+var_98], 4
0x180067c46  mov     [rbp+0D0h+var_A8], 8
0x180067c4e  call    _tlgWriteTransfer_EventWriteTransfer
0x180067c53  mov     rcx, rdi
0x180067c56  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180067c5b  mov     rcx, [rbp+0D0h+var_50]
0x180067c62  xor     rcx, rsp; StackCookie
0x180067c65  call    __security_check_cookie
0x180067c6a  add     rsp, 1D8h
0x180067c71  pop     r15
0x180067c73  pop     r14
0x180067c75  pop     r13
0x180067c77  pop     r12
0x180067c79  pop     rdi
0x180067c7a  pop     rsi
0x180067c7b  pop     rbx
0x180067c7c  pop     rbp
0x180067c7d  retn
```
