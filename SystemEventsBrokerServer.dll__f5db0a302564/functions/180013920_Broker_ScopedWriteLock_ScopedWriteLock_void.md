# Broker::ScopedWriteLock::~ScopedWriteLock(void)

- ea: `0x180013920`
- end: `0x180013942`
- name: `??1ScopedWriteLock@Broker@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(Broker::ScopedWriteLock *__hidden this)`
- caller_count: `27`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800022b0`
- `0x180005cc0`
- `0x180006360`
- `0x180006e00`
- `0x18000b3d0`
- `0x180016590`
- `0x1800186b8`
- `0x180018754`
- `0x1800198e0`
- `0x180019b60`
- `0x18001a9e8`
- `0x18001b378`
- `0x18001b80c`
- `0x18001bcdc`
- `0x18001be34`
- `0x18001c57c`
- `0x180020d84`
- `0x1800225d2`
- `0x1800226f0`
- `0x180022da0`
- `0x180022eb0`
- `0x180023140`
- `0x1800231a0`
- `0x180025193`
- `0x18002533c`
- `0x1800257c6`
- `0x180025b2d`

## callees

- `0x180013920`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180013932`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180013932`

## pseudocode

```c
void __fastcall Broker::ScopedWriteLock::~ScopedWriteLock(Broker::ScopedWriteLock *this)
{
  if ( *((_BYTE *)this + 8) )
  {
    RtlReleaseSRWLockExclusive(*(_QWORD *)this);
    *((_BYTE *)this + 8) = 0;
  }
}

```

## disassembly

```asm
0x180013920  push    rbx
0x180013922  sub     rsp, 20h
0x180013926  cmp     byte ptr [rcx+8], 0
0x18001392a  mov     rbx, rcx
0x18001392d  jz      short loc_18001393C
0x18001392f  mov     rcx, [rcx]
0x180013932  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180013938  mov     byte ptr [rbx+8], 0
0x18001393c  add     rsp, 20h
0x180013940  pop     rbx
0x180013941  retn
```
