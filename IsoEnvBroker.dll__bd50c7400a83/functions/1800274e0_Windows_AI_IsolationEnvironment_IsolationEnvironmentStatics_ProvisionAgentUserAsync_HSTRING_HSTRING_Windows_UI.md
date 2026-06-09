# Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::ProvisionAgentUserAsync(HSTRING__ *,HSTRING__ *,Windows::UI::WindowId,uint,HSTRING__ * *,Windows::Foundation::IAsyncOperation<Windows::AI::IsolationEnvironment::IsolationProvisionResult *> * *)

- ea: `0x1800274e0`
- end: `0x180027b52`
- name: `?ProvisionAgentUserAsync@IsolationEnvironmentStatics@IsolationEnvironment@AI@Windows@@UEAAJPEAUHSTRING__@@0UWindowId@UI@4@IPEAPEAU5@PEAPEAU?$IAsyncOperation@PEAVIsolationProvisionResult@IsolationEnvironment@AI@Windows@@@Foundation@4@@Z`
- size: `1650`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002520`
- `0x18000a464`
- `0x18001045c`
- `0x180011e18`
- `0x180013230`
- `0x1800134e8`
- `0x180014534`
- `0x180014c04`
- `0x1800155d8`
- `0x18001a1f8`
- `0x18001fec8`
- `0x180020d48`
- `0x180022424`
- `0x1800274e0`
- `0x180032e60`
- `0x1800357a0`
- `0x180039b3c`
- `0x18003a79c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800276bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027881`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800279ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027a15`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800276bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027881`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800279ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180027a15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002788f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800279b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002788f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800279b9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180027766`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180027766`

## string_xrefs

- `0x180027567`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x1800276e8`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`

## pseudocode

```c
__int64 __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::ProvisionAgentUserAsync(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6,
        _QWORD *a7)
{
  __int64 v10; // rcx
  int v11; // ebx
  unsigned int i; // ebx
  __int64 String; // rax
  __int64 v15; // rdx
  int AppIdentity; // eax
  unsigned int v17; // eax
  volatile signed __int32 *v18; // rbx
  unsigned int v19; // edi
  RTL_SRWLOCK *v20; // rcx
  int v21; // eax
  signed int v22; // esi
  volatile signed __int32 *v23; // rdi
  HANDLE v24; // rbx
  volatile signed __int32 *v25; // rsi
  __int64 v26; // rsi
  int v27; // esi
  unsigned int v28; // eax
  volatile signed __int32 *v29; // rdi
  unsigned int v30; // esi
  RTL_SRWLOCK *v31; // rcx
  volatile signed __int32 *v32; // rbx
  signed int LastError; // eax
  volatile signed __int32 *v34; // r15
  unsigned int v35; // eax
  volatile signed __int32 *v36; // rdi
  RTL_SRWLOCK *v37; // rcx
  volatile signed __int32 *v38; // rsi
  RTL_SRWLOCK *v39; // rcx
  unsigned __int64 *v40; // rax
  __int64 v41; // r8
  unsigned __int64 *v42; // rdx
  volatile signed __int32 *v43; // rbx
  unsigned __int64 v44; // rax
  __int128 v45; // kr00_16
  int v46; // [rsp+20h] [rbp-E0h]
  const char *v47; // [rsp+28h] [rbp-D8h]
  _BYTE v48[12]; // [rsp+30h] [rbp-D0h] BYREF
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v50; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v51; // [rsp+58h] [rbp-A8h]
  _QWORD *v52; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v53; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v54[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v55[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v56[3]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v57; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v58; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v59; // [rsp+F0h] [rbp-10h]
  __int64 v60; // [rsp+F8h] [rbp-8h]
  __int128 v61; // [rsp+100h] [rbp+0h]
  __int64 v62; // [rsp+110h] [rbp+10h]
  char *v63[4]; // [rsp+120h] [rbp+20h] BYREF
  char *v64[4]; // [rsp+140h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v52 = a7;
  Log(4u, L"IsolationEnvironment::ProvisionClientAsync called.");
  *a7 = 0;
  v11 = CheckCallingProcessCohort(1, 0);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1B3,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)v11,
      (int)"Calling user is not in a supported cohort",
      v47);
    return (unsigned int)v11;
  }
  v51 = 0;
  *(_QWORD *)v48 = a5;
  v50 = 0;
  if ( a5 )
    std::vector<std::wstring>::_Reallocate<0>(&v50, v48);
  for ( i = 0; i < a5; ++i )
  {
    String = GetString(v55, *(_QWORD *)(a6 + 8LL * i));
    v15 = *((_QWORD *)&v50 + 1);
    if ( *((_QWORD *)&v50 + 1) == v51 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v50, *((_QWORD *)&v50 + 1), String);
    }
    else
    {
      **((_OWORD **)&v50 + 1) = 0;
      *(_QWORD *)(v15 + 16) = 0;
      *(_QWORD *)(v15 + 24) = 0;
      *(_OWORD *)v15 = *(_OWORD *)String;
      *(_OWORD *)(v15 + 16) = *(_OWORD *)(String + 16);
      *(_WORD *)String = 0;
      *(_QWORD *)(String + 16) = 0;
      *(_QWORD *)(String + 24) = 7;
      *((_QWORD *)&v50 + 1) += 32LL;
    }
    std::wstring::~wstring((char **)v55);
  }
  v55[0] = 0;
  checked_srwlock::lock_exclusive(v10, &SRWLock);
  *(_QWORD *)v48 = &v52;
  v53 = 0;
  AppIdentity = AppIdentity::QueryAppIdentity((__int64)&v53, 0);
  if ( AppIdentity < 0 )
  {
    v17 = Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::ProvisionAgentUserAsync_::_12_::_lambda_1_::operator()(
            v48,
            (unsigned int)AppIdentity,
            8);
    v18 = (volatile signed __int32 *)*((_QWORD *)&v53 + 1);
    v19 = v17;
    if ( *((_QWORD *)&v53 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v53 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    v20 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v20);
    }
    goto LABEL_66;
  }
  v54[0] = 0;
  v21 = AppIdentity::QueryAppIdentity((__int64)v54, 0);
  v22 = v21;
  if ( v21 >= 0 )
  {
    v24 = OpenProcess(0x101000u, 0, *(_DWORD *)(*(_QWORD *)&v54[0] + 200LL));
    if ( v24 )
    {
      v25 = (volatile signed __int32 *)*((_QWORD *)&v54[0] + 1);
      if ( *((_QWORD *)&v54[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v54[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
          if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v22 = LastError;
      if ( LastError > 0 )
        v22 = (unsigned __int16)LastError | 0x80070000;
      v34 = (volatile signed __int32 *)*((_QWORD *)&v54[0] + 1);
      if ( *((_QWORD *)&v54[0] + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v54[0] + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
          if ( !_InterlockedDecrement(v34 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
        }
      }
      if ( v22 < 0 )
        goto LABEL_47;
    }
    v26 = GetString(v63, a2);
    memset(v54, 0, sizeof(v54));
    std::wstring::_Construct<1,wchar_t const *>((char **)v54, &word_180096C4C, 0);
    v27 = ClientIdentity::Find(v54, &v53, v26, v55);
    std::wstring::~wstring((char **)v54);
    std::wstring::~wstring(v63);
    if ( v27 >= 0 )
    {
      v38 = (volatile signed __int32 *)*((_QWORD *)&v53 + 1);
      if ( *((_QWORD *)&v53 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v53 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
          if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
        }
      }
      v39 = SRWLock;
      if ( SRWLock )
      {
        LODWORD(SRWLock[1].Ptr) = 0;
        ReleaseSRWLockExclusive(v39);
      }
      v40 = (unsigned __int64 *)GetString(v64, a3);
      v56[0] = v24;
      v42 = v40;
      v43 = (volatile signed __int32 *)*((_QWORD *)&v55[0] + 1);
      if ( *((_QWORD *)&v55[0] + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v55[0] + 1) + 8LL));
      v57 = *v40;
      *((_QWORD *)&v57 + 1) = v40[1];
      v58 = v40[2];
      v44 = v40[3];
      v56[1] = *(_QWORD *)&v55[0];
      v59 = v44;
      v56[2] = v43;
      *(_WORD *)v42 = 0;
      v42[2] = 0;
      v42[3] = 7;
      v45 = v50;
      v62 = v51;
      v60 = a4;
      v51 = 0;
      v50 = 0u;
      v61 = v45;
      *(_DWORD *)v48 = 3;
      *(_QWORD *)&v48[4] = 128;
      v19 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::AI::IsolationEnvironment::IIsolationProvisionResult__Windows::AI::IsolationEnvironment::IsolationProvisionResult___Windows::Internal::ComTaskPoolHandler__Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::ProvisionAgentUserAsync_::_2_::_lambda_2___(
              v48,
              v52,
              v41,
              v56);
      Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::ProvisionAgentUserAsync_::_2_::_lambda_2_::__lambda_2_(v56);
      std::wstring::~wstring(v64);
      if ( v43 )
      {
        if ( _InterlockedExchangeAdd(v43 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
          if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
        }
      }
      goto LABEL_66;
    }
    v28 = Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::ProvisionAgentUserAsync_::_12_::_lambda_1_::operator()(
            v48,
            (unsigned int)v27,
            7);
    v29 = (volatile signed __int32 *)*((_QWORD *)&v53 + 1);
    v30 = v28;
    if ( *((_QWORD *)&v53 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v53 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
        if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      }
    }
    v31 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v31);
    }
    if ( v24 )
      CloseHandle(v24);
    v32 = (volatile signed __int32 *)*((_QWORD *)&v55[0] + 1);
    if ( *((_QWORD *)&v55[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v55[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
        if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
      }
    }
    goto LABEL_53;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x40E,
    (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
    (const char *)(unsigned int)v21,
    v46);
  v23 = (volatile signed __int32 *)*((_QWORD *)&v54[0] + 1);
  if ( *((_QWORD *)&v54[0] + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v54[0] + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
      if ( !_InterlockedDecrement(v23 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
    }
  }
LABEL_47:
  v35 = Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::ProvisionAgentUserAsync_::_12_::_lambda_1_::operator()(
          v48,
          (unsigned int)v22,
          9);
  v36 = (volatile signed __int32 *)*((_QWORD *)&v53 + 1);
  v30 = v35;
  if ( *((_QWORD *)&v53 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v53 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
      if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
    }
  }
  v37 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v37);
  }
LABEL_53:
  v19 = v30;
LABEL_66:
  std::vector<std::wstring>::~vector<std::wstring>((__int64)&v50);
  return v19;
}

```

## disassembly

```asm
0x1800274e0  mov     [rsp-8+arg_0], rbx
0x1800274e5  push    rbp
0x1800274e6  push    rsi
0x1800274e7  push    rdi
0x1800274e8  push    r12
0x1800274ea  push    r13
0x1800274ec  push    r14
0x1800274ee  push    r15
0x1800274f0  lea     rbp, [rsp-70h]
0x1800274f5  sub     rsp, 170h
0x1800274fc  mov     rax, cs:__security_cookie
0x180027503  xor     rax, rsp
0x180027506  mov     [rbp+0A0h+var_40], rax
0x18002750a  mov     rax, [rbp+0A0h+arg_30]
0x180027511  mov     r13, rdx
0x180027514  mov     r14, [rbp+0A0h+arg_28]
0x18002751b  lea     rdx, aIsolationenvir_11; "IsolationEnvironment::ProvisionClientAs"...
0x180027522  mov     ecx, 4; unsigned __int8
0x180027527  mov     [rsp+1A0h+var_140], rax
0x18002752c  mov     rdi, r9
0x18002752f  mov     r12, r8
0x180027532  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180027537  mov     rax, [rsp+1A0h+var_140]
0x18002753c  xor     r15d, r15d
0x18002753f  xor     edx, edx; enum Windows::AI::IsolationEnvironment::IsolationUserCohortKind *
0x180027541  mov     cl, 1; bool
0x180027543  mov     [rax], r15
0x180027546  call    ?CheckCallingProcessCohort@@YAJ_NPEAW4IsolationUserCohortKind@IsolationEnvironment@AI@Windows@@@Z; CheckCallingProcessCohort(bool,Windows::AI::IsolationEnvironment::IsolationUserCohortKind *)
0x18002754b  mov     ebx, eax
0x18002754d  test    eax, eax
0x18002754f  jns     short loc_18002757F
0x180027551  mov     rcx, [rbp+0A8h]; this
0x180027558  lea     rax, aCallingUserIsN; "Calling user is not in a supported coho"...
0x18002755f  mov     r9d, ebx; char *
0x180027562  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x180027567  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18002756e  mov     edx, 1B3h; void *
0x180027573  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180027578  mov     eax, ebx
0x18002757a  jmp     loc_180027B2B
0x18002757f  mov     esi, [rbp+0A0h+arg_20]
0x180027585  xorps   xmm0, xmm0
0x180027588  mov     [rsp+1A0h+var_148], r15
0x18002758d  mov     [rsp+1A0h+var_170], rsi
0x180027592  movdqu  [rsp+1A0h+var_158], xmm0
0x180027598  test    esi, esi
0x18002759a  jz      short loc_1800275AB
0x18002759c  lea     rdx, [rsp+1A0h+var_170]
0x1800275a1  lea     rcx, [rsp+1A0h+var_158]
0x1800275a6  call    ??$_Reallocate@$0A@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::wstring>::_Reallocate<0>(unsigned __int64 &)
0x1800275ab  mov     ebx, r15d
0x1800275ae  test    esi, esi
0x1800275b0  jz      short loc_18002761D
0x1800275b2  mov     edx, ebx
0x1800275b4  lea     rcx, [rbp+0A0h+var_100]
0x1800275b8  mov     rdx, [r14+rdx*8]
0x1800275bc  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x1800275c1  mov     rdx, qword ptr [rsp+1A0h+var_158+8]
0x1800275c6  mov     r8, rax
0x1800275c9  cmp     rdx, [rsp+1A0h+var_148]
0x1800275ce  jz      short loc_180027604
0x1800275d0  xorps   xmm0, xmm0
0x1800275d3  movups  xmmword ptr [rdx], xmm0
0x1800275d6  mov     [rdx+10h], r15
0x1800275da  mov     [rdx+18h], r15
0x1800275de  movups  xmm0, xmmword ptr [rax]
0x1800275e1  movups  xmmword ptr [rdx], xmm0
0x1800275e4  movups  xmm1, xmmword ptr [rax+10h]
0x1800275e8  movups  xmmword ptr [rdx+10h], xmm1
0x1800275ec  mov     [rax], r15w
0x1800275f0  mov     [rax+10h], r15
0x1800275f4  mov     qword ptr [rax+18h], 7
0x1800275fc  add     qword ptr [rsp+1A0h+var_158+8], 20h ; ' '
0x180027602  jmp     short loc_18002760E
0x180027604  lea     rcx, [rsp+1A0h+var_158]
0x180027609  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18002760e  lea     rcx, [rbp+0A0h+var_100]
0x180027612  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027617  inc     ebx
0x180027619  cmp     ebx, esi
0x18002761b  jb      short loc_1800275B2
0x18002761d  xorps   xmm0, xmm0
0x180027620  lea     rdx, [rsp+1A0h+SRWLock]
0x180027625  movdqu  [rbp+0A0h+var_100], xmm0
0x18002762a  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x18002762f  lea     rax, [rsp+1A0h+var_140]
0x180027634  xorps   xmm0, xmm0
0x180027637  xor     edx, edx
0x180027639  mov     [rsp+1A0h+var_170], rax
0x18002763e  lea     rcx, [rsp+1A0h+var_138]
0x180027643  movdqu  [rsp+1A0h+var_138], xmm0
0x180027649  call    ?QueryAppIdentity@AppIdentity@@SAJAEAV?$shared_ptr@VAppIdentity@@@std@@PEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@@Z; AppIdentity::QueryAppIdentity(std::shared_ptr<AppIdentity> &,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus *)
0x18002764e  test    eax, eax
0x180027650  jns     short loc_1800276C8
0x180027652  mov     r8d, 8
0x180027658  lea     rcx, [rsp+1A0h+var_170]
0x18002765d  mov     edx, eax
0x18002765f  call    _Windows__AI__IsolationEnvironment__IsolationEnvironmentStatics__ProvisionAgentUserAsync____12____lambda_1___operator__
0x180027664  mov     rbx, qword ptr [rsp+1A0h+var_138+8]
0x180027669  mov     edi, eax
0x18002766b  test    rbx, rbx
0x18002766e  jz      short loc_1800276AB
0x180027670  or      r14d, 0FFFFFFFFh
0x180027674  mov     ecx, r14d
0x180027677  lock xadd [rbx+8], ecx
0x18002767c  add     ecx, r14d
0x18002767f  jnz     short loc_1800276AB
0x180027681  mov     rdx, [rbx]
0x180027684  mov     rcx, rbx
0x180027687  mov     rax, [rdx]
0x18002768a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002768f  mov     eax, r14d
0x180027692  lock xadd [rbx+0Ch], eax
0x180027697  add     eax, r14d
0x18002769a  jnz     short loc_1800276AB
0x18002769c  mov     rax, [rbx]
0x18002769f  mov     rcx, rbx
0x1800276a2  mov     rax, [rax+8]
0x1800276a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276ab  mov     rcx, [rsp+1A0h+SRWLock]; SRWLock
0x1800276b0  test    rcx, rcx
0x1800276b3  jz      loc_180027B1F
0x1800276b9  mov     [rcx+8], r15d
0x1800276bd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800276c3  jmp     loc_180027B1F
0x1800276c8  xorps   xmm0, xmm0
0x1800276cb  lea     rcx, [rbp+0A0h+var_120]
0x1800276cf  xor     edx, edx
0x1800276d1  movdqu  [rbp+0A0h+var_120], xmm0
0x1800276d6  call    ?QueryAppIdentity@AppIdentity@@SAJAEAV?$shared_ptr@VAppIdentity@@@std@@PEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@@Z; AppIdentity::QueryAppIdentity(std::shared_ptr<AppIdentity> &,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus *)
0x1800276db  mov     esi, eax
0x1800276dd  test    eax, eax
0x1800276df  jns     short loc_180027754
0x1800276e1  mov     rcx, [rbp+0A8h]; this
0x1800276e8  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800276ef  mov     r9d, eax; char *
0x1800276f2  mov     edx, 40Eh; void *
0x1800276f7  mov     rbx, r15
0x1800276fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800276ff  mov     rdi, qword ptr [rbp+0A0h+var_120+8]
0x180027703  or      r14d, 0FFFFFFFFh
0x180027707  test    rdi, rdi
0x18002770a  jz      loc_180027948
0x180027710  mov     eax, r14d
0x180027713  lock xadd [rdi+8], eax
0x180027718  add     eax, r14d
0x18002771b  jnz     loc_180027948
0x180027721  mov     rax, [rdi]
0x180027724  mov     rcx, rdi
0x180027727  mov     rax, [rax]
0x18002772a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002772f  mov     eax, r14d
0x180027732  lock xadd [rdi+0Ch], eax
0x180027737  add     eax, r14d
0x18002773a  jnz     loc_180027948
0x180027740  mov     rax, [rdi]
0x180027743  mov     rcx, rdi
0x180027746  mov     rax, [rax+8]
0x18002774a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002774f  jmp     loc_180027948
0x180027754  mov     r8, qword ptr [rbp+0A0h+var_120]
0x180027758  xor     edx, edx; bInheritHandle
0x18002775a  mov     ecx, 101000h; dwDesiredAccess
0x18002775f  mov     r8d, [r8+0C8h]; dwProcessId
0x180027766  call    cs:__imp_OpenProcess
0x18002776c  or      r14d, 0FFFFFFFFh
0x180027770  mov     rbx, rax
0x180027773  test    rax, rax
0x180027776  jz      loc_1800278E6
0x18002777c  mov     rsi, qword ptr [rbp+0A0h+var_120+8]
0x180027780  test    rsi, rsi
0x180027783  jz      short loc_1800277BC
0x180027785  mov     eax, r14d
0x180027788  lock xadd [rsi+8], eax
0x18002778d  add     eax, r14d
0x180027790  jnz     short loc_1800277BC
0x180027792  mov     rax, [rsi]
0x180027795  mov     rcx, rsi
0x180027798  mov     rax, [rax]
0x18002779b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277a0  mov     eax, r14d
0x1800277a3  lock xadd [rsi+0Ch], eax
0x1800277a8  add     eax, r14d
0x1800277ab  jnz     short loc_1800277BC
0x1800277ad  mov     rax, [rsi]
0x1800277b0  mov     rcx, rsi
0x1800277b3  mov     rax, [rax+8]
0x1800277b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277bc  mov     rdx, r13
0x1800277bf  lea     rcx, [rbp+0A0h+var_80]
0x1800277c3  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x1800277c8  xorps   xmm0, xmm0
0x1800277cb  lea     rdx, word_180096C4C
0x1800277d2  xorps   xmm1, xmm1
0x1800277d5  lea     rcx, [rbp+0A0h+var_120]
0x1800277d9  xor     r8d, r8d
0x1800277dc  mov     rsi, rax
0x1800277df  movups  [rbp+0A0h+var_120], xmm0
0x1800277e3  movdqu  [rbp+0A0h+var_110], xmm1
0x1800277e8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800277ed  lea     r9, [rbp+0A0h+var_100]
0x1800277f1  mov     r8, rsi
0x1800277f4  lea     rdx, [rsp+1A0h+var_138]
0x1800277f9  lea     rcx, [rbp+0A0h+var_120]
0x1800277fd  call    ?Find@ClientIdentity@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$shared_ptr@VAppIdentity@@@3@0AEAV?$shared_ptr@VClientIdentity@@@3@@Z; ClientIdentity::Find(std::wstring const &,std::shared_ptr<AppIdentity> const &,std::wstring const &,std::shared_ptr<ClientIdentity> &)
0x180027802  lea     rcx, [rbp+0A0h+var_120]
0x180027806  mov     esi, eax
0x180027808  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002780d  lea     rcx, [rbp+0A0h+var_80]
0x180027811  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027816  test    esi, esi
0x180027818  jns     loc_1800279C6
0x18002781e  mov     r8d, 7
0x180027824  lea     rcx, [rsp+1A0h+var_170]
0x180027829  mov     edx, esi
0x18002782b  call    _Windows__AI__IsolationEnvironment__IsolationEnvironmentStatics__ProvisionAgentUserAsync____12____lambda_1___operator__
0x180027830  mov     rdi, qword ptr [rsp+1A0h+var_138+8]
0x180027835  mov     esi, eax
0x180027837  test    rdi, rdi
0x18002783a  jz      short loc_180027873
0x18002783c  mov     ecx, r14d
0x18002783f  lock xadd [rdi+8], ecx
0x180027844  add     ecx, r14d
0x180027847  jnz     short loc_180027873
0x180027849  mov     rdx, [rdi]
0x18002784c  mov     rcx, rdi
0x18002784f  mov     rax, [rdx]
0x180027852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027857  mov     eax, r14d
0x18002785a  lock xadd [rdi+0Ch], eax
0x18002785f  add     eax, r14d
0x180027862  jnz     short loc_180027873
0x180027864  mov     rax, [rdi]
0x180027867  mov     rcx, rdi
0x18002786a  mov     rax, [rax+8]
0x18002786e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027873  mov     rcx, [rsp+1A0h+SRWLock]; SRWLock
0x180027878  test    rcx, rcx
0x18002787b  jz      short loc_180027887
0x18002787d  mov     [rcx+8], r15d
0x180027881  call    cs:__imp_ReleaseSRWLockExclusive
0x180027887  test    rbx, rbx
0x18002788a  jz      short loc_180027895
0x18002788c  mov     rcx, rbx; hObject
0x18002788f  call    cs:__imp_CloseHandle
0x180027895  mov     rbx, qword ptr [rbp+0A0h+var_100+8]
0x180027899  test    rbx, rbx
0x18002789c  jz      loc_1800279BF
0x1800278a2  mov     eax, r14d
0x1800278a5  lock xadd [rbx+8], eax
0x1800278aa  add     eax, r14d
0x1800278ad  jnz     loc_1800279BF
0x1800278b3  mov     rax, [rbx]
0x1800278b6  mov     rcx, rbx
0x1800278b9  mov     rax, [rax]
0x1800278bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278c1  mov     eax, r14d
0x1800278c4  lock xadd [rbx+0Ch], eax
0x1800278c9  add     eax, r14d
0x1800278cc  jnz     loc_1800279BF
0x1800278d2  mov     rax, [rbx]
0x1800278d5  mov     rcx, rbx
0x1800278d8  mov     rax, [rax+8]
0x1800278dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800278e1  jmp     loc_1800279BF
0x1800278e6  call    cs:__imp_GetLastError
0x1800278ec  mov     esi, eax
0x1800278ee  test    eax, eax
0x1800278f0  jle     short loc_1800278FB
0x1800278f2  movzx   esi, ax
0x1800278f5  or      esi, 80070000h
0x1800278fb  mov     r15, qword ptr [rbp+0A0h+var_120+8]
0x1800278ff  test    r15, r15
0x180027902  jz      short loc_18002793D
0x180027904  mov     eax, r14d
0x180027907  lock xadd [r15+8], eax
0x18002790d  add     eax, r14d
0x180027910  jnz     short loc_18002793D
0x180027912  mov     rax, [r15]
0x180027915  mov     rcx, r15
0x180027918  mov     rax, [rax]
0x18002791b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027920  mov     eax, r14d
0x180027923  lock xadd [r15+0Ch], eax
0x180027929  add     eax, r14d
0x18002792c  jnz     short loc_18002793D
0x18002792e  mov     rax, [r15]
0x180027931  mov     rcx, r15
0x180027934  mov     rax, [rax+8]
0x180027938  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002793d  xor     r15d, r15d
0x180027940  test    esi, esi
0x180027942  jns     loc_1800277BC
0x180027948  mov     r8d, 9
0x18002794e  lea     rcx, [rsp+1A0h+var_170]
0x180027953  mov     edx, esi
0x180027955  call    _Windows__AI__IsolationEnvironment__IsolationEnvironmentStatics__ProvisionAgentUserAsync____12____lambda_1___operator__
0x18002795a  mov     rdi, qword ptr [rsp+1A0h+var_138+8]
0x18002795f  mov     esi, eax
0x180027961  test    rdi, rdi
  ... truncated ...
```
