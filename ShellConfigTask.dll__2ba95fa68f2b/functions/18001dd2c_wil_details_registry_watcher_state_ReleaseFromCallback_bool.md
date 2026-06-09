# wil::details::registry_watcher_state::ReleaseFromCallback(bool)

- ea: `0x18001dd2c`
- end: `0x18001ddeb`
- name: `?ReleaseFromCallback@registry_watcher_state@details@wil@@QEAAX_N@Z`
- size: `191`
- prototype: `void __fastcall(wil::details::registry_watcher_state *__hidden this, bool)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1800217b0`

## callees

- `0x1800025b4`
- `0x1800142c0`
- `0x18001dd2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dd90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001dd90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd7d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001dd4a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001dd4a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dd88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ddd5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dd88`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001ddd5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001dd72`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001dd72`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001ddc7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001ddc7`

## pseudocode

```c
void __fastcall wil::details::registry_watcher_state::ReleaseFromCallback(
        wil::details::registry_watcher_state *this,
        char a2)
{
  RTL_SRWLOCK *v2; // rsi
  struct _TP_WAIT *v5; // rcx
  DWORD LastError; // ebx

  v2 = (RTL_SRWLOCK *)((char *)this + 152);
  AcquireSRWLockExclusive((PSRWLOCK)this + 19);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 37, 0xFFFFFFFF) == 1 )
  {
    v5 = (struct _TP_WAIT *)*((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = 0;
    CloseThreadpoolWait(v5);
    if ( v2 )
    {
      LastError = GetLastError();
      ReleaseSRWLockExclusive(v2);
      SetLastError(LastError);
    }
    if ( this )
    {
      wil::details::registry_watcher_state::~registry_watcher_state(this);
      operator delete(this, (const struct std::nothrow_t *)0xA0);
    }
  }
  else
  {
    if ( a2 )
      SetThreadpoolWait(*((PTP_WAIT *)this + 17), *((HANDLE *)this + 16), 0);
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
  }
}

```

## disassembly

```asm
0x18001dd2c  mov     [rsp+arg_0], rbx
0x18001dd31  mov     [rsp+arg_8], rsi
0x18001dd36  push    rdi
0x18001dd37  sub     rsp, 20h
0x18001dd3b  lea     rsi, [rcx+98h]
0x18001dd42  mov     rdi, rcx
0x18001dd45  mov     rcx, rsi; SRWLock
0x18001dd48  mov     bl, dl
0x18001dd4a  call    cs:__imp_AcquireSRWLockExclusive
0x18001dd50  or      eax, 0FFFFFFFFh
0x18001dd53  lock xadd [rdi+94h], eax
0x18001dd5b  cmp     eax, 1
0x18001dd5e  jnz     short loc_18001DDB2
0x18001dd60  mov     rcx, [rdi+88h]; pwa
0x18001dd67  mov     qword ptr [rdi+88h], 0
0x18001dd72  call    cs:__imp_CloseThreadpoolWait
0x18001dd78  test    rsi, rsi
0x18001dd7b  jz      short loc_18001DD96
0x18001dd7d  call    cs:__imp_GetLastError
0x18001dd83  mov     rcx, rsi; SRWLock
0x18001dd86  mov     ebx, eax
0x18001dd88  call    cs:__imp_ReleaseSRWLockExclusive
0x18001dd8e  mov     ecx, ebx; dwErrCode
0x18001dd90  call    cs:__imp_SetLastError
0x18001dd96  test    rdi, rdi
0x18001dd99  jz      short loc_18001DDDB
0x18001dd9b  mov     rcx, rdi; this
0x18001dd9e  call    ??1registry_watcher_state@details@wil@@QEAA@XZ; wil::details::registry_watcher_state::~registry_watcher_state(void)
0x18001dda3  mov     edx, 0A0h; struct std::nothrow_t *
0x18001dda8  mov     rcx, rdi; void *
0x18001ddab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ddb0  jmp     short loc_18001DDDB
0x18001ddb2  test    bl, bl
0x18001ddb4  jz      short loc_18001DDCD
0x18001ddb6  mov     rdx, [rdi+80h]; h
0x18001ddbd  xor     r8d, r8d; pftTimeout
0x18001ddc0  mov     rcx, [rdi+88h]; pwa
0x18001ddc7  call    cs:__imp_SetThreadpoolWait
0x18001ddcd  test    rsi, rsi
0x18001ddd0  jz      short loc_18001DDDB
0x18001ddd2  mov     rcx, rsi; SRWLock
0x18001ddd5  call    cs:__imp_ReleaseSRWLockExclusive
0x18001dddb  mov     rbx, [rsp+28h+arg_0]
0x18001dde0  mov     rsi, [rsp+28h+arg_8]
0x18001dde5  add     rsp, 20h
0x18001dde9  pop     rdi
0x18001ddea  retn
```
