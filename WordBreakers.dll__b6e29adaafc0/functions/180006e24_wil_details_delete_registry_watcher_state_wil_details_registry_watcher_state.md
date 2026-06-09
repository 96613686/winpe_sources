# wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *)

- ea: `0x180006e24`
- end: `0x180006eaa`
- name: `?delete_registry_watcher_state@details@wil@@YAXPEAUregistry_watcher_state@12@@Z`
- size: `134`
- prototype: `void __fastcall(wil::details *__hidden this, struct wil::details::registry_watcher_state *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x18000bdf0`

## callees

- `0x180003e78`
- `0x180006e24`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006e84`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006e84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006e5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006e6e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006e6e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006e66`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006e94`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006e66`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006e94`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006e40`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006e40`

## pseudocode

```c
void __fastcall wil::details::delete_registry_watcher_state(
        wil::details *this,
        struct wil::details::registry_watcher_state *a2)
{
  RTL_SRWLOCK *v2; // rsi
  DWORD LastError; // ebx

  v2 = (RTL_SRWLOCK *)((char *)this + 152);
  AcquireSRWLockExclusive((PSRWLOCK)this + 19);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 37, 0xFFFFFFFF) == 1 )
  {
    if ( v2 )
    {
      LastError = GetLastError();
      ReleaseSRWLockExclusive(v2);
      SetLastError(LastError);
    }
    if ( this )
    {
      wil::details::registry_watcher_state::~registry_watcher_state(this);
      operator delete(this);
    }
  }
  else if ( v2 )
  {
    ReleaseSRWLockExclusive(v2);
  }
}

```

## disassembly

```asm
0x180006e24  mov     [rsp+arg_0], rbx
0x180006e29  mov     [rsp+arg_8], rsi
0x180006e2e  push    rdi
0x180006e2f  sub     rsp, 20h
0x180006e33  lea     rsi, [rcx+98h]
0x180006e3a  mov     rdi, rcx
0x180006e3d  mov     rcx, rsi; SRWLock
0x180006e40  call    cs:__imp_AcquireSRWLockExclusive
0x180006e46  or      eax, 0FFFFFFFFh
0x180006e49  lock xadd [rdi+94h], eax
0x180006e51  cmp     eax, 1
0x180006e54  jnz     short loc_180006E8C
0x180006e56  test    rsi, rsi
0x180006e59  jz      short loc_180006E74
0x180006e5b  call    cs:__imp_GetLastError
0x180006e61  mov     rcx, rsi; SRWLock
0x180006e64  mov     ebx, eax
0x180006e66  call    cs:__imp_ReleaseSRWLockExclusive
0x180006e6c  mov     ecx, ebx; dwErrCode
0x180006e6e  call    cs:__imp_SetLastError
0x180006e74  test    rdi, rdi
0x180006e77  jz      short loc_180006E9A
0x180006e79  mov     rcx, rdi; this
0x180006e7c  call    ??1registry_watcher_state@details@wil@@QEAA@XZ; wil::details::registry_watcher_state::~registry_watcher_state(void)
0x180006e81  mov     rcx, rdi
0x180006e84  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006e8a  jmp     short loc_180006E9A
0x180006e8c  test    rsi, rsi
0x180006e8f  jz      short loc_180006E9A
0x180006e91  mov     rcx, rsi; SRWLock
0x180006e94  call    cs:__imp_ReleaseSRWLockExclusive
0x180006e9a  mov     rbx, [rsp+28h+arg_0]
0x180006e9f  mov     rsi, [rsp+28h+arg_8]
0x180006ea4  add     rsp, 20h
0x180006ea8  pop     rdi
0x180006ea9  retn
```
