# Windows::AI::IsolationEnvironment::IsolationEnvironment::get_SharingGroupSid(HSTRING__ * *)

- ea: `0x18004b5c0`
- end: `0x18004b6ab`
- name: `?get_SharingGroupSid@IsolationEnvironment@1AI@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::IsolationEnvironment *__hidden this, HSTRING *string)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a464`
- `0x180013230`
- `0x18001355c`
- `0x180032e60`
- `0x180048edc`
- `0x18004b5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004b64f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004b693`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004b64f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18004b693`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18004b672`

## string_xrefs

- `0x18004b5f8`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004b632`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`

## pseudocode

```c
__int64 __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironment::get_SharingGroupSid(
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
      (void *)0x97,
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
    v7 = 155;
    goto LABEL_6;
  }
  v9 = (const WCHAR *)(*((_QWORD *)this + 6) + 208LL);
  if ( *(_QWORD *)(*((_QWORD *)this + 6) + 232LL) > 7u )
    v9 = *(const WCHAR **)v9;
  v5 = WindowsCreateString(v9, *(_DWORD *)(*((_QWORD *)this + 6) + 224LL), string);
  if ( v5 < 0 )
  {
    v7 = 158;
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
0x18004b5c0  mov     [rsp+arg_0], rbx
0x18004b5c5  mov     [rsp+arg_8], rsi
0x18004b5ca  push    rdi
0x18004b5cb  sub     rsp, 30h
0x18004b5cf  mov     rsi, rdx
0x18004b5d2  mov     rdi, rcx
0x18004b5d5  xor     edx, edx; enum Windows::AI::IsolationEnvironment::IsolationUserCohortKind *
0x18004b5d7  xor     ecx, ecx; bool
0x18004b5d9  call    ?CheckCallingProcessCohort@@YAJ_NPEAW4IsolationUserCohortKind@IsolationEnvironment@AI@Windows@@@Z; CheckCallingProcessCohort(bool,Windows::AI::IsolationEnvironment::IsolationUserCohortKind *)
0x18004b5de  mov     ebx, eax
0x18004b5e0  test    eax, eax
0x18004b5e2  jns     short loc_18004B610
0x18004b5e4  mov     rcx, [rsp+38h]; this
0x18004b5e9  lea     rax, aCallingUserIsN; "Calling user is not in a supported coho"...
0x18004b5f0  mov     r9d, ebx; char *
0x18004b5f3  mov     qword ptr [rsp+38h+var_18], rax; int
0x18004b5f8  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004b5ff  mov     edx, 97h; void *
0x18004b604  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004b609  mov     eax, ebx
0x18004b60b  jmp     loc_18004B69B
0x18004b610  lea     rdx, [rsp+38h+SRWLock]
0x18004b615  call    ?lock_shared@checked_srwlock@@QEAA?AV?$holder@USharedTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_shared(void)
0x18004b61a  mov     rcx, rdi; this
0x18004b61d  call    ?CheckEntry@IsolationEnvironment@1AI@Windows@@AEBAJXZ; Windows::AI::IsolationEnvironment::IsolationEnvironment::CheckEntry(void)
0x18004b622  mov     ebx, eax
0x18004b624  test    eax, eax
0x18004b626  jns     short loc_18004B657
0x18004b628  mov     edx, 9Bh; void *
0x18004b62d  mov     rcx, [rsp+38h]; this
0x18004b632  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004b639  mov     r9d, ebx; char *
0x18004b63c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b641  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x18004b646  test    rcx, rcx
0x18004b649  jz      short loc_18004B609
0x18004b64b  lock dec dword ptr [rcx+0Ch]
0x18004b64f  call    cs:__imp_ReleaseSRWLockShared
0x18004b655  jmp     short loc_18004B609
0x18004b657  mov     rcx, [rdi+30h]
0x18004b65b  add     rcx, 0D0h
0x18004b662  cmp     qword ptr [rcx+18h], 7
0x18004b667  mov     edx, [rcx+10h]; length
0x18004b66a  jbe     short loc_18004B66F
0x18004b66c  mov     rcx, [rcx]; sourceString
0x18004b66f  mov     r8, rsi; string
0x18004b672  call    cs:__imp_WindowsCreateString
0x18004b678  mov     ebx, eax
0x18004b67a  test    eax, eax
0x18004b67c  jns     short loc_18004B685
0x18004b67e  mov     edx, 9Eh
0x18004b683  jmp     short loc_18004B62D
0x18004b685  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x18004b68a  test    rcx, rcx
0x18004b68d  jz      short loc_18004B699
0x18004b68f  lock dec dword ptr [rcx+0Ch]
0x18004b693  call    cs:__imp_ReleaseSRWLockShared
0x18004b699  xor     eax, eax
0x18004b69b  mov     rbx, [rsp+38h+arg_0]
0x18004b6a0  mov     rsi, [rsp+38h+arg_8]
0x18004b6a5  add     rsp, 30h
0x18004b6a9  pop     rdi
0x18004b6aa  retn
```
