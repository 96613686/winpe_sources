# Cache::CacheManager::AcquireLock(bool)

- ea: `0x18001f854`
- end: `0x18001f9cc`
- name: `?AcquireLock@CacheManager@Cache@@SA?AV?$TCntPtr@UILock@CacheManager@Cache@@@Mso@@_N@Z`
- size: `376`
- prototype: ``
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x180004378`
- `0x180005430`
- `0x18000d290`
- `0x18000d2f0`
- `0x18000e5d8`
- `0x18000e880`
- `0x180014c30`
- `0x180022814`
- `0x1800229d0`
- `0x1800962d0`
- `0x18010c7c0`
- `0x18010c8f0`
- `0x1801743c0`
- `0x180200890`
- `0x180200a10`

## callees

- `0x180003d60`
- `0x18001f854`
- `0x18001f9cc`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18001f964`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18001f964`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18001f891`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18001f891`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f8d1`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f93c`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f999`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f9c0`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f8d1`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f93c`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f999`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f9c0`

## string_xrefs

- `0x18001f8bc`: `CacheManager::AcquireLock - Failed to aquire lock.`
- `0x18001f951`: `CacheManager::AcquireLock - can't access CacheManager singleton - exceeded error reporting limit, so further error messages will not be emitted.`
- `0x18001f92a`: `CacheManager::AcquireLock - can't access CacheManager singleton.`
- `0x18001f9ae`: `CacheManager::AcquireLock - lock instance failed to be created - exceeded error reporting limit, so further error messages will not be emitted.`
- `0x18001f987`: `CacheManager::AcquireLock - lock instance failed to be created.`

## pseudocode

```c
__int64 *__fastcall Cache::CacheManager::AcquireLock(__int64 *a1, char a2, unsigned int a3)
{
  __int64 v4; // rbx
  struct Cache::CacheManager *v5; // rsi
  Cache::CacheManagerLock *v6; // rax
  bool v8; // zf
  const wchar_t *v9; // r9
  __int64 v10; // rcx

  v4 = 0;
  v5 = Ofc::TSingleton<Cache::CacheManager>::s_pInstance;
  if ( (unsigned __int64)Ofc::TSingleton<Cache::CacheManager>::s_pInstance <= 1 )
    v5 = 0;
  if ( !v5 )
  {
    if ( !a2 )
    {
      *a1 = 0;
      return a1;
    }
    v5 = Cache::CacheManager::PInternalInstance();
    if ( !v5 )
    {
      v8 = ++dword_1805322EC == 100;
      if ( (unsigned int)dword_1805322EC < 0x64 )
      {
        Mso::Logging::MsoSendTraceTag(
          592545612,
          48,
          10,
          L"CacheManager::AcquireLock - can't access CacheManager singleton.");
        v8 = dword_1805322EC == 100;
      }
      if ( !v8 )
        goto LABEL_7;
      v9 = L"CacheManager::AcquireLock - can't access CacheManager singleton - exceeded error reporting limit, so further "
            "error messages will not be emitted.";
      v10 = 592545611;
      goto LABEL_21;
    }
  }
  v6 = (Cache::CacheManagerLock *)Mso::Memory::AllocateEx((Mso::Memory *)0x20, 0, a3);
  if ( !v6 )
  {
    CrashWithRecoveryOnOOM(0x1F65259Du);
    __debugbreak();
  }
  v4 = Cache::CacheManagerLock::CacheManagerLock(v6, v5);
  if ( !v4 && (unsigned int)++dword_1805322E8 <= 0x64 )
  {
    Mso::Logging::MsoSendTraceTag(592545614, 48, 10, L"CacheManager::AcquireLock - lock instance failed to be created.");
    if ( dword_1805322E8 == 100 )
    {
      v9 = L"CacheManager::AcquireLock - lock instance failed to be created - exceeded error reporting limit, so further e"
            "rror messages will not be emitted.";
      v10 = 592545613;
LABEL_21:
      Mso::Logging::MsoSendTraceTag(v10, 48, 10, v9);
    }
  }
  if ( !v4 )
LABEL_7:
    Mso::Logging::MsoSendTraceTag(592545610, 48, 15, L"CacheManager::AcquireLock - Failed to aquire lock.");
  *a1 = v4;
  return a1;
}

```

## disassembly

```asm
0x18001f854  mov     rax, rsp
0x18001f857  mov     [rax+8], rbx
0x18001f85b  mov     [rax+10h], rbp
0x18001f85f  mov     [rax+18h], rsi
0x18001f863  mov     [rax+20h], rdi
0x18001f867  push    r14
0x18001f869  sub     rsp, 20h
0x18001f86d  mov     rdi, rcx
0x18001f870  xor     ebp, ebp
0x18001f872  mov     ebx, ebp
0x18001f874  mov     rsi, cs:?s_pInstance@?$TSingleton@VCacheManager@Cache@@@Ofc@@0PEAVCacheManager@Cache@@EA; Cache::CacheManager * Ofc::TSingleton<Cache::CacheManager>::s_pInstance
0x18001f87b  cmp     rsi, 1
0x18001f87f  cmovbe  rsi, rbp
0x18001f883  lea     r14d, [rbp+30h]
0x18001f887  test    rsi, rsi
0x18001f88a  jz      short loc_18001F8F8
0x18001f88c  xor     edx, edx
0x18001f88e  lea     ecx, [rdx+20h]
0x18001f891  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18001f897  test    rax, rax
0x18001f89a  jz      loc_18001F95F
0x18001f8a0  mov     rdx, rsi; struct Cache::CacheManager *
0x18001f8a3  mov     rcx, rax; this
0x18001f8a6  call    ??0CacheManagerLock@Cache@@QEAA@AEAVCacheManager@1@@Z; Cache::CacheManagerLock::CacheManagerLock(Cache::CacheManager &)
0x18001f8ab  mov     rbx, rax
0x18001f8ae  test    rax, rax
0x18001f8b1  jz      loc_18001F96B
0x18001f8b7  test    rbx, rbx
0x18001f8ba  jnz     short loc_18001F8D7
0x18001f8bc  lea     r9, aCachemanagerAc_0; "CacheManager::AcquireLock - Failed to a"...
0x18001f8c3  mov     r8d, 0Fh
0x18001f8c9  mov     edx, r14d
0x18001f8cc  mov     ecx, 2351874Ah
0x18001f8d1  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x18001f8d7  mov     [rdi], rbx
0x18001f8da  mov     rax, rdi
0x18001f8dd  mov     rbx, [rsp+28h+arg_0]
0x18001f8e2  mov     rbp, [rsp+28h+arg_8]
0x18001f8e7  mov     rsi, [rsp+28h+arg_10]
0x18001f8ec  mov     rdi, [rsp+28h+arg_18]
0x18001f8f1  add     rsp, 20h
0x18001f8f5  pop     r14
0x18001f8f7  retn
0x18001f8f8  test    dl, dl
0x18001f8fa  jnz     short loc_18001F901
0x18001f8fc  mov     [rcx], rbp
0x18001f8ff  jmp     short loc_18001F8DA
0x18001f901  call    ?PInternalInstance@CacheManager@Cache@@SAPEAV12@XZ; Cache::CacheManager::PInternalInstance(void)
0x18001f906  mov     rsi, rax
0x18001f909  test    rax, rax
0x18001f90c  jnz     loc_18001F88C
0x18001f912  mov     eax, cs:dword_1805322EC
0x18001f918  inc     eax
0x18001f91a  mov     cs:dword_1805322EC, eax
0x18001f920  mov     esi, 0Ah
0x18001f925  cmp     eax, 64h ; 'd'
0x18001f928  jnb     short loc_18001F94B
0x18001f92a  lea     r9, aCachemanagerAc_1; "CacheManager::AcquireLock - can't acces"...
0x18001f931  mov     r8d, esi
0x18001f934  mov     edx, r14d
0x18001f937  mov     ecx, 2351874Ch
0x18001f93c  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x18001f942  mov     eax, cs:dword_1805322EC
0x18001f948  cmp     eax, 64h ; 'd'
0x18001f94b  jnz     loc_18001F8BC
0x18001f951  lea     r9, aCachemanagerAc_2; "CacheManager::AcquireLock - can't acces"...
0x18001f958  mov     ecx, 2351874Bh
0x18001f95d  jmp     short loc_18001F9BA
0x18001f95f  mov     ecx, 1F65259Dh
0x18001f964  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x18001f96a  int     3; Trap to Debugger
0x18001f96b  mov     ecx, cs:dword_1805322E8
0x18001f971  inc     ecx
0x18001f973  mov     cs:dword_1805322E8, ecx
0x18001f979  mov     esi, 0Ah
0x18001f97e  cmp     ecx, 64h ; 'd'
0x18001f981  ja      loc_18001F8B7
0x18001f987  lea     r9, aCachemanagerAc; "CacheManager::AcquireLock - lock instan"...
0x18001f98e  mov     r8d, esi
0x18001f991  mov     edx, r14d
0x18001f994  mov     ecx, 2351874Eh
0x18001f999  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x18001f99f  mov     ecx, cs:dword_1805322E8
0x18001f9a5  cmp     ecx, 64h ; 'd'
0x18001f9a8  jnz     loc_18001F8B7
0x18001f9ae  lea     r9, aCachemanagerAc_3; "CacheManager::AcquireLock - lock instan"...
0x18001f9b5  mov     ecx, 2351874Dh
0x18001f9ba  mov     r8d, esi
0x18001f9bd  mov     edx, r14d
0x18001f9c0  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x18001f9c6  jmp     loc_18001F8B7
```
