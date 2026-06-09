# UserHelpers::UserCache::OnUserAdded(Windows::System::IUserWatcher *,Windows::System::IUserChangedEventArgs *)

- ea: `0x1800153f0`
- end: `0x1800154e3`
- name: `?OnUserAdded@UserCache@UserHelpers@@AEAAJPEAUIUserWatcher@System@Windows@@PEAUIUserChangedEventArgs@45@@Z`
- size: `243`
- prototype: `__int64 __fastcall(UserHelpers::UserCache *__hidden this, struct Windows::System::IUserWatcher *, struct Windows::System::IUserChangedEventArgs *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000868c`
- `0x180008c30`
- `0x18000cd18`
- `0x1800136c0`
- `0x1800153f0`
- `0x180021850`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015421`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015421`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001549a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001549a`

## string_xrefs

- `0x1800154d0`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\textinput\UserCache.h`

## pseudocode

```c
__int64 __fastcall UserHelpers::UserCache::OnUserAdded(
        UserHelpers::UserCache *this,
        struct Windows::System::IUserWatcher *a2,
        struct Windows::System::IUserChangedEventArgs *a3)
{
  RTL_SRWLOCK *v5; // rbx
  __int64 v6; // rax
  int v7; // eax
  __int128 *v8; // rax
  const char *v9; // r9
  __int64 result; // rax
  int v11[2]; // [rsp+20h] [rbp-78h] BYREF
  RTL_SRWLOCK *v12; // [rsp+28h] [rbp-70h]
  __int128 v13[5]; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v5 = (RTL_SRWLOCK *)((char *)this + 24);
  AcquireSRWLockExclusive((PSRWLOCK)this + 3);
  try
  {
    v12 = v5;
    v6 = *(_QWORD *)a3;
    *(_QWORD *)v11 = 0;
    v7 = (*(__int64 (__fastcall **)(struct Windows::System::IUserChangedEventArgs *, int *))(v6 + 48))(a3, v11);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x128,
        (int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
        (const char *)(unsigned int)v7,
        v11[0]);
    v8 = UserHelpers::UserCache::CacheForUser(v13, *(UserHelpers **)v11);
    UserHelpers::UserCache::CachedData::operator=((char *)this + 32, (char *)v8);
    UserHelpers::UserCache::CachedData::~CachedData((UserHelpers::UserCache::CachedData *)v13);
    if ( *(_QWORD *)v11 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 16LL))(*(_QWORD *)v11);
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x12D,
                           (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserCache.h",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800153f0  mov     [rsp+arg_8], rbx
0x1800153f5  mov     [rsp+arg_18], rsi
0x1800153fa  push    rdi
0x1800153fb  sub     rsp, 90h
0x180015402  mov     rax, cs:__security_cookie
0x180015409  xor     rax, rsp
0x18001540c  mov     [rsp+98h+var_18], rax
0x180015414  mov     rsi, r8
0x180015417  mov     rdi, rcx
0x18001541a  lea     rbx, [rcx+18h]
0x18001541e  mov     rcx, rbx; SRWLock
0x180015421  call    cs:__imp_AcquireSRWLockExclusive
0x180015427  mov     [rsp+98h+var_70], rbx
0x18001542c  mov     rax, [rsi]
0x18001542f  mov     qword ptr [rsp+98h+var_78], 0; int
0x180015438  lea     rdx, [rsp+98h+var_78]
0x18001543d  mov     rcx, rsi
0x180015440  mov     rax, [rax+30h]
0x180015444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015449  mov     rcx, [rsp+98h]; this
0x180015451  test    eax, eax
0x180015453  js      short loc_1800154CD
0x180015455  mov     rdx, qword ptr [rsp+98h+var_78]
0x18001545a  lea     rcx, [rsp+98h+var_68]
0x18001545f  call    ?CacheForUser@UserCache@UserHelpers@@CA?AUCachedData@12@PEAUIUser@System@Windows@@@Z; UserHelpers::UserCache::CacheForUser(Windows::System::IUser *)
0x180015464  lea     rcx, [rdi+20h]
0x180015468  mov     rdx, rax
0x18001546b  call    ??4CachedData@UserCache@UserHelpers@@QEAAAEAU012@$$QEAU012@@Z; UserHelpers::UserCache::CachedData::operator=(UserHelpers::UserCache::CachedData &&)
0x180015470  lea     rcx, [rsp+98h+var_68]; this
0x180015475  call    ??1CachedData@UserCache@UserHelpers@@QEAA@XZ; UserHelpers::UserCache::CachedData::~CachedData(void)
0x18001547a  nop
0x18001547b  mov     rcx, qword ptr [rsp+98h+var_78]
0x180015480  test    rcx, rcx
0x180015483  jz      short loc_180015492
0x180015485  mov     rax, [rcx]
0x180015488  mov     rax, [rax+10h]
0x18001548c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015491  nop
0x180015492  test    rbx, rbx
0x180015495  jz      short loc_1800154A0
0x180015497  mov     rcx, rbx; SRWLock
0x18001549a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800154a0  xor     eax, eax
0x1800154a2  jmp     short loc_1800154A8
0x1800154a4  mov     eax, [rsp+98h+var_78]
0x1800154a8  mov     rcx, [rsp+98h+var_18]
0x1800154b0  xor     rcx, rsp; StackCookie
0x1800154b3  call    __security_check_cookie
0x1800154b8  lea     r11, [rsp+98h+var_8]
0x1800154c0  mov     rbx, [r11+18h]
0x1800154c4  mov     rsi, [r11+28h]
0x1800154c8  mov     rsp, r11
0x1800154cb  pop     rdi
0x1800154cc  retn
0x1800154cd  mov     r9d, eax; char *
0x1800154d0  lea     r8, aOnecoreInterna_7; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x1800154d7  mov     edx, 128h; void *
0x1800154dc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
