# SmAcquireTrackLockExclusive

- ea: `0x140001020`
- end: `0x14000103d`
- name: `SmAcquireTrackLockExclusive`
- size: `29`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140007e00`

## import_xrefs

- `FLTMGR!FltAcquireResourceExclusive` at `0x14000102b`
- `FLTMGR!FltAcquireResourceExclusive` at `0x14000102b`

## pseudocode

```c
void SmAcquireTrackLockExclusive()
{
  FltAcquireResourceExclusive(Resource);
}

```

## disassembly

```asm
0x140001020  sub     rsp, 28h
0x140001024  mov     rcx, cs:Resource; Resource
0x14000102b  call    cs:__imp_FltAcquireResourceExclusive
0x140001032  nop     dword ptr [rax+rax+00h]
0x140001037  add     rsp, 28h
0x14000103b  retn
```
