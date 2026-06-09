# CProviderRegistrationCache::RenewCertificate(_GUID const *,int)

- ea: `0x18000c864`
- end: `0x18000c882`
- name: `?RenewCertificate@CProviderRegistrationCache@@QEAAJPEBU_GUID@@H@Z`
- size: `30`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, const struct _GUID *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000caa0`
- `0x1800167c8`

## callees

- `0x180018db0`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::RenewCertificate(
        CProviderRegistrationCache *this,
        const struct _GUID *a2,
        unsigned int a3)
{
  if ( *((_QWORD *)this + 32) )
    return guard_dispatch_icall_thunk_10345483385596137414(a2, a3);
  else
    return LsaRenewCertificate(a2, a3);
}

```

## disassembly

```asm
0x18000c864  mov     rax, [rcx+100h]
0x18000c86b  mov     r9, rdx
0x18000c86e  mov     edx, r8d
0x18000c871  mov     rcx, r9
0x18000c874  test    rax, rax
0x18000c877  jnz     _guard_dispatch_icall$thunk$10345483385596137414
0x18000c87d  jmp     LsaRenewCertificate
```
