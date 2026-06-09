# ResumeKeyManager::CompleteUsageWithKey(unsigned __int64 *)

- ea: `0x14003c21c`
- end: `0x14003c27a`
- name: `?CompleteUsageWithKey@ResumeKeyManager@@QEAAXPEA_K@Z`
- size: `94`
- prototype: `void __fastcall(RTL_SRWLOCK *this, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140038a50`
- `0x140039090`
- `0x140039b10`

## callees

- `0x14003c178`
- `0x14003c21c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14003c273`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14003c235`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14003c235`

## pseudocode

```c
void __fastcall ResumeKeyManager::CompleteUsageWithKey(RTL_SRWLOCK *this, unsigned __int64 *a2)
{
  volatile signed __int32 *v4; // [rsp+30h] [rbp+8h] BYREF

  AcquireSRWLockExclusive(this + 5);
  if ( a2 )
  {
    utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>::find<void>(
      this,
      &v4,
      a2);
    if ( v4 != (volatile signed __int32 *)this )
      _InterlockedDecrement(v4 + 24);
  }
  ReleaseSRWLockExclusive(this + 5);
}

```

## disassembly

```asm
0x14003c21c  mov     [rsp+arg_8], rbx
0x14003c221  mov     [rsp+arg_10], rsi
0x14003c226  push    rdi
0x14003c227  sub     rsp, 20h
0x14003c22b  mov     rbx, rcx
0x14003c22e  mov     rsi, rdx
0x14003c231  add     rcx, 28h ; '('; SRWLock
0x14003c235  call    cs:__imp_AcquireSRWLockExclusive
0x14003c23b  test    rsi, rsi
0x14003c23e  jz      short loc_14003C260
0x14003c240  mov     r8, rsi
0x14003c243  lea     rdx, [rsp+28h+arg_0]
0x14003c248  mov     rcx, rbx
0x14003c24b  call    ??$find@X@?$_HashTable@_KU?$pair@$$CB_KVTieringResumeKey@@@utl@@U?$hash@_K@2@U?$equal_to@_K@2@V?$allocator@U?$pair@$$CB_KVTieringResumeKey@@@utl@@@2@$0A@@utl@@QEAA?AV?$_DlistIt@U?$_HashNode@U?$pair@$$CB_KVTieringResumeKey@@@utl@@@utl@@U?$pair@$$CB_KVTieringResumeKey@@@2@@1@AEB_K@Z; utl::_HashTable<unsigned __int64,utl::pair<unsigned __int64 const,TieringResumeKey>,utl::hash<unsigned __int64>,utl::equal_to<unsigned __int64>,utl::allocator<utl::pair<unsigned __int64 const,TieringResumeKey>>,0>::find<void>(unsigned __int64 const &)
0x14003c250  mov     rdx, [rsp+28h+arg_0]
0x14003c255  cmp     rdx, rbx
0x14003c258  jz      short loc_14003C260
0x14003c25a  nop
0x14003c25b  lock dec dword ptr [rdx+60h]
0x14003c25f  nop
0x14003c260  lea     rcx, [rbx+28h]
0x14003c264  mov     rbx, [rsp+28h+arg_8]
0x14003c269  mov     rsi, [rsp+28h+arg_10]
0x14003c26e  add     rsp, 20h
0x14003c272  pop     rdi
0x14003c273  jmp     cs:__imp_ReleaseSRWLockExclusive
```
