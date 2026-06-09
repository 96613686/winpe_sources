# FontCacheServer::CleanupCachedFiles(void)

- ea: `0x1800b1b50`
- end: `0x1800b1d2b`
- name: `?CleanupCachedFiles@FontCacheServer@@AEAAXXZ`
- size: `475`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b1b00`

## callees

- `0x18000d55c`
- `0x180010ca0`
- `0x180028c50`
- `0x180076ca4`
- `0x180096954`
- `0x18009b3b0`
- `0x1800a1960`
- `0x1800a5280`
- `0x1800b1b50`
- `0x1800b1d64`
- `0x1800b3b3c`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1bca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1d08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1bca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b1d08`

## string_xrefs

- `0x1800b1c20`: `FontCache-Obsolete-*.dat`

## pseudocode

```c
// Hidden C++ exception states: #wind=36
void __fastcall FontCacheServer::CleanupCachedFiles(struct _RTL_CRITICAL_SECTION *this)
{
  struct Lock *v2; // r12
  LONG *p_LockCount; // r15
  unsigned int *v4; // rbx
  char v5; // r14
  const struct DWrite::RefString *CacheFolderPath; // rax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  unsigned int v8; // eax
  struct IExceptionHandler *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  struct DWrite::RefString::Data *v12[10]; // [rsp+38h] [rbp-50h] BYREF
  LPCRITICAL_SECTION v13; // [rsp+90h] [rbp+8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+98h] [rbp+10h] BYREF
  int v15; // [rsp+A0h] [rbp+18h]
  unsigned int *v16; // [rsp+A8h] [rbp+20h] BYREF

  v13 = this;
  v16 = 0;
  v2 = (struct Lock *)&this[5];
  v12[1] = (struct DWrite::RefString::Data *)&this[5];
  LockHolder::LockHolder((LockHolder *)&lpCriticalSection, (struct Lock *)&this[5]);
  p_LockCount = &this[6].LockCount;
  v12[2] = (struct DWrite::RefString::Data *)&this[6].LockCount;
  ComPtr<FileCleanup>::AddRef(&this[6].LockCount);
  ComPtr<FileCleanup>::Deref(&v16);
  v16 = *(unsigned int **)&this[6].LockCount;
  v4 = v16;
  LeaveCriticalSection(lpCriticalSection);
  if ( v4 )
  {
    v5 = 0;
    LOBYTE(lpCriticalSection) = 0;
    v15 = -1;
    CacheFolderPath = (const struct DWrite::RefString *)FontCacheServer::GetCacheFolderPath(this, v12);
    try
    {
      FontCache::DeleteCacheFiles(CacheFolderPath, L"FontCache-Obsolete-*.dat", 0);
      DWrite::RefString::DecrementRef(v12[0]);
      DebugInfo = this[10].DebugInfo;
      if ( DebugInfo )
      {
        v8 = (*(__int64 (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG))(*(_QWORD *)&DebugInfo->Type + 48LL))(DebugInfo);
        EventSource<ComInterfaceList<FontCacheServer,IFontCacheServer,IFontCacheServerInternal>,IFontCacheServer,IFontCacheServerInternal>::LogAndThrowIfFailed(
          this,
          v8,
          0x70756E61656C4346LL,
          434);
        v5 = 1;
        LOBYTE(lpCriticalSection) = 1;
      }
      FileCleanup::Cleanup((FileCleanup *)v4);
      v10 = v4[11];
      v15 = v4[11];
    }
    catch ( ... )
    {
      MapExceptionToHresult(v9);
    }
    if ( v5 )
      (*(void (__fastcall **)(PRTL_CRITICAL_SECTION_DEBUG, __int64))(*(_QWORD *)this[10].DebugInfo + 56LL))(
        this[10].DebugInfo,
        v10);
  }
  else
  {
    EventLogger::LogEvent<EventTag>(&this->LockSemaphore, 0x7265767265536346LL, 0x70756E61656C4346LL, 1819047278);
  }
  LockHolder::LockHolder((LockHolder *)&v13, v2);
  v11 = *(_QWORD *)p_LockCount;
  *(_QWORD *)p_LockCount = 0;
  ComPtr<IFontSetCache>::Deref(v11);
  EventLogger::LogEvent<EventTag>(&this->LockSemaphore, 0x7265767265536346LL, 0x70756E61656C4346LL, 6581829);
  LeaveCriticalSection(v13);
  ComPtr<FileCleanup>::Deref(&v16);
}

```

## disassembly

```asm
0x1800b1b50  mov     rax, rsp
0x1800b1b53  mov     [rax+8], rcx
0x1800b1b57  push    rbx
0x1800b1b58  push    rsi
0x1800b1b59  push    rdi
0x1800b1b5a  push    r12
0x1800b1b5c  push    r14
0x1800b1b5e  push    r15
0x1800b1b60  sub     rsp, 58h
0x1800b1b64  mov     rsi, rcx
0x1800b1b67  mov     rdi, 70756E61656C4346h
0x1800b1b71  mov     [rsp+88h+var_58], rdi
0x1800b1b76  mov     qword ptr [rax+20h], 0
0x1800b1b7e  lea     r12, [rcx+0C8h]
0x1800b1b85  mov     [rsp+88h+var_48], r12
0x1800b1b8a  mov     rdx, r12; struct Lock *
0x1800b1b8d  lea     rcx, [rax+10h]; this
0x1800b1b91  call    ??0LockHolder@@QEAA@AEAVLock@@@Z; LockHolder::LockHolder(Lock &)
0x1800b1b96  lea     r15, [rsi+0F8h]
0x1800b1b9d  mov     [rsp+88h+var_40], r15
0x1800b1ba2  mov     rcx, r15
0x1800b1ba5  call    ?AddRef@?$ComPtr@VFileCleanup@@@@AEBAXXZ; ComPtr<FileCleanup>::AddRef(void)
0x1800b1baa  lea     rcx, [rsp+88h+arg_18]
0x1800b1bb2  call    ?Deref@?$ComPtr@VFileCleanup@@@@AEAAXXZ; ComPtr<FileCleanup>::Deref(void)
0x1800b1bb7  mov     rbx, [r15]
0x1800b1bba  mov     [rsp+88h+arg_18], rbx
0x1800b1bc2  mov     rcx, [rsp+88h+lpCriticalSection]; lpCriticalSection
0x1800b1bca  call    cs:__imp_LeaveCriticalSection
0x1800b1bd0  test    rbx, rbx
0x1800b1bd3  jnz     short loc_1800B1BF9
0x1800b1bd5  mov     rbx, 7265767265536346h
0x1800b1bdf  lea     rcx, [rsi+18h]
0x1800b1be3  mov     r9d, 6C6C756Eh
0x1800b1be9  mov     r8, rdi
0x1800b1bec  mov     rdx, rbx
0x1800b1bef  call    ??$LogEvent@VEventTag@@@EventLogger@@QEBAXVEventTag@@00@Z; EventLogger::LogEvent<EventTag>(EventTag,EventTag,EventTag)
0x1800b1bf4  jmp     loc_1800B1CCC
0x1800b1bf9  xor     r14b, r14b
0x1800b1bfc  mov     byte ptr [rsp+88h+lpCriticalSection], r14b
0x1800b1c04  mov     [rsp+88h+arg_10], 0FFFFFFFFh
0x1800b1c0f  lea     rdx, [rsp+88h+var_50]
0x1800b1c14  mov     rcx, rsi
0x1800b1c17  call    ?GetCacheFolderPath@FontCacheServer@@QEBA?AVRefString@DWrite@@XZ; FontCacheServer::GetCacheFolderPath(void)
0x1800b1c1c  nop
0x1800b1c1d  xor     r8d, r8d; bool
0x1800b1c20  lea     rdx, aFontcacheObsol_0; "FontCache-Obsolete-*.dat"
0x1800b1c27  mov     rcx, rax; struct DWrite::RefString *
0x1800b1c2a  call    ?DeleteCacheFiles@FontCache@@SAXAEBVRefString@DWrite@@PEB_W_N@Z; FontCache::DeleteCacheFiles(DWrite::RefString const &,wchar_t const *,bool)
0x1800b1c2f  nop
0x1800b1c30  mov     rcx, [rsp+88h+var_50]; struct DWrite::RefString::Data *
0x1800b1c35  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800b1c3a  mov     rcx, [rsi+190h]
0x1800b1c41  test    rcx, rcx
0x1800b1c44  jz      short loc_1800B1C70
0x1800b1c46  mov     rax, [rcx]
0x1800b1c49  mov     rax, [rax+30h]
0x1800b1c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1c52  mov     r9d, 1B2h
0x1800b1c58  mov     r8, rdi
0x1800b1c5b  mov     edx, eax
0x1800b1c5d  mov     rcx, rsi
0x1800b1c60  call    ?LogAndThrowIfFailed@?$EventSource@V?$ComInterfaceList@VFontCacheServer@@UIFontCacheServer@@UIFontCacheServerInternal@@@@UIFontCacheServer@@UIFontCacheServerInternal@@@@QEBAXJVEventTag@@I@Z; EventSource<ComInterfaceList<FontCacheServer,IFontCacheServer,IFontCacheServerInternal>,IFontCacheServer,IFontCacheServerInternal>::LogAndThrowIfFailed(long,EventTag,uint)
0x1800b1c65  mov     r14b, 1
0x1800b1c68  mov     byte ptr [rsp+88h+lpCriticalSection], r14b
0x1800b1c70  mov     rcx, rbx; this
0x1800b1c73  call    ?Cleanup@FileCleanup@@QEAAXXZ; FileCleanup::Cleanup(void)
0x1800b1c78  mov     edx, [rbx+2Ch]
0x1800b1c7b  mov     [rsp+88h+arg_10], edx
0x1800b1c82  jmp     short loc_1800B1CAA
0x1800b1c84  mov     rsi, [rsp+88h+arg_0]
0x1800b1c8c  mov     rdi, [rsp+88h+var_58]
0x1800b1c91  mov     r14b, byte ptr [rsp+88h+lpCriticalSection]
0x1800b1c99  mov     edx, [rsp+88h+arg_10]
0x1800b1ca0  mov     r12, [rsp+88h+var_48]
0x1800b1ca5  mov     r15, [rsp+88h+var_40]
0x1800b1caa  test    r14b, r14b
0x1800b1cad  jz      short loc_1800B1CC2
0x1800b1caf  mov     rcx, [rsi+190h]
0x1800b1cb6  mov     rax, [rcx]
0x1800b1cb9  mov     rax, [rax+38h]
0x1800b1cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1cc2  mov     rbx, 7265767265536346h
0x1800b1ccc  mov     rdx, r12; struct Lock *
0x1800b1ccf  lea     rcx, [rsp+88h+arg_0]; this
0x1800b1cd7  call    ??0LockHolder@@QEAA@AEAVLock@@@Z; LockHolder::LockHolder(Lock &)
0x1800b1cdc  mov     rcx, [r15]
0x1800b1cdf  mov     qword ptr [r15], 0
0x1800b1ce6  call    ?Deref@?$ComPtr@UIFontSetCache@@@@CAXPEAUIFontSetCache@@@Z; ComPtr<IFontSetCache>::Deref(IFontSetCache *)
0x1800b1ceb  lea     rcx, [rsi+18h]
0x1800b1cef  mov     r9d, 646E45h
0x1800b1cf5  mov     r8, rdi
0x1800b1cf8  mov     rdx, rbx
0x1800b1cfb  call    ??$LogEvent@VEventTag@@@EventLogger@@QEBAXVEventTag@@00@Z; EventLogger::LogEvent<EventTag>(EventTag,EventTag,EventTag)
0x1800b1d00  mov     rcx, [rsp+88h+arg_0]; lpCriticalSection
0x1800b1d08  call    cs:__imp_LeaveCriticalSection
0x1800b1d0e  nop
0x1800b1d0f  lea     rcx, [rsp+88h+arg_18]
0x1800b1d17  call    ?Deref@?$ComPtr@VFileCleanup@@@@AEAAXXZ; ComPtr<FileCleanup>::Deref(void)
0x1800b1d1c  nop
0x1800b1d1d  add     rsp, 58h
0x1800b1d21  pop     r15
0x1800b1d23  pop     r14
0x1800b1d25  pop     r12
0x1800b1d27  pop     rdi
0x1800b1d28  pop     rsi
0x1800b1d29  pop     rbx
0x1800b1d2a  retn
```
