# Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::QueryAppIdentity(Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult * *)

- ea: `0x180028120`
- end: `0x180028338`
- name: `?QueryAppIdentity@IsolationEnvironmentStatics@IsolationEnvironment@AI@Windows@@UEAAJPEAPEAUIIsolationAppIdentityQueryResult@234@@Z`
- size: `536`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics *__hidden this, struct Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000a464`
- `0x18000fda0`
- `0x18000fedc`
- `0x180013230`
- `0x18001355c`
- `0x180028120`
- `0x180032e60`
- `0x180039b3c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028231`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028320`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028231`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028320`

## string_xrefs

- `0x180028154`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x1800281bd`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`
- `0x18002826c`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironmentstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics::QueryAppIdentity(
        Windows::AI::IsolationEnvironment::IsolationEnvironmentStatics *this,
        struct Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult **a2)
{
  __int64 v3; // rcx
  int v4; // ebx
  int v6; // eax
  __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // esi
  volatile signed __int32 *v10; // rdi
  RTL_SRWLOCK *v11; // rcx
  int v12; // eax
  struct Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult *v13; // rax
  volatile signed __int32 *v14; // rdi
  RTL_SRWLOCK *v15; // rcx
  int v16; // [rsp+20h] [rbp-40h]
  const char *v17; // [rsp+28h] [rbp-38h]
  struct Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult *v18; // [rsp+30h] [rbp-30h] BYREF
  PSRWLOCK SRWLock; // [rsp+38h] [rbp-28h] BYREF
  __int64 v20; // [rsp+40h] [rbp-20h] BYREF
  __int128 v21; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  int v23; // [rsp+90h] [rbp+30h] BYREF
  __int64 v24; // [rsp+98h] [rbp+38h] BYREF

  v4 = CheckCallingProcessCohort(0, 0);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xEE,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)v4,
      (int)"Calling user is not in a supported cohort",
      v17);
    return (unsigned int)v4;
  }
  checked_srwlock::lock_shared(v3, &SRWLock);
  v21 = 0;
  v23 = 1;
  v6 = AppIdentity::QueryAppIdentity((__int64)&v21, &v23);
  v7 = 0;
  v24 = 0;
  if ( v6 >= 0 )
  {
    v8 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::IsolationAppIdentity,Windows::AI::IsolationEnvironment::IIsolationAppIdentity,std::shared_ptr<AppIdentity> &>(
           &v24,
           &v21);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x100,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
        (const char *)(unsigned int)v8,
        v16);
      if ( v24 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
LABEL_7:
      v10 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
      if ( *((_QWORD *)&v21 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
          if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        }
      }
      v11 = SRWLock;
      if ( SRWLock )
      {
        _InterlockedAdd((volatile signed __int32 *)&SRWLock[1].Ptr + 1, 0xFFFFFFFF);
        ReleaseSRWLockShared(v11);
      }
      return v9;
    }
    v7 = v24;
  }
  v20 = v7;
  v18 = 0;
  v12 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::IsolationAppIdentityQueryResult,Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult,Windows::AI::IsolationEnvironment::IIsolationAppIdentity *,enum Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &>(
          &v18,
          &v20,
          &v23);
  v9 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x107,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironmentstatics.cpp",
      (const char *)(unsigned int)v12,
      v16);
    if ( v18 )
      (*(void (__fastcall **)(struct Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult *))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v24 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    goto LABEL_7;
  }
  v13 = v18;
  v18 = 0;
  *a2 = v13;
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v14 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
  if ( *((_QWORD *)&v21 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  v15 = SRWLock;
  if ( SRWLock )
  {
    _InterlockedAdd((volatile signed __int32 *)&SRWLock[1].Ptr + 1, 0xFFFFFFFF);
    ReleaseSRWLockShared(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x180028120  mov     [rsp-18h+arg_0], rbx
0x180028125  push    rbp
0x180028126  push    rsi
0x180028127  push    rdi
0x180028128  mov     rbp, rsp
0x18002812b  sub     rsp, 60h
0x18002812f  mov     rdi, rdx
0x180028132  xor     edx, edx; enum Windows::AI::IsolationEnvironment::IsolationUserCohortKind *
0x180028134  xor     ecx, ecx; bool
0x180028136  call    ?CheckCallingProcessCohort@@YAJ_NPEAW4IsolationUserCohortKind@IsolationEnvironment@AI@Windows@@@Z; CheckCallingProcessCohort(bool,Windows::AI::IsolationEnvironment::IsolationUserCohortKind *)
0x18002813b  mov     ebx, eax
0x18002813d  test    eax, eax
0x18002813f  jns     short loc_18002816C
0x180028141  mov     rcx, [rbp+18h]; this
0x180028145  lea     rax, aCallingUserIsN; "Calling user is not in a supported coho"...
0x18002814c  mov     qword ptr [rsp+60h+var_40], rax; int
0x180028151  mov     r9d, ebx; char *
0x180028154  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18002815b  mov     edx, 0EEh; void *
0x180028160  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180028165  mov     eax, ebx
0x180028167  jmp     loc_180028328
0x18002816c  lea     rdx, [rbp+SRWLock]
0x180028170  call    ?lock_shared@checked_srwlock@@QEAA?AV?$holder@USharedTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_shared(void)
0x180028175  xorps   xmm0, xmm0
0x180028178  movdqu  [rbp+var_18], xmm0
0x18002817d  mov     [rbp+arg_10], 1
0x180028184  lea     rdx, [rbp+arg_10]
0x180028188  lea     rcx, [rbp+var_18]
0x18002818c  call    ?QueryAppIdentity@AppIdentity@@SAJAEAV?$shared_ptr@VAppIdentity@@@std@@PEAW4IsolationQueryAppIdentityStatus@IsolationEnvironment@AI@Windows@@@Z; AppIdentity::QueryAppIdentity(std::shared_ptr<AppIdentity> &,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus *)
0x180028191  xor     ecx, ecx
0x180028193  mov     [rbp+arg_18], rcx
0x180028197  test    eax, eax
0x180028199  js      loc_180028242
0x18002819f  lea     rdx, [rbp+var_18]
0x1800281a3  lea     rcx, [rbp+arg_18]
0x1800281a7  call    ??$MakeAndInitialize@VIsolationAppIdentity@IsolationEnvironment@AI@Windows@@UIIsolationAppIdentity@234@AEAV?$shared_ptr@VAppIdentity@@@std@@@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationAppIdentity@IsolationEnvironment@AI@Windows@@AEAV?$shared_ptr@VAppIdentity@@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::IsolationAppIdentity,Windows::AI::IsolationEnvironment::IIsolationAppIdentity,std::shared_ptr<AppIdentity> &>(Windows::AI::IsolationEnvironment::IIsolationAppIdentity * *,std::shared_ptr<AppIdentity> &)
0x1800281ac  mov     esi, eax
0x1800281ae  test    eax, eax
0x1800281b0  jns     loc_18002823E
0x1800281b6  mov     rcx, [rbp+18h]; this
0x1800281ba  mov     r9d, eax; char *
0x1800281bd  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800281c4  mov     edx, 100h; void *
0x1800281c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800281ce  nop
0x1800281cf  mov     rcx, [rbp+arg_18]
0x1800281d3  test    rcx, rcx
0x1800281d6  jz      short loc_1800281E5
0x1800281d8  mov     rax, [rcx]
0x1800281db  mov     rax, [rax+10h]
0x1800281df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281e4  nop
0x1800281e5  or      ebx, 0FFFFFFFFh
0x1800281e8  mov     rdi, qword ptr [rbp+var_18+8]
0x1800281ec  test    rdi, rdi
0x1800281ef  jz      short loc_180028224
0x1800281f1  mov     eax, ebx
0x1800281f3  lock xadd [rdi+8], eax
0x1800281f8  add     eax, ebx
0x1800281fa  jnz     short loc_180028224
0x1800281fc  mov     rax, [rdi]
0x1800281ff  mov     rcx, rdi
0x180028202  mov     rax, [rax]
0x180028205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002820a  mov     eax, ebx
0x18002820c  lock xadd [rdi+0Ch], eax
0x180028211  add     eax, ebx
0x180028213  jnz     short loc_180028224
0x180028215  mov     rax, [rdi]
0x180028218  mov     rcx, rdi
0x18002821b  mov     rax, [rax+8]
0x18002821f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028224  mov     rcx, [rbp+SRWLock]; SRWLock
0x180028228  test    rcx, rcx
0x18002822b  jz      short loc_180028237
0x18002822d  lock add [rcx+0Ch], ebx
0x180028231  call    cs:__imp_ReleaseSRWLockShared
0x180028237  mov     eax, esi
0x180028239  jmp     loc_180028328
0x18002823e  mov     rcx, [rbp+arg_18]
0x180028242  mov     [rbp+var_20], rcx
0x180028246  mov     [rbp+var_30], 0
0x18002824e  lea     r8, [rbp+arg_10]
0x180028252  lea     rdx, [rbp+var_20]
0x180028256  lea     rcx, [rbp+var_30]
0x18002825a  call    ??$MakeAndInitialize@VIsolationAppIdentityQueryResult@IsolationEnvironment@AI@Windows@@UIIsolationAppIdentityQueryResult@234@PEAUIIsolationAppIdentity@234@AEAW4IsolationQueryAppIdentityStatus@234@@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationAppIdentityQueryResult@IsolationEnvironment@AI@Windows@@$$QEAPEAUIIsolationAppIdentity@456@AEAW4IsolationQueryAppIdentityStatus@456@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::IsolationAppIdentityQueryResult,Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult,Windows::AI::IsolationEnvironment::IIsolationAppIdentity *,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &>(Windows::AI::IsolationEnvironment::IIsolationAppIdentityQueryResult * *,Windows::AI::IsolationEnvironment::IIsolationAppIdentity * &&,Windows::AI::IsolationEnvironment::IsolationQueryAppIdentityStatus &)
0x18002825f  mov     esi, eax
0x180028261  test    eax, eax
0x180028263  jns     short loc_1800282AF
0x180028265  mov     rcx, [rbp+18h]; this
0x180028269  mov     r9d, eax; char *
0x18002826c  lea     r8, aOnecoreuapWind_18; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180028273  mov     edx, 107h; void *
0x180028278  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002827d  nop
0x18002827e  mov     rcx, [rbp+var_30]
0x180028282  test    rcx, rcx
0x180028285  jz      short loc_180028294
0x180028287  mov     rax, [rcx]
0x18002828a  mov     rax, [rax+10h]
0x18002828e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028293  nop
0x180028294  mov     rcx, [rbp+arg_18]
0x180028298  test    rcx, rcx
0x18002829b  jz      short loc_1800282AA
0x18002829d  mov     rax, [rcx]
0x1800282a0  mov     rax, [rax+10h]
0x1800282a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282a9  nop
0x1800282aa  jmp     loc_1800281E5
0x1800282af  mov     rax, [rbp+var_30]
0x1800282b3  mov     [rbp+var_30], 0
0x1800282bb  mov     [rdi], rax
0x1800282be  mov     rcx, [rbp+arg_18]
0x1800282c2  test    rcx, rcx
0x1800282c5  jz      short loc_1800282D4
0x1800282c7  mov     rax, [rcx]
0x1800282ca  mov     rax, [rax+10h]
0x1800282ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282d3  nop
0x1800282d4  or      ebx, 0FFFFFFFFh
0x1800282d7  mov     rdi, qword ptr [rbp+var_18+8]
0x1800282db  test    rdi, rdi
0x1800282de  jz      short loc_180028313
0x1800282e0  mov     eax, ebx
0x1800282e2  lock xadd [rdi+8], eax
0x1800282e7  add     eax, ebx
0x1800282e9  jnz     short loc_180028313
0x1800282eb  mov     rax, [rdi]
0x1800282ee  mov     rcx, rdi
0x1800282f1  mov     rax, [rax]
0x1800282f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800282f9  mov     eax, ebx
0x1800282fb  lock xadd [rdi+0Ch], eax
0x180028300  add     eax, ebx
0x180028302  jnz     short loc_180028313
0x180028304  mov     rax, [rdi]
0x180028307  mov     rcx, rdi
0x18002830a  mov     rax, [rax+8]
0x18002830e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028313  mov     rcx, [rbp+SRWLock]; SRWLock
0x180028317  test    rcx, rcx
0x18002831a  jz      short loc_180028326
0x18002831c  lock add [rcx+0Ch], ebx
0x180028320  call    cs:__imp_ReleaseSRWLockShared
0x180028326  xor     eax, eax
0x180028328  mov     rbx, [rsp+60h+arg_0]
0x180028330  add     rsp, 60h
0x180028334  pop     rdi
0x180028335  pop     rsi
0x180028336  pop     rbp
0x180028337  retn
```
