# std::unique_ptr_void__lambda_5beab740efbf3494b609d1267351a2ce___::_unique_ptr_void__lambda_5beab740efbf3494b609d1267351a2ce___

- ea: `0x1800087b0`
- end: `0x1800087c7`
- name: `std::unique_ptr_void__lambda_5beab740efbf3494b609d1267351a2ce___::_unique_ptr_void__lambda_5beab740efbf3494b609d1267351a2ce___`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180008a94`
- `0x18000b558`
- `0x18000c234`
- `0x18000f6a3`
- `0x18000f90c`
- `0x18000fa62`

## callees

- `0x1800087b0`

## import_xrefs

- `SPOOLSS!ImpersonatePrinterClient` at `0x1800087bc`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800087bc`

## pseudocode

```c
BOOL __fastcall std::unique_ptr_void__lambda_5beab740efbf3494b609d1267351a2ce___::_unique_ptr_void__lambda_5beab740efbf3494b609d1267351a2ce___(
        void **a1)
{
  void *v1; // rcx
  BOOL result; // eax

  v1 = *a1;
  if ( v1 )
    return ImpersonatePrinterClient(v1);
  return result;
}

```

## disassembly

```asm
0x1800087b0  sub     rsp, 28h
0x1800087b4  mov     rcx, [rcx]; hToken
0x1800087b7  test    rcx, rcx
0x1800087ba  jz      short loc_1800087C2
0x1800087bc  call    cs:__imp_ImpersonatePrinterClient
0x1800087c2  add     rsp, 28h
0x1800087c6  retn
```
