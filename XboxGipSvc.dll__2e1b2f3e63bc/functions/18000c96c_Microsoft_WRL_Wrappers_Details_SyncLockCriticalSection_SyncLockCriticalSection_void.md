# Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)

- ea: `0x18000c96c`
- end: `0x18000c990`
- name: `??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION **this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001176f`
- `0x180011850`
- `0x1800118d6`
- `0x1800118fa`

## callees

- `0x18000c96c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c97d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c97d`

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
0x18000c96c  push    rbx
0x18000c96e  sub     rsp, 20h
0x18000c972  mov     rbx, rcx
0x18000c975  mov     rcx, [rcx]; lpCriticalSection
0x18000c978  test    rcx, rcx
0x18000c97b  jz      short loc_18000C98A
0x18000c97d  call    cs:__imp_LeaveCriticalSection
0x18000c983  mov     qword ptr [rbx], 0
0x18000c98a  add     rsp, 20h
0x18000c98e  pop     rbx
0x18000c98f  retn
```
