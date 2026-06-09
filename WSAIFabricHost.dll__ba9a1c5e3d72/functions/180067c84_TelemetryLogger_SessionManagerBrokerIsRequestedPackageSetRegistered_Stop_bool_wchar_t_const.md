# TelemetryLogger::SessionManagerBrokerIsRequestedPackageSetRegistered::Stop(bool,wchar_t const *)

- ea: `0x180067c84`
- end: `0x180067fe3`
- name: `?Stop@SessionManagerBrokerIsRequestedPackageSetRegistered@TelemetryLogger@@QEAAX_NPEB_W@Z`
- size: `863`
- prototype: `void __fastcall(TelemetryLogger::SessionManagerBrokerIsRequestedPackageSetRegistered *__hidden this, bool, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180062158`

## callees

- `0x1800017dc`
- `0x180003380`
- `0x180004ca0`
- `0x180017790`
- `0x180061660`
- `0x1800625bc`
- `0x180067c84`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067d03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067eb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067d03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180067eb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067efe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067efe`

## pseudocode

```c
void __fastcall TelemetryLogger::SessionManagerBrokerIsRequestedPackageSetRegistered::Stop(
        TelemetryLogger::SessionManagerBrokerIsRequestedPackageSetRegistered *this,
        char a2,
        const wchar_t *a3)
{
  __int64 v3; // rsi
  int v7; // eax
  int *v8; // rsi
  RTL_SRWLOCK *v9; // rcx
  __int64 v10; // r9
  __int64 v11; // r8
  int v12; // edi
  RTL_SRWLOCK *v13; // rcx
  __int64 v14; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v16; // r8
  __int64 v17; // rdi
  _BYTE v18[4]; // [rsp+B0h] [rbp-80h] BYREF
  int v19; // [rsp+B4h] [rbp-7Ch] BYREF
  PSRWLOCK SRWLock; // [rsp+B8h] [rbp-78h] BYREF
  PSRWLOCK v21; // [rsp+C0h] [rbp-70h] BYREF
  int v22; // [rsp+C8h] [rbp-68h] BYREF
  int v23; // [rsp+CCh] [rbp-64h] BYREF
  int v24; // [rsp+D0h] [rbp-60h] BYREF
  int v25; // [rsp+D4h] [rbp-5Ch] BYREF
  const wchar_t *v26; // [rsp+D8h] [rbp-58h] BYREF
  const wchar_t *v27; // [rsp+E0h] [rbp-50h] BYREF
  const wchar_t *v28; // [rsp+E8h] [rbp-48h] BYREF
  const wchar_t *v29; // [rsp+F0h] [rbp-40h] BYREF
  const wchar_t *v30; // [rsp+F8h] [rbp-38h] BYREF
  const wchar_t *v31; // [rsp+100h] [rbp-30h] BYREF
  const wchar_t *v32; // [rsp+108h] [rbp-28h] BYREF
  const wchar_t *v33; // [rsp+110h] [rbp-20h] BYREF
  const wchar_t *v34; // [rsp+118h] [rbp-18h] BYREF
  __int64 v35; // [rsp+120h] [rbp-10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v36; // [rsp+130h] [rbp+0h] BYREF
  PSRWLOCK *v37; // [rsp+150h] [rbp+20h]
  __int64 v38; // [rsp+158h] [rbp+28h]
  int *v39; // [rsp+160h] [rbp+30h]
  __int64 v40; // [rsp+168h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+170h] [rbp+40h]
  __int64 v42; // [rsp+178h] [rbp+48h]
  _BYTE *v43; // [rsp+180h] [rbp+50h]
  __int64 v44; // [rsp+188h] [rbp+58h]
  const wchar_t *v45; // [rsp+190h] [rbp+60h]
  int v46; // [rsp+198h] [rbp+68h]
  int v47; // [rsp+19Ch] [rbp+6Ch]

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
      v27 = (const wchar_t *)*((_QWORD *)v8 + 15);
      v28 = (const wchar_t *)*((_QWORD *)v8 + 14);
      v11 = *((_QWORD *)this + 34);
      v22 = v8[26];
      v29 = (const wchar_t *)*((_QWORD *)v8 + 12);
      v30 = (const wchar_t *)*((_QWORD *)v8 + 11);
      v23 = v8[20];
      v31 = (const wchar_t *)*((_QWORD *)v8 + 9);
      v24 = v8[8];
      v32 = (const wchar_t *)*((_QWORD *)v8 + 3);
      v25 = *v8;
      v33 = (const wchar_t *)*((_QWORD *)v8 + 16);
      v19 = v8[16];
      v34 = (const wchar_t *)*((_QWORD *)v8 + 7);
      LODWORD(SRWLock) = v8[2];
      v35 = 0x1000000;
      v21 = (PSRWLOCK)0x1000000;
      v26 = a3;
      v18[0] = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>>(
        v10,
        (__int64)&word_18009CF76,
        v11 + 8,
        v10,
        (__int64)&v21,
        (__int64)&v35,
        (__int64)&SRWLock,
        &v34,
        (__int64)&v19,
        &v33,
        (__int64)&v25,
        &v32,
        (__int64)&v24,
        &v31,
        (__int64)&v23,
        &v30,
        &v29,
        (__int64)&v22,
        &v28,
        &v27,
        (__int64)v18,
        &v26);
    }
  }
  else
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v21);
    v12 = 2;
    v13 = v21;
    **((_DWORD **)this + 34) = 2;
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
    v14 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v14 > 5u
      && (*(_QWORD *)(v14 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v14 + 24) & 0x400000000000LL) == *(_QWORD *)(v14 + 24) )
    {
      v18[0] = a2;
      CurrentThreadId = GetCurrentThreadId();
      v16 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v19 = *(_DWORD *)(v16 + 72);
      v21 = (PSRWLOCK)0x1000000;
      if ( a3 )
      {
        v17 = -1;
        do
          ++v17;
        while ( a3[v17] );
        v12 = 2 * v17 + 2;
      }
      else
      {
        a3 = &pszText;
      }
      v45 = a3;
      v43 = v18;
      v46 = v12;
      p_SRWLock = &SRWLock;
      v47 = 0;
      v39 = &v19;
      v44 = 1;
      v37 = &v21;
      v42 = 4;
      v40 = 4;
      v38 = 8;
      tlgWriteTransfer_EventWriteTransfer(v14, (unsigned __int8 *)byte_18009CE57, (const GUID *)(v16 + 8), 0, 7u, &v36);
    }
  }
  wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180067c84  mov     [rsp-8+arg_8], rbx
0x180067c89  mov     [rsp-8+arg_10], rsi
0x180067c8e  push    rbp
0x180067c8f  push    rdi
0x180067c90  push    r12
0x180067c92  push    r14
0x180067c94  push    r15
0x180067c96  lea     rbp, [rsp-80h]
0x180067c9b  sub     rsp, 1B0h
0x180067ca2  mov     rax, cs:__security_cookie
0x180067ca9  xor     rax, rsp
0x180067cac  mov     [rbp+0A0h+var_30], rax
0x180067cb0  mov     rsi, [rcx+110h]
0x180067cb7  xor     r12d, r12d
0x180067cba  mov     r14, r8
0x180067cbd  mov     r15b, dl
0x180067cc0  mov     rbx, rcx
0x180067cc3  mov     eax, [rsi+48h]
0x180067cc6  test    eax, eax
0x180067cc8  jns     loc_180067E96
0x180067cce  add     rsi, 50h ; 'P'
0x180067cd2  cmp     eax, [rsi+8]
0x180067cd5  jnz     loc_180067E96
0x180067cdb  test    rsi, rsi
0x180067cde  jz      loc_180067E96
0x180067ce4  lea     rdx, [rbp+0A0h+SRWLock]
0x180067ce8  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180067ced  mov     rax, [rbx+110h]
0x180067cf4  mov     rcx, [rbp+0A0h+SRWLock]; SRWLock
0x180067cf8  mov     dword ptr [rax], 2
0x180067cfe  test    rcx, rcx
0x180067d01  jz      short loc_180067D09
0x180067d03  call    cs:__imp_ReleaseSRWLockExclusive
0x180067d09  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180067d0e  mov     r9, [rax+8]
0x180067d12  mov     eax, [r9]
0x180067d15  cmp     eax, 5
0x180067d18  jbe     loc_180067FB3
0x180067d1e  mov     rdx, [r9+18h]
0x180067d22  mov     rcx, 400000000000h
0x180067d2c  mov     rax, [r9+10h]
0x180067d30  test    rcx, rax
0x180067d33  jz      loc_180067FB3
0x180067d39  mov     rax, rdx
0x180067d3c  and     rax, rcx
0x180067d3f  cmp     rax, rdx
0x180067d42  jnz     loc_180067FB3
0x180067d48  mov     rax, [rsi+78h]
0x180067d4c  lea     rdx, word_18009CF76
0x180067d53  mov     [rbp+0A0h+var_F0], rax
0x180067d57  mov     rcx, r9
0x180067d5a  mov     rax, [rsi+70h]
0x180067d5e  mov     [rbp+0A0h+var_E8], rax
0x180067d62  mov     eax, [rsi+68h]
0x180067d65  mov     r8, [rbx+110h]
0x180067d6c  mov     [rbp+0A0h+var_108], eax
0x180067d6f  add     r8, 8
0x180067d73  mov     rax, [rsi+60h]
0x180067d77  mov     [rbp+0A0h+var_E0], rax
0x180067d7b  mov     rax, [rsi+58h]
0x180067d7f  mov     [rbp+0A0h+var_D8], rax
0x180067d83  mov     eax, [rsi+50h]
0x180067d86  mov     [rbp+0A0h+var_104], eax
0x180067d89  mov     rax, [rsi+48h]
0x180067d8d  mov     [rbp+0A0h+var_D0], rax
0x180067d91  mov     eax, [rsi+20h]
0x180067d94  mov     [rbp+0A0h+var_100], eax
0x180067d97  mov     rax, [rsi+18h]
0x180067d9b  mov     [rbp+0A0h+var_C8], rax
0x180067d9f  mov     eax, [rsi]
0x180067da1  mov     [rbp+0A0h+var_FC], eax
0x180067da4  mov     rax, [rsi+80h]
0x180067dab  mov     [rbp+0A0h+var_C0], rax
0x180067daf  mov     eax, [rsi+40h]
0x180067db2  mov     [rbp+0A0h+var_11C], eax
0x180067db5  mov     rax, [rsi+38h]
0x180067db9  mov     [rbp+0A0h+var_B8], rax
0x180067dbd  mov     eax, [rsi+8]
0x180067dc0  mov     dword ptr [rbp+0A0h+SRWLock], eax
0x180067dc3  mov     eax, 1000000h
0x180067dc8  mov     [rbp+0A0h+var_B0], rax
0x180067dcc  mov     [rbp+0A0h+var_110], rax
0x180067dd0  lea     rax, [rbp+0A0h+var_F8]
0x180067dd4  mov     [rsp+1D0h+var_128], rax
0x180067ddc  lea     rax, [rbp+0A0h+var_120]
0x180067de0  mov     [rsp+1D0h+var_130], rax
0x180067de8  lea     rax, [rbp+0A0h+var_F0]
0x180067dec  mov     [rsp+1D0h+var_138], rax
0x180067df4  lea     rax, [rbp+0A0h+var_E8]
0x180067df8  mov     [rsp+1D0h+var_140], rax
0x180067e00  lea     rax, [rbp+0A0h+var_108]
0x180067e04  mov     [rsp+1D0h+var_148], rax
0x180067e0c  lea     rax, [rbp+0A0h+var_E0]
0x180067e10  mov     [rsp+1D0h+var_150], rax
0x180067e18  lea     rax, [rbp+0A0h+var_D8]
0x180067e1c  mov     [rsp+1D0h+var_158], rax
0x180067e21  lea     rax, [rbp+0A0h+var_104]
0x180067e25  mov     [rsp+1D0h+var_160], rax
0x180067e2a  lea     rax, [rbp+0A0h+var_D0]
0x180067e2e  mov     [rsp+1D0h+var_168], rax
0x180067e33  lea     rax, [rbp+0A0h+var_100]
0x180067e37  mov     [rsp+1D0h+var_170], rax
0x180067e3c  lea     rax, [rbp+0A0h+var_C8]
0x180067e40  mov     [rsp+1D0h+var_178], rax
0x180067e45  lea     rax, [rbp+0A0h+var_FC]
0x180067e49  mov     [rsp+1D0h+var_180], rax
0x180067e4e  lea     rax, [rbp+0A0h+var_C0]
0x180067e52  mov     [rsp+1D0h+var_188], rax
0x180067e57  lea     rax, [rbp+0A0h+var_11C]
0x180067e5b  mov     [rsp+1D0h+var_190], rax
0x180067e60  lea     rax, [rbp+0A0h+var_B8]
0x180067e64  mov     [rsp+1D0h+var_198], rax
0x180067e69  lea     rax, [rbp+0A0h+SRWLock]
0x180067e6d  mov     [rsp+1D0h+var_1A0], rax
0x180067e72  lea     rax, [rbp+0A0h+var_B0]
0x180067e76  mov     [rsp+1D0h+var_1A8], rax
0x180067e7b  lea     rax, [rbp+0A0h+var_110]
0x180067e7f  mov     [rsp+1D0h+var_1B0], rax
0x180067e84  mov     [rbp+0A0h+var_F8], r14
0x180067e88  mov     [rbp+0A0h+var_120], r15b
0x180067e8c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456AEBU?$_tlgWrapperByVal@$00@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<wchar_t> const &)
0x180067e91  jmp     loc_180067FB3
0x180067e96  lea     rdx, [rbp+0A0h+var_110]
0x180067e9a  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180067e9f  mov     rax, [rbx+110h]
0x180067ea6  mov     edi, 2
0x180067eab  mov     rcx, [rbp+0A0h+var_110]; SRWLock
0x180067eaf  mov     [rax], edi
0x180067eb1  test    rcx, rcx
0x180067eb4  jz      short loc_180067EBC
0x180067eb6  call    cs:__imp_ReleaseSRWLockExclusive
0x180067ebc  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180067ec1  mov     rsi, [rax+8]
0x180067ec5  mov     eax, [rsi]
0x180067ec7  cmp     eax, 5
0x180067eca  jbe     loc_180067FB3
0x180067ed0  mov     rdx, [rsi+18h]
0x180067ed4  mov     rcx, 400000000000h
0x180067ede  mov     rax, [rsi+10h]
0x180067ee2  test    rcx, rax
0x180067ee5  jz      loc_180067FB3
0x180067eeb  mov     rax, rdx
0x180067eee  and     rax, rcx
0x180067ef1  cmp     rax, rdx
0x180067ef4  jnz     loc_180067FB3
0x180067efa  mov     [rbp+0A0h+var_120], r15b
0x180067efe  call    cs:__imp_GetCurrentThreadId
0x180067f04  mov     r8, [rbx+110h]
0x180067f0b  mov     dword ptr [rbp+0A0h+SRWLock], eax
0x180067f0e  mov     eax, [r8+48h]
0x180067f12  mov     [rbp+0A0h+var_11C], eax
0x180067f15  mov     eax, 1000000h
0x180067f1a  mov     [rbp+0A0h+var_110], rax
0x180067f1e  test    r14, r14
0x180067f21  jz      short loc_180067F3A
0x180067f23  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180067f27  inc     rdi
0x180067f2a  cmp     [r14+rdi*2], r12w
0x180067f2f  jnz     short loc_180067F27
0x180067f31  lea     edi, ds:2[rdi*2]
0x180067f38  jmp     short loc_180067F41
0x180067f3a  lea     r14, pszText
0x180067f41  lea     rax, [rbp+0A0h+var_120]
0x180067f45  mov     [rbp+0A0h+var_40], r14
0x180067f49  mov     [rbp+0A0h+var_50], rax
0x180067f4d  lea     rdx, byte_18009CE57
0x180067f54  lea     rax, [rbp+0A0h+SRWLock]
0x180067f58  mov     [rbp+0A0h+var_38], edi
0x180067f5b  mov     [rbp+0A0h+var_60], rax
0x180067f5f  add     r8, 8
0x180067f63  lea     rax, [rbp+0A0h+var_11C]
0x180067f67  mov     [rbp+0A0h+var_34], r12d
0x180067f6b  mov     [rbp+0A0h+var_70], rax
0x180067f6f  xor     r9d, r9d
0x180067f72  lea     rax, [rbp+0A0h+var_110]
0x180067f76  mov     [rbp+0A0h+var_48], 1
0x180067f7e  mov     [rbp+0A0h+var_80], rax
0x180067f82  mov     rcx, rsi
0x180067f85  lea     rax, [rbp+0A0h+var_A0]
0x180067f89  mov     [rbp+0A0h+var_58], 4
0x180067f91  mov     [rsp+1D0h+var_1A8], rax
0x180067f96  mov     dword ptr [rsp+1D0h+var_1B0], 7
0x180067f9e  mov     [rbp+0A0h+var_68], 4
0x180067fa6  mov     [rbp+0A0h+var_78], 8
0x180067fae  call    _tlgWriteTransfer_EventWriteTransfer
0x180067fb3  mov     rcx, rbx
0x180067fb6  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180067fbb  mov     rcx, [rbp+0A0h+var_30]
0x180067fbf  xor     rcx, rsp; StackCookie
0x180067fc2  call    __security_check_cookie
0x180067fc7  lea     r11, [rsp+1D0h+var_20]
0x180067fcf  mov     rbx, [r11+38h]
0x180067fd3  mov     rsi, [r11+40h]
0x180067fd7  mov     rsp, r11
0x180067fda  pop     r15
0x180067fdc  pop     r14
0x180067fde  pop     r12
0x180067fe0  pop     rdi
0x180067fe1  pop     rbp
0x180067fe2  retn
```
