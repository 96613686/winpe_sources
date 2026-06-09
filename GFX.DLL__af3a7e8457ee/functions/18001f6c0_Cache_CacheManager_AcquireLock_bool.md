# Cache::CacheManager::AcquireLock(bool)

- ea: `0x18001f6c0`
- end: `0x18001f838`
- name: `?AcquireLock@CacheManager@Cache@@SA?AV?$TCntPtr@UILock@CacheManager@Cache@@@Mso@@_N@Z`
- size: `376`
- prototype: ``
- caller_count: `15`
- callee_count: `3`
- tags: ``

## callers

- `0x1800041c8`
- `0x180005340`
- `0x18000d3d0`
- `0x18000d430`
- `0x18000db54`
- `0x18000ddf0`
- `0x180014680`
- `0x1800221b4`
- `0x180022370`
- `0x18006715c`
- `0x180112350`
- `0x180112480`
- `0x18016fa20`
- `0x1801fd560`
- `0x1801fd6e0`

## callees

- `0x180003cc4`
- `0x18001f6c0`
- `0x18001f838`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18001f7d0`
- `Mso20Win32Client!__imp_?CrashWithRecoveryOnOOM@@YAXI@Z` at `0x18001f7d0`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18001f6fd`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x18001f6fd`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f73d`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f7a8`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f805`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f82c`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f73d`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f7a8`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f805`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x18001f82c`

## string_xrefs

- `0x18001f728`: `CacheManager::AcquireLock - Failed to aquire lock.`
- `0x18001f7bd`: `CacheManager::AcquireLock - can't access CacheManager singleton - exceeded error reporting limit, so further error messages will not be emitted.`
- `0x18001f796`: `CacheManager::AcquireLock - can't access CacheManager singleton.`
- `0x18001f81a`: `CacheManager::AcquireLock - lock instance failed to be created - exceeded error reporting limit, so further error messages will not be emitted.`
- `0x18001f7f3`: `CacheManager::AcquireLock - lock instance failed to be created.`

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
      v8 = ++dword_18052E29C == 100;
      if ( (unsigned int)dword_18052E29C < 0x64 )
      {
        Mso::Logging::MsoSendTraceTag(
          592545612,
          48,
          10,
          L"CacheManager::AcquireLock - can't access CacheManager singleton.");
        v8 = dword_18052E29C == 100;
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
  if ( !v4 && (unsigned int)++dword_18052E298 <= 0x64 )
  {
    Mso::Logging::MsoSendTraceTag(592545614, 48, 10, L"CacheManager::AcquireLock - lock instance failed to be created.");
    if ( dword_18052E298 == 100 )
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
0x18001f6c0  mov     rax, rsp
0x18001f6c3  mov     [rax+8], rbx
0x18001f6c7  mov     [rax+10h], rbp
0x18001f6cb  mov     [rax+18h], rsi
0x18001f6cf  mov     [rax+20h], rdi
0x18001f6d3  push    r14
0x18001f6d5  sub     rsp, 20h
0x18001f6d9  mov     rdi, rcx
0x18001f6dc  xor     ebp, ebp
0x18001f6de  mov     ebx, ebp
0x18001f6e0  mov     rsi, cs:?s_pInstance@?$TSingleton@VCacheManager@Cache@@@Ofc@@0PEAVCacheManager@Cache@@EA; Cache::CacheManager * Ofc::TSingleton<Cache::CacheManager>::s_pInstance
0x18001f6e7  cmp     rsi, 1
0x18001f6eb  cmovbe  rsi, rbp
0x18001f6ef  lea     r14d, [rbp+30h]
0x18001f6f3  test    rsi, rsi
0x18001f6f6  jz      short loc_18001F764
0x18001f6f8  xor     edx, edx
0x18001f6fa  lea     ecx, [rdx+20h]
0x18001f6fd  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x18001f703  test    rax, rax
0x18001f706  jz      loc_18001F7CB
0x18001f70c  mov     rdx, rsi; struct Cache::CacheManager *
0x18001f70f  mov     rcx, rax; this
0x18001f712  call    ??0CacheManagerLock@Cache@@QEAA@AEAVCacheManager@1@@Z; Cache::CacheManagerLock::CacheManagerLock(Cache::CacheManager &)
0x18001f717  mov     rbx, rax
0x18001f71a  test    rax, rax
0x18001f71d  jz      loc_18001F7D7
0x18001f723  test    rbx, rbx
0x18001f726  jnz     short loc_18001F743
0x18001f728  lea     r9, aCachemanagerAc_0; "CacheManager::AcquireLock - Failed to a"...
0x18001f72f  mov     r8d, 0Fh
0x18001f735  mov     edx, r14d
0x18001f738  mov     ecx, 2351874Ah
0x18001f73d  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x18001f743  mov     [rdi], rbx
0x18001f746  mov     rax, rdi
0x18001f749  mov     rbx, [rsp+28h+arg_0]
0x18001f74e  mov     rbp, [rsp+28h+arg_8]
0x18001f753  mov     rsi, [rsp+28h+arg_10]
0x18001f758  mov     rdi, [rsp+28h+arg_18]
0x18001f75d  add     rsp, 20h
0x18001f761  pop     r14
0x18001f763  retn
0x18001f764  test    dl, dl
0x18001f766  jnz     short loc_18001F76D
0x18001f768  mov     [rcx], rbp
0x18001f76b  jmp     short loc_18001F746
0x18001f76d  call    ?PInternalInstance@CacheManager@Cache@@SAPEAV12@XZ; Cache::CacheManager::PInternalInstance(void)
0x18001f772  mov     rsi, rax
0x18001f775  test    rax, rax
0x18001f778  jnz     loc_18001F6F8
0x18001f77e  mov     eax, cs:dword_18052E29C
0x18001f784  inc     eax
0x18001f786  mov     cs:dword_18052E29C, eax
0x18001f78c  mov     esi, 0Ah
0x18001f791  cmp     eax, 64h ; 'd'
0x18001f794  jnb     short loc_18001F7B7
0x18001f796  lea     r9, aCachemanagerAc_1; "CacheManager::AcquireLock - can't acces"...
0x18001f79d  mov     r8d, esi
0x18001f7a0  mov     edx, r14d
0x18001f7a3  mov     ecx, 2351874Ch
0x18001f7a8  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x18001f7ae  mov     eax, cs:dword_18052E29C
0x18001f7b4  cmp     eax, 64h ; 'd'
0x18001f7b7  jnz     loc_18001F728
0x18001f7bd  lea     r9, aCachemanagerAc_2; "CacheManager::AcquireLock - can't acces"...
0x18001f7c4  mov     ecx, 2351874Bh
0x18001f7c9  jmp     short loc_18001F826
0x18001f7cb  mov     ecx, 1F65259Dh
0x18001f7d0  call    cs:__imp_?CrashWithRecoveryOnOOM@@YAXI@Z; CrashWithRecoveryOnOOM(uint)
0x18001f7d6  int     3; Trap to Debugger
0x18001f7d7  mov     ecx, cs:dword_18052E298
0x18001f7dd  inc     ecx
0x18001f7df  mov     cs:dword_18052E298, ecx
0x18001f7e5  mov     esi, 0Ah
0x18001f7ea  cmp     ecx, 64h ; 'd'
0x18001f7ed  ja      loc_18001F723
0x18001f7f3  lea     r9, aCachemanagerAc; "CacheManager::AcquireLock - lock instan"...
0x18001f7fa  mov     r8d, esi
0x18001f7fd  mov     edx, r14d
0x18001f800  mov     ecx, 2351874Eh
0x18001f805  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x18001f80b  mov     ecx, cs:dword_18052E298
0x18001f811  cmp     ecx, 64h ; 'd'
0x18001f814  jnz     loc_18001F723
0x18001f81a  lea     r9, aCachemanagerAc_3; "CacheManager::AcquireLock - lock instan"...
0x18001f821  mov     ecx, 2351874Dh
0x18001f826  mov     r8d, esi
0x18001f829  mov     edx, r14d
0x18001f82c  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x18001f832  jmp     loc_18001F723
```
