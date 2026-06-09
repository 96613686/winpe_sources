# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::Create(Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp2 * *)

- ea: `0x1800564f0`
- end: `0x18005697d`
- name: `?Create@IsolationEnvironmentStatics2@Preview@IsolationEnvironment@AI@Windows@@UEAAJPEAPEAUIIsolationEnvironmentCreationResult_Exp2@2345@@Z`
- size: `1165`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2 *__hidden this, struct Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp2 **)`
- caller_count: `0`
- callee_count: `17`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002520`
- `0x180002a30`
- `0x18000a464`
- `0x18001045c`
- `0x180011e18`
- `0x1800134e8`
- `0x18004fb50`
- `0x180053110`
- `0x18005579c`
- `0x180055c74`
- `0x1800564f0`
- `0x180056984`
- `0x1800574b8`
- `0x180058110`
- `0x18005ed84`
- `0x180063594`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056558`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005658e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800567b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056888`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056955`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056558`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005658e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800567b6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056888`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056955`

## string_xrefs

- `0x18005651f`: `Create for IsolationEnvironment called.`
- `0x1800568a3`: `IsolationEnvironment created.`
- `0x180056749`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironmentstatics.cpp`
- `0x180056804`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironmentstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::Create(
        Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2 *this,
        wchar_t *a2)
{
  wchar_t *v2; // rdi
  __int64 v3; // rcx
  RTL_SRWLOCK *v4; // rcx
  Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2 *v6; // rcx
  RTL_SRWLOCK *v7; // rcx
  wchar_t *v8; // rax
  const wchar_t *v9; // rdi
  const wchar_t *v10; // rsi
  const wchar_t *v11; // r14
  const wchar_t *v12; // r15
  const wchar_t *v13; // r12
  const wchar_t *v14; // r13
  Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2 *v15; // rax
  int v16; // edi
  Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2 *v17; // rbx
  RTL_SRWLOCK *v18; // rcx
  int v19; // eax
  __int64 v20; // rdx
  unsigned int v21; // ebx
  RTL_SRWLOCK *v22; // rcx
  SecurityLog *v23; // rcx
  __int16 v24; // r8
  wchar_t *v25; // rax
  __int64 v26; // rax
  RTL_SRWLOCK *v27; // rcx
  int v28; // [rsp+20h] [rbp-E0h]
  wchar_t *v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v31; // [rsp+50h] [rbp-B0h] BYREF
  PSRWLOCK SRWLock; // [rsp+58h] [rbp-A8h] BYREF
  int NewAgentUserForCaller; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *v34[2]; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v35[2]; // [rsp+78h] [rbp-88h] BYREF
  __m128i v36; // [rsp+88h] [rbp-78h]
  wchar_t *v37[2]; // [rsp+98h] [rbp-68h] BYREF
  __m128i v38; // [rsp+A8h] [rbp-58h]
  wchar_t *v39[2]; // [rsp+B8h] [rbp-48h] BYREF
  __m128i v40; // [rsp+C8h] [rbp-38h]
  wchar_t *v41[2]; // [rsp+D8h] [rbp-28h] BYREF
  __m128i v42; // [rsp+E8h] [rbp-18h]
  wchar_t *v43[2]; // [rsp+F8h] [rbp-8h] BYREF
  __m128i v44; // [rsp+108h] [rbp+8h]
  wchar_t *v45[2]; // [rsp+118h] [rbp+18h] BYREF
  __m128i si128; // [rsp+128h] [rbp+28h]
  char *v47[4]; // [rsp+138h] [rbp+38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v2 = a2;
  v34[0] = a2;
  Log(4u, L"Create for IsolationEnvironment called.");
  checked_srwlock::lock_exclusive(v3, &SRWLock);
  *(_QWORD *)v2 = 0;
  if ( (unsigned int)GetIsSupportedResult2(0) != 1 )
  {
    v4 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v4);
    }
    return 2147942450LL;
  }
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl)
    && !Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::EnabledChildSessions(v6) )
  {
    v7 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v7);
    }
    return 2147549183LL;
  }
  *(_OWORD *)v45 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v45[0]) = 0;
  *(_OWORD *)v43 = 0;
  v44 = si128;
  LOWORD(v43[0]) = 0;
  *(_OWORD *)v41 = 0;
  v42 = si128;
  LOWORD(v41[0]) = 0;
  *(_OWORD *)v35 = 0;
  v36 = si128;
  LOWORD(v35[0]) = 0;
  *(_OWORD *)v39 = 0;
  v40 = si128;
  LOWORD(v39[0]) = 0;
  *(_OWORD *)v37 = 0;
  v38 = si128;
  LOWORD(v37[0]) = 0;
  v30 = 0;
  NewAgentUserForCaller = Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CreateNewAgentUserForCaller(
                            (__int64)v6,
                            v45,
                            (__int64)v43,
                            (__int64)v41,
                            (__int64)v35,
                            (__int64)v39,
                            (__int64)v37);
  if ( NewAgentUserForCaller < 0 )
  {
    v30 = 1;
    v8 = 0;
    v29 = 0;
    goto LABEL_37;
  }
  v29 = 0;
  v9 = (const wchar_t *)v37;
  if ( v38.m128i_i64[1] > 7uLL )
    v9 = v37[0];
  v10 = (const wchar_t *)v39;
  if ( v40.m128i_i64[1] > 7uLL )
    v10 = v39[0];
  v11 = (const wchar_t *)v35;
  if ( v36.m128i_i64[1] > 7uLL )
    v11 = v35[0];
  v12 = (const wchar_t *)v41;
  if ( v42.m128i_i64[1] > 7uLL )
    v12 = v41[0];
  v13 = (const wchar_t *)v43;
  if ( v44.m128i_i64[1] > 7uLL )
    v13 = v43[0];
  v14 = (const wchar_t *)v45;
  if ( si128.m128i_i64[1] > 7uLL )
    v14 = v45[0];
  v15 = (Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2 *)operator new(
                                                                               0xE8u,
                                                                               (const struct std::nothrow_t *)&std::nothrow);
  if ( v15 )
  {
    v17 = (Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2 *)Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::IsolationEnvironment2(v15);
    v16 = Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::RuntimeClassInitialize(
            v17,
            v14,
            v13,
            v12,
            v11,
            v10,
            v9);
    if ( v16 >= 0 )
    {
      v16 = (**(__int64 (__fastcall ***)(Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2 *, GUID *, wchar_t **))v17)(
              v17,
              &GUID_ab8dcf8e_08ad_562a_9967_fced64b54cb2,
              &v29);
      (*(void (__fastcall **)(Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2 *))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v16 >= 0 )
      {
        v8 = v29;
        v2 = v34[0];
LABEL_37:
        v34[0] = v8;
        v31 = 0;
        v19 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::Preview::EnvironmentCreationResult2,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp2,enum Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentCreationStatus_Exp2 &,long &,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp2 *>(
                &v31,
                &v30,
                &NewAgentUserForCaller,
                v34);
        v21 = v19;
        if ( v19 >= 0 )
        {
          std::operator+<wchar_t>(v47, v20, v35);
          v34[0] = L"IsolationEnvironment created.";
          v25 = (wchar_t *)v47;
          if ( v47[3] > (char *)7 )
            v25 = (wchar_t *)v47[0];
          v34[1] = v25;
          SecurityLog::WriteLog(v23, (const wchar_t **const)v34, v24);
          v26 = v31;
          v31 = 0;
          *(_QWORD *)v2 = v26;
          std::wstring::~wstring(v47);
          if ( v31 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
          if ( v29 )
            (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v29 + 16LL))(v29);
          std::wstring::~wstring((char **)v37);
          std::wstring::~wstring((char **)v39);
          std::wstring::~wstring((char **)v35);
          std::wstring::~wstring((char **)v41);
          std::wstring::~wstring((char **)v43);
          std::wstring::~wstring((char **)v45);
          v27 = SRWLock;
          if ( SRWLock )
          {
            LODWORD(SRWLock[1].Ptr) = 0;
            ReleaseSRWLockExclusive(v27);
          }
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5E,
            (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironmentstatics.cpp",
            (const char *)(unsigned int)v19,
            v28);
          if ( v31 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
          if ( v29 )
            (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v29 + 16LL))(v29);
          std::wstring::~wstring((char **)v37);
          std::wstring::~wstring((char **)v39);
          std::wstring::~wstring((char **)v35);
          std::wstring::~wstring((char **)v41);
          std::wstring::~wstring((char **)v43);
          std::wstring::~wstring((char **)v45);
          v22 = SRWLock;
          if ( SRWLock )
          {
            LODWORD(SRWLock[1].Ptr) = 0;
            ReleaseSRWLockExclusive(v22);
          }
          return v21;
        }
      }
    }
    else if ( v17 )
    {
      (*(void (__fastcall **)(Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2 *))(*(_QWORD *)v17 + 16LL))(v17);
    }
  }
  else
  {
    v16 = -2147024882;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironmentstatics.cpp",
    (const char *)(unsigned int)v16,
    v28);
  if ( v29 )
    (*(void (__fastcall **)(wchar_t *))(*(_QWORD *)v29 + 16LL))(v29);
  std::wstring::~wstring((char **)v37);
  std::wstring::~wstring((char **)v39);
  std::wstring::~wstring((char **)v35);
  std::wstring::~wstring((char **)v41);
  std::wstring::~wstring((char **)v43);
  std::wstring::~wstring((char **)v45);
  v18 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v18);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1800564f0  push    rbp
0x1800564f2  push    rbx
0x1800564f3  push    rsi
0x1800564f4  push    rdi
0x1800564f5  push    r12
0x1800564f7  push    r13
0x1800564f9  push    r14
0x1800564fb  push    r15
0x1800564fd  lea     rbp, [rsp-68h]
0x180056502  sub     rsp, 168h
0x180056509  mov     rax, cs:__security_cookie
0x180056510  xor     rax, rsp
0x180056513  mov     [rbp+0A0h+var_48], rax
0x180056517  mov     rdi, rdx
0x18005651a  mov     [rsp+1A0h+var_138], rdx
0x18005651f  lea     rdx, aCreateForIsola; "Create for IsolationEnvironment called."
0x180056526  mov     ecx, 4; unsigned __int8
0x18005652b  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180056530  lea     rdx, [rsp+1A0h+SRWLock]
0x180056535  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x18005653a  xor     esi, esi
0x18005653c  mov     [rdi], rsi
0x18005653f  xor     ecx, ecx
0x180056541  call    ?GetIsSupportedResult2@@YA?AW4IsIsolationSupportedResult_Exp2@Preview@IsolationEnvironment@AI@Windows@@_N@Z; GetIsSupportedResult2(bool)
0x180056546  cmp     eax, 1
0x180056549  jz      short loc_180056568
0x18005654b  mov     rcx, [rsp+1A0h+SRWLock]; SRWLock
0x180056550  test    rcx, rcx
0x180056553  jz      short loc_18005655E
0x180056555  mov     [rcx+8], esi
0x180056558  call    cs:__imp_ReleaseSRWLockExclusive
0x18005655e  mov     eax, 80070032h
0x180056563  jmp     loc_18005695D
0x180056568  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement> `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl(void)'::`2'::impl
0x18005656f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::__private_IsEnabled(void)
0x180056574  test    al, al
0x180056576  jnz     short loc_18005659E
0x180056578  call    ?EnabledChildSessions@IsolationEnvironmentStatics2@Preview@IsolationEnvironment@AI@Windows@@AEAA_NXZ; Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::EnabledChildSessions(void)
0x18005657d  test    al, al
0x18005657f  jnz     short loc_18005659E
0x180056581  mov     rcx, [rsp+1A0h+SRWLock]; SRWLock
0x180056586  test    rcx, rcx
0x180056589  jz      short loc_180056594
0x18005658b  mov     [rcx+8], esi
0x18005658e  call    cs:__imp_ReleaseSRWLockExclusive
0x180056594  mov     eax, 8000FFFFh
0x180056599  jmp     loc_18005695D
0x18005659e  xorps   xmm0, xmm0
0x1800565a1  movups  xmmword ptr [rbp+0A0h+var_88], xmm0
0x1800565a5  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800565ad  movdqu  [rbp+0A0h+var_78], xmm1
0x1800565b2  mov     word ptr [rbp+0A0h+var_88], si
0x1800565b6  movups  xmmword ptr [rbp+0A0h+var_A8], xmm0
0x1800565ba  movdqu  [rbp+0A0h+var_98], xmm1
0x1800565bf  mov     word ptr [rbp+0A0h+var_A8], si
0x1800565c3  movups  xmmword ptr [rbp+0A0h+var_C8], xmm0
0x1800565c7  movdqu  [rbp+0A0h+var_B8], xmm1
0x1800565cc  mov     word ptr [rbp+0A0h+var_C8], si
0x1800565d0  movups  xmmword ptr [rsp+1A0h+var_128], xmm0
0x1800565d5  movdqu  [rbp+0A0h+var_118], xmm1
0x1800565da  mov     word ptr [rsp+1A0h+var_128], si
0x1800565df  movups  xmmword ptr [rbp+0A0h+var_E8], xmm0
0x1800565e3  movdqu  [rbp+0A0h+var_D8], xmm1
0x1800565e8  mov     word ptr [rbp+0A0h+var_E8], si
0x1800565ec  movups  xmmword ptr [rbp+0A0h+var_108], xmm0
0x1800565f0  movdqu  [rbp+0A0h+var_F8], xmm1
0x1800565f5  mov     word ptr [rbp+0A0h+var_108], si
0x1800565f9  mov     [rsp+1A0h+var_158], esi
0x1800565fd  lea     rax, [rbp+0A0h+var_108]
0x180056601  mov     [rsp+1A0h+var_170], rax
0x180056606  lea     rax, [rbp+0A0h+var_E8]
0x18005660a  mov     [rsp+1A0h+var_178], rax
0x18005660f  lea     rax, [rsp+1A0h+var_128]
0x180056614  mov     [rsp+1A0h+var_180], rax
0x180056619  lea     r9, [rbp+0A0h+var_C8]
0x18005661d  lea     r8, [rbp+0A0h+var_A8]
0x180056621  lea     rdx, [rbp+0A0h+var_88]
0x180056625  call    ?CreateNewAgentUserForCaller@IsolationEnvironmentStatics2@Preview@IsolationEnvironment@AI@Windows@@AEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00000@Z; Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CreateNewAgentUserForCaller(std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &)
0x18005662a  mov     [rsp+1A0h+var_140], eax
0x18005662e  test    eax, eax
0x180056630  jns     short loc_180056647
0x180056632  mov     [rsp+1A0h+var_158], 1
0x18005663a  mov     rax, rsi
0x18005663d  mov     [rsp+1A0h+var_160], rax
0x180056642  jmp     loc_1800567CD
0x180056647  mov     [rsp+1A0h+var_160], rsi
0x18005664c  lea     rdi, [rbp+0A0h+var_108]
0x180056650  cmp     qword ptr [rbp+0A0h+var_F8+8], 7
0x180056655  cmova   rdi, [rbp+0A0h+var_108]
0x18005665a  lea     rsi, [rbp+0A0h+var_E8]
0x18005665e  cmp     qword ptr [rbp+0A0h+var_D8+8], 7
0x180056663  cmova   rsi, [rbp+0A0h+var_E8]
0x180056668  lea     r14, [rsp+1A0h+var_128]
0x18005666d  cmp     qword ptr [rbp+0A0h+var_118+8], 7
0x180056672  cmova   r14, [rsp+1A0h+var_128]
0x180056678  lea     r15, [rbp+0A0h+var_C8]
0x18005667c  cmp     qword ptr [rbp+0A0h+var_B8+8], 7
0x180056681  cmova   r15, [rbp+0A0h+var_C8]
0x180056686  lea     r12, [rbp+0A0h+var_A8]
0x18005668a  cmp     qword ptr [rbp+0A0h+var_98+8], 7
0x18005668f  cmova   r12, [rbp+0A0h+var_A8]
0x180056694  lea     r13, [rbp+0A0h+var_88]
0x180056698  cmp     qword ptr [rbp+0A0h+var_78+8], 7
0x18005669d  cmova   r13, [rbp+0A0h+var_88]
0x1800566a2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800566a9  mov     ecx, 0E8h; unsigned __int64
0x1800566ae  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800566b3  test    rax, rax
0x1800566b6  jnz     short loc_1800566C1
0x1800566b8  mov     edi, 8007000Eh
0x1800566bd  xor     esi, esi
0x1800566bf  jmp     short loc_18005673F
0x1800566c1  mov     rcx, rax; this
0x1800566c4  call    ??0IsolationEnvironment2@Preview@IsolationEnvironment@AI@Windows@@QEAA@XZ; Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::IsolationEnvironment2(void)
0x1800566c9  mov     rbx, rax
0x1800566cc  mov     [rsp+1A0h+var_170], rdi; wchar_t *
0x1800566d1  mov     [rsp+1A0h+var_178], rsi; wchar_t *
0x1800566d6  mov     [rsp+1A0h+var_180], r14; int
0x1800566db  mov     r9, r15; wchar_t *
0x1800566de  mov     r8, r12; wchar_t *
0x1800566e1  mov     rdx, r13; wchar_t *
0x1800566e4  mov     rcx, rax; this
0x1800566e7  call    ?RuntimeClassInitialize@IsolationEnvironment2@Preview@IsolationEnvironment@AI@Windows@@QEAAJPEB_W00000@Z; Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::RuntimeClassInitialize(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)
0x1800566ec  mov     edi, eax
0x1800566ee  xor     esi, esi
0x1800566f0  test    eax, eax
0x1800566f2  jns     short loc_18005670B
0x1800566f4  test    rbx, rbx
0x1800566f7  jz      short loc_180056709
0x1800566f9  mov     rax, [rbx]
0x1800566fc  mov     rcx, rbx
0x1800566ff  mov     rax, [rax+10h]
0x180056703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056708  nop
0x180056709  jmp     short loc_18005673F
0x18005670b  mov     rax, [rbx]
0x18005670e  lea     r8, [rsp+1A0h+var_160]
0x180056713  lea     rdx, _GUID_ab8dcf8e_08ad_562a_9967_fced64b54cb2
0x18005671a  mov     rcx, rbx
0x18005671d  mov     rax, [rax]
0x180056720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056725  mov     edi, eax
0x180056727  mov     rax, [rbx]
0x18005672a  mov     rcx, rbx
0x18005672d  mov     rax, [rax+10h]
0x180056731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056736  nop
0x180056737  test    edi, edi
0x180056739  jns     loc_1800567C3
0x18005673f  mov     rcx, [rbp+0A8h]; this
0x180056746  mov     r9d, edi; char *
0x180056749  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180056750  mov     edx, 56h ; 'V'; void *
0x180056755  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005675a  nop
0x18005675b  mov     rcx, [rsp+1A0h+var_160]
0x180056760  test    rcx, rcx
0x180056763  jz      short loc_180056772
0x180056765  mov     rax, [rcx]
0x180056768  mov     rax, [rax+10h]
0x18005676c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056771  nop
0x180056772  lea     rcx, [rbp+0A0h+var_108]
0x180056776  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005677b  lea     rcx, [rbp+0A0h+var_E8]
0x18005677f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056784  lea     rcx, [rsp+1A0h+var_128]
0x180056789  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005678e  lea     rcx, [rbp+0A0h+var_C8]
0x180056792  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056797  lea     rcx, [rbp+0A0h+var_A8]
0x18005679b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800567a0  lea     rcx, [rbp+0A0h+var_88]
0x1800567a4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800567a9  mov     rcx, [rsp+1A0h+SRWLock]; SRWLock
0x1800567ae  test    rcx, rcx
0x1800567b1  jz      short loc_1800567BC
0x1800567b3  mov     [rcx+8], esi
0x1800567b6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800567bc  mov     eax, edi
0x1800567be  jmp     loc_18005695D
0x1800567c3  mov     rax, [rsp+1A0h+var_160]
0x1800567c8  mov     rdi, [rsp+1A0h+var_138]
0x1800567cd  mov     [rsp+1A0h+var_138], rax
0x1800567d2  mov     [rsp+1A0h+var_150], rsi
0x1800567d7  lea     r9, [rsp+1A0h+var_138]
0x1800567dc  lea     r8, [rsp+1A0h+var_140]
0x1800567e1  lea     rdx, [rsp+1A0h+var_158]
0x1800567e6  lea     rcx, [rsp+1A0h+var_150]
0x1800567eb  call    ??$MakeAndInitialize@VEnvironmentCreationResult2@Preview@IsolationEnvironment@AI@Windows@@UIIsolationEnvironmentCreationResult_Exp2@2345@AEAW4IsolationEnvironmentCreationStatus_Exp2@2345@AEAJPEAUIIsolationEnvironment_Exp2@2345@@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationEnvironmentCreationResult_Exp2@Preview@IsolationEnvironment@AI@Windows@@AEAW4IsolationEnvironmentCreationStatus_Exp2@4567@AEAJ$$QEAPEAUIIsolationEnvironment_Exp2@4567@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::Preview::EnvironmentCreationResult2,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp2,Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentCreationStatus_Exp2 &,long &,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp2 *>(Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp2 * *,Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentCreationStatus_Exp2 &,long &,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp2 * &&)
0x1800567f0  mov     ebx, eax
0x1800567f2  test    eax, eax
0x1800567f4  jns     loc_180056895
0x1800567fa  mov     rcx, [rbp+0A8h]; this
0x180056801  mov     r9d, eax; char *
0x180056804  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005680b  mov     edx, 5Eh ; '^'; void *
0x180056810  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056815  nop
0x180056816  mov     rcx, [rsp+1A0h+var_150]
0x18005681b  test    rcx, rcx
0x18005681e  jz      short loc_18005682D
0x180056820  mov     rax, [rcx]
0x180056823  mov     rax, [rax+10h]
0x180056827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005682c  nop
0x18005682d  mov     rcx, [rsp+1A0h+var_160]
0x180056832  test    rcx, rcx
0x180056835  jz      short loc_180056844
0x180056837  mov     rax, [rcx]
0x18005683a  mov     rax, [rax+10h]
0x18005683e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056843  nop
0x180056844  lea     rcx, [rbp+0A0h+var_108]
0x180056848  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005684d  lea     rcx, [rbp+0A0h+var_E8]
0x180056851  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056856  lea     rcx, [rsp+1A0h+var_128]
0x18005685b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056860  lea     rcx, [rbp+0A0h+var_C8]
0x180056864  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056869  lea     rcx, [rbp+0A0h+var_A8]
0x18005686d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056872  lea     rcx, [rbp+0A0h+var_88]
0x180056876  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005687b  mov     rcx, [rsp+1A0h+SRWLock]; SRWLock
0x180056880  test    rcx, rcx
0x180056883  jz      short loc_18005688E
0x180056885  mov     [rcx+8], esi
0x180056888  call    cs:__imp_ReleaseSRWLockExclusive
0x18005688e  mov     eax, ebx
0x180056890  jmp     loc_18005695D
0x180056895  lea     r8, [rsp+1A0h+var_128]
0x18005689a  lea     rcx, [rbp+0A0h+var_68]
0x18005689e  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_WAEBV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring const &)
0x1800568a3  lea     rax, aIsolationenvir_0; "IsolationEnvironment created."
0x1800568aa  mov     [rsp+1A0h+var_138], rax
0x1800568af  lea     rax, [rbp+0A0h+var_68]
0x1800568b3  cmp     [rbp+0A0h+var_50], 7
0x1800568b8  cmova   rax, [rbp+0A0h+var_68]
0x1800568bd  mov     [rsp+1A0h+var_130], rax
0x1800568c2  lea     rdx, [rsp+1A0h+var_138]; wchar_t **
0x1800568c7  call    ?WriteLog@SecurityLog@@QEAA_NQEAPEB_WG@Z; SecurityLog::WriteLog(wchar_t const * * const,ushort)
0x1800568cc  mov     rax, [rsp+1A0h+var_150]
0x1800568d1  mov     [rsp+1A0h+var_150], rsi
0x1800568d6  mov     [rdi], rax
0x1800568d9  lea     rcx, [rbp+0A0h+var_68]
0x1800568dd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800568e2  nop
0x1800568e3  mov     rcx, [rsp+1A0h+var_150]
0x1800568e8  test    rcx, rcx
0x1800568eb  jz      short loc_1800568FA
0x1800568ed  mov     rax, [rcx]
0x1800568f0  mov     rax, [rax+10h]
0x1800568f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800568f9  nop
0x1800568fa  mov     rcx, [rsp+1A0h+var_160]
0x1800568ff  test    rcx, rcx
0x180056902  jz      short loc_180056911
0x180056904  mov     rax, [rcx]
0x180056907  mov     rax, [rax+10h]
0x18005690b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056910  nop
0x180056911  lea     rcx, [rbp+0A0h+var_108]
0x180056915  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005691a  lea     rcx, [rbp+0A0h+var_E8]
0x18005691e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056923  lea     rcx, [rsp+1A0h+var_128]
0x180056928  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005692d  lea     rcx, [rbp+0A0h+var_C8]
0x180056931  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056936  lea     rcx, [rbp+0A0h+var_A8]
0x18005693a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005693f  lea     rcx, [rbp+0A0h+var_88]
0x180056943  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056948  mov     rcx, [rsp+1A0h+SRWLock]; SRWLock
0x18005694d  test    rcx, rcx
0x180056950  jz      short loc_18005695B
0x180056952  mov     [rcx+8], esi
0x180056955  call    cs:__imp_ReleaseSRWLockExclusive
0x18005695b  xor     eax, eax
0x18005695d  mov     rcx, [rbp+0A0h+var_48]
0x180056961  xor     rcx, rsp; StackCookie
0x180056964  call    __security_check_cookie
0x180056969  add     rsp, 168h
0x180056970  pop     r15
0x180056972  pop     r14
0x180056974  pop     r13
0x180056976  pop     r12
0x180056978  pop     rdi
0x180056979  pop     rsi
0x18005697a  pop     rbx
0x18005697b  pop     rbp
0x18005697c  retn
```
