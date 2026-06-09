# ATL::CSecurityDesc::Clear(void)

- ea: `0x180012070`
- end: `0x180012184`
- name: `?Clear@CSecurityDesc@ATL@@MEAAXXZ`
- size: `276`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001039c`
- `0x18002cb7c`
- `0x180047840`

## callees

- `0x180012070`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800120b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001210d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012129`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001214f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012179`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800120b4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001210d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012129`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001214f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012179`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180012165`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180012165`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001213f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001213f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18001211f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorGroup` at `0x18001211f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180012103`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorOwner` at `0x180012103`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18001209b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18001209b`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::Clear(ATL::CSecurityDesc *this)
{
  void *v2; // rcx
  void *v3; // rcx
  PSID pGroup; // [rsp+20h] [rbp-28h] BYREF
  PACL pDacl; // [rsp+28h] [rbp-20h] BYREF
  PACL pSacl; // [rsp+30h] [rbp-18h] BYREF
  WORD pControl; // [rsp+60h] [rbp+18h] BYREF
  DWORD dwRevision; // [rsp+68h] [rbp+20h] BYREF
  WINBOOL bDaclPresent; // [rsp+70h] [rbp+28h] BYREF
  PSID pOwner; // [rsp+78h] [rbp+30h] BYREF

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    dwRevision = 0;
    pControl = 0;
    if ( GetSecurityDescriptorControl(v2, &pControl, &dwRevision) && (pControl & 0x8000u) == 0 )
    {
      v3 = (void *)*((_QWORD *)this + 1);
      pOwner = 0;
      pGroup = 0;
      pDacl = 0;
      pSacl = 0;
      dwRevision = 0;
      bDaclPresent = 0;
      GetSecurityDescriptorOwner(v3, &pOwner, (LPBOOL)&dwRevision);
      free(pOwner);
      GetSecurityDescriptorGroup(*((PSECURITY_DESCRIPTOR *)this + 1), &pGroup, (LPBOOL)&dwRevision);
      free(pGroup);
      GetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 1), &bDaclPresent, &pDacl, (LPBOOL)&dwRevision);
      if ( bDaclPresent )
        free(pDacl);
      GetSecurityDescriptorSacl(*((PSECURITY_DESCRIPTOR *)this + 1), &bDaclPresent, &pSacl, (LPBOOL)&dwRevision);
      if ( bDaclPresent )
        free(pSacl);
    }
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x180012070  push    rbp
0x180012072  push    rbx
0x180012073  mov     rbp, rsp
0x180012076  sub     rsp, 48h
0x18001207a  mov     rbx, rcx
0x18001207d  mov     rcx, [rcx+8]; pSecurityDescriptor
0x180012081  test    rcx, rcx
0x180012084  jz      short loc_1800120C2
0x180012086  xor     eax, eax
0x180012088  mov     [rbp+dwRevision], 0
0x18001208f  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180012093  mov     [rbp+pControl], ax
0x180012097  lea     rdx, [rbp+pControl]; pControl
0x18001209b  call    cs:__imp_GetSecurityDescriptorControl
0x1800120a1  test    eax, eax
0x1800120a3  jz      short loc_1800120B0
0x1800120a5  mov     eax, 8000h
0x1800120aa  test    [rbp+pControl], ax
0x1800120ae  jz      short loc_1800120C9
0x1800120b0  mov     rcx, [rbx+8]; Block
0x1800120b4  call    cs:__imp_free
0x1800120ba  mov     qword ptr [rbx+8], 0
0x1800120c2  add     rsp, 48h
0x1800120c6  pop     rbx
0x1800120c7  pop     rbp
0x1800120c8  retn
0x1800120c9  mov     rcx, [rbx+8]; pSecurityDescriptor
0x1800120cd  lea     r8, [rbp+dwRevision]; lpbOwnerDefaulted
0x1800120d1  lea     rdx, [rbp+pOwner]; pOwner
0x1800120d5  mov     [rbp+pOwner], 0
0x1800120dd  mov     [rbp+pGroup], 0
0x1800120e5  mov     [rbp+pDacl], 0
0x1800120ed  mov     [rbp+pSacl], 0
0x1800120f5  mov     [rbp+dwRevision], 0
0x1800120fc  mov     [rbp+bDaclPresent], 0
0x180012103  call    cs:__imp_GetSecurityDescriptorOwner
0x180012109  mov     rcx, [rbp+pOwner]; Block
0x18001210d  call    cs:__imp_free
0x180012113  mov     rcx, [rbx+8]; pSecurityDescriptor
0x180012117  lea     r8, [rbp+dwRevision]; lpbGroupDefaulted
0x18001211b  lea     rdx, [rbp+pGroup]; pGroup
0x18001211f  call    cs:__imp_GetSecurityDescriptorGroup
0x180012125  mov     rcx, [rbp+pGroup]; Block
0x180012129  call    cs:__imp_free
0x18001212f  mov     rcx, [rbx+8]; pSecurityDescriptor
0x180012133  lea     r9, [rbp+dwRevision]; lpbDaclDefaulted
0x180012137  lea     r8, [rbp+pDacl]; pDacl
0x18001213b  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18001213f  call    cs:__imp_GetSecurityDescriptorDacl
0x180012145  cmp     [rbp+bDaclPresent], 0
0x180012149  jz      short loc_180012155
0x18001214b  mov     rcx, [rbp+pDacl]; Block
0x18001214f  call    cs:__imp_free
0x180012155  mov     rcx, [rbx+8]; pSecurityDescriptor
0x180012159  lea     r9, [rbp+dwRevision]; lpbSaclDefaulted
0x18001215d  lea     r8, [rbp+pSacl]; pSacl
0x180012161  lea     rdx, [rbp+bDaclPresent]; lpbSaclPresent
0x180012165  call    cs:__imp_GetSecurityDescriptorSacl
0x18001216b  cmp     [rbp+bDaclPresent], 0
0x18001216f  jz      loc_1800120B0
0x180012175  mov     rcx, [rbp+pSacl]; Block
0x180012179  call    cs:__imp_free
0x18001217f  jmp     loc_1800120B0
```
