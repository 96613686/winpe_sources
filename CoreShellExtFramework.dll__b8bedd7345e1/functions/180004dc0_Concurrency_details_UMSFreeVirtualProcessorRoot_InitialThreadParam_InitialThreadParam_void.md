# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180004dc0`
- end: `0x180004dd7`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(RTL_SRWLOCK **this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c6ac`
- `0x180010140`

## callees

- `0x180004dc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004dcc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180004dcc`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        RTL_SRWLOCK **this)
{
  RTL_SRWLOCK *v1; // rcx

  v1 = *this;
  if ( v1 )
    ReleaseSRWLockShared(v1);
}

```

## disassembly

```asm
0x180004dc0  sub     rsp, 28h
0x180004dc4  mov     rcx, [rcx]; SRWLock
0x180004dc7  test    rcx, rcx
0x180004dca  jz      short loc_180004DD2
0x180004dcc  call    cs:ReleaseSRWLockShared
0x180004dd2  add     rsp, 28h
0x180004dd6  retn
```
