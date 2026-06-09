# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::Create_v3(HSTRING__ *,HSTRING__ *,Windows::AI::IsolationEnvironment::Preview::IsolationConfigurationId_Exp2,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp2 * *)

- ea: `0x180056d90`
- end: `0x1800574b2`
- name: `?Create_v3@IsolationEnvironmentStatics2@Preview@IsolationEnvironment@AI@Windows@@UEAAJPEAUHSTRING__@@0W4IsolationConfigurationId_Exp2@2345@PEAPEAUIIsolationEnvironmentCreationResult_Exp2@2345@@Z`
- size: `1826`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180002520`
- `0x180002ee8`
- `0x18000a464`
- `0x18001045c`
- `0x180011e18`
- `0x1800134e8`
- `0x180021564`
- `0x1800357a0`
- `0x18004fb50`
- `0x18005579c`
- `0x180055894`
- `0x180056d90`
- `0x1800574b8`
- `0x180058110`
- `0x180058654`
- `0x180059040`
- `0x18005b2a4`
- `0x180063594`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056e5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056e82`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056fda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005707c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057186`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057276`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005741d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056e5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056e82`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180056fda`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005707c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057186`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057276`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005741d`

## string_xrefs

- `0x180057365`: `IsolationEnvironment created.`
- `0x180056dca`: `IsolationEnvironment::Create_v3 called.`
- `0x180056fbc`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironmentstatics.cpp`
- `0x1800570ca`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironmentstatics.cpp`
- `0x180057124`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironmentstatics.cpp`
- `0x1800571fc`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironmentstatics.cpp`
- `0x18005730f`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironmentstatics.cpp`
- `0x180056f40`: `onecoreuap\windows\core\isoenvbroker\lib\v2\clientconnection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::Create_v3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        _QWORD *a5)
{
  Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2 *v9; // rcx
  RTL_SRWLOCK *v10; // rcx
  int v11; // ebx
  RTL_SRWLOCK *v12; // rcx
  const char *String; // rsi
  char *v14; // rbx
  char *v15; // r14
  char *v16; // r15
  int Worker; // eax
  __int64 v18; // r8
  RTL_SRWLOCK *v19; // rcx
  void (__fastcall **v20)(_QWORD); // rax
  char *v21; // rcx
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // r8
  RTL_SRWLOCK *v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  int AgentUser; // eax
  volatile signed __int32 *v29; // rdi
  RTL_SRWLOCK *v30; // rcx
  int v31; // eax
  volatile signed __int32 *v32; // rdi
  RTL_SRWLOCK *v33; // rcx
  char *v34; // rdi
  int v35; // eax
  __int64 v36; // rdx
  SecurityLog *v37; // rcx
  unsigned __int16 v38; // r8
  wchar_t *v39; // rax
  __int64 v40; // rax
  volatile signed __int32 *v41; // rbx
  RTL_SRWLOCK *v42; // rcx
  volatile signed __int32 *v43; // rbx
  int v45; // [rsp+20h] [rbp-E0h]
  int v46; // [rsp+20h] [rbp-E0h]
  PSRWLOCK SRWLock; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v48; // [rsp+38h] [rbp-C8h] BYREF
  PSRWLOCK v49; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v50; // [rsp+48h] [rbp-B8h] BYREF
  int v51; // [rsp+58h] [rbp-A8h] BYREF
  int v52; // [rsp+5Ch] [rbp-A4h] BYREF
  wchar_t *v53[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v54[4]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v55; // [rsp+80h] [rbp-80h]
  __int64 v56; // [rsp+88h] [rbp-78h]
  _OWORD v57[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v58; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v59; // [rsp+C0h] [rbp-40h]
  __int64 v60; // [rsp+C8h] [rbp-38h]
  __int128 v61; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v62; // [rsp+E0h] [rbp-20h]
  __int64 v63; // [rsp+E8h] [rbp-18h]
  __int128 v64; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v65; // [rsp+100h] [rbp+0h]
  __int64 v66; // [rsp+108h] [rbp+8h]
  __int128 v67; // [rsp+110h] [rbp+10h] BYREF
  __int64 v68; // [rsp+120h] [rbp+20h]
  __int64 v69; // [rsp+128h] [rbp+28h]
  char *v70[4]; // [rsp+130h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  Log(4u, L"IsolationEnvironment::Create_v3 called.");
  *a5 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 7;
  LOWORD(v67) = 0;
  v64 = 0;
  v65 = 0;
  v66 = 7;
  LOWORD(v64) = 0;
  v61 = 0;
  v62 = 0;
  v63 = 7;
  LOWORD(v61) = 0;
  v58 = 0;
  v59 = 0;
  v60 = 7;
  LOWORD(v58) = 0;
  v50 = 0;
  checked_srwlock::lock_exclusive(7, &SRWLock);
  if ( (unsigned int)GetIsSupportedResult2(0) != 1 )
  {
    v10 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v10);
    }
    v11 = -2147024846;
    goto LABEL_73;
  }
  if ( !Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::EnabledChildSessions(v9) )
  {
    v12 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v12);
    }
    v11 = -2147418113;
    goto LABEL_73;
  }
  String = (const char *)GetString(v57, a3);
  v14 = (char *)GetString(v70, a2);
  v15 = (char *)operator new(0x88u);
  *((_DWORD *)v15 + 2) = 1;
  *((_DWORD *)v15 + 3) = 1;
  *(_QWORD *)v15 = &std::_Ref_count_obj2<ClientConnection2>::`vftable';
  v16 = v15 + 16;
  v15[16] = 0;
  *((_QWORD *)v15 + 3) = 0;
  *((_OWORD *)v15 + 2) = 0;
  *((_QWORD *)v15 + 6) = 0;
  *((_QWORD *)v15 + 7) = 7;
  *((_WORD *)v15 + 16) = 0;
  *((_DWORD *)v15 + 16) = 0;
  *((_QWORD *)v15 + 9) = 0;
  v15[80] = 0;
  *((_QWORD *)v15 + 11) = 0;
  *((_QWORD *)v15 + 12) = 0;
  *((_QWORD *)v15 + 13) = 0;
  *((_QWORD *)v15 + 14) = 0;
  *((_QWORD *)v15 + 15) = 0;
  *((_QWORD *)v15 + 16) = 0;
  Worker = ClientConnection2::CreateWorker((_DWORD *)v15 + 4, a1 - 16, v14, String);
  v11 = Worker;
  if ( Worker >= 0 )
  {
    *(_QWORD *)&v50 = v15 + 16;
    *((_QWORD *)&v50 + 1) = v15;
    v11 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\clientconnection.cpp",
      (const char *)(unsigned int)Worker,
      v45);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v15)(v15);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(char *))(*(_QWORD *)v15 + 8LL))(v15);
    }
    v15 = (char *)*((_QWORD *)&v50 + 1);
    v16 = (char *)v50;
  }
  std::wstring::~wstring(v70);
  std::wstring::~wstring((char **)v57);
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x95,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)v11,
      v45);
    v19 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v19);
    }
LABEL_18:
    if ( !v15 || _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 2, 0xFFFFFFFF) != 1 )
      goto LABEL_73;
    goto LABEL_20;
  }
  std::wstring::operator=((__int64)&v67, (_QWORD *)(*((_QWORD *)v16 + 9) + 8LL), v18);
  std::wstring::operator=((__int64)&v61, (_QWORD *)(*((_QWORD *)v16 + 9) + 56LL), v22);
  std::wstring::operator=((__int64)&v64, (_QWORD *)(*((_QWORD *)v16 + 9) + 88LL), v23);
  std::wstring::operator=((__int64)&v58, (_QWORD *)(*((_QWORD *)v16 + 13) + 16LL), v24);
  v25 = SRWLock;
  if ( SRWLock )
  {
    LODWORD(SRWLock[1].Ptr) = 0;
    ReleaseSRWLockExclusive(v25);
  }
  *(_OWORD *)v54 = 0;
  v55 = 0;
  v56 = 7;
  LOWORD(v54[0]) = 0;
  v26 = AgentAccountHelpers2::CheckUserConsent_NoLock(&v67, (__int64)&v61, (__int64)&v64, (__int64)&v58, (__int64)v54);
  v11 = v26;
  if ( v26 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)v26,
      v46);
    std::wstring::~wstring((char **)v54);
    goto LABEL_18;
  }
  checked_srwlock::lock_exclusive(v27, &v49);
  v57[0] = 0;
  AgentUser = AgentManager2::AllocateAgentUser(v16, v54, a4, v57);
  v11 = AgentUser;
  if ( AgentUser >= 0 )
  {
    SRWLock = 0;
    v31 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp2,std::shared_ptr<ClientConnection2> &,std::shared_ptr<AgentUser2> &>(
            &SRWLock,
            (__int64)&v50,
            (__int64)v57);
    v11 = v31;
    if ( v31 >= 0 )
    {
      v51 = 0;
      v52 = 0;
      v53[0] = (wchar_t *)SRWLock;
      v48 = 0;
      v35 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::Preview::EnvironmentCreationResult2,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironmentCreationResult_Exp2,enum Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentCreationStatus_Exp2 &,long &,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp2 *>(
              &v48,
              &v52,
              &v51,
              v53);
      v11 = v35;
      if ( v35 >= 0 )
      {
        std::operator+<wchar_t>(v70, v36, *(_QWORD *)&v57[0] + 72LL);
        v53[0] = L"IsolationEnvironment created.";
        v39 = (wchar_t *)v70;
        if ( v70[3] > (char *)7 )
          v39 = (wchar_t *)v70[0];
        v53[1] = v39;
        SecurityLog::WriteLog(v37, (const wchar_t **const)v53, v38);
        v40 = v48;
        v48 = 0;
        *a5 = v40;
        std::wstring::~wstring(v70);
        if ( v48 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
        if ( SRWLock )
          (*((void (__fastcall **)(PSRWLOCK))SRWLock->Ptr + 2))(SRWLock);
        v41 = (volatile signed __int32 *)*((_QWORD *)&v57[0] + 1);
        if ( *((_QWORD *)&v57[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v57[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
            if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
          }
        }
        v42 = v49;
        if ( v49 )
        {
          LODWORD(v49[1].Ptr) = 0;
          ReleaseSRWLockExclusive(v42);
        }
        std::wstring::~wstring((char **)v54);
        v43 = (volatile signed __int32 *)*((_QWORD *)&v50 + 1);
        if ( *((_QWORD *)&v50 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v50 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
            if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
          }
        }
        v11 = 0;
        goto LABEL_73;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD5,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironmentstatics.cpp",
        (const char *)(unsigned int)v35,
        v46);
      if ( v48 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
      if ( SRWLock )
        (*((void (__fastcall **)(PSRWLOCK))SRWLock->Ptr + 2))(SRWLock);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC8,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironmentstatics.cpp",
        (const char *)(unsigned int)v31,
        v46);
      if ( SRWLock )
        (*((void (__fastcall **)(PSRWLOCK))SRWLock->Ptr + 2))(SRWLock);
    }
    v32 = (volatile signed __int32 *)*((_QWORD *)&v57[0] + 1);
    if ( *((_QWORD *)&v57[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v57[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
        if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
      }
    }
    v33 = v49;
    if ( v49 )
    {
      LODWORD(v49[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v33);
    }
    std::wstring::~wstring((char **)v54);
    v34 = (char *)*((_QWORD *)&v50 + 1);
    if ( *((_QWORD *)&v50 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v50 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(char *))v34)(v34);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v34 + 3, 0xFFFFFFFF) == 1 )
        {
          v20 = *(void (__fastcall ***)(_QWORD))v34;
          v21 = v34;
          goto LABEL_22;
        }
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)AgentUser,
      v46);
    v29 = (volatile signed __int32 *)*((_QWORD *)&v57[0] + 1);
    if ( *((_QWORD *)&v57[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v57[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v29)(v29);
        if ( _InterlockedExchangeAdd(v29 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v29 + 8LL))(v29);
      }
    }
    v30 = v49;
    if ( v49 )
    {
      LODWORD(v49[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v30);
    }
    std::wstring::~wstring((char **)v54);
    if ( v15 && _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 2, 0xFFFFFFFF) == 1 )
    {
LABEL_20:
      (**(void (__fastcall ***)(void *))v15)(v15);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v15 + 3, 0xFFFFFFFF) != 1 )
        goto LABEL_73;
      v20 = *(void (__fastcall ***)(_QWORD))v15;
      v21 = v15;
LABEL_22:
      ((void (__fastcall **)(char *))v20)[1](v21);
    }
  }
LABEL_73:
  std::wstring::~wstring((char **)&v58);
  std::wstring::~wstring((char **)&v61);
  std::wstring::~wstring((char **)&v64);
  std::wstring::~wstring((char **)&v67);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180056d90  push    rbp
0x180056d92  push    rbx
0x180056d93  push    rsi
0x180056d94  push    rdi
0x180056d95  push    r12
0x180056d97  push    r13
0x180056d99  push    r14
0x180056d9b  push    r15
0x180056d9d  lea     rbp, [rsp-68h]
0x180056da2  sub     rsp, 168h
0x180056da9  mov     rax, cs:__security_cookie
0x180056db0  xor     rax, rsp
0x180056db3  mov     [rbp+0A0h+var_50], rax
0x180056db7  mov     r13d, r9d
0x180056dba  mov     rsi, r8
0x180056dbd  mov     rbx, rdx
0x180056dc0  mov     rdi, rcx
0x180056dc3  mov     r12, [rbp+0A0h+arg_20]
0x180056dca  lea     rdx, aIsolationenvir_4; "IsolationEnvironment::Create_v3 called."
0x180056dd1  mov     ecx, 4; unsigned __int8
0x180056dd6  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180056ddb  xor     r14d, r14d
0x180056dde  mov     [r12], r14
0x180056de2  xorps   xmm0, xmm0
0x180056de5  movups  [rbp+0A0h+var_90], xmm0
0x180056de9  mov     [rbp+0A0h+var_80], r14
0x180056ded  lea     ecx, [r14+7]
0x180056df1  mov     [rbp+0A0h+var_78], rcx
0x180056df5  mov     word ptr [rbp+0A0h+var_90], r14w
0x180056dfa  movups  [rbp+0A0h+var_B0], xmm0
0x180056dfe  mov     [rbp+0A0h+var_A0], r14
0x180056e02  mov     [rbp+0A0h+var_98], rcx
0x180056e06  mov     word ptr [rbp+0A0h+var_B0], r14w
0x180056e0b  movups  [rbp+0A0h+var_D0], xmm0
0x180056e0f  mov     [rbp+0A0h+var_C0], r14
0x180056e13  mov     [rbp+0A0h+var_B8], rcx
0x180056e17  mov     word ptr [rbp+0A0h+var_D0], r14w
0x180056e1c  movups  [rbp+0A0h+var_F0], xmm0
0x180056e20  mov     [rbp+0A0h+var_E0], r14
0x180056e24  mov     [rbp+0A0h+var_D8], rcx
0x180056e28  mov     word ptr [rbp+0A0h+var_F0], r14w
0x180056e2d  movdqu  [rsp+1A0h+var_158], xmm0
0x180056e33  lea     rdx, [rsp+1A0h+SRWLock]
0x180056e38  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x180056e3d  xor     ecx, ecx
0x180056e3f  call    ?GetIsSupportedResult2@@YA?AW4IsIsolationSupportedResult_Exp2@Preview@IsolationEnvironment@AI@Windows@@_N@Z; GetIsSupportedResult2(bool)
0x180056e44  lea     r15d, [r14+1]
0x180056e48  cmp     eax, r15d
0x180056e4b  jz      short loc_180056E6B
0x180056e4d  mov     rcx, [rsp+1A0h+SRWLock]; SRWLock
0x180056e52  test    rcx, rcx
0x180056e55  jz      short loc_180056E61
0x180056e57  mov     [rcx+8], r14d
0x180056e5b  call    cs:__imp_ReleaseSRWLockExclusive
0x180056e61  mov     ebx, 80070032h
0x180056e66  jmp     loc_18005746C
0x180056e6b  call    ?EnabledChildSessions@IsolationEnvironmentStatics2@Preview@IsolationEnvironment@AI@Windows@@AEAA_NXZ; Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::EnabledChildSessions(void)
0x180056e70  test    al, al
0x180056e72  jnz     short loc_180056E92
0x180056e74  mov     rcx, [rsp+1A0h+SRWLock]; SRWLock
0x180056e79  test    rcx, rcx
0x180056e7c  jz      short loc_180056E88
0x180056e7e  mov     [rcx+8], r14d
0x180056e82  call    cs:__imp_ReleaseSRWLockExclusive
0x180056e88  mov     ebx, 8000FFFFh
0x180056e8d  jmp     loc_18005746C
0x180056e92  mov     rdx, rsi
0x180056e95  lea     rcx, [rbp+0A0h+var_110]
0x180056e99  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x180056e9e  mov     rsi, rax
0x180056ea1  mov     rdx, rbx
0x180056ea4  lea     rcx, [rbp+0A0h+var_70]
0x180056ea8  call    ?GetString@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHSTRING__@@@Z; GetString(HSTRING__ *)
0x180056ead  mov     rbx, rax
0x180056eb0  mov     ecx, 88h; Size
0x180056eb5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180056eba  mov     r14, rax
0x180056ebd  mov     [rax+8], r15d
0x180056ec1  mov     [rax+0Ch], r15d
0x180056ec5  lea     rax, ??_7?$_Ref_count_obj2@VClientConnection2@@@std@@6B@; const std::_Ref_count_obj2<ClientConnection2>::`vftable'
0x180056ecc  mov     [r14], rax
0x180056ecf  lea     r15, [r14+10h]
0x180056ed3  xor     ecx, ecx
0x180056ed5  mov     [r15], cl
0x180056ed8  mov     [r15+8], rcx
0x180056edc  xorps   xmm0, xmm0
0x180056edf  movups  xmmword ptr [r15+10h], xmm0
0x180056ee4  mov     [r15+20h], rcx
0x180056ee8  mov     qword ptr [r15+28h], 7
0x180056ef0  mov     [r15+10h], cx
0x180056ef5  mov     [r15+30h], ecx
0x180056ef9  mov     [r15+38h], rcx
0x180056efd  mov     [r15+40h], cl
0x180056f01  mov     [r15+48h], rcx
0x180056f05  mov     [r15+50h], rcx
0x180056f09  mov     [r15+58h], rcx
0x180056f0d  mov     [r15+60h], rcx
0x180056f11  mov     [r15+68h], rcx
0x180056f15  mov     [r15+70h], rcx
0x180056f19  mov     r9, rsi
0x180056f1c  mov     r8, rbx
0x180056f1f  lea     rdx, [rdi-10h]
0x180056f23  mov     rcx, r15
0x180056f26  call    ?CreateWorker@ClientConnection2@@AEAAJPEAUIUnknown@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; ClientConnection2::CreateWorker(IUnknown *,std::wstring const &,std::wstring const &)
0x180056f2b  mov     ebx, eax
0x180056f2d  or      edi, 0FFFFFFFFh
0x180056f30  xor     esi, esi
0x180056f32  test    eax, eax
0x180056f34  jns     short loc_180056F90
0x180056f36  mov     rcx, [rbp+0A8h]; this
0x180056f3d  mov     r9d, eax; char *
0x180056f40  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180056f47  lea     edx, [rdi+37h]; void *
0x180056f4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056f4f  mov     eax, edi
0x180056f51  lock xadd [r14+8], eax
0x180056f57  add     eax, edi
0x180056f59  jnz     short loc_180056F84
0x180056f5b  mov     rax, [r14]
0x180056f5e  mov     rcx, r14
0x180056f61  mov     rax, [rax]
0x180056f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f69  mov     eax, edi
0x180056f6b  lock xadd [r14+0Ch], eax
0x180056f71  add     eax, edi
0x180056f73  jnz     short loc_180056F84
0x180056f75  mov     rax, [r14]
0x180056f78  mov     rcx, r14
0x180056f7b  mov     rax, [rax+8]
0x180056f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f84  mov     r14, qword ptr [rsp+1A0h+var_158+8]
0x180056f89  mov     r15, qword ptr [rsp+1A0h+var_158]
0x180056f8e  jmp     short loc_180056F9C
0x180056f90  mov     qword ptr [rsp+1A0h+var_158], r15
0x180056f95  mov     qword ptr [rsp+1A0h+var_158+8], r14
0x180056f9a  mov     ebx, esi
0x180056f9c  lea     rcx, [rbp+0A0h+var_70]
0x180056fa0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056fa5  lea     rcx, [rbp+0A0h+var_110]
0x180056fa9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056fae  test    ebx, ebx
0x180056fb0  jns     short loc_18005702B
0x180056fb2  mov     rcx, [rbp+0A8h]; this
0x180056fb9  mov     r9d, ebx; char *
0x180056fbc  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180056fc3  mov     edx, 95h; void *
0x180056fc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056fcd  mov     rcx, [rsp+1A0h+SRWLock]; SRWLock
0x180056fd2  test    rcx, rcx
0x180056fd5  jz      short loc_180056FE0
0x180056fd7  mov     [rcx+8], esi
0x180056fda  call    cs:__imp_ReleaseSRWLockExclusive
0x180056fe0  test    r14, r14
0x180056fe3  jz      loc_18005746C
0x180056fe9  mov     eax, edi
0x180056feb  lock xadd [r14+8], eax
0x180056ff1  add     eax, edi
0x180056ff3  jnz     loc_18005746C
0x180056ff9  mov     rax, [r14]
0x180056ffc  mov     rcx, r14
0x180056fff  mov     rax, [rax]
0x180057002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057007  mov     eax, edi
0x180057009  lock xadd [r14+0Ch], eax
0x18005700f  add     eax, edi
0x180057011  jnz     loc_18005746C
0x180057017  mov     rax, [r14]
0x18005701a  mov     rcx, r14
0x18005701d  mov     rax, [rax+8]
0x180057021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057026  jmp     loc_18005746C
0x18005702b  mov     rdx, [r15+48h]
0x18005702f  add     rdx, 8
0x180057033  lea     rcx, [rbp+0A0h+var_90]
0x180057037  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005703c  mov     rdx, [r15+48h]
0x180057040  add     rdx, 38h ; '8'
0x180057044  lea     rcx, [rbp+0A0h+var_D0]
0x180057048  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005704d  mov     rdx, [r15+48h]
0x180057051  add     rdx, 58h ; 'X'
0x180057055  lea     rcx, [rbp+0A0h+var_B0]
0x180057059  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005705e  mov     rdx, [r15+68h]
0x180057062  add     rdx, 10h
0x180057066  lea     rcx, [rbp+0A0h+var_F0]
0x18005706a  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005706f  mov     rcx, [rsp+1A0h+SRWLock]; SRWLock
0x180057074  test    rcx, rcx
0x180057077  jz      short loc_180057082
0x180057079  mov     [rcx+8], esi
0x18005707c  call    cs:__imp_ReleaseSRWLockExclusive
0x180057082  xorps   xmm0, xmm0
0x180057085  movups  xmmword ptr [rsp+1A0h+var_130], xmm0
0x18005708a  mov     [rbp+0A0h+var_120], rsi
0x18005708e  mov     [rbp+0A0h+var_118], 7
0x180057096  mov     word ptr [rsp+1A0h+var_130], si
0x18005709b  lea     rax, [rsp+1A0h+var_130]
0x1800570a0  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x1800570a5  lea     r9, [rbp+0A0h+var_F0]
0x1800570a9  lea     r8, [rbp+0A0h+var_B0]
0x1800570ad  lea     rdx, [rbp+0A0h+var_D0]
0x1800570b1  lea     rcx, [rbp+0A0h+var_90]
0x1800570b5  call    ?CheckUserConsent_NoLock@AgentAccountHelpers2@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@000AEAV23@@Z; AgentAccountHelpers2::CheckUserConsent_NoLock(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring &)
0x1800570ba  mov     ebx, eax
0x1800570bc  test    eax, eax
0x1800570be  jns     short loc_1800570EA
0x1800570c0  mov     rcx, [rbp+0A8h]; this
0x1800570c7  mov     r9d, eax; char *
0x1800570ca  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800570d1  mov     edx, 0B0h; void *
0x1800570d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800570db  lea     rcx, [rsp+1A0h+var_130]
0x1800570e0  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800570e5  jmp     loc_180056FE0
0x1800570ea  lea     rdx, [rsp+1A0h+var_160]
0x1800570ef  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x1800570f4  xorps   xmm0, xmm0
0x1800570f7  movdqu  [rbp+0A0h+var_110], xmm0
0x1800570fc  lea     r9, [rbp+0A0h+var_110]
0x180057100  mov     r8d, r13d
0x180057103  lea     rdx, [rsp+1A0h+var_130]
0x180057108  mov     rcx, r15
0x18005710b  call    ?AllocateAgentUser@AgentManager2@@SAJPEAVClientConnection2@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4IsolationConfigurationId_Exp2@Preview@IsolationEnvironment@AI@Windows@@AEAV?$shared_ptr@VAgentUser2@@@4@@Z; AgentManager2::AllocateAgentUser(ClientConnection2 *,std::wstring const &,Windows::AI::IsolationEnvironment::Preview::IsolationConfigurationId_Exp2,std::shared_ptr<AgentUser2> &)
0x180057110  mov     ebx, eax
0x180057112  test    eax, eax
0x180057114  jns     loc_1800571D0
0x18005711a  mov     rcx, [rbp+0A8h]; this
0x180057121  mov     r9d, eax; char *
0x180057124  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005712b  mov     edx, 0BEh; void *
0x180057130  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057135  mov     rdi, qword ptr [rbp+0A0h+var_110+8]
0x180057139  or      r15d, 0FFFFFFFFh
0x18005713d  test    rdi, rdi
0x180057140  jz      short loc_180057179
0x180057142  mov     eax, r15d
0x180057145  lock xadd [rdi+8], eax
0x18005714a  add     eax, r15d
0x18005714d  jnz     short loc_180057179
0x18005714f  mov     rax, [rdi]
0x180057152  mov     rcx, rdi
0x180057155  mov     rax, [rax]
0x180057158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005715d  mov     eax, r15d
0x180057160  lock xadd [rdi+0Ch], eax
0x180057165  add     eax, r15d
0x180057168  jnz     short loc_180057179
0x18005716a  mov     rax, [rdi]
0x18005716d  mov     rcx, rdi
0x180057170  mov     rax, [rax+8]
0x180057174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057179  mov     rcx, [rsp+1A0h+var_160]; SRWLock
0x18005717e  test    rcx, rcx
0x180057181  jz      short loc_18005718C
0x180057183  mov     [rcx+8], esi
0x180057186  call    cs:__imp_ReleaseSRWLockExclusive
0x18005718c  lea     rcx, [rsp+1A0h+var_130]
0x180057191  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180057196  test    r14, r14
0x180057199  jz      loc_18005746C
0x18005719f  mov     eax, r15d
0x1800571a2  lock xadd [r14+8], eax
0x1800571a8  add     eax, r15d
0x1800571ab  jnz     loc_18005746C
0x1800571b1  mov     rax, [r14]
0x1800571b4  mov     rcx, r14
0x1800571b7  mov     rax, [rax]
0x1800571ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800571bf  mov     eax, r15d
0x1800571c2  lock xadd [r14+0Ch], eax
0x1800571c8  add     eax, r15d
0x1800571cb  jmp     loc_180057011
0x1800571d0  mov     [rsp+1A0h+SRWLock], rsi
0x1800571d5  lea     r8, [rbp+0A0h+var_110]
0x1800571d9  lea     rdx, [rsp+1A0h+var_158]
0x1800571de  lea     rcx, [rsp+1A0h+SRWLock]
0x1800571e3  call    ??$MakeAndInitialize@VIsolationEnvironment2@Preview@IsolationEnvironment@AI@Windows@@UIIsolationEnvironment_Exp2@2345@AEAV?$shared_ptr@VClientConnection2@@@std@@AEAV?$shared_ptr@VAgentUser2@@@8@@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationEnvironment_Exp2@Preview@IsolationEnvironment@AI@Windows@@AEAV?$shared_ptr@VClientConnection2@@@std@@AEAV?$shared_ptr@VAgentUser2@@@9@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2,Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp2,std::shared_ptr<ClientConnection2> &,std::shared_ptr<AgentUser2> &>(Windows::AI::IsolationEnvironment::Preview::IIsolationEnvironment_Exp2 * *,std::shared_ptr<ClientConnection2> &,std::shared_ptr<AgentUser2> &)
0x1800571e8  mov     ebx, eax
0x1800571ea  test    eax, eax
0x1800571ec  jns     loc_1800572CF
0x1800571f2  mov     rcx, [rbp+0A8h]; this
0x1800571f9  mov     r9d, eax; char *
0x1800571fc  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180057203  mov     edx, 0C8h; void *
0x180057208  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005720d  nop
0x18005720e  mov     rcx, [rsp+1A0h+SRWLock]
0x180057213  test    rcx, rcx
0x180057216  jz      short loc_180057225
0x180057218  mov     rax, [rcx]
0x18005721b  mov     rax, [rax+10h]
0x18005721f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057224  nop
0x180057225  or      r15d, 0FFFFFFFFh
0x180057229  mov     rdi, qword ptr [rbp+0A0h+var_110+8]
0x18005722d  test    rdi, rdi
0x180057230  jz      short loc_180057269
0x180057232  mov     eax, r15d
0x180057235  lock xadd [rdi+8], eax
  ... truncated ...
```
