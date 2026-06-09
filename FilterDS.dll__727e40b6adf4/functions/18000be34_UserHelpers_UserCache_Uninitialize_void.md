# UserHelpers::UserCache::Uninitialize(void)

- ea: `0x18000be34`
- end: `0x18000bf63`
- name: `?Uninitialize@UserCache@UserHelpers@@QEAAXXZ`
- size: `303`
- prototype: `void __fastcall(UserHelpers::UserCache *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180008ea0`

## callees

- `0x18000868c`
- `0x180008c30`
- `0x18000be34`
- `0x18000d760`
- `0x180021850`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000be5a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000be5a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000be72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000be85`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000be72`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000be85`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000be8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000be8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bf3f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000bf3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UserHelpers::UserCache::Uninitialize(UserHelpers::UserCache *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK v3; // rcx
  __int64 v4; // rcx
  __int128 v5; // [rsp+20h] [rbp-68h] BYREF
  __int16 v6; // [rsp+30h] [rbp-58h]
  __int64 v7; // [rsp+40h] [rbp-48h]
  __int64 v8; // [rsp+48h] [rbp-40h]
  __int128 v9; // [rsp+50h] [rbp-38h]
  __int64 v10; // [rsp+60h] [rbp-28h]

  v2 = (RTL_SRWLOCK *)((char *)this + 24);
  AcquireSRWLockShared((PSRWLOCK)this + 3);
  if ( *((_BYTE *)this + 16) )
  {
    if ( v2 )
      ReleaseSRWLockShared(v2);
    AcquireSRWLockExclusive(v2);
    if ( *((_BYTE *)this + 16) )
    {
      v5 = 0;
      v8 = 7;
      v7 = 0;
      v6 = 0;
      v9 = 0;
      v10 = 0;
      UserHelpers::UserCache::CachedData::operator=((char *)this + 32, (char *)&v5);
      UserHelpers::UserCache::CachedData::~CachedData((UserHelpers::UserCache::CachedData *)&v5);
      wil::unique_winrt_event_token<Windows::System::IUserWatcher>::reset((__int64)this + 104);
      wil::unique_winrt_event_token<Windows::System::IUserWatcher>::reset((__int64)this + 128);
      v3.Ptr = *(PVOID *)this;
      *(_QWORD *)this = 0;
      if ( v3.Ptr )
        (*(void (__fastcall **)(RTL_SRWLOCK))(*(_QWORD *)v3.Ptr + 16LL))(v3);
      v4 = *((_QWORD *)this + 1);
      *((_QWORD *)this + 1) = 0;
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      *((_BYTE *)this + 16) = 0;
    }
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
  }
  else if ( v2 )
  {
    ReleaseSRWLockShared(v2);
  }
}

```

## disassembly

```asm
0x18000be34  mov     [rsp+arg_8], rbx
0x18000be39  push    rdi
0x18000be3a  sub     rsp, 80h
0x18000be41  mov     rax, cs:__security_cookie
0x18000be48  xor     rax, rsp
0x18000be4b  mov     [rsp+88h+var_18], rax
0x18000be50  mov     rdi, rcx
0x18000be53  lea     rbx, [rcx+18h]
0x18000be57  mov     rcx, rbx; SRWLock
0x18000be5a  call    cs:__imp_AcquireSRWLockShared
0x18000be60  cmp     byte ptr [rdi+10h], 0
0x18000be64  jnz     short loc_18000BE7D
0x18000be66  test    rbx, rbx
0x18000be69  jz      loc_18000BF45
0x18000be6f  mov     rcx, rbx; SRWLock
0x18000be72  call    cs:__imp_ReleaseSRWLockShared
0x18000be78  jmp     loc_18000BF45
0x18000be7d  test    rbx, rbx
0x18000be80  jz      short loc_18000BE8B
0x18000be82  mov     rcx, rbx; SRWLock
0x18000be85  call    cs:__imp_ReleaseSRWLockShared
0x18000be8b  mov     rcx, rbx; SRWLock
0x18000be8e  call    cs:__imp_AcquireSRWLockExclusive
0x18000be94  cmp     byte ptr [rdi+10h], 0
0x18000be98  jz      loc_18000BF37
0x18000be9e  xorps   xmm0, xmm0
0x18000bea1  movdqa  [rsp+88h+var_68], xmm0
0x18000bea7  mov     [rsp+88h+var_40], 7
0x18000beb0  mov     [rsp+88h+var_48], 0
0x18000beb9  xor     eax, eax
0x18000bebb  mov     [rsp+88h+var_58], ax
0x18000bec0  movdqa  [rsp+88h+var_38], xmm0
0x18000bec6  mov     [rsp+88h+var_28], rax
0x18000becb  lea     rcx, [rdi+20h]
0x18000becf  lea     rdx, [rsp+88h+var_68]
0x18000bed4  call    ??4CachedData@UserCache@UserHelpers@@QEAAAEAU012@$$QEAU012@@Z; UserHelpers::UserCache::CachedData::operator=(UserHelpers::UserCache::CachedData &&)
0x18000bed9  lea     rcx, [rsp+88h+var_68]; this
0x18000bede  call    ??1CachedData@UserCache@UserHelpers@@QEAA@XZ; UserHelpers::UserCache::CachedData::~CachedData(void)
0x18000bee3  lea     rcx, [rdi+68h]
0x18000bee7  call    ?reset@?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@wil@@QEAAXXZ; wil::unique_winrt_event_token<Windows::System::IUserWatcher>::reset(void)
0x18000beec  lea     rcx, [rdi+80h]
0x18000bef3  call    ?reset@?$unique_winrt_event_token@UIUserWatcher@System@Windows@@@wil@@QEAAXXZ; wil::unique_winrt_event_token<Windows::System::IUserWatcher>::reset(void)
0x18000bef8  nop
0x18000bef9  mov     rcx, [rdi]
0x18000befc  mov     qword ptr [rdi], 0
0x18000bf03  test    rcx, rcx
0x18000bf06  jz      short loc_18000BF15
0x18000bf08  mov     rax, [rcx]
0x18000bf0b  mov     rax, [rax+10h]
0x18000bf0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf14  nop
0x18000bf15  mov     rcx, [rdi+8]
0x18000bf19  mov     qword ptr [rdi+8], 0
0x18000bf21  test    rcx, rcx
0x18000bf24  jz      short loc_18000BF33
0x18000bf26  mov     rax, [rcx]
0x18000bf29  mov     rax, [rax+10h]
0x18000bf2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf32  nop
0x18000bf33  mov     byte ptr [rdi+10h], 0
0x18000bf37  test    rbx, rbx
0x18000bf3a  jz      short loc_18000BF45
0x18000bf3c  mov     rcx, rbx; SRWLock
0x18000bf3f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000bf45  mov     rcx, [rsp+88h+var_18]
0x18000bf4a  xor     rcx, rsp; StackCookie
0x18000bf4d  call    __security_check_cookie
0x18000bf52  mov     rbx, [rsp+88h+arg_8]
0x18000bf5a  add     rsp, 80h
0x18000bf61  pop     rdi
0x18000bf62  retn
```
