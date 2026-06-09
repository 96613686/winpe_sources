# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180075e70`
- end: `0x180075e87`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION **this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180075e70`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180075e7c`
- `KERNEL32!LeaveCriticalSection` at `0x180075e7c`

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
0x180075e70  sub     rsp, 28h
0x180075e74  mov     rcx, [rcx]; lpCriticalSection
0x180075e77  test    rcx, rcx
0x180075e7a  jz      short loc_180075E82
0x180075e7c  call    cs:LeaveCriticalSection
0x180075e82  add     rsp, 28h
0x180075e86  retn
```
