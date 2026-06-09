# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x18000c700`
- end: `0x18000c717`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_0`
- size: `23`
- prototype: `void __fastcall(Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam *__hidden this)`
- caller_count: `32`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b7d0`
- `0x18000b840`
- `0x18000d188`
- `0x18000d248`
- `0x18000d2e4`
- `0x18000ebf4`
- `0x18000ecc0`
- `0x18000ede8`
- `0x18000eed4`
- `0x18000f2a4`
- `0x18000f34c`
- `0x18000f4cc`
- `0x180010600`
- `0x180010694`
- `0x18001072c`
- `0x180010bb0`
- `0x18001be00`
- `0x18001c5ac`
- `0x18001e0f0`
- `0x18001fc28`
- `0x1800201f0`
- `0x1800228dc`
- `0x1800277ac`
- `0x1800279e4`
- `0x180027a70`
- `0x180027e50`
- `0x180028018`
- `0x1800284cc`
- `0x1800403ec`
- `0x1800408b0`
- `0x180040f9c`
- `0x180041acc`

## callees

- `0x18000c700`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c70c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000c70c`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        RTL_SRWLOCK **this)
{
  RTL_SRWLOCK *v1; // rcx

  v1 = *this;
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
}

```

## disassembly

```asm
0x18000c700  sub     rsp, 28h
0x18000c704  mov     rcx, [rcx]; SRWLock
0x18000c707  test    rcx, rcx
0x18000c70a  jz      short loc_18000C712
0x18000c70c  call    cs:__imp_ReleaseSRWLockExclusive
0x18000c712  add     rsp, 28h
0x18000c716  retn
```
