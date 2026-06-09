# ATL::CSecurityDesc::Clear(void)

- ea: `0x18002fa20`
- end: `0x18002fb29`
- name: `?Clear@CSecurityDesc@ATL@@MEAAXXZ`
- size: `265`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002dfd0`
- `0x18002e980`
- `0x18002f9c8`
- `0x18002f9e0`

## callees

- `0x18002fa20`
- `0x180049b50`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorSacl` at `0x18002fae8`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x18002fae8`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18002fac3`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18002fac3`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x18002faa3`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x18002faa3`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18002fa87`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18002fa87`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18002fa5e`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x18002fa5e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002fa91`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002faad`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002fad2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002faf7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002fb01`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002fa91`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002faad`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002fad2`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002faf7`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002fb01`

## pseudocode

```c
void __fastcall ATL::CSecurityDesc::Clear(ATL::CSecurityDesc *this)
{
  void *v2; // rcx
  PSID pOwner; // [rsp+20h] [rbp-40h] BYREF
  PSID pGroup; // [rsp+28h] [rbp-38h] BYREF
  PACL pDacl; // [rsp+30h] [rbp-30h] BYREF
  PACL pSacl; // [rsp+38h] [rbp-28h] BYREF
  WORD pControl[2]; // [rsp+40h] [rbp-20h] BYREF
  DWORD dwRevision; // [rsp+44h] [rbp-1Ch] BYREF
  BOOL bOwnerDefaulted; // [rsp+48h] [rbp-18h] BYREF

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    pControl[0] = 0;
    if ( GetSecurityDescriptorControl(v2, pControl, &dwRevision) && (pControl[0] & 0x8000u) == 0 )
    {
      GetSecurityDescriptorOwner(*((PSECURITY_DESCRIPTOR *)this + 1), &pOwner, &bOwnerDefaulted);
      free(pOwner);
      GetSecurityDescriptorGroup(*((PSECURITY_DESCRIPTOR *)this + 1), &pGroup, &bOwnerDefaulted);
      free(pGroup);
      GetSecurityDescriptorDacl(*((PSECURITY_DESCRIPTOR *)this + 1), (LPBOOL)&dwRevision, &pDacl, &bOwnerDefaulted);
      if ( dwRevision )
        free(pDacl);
      GetSecurityDescriptorSacl(*((PSECURITY_DESCRIPTOR *)this + 1), (LPBOOL)&dwRevision, &pSacl, &bOwnerDefaulted);
      if ( dwRevision )
        free(pSacl);
    }
    free(*((void **)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18002fa20  mov     [rsp-8+arg_8], rbx
0x18002fa25  mov     [rsp-8+arg_10], rdi
0x18002fa2a  push    rbp
0x18002fa2b  mov     rbp, rsp
0x18002fa2e  sub     rsp, 60h
0x18002fa32  mov     rax, cs:__security_cookie
0x18002fa39  xor     rax, rsp
0x18002fa3c  mov     [rbp+var_10], rax
0x18002fa40  mov     rbx, rcx
0x18002fa43  xor     edi, edi
0x18002fa45  mov     rcx, [rcx+8]; pSecurityDescriptor
0x18002fa49  test    rcx, rcx
0x18002fa4c  jz      loc_18002FB0B
0x18002fa52  lea     r8, [rbp+dwRevision]; lpdwRevision
0x18002fa56  mov     [rbp+pControl], di
0x18002fa5a  lea     rdx, [rbp+pControl]; pControl
0x18002fa5e  call    cs:__imp_GetSecurityDescriptorControl
0x18002fa64  test    eax, eax
0x18002fa66  jz      loc_18002FAFD
0x18002fa6c  mov     eax, 8000h
0x18002fa71  test    [rbp+pControl], ax
0x18002fa75  jnz     loc_18002FAFD
0x18002fa7b  mov     rcx, [rbx+8]; pSecurityDescriptor
0x18002fa7f  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x18002fa83  lea     rdx, [rbp+pOwner]; pOwner
0x18002fa87  call    cs:__imp_GetSecurityDescriptorOwner
0x18002fa8d  mov     rcx, [rbp+pOwner]; Block
0x18002fa91  call    cs:__imp_free
0x18002fa97  mov     rcx, [rbx+8]; pSecurityDescriptor
0x18002fa9b  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x18002fa9f  lea     rdx, [rbp+pGroup]; pGroup
0x18002faa3  call    cs:__imp_GetSecurityDescriptorGroup
0x18002faa9  mov     rcx, [rbp+pGroup]; Block
0x18002faad  call    cs:__imp_free
0x18002fab3  mov     rcx, [rbx+8]; pSecurityDescriptor
0x18002fab7  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x18002fabb  lea     r8, [rbp+pDacl]; pDacl
0x18002fabf  lea     rdx, [rbp+dwRevision]; lpbDaclPresent
0x18002fac3  call    cs:__imp_GetSecurityDescriptorDacl
0x18002fac9  cmp     [rbp+dwRevision], edi
0x18002facc  jz      short loc_18002FAD8
0x18002face  mov     rcx, [rbp+pDacl]; Block
0x18002fad2  call    cs:__imp_free
0x18002fad8  mov     rcx, [rbx+8]; pSecurityDescriptor
0x18002fadc  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x18002fae0  lea     r8, [rbp+pSacl]; pSacl
0x18002fae4  lea     rdx, [rbp+dwRevision]; lpbSaclPresent
0x18002fae8  call    cs:__imp_GetSecurityDescriptorSacl
0x18002faee  cmp     [rbp+dwRevision], edi
0x18002faf1  jz      short loc_18002FAFD
0x18002faf3  mov     rcx, [rbp+pSacl]; Block
0x18002faf7  call    cs:__imp_free
0x18002fafd  mov     rcx, [rbx+8]; Block
0x18002fb01  call    cs:__imp_free
0x18002fb07  mov     [rbx+8], rdi
0x18002fb0b  mov     rcx, [rbp+var_10]
0x18002fb0f  xor     rcx, rsp; StackCookie
0x18002fb12  call    __security_check_cookie
0x18002fb17  lea     r11, [rsp+60h+var_s0]
0x18002fb1c  mov     rbx, [r11+18h]
0x18002fb20  mov     rdi, [r11+20h]
0x18002fb24  mov     rsp, r11
0x18002fb27  pop     rbp
0x18002fb28  retn
```
