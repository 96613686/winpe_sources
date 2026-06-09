# StateRepository::ProcessShutdown

- ea: `0x18001704c`
- end: `0x1800170a9`
- name: `StateRepository::ProcessShutdown`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180016dcc`
- `0x18001792c`

## callees

- `0x18001704c`
- `0x18002974c`
- `0x1800297a8`

## import_xrefs

- `StateRepository.Core!sqlite3_shutdown` at `0x18001708a`
- `StateRepository.Core!sqlite3_shutdown` at `0x18001708a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_CacheShutdown` at `0x18001706e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_CacheShutdown` at `0x18001706e`

## pseudocode

```c
__int64 __fastcall StateRepository::ProcessShutdown(char a1)
{
  int v1; // ebx
  int v2; // eax
  int v3; // eax
  signed int v4; // eax

  v1 = 0;
  if ( (a1 & 2) == 0 && _InterlockedExchangeAdd(&dword_18004BDE8, 0xFFFFFFFF) == 1 )
  {
    if ( (a1 & 4) == 0 )
      v1 = SRCacheContext_CacheShutdown();
    v2 = StateRepository::DatabaseCacheSingleton::Shutdown();
    if ( v1 >= 0 )
      v1 = v2;
    v3 = StateRepository::VfsNoImpersonation::Unregister();
    if ( v1 >= 0 )
      v1 = v3;
    v4 = sqlite3_shutdown();
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x87AF0000;
    if ( v1 >= 0 )
      return (unsigned int)v4;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001704c  push    rbx
0x18001704e  sub     rsp, 20h
0x180017052  xor     ebx, ebx
0x180017054  test    cl, 2
0x180017057  jnz     short loc_1800170A1
0x180017059  or      eax, 0FFFFFFFFh
0x18001705c  lock xadd cs:dword_18004BDE8, eax
0x180017064  cmp     eax, 1
0x180017067  jnz     short loc_1800170A1
0x180017069  test    cl, 4
0x18001706c  jnz     short loc_180017076
0x18001706e  call    cs:__imp_SRCacheContext_CacheShutdown
0x180017074  mov     ebx, eax
0x180017076  call    ?Shutdown@DatabaseCacheSingleton@StateRepository@@SAJXZ; StateRepository::DatabaseCacheSingleton::Shutdown(void)
0x18001707b  test    ebx, ebx
0x18001707d  cmovns  ebx, eax
0x180017080  call    ?Unregister@VfsNoImpersonation@StateRepository@@SAJXZ; StateRepository::VfsNoImpersonation::Unregister(void)
0x180017085  test    ebx, ebx
0x180017087  cmovns  ebx, eax
0x18001708a  call    cs:__imp_sqlite3_shutdown
0x180017090  test    eax, eax
0x180017092  jle     short loc_18001709C
0x180017094  movzx   eax, ax
0x180017097  or      eax, 87AF0000h
0x18001709c  test    ebx, ebx
0x18001709e  cmovns  ebx, eax
0x1800170a1  mov     eax, ebx
0x1800170a3  add     rsp, 20h
0x1800170a7  pop     rbx
0x1800170a8  retn
```
