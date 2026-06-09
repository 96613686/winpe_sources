# WinApiLite::GetSecurityDescriptorSacl(void *,int *,_ACL * *,int *)

- ea: `0x1800171c0`
- end: `0x1800171db`
- name: `?GetSecurityDescriptorSacl@WinApiLite@@UEAAHPEAXPEAHPEAPEAU_ACL@@1@Z`
- size: `27`
- prototype: `BOOL __fastcall(WinApiLite *this, void *, int *, struct _ACL **, int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800171d4`

## pseudocode

```c
BOOL __fastcall WinApiLite::GetSecurityDescriptorSacl(WinApiLite *this, void *a2, int *a3, struct _ACL **a4, int *a5)
{
  return GetSecurityDescriptorSacl(a2, a3, a4, a5);
}

```

## disassembly

```asm
0x1800171c0  mov     rax, r9
0x1800171c3  mov     r10, r8
0x1800171c6  mov     r9, [rsp+arg_20]
0x1800171cb  mov     rcx, rdx
0x1800171ce  mov     r8, rax
0x1800171d1  mov     rdx, r10
0x1800171d4  jmp     cs:__imp_GetSecurityDescriptorSacl
```
