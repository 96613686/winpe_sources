# wil::srwlock::lock_shared(void)

- ea: `0x180003da0`
- end: `0x180003dc7`
- name: `?lock_shared@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b3d0`
- `0x18000b660`
- `0x18000b750`
- `0x18000b920`
- `0x18000ba20`
- `0x18000c060`
- `0x18000ca80`
- `0x18000cdb0`
- `0x18000cfd0`
- `0x18000d510`
- `0x18000d6e0`
- `0x18000d960`
- `0x18000db90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003db0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180003db0`

## pseudocode

```c
RTL_SRWLOCK **__fastcall wil::srwlock::lock_shared(RTL_SRWLOCK *a1, RTL_SRWLOCK **a2)
{
  AcquireSRWLockShared(a1);
  *a2 = a1;
  return a2;
}

```

## disassembly

```asm
0x180003da0  mov     [rsp+arg_0], rbx
0x180003da5  push    rdi
0x180003da6  sub     rsp, 20h
0x180003daa  mov     rdi, rdx
0x180003dad  mov     rbx, rcx
0x180003db0  call    cs:__imp_AcquireSRWLockShared
0x180003db6  mov     [rdi], rbx
0x180003db9  mov     rax, rdi
0x180003dbc  mov     rbx, [rsp+28h+arg_0]
0x180003dc1  add     rsp, 20h
0x180003dc5  pop     rdi
0x180003dc6  retn
```
