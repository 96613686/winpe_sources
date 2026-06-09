# std::unique_ptr<_ACL,localfree_deleter>::~unique_ptr<_ACL,localfree_deleter>(void)

- ea: `0x180006124`
- end: `0x18000613c`
- name: `??1?$unique_ptr@U_ACL@@Ulocalfree_deleter@@@std@@QEAA@XZ`
- size: `24`
- prototype: `HLOCAL __fastcall(void **)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000c744`
- `0x18000c756`
- `0x18000c768`

## callees

- `0x180006124`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006130`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006130`

## pseudocode

```c
HLOCAL __fastcall std::unique_ptr<_ACL,localfree_deleter>::~unique_ptr<_ACL,localfree_deleter>(void **a1)
{
  void *v1; // rcx
  HLOCAL result; // rax

  v1 = *a1;
  if ( v1 )
    return LocalFree(v1);
  return result;
}

```

## disassembly

```asm
0x180006124  sub     rsp, 28h
0x180006128  mov     rcx, [rcx]; hMem
0x18000612b  test    rcx, rcx
0x18000612e  jz      short loc_180006137
0x180006130  call    cs:__imp_LocalFree
0x180006136  nop
0x180006137  add     rsp, 28h
0x18000613b  retn
```
