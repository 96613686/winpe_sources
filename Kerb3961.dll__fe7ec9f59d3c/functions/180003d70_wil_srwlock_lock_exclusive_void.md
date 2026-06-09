# wil::srwlock::lock_exclusive(void)

- ea: `0x180003d70`
- end: `0x180003d97`
- name: `?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180003410`
- `0x180003610`
- `0x180003dd0`
- `0x180003eb0`
- `0x180004040`
- `0x18000a2a0`
- `0x18000b024`
- `0x18000c3a0`
- `0x18000c4c8`
- `0x18000d1ec`
- `0x18000d8b0`
- `0x18000de50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003d80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003d80`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::srwlock::lock_exclusive(RTL_SRWLOCK *a1, RTL_SRWLOCK **a2)
{
  AcquireSRWLockExclusive(a1);
  *a2 = a1;
  return a2;
}

```

## disassembly

```asm
0x180003d70  mov     [rsp+arg_0], rbx
0x180003d75  push    rdi
0x180003d76  sub     rsp, 20h
0x180003d7a  mov     rdi, rdx
0x180003d7d  mov     rbx, rcx
0x180003d80  call    cs:__imp_AcquireSRWLockExclusive
0x180003d86  mov     [rdi], rbx
0x180003d89  mov     rax, rdi
0x180003d8c  mov     rbx, [rsp+28h+arg_0]
0x180003d91  add     rsp, 20h
0x180003d95  pop     rdi
0x180003d96  retn
```
