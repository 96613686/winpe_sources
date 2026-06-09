# TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::Stop(unsigned __int64,bool,char const *)

- ea: `0x18006870c`
- end: `0x180068a8d`
- name: `?Stop@UpdateModelCacheOnDriverUpdateStart@TelemetryLogger@@QEAAX_K_NPEBD@Z`
- size: `897`
- prototype: `void __fastcall(TelemetryLogger::UpdateModelCacheOnDriverUpdateStart *__hidden this, unsigned __int64, bool, const char *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18005a8c0`
- `0x180065ea0`

## callees

- `0x1800017dc`
- `0x180002118`
- `0x180004ca0`
- `0x180017790`
- `0x180061660`
- `0x1800625bc`
- `0x18006870c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068788`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068958`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068788`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180068958`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800689b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800689b2`

## pseudocode

```c
void __fastcall TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::Stop(
        TelemetryLogger::UpdateModelCacheOnDriverUpdateStart *this,
        RTL_SRWLOCK *a2,
        char a3,
        const wchar_t *a4)
{
  __int64 v4; // rsi
  int v9; // eax
  int *v10; // rsi
  RTL_SRWLOCK *v11; // rcx
  __int64 v12; // r9
  __int64 v13; // r8
  RTL_SRWLOCK *v14; // rcx
  __int64 v15; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  __int64 v18; // rax
  _BYTE v19[4]; // [rsp+C0h] [rbp-80h] BYREF
  int v20; // [rsp+C4h] [rbp-7Ch] BYREF
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK v22; // [rsp+D0h] [rbp-70h] BYREF
  int v23; // [rsp+D8h] [rbp-68h] BYREF
  int v24; // [rsp+DCh] [rbp-64h] BYREF
  int v25; // [rsp+E0h] [rbp-60h] BYREF
  int v26; // [rsp+E4h] [rbp-5Ch] BYREF
  __int64 v27; // [rsp+E8h] [rbp-58h] BYREF
  const wchar_t *v28; // [rsp+F0h] [rbp-50h] BYREF
  RTL_SRWLOCK *v29; // [rsp+F8h] [rbp-48h] BYREF
  const wchar_t *v30; // [rsp+100h] [rbp-40h] BYREF
  const wchar_t *v31; // [rsp+108h] [rbp-38h] BYREF
  const wchar_t *v32; // [rsp+110h] [rbp-30h] BYREF
  const wchar_t *v33; // [rsp+118h] [rbp-28h] BYREF
  const wchar_t *v34; // [rsp+120h] [rbp-20h] BYREF
  const wchar_t *v35; // [rsp+128h] [rbp-18h] BYREF
  const wchar_t *v36; // [rsp+130h] [rbp-10h] BYREF
  const wchar_t *v37; // [rsp+138h] [rbp-8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v38; // [rsp+140h] [rbp+0h] BYREF
  __int64 *v39; // [rsp+160h] [rbp+20h]
  __int64 v40; // [rsp+168h] [rbp+28h]
  int *v41; // [rsp+170h] [rbp+30h]
  __int64 v42; // [rsp+178h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+180h] [rbp+40h]
  __int64 v44; // [rsp+188h] [rbp+48h]
  PSRWLOCK *v45; // [rsp+190h] [rbp+50h]
  __int64 v46; // [rsp+198h] [rbp+58h]
  _BYTE *v47; // [rsp+1A0h] [rbp+60h]
  __int64 v48; // [rsp+1A8h] [rbp+68h]
  const wchar_t *v49; // [rsp+1B0h] [rbp+70h]
  int v50; // [rsp+1B8h] [rbp+78h]
  int v51; // [rsp+1BCh] [rbp+7Ch]

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
      v13 = *((_QWORD *)this + 34);
      v19[0] = a3;
      v29 = a2;
      if ( !a4 )
        a4 = (const wchar_t *)"Unknown";
      v30 = (const wchar_t *)*((_QWORD *)v10 + 15);
      v31 = (const wchar_t *)*((_QWORD *)v10 + 14);
      v23 = v10[26];
      v32 = (const wchar_t *)*((_QWORD *)v10 + 12);
      v33 = (const wchar_t *)*((_QWORD *)v10 + 11);
      v24 = v10[20];
      v34 = (const wchar_t *)*((_QWORD *)v10 + 9);
      v25 = v10[8];
      v35 = (const wchar_t *)*((_QWORD *)v10 + 3);
      v26 = *v10;
      v36 = (const wchar_t *)*((_QWORD *)v10 + 16);
      v20 = v10[16];
      v37 = (const wchar_t *)*((_QWORD *)v10 + 7);
      LODWORD(SRWLock) = v10[2];
      v27 = 0x1000000;
      v22 = (PSRWLOCK)0x1000000;
      v28 = a4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapSz<char>>(
        v12,
        (__int64)&byte_18009C8E7,
        v13 + 8,
        v12,
        (__int64)&v22,
        (__int64)&v27,
        (__int64)&SRWLock,
        &v37,
        (__int64)&v20,
        &v36,
        (__int64)&v26,
        &v35,
        (__int64)&v25,
        &v34,
        (__int64)&v24,
        &v33,
        &v32,
        (__int64)&v23,
        &v31,
        &v30,
        (__int64)&v29,
        (__int64)v19,
        &v28);
    }
  }
  else
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v22);
    v14 = v22;
    **((_DWORD **)this + 34) = 2;
    if ( v14 )
      ReleaseSRWLockExclusive(v14);
    v15 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v15 > 5u
      && (*(_QWORD *)(v15 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v15 + 24) & 0x400000000000LL) == *(_QWORD *)(v15 + 24) )
    {
      v19[0] = a3;
      v22 = a2;
      if ( !a4 )
        a4 = (const wchar_t *)"Unknown";
      CurrentThreadId = GetCurrentThreadId();
      v17 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v20 = *(_DWORD *)(v17 + 72);
      v27 = 0x1000000;
      v18 = -1;
      do
        ++v18;
      while ( *((_BYTE *)a4 + v18) );
      v49 = a4;
      v50 = v18 + 1;
      v51 = 0;
      v47 = v19;
      v48 = 1;
      v45 = &v22;
      v46 = 8;
      p_SRWLock = &SRWLock;
      v44 = 4;
      v41 = &v20;
      v39 = &v27;
      v42 = 4;
      v40 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        v15,
        (unsigned __int8 *)&dword_18009C724,
        (const GUID *)(v17 + 8),
        0,
        8u,
        &v38);
    }
  }
  wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18006870c  push    rbp
0x18006870e  push    rbx
0x18006870f  push    rsi
0x180068710  push    rdi
0x180068711  push    r14
0x180068713  push    r15
0x180068715  lea     rbp, [rsp-98h]
0x18006871d  sub     rsp, 1D8h
0x180068724  mov     rax, cs:__security_cookie
0x18006872b  xor     rax, rsp
0x18006872e  mov     [rbp+0C0h+var_40], rax
0x180068735  mov     rsi, [rcx+110h]
0x18006873c  mov     rdi, r9
0x18006873f  mov     r14b, r8b
0x180068742  mov     r15, rdx
0x180068745  mov     rbx, rcx
0x180068748  mov     eax, [rsi+48h]
0x18006874b  test    eax, eax
0x18006874d  jns     loc_180068939
0x180068753  add     rsi, 50h ; 'P'
0x180068757  cmp     eax, [rsi+8]
0x18006875a  jnz     loc_180068939
0x180068760  test    rsi, rsi
0x180068763  jz      loc_180068939
0x180068769  lea     rdx, [rbp+0C0h+SRWLock]
0x18006876d  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180068772  mov     rax, [rbx+110h]
0x180068779  mov     rcx, [rbp+0C0h+SRWLock]; SRWLock
0x18006877d  mov     dword ptr [rax], 2
0x180068783  test    rcx, rcx
0x180068786  jz      short loc_18006878E
0x180068788  call    cs:__imp_ReleaseSRWLockExclusive
0x18006878e  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180068793  mov     r9, [rax+8]
0x180068797  mov     eax, [r9]
0x18006879a  cmp     eax, 5
0x18006879d  jbe     loc_180068A66
0x1800687a3  mov     rdx, [r9+18h]
0x1800687a7  mov     rcx, 400000000000h
0x1800687b1  mov     rax, [r9+10h]
0x1800687b5  test    rcx, rax
0x1800687b8  jz      loc_180068A66
0x1800687be  mov     rax, rdx
0x1800687c1  and     rax, rcx
0x1800687c4  cmp     rax, rdx
0x1800687c7  jnz     loc_180068A66
0x1800687cd  mov     r8, [rbx+110h]
0x1800687d4  lea     rax, aUnknown; "Unknown"
0x1800687db  test    rdi, rdi
0x1800687de  mov     [rbp+0C0h+var_140], r14b
0x1800687e2  lea     rdx, byte_18009C8E7
0x1800687e9  mov     [rbp+0C0h+var_108], r15
0x1800687ed  cmovz   rdi, rax
0x1800687f1  mov     rcx, r9
0x1800687f4  mov     rax, [rsi+78h]
0x1800687f8  add     r8, 8
0x1800687fc  mov     [rbp+0C0h+var_100], rax
0x180068800  mov     rax, [rsi+70h]
0x180068804  mov     [rbp+0C0h+var_F8], rax
0x180068808  mov     eax, [rsi+68h]
0x18006880b  mov     [rbp+0C0h+var_128], eax
0x18006880e  mov     rax, [rsi+60h]
0x180068812  mov     [rbp+0C0h+var_F0], rax
0x180068816  mov     rax, [rsi+58h]
0x18006881a  mov     [rbp+0C0h+var_E8], rax
0x18006881e  mov     eax, [rsi+50h]
0x180068821  mov     [rbp+0C0h+var_124], eax
0x180068824  mov     rax, [rsi+48h]
0x180068828  mov     [rbp+0C0h+var_E0], rax
0x18006882c  mov     eax, [rsi+20h]
0x18006882f  mov     [rbp+0C0h+var_120], eax
0x180068832  mov     rax, [rsi+18h]
0x180068836  mov     [rbp+0C0h+var_D8], rax
0x18006883a  mov     eax, [rsi]
0x18006883c  mov     [rbp+0C0h+var_11C], eax
0x18006883f  mov     rax, [rsi+80h]
0x180068846  mov     [rbp+0C0h+var_D0], rax
0x18006884a  mov     eax, [rsi+40h]
0x18006884d  mov     [rbp+0C0h+var_13C], eax
0x180068850  mov     rax, [rsi+38h]
0x180068854  mov     [rbp+0C0h+var_C8], rax
0x180068858  mov     eax, [rsi+8]
0x18006885b  mov     dword ptr [rbp+0C0h+SRWLock], eax
0x18006885e  mov     eax, 1000000h
0x180068863  mov     [rbp+0C0h+var_118], rax
0x180068867  mov     [rbp+0C0h+var_130], rax
0x18006886b  lea     rax, [rbp+0C0h+var_110]
0x18006886f  mov     [rsp+200h+var_150], rax
0x180068877  lea     rax, [rbp+0C0h+var_140]
0x18006887b  mov     [rsp+200h+var_158], rax
0x180068883  lea     rax, [rbp+0C0h+var_108]
0x180068887  mov     [rsp+200h+var_160], rax
0x18006888f  lea     rax, [rbp+0C0h+var_100]
0x180068893  mov     [rsp+200h+var_168], rax
0x18006889b  lea     rax, [rbp+0C0h+var_F8]
0x18006889f  mov     [rsp+200h+var_170], rax
0x1800688a7  lea     rax, [rbp+0C0h+var_128]
0x1800688ab  mov     [rsp+200h+var_178], rax
0x1800688b3  lea     rax, [rbp+0C0h+var_F0]
0x1800688b7  mov     [rsp+200h+var_180], rax
0x1800688bf  lea     rax, [rbp+0C0h+var_E8]
0x1800688c3  mov     [rsp+200h+var_188], rax
0x1800688c8  lea     rax, [rbp+0C0h+var_124]
0x1800688cc  mov     [rsp+200h+var_190], rax
0x1800688d1  lea     rax, [rbp+0C0h+var_E0]
0x1800688d5  mov     [rsp+200h+var_198], rax
0x1800688da  lea     rax, [rbp+0C0h+var_120]
0x1800688de  mov     [rsp+200h+var_1A0], rax
0x1800688e3  lea     rax, [rbp+0C0h+var_D8]
0x1800688e7  mov     [rsp+200h+var_1A8], rax
0x1800688ec  lea     rax, [rbp+0C0h+var_11C]
0x1800688f0  mov     [rsp+200h+var_1B0], rax
0x1800688f5  lea     rax, [rbp+0C0h+var_D0]
0x1800688f9  mov     [rsp+200h+var_1B8], rax
0x1800688fe  lea     rax, [rbp+0C0h+var_13C]
0x180068902  mov     [rsp+200h+var_1C0], rax
0x180068907  lea     rax, [rbp+0C0h+var_C8]
0x18006890b  mov     [rsp+200h+var_1C8], rax
0x180068910  lea     rax, [rbp+0C0h+SRWLock]
0x180068914  mov     [rsp+200h+var_1D0], rax
0x180068919  lea     rax, [rbp+0C0h+var_118]
0x18006891d  mov     [rsp+200h+var_1D8], rax
0x180068922  lea     rax, [rbp+0C0h+var_130]
0x180068926  mov     [rsp+200h+var_1E0], rax
0x18006892b  mov     [rbp+0C0h+var_110], rdi
0x18006892f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U1@U?$_tlgWrapperByVal@$00@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@454564563AEBU?$_tlgWrapperByVal@$00@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<char> const &)
0x180068934  jmp     loc_180068A66
0x180068939  lea     rdx, [rbp+0C0h+var_130]
0x18006893d  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180068942  mov     rax, [rbx+110h]
0x180068949  mov     rcx, [rbp+0C0h+var_130]; SRWLock
0x18006894d  mov     dword ptr [rax], 2
0x180068953  test    rcx, rcx
0x180068956  jz      short loc_18006895E
0x180068958  call    cs:__imp_ReleaseSRWLockExclusive
0x18006895e  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180068963  mov     rsi, [rax+8]
0x180068967  mov     eax, [rsi]
0x180068969  cmp     eax, 5
0x18006896c  jbe     loc_180068A66
0x180068972  mov     rdx, [rsi+18h]
0x180068976  mov     rcx, 400000000000h
0x180068980  mov     rax, [rsi+10h]
0x180068984  test    rcx, rax
0x180068987  jz      loc_180068A66
0x18006898d  mov     rax, rdx
0x180068990  and     rax, rcx
0x180068993  cmp     rax, rdx
0x180068996  jnz     loc_180068A66
0x18006899c  lea     rax, aUnknown; "Unknown"
0x1800689a3  mov     [rbp+0C0h+var_140], r14b
0x1800689a7  test    rdi, rdi
0x1800689aa  mov     [rbp+0C0h+var_130], r15
0x1800689ae  cmovz   rdi, rax
0x1800689b2  call    cs:__imp_GetCurrentThreadId
0x1800689b8  mov     r8, [rbx+110h]
0x1800689bf  mov     dword ptr [rbp+0C0h+SRWLock], eax
0x1800689c2  mov     eax, [r8+48h]
0x1800689c6  mov     [rbp+0C0h+var_13C], eax
0x1800689c9  mov     eax, 1000000h
0x1800689ce  mov     [rbp+0C0h+var_118], rax
0x1800689d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800689d6  inc     rax
0x1800689d9  cmp     byte ptr [rdi+rax], 0
0x1800689dd  jnz     short loc_1800689D6
0x1800689df  inc     eax
0x1800689e1  mov     [rbp+0C0h+var_50], rdi
0x1800689e5  mov     [rbp+0C0h+var_48], eax
0x1800689e8  lea     rdx, dword_18009C724
0x1800689ef  lea     rax, [rbp+0C0h+var_140]
0x1800689f3  mov     [rbp+0C0h+var_44], 0
0x1800689fa  mov     [rbp+0C0h+var_60], rax
0x1800689fe  add     r8, 8
0x180068a02  lea     rax, [rbp+0C0h+var_130]
0x180068a06  mov     [rbp+0C0h+var_58], 1
0x180068a0e  mov     [rbp+0C0h+var_70], rax
0x180068a12  xor     r9d, r9d
0x180068a15  lea     rax, [rbp+0C0h+SRWLock]
0x180068a19  mov     [rbp+0C0h+var_68], 8
0x180068a21  mov     [rbp+0C0h+var_80], rax
0x180068a25  mov     rcx, rsi
0x180068a28  lea     rax, [rbp+0C0h+var_13C]
0x180068a2c  mov     [rbp+0C0h+var_78], 4
0x180068a34  mov     [rbp+0C0h+var_90], rax
0x180068a38  lea     rax, [rbp+0C0h+var_118]
0x180068a3c  mov     [rbp+0C0h+var_A0], rax
0x180068a40  lea     rax, [rbp+0C0h+var_C0]
0x180068a44  mov     [rsp+200h+var_1D8], rax
0x180068a49  mov     dword ptr [rsp+200h+var_1E0], 8
0x180068a51  mov     [rbp+0C0h+var_88], 4
0x180068a59  mov     [rbp+0C0h+var_98], 8
0x180068a61  call    _tlgWriteTransfer_EventWriteTransfer
0x180068a66  mov     rcx, rbx
0x180068a69  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180068a6e  mov     rcx, [rbp+0C0h+var_40]
0x180068a75  xor     rcx, rsp; StackCookie
0x180068a78  call    __security_check_cookie
0x180068a7d  add     rsp, 1D8h
0x180068a84  pop     r15
0x180068a86  pop     r14
0x180068a88  pop     rdi
0x180068a89  pop     rsi
0x180068a8a  pop     rbx
0x180068a8b  pop     rbp
0x180068a8c  retn
```
