# wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(PCPStorageProviderKey *)

- ea: `0x18001b860`
- end: `0x18001b8a4`
- name: `?reset@?$unique_ptr@VPCPStorageProviderKey@@U?$default_delete@VPCPStorageProviderKey@@@wistd@@@wistd@@QEAAXPEAVPCPStorageProviderKey@@@Z`
- size: `68`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800204a0`
- `0x180038aa0`
- `0x18003a340`
- `0x1800604d0`
- `0x18007f068`

## callees

- `0x18001b860`
- `0x18001b8f0`
- `0x1800768a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b884`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b884`

## pseudocode

```c
void __fastcall wistd::unique_ptr<PCPStorageProviderKey,wistd::default_delete<PCPStorageProviderKey>>::reset(
        __int64 *a1,
        __int64 a2)
{
  __int64 v2; // rbx

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
  {
    PCPStorageProviderKey::Teardown((PCPStorageProviderKey *)v2);
    if ( (*(_DWORD *)(v2 + 4) & 1) == 0 )
      DeleteCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
    operator delete((void *)v2, (const struct std::nothrow_t *)0x318);
  }
}

```

## disassembly

```asm
0x18001b860  push    rbx
0x18001b862  sub     rsp, 20h
0x18001b866  mov     rbx, [rcx]
0x18001b869  mov     [rcx], rdx
0x18001b86c  test    rbx, rbx
0x18001b86f  jz      short loc_18001B89D
0x18001b871  mov     rcx, rbx; this
0x18001b874  call    ?Teardown@PCPStorageProviderKey@@QEAAJXZ; PCPStorageProviderKey::Teardown(void)
0x18001b879  mov     eax, [rbx+4]
0x18001b87c  test    al, 1
0x18001b87e  jnz     short loc_18001B890
0x18001b880  lea     rcx, [rbx+8]; lpCriticalSection
0x18001b884  call    cs:__imp_DeleteCriticalSection
0x18001b88b  nop     dword ptr [rax+rax+00h]
0x18001b890  mov     edx, 318h; struct std::nothrow_t *
0x18001b895  mov     rcx, rbx; void *
0x18001b898  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b89d  add     rsp, 20h
0x18001b8a1  pop     rbx
0x18001b8a2  retn
```
