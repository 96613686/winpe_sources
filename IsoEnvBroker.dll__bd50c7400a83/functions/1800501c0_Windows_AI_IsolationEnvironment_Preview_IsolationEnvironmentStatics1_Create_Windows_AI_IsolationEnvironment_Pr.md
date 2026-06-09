# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics1::Create(Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp * *)

- ea: `0x1800501c0`
- end: `0x1800507a1`
- name: `?Create@IsolationEnvironmentStatics1@Preview@IsolationEnvironment@AI@Windows@@UEAAJPEAPEAUIIsolationEnvironmentCreationResult_Exp@2345@@Z`
- size: `1505`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics1 *__hidden this, struct Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp **)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002520`
- `0x180002a30`
- `0x18000a464`
- `0x18001045c`
- `0x180011e18`
- `0x1800134e8`
- `0x18004fb50`
- `0x1800501c0`
- `0x1800507a8`
- `0x180053110`
- `0x180053cf0`
- `0x180055450`
- `0x180063594`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005026a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005026a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180050278`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005028f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180050278`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18005028f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005022b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800502a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005058c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180050772`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005022b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800502a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005058c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180050772`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180050252`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x180050252`

## string_xrefs

- `0x18005024b`: `wtsapi32.dll`
- `0x1800501f0`: `Create for IsolationEnvironment called.`
- `0x18005051e`: `onecoreuap\windows\core\isoenvbroker\lib\v1\isolationenvironmentstatics.cpp`
- `0x18005066c`: `onecoreuap\windows\core\isoenvbroker\lib\v1\isolationenvironmentstatics.cpp`
- `0x1800506bf`: `IsolationEnvironment created.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics1::Create(
        Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics1 *this,
        struct Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp **a2)
{
  int v3; // r14d
  __int64 v4; // rcx
  RTL_SRWLOCK *v5; // rcx
  HMODULE LibraryW; // rax
  HMODULE v8; // rbx
  FARPROC ProcAddress; // rax
  int v10; // edi
  RTL_SRWLOCK *v11; // rcx
  int NewAgentUserForCaller; // r14d
  const wchar_t *v13; // rdi
  const wchar_t *v14; // r15
  const wchar_t *v15; // r12
  const wchar_t *v16; // r13
  wchar_t *v17; // rax
  wchar_t *v18; // rax
  _QWORD *v19; // rax
  _QWORD *v20; // rbx
  int v21; // edi
  __int64 v22; // rax
  RTL_SRWLOCK *v23; // rcx
  __int64 v24; // rdi
  _QWORD *v25; // rax
  _QWORD *v26; // rbx
  __int64 v27; // rdx
  SecurityLog *v28; // rcx
  unsigned __int16 v29; // r8
  wchar_t *v30; // rax
  struct Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp *v31; // rax
  RTL_SRWLOCK *v32; // rcx
  int v33; // [rsp+20h] [rbp-E0h]
  struct Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp *v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v37[2]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *v38; // [rsp+68h] [rbp-98h]
  wchar_t *v39[2]; // [rsp+70h] [rbp-90h] BYREF
  __m128i v40; // [rsp+80h] [rbp-80h]
  wchar_t *v41[2]; // [rsp+90h] [rbp-70h] BYREF
  __m128i v42; // [rsp+A0h] [rbp-60h]
  wchar_t *v43[2]; // [rsp+B0h] [rbp-50h] BYREF
  __m128i v44; // [rsp+C0h] [rbp-40h]
  wchar_t *v45[2]; // [rsp+D0h] [rbp-30h] BYREF
  __m128i v46; // [rsp+E0h] [rbp-20h]
  __int128 v47; // [rsp+F0h] [rbp-10h] BYREF
  __m128i v48; // [rsp+100h] [rbp+0h]
  __int128 v49; // [rsp+110h] [rbp+10h] BYREF
  __m128i si128; // [rsp+120h] [rbp+20h]
  _QWORD v51[4]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v3 = (int)this;
  Log(4u, L"Create for IsolationEnvironment called.");
  checked_srwlock::lock_exclusive(v4, &SRWLock);
  *a2 = 0;
  if ( (unsigned int)GetIsSupportedResult1(0) != 1 )
  {
    v5 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v5);
    }
    return 2147942450LL;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl'::`2'::impl) )
  {
    LibraryW = LoadLibraryW(L"wtsapi32.dll");
    v8 = LibraryW;
    if ( !LibraryW )
    {
LABEL_10:
      v11 = SRWLock;
      if ( SRWLock )
      {
        LODWORD(SRWLock[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v11);
      }
      return 2147549183LL;
    }
    ProcAddress = GetProcAddress(LibraryW, "WTSEnableChildSessions");
    if ( !ProcAddress )
    {
      FreeLibrary(v8);
      goto LABEL_10;
    }
    v10 = ((__int64 (__fastcall *)(__int64))ProcAddress)(1);
    FreeLibrary(v8);
    if ( !v10 )
      goto LABEL_10;
  }
  v49 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v49) = 0;
  v47 = 0;
  v48 = si128;
  LOWORD(v47) = 0;
  *(_OWORD *)v45 = 0;
  v46 = si128;
  LOWORD(v45[0]) = 0;
  *(_OWORD *)v39 = 0;
  v40 = si128;
  LOWORD(v39[0]) = 0;
  *(_OWORD *)v43 = 0;
  v44 = si128;
  LOWORD(v43[0]) = 0;
  *(_OWORD *)v41 = 0;
  v42 = si128;
  LOWORD(v41[0]) = 0;
  NewAgentUserForCaller = Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics1::CreateNewAgentUserForCaller(
                            v3 - 8,
                            (unsigned int)&v49,
                            (unsigned int)&v47,
                            (unsigned int)v45,
                            (__int64)v39,
                            (__int64)v43,
                            (__int64)v41);
  v13 = (const wchar_t *)v41;
  if ( v42.m128i_i64[1] > 7uLL )
    v13 = v41[0];
  v14 = (const wchar_t *)v43;
  if ( v44.m128i_i64[1] > 7uLL )
    v14 = v43[0];
  v15 = (const wchar_t *)v39;
  if ( v40.m128i_i64[1] > 7uLL )
    v15 = v39[0];
  v16 = (const wchar_t *)v45;
  if ( v46.m128i_i64[1] > 7uLL )
    v16 = v45[0];
  v17 = (wchar_t *)&v47;
  if ( v48.m128i_i64[1] > 7uLL )
    v17 = (wchar_t *)v47;
  v38 = v17;
  v18 = (wchar_t *)&v49;
  if ( si128.m128i_i64[1] > 7uLL )
    v18 = (wchar_t *)v49;
  v37[0] = v18;
  v35 = 0;
  v19 = operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  v20 = v19;
  if ( !v19 )
  {
    v21 = -2147024882;
    goto LABEL_32;
  }
  v19[4] = 1;
  *v19 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp,Windows::Foundation::IClosable>::`vftable';
  v19[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp,Windows::Foundation::IClosable>::`vftable'{for `IWeakReferenceSource'};
  v19[2] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp,Windows::Foundation::IClosable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *, _QWORD))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                              + 8LL))(
      Microsoft::WRL::Details::ModuleBase::module_,
      0);
  *v20 = &Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::`vftable';
  v20[1] = &Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::`vftable'{for `IWeakReferenceSource'};
  v20[2] = &Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'};
  *(_OWORD *)(v20 + 5) = 0;
  v20[7] = 0;
  v20[8] = 7;
  *((_WORD *)v20 + 20) = 0;
  *(_OWORD *)(v20 + 9) = 0;
  v20[11] = 0;
  v20[12] = 7;
  *((_WORD *)v20 + 36) = 0;
  *(_OWORD *)(v20 + 13) = 0;
  v20[15] = 0;
  v20[16] = 7;
  *((_WORD *)v20 + 52) = 0;
  *(_OWORD *)(v20 + 17) = 0;
  v20[19] = 0;
  v20[20] = 7;
  *((_WORD *)v20 + 68) = 0;
  v20[21] = 0;
  v20[22] = 0;
  v21 = Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::RuntimeClassInitialize(
          (Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1 *)v20,
          v37[0],
          v38,
          v16,
          v15,
          v14,
          v13);
  v22 = *v20;
  if ( v21 < 0 )
  {
    (*(void (__fastcall **)(_QWORD *))(v22 + 16))(v20);
    goto LABEL_32;
  }
  v21 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))v22)(
          v20,
          &GUID_1e5b19a7_2376_5263_bb90_cb067dd21747,
          &v35);
  (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
  if ( v21 < 0 )
  {
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v1\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)v21,
      v33);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
LABEL_34:
    std::wstring::~wstring(v41);
    std::wstring::~wstring(v43);
    std::wstring::~wstring(v39);
    std::wstring::~wstring(v45);
    std::wstring::~wstring(&v47);
    std::wstring::~wstring(&v49);
    v23 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v23);
    }
    return (unsigned int)v21;
  }
  v24 = v35;
  v34 = 0;
  v25 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v25;
  if ( !v25 )
  {
    v21 = -2147024882;
LABEL_44:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v1\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)v21,
      v33);
    if ( v34 )
      (*(void (__fastcall **)(struct Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp *))(*(_QWORD *)v34 + 16LL))(v34);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    goto LABEL_34;
  }
  v25[3] = 1;
  *v25 = &Microsoft::WRL::RuntimeClass<Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp>::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp'};
  v25[1] = &Microsoft::WRL::RuntimeClass<Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *v26 = &Windows::AI::IsolationEnvironment::Preview::EnvironmentCreationResult1::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp'};
  v26[1] = &Windows::AI::IsolationEnvironment::Preview::EnvironmentCreationResult1::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
  *((_DWORD *)v26 + 8) = 0;
  *((_DWORD *)v26 + 9) = NewAgentUserForCaller;
  v26[5] = v24;
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 8LL))(v24);
  v21 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, struct Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp **))*v26)(
          v26,
          &GUID_ed8425e5_5d71_5f72_8b49_1689f1e0a744,
          &v34);
  (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
  if ( v21 < 0 )
    goto LABEL_44;
  std::operator+<wchar_t>(v51, v27, v39);
  v37[0] = L"IsolationEnvironment created.";
  v30 = (wchar_t *)v51;
  if ( v51[3] > 7u )
    v30 = (wchar_t *)v51[0];
  v37[1] = v30;
  SecurityLog::WriteLog(v28, (const wchar_t **const)v37, v29);
  v31 = v34;
  v34 = 0;
  *a2 = v31;
  std::wstring::~wstring(v51);
  if ( v34 )
    (*(void (__fastcall **)(struct Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp *))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  std::wstring::~wstring(v41);
  std::wstring::~wstring(v43);
  std::wstring::~wstring(v39);
  std::wstring::~wstring(v45);
  std::wstring::~wstring(&v47);
  std::wstring::~wstring(&v49);
  v32 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v32);
  }
  return 0;
}

```

## disassembly

```asm
0x1800501c0  mov     [rsp-8+arg_10], rbx
0x1800501c5  push    rbp
0x1800501c6  push    rsi
0x1800501c7  push    rdi
0x1800501c8  push    r12
0x1800501ca  push    r13
0x1800501cc  push    r14
0x1800501ce  push    r15
0x1800501d0  lea     rbp, [rsp-60h]
0x1800501d5  sub     rsp, 160h
0x1800501dc  mov     rax, cs:__security_cookie
0x1800501e3  xor     rax, rsp
0x1800501e6  mov     [rbp+90h+var_40], rax
0x1800501ea  mov     rsi, rdx
0x1800501ed  mov     r14, rcx
0x1800501f0  lea     rdx, aCreateForIsola; "Create for IsolationEnvironment called."
0x1800501f7  mov     ecx, 4; unsigned __int8
0x1800501fc  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180050201  lea     rdx, [rsp+190h+SRWLock]
0x180050206  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x18005020b  xor     r15d, r15d
0x18005020e  mov     [rsi], r15
0x180050211  xor     ecx, ecx
0x180050213  call    ?GetIsSupportedResult1@@YA?AW4IsIsolationSupportedResult_Exp@Preview@IsolationEnvironment@AI@Windows@@_N@Z; GetIsSupportedResult1(bool)
0x180050218  cmp     eax, 1
0x18005021b  jz      short loc_18005023B
0x18005021d  mov     rcx, [rsp+190h+SRWLock]; SRWLock
0x180050222  test    rcx, rcx
0x180050225  jz      short loc_180050231
0x180050227  mov     [rcx+8], r15d
0x18005022b  call    cs:__imp_ReleaseSRWLockExclusive
0x180050231  mov     eax, 80070032h
0x180050236  jmp     loc_18005077A
0x18005023b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement> `wil::Feature<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::GetImpl(void)'::`2'::impl
0x180050242  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DecoupleAgentAndChildSessionEnablement>::__private_IsEnabled(void)
0x180050247  test    al, al
0x180050249  jnz     short loc_1800502B7
0x18005024b  lea     rcx, LibFileName; "wtsapi32.dll"
0x180050252  call    cs:__imp_LoadLibraryW
0x180050258  mov     rbx, rax
0x18005025b  test    rax, rax
0x18005025e  jz      short loc_180050299
0x180050260  lea     rdx, aWtsenablechild; "WTSEnableChildSessions"
0x180050267  mov     rcx, rax; hModule
0x18005026a  call    cs:__imp_GetProcAddress
0x180050270  test    rax, rax
0x180050273  jnz     short loc_180050280
0x180050275  mov     rcx, rbx; hLibModule
0x180050278  call    cs:__imp_FreeLibrary
0x18005027e  jmp     short loc_180050299
0x180050280  mov     ecx, 1
0x180050285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005028a  mov     edi, eax
0x18005028c  mov     rcx, rbx; hLibModule
0x18005028f  call    cs:__imp_FreeLibrary
0x180050295  test    edi, edi
0x180050297  jnz     short loc_1800502B7
0x180050299  mov     rcx, [rsp+190h+SRWLock]; SRWLock
0x18005029e  test    rcx, rcx
0x1800502a1  jz      short loc_1800502AD
0x1800502a3  mov     [rcx+8], r15d
0x1800502a7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800502ad  mov     eax, 8000FFFFh
0x1800502b2  jmp     loc_18005077A
0x1800502b7  xorps   xmm0, xmm0
0x1800502ba  movups  [rbp+90h+var_80], xmm0
0x1800502be  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800502c6  movdqu  [rbp+90h+var_70], xmm1
0x1800502cb  mov     word ptr [rbp+90h+var_80], r15w
0x1800502d0  movups  [rbp+90h+var_A0], xmm0
0x1800502d4  movdqu  [rbp+90h+var_90], xmm1
0x1800502d9  mov     word ptr [rbp+90h+var_A0], r15w
0x1800502de  movups  xmmword ptr [rbp+90h+var_C0], xmm0
0x1800502e2  movdqu  [rbp+90h+var_B0], xmm1
0x1800502e7  mov     word ptr [rbp+90h+var_C0], r15w
0x1800502ec  movups  xmmword ptr [rsp+190h+var_120], xmm0
0x1800502f1  movdqu  [rbp+90h+var_110], xmm1
0x1800502f6  mov     word ptr [rsp+190h+var_120], r15w
0x1800502fc  movups  xmmword ptr [rbp+90h+var_E0], xmm0
0x180050300  movdqu  [rbp+90h+var_D0], xmm1
0x180050305  mov     word ptr [rbp+90h+var_E0], r15w
0x18005030a  movups  xmmword ptr [rbp+90h+var_100], xmm0
0x18005030e  movdqu  [rbp+90h+var_F0], xmm1
0x180050313  mov     word ptr [rbp+90h+var_100], r15w
0x180050318  lea     rcx, [r14-8]
0x18005031c  lea     rax, [rbp+90h+var_100]
0x180050320  mov     [rsp+190h+var_160], rax
0x180050325  lea     rax, [rbp+90h+var_E0]
0x180050329  mov     [rsp+190h+var_168], rax
0x18005032e  lea     rax, [rsp+190h+var_120]
0x180050333  mov     [rsp+190h+var_170], rax
0x180050338  lea     r9, [rbp+90h+var_C0]
0x18005033c  lea     r8, [rbp+90h+var_A0]
0x180050340  lea     rdx, [rbp+90h+var_80]
0x180050344  call    ?CreateNewAgentUserForCaller@IsolationEnvironmentStatics1@Preview@IsolationEnvironment@AI@Windows@@AEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00000@Z; Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics1::CreateNewAgentUserForCaller(std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &,std::wstring &)
0x180050349  mov     r14d, eax
0x18005034c  lea     rdi, [rbp+90h+var_100]
0x180050350  cmp     qword ptr [rbp+90h+var_F0+8], 7
0x180050355  cmova   rdi, [rbp+90h+var_100]
0x18005035a  lea     r15, [rbp+90h+var_E0]
0x18005035e  cmp     qword ptr [rbp+90h+var_D0+8], 7
0x180050363  cmova   r15, [rbp+90h+var_E0]
0x180050368  lea     r12, [rsp+190h+var_120]
0x18005036d  cmp     qword ptr [rbp+90h+var_110+8], 7
0x180050372  cmova   r12, [rsp+190h+var_120]
0x180050378  lea     r13, [rbp+90h+var_C0]
0x18005037c  cmp     qword ptr [rbp+90h+var_B0+8], 7
0x180050381  cmova   r13, [rbp+90h+var_C0]
0x180050386  lea     rax, [rbp+90h+var_A0]
0x18005038a  cmp     qword ptr [rbp+90h+var_90+8], 7
0x18005038f  cmova   rax, qword ptr [rbp+90h+var_A0]
0x180050394  mov     [rsp+190h+var_128], rax
0x180050399  lea     rax, [rbp+90h+var_80]
0x18005039d  cmp     qword ptr [rbp+90h+var_70+8], 7
0x1800503a2  cmova   rax, qword ptr [rbp+90h+var_80]
0x1800503a7  mov     [rsp+190h+var_138], rax
0x1800503ac  mov     [rsp+190h+var_148], 0
0x1800503b5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800503bc  mov     ecx, 0B8h; unsigned __int64
0x1800503c1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800503c6  mov     rbx, rax
0x1800503c9  xor     edx, edx
0x1800503cb  test    rax, rax
0x1800503ce  jnz     short loc_1800503DD
0x1800503d0  mov     edi, 8007000Eh
0x1800503d5  xor     r15d, r15d
0x1800503d8  jmp     loc_180050514
0x1800503dd  mov     qword ptr [rax+20h], 1
0x1800503e5  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIsolationEnvironment_Exp@Preview@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@8@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp,Windows::Foundation::IClosable>::`vftable'
0x1800503ec  mov     [rbx], rax
0x1800503ef  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIsolationEnvironment_Exp@Preview@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@8@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp,Windows::Foundation::IClosable>::`vftable'{for `IWeakReferenceSource'}
0x1800503f6  mov     [rbx+8], rax
0x1800503fa  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIsolationEnvironment_Exp@Preview@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@8@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp,Windows::Foundation::IClosable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'}
0x180050401  mov     [rbx+10h], rax
0x180050405  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18005040c  test    rcx, rcx
0x18005040f  jz      short loc_18005041F
0x180050411  mov     rax, [rcx]
0x180050414  mov     rax, [rax+8]
0x180050418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005041d  xor     edx, edx
0x18005041f  lea     rax, ??_7IsolationEnvironment1@Preview@IsolationEnvironment@AI@Windows@@6B@; const Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::`vftable'
0x180050426  mov     [rbx], rax
0x180050429  lea     rax, ??_7IsolationEnvironment1@Preview@IsolationEnvironment@AI@Windows@@6BIWeakReferenceSource@@@; const Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::`vftable'{for `IWeakReferenceSource'}
0x180050430  mov     [rbx+8], rax
0x180050434  lea     rax, ??_7IsolationEnvironment1@Preview@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'}
0x18005043b  mov     [rbx+10h], rax
0x18005043f  xorps   xmm0, xmm0
0x180050442  movups  xmmword ptr [rbx+28h], xmm0
0x180050446  mov     [rbx+38h], rdx
0x18005044a  mov     ecx, 7
0x18005044f  mov     [rbx+40h], rcx
0x180050453  mov     [rbx+28h], dx
0x180050457  movups  xmmword ptr [rbx+48h], xmm0
0x18005045b  mov     [rbx+58h], rdx
0x18005045f  mov     [rbx+60h], rcx
0x180050463  mov     [rbx+48h], dx
0x180050467  movups  xmmword ptr [rbx+68h], xmm0
0x18005046b  mov     [rbx+78h], rdx
0x18005046f  mov     [rbx+80h], rcx
0x180050476  mov     [rbx+68h], dx
0x18005047a  movups  xmmword ptr [rbx+88h], xmm0
0x180050481  mov     [rbx+98h], rdx
0x180050488  mov     [rbx+0A0h], rcx
0x18005048f  mov     [rbx+88h], dx
0x180050496  mov     [rbx+0A8h], rdx
0x18005049d  mov     [rbx+0B0h], rdx
0x1800504a4  mov     [rsp+190h+var_160], rdi; wchar_t *
0x1800504a9  mov     [rsp+190h+var_168], r15; wchar_t *
0x1800504ae  mov     [rsp+190h+var_170], r12; int
0x1800504b3  mov     r9, r13; wchar_t *
0x1800504b6  mov     r8, [rsp+190h+var_128]; wchar_t *
0x1800504bb  mov     rdx, [rsp+190h+var_138]; wchar_t *
0x1800504c0  mov     rcx, rbx; this
0x1800504c3  call    ?RuntimeClassInitialize@IsolationEnvironment1@Preview@IsolationEnvironment@AI@Windows@@QEAAJPEB_W00000@Z; Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::RuntimeClassInitialize(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)
0x1800504c8  mov     edi, eax
0x1800504ca  mov     rax, [rbx]
0x1800504cd  xor     r15d, r15d
0x1800504d0  test    edi, edi
0x1800504d2  jns     short loc_1800504E3
0x1800504d4  mov     rcx, rbx
0x1800504d7  mov     rax, [rax+10h]
0x1800504db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504e0  nop
0x1800504e1  jmp     short loc_180050514
0x1800504e3  lea     r8, [rsp+190h+var_148]
0x1800504e8  lea     rdx, _GUID_1e5b19a7_2376_5263_bb90_cb067dd21747
0x1800504ef  mov     rcx, rbx
0x1800504f2  mov     rax, [rax]
0x1800504f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504fa  mov     edi, eax
0x1800504fc  mov     rax, [rbx]
0x1800504ff  mov     rcx, rbx
0x180050502  mov     rax, [rax+10h]
0x180050506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005050b  nop
0x18005050c  test    edi, edi
0x18005050e  jns     loc_180050599
0x180050514  mov     rcx, [rbp+98h]; this
0x18005051b  mov     r9d, edi; char *
0x18005051e  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180050525  mov     edx, 4Bh ; 'K'; void *
0x18005052a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005052f  nop
0x180050530  mov     rcx, [rsp+190h+var_148]
0x180050535  test    rcx, rcx
0x180050538  jz      short loc_180050547
0x18005053a  mov     rax, [rcx]
0x18005053d  mov     rax, [rax+10h]
0x180050541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050546  nop
0x180050547  lea     rcx, [rbp+90h+var_100]
0x18005054b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050550  lea     rcx, [rbp+90h+var_E0]
0x180050554  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050559  lea     rcx, [rsp+190h+var_120]
0x18005055e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050563  lea     rcx, [rbp+90h+var_C0]
0x180050567  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005056c  lea     rcx, [rbp+90h+var_A0]
0x180050570  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180050575  lea     rcx, [rbp+90h+var_80]
0x180050579  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005057e  mov     rcx, [rsp+190h+SRWLock]; SRWLock
0x180050583  test    rcx, rcx
0x180050586  jz      short loc_180050592
0x180050588  mov     [rcx+8], r15d
0x18005058c  call    cs:__imp_ReleaseSRWLockExclusive
0x180050592  mov     eax, edi
0x180050594  jmp     loc_18005077A
0x180050599  mov     rdi, [rsp+190h+var_148]
0x18005059e  mov     [rsp+190h+var_150], r15
0x1800505a3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800505aa  mov     ecx, 30h ; '0'; unsigned __int64
0x1800505af  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800505b4  mov     rbx, rax
0x1800505b7  test    rax, rax
0x1800505ba  jnz     short loc_1800505C6
0x1800505bc  mov     edi, 8007000Eh
0x1800505c1  jmp     loc_180050662
0x1800505c6  mov     qword ptr [rax+18h], 1
0x1800505ce  lea     rax, ??_7?$RuntimeClass@UIIsolationEnvironmentCreationResult_Exp@Preview@IsolationEnvironment@AI@Windows@@@WRL@Microsoft@@6BIIsolationEnvironmentCreationResult_Exp@Preview@IsolationEnvironment@AI@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp>::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp'}
0x1800505d5  mov     [rbx], rax
0x1800505d8  lea     rax, ??_7?$RuntimeClass@UIIsolationEnvironmentCreationResult_Exp@Preview@IsolationEnvironment@AI@Windows@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x1800505df  mov     [rbx+8], rax
0x1800505e3  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800505ea  test    rcx, rcx
0x1800505ed  jz      short loc_1800505FC
0x1800505ef  mov     rax, [rcx]
0x1800505f2  mov     rax, [rax+8]
0x1800505f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800505fb  nop
0x1800505fc  lea     rax, ??_7EnvironmentCreationResult1@Preview@IsolationEnvironment@AI@Windows@@6BIIsolationEnvironmentCreationResult_Exp@1234@@; const Windows::AI::IsolationEnvironment::Preview::EnvironmentCreationResult1::`vftable'{for `Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp'}
0x180050603  mov     [rbx], rax
0x180050606  lea     rax, ??_7EnvironmentCreationResult1@Preview@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::Preview::EnvironmentCreationResult1::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x18005060d  mov     [rbx+8], rax
0x180050611  mov     [rbx+20h], r15d
0x180050615  mov     [rbx+24h], r14d
0x180050619  mov     [rbx+28h], rdi
0x18005061d  test    rdi, rdi
0x180050620  jz      short loc_180050632
0x180050622  mov     rax, [rdi]
0x180050625  mov     rcx, rdi
0x180050628  mov     rax, [rax+8]
0x18005062c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050631  nop
0x180050632  mov     rax, [rbx]
0x180050635  lea     r8, [rsp+190h+var_150]
0x18005063a  lea     rdx, _GUID_ed8425e5_5d71_5f72_8b49_1689f1e0a744
0x180050641  mov     rcx, rbx
0x180050644  mov     rax, [rax]
0x180050647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005064c  mov     edi, eax
0x18005064e  mov     rax, [rbx]
0x180050651  mov     rcx, rbx
0x180050654  mov     rax, [rax+10h]
0x180050658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005065d  nop
0x18005065e  test    edi, edi
0x180050660  jns     short loc_1800506B1
0x180050662  mov     rcx, [rbp+98h]; this
0x180050669  mov     r9d, edi; char *
0x18005066c  lea     r8, aOnecoreuapWind_9; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180050673  mov     edx, 52h ; 'R'; void *
0x180050678  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005067d  nop
0x18005067e  mov     rcx, [rsp+190h+var_150]
0x180050683  test    rcx, rcx
0x180050686  jz      short loc_180050695
0x180050688  mov     rax, [rcx]
0x18005068b  mov     rax, [rax+10h]
0x18005068f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050694  nop
0x180050695  mov     rcx, [rsp+190h+var_148]
0x18005069a  test    rcx, rcx
0x18005069d  jz      short loc_1800506AC
0x18005069f  mov     rax, [rcx]
0x1800506a2  mov     rax, [rax+10h]
0x1800506a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800506ab  nop
  ... truncated ...
```
