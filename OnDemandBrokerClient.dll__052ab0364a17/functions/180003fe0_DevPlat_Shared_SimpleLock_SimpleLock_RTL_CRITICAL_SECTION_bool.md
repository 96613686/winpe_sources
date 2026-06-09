# DevPlat::Shared::SimpleLock::SimpleLock(_RTL_CRITICAL_SECTION *,bool)

- ea: `0x180003fe0`
- end: `0x180004002`
- name: `??0SimpleLock@Shared@DevPlat@@QEAA@PEAU_RTL_CRITICAL_SECTION@@_N@Z`
- size: `34`
- prototype: `DevPlat::Shared::SimpleLock *__fastcall(DevPlat::Shared::SimpleLock *this, struct _RTL_CRITICAL_SECTION *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180005230`
- `0x180005b70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003ff3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003ff3`

## pseudocode

```c
DevPlat::Shared::SimpleLock *__fastcall DevPlat::Shared::SimpleLock::SimpleLock(
        DevPlat::Shared::SimpleLock *this,
        struct _RTL_CRITICAL_SECTION *a2)
{
  *(_QWORD *)this = a2;
  *((_BYTE *)this + 8) = 0;
  EnterCriticalSection(a2);
  return this;
}

```

## disassembly

```asm
0x180003fe0  push    rbx
0x180003fe2  sub     rsp, 20h
0x180003fe6  mov     rbx, rcx
0x180003fe9  mov     [rcx], rdx
0x180003fec  mov     byte ptr [rcx+8], 0
0x180003ff0  mov     rcx, rdx; lpCriticalSection
0x180003ff3  call    cs:__imp_EnterCriticalSection
0x180003ff9  mov     rax, rbx
0x180003ffc  add     rsp, 20h
0x180004000  pop     rbx
0x180004001  retn
```
