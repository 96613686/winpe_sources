# Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)

- ea: `0x18000dd50`
- end: `0x18000dd7b`
- name: `??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001080a`
- `0x18001081c`
- `0x1800108ac`
- `0x1800108be`

## callees

- `0x18000dd50`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000dd61`
- `KERNEL32!LeaveCriticalSection` at `0x18000dd61`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(
        struct _RTL_CRITICAL_SECTION **this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    LeaveCriticalSection(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x18000dd50  push    rbx
0x18000dd52  sub     rsp, 20h
0x18000dd56  mov     rbx, rcx
0x18000dd59  mov     rcx, [rcx]; lpCriticalSection
0x18000dd5c  test    rcx, rcx
0x18000dd5f  jz      short loc_18000DD74
0x18000dd61  call    cs:__imp_LeaveCriticalSection
0x18000dd68  nop     dword ptr [rax+rax+00h]
0x18000dd6d  mov     qword ptr [rbx], 0
0x18000dd74  add     rsp, 20h
0x18000dd78  pop     rbx
0x18000dd79  retn
```
