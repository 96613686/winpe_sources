# Broker::ScopedWriteLock::~ScopedWriteLock(void)

- ea: `0x18000ed50`
- end: `0x18000ed72`
- name: `??1ScopedWriteLock@Broker@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(Broker::ScopedWriteLock *__hidden this)`
- caller_count: `19`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000b3cc`
- `0x18000c4c0`
- `0x18000c970`
- `0x1800119f4`
- `0x1800153e4`
- `0x180017578`
- `0x18001764c`
- `0x180017a9c`
- `0x180018004`
- `0x180019010`
- `0x18001af32`
- `0x18001afe8`
- `0x18001bdab`
- `0x18001bfc6`
- `0x18001c031`
- `0x18001c896`
- `0x18001d791`
- `0x18001d82d`
- `0x18001d83f`

## callees

- `0x18000ed50`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ed62`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000ed62`

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
0x18000ed50  push    rbx
0x18000ed52  sub     rsp, 20h
0x18000ed56  cmp     byte ptr [rcx+8], 0
0x18000ed5a  mov     rbx, rcx
0x18000ed5d  jz      short loc_18000ED6C
0x18000ed5f  mov     rcx, [rcx]
0x18000ed62  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000ed68  mov     byte ptr [rbx+8], 0
0x18000ed6c  add     rsp, 20h
0x18000ed70  pop     rbx
0x18000ed71  retn
```
