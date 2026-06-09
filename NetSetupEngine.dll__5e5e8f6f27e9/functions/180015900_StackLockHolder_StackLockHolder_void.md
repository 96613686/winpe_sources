# StackLockHolder::~StackLockHolder(void)

- ea: `0x180015900`
- end: `0x18001597f`
- name: `??1StackLockHolder@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(StackLockHolder *__hidden this)`
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x180008c90`
- `0x18000a460`
- `0x180011e54`
- `0x180012220`
- `0x1800154ac`
- `0x1800291d4`
- `0x1800443fc`
- `0x180045544`
- `0x18006056c`
- `0x180067594`
- `0x180067670`
- `0x180067b00`
- `0x180067c60`
- `0x180067cc0`
- `0x180081e10`
- `0x180081ee0`
- `0x180082000`
- `0x180082b31`
- `0x1800830f0`
- `0x1800877b7`
- `0x1800891fc`
- `0x18008924a`

## callees

- `0x180015900`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015952`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015977`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015952`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015977`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001591f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001591f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015925`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015925`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18001595b`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18001595b`

## pseudocode

```c
void __fastcall StackLockHolder::~StackLockHolder(StackLockHolder *this)
{
  __int64 v1; // rbx
  RTL_SRWLOCK *v2; // rcx
  __int64 v3; // rax

  if ( *((_BYTE *)this + 32) )
  {
    v1 = *(_QWORD *)this;
    *((_BYTE *)this + 32) = 0;
    AcquireSRWLockExclusive((PSRWLOCK)(v1 + 8));
    *(_DWORD *)(v1 + 16) = GetCurrentThreadId();
    v2 = (RTL_SRWLOCK *)(v1 + 8);
    --*(_DWORD *)(*(_QWORD *)(v1 + 24) + 8LL);
    v3 = *(_QWORD *)(v1 + 24);
    if ( *(_DWORD *)(v3 + 8) )
    {
      *(_DWORD *)(v1 + 16) = 0;
      ReleaseSRWLockExclusive(v2);
    }
    else
    {
      *(_QWORD *)(v1 + 24) = *(_QWORD *)(v3 + 16);
      *(_DWORD *)(v1 + 16) = 0;
      ReleaseSRWLockExclusive(v2);
      WakeAllConditionVariable((PCONDITION_VARIABLE)v1);
    }
  }
}

```

## disassembly

```asm
0x180015900  sub     rsp, 28h
0x180015904  cmp     byte ptr [rcx+20h], 0
0x180015908  jz      short loc_18001596B
0x18001590a  mov     [rsp+28h+arg_0], rbx
0x18001590f  mov     rbx, [rcx]
0x180015912  mov     byte ptr [rcx+20h], 0
0x180015916  mov     [rsp+28h+var_8], rdi
0x18001591b  lea     rcx, [rbx+8]; SRWLock
0x18001591f  call    cs:__imp_AcquireSRWLockExclusive
0x180015925  call    cs:__imp_GetCurrentThreadId
0x18001592b  mov     [rbx+10h], eax
0x18001592e  lea     rcx, [rbx+8]; SRWLock
0x180015932  mov     rax, [rbx+18h]
0x180015936  dec     dword ptr [rax+8]
0x180015939  mov     rax, [rbx+18h]
0x18001593d  cmp     dword ptr [rax+8], 0
0x180015941  jnz     short loc_180015970
0x180015943  mov     rax, [rax+10h]
0x180015947  mov     [rbx+18h], rax
0x18001594b  mov     dword ptr [rbx+10h], 0
0x180015952  call    cs:__imp_ReleaseSRWLockExclusive
0x180015958  mov     rcx, rbx; ConditionVariable
0x18001595b  call    cs:__imp_WakeAllConditionVariable
0x180015961  mov     rbx, [rsp+28h+arg_0]
0x180015966  mov     rdi, [rsp+28h+var_8]
0x18001596b  add     rsp, 28h
0x18001596f  retn
0x180015970  mov     dword ptr [rbx+10h], 0
0x180015977  call    cs:__imp_ReleaseSRWLockExclusive
0x18001597d  jmp     short loc_180015961
```
