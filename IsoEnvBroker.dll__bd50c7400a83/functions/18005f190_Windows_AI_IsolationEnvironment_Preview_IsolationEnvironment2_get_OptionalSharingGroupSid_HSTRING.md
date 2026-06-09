# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::get_OptionalSharingGroupSid(HSTRING__ * *)

- ea: `0x18005f190`
- end: `0x18005f23a`
- name: `?get_OptionalSharingGroupSid@IsolationEnvironment2@Preview@IsolationEnvironment@AI@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `170`
- prototype: `int(Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2 *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a464`
- `0x18001355c`
- `0x180034d48`
- `0x18005f190`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005f1df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005f224`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005f1df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18005f224`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005f20c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005f20c`

## string_xrefs

- `0x18005f1b8`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironment.cpp`

## pseudocode

```c
__int64 __fastcall Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::get_OptionalSharingGroupSid(
        Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2 *this,
        HSTRING *a2)
{
  unsigned int String; // ebx
  RTL_SRWLOCK *v5; // rcx
  __int64 v7; // rcx
  __int64 *v8; // rcx
  UINT32 v9; // edx
  RTL_SRWLOCK *v10; // rcx
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  PSRWLOCK SRWLock; // [rsp+40h] [rbp+18h] BYREF

  checked_srwlock::lock_shared(this, &SRWLock);
  if ( !ProblematicAdminCheck() )
  {
    String = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10C,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironment.cpp",
      (const char *)0x80070005LL,
      v11);
LABEL_3:
    v5 = SRWLock;
    if ( SRWLock )
    {
      _InterlockedDecrement((volatile signed __int32 *)&SRWLock[1].Ptr + 1);
      ReleaseSRWLockShared(v5);
    }
    return String;
  }
  v7 = *((_QWORD *)this + 24);
  if ( v7 )
  {
    v8 = (__int64 *)(v7 + 200);
    v9 = *((_DWORD *)v8 + 4);
    if ( (unsigned __int64)v8[3] > 7 )
      v8 = (__int64 *)*v8;
    String = WindowsCreateString((PCNZWCH)v8, v9, a2);
    goto LABEL_3;
  }
  v10 = SRWLock;
  if ( SRWLock )
  {
    _InterlockedDecrement((volatile signed __int32 *)&SRWLock[1].Ptr + 1);
    ReleaseSRWLockShared(v10);
  }
  return 2147500033LL;
}

```

## disassembly

```asm
0x18005f190  mov     [rsp+arg_0], rbx
0x18005f195  push    rdi; int
0x18005f196  sub     rsp, 20h
0x18005f19a  mov     rdi, rdx
0x18005f19d  mov     rbx, rcx
0x18005f1a0  lea     rdx, [rsp+28h+SRWLock]
0x18005f1a5  call    ?lock_shared@checked_srwlock@@QEAA?AV?$holder@USharedTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_shared(void)
0x18005f1aa  call    _ProblematicAdminCheck
0x18005f1af  test    al, al
0x18005f1b1  jnz     short loc_18005F1E9
0x18005f1b3  mov     rcx, [rsp+28h]; this
0x18005f1b8  lea     r8, aOnecoreuapWind_19; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005f1bf  mov     ebx, 80070005h
0x18005f1c4  mov     edx, 10Ch; void *
0x18005f1c9  mov     r9d, ebx; char *
0x18005f1cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f1d1  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x18005f1d6  test    rcx, rcx
0x18005f1d9  jz      short loc_18005F1E5
0x18005f1db  lock dec dword ptr [rcx+0Ch]
0x18005f1df  call    cs:__imp_ReleaseSRWLockShared
0x18005f1e5  mov     eax, ebx
0x18005f1e7  jmp     short loc_18005F22F
0x18005f1e9  mov     rcx, [rbx+0C0h]
0x18005f1f0  test    rcx, rcx
0x18005f1f3  jz      short loc_18005F216
0x18005f1f5  add     rcx, 0C8h
0x18005f1fc  cmp     qword ptr [rcx+18h], 7
0x18005f201  mov     edx, [rcx+10h]; length
0x18005f204  jbe     short loc_18005F209
0x18005f206  mov     rcx, [rcx]; sourceString
0x18005f209  mov     r8, rdi; string
0x18005f20c  call    cs:__imp_WindowsCreateString
0x18005f212  mov     ebx, eax
0x18005f214  jmp     short loc_18005F1D1
0x18005f216  mov     rcx, [rsp+28h+SRWLock]; SRWLock
0x18005f21b  test    rcx, rcx
0x18005f21e  jz      short loc_18005F22A
0x18005f220  lock dec dword ptr [rcx+0Ch]
0x18005f224  call    cs:__imp_ReleaseSRWLockShared
0x18005f22a  mov     eax, 80004001h
0x18005f22f  mov     rbx, [rsp+28h+arg_0]
0x18005f234  add     rsp, 20h
0x18005f238  pop     rdi
0x18005f239  retn
```
