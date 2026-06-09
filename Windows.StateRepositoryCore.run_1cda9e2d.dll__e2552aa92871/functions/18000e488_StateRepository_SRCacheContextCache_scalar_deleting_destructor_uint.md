# StateRepository::SRCacheContextCache::`scalar deleting destructor'(uint)

- ea: `0x18000e488`
- end: `0x18000e4ac`
- name: `??_GSRCacheContextCache@StateRepository@@QEAAPEAXI@Z`
- size: `36`
- prototype: `void *__fastcall(StateRepository::SRCacheContextCache *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e55c`
- `0x18000e6d8`

## callees

- `0x1800022a0`
- `0x18000e3e0`

## pseudocode

```c
StateRepository::SRCacheContextCache *__fastcall StateRepository::SRCacheContextCache::`scalar deleting destructor'(
        StateRepository::SRCacheContextCache *this)
{
  Common::Array<StateRepository::CacheContextEntry,Common::ContainerOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>,unsigned short,Common::ContainerOperations<unsigned short,StateRepository::CacheContextEntry>,Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>>::~Array<StateRepository::CacheContextEntry,Common::ContainerOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>,unsigned short,Common::ContainerOperations<unsigned short,StateRepository::CacheContextEntry>,Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>>((__int64)this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000e488  push    rbx
0x18000e48a  sub     rsp, 20h
0x18000e48e  mov     rbx, rcx
0x18000e491  call    ??1?$Array@VCacheContextEntry@StateRepository@@V?$ContainerOperations@VCacheContextEntry@StateRepository@@V12@@Common@@GV?$ContainerOperations@GVCacheContextEntry@StateRepository@@@4@V?$ArrayOperations@VCacheContextEntry@StateRepository@@V12@@4@@Common@@QEAA@XZ; Common::Array<StateRepository::CacheContextEntry,Common::ContainerOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>,ushort,Common::ContainerOperations<ushort,StateRepository::CacheContextEntry>,Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>>::~Array<StateRepository::CacheContextEntry,Common::ContainerOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>,ushort,Common::ContainerOperations<ushort,StateRepository::CacheContextEntry>,Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>>(void)
0x18000e496  mov     edx, 38h ; '8'; unsigned __int64
0x18000e49b  mov     rcx, rbx; void *
0x18000e49e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e4a3  mov     rax, rbx
0x18000e4a6  add     rsp, 20h
0x18000e4aa  pop     rbx
0x18000e4ab  retn
```
