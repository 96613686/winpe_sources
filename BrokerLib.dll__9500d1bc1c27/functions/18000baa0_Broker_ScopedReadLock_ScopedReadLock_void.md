# Broker::ScopedReadLock::~ScopedReadLock(void)

- ea: `0x18000baa0`
- end: `0x18000bac2`
- name: `??1ScopedReadLock@Broker@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(Broker::ScopedReadLock *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014558`
- `0x180018ec0`
- `0x18001b550`
- `0x18001c3ea`
- `0x18001dc0b`

## callees

- `0x18000baa0`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x18000bab2`
- `ntdll!RtlReleaseSRWLockShared` at `0x18000bab2`

## pseudocode

```c
void __fastcall Broker::ScopedReadLock::~ScopedReadLock(Broker::ScopedReadLock *this)
{
  if ( *((_BYTE *)this + 8) )
  {
    RtlReleaseSRWLockShared(*(_QWORD *)this);
    *((_BYTE *)this + 8) = 0;
  }
}

```

## disassembly

```asm
0x18000baa0  push    rbx
0x18000baa2  sub     rsp, 20h
0x18000baa6  cmp     byte ptr [rcx+8], 0
0x18000baaa  mov     rbx, rcx
0x18000baad  jz      short loc_18000BABC
0x18000baaf  mov     rcx, [rcx]
0x18000bab2  call    cs:__imp_RtlReleaseSRWLockShared
0x18000bab8  mov     byte ptr [rbx+8], 0
0x18000babc  add     rsp, 20h
0x18000bac0  pop     rbx
0x18000bac1  retn
```
