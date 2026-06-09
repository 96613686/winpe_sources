# WinApiLite::SetNamedSecurityInfoW(ushort *,_SE_OBJECT_TYPE,ulong,void *,void *,_ACL *,_ACL *)

- ea: `0x180017630`
- end: `0x18001767a`
- name: `?SetNamedSecurityInfoW@WinApiLite@@UEAAKPEAGW4_SE_OBJECT_TYPE@@KPEAX2PEAU_ACL@@3@Z`
- size: `74`
- prototype: `unsigned int(WinApiLite *__hidden this, unsigned __int16 *, enum _SE_OBJECT_TYPE, unsigned int, void *, void *, struct _ACL *, struct _ACL *)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18001766e`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x18001766e`

## pseudocode

```c
DWORD __fastcall WinApiLite::SetNamedSecurityInfoW(
        WinApiLite *this,
        unsigned __int16 *a2,
        SE_OBJECT_TYPE a3,
        SECURITY_INFORMATION a4,
        PSID psidOwner,
        PSID psidGroup,
        struct _ACL *pDacl,
        struct _ACL *pSacl)
{
  return SetNamedSecurityInfoW(a2, a3, a4, psidOwner, psidGroup, pDacl, pSacl);
}

```

## disassembly

```asm
0x180017630  push    rbx
0x180017632  sub     rsp, 40h
0x180017636  mov     rax, [rsp+48h+arg_38]
0x18001763e  mov     r10d, r9d
0x180017641  mov     r9, [rsp+48h+psidOwner]; psidOwner
0x180017646  mov     r11d, r8d
0x180017649  mov     [rsp+48h+pSacl], rax; pSacl
0x18001764e  mov     rcx, rdx; pObjectName
0x180017651  mov     rax, [rsp+48h+arg_30]
0x180017659  mov     r8d, r10d; SecurityInfo
0x18001765c  mov     [rsp+48h+pDacl], rax; pDacl
0x180017661  mov     edx, r11d; ObjectType
0x180017664  mov     rax, [rsp+48h+arg_28]
0x180017669  mov     [rsp+48h+psidGroup], rax; psidGroup
0x18001766e  call    cs:__imp_SetNamedSecurityInfoW
0x180017674  add     rsp, 40h
0x180017678  pop     rbx
0x180017679  retn
```
