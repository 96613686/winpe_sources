# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x18000a6c4`
- end: `0x18000a6db`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_1`
- size: `23`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION **this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c6ac`
- `0x18000e2bc`

## callees

- `0x18000a6c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a6d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a6d0`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        struct _RTL_CRITICAL_SECTION **this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rcx

  v1 = *this;
  if ( v1 )
    LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x18000a6c4  sub     rsp, 28h
0x18000a6c8  mov     rcx, [rcx]; lpCriticalSection
0x18000a6cb  test    rcx, rcx
0x18000a6ce  jz      short loc_18000A6D6
0x18000a6d0  call    cs:LeaveCriticalSection
0x18000a6d6  add     rsp, 28h
0x18000a6da  retn
```
