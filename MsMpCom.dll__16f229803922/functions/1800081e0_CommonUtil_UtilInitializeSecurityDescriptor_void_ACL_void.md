# CommonUtil::UtilInitializeSecurityDescriptor(void *,_ACL *,void *)

- ea: `0x1800081e0`
- end: `0x18000822f`
- name: `?UtilInitializeSecurityDescriptor@CommonUtil@@YAJPEAXPEAU_ACL@@0@Z`
- size: `79`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, PACL pDacl, struct _ACL *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006a2c`

## callees

- `0x1800081e0`
- `0x1800090e4`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180008218`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180008218`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800081f5`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800081f5`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilInitializeSecurityDescriptor(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        PACL pDacl,
        struct _ACL *a3,
        void *a4)
{
  __int64 v6; // rcx

  if ( InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
    && (!pDacl || SetSecurityDescriptorDacl(pSecurityDescriptor, 1, pDacl, 0)) )
  {
    return 0;
  }
  else
  {
    return HrGetLastFailure(v6);
  }
}

```

## disassembly

```asm
0x1800081e0  mov     [rsp+arg_0], rbx
0x1800081e5  push    rdi
0x1800081e6  sub     rsp, 20h
0x1800081ea  mov     rbx, rdx
0x1800081ed  mov     rdi, rcx
0x1800081f0  mov     edx, 1; dwRevision
0x1800081f5  call    cs:__imp_InitializeSecurityDescriptor
0x1800081fb  test    eax, eax
0x1800081fd  jnz     short loc_180008206
0x1800081ff  call    HrGetLastFailure
0x180008204  jmp     short loc_180008224
0x180008206  test    rbx, rbx
0x180008209  jz      short loc_180008222
0x18000820b  xor     r9d, r9d; bDaclDefaulted
0x18000820e  mov     r8, rbx; pDacl
0x180008211  mov     rcx, rdi; pSecurityDescriptor
0x180008214  lea     edx, [r9+1]; bDaclPresent
0x180008218  call    cs:__imp_SetSecurityDescriptorDacl
0x18000821e  test    eax, eax
0x180008220  jz      short loc_1800081FF
0x180008222  xor     eax, eax
0x180008224  mov     rbx, [rsp+28h+arg_0]
0x180008229  add     rsp, 20h
0x18000822d  pop     rdi
0x18000822e  retn
```
