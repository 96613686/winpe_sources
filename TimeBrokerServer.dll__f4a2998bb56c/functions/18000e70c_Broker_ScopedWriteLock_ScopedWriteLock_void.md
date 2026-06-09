# Broker::ScopedWriteLock::~ScopedWriteLock(void)

- ea: `0x18000e70c`
- end: `0x18000e72e`
- name: `??1ScopedWriteLock@Broker@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(Broker::ScopedWriteLock *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010350`
- `0x180017e64`
- `0x18001807c`
- `0x18001beab`

## callees

- `0x18000e70c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e71e`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000e71e`

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
0x18000e70c  push    rbx
0x18000e70e  sub     rsp, 20h
0x18000e712  cmp     byte ptr [rcx+8], 0
0x18000e716  mov     rbx, rcx
0x18000e719  jz      short loc_18000E728
0x18000e71b  mov     rcx, [rcx]
0x18000e71e  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000e724  mov     byte ptr [rbx+8], 0
0x18000e728  add     rsp, 20h
0x18000e72c  pop     rbx
0x18000e72d  retn
```
