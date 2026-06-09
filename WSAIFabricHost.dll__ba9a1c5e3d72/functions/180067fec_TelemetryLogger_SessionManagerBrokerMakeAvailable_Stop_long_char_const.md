# TelemetryLogger::SessionManagerBrokerMakeAvailable::Stop(long,char const *)

- ea: `0x180067fec`
- end: `0x18006834a`
- name: `?Stop@SessionManagerBrokerMakeAvailable@TelemetryLogger@@QEAAXJPEBD@Z`
- size: `862`
- prototype: `void __fastcall(TelemetryLogger::SessionManagerBrokerMakeAvailable *__hidden this, int, const char *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005aa1c`
- `0x180062660`

## callees

- `0x1800017dc`
- `0x18000273c`
- `0x180004ca0`
- `0x180017790`
- `0x180061660`
- `0x1800625bc`
- `0x180067fec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068064`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068224`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068064`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068224`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006827a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006827a`

## pseudocode

```c
void __fastcall TelemetryLogger::SessionManagerBrokerMakeAvailable::Stop(
        TelemetryLogger::SessionManagerBrokerMakeAvailable *this,
        int a2,
        const wchar_t *a3)
{
  __int64 v3; // rsi
  int v7; // eax
  int *v8; // rsi
  RTL_SRWLOCK *v9; // rcx
  __int64 v10; // r9
  __int64 v11; // r8
  RTL_SRWLOCK *v12; // rcx
  __int64 v13; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // rax
  int v17; // [rsp+B0h] [rbp-80h] BYREF
  DWORD v18; // [rsp+B4h] [rbp-7Ch] BYREF
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
  struct _EVENT_DATA_DESCRIPTOR v35; // [rsp+130h] [rbp+0h] BYREF
  PSRWLOCK *v36; // [rsp+150h] [rbp+20h]
  __int64 v37; // [rsp+158h] [rbp+28h]
  int *v38; // [rsp+160h] [rbp+30h]
  __int64 v39; // [rsp+168h] [rbp+38h]
  DWORD *v40; // [rsp+170h] [rbp+40h]
  __int64 v41; // [rsp+178h] [rbp+48h]
  PSRWLOCK *p_SRWLock; // [rsp+180h] [rbp+50h]
  __int64 v43; // [rsp+188h] [rbp+58h]
  const wchar_t *v44; // [rsp+190h] [rbp+60h]
  int v45; // [rsp+198h] [rbp+68h]
  int v46; // [rsp+19Ch] [rbp+6Ch]

  v3 = *((_QWORD *)this + 34);
  v7 = *(_DWORD *)(v3 + 72);
  if ( v7 < 0 && (v8 = (int *)(v3 + 80), v7 == v8[2]) && v8 )
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v10 > 5u
      && (*(_QWORD *)(v10 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v10 + 24) & 0x400000000000LL) == *(_QWORD *)(v10 + 24) )
    {
      v11 = *((_QWORD *)this + 34);
      v21 = a2;
      if ( !a3 )
        a3 = (const wchar_t *)"Unknown";
      v26 = (const wchar_t *)*((_QWORD *)v8 + 15);
      v27 = (const wchar_t *)*((_QWORD *)v8 + 14);
      v22 = v8[26];
      v28 = (const wchar_t *)*((_QWORD *)v8 + 12);
      v29 = (const wchar_t *)*((_QWORD *)v8 + 11);
      v23 = v8[20];
      v30 = (const wchar_t *)*((_QWORD *)v8 + 9);
      v24 = v8[8];
      v31 = (const wchar_t *)*((_QWORD *)v8 + 3);
      v17 = *v8;
      v32 = (const wchar_t *)*((_QWORD *)v8 + 16);
      v18 = v8[16];
      v33 = (const wchar_t *)*((_QWORD *)v8 + 7);
      LODWORD(SRWLock) = v8[2];
      v34 = 0x1000000;
      v20 = (PSRWLOCK)0x1000000;
      v25 = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v10,
        (__int64)word_18009D322,
        v11 + 8,
        v10,
        (__int64)&v20,
        (__int64)&v34,
        (__int64)&SRWLock,
        &v33,
        (__int64)&v18,
        &v32,
        (__int64)&v17,
        &v31,
        (__int64)&v24,
        &v30,
        (__int64)&v23,
        &v29,
        &v28,
        (__int64)&v22,
        &v27,
        &v26,
        (__int64)&v21,
        &v25);
    }
  }
  else
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v20);
    v12 = v20;
    **((_DWORD **)this + 34) = 2;
    if ( v12 )
      ReleaseSRWLockExclusive(v12);
    v13 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v13 > 5u
      && (*(_QWORD *)(v13 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v13 + 24) & 0x400000000000LL) == *(_QWORD *)(v13 + 24) )
    {
      LODWORD(SRWLock) = a2;
      if ( !a3 )
        a3 = (const wchar_t *)"Unknown";
      CurrentThreadId = GetCurrentThreadId();
      v15 = *((_QWORD *)this + 34);
      v18 = CurrentThreadId;
      v17 = *(_DWORD *)(v15 + 72);
      v20 = (PSRWLOCK)0x1000000;
      v16 = -1;
      do
        ++v16;
      while ( *((_BYTE *)a3 + v16) );
      v44 = a3;
      v45 = v16 + 1;
      v46 = 0;
      p_SRWLock = &SRWLock;
      v43 = 4;
      v40 = &v18;
      v41 = 4;
      v38 = &v17;
      v39 = 4;
      v36 = &v20;
      v37 = 8;
      tlgWriteTransfer_EventWriteTransfer(v13, (unsigned __int8 *)word_18009D162, (const GUID *)(v15 + 8), 0, 7u, &v35);
    }
  }
  wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180067fec  mov     [rsp-8+arg_8], rbx
0x180067ff1  mov     [rsp-8+arg_10], rsi
0x180067ff6  push    rbp
0x180067ff7  push    rdi
0x180067ff8  push    r14
0x180067ffa  lea     rbp, [rsp-80h]
0x180067fff  sub     rsp, 1B0h
0x180068006  mov     rax, cs:__security_cookie
0x18006800d  xor     rax, rsp
0x180068010  mov     [rbp+90h+var_20], rax
0x180068014  mov     rsi, [rcx+110h]
0x18006801b  mov     rdi, r8
0x18006801e  mov     r14d, edx
0x180068021  mov     rbx, rcx
0x180068024  mov     eax, [rsi+48h]
0x180068027  test    eax, eax
0x180068029  jns     loc_180068205
0x18006802f  add     rsi, 50h ; 'P'
0x180068033  cmp     eax, [rsi+8]
0x180068036  jnz     loc_180068205
0x18006803c  test    rsi, rsi
0x18006803f  jz      loc_180068205
0x180068045  lea     rdx, [rbp+90h+SRWLock]
0x180068049  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006804e  mov     rax, [rbx+110h]
0x180068055  mov     rcx, [rbp+90h+SRWLock]; SRWLock
0x180068059  mov     dword ptr [rax], 2
0x18006805f  test    rcx, rcx
0x180068062  jz      short loc_18006806A
0x180068064  call    cs:__imp_ReleaseSRWLockExclusive
0x18006806a  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18006806f  mov     r9, [rax+8]
0x180068073  mov     eax, [r9]
0x180068076  cmp     eax, 5
0x180068079  jbe     loc_18006831E
0x18006807f  mov     rdx, [r9+18h]
0x180068083  mov     rcx, 400000000000h
0x18006808d  mov     rax, [r9+10h]
0x180068091  test    rcx, rax
0x180068094  jz      loc_18006831E
0x18006809a  mov     rax, rdx
0x18006809d  and     rax, rcx
0x1800680a0  cmp     rax, rdx
0x1800680a3  jnz     loc_18006831E
0x1800680a9  mov     r8, [rbx+110h]
0x1800680b0  lea     rax, aUnknown; "Unknown"
0x1800680b7  test    rdi, rdi
0x1800680ba  mov     [rbp+90h+var_F8], r14d
0x1800680be  lea     rdx, word_18009D322
0x1800680c5  mov     rcx, r9
0x1800680c8  cmovz   rdi, rax
0x1800680cc  mov     rax, [rsi+78h]
0x1800680d0  mov     [rbp+90h+var_E0], rax
0x1800680d4  add     r8, 8
0x1800680d8  mov     rax, [rsi+70h]
0x1800680dc  mov     [rbp+90h+var_D8], rax
0x1800680e0  mov     eax, [rsi+68h]
0x1800680e3  mov     [rbp+90h+var_F4], eax
0x1800680e6  mov     rax, [rsi+60h]
0x1800680ea  mov     [rbp+90h+var_D0], rax
0x1800680ee  mov     rax, [rsi+58h]
0x1800680f2  mov     [rbp+90h+var_C8], rax
0x1800680f6  mov     eax, [rsi+50h]
0x1800680f9  mov     [rbp+90h+var_F0], eax
0x1800680fc  mov     rax, [rsi+48h]
0x180068100  mov     [rbp+90h+var_C0], rax
0x180068104  mov     eax, [rsi+20h]
0x180068107  mov     [rbp+90h+var_EC], eax
0x18006810a  mov     rax, [rsi+18h]
0x18006810e  mov     [rbp+90h+var_B8], rax
0x180068112  mov     eax, [rsi]
0x180068114  mov     [rbp+90h+var_110], eax
0x180068117  mov     rax, [rsi+80h]
0x18006811e  mov     [rbp+90h+var_B0], rax
0x180068122  mov     eax, [rsi+40h]
0x180068125  mov     [rbp+90h+var_10C], eax
0x180068128  mov     rax, [rsi+38h]
0x18006812c  mov     [rbp+90h+var_A8], rax
0x180068130  mov     eax, [rsi+8]
0x180068133  mov     dword ptr [rbp+90h+SRWLock], eax
0x180068136  mov     eax, 1000000h
0x18006813b  mov     [rbp+90h+var_A0], rax
0x18006813f  mov     [rbp+90h+var_100], rax
0x180068143  lea     rax, [rbp+90h+var_E8]
0x180068147  mov     [rsp+1C0h+var_118], rax
0x18006814f  lea     rax, [rbp+90h+var_F8]
0x180068153  mov     [rsp+1C0h+var_120], rax
0x18006815b  lea     rax, [rbp+90h+var_E0]
0x18006815f  mov     [rsp+1C0h+var_128], rax
0x180068167  lea     rax, [rbp+90h+var_D8]
0x18006816b  mov     [rsp+1C0h+var_130], rax
0x180068173  lea     rax, [rbp+90h+var_F4]
0x180068177  mov     [rsp+1C0h+var_138], rax
0x18006817f  lea     rax, [rbp+90h+var_D0]
0x180068183  mov     [rsp+1C0h+var_140], rax
0x18006818b  lea     rax, [rbp+90h+var_C8]
0x18006818f  mov     [rsp+1C0h+var_148], rax
0x180068194  lea     rax, [rbp+90h+var_F0]
0x180068198  mov     [rsp+1C0h+var_150], rax
0x18006819d  lea     rax, [rbp+90h+var_C0]
0x1800681a1  mov     [rsp+1C0h+var_158], rax
0x1800681a6  lea     rax, [rbp+90h+var_EC]
0x1800681aa  mov     [rsp+1C0h+var_160], rax
0x1800681af  lea     rax, [rbp+90h+var_B8]
0x1800681b3  mov     [rsp+1C0h+var_168], rax
0x1800681b8  lea     rax, [rbp+90h+var_110]
0x1800681bc  mov     [rsp+1C0h+var_170], rax
0x1800681c1  lea     rax, [rbp+90h+var_B0]
0x1800681c5  mov     [rsp+1C0h+var_178], rax
0x1800681ca  lea     rax, [rbp+90h+var_10C]
0x1800681ce  mov     [rsp+1C0h+var_180], rax
0x1800681d3  lea     rax, [rbp+90h+var_A8]
0x1800681d7  mov     [rsp+1C0h+var_188], rax
0x1800681dc  lea     rax, [rbp+90h+SRWLock]
0x1800681e0  mov     [rsp+1C0h+var_190], rax
0x1800681e5  lea     rax, [rbp+90h+var_A0]
0x1800681e9  mov     [rsp+1C0h+var_198], rax
0x1800681ee  lea     rax, [rbp+90h+var_100]
0x1800681f2  mov     [rsp+1C0h+var_1A0], rax
0x1800681f7  mov     [rbp+90h+var_E8], rdi
0x1800681fb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@4545645645@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180068200  jmp     loc_18006831E
0x180068205  lea     rdx, [rbp+90h+var_100]
0x180068209  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006820e  mov     rax, [rbx+110h]
0x180068215  mov     rcx, [rbp+90h+var_100]; SRWLock
0x180068219  mov     dword ptr [rax], 2
0x18006821f  test    rcx, rcx
0x180068222  jz      short loc_18006822A
0x180068224  call    cs:__imp_ReleaseSRWLockExclusive
0x18006822a  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18006822f  mov     rsi, [rax+8]
0x180068233  mov     eax, [rsi]
0x180068235  cmp     eax, 5
0x180068238  jbe     loc_18006831E
0x18006823e  mov     rdx, [rsi+18h]
0x180068242  mov     rcx, 400000000000h
0x18006824c  mov     rax, [rsi+10h]
0x180068250  test    rcx, rax
0x180068253  jz      loc_18006831E
0x180068259  mov     rax, rdx
0x18006825c  and     rax, rcx
0x18006825f  cmp     rax, rdx
0x180068262  jnz     loc_18006831E
0x180068268  lea     rax, aUnknown; "Unknown"
0x18006826f  mov     dword ptr [rbp+90h+SRWLock], r14d
0x180068273  test    rdi, rdi
0x180068276  cmovz   rdi, rax
0x18006827a  call    cs:__imp_GetCurrentThreadId
0x180068280  mov     r8, [rbx+110h]
0x180068287  mov     [rbp+90h+var_10C], eax
0x18006828a  mov     eax, [r8+48h]
0x18006828e  mov     [rbp+90h+var_110], eax
0x180068291  mov     eax, 1000000h
0x180068296  mov     [rbp+90h+var_100], rax
0x18006829a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006829e  inc     rax
0x1800682a1  cmp     byte ptr [rdi+rax], 0
0x1800682a5  jnz     short loc_18006829E
0x1800682a7  inc     eax
0x1800682a9  mov     [rbp+90h+var_30], rdi
0x1800682ad  mov     [rbp+90h+var_28], eax
0x1800682b0  lea     rdx, word_18009D162
0x1800682b7  lea     rax, [rbp+90h+SRWLock]
0x1800682bb  mov     [rbp+90h+var_24], 0
0x1800682c2  mov     [rbp+90h+var_40], rax
0x1800682c6  add     r8, 8
0x1800682ca  lea     rax, [rbp+90h+var_10C]
0x1800682ce  mov     [rbp+90h+var_38], 4
0x1800682d6  mov     [rbp+90h+var_50], rax
0x1800682da  xor     r9d, r9d
0x1800682dd  lea     rax, [rbp+90h+var_110]
0x1800682e1  mov     [rbp+90h+var_48], 4
0x1800682e9  mov     [rbp+90h+var_60], rax
0x1800682ed  mov     rcx, rsi
0x1800682f0  lea     rax, [rbp+90h+var_100]
0x1800682f4  mov     [rbp+90h+var_58], 4
0x1800682fc  mov     [rbp+90h+var_70], rax
0x180068300  lea     rax, [rbp+90h+var_90]
0x180068304  mov     [rsp+1C0h+var_198], rax
0x180068309  mov     dword ptr [rsp+1C0h+var_1A0], 7
0x180068311  mov     [rbp+90h+var_68], 8
0x180068319  call    _tlgWriteTransfer_EventWriteTransfer
0x18006831e  mov     rcx, rbx
0x180068321  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180068326  mov     rcx, [rbp+90h+var_20]
0x18006832a  xor     rcx, rsp; StackCookie
0x18006832d  call    __security_check_cookie
0x180068332  lea     r11, [rsp+1C0h+var_10]
0x18006833a  mov     rbx, [r11+28h]
0x18006833e  mov     rsi, [r11+30h]
0x180068342  mov     rsp, r11
0x180068345  pop     r14
0x180068347  pop     rdi
0x180068348  pop     rbp
0x180068349  retn
```
