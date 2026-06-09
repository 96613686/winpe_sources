# TelemetryLogger::UpdateModelCacheOnDriverUpdateCacheModels::Stop(bool,unsigned __int64,long,char const *)

- ea: `0x180068350`
- end: `0x180068705`
- name: `?Stop@UpdateModelCacheOnDriverUpdateCacheModels@TelemetryLogger@@QEAAX_N_KJPEBD@Z`
- size: `949`
- prototype: `void __fastcall(TelemetryLogger::UpdateModelCacheOnDriverUpdateCacheModels *__hidden this, bool, unsigned __int64, int, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18005aeb8`

## callees

- `0x1800017dc`
- `0x180003054`
- `0x180004ca0`
- `0x180017790`
- `0x180061660`
- `0x1800625bc`
- `0x180068350`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800683cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800685a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800683cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800685a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800685f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800685f3`

## pseudocode

```c
void __fastcall TelemetryLogger::UpdateModelCacheOnDriverUpdateCacheModels::Stop(
        TelemetryLogger::UpdateModelCacheOnDriverUpdateCacheModels *this,
        char a2,
        RTL_SRWLOCK *a3,
        int a4,
        const char *a5)
{
  __int64 v5; // rdi
  int v10; // eax
  int *v11; // rdi
  RTL_SRWLOCK *v12; // rcx
  __int64 v13; // r9
  __int64 v14; // r8
  RTL_SRWLOCK *v15; // rcx
  __int64 v16; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v18; // r8
  const wchar_t *v19; // rcx
  __int64 v20; // rax
  int v21; // eax
  _BYTE v22[4]; // [rsp+C0h] [rbp-80h] BYREF
  int v23; // [rsp+C4h] [rbp-7Ch] BYREF
  DWORD v24; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK SRWLock; // [rsp+D0h] [rbp-70h] BYREF
  PSRWLOCK v26; // [rsp+D8h] [rbp-68h] BYREF
  int v27; // [rsp+E0h] [rbp-60h] BYREF
  int v28; // [rsp+E4h] [rbp-5Ch] BYREF
  int v29; // [rsp+E8h] [rbp-58h] BYREF
  int v30; // [rsp+ECh] [rbp-54h] BYREF
  __int64 v31; // [rsp+F0h] [rbp-50h] BYREF
  const wchar_t *v32; // [rsp+F8h] [rbp-48h] BYREF
  RTL_SRWLOCK *v33; // [rsp+100h] [rbp-40h] BYREF
  const wchar_t *v34; // [rsp+108h] [rbp-38h] BYREF
  const wchar_t *v35; // [rsp+110h] [rbp-30h] BYREF
  const wchar_t *v36; // [rsp+118h] [rbp-28h] BYREF
  const wchar_t *v37; // [rsp+120h] [rbp-20h] BYREF
  const wchar_t *v38; // [rsp+128h] [rbp-18h] BYREF
  const wchar_t *v39; // [rsp+130h] [rbp-10h] BYREF
  const wchar_t *v40; // [rsp+138h] [rbp-8h] BYREF
  const wchar_t *v41; // [rsp+140h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v42; // [rsp+150h] [rbp+10h] BYREF
  __int64 *v43; // [rsp+170h] [rbp+30h]
  __int64 v44; // [rsp+178h] [rbp+38h]
  int *v45; // [rsp+180h] [rbp+40h]
  __int64 v46; // [rsp+188h] [rbp+48h]
  DWORD *v47; // [rsp+190h] [rbp+50h]
  __int64 v48; // [rsp+198h] [rbp+58h]
  _BYTE *v49; // [rsp+1A0h] [rbp+60h]
  __int64 v50; // [rsp+1A8h] [rbp+68h]
  PSRWLOCK *v51; // [rsp+1B0h] [rbp+70h]
  __int64 v52; // [rsp+1B8h] [rbp+78h]
  PSRWLOCK *p_SRWLock; // [rsp+1C0h] [rbp+80h]
  __int64 v54; // [rsp+1C8h] [rbp+88h]
  const wchar_t *v55; // [rsp+1D0h] [rbp+90h]
  int v56; // [rsp+1D8h] [rbp+98h]
  int v57; // [rsp+1DCh] [rbp+9Ch]

  v5 = *((_QWORD *)this + 34);
  v10 = *(_DWORD *)(v5 + 72);
  if ( v10 < 0 && (v11 = (int *)(v5 + 80), v10 == v11[2]) && v11 )
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v12 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v12 )
      ReleaseSRWLockExclusive(v12);
    v13 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v13 > 5u
      && (*(_QWORD *)(v13 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v13 + 24) & 0x400000000000LL) == *(_QWORD *)(v13 + 24) )
    {
      v32 = (const wchar_t *)a5;
      v34 = (const wchar_t *)*((_QWORD *)v11 + 15);
      v35 = (const wchar_t *)*((_QWORD *)v11 + 14);
      v28 = v11[26];
      v36 = (const wchar_t *)*((_QWORD *)v11 + 12);
      v14 = *((_QWORD *)this + 34);
      v37 = (const wchar_t *)*((_QWORD *)v11 + 11);
      v29 = v11[20];
      v38 = (const wchar_t *)*((_QWORD *)v11 + 9);
      v30 = v11[8];
      v39 = (const wchar_t *)*((_QWORD *)v11 + 3);
      v23 = *v11;
      v40 = (const wchar_t *)*((_QWORD *)v11 + 16);
      v24 = v11[16];
      v41 = (const wchar_t *)*((_QWORD *)v11 + 7);
      LODWORD(SRWLock) = v11[2];
      v31 = 0x1000000;
      v26 = (PSRWLOCK)0x1000000;
      v27 = a4;
      v33 = a3;
      v22[0] = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v13,
        (__int64)word_18009C4AA,
        v14 + 8,
        v13,
        (__int64)&v26,
        (__int64)&v31,
        (__int64)&SRWLock,
        &v41,
        (__int64)&v24,
        &v40,
        (__int64)&v23,
        &v39,
        (__int64)&v30,
        &v38,
        (__int64)&v29,
        &v37,
        &v36,
        (__int64)&v28,
        &v35,
        &v34,
        (__int64)v22,
        (__int64)&v33,
        (__int64)&v27,
        &v32);
    }
  }
  else
  {
    wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v26);
    v15 = v26;
    **((_DWORD **)this + 34) = 2;
    if ( v15 )
      ReleaseSRWLockExclusive(v15);
    v16 = *((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( *(_DWORD *)v16 > 5u
      && (*(_QWORD *)(v16 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v16 + 24) & 0x400000000000LL) == *(_QWORD *)(v16 + 24) )
    {
      LODWORD(SRWLock) = a4;
      v26 = a3;
      v22[0] = a2;
      CurrentThreadId = GetCurrentThreadId();
      v18 = *((_QWORD *)this + 34);
      v19 = (const wchar_t *)a5;
      v24 = CurrentThreadId;
      v23 = *(_DWORD *)(v18 + 72);
      v31 = 0x1000000;
      if ( a5 )
      {
        v20 = -1;
        do
          ++v20;
        while ( a5[v20] );
        v21 = v20 + 1;
      }
      else
      {
        v19 = &byte_18008E2FF;
        v21 = 1;
      }
      v56 = v21;
      v55 = v19;
      p_SRWLock = &SRWLock;
      v50 = 1;
      v51 = &v26;
      v57 = 0;
      v49 = v22;
      v54 = 4;
      v47 = &v24;
      v45 = &v23;
      v43 = &v31;
      v52 = 8;
      v48 = 4;
      v46 = 4;
      v44 = 8;
      tlgWriteTransfer_EventWriteTransfer(v16, (unsigned __int8 *)&word_18009C3FE, (const GUID *)(v18 + 8), 0, 9u, &v42);
    }
  }
  wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180068350  push    rbp
0x180068352  push    rbx
0x180068353  push    rsi
0x180068354  push    rdi
0x180068355  push    r14
0x180068357  push    r15
0x180068359  lea     rbp, [rsp-0B8h]
0x180068361  sub     rsp, 1F8h
0x180068368  mov     rax, cs:__security_cookie
0x18006836f  xor     rax, rsp
0x180068372  mov     [rbp+0E0h+var_40], rax
0x180068379  mov     rdi, [rcx+110h]
0x180068380  mov     esi, r9d
0x180068383  mov     r14, r8
0x180068386  mov     r15b, dl
0x180068389  mov     rbx, rcx
0x18006838c  mov     eax, [rdi+48h]
0x18006838f  test    eax, eax
0x180068391  jns     loc_180068585
0x180068397  add     rdi, 50h ; 'P'
0x18006839b  cmp     eax, [rdi+8]
0x18006839e  jnz     loc_180068585
0x1800683a4  test    rdi, rdi
0x1800683a7  jz      loc_180068585
0x1800683ad  lea     rdx, [rbp+0E0h+SRWLock]
0x1800683b1  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800683b6  mov     rax, [rbx+110h]
0x1800683bd  mov     rcx, [rbp+0E0h+SRWLock]; SRWLock
0x1800683c1  mov     dword ptr [rax], 2
0x1800683c7  test    rcx, rcx
0x1800683ca  jz      short loc_1800683D2
0x1800683cc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800683d2  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800683d7  mov     r9, [rax+8]
0x1800683db  mov     eax, [r9]
0x1800683de  cmp     eax, 5
0x1800683e1  jbe     loc_1800686DE
0x1800683e7  mov     rdx, [r9+18h]
0x1800683eb  mov     rcx, 400000000000h
0x1800683f5  mov     rax, [r9+10h]
0x1800683f9  test    rcx, rax
0x1800683fc  jz      loc_1800686DE
0x180068402  mov     rax, rdx
0x180068405  and     rax, rcx
0x180068408  cmp     rax, rdx
0x18006840b  jnz     loc_1800686DE
0x180068411  mov     rax, [rbp+0E0h+arg_20]
0x180068418  lea     rdx, word_18009C4AA
0x18006841f  mov     [rbp+0E0h+var_128], rax
0x180068423  mov     rcx, r9
0x180068426  mov     rax, [rdi+78h]
0x18006842a  mov     [rbp+0E0h+var_118], rax
0x18006842e  mov     rax, [rdi+70h]
0x180068432  mov     [rbp+0E0h+var_110], rax
0x180068436  mov     eax, [rdi+68h]
0x180068439  mov     [rbp+0E0h+var_13C], eax
0x18006843c  mov     rax, [rdi+60h]
0x180068440  mov     [rbp+0E0h+var_108], rax
0x180068444  mov     rax, [rdi+58h]
0x180068448  mov     r8, [rbx+110h]
0x18006844f  mov     [rbp+0E0h+var_100], rax
0x180068453  add     r8, 8
0x180068457  mov     eax, [rdi+50h]
0x18006845a  mov     [rbp+0E0h+var_138], eax
0x18006845d  mov     rax, [rdi+48h]
0x180068461  mov     [rbp+0E0h+var_F8], rax
0x180068465  mov     eax, [rdi+20h]
0x180068468  mov     [rbp+0E0h+var_134], eax
0x18006846b  mov     rax, [rdi+18h]
0x18006846f  mov     [rbp+0E0h+var_F0], rax
0x180068473  mov     eax, [rdi]
0x180068475  mov     [rbp+0E0h+var_15C], eax
0x180068478  mov     rax, [rdi+80h]
0x18006847f  mov     [rbp+0E0h+var_E8], rax
0x180068483  mov     eax, [rdi+40h]
0x180068486  mov     [rbp+0E0h+var_158], eax
0x180068489  mov     rax, [rdi+38h]
0x18006848d  mov     [rbp+0E0h+var_E0], rax
0x180068491  mov     eax, [rdi+8]
0x180068494  mov     dword ptr [rbp+0E0h+SRWLock], eax
0x180068497  mov     eax, 1000000h
0x18006849c  mov     [rbp+0E0h+var_130], rax
0x1800684a0  mov     [rbp+0E0h+var_148], rax
0x1800684a4  lea     rax, [rbp+0E0h+var_128]
0x1800684a8  mov     [rsp+220h+var_168], rax
0x1800684b0  lea     rax, [rbp+0E0h+var_140]
0x1800684b4  mov     [rsp+220h+var_170], rax
0x1800684bc  lea     rax, [rbp+0E0h+var_120]
0x1800684c0  mov     [rsp+220h+var_178], rax
0x1800684c8  lea     rax, [rbp+0E0h+var_160]
0x1800684cc  mov     [rsp+220h+var_180], rax
0x1800684d4  lea     rax, [rbp+0E0h+var_118]
0x1800684d8  mov     [rsp+220h+var_188], rax
0x1800684e0  lea     rax, [rbp+0E0h+var_110]
0x1800684e4  mov     [rsp+220h+var_190], rax
0x1800684ec  lea     rax, [rbp+0E0h+var_13C]
0x1800684f0  mov     [rsp+220h+var_198], rax
0x1800684f8  lea     rax, [rbp+0E0h+var_108]
0x1800684fc  mov     [rsp+220h+var_1A0], rax
0x180068504  lea     rax, [rbp+0E0h+var_100]
0x180068508  mov     [rsp+220h+var_1A8], rax
0x18006850d  lea     rax, [rbp+0E0h+var_138]
0x180068511  mov     [rsp+220h+var_1B0], rax
0x180068516  lea     rax, [rbp+0E0h+var_F8]
0x18006851a  mov     [rsp+220h+var_1B8], rax
0x18006851f  lea     rax, [rbp+0E0h+var_134]
0x180068523  mov     [rsp+220h+var_1C0], rax
0x180068528  lea     rax, [rbp+0E0h+var_F0]
0x18006852c  mov     [rsp+220h+var_1C8], rax
0x180068531  lea     rax, [rbp+0E0h+var_15C]
0x180068535  mov     [rsp+220h+var_1D0], rax
0x18006853a  lea     rax, [rbp+0E0h+var_E8]
0x18006853e  mov     [rsp+220h+var_1D8], rax
0x180068543  lea     rax, [rbp+0E0h+var_158]
0x180068547  mov     [rsp+220h+var_1E0], rax
0x18006854c  lea     rax, [rbp+0E0h+var_E0]
0x180068550  mov     [rsp+220h+var_1E8], rax
0x180068555  lea     rax, [rbp+0E0h+SRWLock]
0x180068559  mov     [rsp+220h+var_1F0], rax
0x18006855e  lea     rax, [rbp+0E0h+var_130]
0x180068562  mov     [rsp+220h+var_1F8], rax
0x180068567  lea     rax, [rbp+0E0h+var_148]
0x18006856b  mov     [rsp+220h+var_200], rax
0x180068570  mov     [rbp+0E0h+var_140], esi
0x180068573  mov     [rbp+0E0h+var_120], r14
0x180068577  mov     [rbp+0E0h+var_160], r15b
0x18006857b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U?$_tlgWrapperByVal@$00@@U1@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456AEBU?$_tlgWrapperByVal@$00@@345@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180068580  jmp     loc_1800686DE
0x180068585  lea     rdx, [rbp+0E0h+var_148]
0x180068589  call    ?LockExclusive@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18006858e  mov     rax, [rbx+110h]
0x180068595  mov     rcx, [rbp+0E0h+var_148]; SRWLock
0x180068599  mov     dword ptr [rax], 2
0x18006859f  test    rcx, rcx
0x1800685a2  jz      short loc_1800685AA
0x1800685a4  call    cs:__imp_ReleaseSRWLockExclusive
0x1800685aa  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800685af  mov     rdi, [rax+8]
0x1800685b3  mov     eax, [rdi]
0x1800685b5  cmp     eax, 5
0x1800685b8  jbe     loc_1800686DE
0x1800685be  mov     rdx, [rdi+18h]
0x1800685c2  mov     rcx, 400000000000h
0x1800685cc  mov     rax, [rdi+10h]
0x1800685d0  test    rcx, rax
0x1800685d3  jz      loc_1800686DE
0x1800685d9  mov     rax, rdx
0x1800685dc  and     rax, rcx
0x1800685df  cmp     rax, rdx
0x1800685e2  jnz     loc_1800686DE
0x1800685e8  mov     dword ptr [rbp+0E0h+SRWLock], esi
0x1800685eb  mov     [rbp+0E0h+var_148], r14
0x1800685ef  mov     [rbp+0E0h+var_160], r15b
0x1800685f3  call    cs:__imp_GetCurrentThreadId
0x1800685f9  mov     r8, [rbx+110h]
0x180068600  mov     edx, 1
0x180068605  mov     rcx, [rbp+0E0h+arg_20]
0x18006860c  mov     [rbp+0E0h+var_158], eax
0x18006860f  mov     eax, [r8+48h]
0x180068613  mov     [rbp+0E0h+var_15C], eax
0x180068616  mov     eax, 1000000h
0x18006861b  mov     [rbp+0E0h+var_130], rax
0x18006861f  test    rcx, rcx
0x180068622  jz      short loc_180068635
0x180068624  or      rax, 0FFFFFFFFFFFFFFFFh
0x180068628  inc     rax
0x18006862b  cmp     byte ptr [rcx+rax], 0
0x18006862f  jnz     short loc_180068628
0x180068631  inc     eax
0x180068633  jmp     short loc_18006863E
0x180068635  lea     rcx, byte_18008E2FF
0x18006863c  mov     eax, edx
0x18006863e  mov     [rbp+0E0h+var_48], eax
0x180068644  add     r8, 8
0x180068648  lea     rax, [rbp+0E0h+SRWLock]
0x18006864c  mov     [rbp+0E0h+var_50], rcx
0x180068653  mov     [rbp+0E0h+var_60], rax
0x18006865a  xor     r9d, r9d
0x18006865d  lea     rax, [rbp+0E0h+var_148]
0x180068661  mov     [rbp+0E0h+var_78], rdx
0x180068665  mov     [rbp+0E0h+var_70], rax
0x180068669  lea     rdx, word_18009C3FE
0x180068670  lea     rax, [rbp+0E0h+var_160]
0x180068674  mov     [rbp+0E0h+var_44], 0
0x18006867e  mov     [rbp+0E0h+var_80], rax
0x180068682  mov     rcx, rdi
0x180068685  lea     rax, [rbp+0E0h+var_158]
0x180068689  mov     [rbp+0E0h+var_58], 4
0x180068694  mov     [rbp+0E0h+var_90], rax
0x180068698  lea     rax, [rbp+0E0h+var_15C]
0x18006869c  mov     [rbp+0E0h+var_A0], rax
0x1800686a0  lea     rax, [rbp+0E0h+var_130]
0x1800686a4  mov     [rbp+0E0h+var_B0], rax
0x1800686a8  lea     rax, [rbp+0E0h+var_D0]
0x1800686ac  mov     [rsp+220h+var_1F8], rax
0x1800686b1  mov     dword ptr [rsp+220h+var_200], 9
0x1800686b9  mov     [rbp+0E0h+var_68], 8
0x1800686c1  mov     [rbp+0E0h+var_88], 4
0x1800686c9  mov     [rbp+0E0h+var_98], 4
0x1800686d1  mov     [rbp+0E0h+var_A8], 8
0x1800686d9  call    _tlgWriteTransfer_EventWriteTransfer
0x1800686de  mov     rcx, rbx
0x1800686e1  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetryLogger@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<TelemetryLogger,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x1800686e6  mov     rcx, [rbp+0E0h+var_40]
0x1800686ed  xor     rcx, rsp; StackCookie
0x1800686f0  call    __security_check_cookie
0x1800686f5  add     rsp, 1F8h
0x1800686fc  pop     r15
0x1800686fe  pop     r14
0x180068700  pop     rdi
0x180068701  pop     rsi
0x180068702  pop     rbx
0x180068703  pop     rbp
0x180068704  retn
```
