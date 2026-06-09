# wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::~unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>(void)

- ea: `0x18001b810`
- end: `0x18001b858`
- name: `??1?$unique_ptr@VPCPStorageProviderKey@@U?$default_delete@VPCPStorageProviderKey@@@wistd@@@wistd@@QEAA@XZ`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800c6ec4`

## callees

- `0x18001b810`
- `0x18001b8f0`
- `0x1800768a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b838`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b838`

## pseudocode

```c
void __fastcall wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::~unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>(
        __int64 *a1)
{
  __int64 v1; // rbx

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
  {
    PCPStorageProviderKey::Teardown((PCPStorageProviderKey *)v1);
    if ( (*(_DWORD *)(v1 + 4) & 1) == 0 )
      DeleteCriticalSection((LPCRITICAL_SECTION)(v1 + 8));
    operator delete((void *)v1, (const struct std::nothrow_t *)0x318);
  }
}

```

## disassembly

```asm
0x18001b810  push    rbx
0x18001b812  sub     rsp, 20h
0x18001b816  mov     rbx, [rcx]
0x18001b819  mov     qword ptr [rcx], 0
0x18001b820  test    rbx, rbx
0x18001b823  jz      short loc_18001B851
0x18001b825  mov     rcx, rbx; this
0x18001b828  call    ?Teardown@PCPStorageProviderKey@@QEAAJXZ; PCPStorageProviderKey::Teardown(void)
0x18001b82d  mov     eax, [rbx+4]
0x18001b830  test    al, 1
0x18001b832  jnz     short loc_18001B844
0x18001b834  lea     rcx, [rbx+8]; lpCriticalSection
0x18001b838  call    cs:__imp_DeleteCriticalSection
0x18001b83f  nop     dword ptr [rax+rax+00h]
0x18001b844  mov     edx, 318h; struct std::nothrow_t *
0x18001b849  mov     rcx, rbx; void *
0x18001b84c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b851  add     rsp, 20h
0x18001b855  pop     rbx
0x18001b856  retn
```
