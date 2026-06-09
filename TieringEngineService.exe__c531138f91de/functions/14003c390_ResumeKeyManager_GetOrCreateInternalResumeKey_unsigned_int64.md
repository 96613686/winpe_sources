# ResumeKeyManager::GetOrCreateInternalResumeKey(unsigned __int64 *)

- ea: `0x14003c390`
- end: `0x14003c48b`
- name: `?GetOrCreateInternalResumeKey@ResumeKeyManager@@QEAAPEAU_TE_ENUM_INTERNAL_RESUME_KEY@@PEA_K@Z`
- size: `251`
- prototype: `struct _TE_ENUM_INTERNAL_RESUME_KEY *__fastcall(ResumeKeyManager *__hidden this, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140038a50`
- `0x140039090`
- `0x140039b10`

## callees

- `0x14003c178`
- `0x14003c280`
- `0x14003c390`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c3d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c41c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c44a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c477`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c3d2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c41c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c44a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c477`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14003c3bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14003c427`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14003c3bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14003c427`

## pseudocode

```c
struct _TE_ENUM_INTERNAL_RESUME_KEY *__fastcall ResumeKeyManager::GetOrCreateInternalResumeKey(
        ResumeKeyManager *this,
        unsigned __int64 *a2)
{
  RTL_SRWLOCK *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  struct _TE_ENUM_INTERNAL_RESUME_KEY *v6; // rbx
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 )
    return 0;
  v4 = (RTL_SRWLOCK *)((char *)this + 40);
  v5 = (RTL_SRWLOCK *)((char *)this + 40);
  if ( !*a2 )
  {
    v9 = 0;
    AcquireSRWLockExclusive(v5);
    if ( *((_QWORD *)this + 3) < 0x3E80u && (v6 = ResumeKeyManager::CreateNewResumeKeyLocked(this, &v9)) != 0 )
    {
      *a2 = v9;
      utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>::find<void>(
        this,
        &v9,
        a2);
      if ( (ResumeKeyManager *)v9 != this )
        _InterlockedIncrement((volatile signed __int32 *)(v9 + 96));
      ReleaseSRWLockExclusive(v4);
    }
    else
    {
      ReleaseSRWLockExclusive(v4);
      return 0;
    }
    return v6;
  }
  AcquireSRWLockExclusive(v5);
  utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>::find<void>(
    this,
    &v9,
    a2);
  v8 = v9;
  if ( (ResumeKeyManager *)v9 == this )
  {
    ReleaseSRWLockExclusive(v4);
    return 0;
  }
  utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>::find<void>(
    this,
    &v9,
    a2);
  if ( (ResumeKeyManager *)v9 != this )
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 96));
  ReleaseSRWLockExclusive(v4);
  return (struct _TE_ENUM_INTERNAL_RESUME_KEY *)(v8 + 32);
}

```

## disassembly

```asm
0x14003c390  push    rbx
0x14003c392  push    rsi
0x14003c393  push    rdi
0x14003c394  push    r14
0x14003c396  sub     rsp, 28h
0x14003c39a  mov     r14, rdx
0x14003c39d  mov     rsi, rcx
0x14003c3a0  test    rdx, rdx
0x14003c3a3  jz      loc_14003C450
0x14003c3a9  cmp     qword ptr [rdx], 0
0x14003c3ad  lea     rdi, [rcx+28h]
0x14003c3b1  mov     rcx, rdi; SRWLock
0x14003c3b4  jnz     short loc_14003C427
0x14003c3b6  mov     [rsp+48h+arg_8], 0
0x14003c3bf  call    cs:__imp_AcquireSRWLockExclusive
0x14003c3c5  cmp     qword ptr [rsi+18h], 3E80h
0x14003c3cd  jb      short loc_14003C3DC
0x14003c3cf  mov     rcx, rdi; SRWLock
0x14003c3d2  call    cs:__imp_ReleaseSRWLockExclusive
0x14003c3d8  xor     ebx, ebx
0x14003c3da  jmp     short loc_14003C422
0x14003c3dc  lea     rdx, [rsp+48h+arg_8]; unsigned __int64 *
0x14003c3e1  mov     rcx, rsi; this
0x14003c3e4  call    ?CreateNewResumeKeyLocked@ResumeKeyManager@@AEAAPEAU_TE_ENUM_INTERNAL_RESUME_KEY@@PEA_K@Z; ResumeKeyManager::CreateNewResumeKeyLocked(unsigned __int64 *)
0x14003c3e9  mov     rbx, rax
0x14003c3ec  test    rax, rax
0x14003c3ef  jz      short loc_14003C3CF
0x14003c3f1  mov     rax, [rsp+48h+arg_8]
0x14003c3f6  lea     rdx, [rsp+48h+arg_8]
0x14003c3fb  mov     r8, r14
0x14003c3fe  mov     [r14], rax
0x14003c401  mov     rcx, rsi
0x14003c404  call    ??$find@X@?$_HashTable@_KU?$pair@$$CB_KVTieringResumeKey@@@utl@@U?$hash@_K@2@U?$equal_to@_K@2@V?$allocator@U?$pair@$$CB_KVTieringResumeKey@@@utl@@@2@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CB_KVTieringResumeKey@@@utl@@@utl@@U?$pair@$$CB_KVTieringResumeKey@@@2@@1@AEB_K@Z; utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>::find<void>(unsigned __int64 const &)
0x14003c409  mov     rdx, [rsp+48h+arg_8]
0x14003c40e  cmp     rdx, rsi
0x14003c411  jz      short loc_14003C419
0x14003c413  nop
0x14003c414  lock inc dword ptr [rdx+60h]
0x14003c418  nop
0x14003c419  mov     rcx, rdi; SRWLock
0x14003c41c  call    cs:__imp_ReleaseSRWLockExclusive
0x14003c422  mov     rax, rbx
0x14003c425  jmp     short loc_14003C481
0x14003c427  call    cs:__imp_AcquireSRWLockExclusive
0x14003c42d  mov     r8, r14
0x14003c430  lea     rdx, [rsp+48h+arg_8]
0x14003c435  mov     rcx, rsi
0x14003c438  call    ??$find@X@?$_HashTable@_KU?$pair@$$CB_KVTieringResumeKey@@@utl@@U?$hash@_K@2@U?$equal_to@_K@2@V?$allocator@U?$pair@$$CB_KVTieringResumeKey@@@utl@@@2@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CB_KVTieringResumeKey@@@utl@@@utl@@U?$pair@$$CB_KVTieringResumeKey@@@2@@1@AEB_K@Z; utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>::find<void>(unsigned __int64 const &)
0x14003c43d  mov     rbx, [rsp+48h+arg_8]
0x14003c442  cmp     rbx, rsi
0x14003c445  jnz     short loc_14003C454
0x14003c447  mov     rcx, rdi; SRWLock
0x14003c44a  call    cs:__imp_ReleaseSRWLockExclusive
0x14003c450  xor     eax, eax
0x14003c452  jmp     short loc_14003C481
0x14003c454  mov     r8, r14
0x14003c457  lea     rdx, [rsp+48h+arg_8]
0x14003c45c  mov     rcx, rsi
0x14003c45f  call    ??$find@X@?$_HashTable@_KU?$pair@$$CB_KVTieringResumeKey@@@utl@@U?$hash@_K@2@U?$equal_to@_K@2@V?$allocator@U?$pair@$$CB_KVTieringResumeKey@@@utl@@@2@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CB_KVTieringResumeKey@@@utl@@@utl@@U?$pair@$$CB_KVTieringResumeKey@@@2@@1@AEB_K@Z; utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>::find<void>(unsigned __int64 const &)
0x14003c464  mov     rdx, [rsp+48h+arg_8]
0x14003c469  cmp     rdx, rsi
0x14003c46c  jz      short loc_14003C474
0x14003c46e  nop
0x14003c46f  lock inc dword ptr [rdx+60h]
0x14003c473  nop
0x14003c474  mov     rcx, rdi; SRWLock
0x14003c477  call    cs:__imp_ReleaseSRWLockExclusive
0x14003c47d  lea     rax, [rbx+20h]
0x14003c481  add     rsp, 28h
0x14003c485  pop     r14
0x14003c487  pop     rdi
0x14003c488  pop     rsi
0x14003c489  pop     rbx
0x14003c48a  retn
```
