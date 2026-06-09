# Windows::Telemetry::Worker::RefreshSettings::Stop(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180043964`
- end: `0x180043d7e`
- name: `?Stop@RefreshSettings@Worker@Telemetry@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z`
- size: `1050`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180042130`

## callees

- `0x1800019cc`
- `0x180001d74`
- `0x180007660`
- `0x180041ba0`
- `0x180041c1c`
- `0x180041cd8`
- `0x180043964`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800439eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180043be2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800439eb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180043be2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043c48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180043c48`

## pseudocode

```c
void __fastcall Windows::Telemetry::Worker::RefreshSettings::Stop(
        __int64 a1,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4)
{
  __int64 v4; // r12
  int v9; // eax
  int *v10; // r12
  RTL_SRWLOCK *v11; // rcx
  __int64 v12; // r9
  bool v13; // cc
  __int64 v14; // r8
  int v15; // r14d
  RTL_SRWLOCK *v16; // rcx
  __int64 v17; // r12
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  __int64 v20; // rax
  __int64 v21; // rcx
  int v22; // ecx
  __int64 v23; // rcx
  int v24; // ecx
  __int64 v25; // [rsp+C0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+C8h] [rbp-78h] BYREF
  PSRWLOCK v27; // [rsp+D0h] [rbp-70h] BYREF
  int v28; // [rsp+D8h] [rbp-68h] BYREF
  int v29; // [rsp+DCh] [rbp-64h] BYREF
  int v30; // [rsp+E0h] [rbp-60h] BYREF
  int v31; // [rsp+E4h] [rbp-5Ch] BYREF
  __int64 v32; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v33; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v34; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v35; // [rsp+100h] [rbp-40h] BYREF
  __int64 v36; // [rsp+108h] [rbp-38h] BYREF
  __int64 v37; // [rsp+110h] [rbp-30h] BYREF
  __int64 v38; // [rsp+118h] [rbp-28h] BYREF
  __int64 v39; // [rsp+120h] [rbp-20h] BYREF
  __int64 v40; // [rsp+128h] [rbp-18h] BYREF
  __int64 v41; // [rsp+130h] [rbp-10h] BYREF
  __int64 v42; // [rsp+138h] [rbp-8h] BYREF
  __int64 v43; // [rsp+140h] [rbp+0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v44; // [rsp+150h] [rbp+10h] BYREF
  PSRWLOCK *v45; // [rsp+170h] [rbp+30h]
  __int64 v46; // [rsp+178h] [rbp+38h]
  __int64 *v47; // [rsp+180h] [rbp+40h]
  __int64 v48; // [rsp+188h] [rbp+48h]
  PSRWLOCK *p_SRWLock; // [rsp+190h] [rbp+50h]
  __int64 v50; // [rsp+198h] [rbp+58h]
  const wchar_t *v51; // [rsp+1A0h] [rbp+60h]
  int v52; // [rsp+1A8h] [rbp+68h]
  int v53; // [rsp+1ACh] [rbp+6Ch]
  const wchar_t *v54; // [rsp+1B0h] [rbp+70h]
  int v55; // [rsp+1B8h] [rbp+78h]
  int v56; // [rsp+1BCh] [rbp+7Ch]
  const wchar_t *v57; // [rsp+1C0h] [rbp+80h]
  int v58; // [rsp+1C8h] [rbp+88h]
  int v59; // [rsp+1CCh] [rbp+8Ch]

  v4 = *(_QWORD *)(a1 + 272);
  v9 = *(_DWORD *)(v4 + 72);
  if ( v9 < 0 && (v10 = (int *)(v4 + 80), v9 == v10[2]) && v10 )
  {
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &SRWLock);
    v11 = SRWLock;
    **(_DWORD **)(a1 + 272) = 2;
    if ( v11 )
      ReleaseSRWLockExclusive(v11);
    v12 = *((_QWORD *)Windows::Telemetry::Base::Instance() + 1);
    if ( *(_DWORD *)v12 > 5u
      && (*(_QWORD *)(v12 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v12 + 24) & 0x400000000000LL) == *(_QWORD *)(v12 + 24) )
    {
      if ( *((_QWORD *)a4 + 3) > 7u )
        a4 = *(const wchar_t **)a4;
      v13 = *((_QWORD *)a3 + 3) <= 7u;
      v32 = (__int64)a4;
      if ( !v13 )
        a3 = *(const wchar_t **)a3;
      v13 = *((_QWORD *)a2 + 3) <= 7u;
      v33 = (__int64)a3;
      if ( !v13 )
        a2 = *(const wchar_t **)a2;
      v35 = *((_QWORD *)v10 + 15);
      v36 = *((_QWORD *)v10 + 14);
      v28 = v10[26];
      v14 = *(_QWORD *)(a1 + 272);
      v37 = *((_QWORD *)v10 + 12);
      v38 = *((_QWORD *)v10 + 11);
      v29 = v10[20];
      v39 = *((_QWORD *)v10 + 9);
      v30 = v10[8];
      v40 = *((_QWORD *)v10 + 3);
      v31 = *v10;
      v41 = *((_QWORD *)v10 + 16);
      LODWORD(v25) = v10[16];
      v42 = *((_QWORD *)v10 + 7);
      LODWORD(SRWLock) = v10[2];
      v43 = 0x1000000;
      v27 = (PSRWLOCK)0x1000000;
      v34 = (__int64)a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v12,
        (int)&word_1800819DE,
        v14 + 8,
        (__int64)&v27,
        (__int64)&v43,
        (__int64)&SRWLock,
        (__int64)&v42,
        (__int64)&v25,
        (__int64)&v41,
        (__int64)&v31,
        (__int64)&v40,
        (__int64)&v30,
        (__int64)&v39,
        (__int64)&v29,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)&v28,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v32);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      a1,
      &v27);
    v15 = 2;
    v16 = v27;
    **(_DWORD **)(a1 + 272) = 2;
    if ( v16 )
      ReleaseSRWLockExclusive(v16);
    v17 = *((_QWORD *)Windows::Telemetry::Base::Instance() + 1);
    if ( *(_DWORD *)v17 > 5u
      && (*(_QWORD *)(v17 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v17 + 24) & 0x400000000000LL) == *(_QWORD *)(v17 + 24) )
    {
      if ( *((_QWORD *)a4 + 3) > 7u )
        a4 = *(const wchar_t **)a4;
      if ( *((_QWORD *)a3 + 3) > 7u )
        a3 = *(const wchar_t **)a3;
      if ( *((_QWORD *)a2 + 3) > 7u )
        a2 = *(const wchar_t **)a2;
      CurrentThreadId = GetCurrentThreadId();
      v19 = *(_QWORD *)(a1 + 272);
      LODWORD(SRWLock) = CurrentThreadId;
      LODWORD(v25) = *(_DWORD *)(v19 + 72);
      v27 = (PSRWLOCK)0x1000000;
      v20 = -1;
      if ( a4 )
      {
        v21 = -1;
        do
          ++v21;
        while ( a4[v21] );
        v22 = 2 * v21 + 2;
      }
      else
      {
        a4 = &psz;
        v22 = 2;
      }
      v57 = a4;
      v58 = v22;
      v59 = 0;
      if ( a3 )
      {
        v23 = -1;
        do
          ++v23;
        while ( a3[v23] );
        v24 = 2 * v23 + 2;
      }
      else
      {
        a3 = &psz;
        v24 = 2;
      }
      v54 = a3;
      v55 = v24;
      v56 = 0;
      if ( a2 )
      {
        do
          ++v20;
        while ( a2[v20] );
        v15 = 2 * v20 + 2;
      }
      else
      {
        a2 = &psz;
      }
      v51 = a2;
      p_SRWLock = &SRWLock;
      v52 = v15;
      v47 = &v25;
      v53 = 0;
      v45 = &v27;
      v50 = 4;
      v48 = 4;
      v46 = 8;
      tlgWriteTransfer_EventWriteTransfer(
        v17,
        (unsigned __int8 *)&dword_18008196C,
        (const GUID *)(v19 + 8),
        0,
        8u,
        &v44);
    }
  }
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x180043964  push    rbp
0x180043966  push    rbx
0x180043967  push    rsi
0x180043968  push    rdi
0x180043969  push    r12
0x18004396b  push    r13
0x18004396d  push    r14
0x18004396f  push    r15
0x180043971  lea     rbp, [rsp-0A8h]
0x180043979  sub     rsp, 1E8h
0x180043980  mov     rax, cs:__security_cookie
0x180043987  xor     rax, rsp
0x18004398a  mov     [rbp+0E0h+var_50], rax
0x180043991  mov     r12, [rcx+110h]
0x180043998  xor     r13d, r13d
0x18004399b  mov     rbx, r9
0x18004399e  mov     rdi, r8
0x1800439a1  mov     rsi, rdx
0x1800439a4  mov     r15, rcx
0x1800439a7  mov     eax, [r12+48h]
0x1800439ac  test    eax, eax
0x1800439ae  jns     loc_180043BC0
0x1800439b4  add     r12, 50h ; 'P'
0x1800439b8  cmp     eax, [r12+8]
0x1800439bd  jnz     loc_180043BC0
0x1800439c3  test    r12, r12
0x1800439c6  jz      loc_180043BC0
0x1800439cc  lea     rdx, [rbp+0E0h+SRWLock]
0x1800439d0  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800439d5  mov     rax, [r15+110h]
0x1800439dc  mov     rcx, [rbp+0E0h+SRWLock]; SRWLock
0x1800439e0  mov     dword ptr [rax], 2
0x1800439e6  test    rcx, rcx
0x1800439e9  jz      short loc_1800439F1
0x1800439eb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800439f1  call    ?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::Base::Instance(void)
0x1800439f6  mov     r9, [rax+8]
0x1800439fa  mov     eax, [r9]
0x1800439fd  cmp     eax, 5
0x180043a00  jbe     loc_180043D53
0x180043a06  mov     rdx, [r9+18h]
0x180043a0a  mov     rcx, 400000000000h
0x180043a14  mov     rax, [r9+10h]
0x180043a18  test    rcx, rax
0x180043a1b  jz      loc_180043D53
0x180043a21  mov     rax, rdx
0x180043a24  and     rax, rcx
0x180043a27  cmp     rax, rdx
0x180043a2a  jnz     loc_180043D53
0x180043a30  cmp     qword ptr [rbx+18h], 7
0x180043a35  jbe     short loc_180043A3A
0x180043a37  mov     rbx, [rbx]
0x180043a3a  cmp     qword ptr [rdi+18h], 7
0x180043a3f  mov     [rbp+0E0h+var_138], rbx
0x180043a43  jbe     short loc_180043A48
0x180043a45  mov     rdi, [rdi]
0x180043a48  cmp     qword ptr [rsi+18h], 7
0x180043a4d  mov     [rbp+0E0h+var_130], rdi
0x180043a51  jbe     short loc_180043A56
0x180043a53  mov     rsi, [rsi]
0x180043a56  mov     rax, [r12+78h]
0x180043a5b  lea     rdx, word_1800819DE; int
0x180043a62  mov     [rbp+0E0h+var_120], rax
0x180043a66  mov     rcx, r9; int
0x180043a69  mov     rax, [r12+70h]
0x180043a6e  mov     [rbp+0E0h+var_118], rax
0x180043a72  mov     eax, [r12+68h]
0x180043a77  mov     dword ptr [rbp+0E0h+var_148], eax
0x180043a7a  mov     rax, [r12+60h]
0x180043a7f  mov     r8, [r15+110h]
0x180043a86  mov     [rbp+0E0h+var_110], rax
0x180043a8a  add     r8, 8; int
0x180043a8e  mov     rax, [r12+58h]
0x180043a93  mov     [rbp+0E0h+var_108], rax
0x180043a97  mov     eax, [r12+50h]
0x180043a9c  mov     dword ptr [rbp+0E0h+var_148+4], eax
0x180043a9f  mov     rax, [r12+48h]
0x180043aa4  mov     [rbp+0E0h+var_100], rax
0x180043aa8  mov     eax, [r12+20h]
0x180043aad  mov     dword ptr [rbp+0E0h+var_140], eax
0x180043ab0  mov     rax, [r12+18h]
0x180043ab5  mov     [rbp+0E0h+var_F8], rax
0x180043ab9  mov     eax, [r12]
0x180043abd  mov     dword ptr [rbp+0E0h+var_140+4], eax
0x180043ac0  mov     rax, [r12+80h]
0x180043ac8  mov     [rbp+0E0h+var_F0], rax
0x180043acc  mov     eax, [r12+40h]
0x180043ad1  mov     dword ptr [rbp+0E0h+var_160], eax
0x180043ad4  mov     rax, [r12+38h]
0x180043ad9  mov     [rbp+0E0h+var_E8], rax
0x180043add  mov     eax, [r12+8]
0x180043ae2  mov     dword ptr [rbp+0E0h+SRWLock], eax
0x180043ae5  mov     eax, 1000000h
0x180043aea  mov     [rbp+0E0h+var_E0], rax
0x180043aee  mov     [rbp+0E0h+var_150], rax
0x180043af2  lea     rax, [rbp+0E0h+var_138]
0x180043af6  mov     [rsp+220h+var_170], rax; __int64
0x180043afe  lea     rax, [rbp+0E0h+var_130]
0x180043b02  mov     [rsp+220h+var_178], rax; __int64
0x180043b0a  lea     rax, [rbp+0E0h+var_128]
0x180043b0e  mov     [rsp+220h+var_180], rax; __int64
0x180043b16  lea     rax, [rbp+0E0h+var_120]
0x180043b1a  mov     [rsp+220h+var_188], rax; __int64
0x180043b22  lea     rax, [rbp+0E0h+var_118]
0x180043b26  mov     [rsp+220h+var_190], rax; __int64
0x180043b2e  lea     rax, [rbp+0E0h+var_148]
0x180043b32  mov     [rsp+220h+var_198], rax; __int64
0x180043b3a  lea     rax, [rbp+0E0h+var_110]
0x180043b3e  mov     [rsp+220h+var_1A0], rax; __int64
0x180043b46  lea     rax, [rbp+0E0h+var_108]
0x180043b4a  mov     [rsp+220h+var_1A8], rax; __int64
0x180043b4f  lea     rax, [rbp+0E0h+var_148+4]
0x180043b53  mov     [rsp+220h+var_1B0], rax; __int64
0x180043b58  lea     rax, [rbp+0E0h+var_100]
0x180043b5c  mov     [rsp+220h+var_1B8], rax; __int64
0x180043b61  lea     rax, [rbp+0E0h+var_140]
0x180043b65  mov     [rsp+220h+var_1C0], rax; __int64
0x180043b6a  lea     rax, [rbp+0E0h+var_F8]
0x180043b6e  mov     [rsp+220h+var_1C8], rax; __int64
0x180043b73  lea     rax, [rbp+0E0h+var_140+4]
0x180043b77  mov     [rsp+220h+var_1D0], rax; __int64
0x180043b7c  lea     rax, [rbp+0E0h+var_F0]
0x180043b80  mov     [rsp+220h+var_1D8], rax; __int64
0x180043b85  lea     rax, [rbp+0E0h+var_160]
0x180043b89  mov     [rsp+220h+var_1E0], rax; __int64
0x180043b8e  lea     rax, [rbp+0E0h+var_E8]
0x180043b92  mov     [rsp+220h+var_1E8], rax; __int64
0x180043b97  lea     rax, [rbp+0E0h+SRWLock]
0x180043b9b  mov     [rsp+220h+var_1F0], rax; __int64
0x180043ba0  lea     rax, [rbp+0E0h+var_E0]
0x180043ba4  mov     [rsp+220h+var_1F8], rax; __int64
0x180043ba9  lea     rax, [rbp+0E0h+var_150]
0x180043bad  mov     qword ptr [rsp+220h+var_200], rax; __int64
0x180043bb2  mov     [rbp+0E0h+var_128], rsi
0x180043bb6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180043bbb  jmp     loc_180043D53
0x180043bc0  lea     rdx, [rbp+0E0h+var_150]
0x180043bc4  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180043bc9  mov     rax, [r15+110h]
0x180043bd0  mov     r14d, 2
0x180043bd6  mov     rcx, [rbp+0E0h+var_150]; SRWLock
0x180043bda  mov     [rax], r14d
0x180043bdd  test    rcx, rcx
0x180043be0  jz      short loc_180043BE8
0x180043be2  call    cs:__imp_ReleaseSRWLockExclusive
0x180043be8  call    ?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::Base::Instance(void)
0x180043bed  mov     r12, [rax+8]
0x180043bf1  mov     eax, [r12]
0x180043bf5  cmp     eax, 5
0x180043bf8  jbe     loc_180043D53
0x180043bfe  mov     rdx, [r12+18h]
0x180043c03  mov     rcx, 400000000000h
0x180043c0d  mov     rax, [r12+10h]
0x180043c12  test    rcx, rax
0x180043c15  jz      loc_180043D53
0x180043c1b  mov     rax, rdx
0x180043c1e  and     rax, rcx
0x180043c21  cmp     rax, rdx
0x180043c24  jnz     loc_180043D53
0x180043c2a  cmp     qword ptr [rbx+18h], 7
0x180043c2f  jbe     short loc_180043C34
0x180043c31  mov     rbx, [rbx]
0x180043c34  cmp     qword ptr [rdi+18h], 7
0x180043c39  jbe     short loc_180043C3E
0x180043c3b  mov     rdi, [rdi]
0x180043c3e  cmp     qword ptr [rsi+18h], 7
0x180043c43  jbe     short loc_180043C48
0x180043c45  mov     rsi, [rsi]
0x180043c48  call    cs:__imp_GetCurrentThreadId
0x180043c4e  mov     r8, [r15+110h]
0x180043c55  lea     rdx, psz
0x180043c5c  mov     dword ptr [rbp+0E0h+SRWLock], eax
0x180043c5f  mov     eax, [r8+48h]
0x180043c63  mov     dword ptr [rbp+0E0h+var_160], eax
0x180043c66  mov     eax, 1000000h
0x180043c6b  mov     [rbp+0E0h+var_150], rax
0x180043c6f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043c73  test    rbx, rbx
0x180043c76  jz      short loc_180043C8E
0x180043c78  mov     rcx, rax
0x180043c7b  inc     rcx
0x180043c7e  cmp     [rbx+rcx*2], r13w
0x180043c83  jnz     short loc_180043C7B
0x180043c85  lea     ecx, ds:2[rcx*2]
0x180043c8c  jmp     short loc_180043C94
0x180043c8e  mov     rbx, rdx
0x180043c91  mov     ecx, r14d
0x180043c94  mov     [rbp+0E0h+var_60], rbx
0x180043c9b  mov     [rbp+0E0h+var_58], ecx
0x180043ca1  mov     [rbp+0E0h+var_54], r13d
0x180043ca8  test    rdi, rdi
0x180043cab  jz      short loc_180043CC3
0x180043cad  mov     rcx, rax
0x180043cb0  inc     rcx
0x180043cb3  cmp     [rdi+rcx*2], r13w
0x180043cb8  jnz     short loc_180043CB0
0x180043cba  lea     ecx, ds:2[rcx*2]
0x180043cc1  jmp     short loc_180043CC9
0x180043cc3  mov     rdi, rdx
0x180043cc6  mov     ecx, r14d
0x180043cc9  mov     [rbp+0E0h+var_70], rdi
0x180043ccd  mov     [rbp+0E0h+var_68], ecx
0x180043cd0  mov     [rbp+0E0h+var_64], r13d
0x180043cd4  test    rsi, rsi
0x180043cd7  jz      short loc_180043CED
0x180043cd9  inc     rax
0x180043cdc  cmp     [rsi+rax*2], r13w
0x180043ce1  jnz     short loc_180043CD9
0x180043ce3  lea     r14d, ds:2[rax*2]
0x180043ceb  jmp     short loc_180043CF0
0x180043ced  mov     rsi, rdx
0x180043cf0  lea     rax, [rbp+0E0h+SRWLock]
0x180043cf4  mov     [rbp+0E0h+var_80], rsi
0x180043cf8  mov     [rbp+0E0h+var_90], rax
0x180043cfc  lea     rdx, dword_18008196C; int
0x180043d03  lea     rax, [rbp+0E0h+var_160]
0x180043d07  mov     [rbp+0E0h+var_78], r14d
0x180043d0b  mov     [rbp+0E0h+var_A0], rax
0x180043d0f  add     r8, 8; int
0x180043d13  lea     rax, [rbp+0E0h+var_150]
0x180043d17  mov     [rbp+0E0h+var_74], r13d
0x180043d1b  mov     [rbp+0E0h+var_B0], rax
0x180043d1f  xor     r9d, r9d; int
0x180043d22  lea     rax, [rbp+0E0h+var_D0]
0x180043d26  mov     [rbp+0E0h+var_88], 4
0x180043d2e  mov     [rsp+220h+var_1F8], rax; PEVENT_DATA_DESCRIPTOR
0x180043d33  mov     rcx, r12; int
0x180043d36  mov     [rsp+220h+var_200], 8; ULONG
0x180043d3e  mov     [rbp+0E0h+var_98], 4
0x180043d46  mov     [rbp+0E0h+var_A8], 8
0x180043d4e  call    _tlgWriteTransfer_EventWriteTransfer
0x180043d53  mov     rcx, r15
0x180043d56  call    ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180043d5b  mov     rcx, [rbp+0E0h+var_50]
0x180043d62  xor     rcx, rsp; StackCookie
0x180043d65  call    __security_check_cookie
0x180043d6a  add     rsp, 1E8h
0x180043d71  pop     r15
0x180043d73  pop     r14
0x180043d75  pop     r13
0x180043d77  pop     r12
0x180043d79  pop     rdi
0x180043d7a  pop     rsi
0x180043d7b  pop     rbx
0x180043d7c  pop     rbp
0x180043d7d  retn
```
