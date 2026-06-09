# UserHelpers::UserCache::GetUserTokenHandle(void)

- ea: `0x180015de4`
- end: `0x180016005`
- name: `?GetUserTokenHandle@UserCache@UserHelpers@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ`
- size: `545`
- prototype: `__int64 *__fastcall(RTL_SRWLOCK *this, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180015c0c`

## callees

- `0x180002234`
- `0x18000297c`
- `0x1800029ec`
- `0x180012f4c`
- `0x1800136c0`
- `0x180014c20`
- `0x180015de4`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015e56`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015e56`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015ee8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015efb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015ee8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015efb`

## pseudocode

```c
__int64 *__fastcall UserHelpers::UserCache::GetUserTokenHandle(RTL_SRWLOCK *this, __int64 *a2)
{
  __int64 v4; // r14
  RTL_SRWLOCK *v6; // rsi
  _QWORD *Ptr; // rax
  volatile signed __int32 *v8; // rbp
  PVOID v9; // r14
  volatile signed __int32 *v10; // rdi
  __int64 v11; // rsi
  __int64 v12; // rbp
  volatile signed __int32 *v13; // rdi
  __int64 v15; // rcx

  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( __TSS0__1__IsValid_UserCache_UserHelpers__QEAA_NXZ_4HA > *(_DWORD *)(v4 + 4) )
  {
    Init_thread_header(&__TSS0__1__IsValid_UserCache_UserHelpers__QEAA_NXZ_4HA);
    if ( __TSS0__1__IsValid_UserCache_UserHelpers__QEAA_NXZ_4HA == -1 )
    {
      `UserHelpers::UserCache::IsValid'::`2'::notWarmbloodUser = _lambda_7a6b932087c5bd57880202007f3fcd96_::operator()(v15);
      Init_thread_footer(&__TSS0__1__IsValid_UserCache_UserHelpers__QEAA_NXZ_4HA);
    }
  }
  if ( `UserHelpers::UserCache::IsValid'::`2'::notWarmbloodUser && SHIDWORD(this[2].Ptr) > 0 )
  {
    if ( !LOBYTE(this[2].Ptr) )
      UserHelpers::UserCache::Initialize((UserHelpers::UserCache *)this);
    v6 = this + 3;
    AcquireSRWLockShared(this + 3);
    Ptr = this[4].Ptr;
    if ( Ptr && (unsigned __int64)(*Ptr - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      *a2 = 0;
      a2[1] = 0;
      v8 = (volatile signed __int32 *)this[5].Ptr;
      v9 = this[4].Ptr;
      if ( v8 )
        _InterlockedIncrement(v8 + 2);
      v10 = (volatile signed __int32 *)a2[1];
      if ( v10 )
      {
        if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
          if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        }
      }
      a2[1] = (__int64)v8;
      *a2 = (__int64)v9;
      if ( v6 )
        ReleaseSRWLockShared(v6);
      return a2;
    }
    if ( this != (RTL_SRWLOCK *)-24LL )
      ReleaseSRWLockShared(this + 3);
  }
  if ( __TSS0__1__GetCachedForProcess_UserCache_UserHelpers__CAAEAUCachedData_23_XZ_4HA > *(_DWORD *)(v4 + 4) )
  {
    Init_thread_header(&__TSS0__1__GetCachedForProcess_UserCache_UserHelpers__CAAEAUCachedData_23_XZ_4HA);
    if ( __TSS0__1__GetCachedForProcess_UserCache_UserHelpers__CAAEAUCachedData_23_XZ_4HA == -1 )
    {
      UserHelpers::UserCache::CacheForUser(
        (__int128 *)&`UserHelpers::UserCache::GetCachedForProcess'::`2'::cachedForProcess,
        0);
      atexit(`UserHelpers::UserCache::GetCachedForProcess'::`2'::`dynamic atexit destructor for 'cachedForProcess'');
      Init_thread_footer(&__TSS0__1__GetCachedForProcess_UserCache_UserHelpers__CAAEAUCachedData_23_XZ_4HA);
    }
  }
  *a2 = 0;
  a2[1] = 0;
  v11 = qword_180030C28;
  v12 = `UserHelpers::UserCache::GetCachedForProcess'::`2'::cachedForProcess;
  if ( qword_180030C28 )
    _InterlockedIncrement((volatile signed __int32 *)(qword_180030C28 + 8));
  v13 = (volatile signed __int32 *)a2[1];
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  a2[1] = v11;
  *a2 = v12;
  return a2;
}

```

## disassembly

```asm
0x180015de4  push    rbx
0x180015de6  push    rbp
0x180015de7  push    rsi
0x180015de8  push    rdi
0x180015de9  push    r12
0x180015deb  push    r14
0x180015ded  sub     rsp, 38h
0x180015df1  mov     rbx, rdx
0x180015df4  mov     rdi, rcx
0x180015df7  mov     r8d, cs:_tls_index
0x180015dfe  mov     rax, gs:58h
0x180015e07  mov     ebp, 4
0x180015e0c  mov     r14, [rax+r8*8]
0x180015e10  or      r12d, 0FFFFFFFFh
0x180015e14  mov     eax, [r14+rbp]
0x180015e18  cmp     cs:?$TSS0@?1??IsValid@UserCache@UserHelpers@@QEAA_NXZ@4HA, eax
0x180015e1e  jg      loc_180015FCF
0x180015e24  cmp     cs:?notWarmbloodUser@?1??IsValid@UserCache@UserHelpers@@QEAA_NXZ@4_NA, 0; bool `UserHelpers::UserCache::IsValid(void)'::`2'::notWarmbloodUser
0x180015e2b  jz      short loc_180015E37
0x180015e2d  cmp     dword ptr [rdi+14h], 0
0x180015e31  jle     short loc_180015E37
0x180015e33  mov     al, 1
0x180015e35  jmp     short loc_180015E39
0x180015e37  xor     al, al
0x180015e39  test    al, al
0x180015e3b  jz      loc_180015F01
0x180015e41  cmp     byte ptr [rdi+10h], 0
0x180015e45  jnz     short loc_180015E4F
0x180015e47  mov     rcx, rdi; this
0x180015e4a  call    ?Initialize@UserCache@UserHelpers@@QEAAXXZ; UserHelpers::UserCache::Initialize(void)
0x180015e4f  lea     rsi, [rdi+18h]
0x180015e53  mov     rcx, rsi; SRWLock
0x180015e56  call    cs:__imp_AcquireSRWLockShared
0x180015e5c  mov     rax, [rdi+20h]
0x180015e60  test    rax, rax
0x180015e63  jz      loc_180015EF3
0x180015e69  mov     rax, [rax]
0x180015e6c  dec     rax
0x180015e6f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180015e73  ja      short loc_180015EF3
0x180015e75  mov     qword ptr [rbx], 0
0x180015e7c  mov     qword ptr [rbx+8], 0
0x180015e84  mov     rbp, [rdi+28h]
0x180015e88  mov     r14, [rdi+20h]
0x180015e8c  test    rbp, rbp
0x180015e8f  jz      short loc_180015E95
0x180015e91  lock inc dword ptr [rbp+8]
0x180015e95  mov     rdi, [rbx+8]
0x180015e99  test    rdi, rdi
0x180015e9c  jz      short loc_180015ED5
0x180015e9e  mov     eax, r12d
0x180015ea1  lock xadd [rdi+8], eax
0x180015ea6  add     eax, r12d
0x180015ea9  jnz     short loc_180015ED5
0x180015eab  mov     rax, [rdi]
0x180015eae  mov     rcx, rdi
0x180015eb1  mov     rax, [rax]
0x180015eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eb9  mov     eax, r12d
0x180015ebc  lock xadd [rdi+0Ch], eax
0x180015ec1  add     eax, r12d
0x180015ec4  jnz     short loc_180015ED5
0x180015ec6  mov     rax, [rdi]
0x180015ec9  mov     rcx, rdi
0x180015ecc  mov     rax, [rax+8]
0x180015ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ed5  mov     [rbx+8], rbp
0x180015ed9  mov     [rbx], r14
0x180015edc  test    rsi, rsi
0x180015edf  jz      loc_180015F7A
0x180015ee5  mov     rcx, rsi; SRWLock
0x180015ee8  call    cs:__imp_ReleaseSRWLockShared
0x180015eee  jmp     loc_180015F7A
0x180015ef3  test    rsi, rsi
0x180015ef6  jz      short loc_180015F01
0x180015ef8  mov     rcx, rsi; SRWLock
0x180015efb  call    cs:__imp_ReleaseSRWLockShared
0x180015f01  mov     eax, [r14+rbp]
0x180015f05  cmp     cs:?$TSS0@?1??GetCachedForProcess@UserCache@UserHelpers@@CAAEAUCachedData@23@XZ@4HA, eax
0x180015f0b  jg      short loc_180015F8A
0x180015f0d  mov     qword ptr [rbx], 0
0x180015f14  mov     qword ptr [rbx+8], 0
0x180015f1c  mov     rsi, cs:qword_180030C28
0x180015f23  mov     rbp, cs:?cachedForProcess@?1??GetCachedForProcess@UserCache@UserHelpers@@CAAEAUCachedData@23@XZ@4U423@A; UserHelpers::UserCache::CachedData `UserHelpers::UserCache::GetCachedForProcess(void)'::`2'::cachedForProcess
0x180015f2a  test    rsi, rsi
0x180015f2d  jz      short loc_180015F33
0x180015f2f  lock inc dword ptr [rsi+8]
0x180015f33  mov     rdi, [rbx+8]
0x180015f37  test    rdi, rdi
0x180015f3a  jz      short loc_180015F73
0x180015f3c  mov     eax, r12d
0x180015f3f  lock xadd [rdi+8], eax
0x180015f44  add     eax, r12d
0x180015f47  jnz     short loc_180015F73
0x180015f49  mov     rax, [rdi]
0x180015f4c  mov     rcx, rdi
0x180015f4f  mov     rax, [rax]
0x180015f52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f57  mov     eax, r12d
0x180015f5a  lock xadd [rdi+0Ch], eax
0x180015f5f  add     eax, r12d
0x180015f62  jnz     short loc_180015F73
0x180015f64  mov     rax, [rdi]
0x180015f67  mov     rcx, rdi
0x180015f6a  mov     rax, [rax+8]
0x180015f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f73  mov     [rbx+8], rsi
0x180015f77  mov     [rbx], rbp
0x180015f7a  mov     rax, rbx
0x180015f7d  add     rsp, 38h
0x180015f81  pop     r14
0x180015f83  pop     r12
0x180015f85  pop     rdi
0x180015f86  pop     rsi
0x180015f87  pop     rbp
0x180015f88  pop     rbx
0x180015f89  retn
0x180015f8a  lea     rcx, ?$TSS0@?1??GetCachedForProcess@UserCache@UserHelpers@@CAAEAUCachedData@23@XZ@4HA
0x180015f91  call    _Init_thread_header
0x180015f96  cmp     cs:?$TSS0@?1??GetCachedForProcess@UserCache@UserHelpers@@CAAEAUCachedData@23@XZ@4HA, r12d
0x180015f9d  jnz     loc_180015F0D
0x180015fa3  xor     edx, edx
0x180015fa5  lea     rcx, ?cachedForProcess@?1??GetCachedForProcess@UserCache@UserHelpers@@CAAEAUCachedData@23@XZ@4U423@A; UserHelpers::UserCache::CachedData `UserHelpers::UserCache::GetCachedForProcess(void)'::`2'::cachedForProcess
0x180015fac  call    ?CacheForUser@UserCache@UserHelpers@@CA?AUCachedData@12@PEAUIUser@System@Windows@@@Z; UserHelpers::UserCache::CacheForUser(Windows::System::IUser *)
0x180015fb1  lea     rcx, ??__FcachedForProcess@?1??GetCachedForProcess@UserCache@UserHelpers@@CAAEAUCachedData@12@XZ@YAXXZ; void (__cdecl *)()
0x180015fb8  call    atexit
0x180015fbd  nop
0x180015fbe  lea     rcx, ?$TSS0@?1??GetCachedForProcess@UserCache@UserHelpers@@CAAEAUCachedData@23@XZ@4HA
0x180015fc5  call    _Init_thread_footer
0x180015fca  jmp     loc_180015F0D
0x180015fcf  lea     rcx, ?$TSS0@?1??IsValid@UserCache@UserHelpers@@QEAA_NXZ@4HA
0x180015fd6  call    _Init_thread_header
0x180015fdb  cmp     cs:?$TSS0@?1??IsValid@UserCache@UserHelpers@@QEAA_NXZ@4HA, r12d
0x180015fe2  jnz     loc_180015E24
0x180015fe8  call    ??R_lambda_7a6b932087c5bd57880202007f3fcd96_@@QEBA@XZ; _lambda_7a6b932087c5bd57880202007f3fcd96_::operator()(void)
0x180015fed  mov     cs:?notWarmbloodUser@?1??IsValid@UserCache@UserHelpers@@QEAA_NXZ@4_NA, al; bool `UserHelpers::UserCache::IsValid(void)'::`2'::notWarmbloodUser
0x180015ff3  lea     rcx, ?$TSS0@?1??IsValid@UserCache@UserHelpers@@QEAA_NXZ@4HA
0x180015ffa  call    _Init_thread_footer
0x180015fff  jmp     loc_180015E24
```
