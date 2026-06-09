# StorageService::~StorageService(void)

- ea: `0x18001faf0`
- end: `0x18001fb55`
- name: `??1StorageService@@QEAA@XZ`
- size: `101`
- prototype: `void __fastcall(StorageService *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800891a0`

## callees

- `0x18000d460`
- `0x18001c208`
- `0x18001fb5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fb11`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fb1f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fb11`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001fb1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall StorageService::~StorageService(struct _RTL_CRITICAL_SECTION *this)
{
  std::wstring::_Tidy_deallocate(&this[47]);
  DeleteCriticalSection(this + 46);
  DeleteCriticalSection(this + 45);
  StorageUsageCache::~StorageUsageCache((StorageUsageCache *)&this[43].LockCount);
  `eh vector destructor iterator'(&this[1].OwningThread, 0x2F8u, 2u, (void (*)(void *))StorageCleanup::~StorageCleanup);
}

```

## disassembly

```asm
0x18001faf0  mov     [rsp+arg_0], rcx
0x18001faf5  push    rbx
0x18001faf6  sub     rsp, 20h
0x18001fafa  mov     rbx, rcx
0x18001fafd  add     rcx, 758h
0x18001fb04  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fb09  nop
0x18001fb0a  lea     rcx, [rbx+730h]; lpCriticalSection
0x18001fb11  call    cs:__imp_DeleteCriticalSection
0x18001fb17  nop
0x18001fb18  lea     rcx, [rbx+708h]; lpCriticalSection
0x18001fb1f  call    cs:__imp_DeleteCriticalSection
0x18001fb25  nop
0x18001fb26  lea     rcx, [rbx+6C0h]; this
0x18001fb2d  call    ??1StorageUsageCache@@QEAA@XZ; StorageUsageCache::~StorageUsageCache(void)
0x18001fb32  nop
0x18001fb33  lea     rcx, [rbx+38h]; void *
0x18001fb37  lea     r9, ??1StorageCleanup@@QEAA@XZ; void (*)(void *)
0x18001fb3e  mov     edx, 2F8h; unsigned __int64
0x18001fb43  mov     r8d, 2; unsigned __int64
0x18001fb49  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18001fb4e  nop
0x18001fb4f  add     rsp, 20h
0x18001fb53  pop     rbx
0x18001fb54  retn
```
