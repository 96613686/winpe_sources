# Wns::CleanupWork::~CleanupWork(void)

- ea: `0x1800175a8`
- end: `0x1800175bf`
- name: `??1CleanupWork@Wns@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(struct _TP_WORK **this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800321c0`
- `0x180035120`
- `0x180036149`

## callees

- `0x1800175a8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800175b4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800175b4`

## pseudocode

```c
void __fastcall Wns::CleanupWork::~CleanupWork(struct _TP_WORK **this)
{
  struct _TP_WORK *v1; // rcx

  v1 = *this;
  if ( v1 )
    SubmitThreadpoolWork(v1);
}

```

## disassembly

```asm
0x1800175a8  sub     rsp, 28h
0x1800175ac  mov     rcx, [rcx]; pwk
0x1800175af  test    rcx, rcx
0x1800175b2  jz      short loc_1800175BA
0x1800175b4  call    cs:__imp_SubmitThreadpoolWork
0x1800175ba  add     rsp, 28h
0x1800175be  retn
```
