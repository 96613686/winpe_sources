# WinApiLite::GetSecurityDescriptorDacl(void *,int *,_ACL * *,int *)

- ea: `0x180017190`
- end: `0x1800171ab`
- name: `?GetSecurityDescriptorDacl@WinApiLite@@UEAAHPEAXPEAHPEAPEAU_ACL@@1@Z`
- size: `27`
- prototype: `BOOL __fastcall(WinApiLite *this, void *, int *, struct _ACL **, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800171a4`

## pseudocode

```c
BOOL __fastcall WinApiLite::GetSecurityDescriptorDacl(WinApiLite *this, void *a2, int *a3, struct _ACL **a4, int *a5)
{
  return GetSecurityDescriptorDacl(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x180017190  mov     rax, r9
0x180017193  mov     r10, r8
0x180017196  mov     r9, [rsp+arg_20]
0x18001719b  mov     rcx, rdx
0x18001719e  mov     r8, rax
0x1800171a1  mov     rdx, r10
0x1800171a4  jmp     cs:__imp_GetSecurityDescriptorDacl
```
