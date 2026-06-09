# GameInputClient::CreateDispatcher(IGameInputDispatcher * *)

- ea: `0x1800055a0`
- end: `0x1800056c0`
- name: `?CreateDispatcher@GameInputClient@@UEAAJPEAPEAUIGameInputDispatcher@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(GameInputClient *__hidden this, struct IGameInputDispatcher **)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x1800055a0`
- `0x1800065d8`
- `0x180007e80`
- `0x18000b6c8`
- `0x18000d68c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800055bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000565e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800055bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000565e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800055fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000564a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005687`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005696`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800055fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000564a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005687`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005696`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000560e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000560e`

## pseudocode

```c
__int64 __fastcall GameInputClient::CreateDispatcher(RTL_SRWLOCK *this, RTL_SRWLOCK **a2)
{
  RTL_SRWLOCK *v2; // rdi
  RTL_SRWLOCK *v4; // rbp
  unsigned int v5; // esi
  int v6; // ebx

  v2 = this + 26;
  v4 = this + 28;
  AcquireSRWLockExclusive(this + 28);
  if ( v2[8].Ptr == (PVOID)-1LL )
  {
    v2[8].Ptr = (PVOID)(GetTickCount64() + 1000);
    _mm_mfence();
    v5 = 0;
    v6 = GameInputDispatcher::SignalThread((GameInputDispatcher *)v2);
    if ( v6 >= 0 )
    {
      AcquireSRWLockExclusive(v2 + 3);
      _InterlockedIncrement((volatile signed __int32 *)&v2[1]);
      GameInputClient::IncrementGlobalObjectCount();
      ++dword_1800696A0;
      GameInputClientDebugRefCountCheck();
      *a2 = v2;
      ReleaseSRWLockExclusive(v2 + 3);
      ReleaseSRWLockExclusive(v4);
    }
    else
    {
      v2[8].Ptr = (PVOID)-1LL;
      _mm_mfence();
      *a2 = 0;
      ReleaseSRWLockExclusive(v4);
      return (unsigned int)v6;
    }
  }
  else
  {
    if ( (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&v2[1]) <= 1 )
    {
      GameInputFailFast(2147500036LL, 143);
      JUMPOUT(0x1800056BFLL);
    }
    ++dword_1800696C8;
    GameInputClientDebugRefCountCheck();
    *a2 = v2;
    ReleaseSRWLockExclusive(v4);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800055a0  push    rbx
0x1800055a2  push    rbp
0x1800055a3  push    rsi
0x1800055a4  push    rdi
0x1800055a5  push    r14
0x1800055a7  sub     rsp, 20h
0x1800055ab  lea     rdi, [rcx+0D0h]
0x1800055b2  mov     r14, rdx
0x1800055b5  lea     rbp, [rdi+10h]
0x1800055b9  mov     rcx, rbp; SRWLock
0x1800055bc  call    cs:__imp_AcquireSRWLockExclusive
0x1800055c3  nop     dword ptr [rax+rax+00h]
0x1800055c8  mov     rax, [rdi+40h]
0x1800055cc  nop
0x1800055cd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800055d1  jz      short loc_18000560E
0x1800055d3  nop
0x1800055d4  mov     eax, 1
0x1800055d9  lock xadd [rdi+8], eax
0x1800055de  inc     eax
0x1800055e0  nop
0x1800055e1  cmp     eax, 1
0x1800055e4  jbe     loc_1800056B0
0x1800055ea  inc     cs:dword_1800696C8
0x1800055f0  call    GameInputClientDebugRefCountCheck
0x1800055f5  mov     rcx, rbp; SRWLock
0x1800055f8  mov     [r14], rdi
0x1800055fb  call    cs:__imp_ReleaseSRWLockExclusive
0x180005602  nop     dword ptr [rax+rax+00h]
0x180005607  xor     esi, esi
0x180005609  jmp     loc_1800056A2
0x18000560e  call    cs:__imp_GetTickCount64
0x180005615  nop     dword ptr [rax+rax+00h]
0x18000561a  add     rax, 3E8h
0x180005620  nop
0x180005621  mov     [rdi+40h], rax
0x180005625  mfence
0x180005628  mov     rcx, rdi; this
0x18000562b  call    ?SignalThread@GameInputDispatcher@@AEAAJXZ; GameInputDispatcher::SignalThread(void)
0x180005630  xor     esi, esi
0x180005632  mov     ebx, eax
0x180005634  test    eax, eax
0x180005636  jns     short loc_18000565A
0x180005638  nop
0x180005639  mov     qword ptr [rdi+40h], 0FFFFFFFFFFFFFFFFh
0x180005641  mfence
0x180005644  mov     rcx, rbp; SRWLock
0x180005647  mov     [r14], rsi
0x18000564a  call    cs:__imp_ReleaseSRWLockExclusive
0x180005651  nop     dword ptr [rax+rax+00h]
0x180005656  mov     esi, ebx
0x180005658  jmp     short loc_1800056A2
0x18000565a  lea     rcx, [rdi+18h]; SRWLock
0x18000565e  call    cs:__imp_AcquireSRWLockExclusive
0x180005665  nop     dword ptr [rax+rax+00h]
0x18000566a  nop
0x18000566b  lock inc dword ptr [rdi+8]
0x18000566f  nop
0x180005670  call    ?IncrementGlobalObjectCount@GameInputClient@@SAXXZ; GameInputClient::IncrementGlobalObjectCount(void)
0x180005675  inc     cs:dword_1800696A0
0x18000567b  call    GameInputClientDebugRefCountCheck
0x180005680  lea     rcx, [rdi+18h]; SRWLock
0x180005684  mov     [r14], rdi
0x180005687  call    cs:__imp_ReleaseSRWLockExclusive
0x18000568e  nop     dword ptr [rax+rax+00h]
0x180005693  mov     rcx, rbp; SRWLock
0x180005696  call    cs:__imp_ReleaseSRWLockExclusive
0x18000569d  nop     dword ptr [rax+rax+00h]
0x1800056a2  mov     eax, esi
0x1800056a4  add     rsp, 20h
0x1800056a8  pop     r14
0x1800056aa  pop     rdi
0x1800056ab  pop     rsi
0x1800056ac  pop     rbp
0x1800056ad  pop     rbx
0x1800056ae  retn
0x1800056b0  mov     edx, 8Fh
0x1800056b5  mov     ecx, 80004004h
0x1800056ba  call    GameInputFailFast
```
