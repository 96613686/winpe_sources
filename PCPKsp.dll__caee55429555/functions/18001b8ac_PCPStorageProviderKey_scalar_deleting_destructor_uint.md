# PCPStorageProviderKey::`scalar deleting destructor'(uint)

- ea: `0x18001b8ac`
- end: `0x18001b8e8`
- name: `??_GPCPStorageProviderKey@@QEAAPEAXI@Z`
- size: `60`
- prototype: `void *__fastcall(PCPStorageProviderKey *__hidden this, unsigned int)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180038aa0`
- `0x180059ea0`
- `0x18005aebc`
- `0x1800604d0`
- `0x18006a9c4`

## callees

- `0x18001b8ac`
- `0x18001b8f0`
- `0x1800768a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b8c5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b8c5`

## pseudocode

```c
PCPStorageProviderKey *__fastcall PCPStorageProviderKey::`scalar deleting destructor'(PCPStorageProviderKey *this)
{
  PCPStorageProviderKey::Teardown(this);
  if ( (*((_DWORD *)this + 1) & 1) == 0 )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  operator delete(this, (const struct std::nothrow_t *)0x318);
  return this;
}

```

## disassembly

```asm
0x18001b8ac  push    rbx
0x18001b8ae  sub     rsp, 20h
0x18001b8b2  mov     rbx, rcx
0x18001b8b5  call    ?Teardown@PCPStorageProviderKey@@QEAAJXZ; PCPStorageProviderKey::Teardown(void)
0x18001b8ba  mov     eax, [rbx+4]
0x18001b8bd  test    al, 1
0x18001b8bf  jnz     short loc_18001B8D1
0x18001b8c1  lea     rcx, [rbx+8]; lpCriticalSection
0x18001b8c5  call    cs:__imp_DeleteCriticalSection
0x18001b8cc  nop     dword ptr [rax+rax+00h]
0x18001b8d1  mov     edx, 318h; struct std::nothrow_t *
0x18001b8d6  mov     rcx, rbx; void *
0x18001b8d9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b8de  mov     rax, rbx
0x18001b8e1  add     rsp, 20h
0x18001b8e5  pop     rbx
0x18001b8e6  retn
```
