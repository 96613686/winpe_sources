# wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)

- ea: `0x180004650`
- end: `0x18000467a`
- name: `?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z`
- size: `42`
- prototype: ``
- caller_count: `35`
- callee_count: `0`
- tags: ``

## callers

- `0x180002c90`
- `0x1800048c8`
- `0x18000496c`
- `0x180004a04`
- `0x180004d14`
- `0x180004e44`
- `0x180004f74`
- `0x1800050a4`
- `0x1800051d4`
- `0x180005304`
- `0x180005434`
- `0x180005564`
- `0x180005694`
- `0x1800057c4`
- `0x1800058f4`
- `0x180005a24`
- `0x18000797c`
- `0x180007a40`
- `0x180007ac0`
- `0x180007b08`
- `0x180007bec`
- `0x180007ccc`
- `0x180007d50`
- `0x1800080d4`
- `0x1800082cc`
- `0x180009cf0`
- `0x180009d78`
- `0x18000a23c`
- `0x18000a430`
- `0x18000bfac`
- `0x18000ca10`
- `0x18000de90`
- `0x18000e4c0`
- `0x18000e55c`
- `0x18000e6d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004663`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004663`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::AcquireSRWLockExclusive(RTL_SRWLOCK **a1, RTL_SRWLOCK *a2)
{
  AcquireSRWLockExclusive(a2);
  *a1 = a2;
  return a1;
}

```

## disassembly

```asm
0x180004650  mov     [rsp+arg_0], rbx
0x180004655  push    rdi
0x180004656  sub     rsp, 20h
0x18000465a  mov     rdi, rcx
0x18000465d  mov     rbx, rdx
0x180004660  mov     rcx, rdx; SRWLock
0x180004663  call    cs:__imp_AcquireSRWLockExclusive
0x180004669  mov     [rdi], rbx
0x18000466c  mov     rax, rdi
0x18000466f  mov     rbx, [rsp+28h+arg_0]
0x180004674  add     rsp, 20h
0x180004678  pop     rdi
0x180004679  retn
```
