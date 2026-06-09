# SilentTSAutologonManager::EnsureCredentialThreadStarted(void)

- ea: `0x18005db5c`
- end: `0x18005dce6`
- name: `?EnsureCredentialThreadStarted@SilentTSAutologonManager@@AEAAJXZ`
- size: `394`
- prototype: `__int64 __fastcall(SilentTSAutologonManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800697f4`

## callees

- `0x180004c00`
- `0x180026e70`
- `0x18004daec`
- `0x18005d488`
- `0x18005d4e8`
- `0x18005db5c`
- `0x18005dcec`
- `0x18005f55c`
- `0x18007fc88`

## import_xrefs

- `KERNEL32!CreateEventExW` at `0x18005dbac`
- `KERNEL32!CreateEventExW` at `0x18005dbac`
- `KERNEL32!CreateSemaphoreExW` at `0x18005dc2d`
- `KERNEL32!CreateSemaphoreExW` at `0x18005dc2d`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005dbf0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005dcce`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005dbf0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18005dcce`
- `SHCORE!SHCreateThreadWithHandle` at `0x18005dc9d`
- `SHCORE!SHCreateThreadWithHandle` at `0x18005dc9d`

## pseudocode

```c
__int64 __fastcall SilentTSAutologonManager::EnsureCredentialThreadStarted(SilentTSAutologonManager *this)
{
  HANDLE Event; // rax
  int Error; // ebx
  __int64 v4; // rdx
  HANDLE Semaphore; // rax
  const char *v7; // r9
  int dwFlags; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  PSRWLOCK SRWLock; // [rsp+40h] [rbp+8h] BYREF

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, (char *)this + 80);
  if ( !*((_QWORD *)this + 17) )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 144,
      0);
    Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
    *((_QWORD *)this + 18) = Event;
    if ( !Event )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        v4 = 467;
LABEL_5:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v4,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\silenttsautologonmanager.cpp",
          (const char *)(unsigned int)Error,
          dwFlags);
LABEL_6:
        SilentTSAutologonManager::ShutdownCredentialThreadLockHeld(this);
        if ( SRWLock )
          ReleaseSRWLockExclusive(SRWLock);
        return (unsigned int)Error;
      }
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 152,
      0);
    Semaphore = CreateSemaphoreExW(0, 1, 2147483646, 0, 0, 0x1F0003u);
    *((_QWORD *)this + 19) = Semaphore;
    if ( !Semaphore )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        v4 = 468;
        goto LABEL_5;
      }
    }
    Microsoft::WRL::ComPtr<OptionalDependencyProvider>::InternalRelease((char *)this + 160);
    Error = Microsoft::WRL::Details::MakeAndInitialize<EventDispatcher,EventDispatcher,>((char *)this + 160);
    if ( Error < 0 )
    {
      v4 = 469;
      goto LABEL_5;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 136,
      0);
    if ( !SHCreateThreadWithHandle(
            SilentTSAutologonManager::s_CredentialStackThreadProc,
            this,
            8u,
            SilentTSAutologonManager::s_CredentialStackStartThreadProc,
            (HANDLE *)this + 17) )
    {
      Error = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)0x1DC,
                (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\silenttsautologonmanager.cpp",
                v7);
      goto LABEL_6;
    }
  }
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return 0;
}

```

## disassembly

```asm
0x18005db5c  mov     [rsp+arg_8], rbx
0x18005db61  mov     [rsp+arg_10], rsi
0x18005db66  push    rdi
0x18005db67  sub     rsp, 30h
0x18005db6b  mov     rdi, rcx
0x18005db6e  lea     rdx, [rcx+50h]
0x18005db72  lea     rcx, [rsp+38h+SRWLock]
0x18005db77  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18005db7c  lea     rsi, [rdi+88h]
0x18005db83  cmp     qword ptr [rsi], 0
0x18005db87  jnz     loc_18005DCC4
0x18005db8d  lea     rbx, [rdi+90h]
0x18005db94  xor     edx, edx
0x18005db96  mov     rcx, rbx
0x18005db99  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18005db9e  xor     edx, edx; lpName
0x18005dba0  xor     ecx, ecx; lpEventAttributes
0x18005dba2  mov     r9d, 1F0003h; dwDesiredAccess
0x18005dba8  lea     r8d, [rdx+1]; dwFlags
0x18005dbac  call    cs:__imp_CreateEventExW
0x18005dbb2  mov     [rbx], rax
0x18005dbb5  test    rax, rax
0x18005dbb8  jnz     short loc_18005DBFD
0x18005dbba  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005dbbf  mov     ebx, eax
0x18005dbc1  test    eax, eax
0x18005dbc3  jns     short loc_18005DBFD
0x18005dbc5  mov     edx, 1D3h; void *
0x18005dbca  mov     rcx, [rsp+38h]; this
0x18005dbcf  lea     r8, aPcshellShellAu_1; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005dbd6  mov     r9d, ebx; char *
0x18005dbd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005dbde  mov     rcx, rdi; this
0x18005dbe1  call    ?ShutdownCredentialThreadLockHeld@SilentTSAutologonManager@@AEAAXXZ; SilentTSAutologonManager::ShutdownCredentialThreadLockHeld(void)
0x18005dbe6  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x18005dbeb  test    rcx, rcx
0x18005dbee  jz      short loc_18005DBF6
0x18005dbf0  call    cs:__imp_ReleaseSRWLockExclusive
0x18005dbf6  mov     eax, ebx
0x18005dbf8  jmp     loc_18005DCD6
0x18005dbfd  lea     rbx, [rdi+98h]
0x18005dc04  xor     edx, edx
0x18005dc06  mov     rcx, rbx
0x18005dc09  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18005dc0e  xor     r9d, r9d; lpName
0x18005dc11  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18005dc19  xor     ecx, ecx; lpSemaphoreAttributes
0x18005dc1b  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18005dc23  mov     r8d, 7FFFFFFEh; lMaximumCount
0x18005dc29  lea     edx, [r9+1]; lInitialCount
0x18005dc2d  call    cs:__imp_CreateSemaphoreExW
0x18005dc33  mov     [rbx], rax
0x18005dc36  test    rax, rax
0x18005dc39  jnz     short loc_18005DC50
0x18005dc3b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005dc40  mov     ebx, eax
0x18005dc42  test    eax, eax
0x18005dc44  jns     short loc_18005DC50
0x18005dc46  mov     edx, 1D4h
0x18005dc4b  jmp     loc_18005DBCA
0x18005dc50  lea     rbx, [rdi+0A0h]
0x18005dc57  mov     rcx, rbx
0x18005dc5a  call    ?InternalRelease@?$ComPtr@VOptionalDependencyProvider@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OptionalDependencyProvider>::InternalRelease(void)
0x18005dc5f  mov     rcx, rbx
0x18005dc62  call    ??$MakeAndInitialize@VEventDispatcher@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVEventDispatcher@@@Z; Microsoft::WRL::Details::MakeAndInitialize<EventDispatcher,EventDispatcher,>(EventDispatcher * *)
0x18005dc67  mov     ebx, eax
0x18005dc69  test    eax, eax
0x18005dc6b  jns     short loc_18005DC77
0x18005dc6d  mov     edx, 1D5h
0x18005dc72  jmp     loc_18005DBCA
0x18005dc77  xor     edx, edx
0x18005dc79  mov     rcx, rsi
0x18005dc7c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18005dc81  lea     r9, ?s_CredentialStackStartThreadProc@SilentTSAutologonManager@@CAKPEAX@Z; pfnCallback
0x18005dc88  mov     qword ptr [rsp+38h+dwFlags], rsi; pHandle
0x18005dc8d  mov     r8d, 8; flags
0x18005dc93  lea     rcx, ?s_CredentialStackThreadProc@SilentTSAutologonManager@@CAKPEAX@Z; pfnThreadProc
0x18005dc9a  mov     rdx, rdi; pData
0x18005dc9d  call    cs:__imp_SHCreateThreadWithHandle
0x18005dca3  test    eax, eax
0x18005dca5  jnz     short loc_18005DCC4
0x18005dca7  mov     rcx, [rsp+38h]; this
0x18005dcac  lea     r8, aPcshellShellAu_1; "pcshell\\shell\\auth\\authux\\controlle"...
0x18005dcb3  mov     edx, 1DCh; void *
0x18005dcb8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005dcbd  mov     ebx, eax
0x18005dcbf  jmp     loc_18005DBDE
0x18005dcc4  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x18005dcc9  test    rcx, rcx
0x18005dccc  jz      short loc_18005DCD4
0x18005dcce  call    cs:__imp_ReleaseSRWLockExclusive
0x18005dcd4  xor     eax, eax
0x18005dcd6  mov     rbx, [rsp+38h+arg_8]
0x18005dcdb  mov     rsi, [rsp+38h+arg_10]
0x18005dce0  add     rsp, 30h
0x18005dce4  pop     rdi
0x18005dce5  retn
```
