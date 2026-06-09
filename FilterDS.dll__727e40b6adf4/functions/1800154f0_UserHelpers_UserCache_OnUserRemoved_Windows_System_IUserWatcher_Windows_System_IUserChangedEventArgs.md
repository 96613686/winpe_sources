# UserHelpers::UserCache::OnUserRemoved(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)

- ea: `0x1800154f0`
- end: `0x18001559c`
- name: `?OnUserRemoved@UserCache@UserHelpers@@AEAAJPEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@45@@Z`
- size: `172`
- prototype: `__int64 __fastcall(UserHelpers::UserCache *__hidden this, struct Windows::System::IUserWatcher *, struct Windows::System::IUserChangedEventArgs *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000868c`
- `0x180008c30`
- `0x1800154f0`
- `0x180021850`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015519`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015519`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001556c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001556c`

## pseudocode

```c
__int64 __fastcall UserHelpers::UserCache::OnUserRemoved(
        UserHelpers::UserCache *this,
        struct Windows::System::IUserWatcher *a2,
        struct Windows::System::IUserChangedEventArgs *a3)
{
  RTL_SRWLOCK *v4; // rbx
  const char *v5; // r9
  __int64 result; // rax
  __int128 v7; // [rsp+30h] [rbp-68h] BYREF
  __int16 v8; // [rsp+40h] [rbp-58h]
  __int64 v9; // [rsp+50h] [rbp-48h]
  __int64 v10; // [rsp+58h] [rbp-40h]
  __int128 v11; // [rsp+60h] [rbp-38h]
  __int64 v12; // [rsp+70h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v4 = (RTL_SRWLOCK *)((char *)this + 24);
  AcquireSRWLockExclusive((PSRWLOCK)this + 3);
  v7 = 0;
  v10 = 7;
  v9 = 0;
  v8 = 0;
  v11 = 0;
  v12 = 0;
  UserHelpers::UserCache::CachedData::operator=((char *)this + 32, (char *)&v7);
  UserHelpers::UserCache::CachedData::~CachedData((UserHelpers::UserCache::CachedData *)&v7);
  if ( v4 )
    ReleaseSRWLockExclusive(v4);
  result = 0;
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      result = (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x136,
                               (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
                               v5);
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x1800154f0  mov     [rsp+arg_8], rbx
0x1800154f5  push    rdi
0x1800154f6  sub     rsp, 90h
0x1800154fd  mov     rax, cs:__security_cookie
0x180015504  xor     rax, rsp
0x180015507  mov     [rsp+98h+var_18], rax
0x18001550f  mov     rdi, rcx
0x180015512  lea     rbx, [rcx+18h]
0x180015516  mov     rcx, rbx; SRWLock
0x180015519  call    cs:__imp_AcquireSRWLockExclusive
0x18001551f  xorps   xmm0, xmm0
0x180015522  movdqa  [rsp+98h+var_68], xmm0
0x180015528  mov     [rsp+98h+var_40], 7
0x180015531  mov     [rsp+98h+var_48], 0
0x18001553a  xor     eax, eax
0x18001553c  mov     [rsp+98h+var_58], ax
0x180015541  movdqa  [rsp+98h+var_38], xmm0
0x180015547  mov     [rsp+98h+var_28], rax
0x18001554c  lea     rcx, [rdi+20h]
0x180015550  lea     rdx, [rsp+98h+var_68]
0x180015555  call    ??4CachedData@UserCache@UserHelpers@@QEAAAEAU012@$$QEAU012@@Z; UserHelpers::UserCache::CachedData::operator=(UserHelpers::UserCache::CachedData &&)
0x18001555a  lea     rcx, [rsp+98h+var_68]; this
0x18001555f  call    ??1CachedData@UserCache@UserHelpers@@QEAA@XZ; UserHelpers::UserCache::CachedData::~CachedData(void)
0x180015564  test    rbx, rbx
0x180015567  jz      short loc_180015572
0x180015569  mov     rcx, rbx; SRWLock
0x18001556c  call    cs:__imp_ReleaseSRWLockExclusive
0x180015572  xor     eax, eax
0x180015574  jmp     short loc_18001557A
0x180015576  mov     eax, [rsp+98h+var_78]
0x18001557a  mov     rcx, [rsp+98h+var_18]
0x180015582  xor     rcx, rsp; StackCookie
0x180015585  call    __security_check_cookie
0x18001558a  mov     rbx, [rsp+98h+arg_8]
0x180015592  add     rsp, 90h
0x180015599  pop     rdi
0x18001559a  retn
```
