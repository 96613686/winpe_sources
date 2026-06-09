# UserHelpers::UserCache::GetHKCU(void)

- ea: `0x18001442c`
- end: `0x180014647`
- name: `?GetHKCU@UserCache@UserHelpers@@QEAA?AV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@XZ`
- size: `539`
- prototype: `__int64 *__fastcall(RTL_SRWLOCK *this, __int64 *)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013d40`
- `0x1800140b0`
- `0x180015054`
- `0x18001619c`

## callees

- `0x180002234`
- `0x18000297c`
- `0x1800029ec`
- `0x180012f4c`
- `0x1800136c0`
- `0x18001442c`
- `0x180014c20`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001449e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001449e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001452a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001453d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001452a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001453d`

## pseudocode

```c
__int64 *__fastcall UserHelpers::UserCache::GetHKCU(RTL_SRWLOCK *this, __int64 *a2)
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
    Ptr = this[10].Ptr;
    if ( Ptr && *Ptr )
    {
      *a2 = 0;
      a2[1] = 0;
      v8 = (volatile signed __int32 *)this[11].Ptr;
      v9 = this[10].Ptr;
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
  v11 = qword_180030C58;
  v12 = qword_180030C50;
  if ( qword_180030C58 )
    _InterlockedIncrement((volatile signed __int32 *)(qword_180030C58 + 8));
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
0x18001442c  push    rbx
0x18001442e  push    rbp
0x18001442f  push    rsi
0x180014430  push    rdi
0x180014431  push    r12
0x180014433  push    r14
0x180014435  sub     rsp, 38h
0x180014439  mov     rbx, rdx
0x18001443c  mov     rdi, rcx
0x18001443f  mov     r8d, cs:_tls_index
0x180014446  mov     rax, gs:58h
0x18001444f  mov     ebp, 4
0x180014454  mov     r14, [rax+r8*8]
0x180014458  or      r12d, 0FFFFFFFFh
0x18001445c  mov     eax, [r14+rbp]
0x180014460  cmp     cs:?$TSS0@?1??IsValid@UserCache@UserHelpers@@QEAA_NXZ@4HA, eax
0x180014466  jg      loc_180014611
0x18001446c  cmp     cs:?notWarmbloodUser@?1??IsValid@UserCache@UserHelpers@@QEAA_NXZ@4_NA, 0; bool `UserHelpers::UserCache::IsValid(void)'::`2'::notWarmbloodUser
0x180014473  jz      short loc_18001447F
0x180014475  cmp     dword ptr [rdi+14h], 0
0x180014479  jle     short loc_18001447F
0x18001447b  mov     al, 1
0x18001447d  jmp     short loc_180014481
0x18001447f  xor     al, al
0x180014481  test    al, al
0x180014483  jz      loc_180014543
0x180014489  cmp     byte ptr [rdi+10h], 0
0x18001448d  jnz     short loc_180014497
0x18001448f  mov     rcx, rdi; this
0x180014492  call    ?Initialize@UserCache@UserHelpers@@QEAAXXZ; UserHelpers::UserCache::Initialize(void)
0x180014497  lea     rsi, [rdi+18h]
0x18001449b  mov     rcx, rsi; SRWLock
0x18001449e  call    cs:__imp_AcquireSRWLockShared
0x1800144a4  mov     rax, [rdi+50h]
0x1800144a8  test    rax, rax
0x1800144ab  jz      loc_180014535
0x1800144b1  cmp     qword ptr [rax], 0
0x1800144b5  jz      short loc_180014535
0x1800144b7  mov     qword ptr [rbx], 0
0x1800144be  mov     qword ptr [rbx+8], 0
0x1800144c6  mov     rbp, [rdi+58h]
0x1800144ca  mov     r14, [rdi+50h]
0x1800144ce  test    rbp, rbp
0x1800144d1  jz      short loc_1800144D7
0x1800144d3  lock inc dword ptr [rbp+8]
0x1800144d7  mov     rdi, [rbx+8]
0x1800144db  test    rdi, rdi
0x1800144de  jz      short loc_180014517
0x1800144e0  mov     eax, r12d
0x1800144e3  lock xadd [rdi+8], eax
0x1800144e8  add     eax, r12d
0x1800144eb  jnz     short loc_180014517
0x1800144ed  mov     rax, [rdi]
0x1800144f0  mov     rcx, rdi
0x1800144f3  mov     rax, [rax]
0x1800144f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144fb  mov     eax, r12d
0x1800144fe  lock xadd [rdi+0Ch], eax
0x180014503  add     eax, r12d
0x180014506  jnz     short loc_180014517
0x180014508  mov     rax, [rdi]
0x18001450b  mov     rcx, rdi
0x18001450e  mov     rax, [rax+8]
0x180014512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014517  mov     [rbx+8], rbp
0x18001451b  mov     [rbx], r14
0x18001451e  test    rsi, rsi
0x180014521  jz      loc_1800145BC
0x180014527  mov     rcx, rsi; SRWLock
0x18001452a  call    cs:__imp_ReleaseSRWLockShared
0x180014530  jmp     loc_1800145BC
0x180014535  test    rsi, rsi
0x180014538  jz      short loc_180014543
0x18001453a  mov     rcx, rsi; SRWLock
0x18001453d  call    cs:__imp_ReleaseSRWLockShared
0x180014543  mov     eax, [r14+rbp]
0x180014547  cmp     cs:?$TSS0@?1??GetCachedForProcess@UserCache@UserHelpers@@CAAEAUCachedData@23@XZ@4HA, eax
0x18001454d  jg      short loc_1800145CC
0x18001454f  mov     qword ptr [rbx], 0
0x180014556  mov     qword ptr [rbx+8], 0
0x18001455e  mov     rsi, cs:qword_180030C58
0x180014565  mov     rbp, cs:qword_180030C50
0x18001456c  test    rsi, rsi
0x18001456f  jz      short loc_180014575
0x180014571  lock inc dword ptr [rsi+8]
0x180014575  mov     rdi, [rbx+8]
0x180014579  test    rdi, rdi
0x18001457c  jz      short loc_1800145B5
0x18001457e  mov     eax, r12d
0x180014581  lock xadd [rdi+8], eax
0x180014586  add     eax, r12d
0x180014589  jnz     short loc_1800145B5
0x18001458b  mov     rax, [rdi]
0x18001458e  mov     rcx, rdi
0x180014591  mov     rax, [rax]
0x180014594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014599  mov     eax, r12d
0x18001459c  lock xadd [rdi+0Ch], eax
0x1800145a1  add     eax, r12d
0x1800145a4  jnz     short loc_1800145B5
0x1800145a6  mov     rax, [rdi]
0x1800145a9  mov     rcx, rdi
0x1800145ac  mov     rax, [rax+8]
0x1800145b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145b5  mov     [rbx+8], rsi
0x1800145b9  mov     [rbx], rbp
0x1800145bc  mov     rax, rbx
0x1800145bf  add     rsp, 38h
0x1800145c3  pop     r14
0x1800145c5  pop     r12
0x1800145c7  pop     rdi
0x1800145c8  pop     rsi
0x1800145c9  pop     rbp
0x1800145ca  pop     rbx
0x1800145cb  retn
0x1800145cc  lea     rcx, ?$TSS0@?1??GetCachedForProcess@UserCache@UserHelpers@@CAAEAUCachedData@23@XZ@4HA
0x1800145d3  call    _Init_thread_header
0x1800145d8  cmp     cs:?$TSS0@?1??GetCachedForProcess@UserCache@UserHelpers@@CAAEAUCachedData@23@XZ@4HA, r12d
0x1800145df  jnz     loc_18001454F
0x1800145e5  xor     edx, edx
0x1800145e7  lea     rcx, ?cachedForProcess@?1??GetCachedForProcess@UserCache@UserHelpers@@CAAEAUCachedData@23@XZ@4U423@A; UserHelpers::UserCache::CachedData `UserHelpers::UserCache::GetCachedForProcess(void)'::`2'::cachedForProcess
0x1800145ee  call    ?CacheForUser@UserCache@UserHelpers@@CA?AUCachedData@12@PEAUIUser@System@Windows@@@Z; UserHelpers::UserCache::CacheForUser(Windows::System::IUser *)
0x1800145f3  lea     rcx, ??__FcachedForProcess@?1??GetCachedForProcess@UserCache@UserHelpers@@CAAEAUCachedData@12@XZ@YAXXZ; void (__cdecl *)()
0x1800145fa  call    atexit
0x1800145ff  nop
0x180014600  lea     rcx, ?$TSS0@?1??GetCachedForProcess@UserCache@UserHelpers@@CAAEAUCachedData@23@XZ@4HA
0x180014607  call    _Init_thread_footer
0x18001460c  jmp     loc_18001454F
0x180014611  lea     rcx, ?$TSS0@?1??IsValid@UserCache@UserHelpers@@QEAA_NXZ@4HA
0x180014618  call    _Init_thread_header
0x18001461d  cmp     cs:?$TSS0@?1??IsValid@UserCache@UserHelpers@@QEAA_NXZ@4HA, r12d
0x180014624  jnz     loc_18001446C
0x18001462a  call    ??R_lambda_7a6b932087c5bd57880202007f3fcd96_@@QEBA@XZ; _lambda_7a6b932087c5bd57880202007f3fcd96_::operator()(void)
0x18001462f  mov     cs:?notWarmbloodUser@?1??IsValid@UserCache@UserHelpers@@QEAA_NXZ@4_NA, al; bool `UserHelpers::UserCache::IsValid(void)'::`2'::notWarmbloodUser
0x180014635  lea     rcx, ?$TSS0@?1??IsValid@UserCache@UserHelpers@@QEAA_NXZ@4HA
0x18001463c  call    _Init_thread_footer
0x180014641  jmp     loc_18001446C
```
