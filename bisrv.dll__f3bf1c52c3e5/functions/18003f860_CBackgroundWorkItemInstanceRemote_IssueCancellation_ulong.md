# CBackgroundWorkItemInstanceRemote::IssueCancellation(ulong)

- ea: `0x18003f860`
- end: `0x18003f93b`
- name: `?IssueCancellation@CBackgroundWorkItemInstanceRemote@@UEAAJK@Z`
- size: `219`
- prototype: `__int64 __fastcall(CBackgroundWorkItemInstanceRemote *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18003f860`
- `0x180095010`

## import_xrefs

- `ntdll!RtlWakeAddressAll` at `0x18003f91c`
- `ntdll!RtlWakeAddressAll` at `0x18003f91c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003f884`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003f8f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003f884`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003f8f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f8c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f913`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f8c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003f913`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f88a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f8fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f88a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f8fd`

## pseudocode

```c
__int64 __fastcall CBackgroundWorkItemInstanceRemote::IssueCancellation(RTL_SRWLOCK *this, unsigned int a2)
{
  RTL_SRWLOCK *v2; // rsi
  PVOID v5; // r14
  int *v6; // rdi
  int Ptr; // eax
  unsigned int v8; // ebp

  v2 = this + 20;
  v5 = 0;
  AcquireSRWLockExclusive(this + 20);
  GetCurrentThreadId();
  v6 = (int *)&this[22];
  Ptr = (int)this[22].Ptr;
  if ( (Ptr & 3) == 0 )
  {
    v5 = this[23].Ptr;
    *v6 = Ptr | 2;
    HIDWORD(this[25].Ptr) = a2;
    this[23].Ptr = 0;
  }
  LODWORD(this[19].Ptr) = 0;
  ReleaseSRWLockExclusive(v2);
  if ( v5 )
  {
    v8 = (*(__int64 (__fastcall **)(PVOID, _QWORD))(*(_QWORD *)v5 + 24LL))(v5, a2);
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v5 + 16LL))(v5);
  }
  else
  {
    v8 = 0;
  }
  AcquireSRWLockExclusive(v2);
  GetCurrentThreadId();
  *v6 |= 4u;
  LODWORD(this[19].Ptr) = 0;
  ReleaseSRWLockExclusive(v2);
  RtlWakeAddressAll(&this[22]);
  return v8;
}

```

## disassembly

```asm
0x18003f860  mov     [rsp+arg_8], rbx
0x18003f865  mov     [rsp+arg_10], rbp
0x18003f86a  push    rsi
0x18003f86b  push    rdi
0x18003f86c  push    r14
0x18003f86e  sub     rsp, 20h
0x18003f872  lea     rsi, [rcx+0A0h]
0x18003f879  mov     rbx, rcx
0x18003f87c  mov     rcx, rsi; SRWLock
0x18003f87f  mov     ebp, edx
0x18003f881  xor     r14d, r14d
0x18003f884  call    cs:__imp_AcquireSRWLockExclusive
0x18003f88a  call    cs:__imp_GetCurrentThreadId
0x18003f890  lea     rdi, [rbx+0B0h]
0x18003f897  mov     eax, [rdi]
0x18003f899  test    al, 3
0x18003f89b  jnz     short loc_18003F8BA
0x18003f89d  mov     r14, [rbx+0B8h]
0x18003f8a4  or      eax, 2
0x18003f8a7  mov     [rdi], eax
0x18003f8a9  mov     [rbx+0CCh], ebp
0x18003f8af  mov     qword ptr [rbx+0B8h], 0
0x18003f8ba  mov     rcx, rsi; SRWLock
0x18003f8bd  mov     dword ptr [rbx+98h], 0
0x18003f8c7  call    cs:__imp_ReleaseSRWLockExclusive
0x18003f8cd  test    r14, r14
0x18003f8d0  jz      short loc_18003F937
0x18003f8d2  mov     rax, [r14]
0x18003f8d5  mov     edx, ebp
0x18003f8d7  mov     rcx, r14
0x18003f8da  mov     rax, [rax+18h]
0x18003f8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8e3  mov     ebp, eax
0x18003f8e5  mov     rdx, [r14]
0x18003f8e8  mov     rcx, r14
0x18003f8eb  mov     rax, [rdx+10h]
0x18003f8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f8f4  mov     rcx, rsi; SRWLock
0x18003f8f7  call    cs:__imp_AcquireSRWLockExclusive
0x18003f8fd  call    cs:__imp_GetCurrentThreadId
0x18003f903  or      dword ptr [rdi], 4
0x18003f906  mov     rcx, rsi; SRWLock
0x18003f909  mov     dword ptr [rbx+98h], 0
0x18003f913  call    cs:__imp_ReleaseSRWLockExclusive
0x18003f919  mov     rcx, rdi
0x18003f91c  call    cs:__imp_RtlWakeAddressAll
0x18003f922  mov     rbx, [rsp+38h+arg_8]
0x18003f927  mov     eax, ebp
0x18003f929  mov     rbp, [rsp+38h+arg_10]
0x18003f92e  add     rsp, 20h
0x18003f932  pop     r14
0x18003f934  pop     rdi
0x18003f935  pop     rsi
0x18003f936  retn
0x18003f937  xor     ebp, ebp
0x18003f939  jmp     short loc_18003F8F4
```
