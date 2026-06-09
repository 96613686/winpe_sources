# Windows::AI::IsolationEnvironment::IsolationEnvironment::get_AgentAccountName(HSTRING__ * *)

- ea: `0x18004b4a0`
- end: `0x18004b58b`
- name: `?get_AgentAccountName@IsolationEnvironment@1AI@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::IsolationEnvironment *__hidden this, HSTRING *string)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000a464`
- `0x180013230`
- `0x18001355c`
- `0x180032e60`
- `0x180048edc`
- `0x18004b4a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004b52f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004b573`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004b52f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004b573`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b552`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b552`

## string_xrefs

- `0x18004b4d8`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004b512`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`

## pseudocode

```c
__int64 __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironment::get_AgentAccountName(
        Windows::AI::IsolationEnvironment::IsolationEnvironment *this,
        HSTRING *string)
{
  __int64 v4; // rcx
  int v5; // ebx
  __int64 v7; // rdx
  RTL_SRWLOCK *v8; // rcx
  const WCHAR *v9; // rcx
  RTL_SRWLOCK *v10; // rcx
  int v11; // [rsp+20h] [rbp-18h]
  const char *v12; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PSRWLOCK SRWLock; // [rsp+50h] [rbp+18h] BYREF

  v5 = CheckCallingProcessCohort(0, 0);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xA8,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)(unsigned int)v5,
      (int)"Calling user is not in a supported cohort",
      v12);
    return (unsigned int)v5;
  }
  checked_srwlock::lock_shared(v4, &SRWLock);
  v5 = Windows::AI::IsolationEnvironment::IsolationEnvironment::CheckEntry(this);
  if ( v5 < 0 )
  {
    v7 = 172;
    goto LABEL_6;
  }
  v9 = (const WCHAR *)(*((_QWORD *)this + 6) + 144LL);
  if ( *(_QWORD *)(*((_QWORD *)this + 6) + 168LL) > 7u )
    v9 = *(const WCHAR **)v9;
  v5 = WindowsCreateString(v9, *(_DWORD *)(*((_QWORD *)this + 6) + 160LL), string);
  if ( v5 < 0 )
  {
    v7 = 175;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)(unsigned int)v5,
      v11);
    v8 = SRWLock;
    if ( SRWLock )
    {
      _InterlockedDecrement((volatile signed __int32 *)&SRWLock[1].Ptr + 1);
      ReleaseSRWLockShared(v8);
    }
    return (unsigned int)v5;
  }
  v10 = SRWLock;
  if ( SRWLock )
  {
    _InterlockedDecrement((volatile signed __int32 *)&SRWLock[1].Ptr + 1);
    ReleaseSRWLockShared(v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18004b4a0  mov     [rsp+arg_0], rbx
0x18004b4a5  mov     [rsp+arg_8], rsi
0x18004b4aa  push    rdi
0x18004b4ab  sub     rsp, 30h
0x18004b4af  mov     rsi, rdx
0x18004b4b2  mov     rdi, rcx
0x18004b4b5  xor     edx, edx; enum Windows::AI::IsolationEnvironment::IsolationUserCohortKind *
0x18004b4b7  xor     ecx, ecx; bool
0x18004b4b9  call    ?CheckCallingProcessCohort@@YAJ_NPEAW4IsolationUserCohortKind@IsolationEnvironment@AI@Windows@@@Z; CheckCallingProcessCohort(bool,Windows::AI::IsolationEnvironment::IsolationUserCohortKind *)
0x18004b4be  mov     ebx, eax
0x18004b4c0  test    eax, eax
0x18004b4c2  jns     short loc_18004B4F0
0x18004b4c4  mov     rcx, [rsp+38h]; this
0x18004b4c9  lea     rax, aCallingUserIsN; "Calling user is not in a supported coho"...
0x18004b4d0  mov     r9d, ebx; char *
0x18004b4d3  mov     qword ptr [rsp+38h+var_18], rax; int
0x18004b4d8  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004b4df  mov     edx, 0A8h; void *
0x18004b4e4  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004b4e9  mov     eax, ebx
0x18004b4eb  jmp     loc_18004B57B
0x18004b4f0  lea     rdx, [rsp+38h+SRWLock]
0x18004b4f5  call    ?lock_shared@checked_srwlock@@QEAA?AV?$holder@USharedTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_shared(void)
0x18004b4fa  mov     rcx, rdi; this
0x18004b4fd  call    ?CheckEntry@IsolationEnvironment@1AI@Windows@@AEBAJXZ; Windows::AI::IsolationEnvironment::IsolationEnvironment::CheckEntry(void)
0x18004b502  mov     ebx, eax
0x18004b504  test    eax, eax
0x18004b506  jns     short loc_18004B537
0x18004b508  mov     edx, 0ACh; void *
0x18004b50d  mov     rcx, [rsp+38h]; this
0x18004b512  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004b519  mov     r9d, ebx; char *
0x18004b51c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b521  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x18004b526  test    rcx, rcx
0x18004b529  jz      short loc_18004B4E9
0x18004b52b  lock dec dword ptr [rcx+0Ch]
0x18004b52f  call    cs:__imp_ReleaseSRWLockShared
0x18004b535  jmp     short loc_18004B4E9
0x18004b537  mov     rcx, [rdi+30h]
0x18004b53b  add     rcx, 90h
0x18004b542  cmp     qword ptr [rcx+18h], 7
0x18004b547  mov     edx, [rcx+10h]; length
0x18004b54a  jbe     short loc_18004B54F
0x18004b54c  mov     rcx, [rcx]; sourceString
0x18004b54f  mov     r8, rsi; string
0x18004b552  call    cs:__imp_WindowsCreateString
0x18004b558  mov     ebx, eax
0x18004b55a  test    eax, eax
0x18004b55c  jns     short loc_18004B565
0x18004b55e  mov     edx, 0AFh
0x18004b563  jmp     short loc_18004B50D
0x18004b565  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x18004b56a  test    rcx, rcx
0x18004b56d  jz      short loc_18004B579
0x18004b56f  lock dec dword ptr [rcx+0Ch]
0x18004b573  call    cs:__imp_ReleaseSRWLockShared
0x18004b579  xor     eax, eax
0x18004b57b  mov     rbx, [rsp+38h+arg_0]
0x18004b580  mov     rsi, [rsp+38h+arg_8]
0x18004b585  add     rsp, 30h
0x18004b589  pop     rdi
0x18004b58a  retn
```
