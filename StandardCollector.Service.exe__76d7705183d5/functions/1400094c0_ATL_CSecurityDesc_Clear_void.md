# ATL::CSecurityDesc::Clear(void)

- ea: `0x1400094c0`
- end: `0x1400095c9`
- name: `?Clear@CSecurityDesc@ATL@@MEAAXXZ`
- size: `265`
- prototype: `void __fastcall(ATL::CSecurityDesc *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400086fc`
- `0x140008a28`
- `0x140009480`
- `0x1400095cc`
- `0x140011b04`

## callees

- `0x1400094c0`
- `0x1400137e0`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorControl` at `0x1400094fe`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x1400094fe`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x140009527`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x140009527`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x140009543`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x140009543`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x140009563`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x140009563`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x140009588`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x140009588`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140009531`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14000954d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140009572`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140009597`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1400095a1`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140009531`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x14000954d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140009572`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x140009597`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1400095a1`

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
0x1400094c0  mov     [rsp-8+arg_8], rbx
0x1400094c5  mov     [rsp-8+arg_10], rdi
0x1400094ca  push    rbp
0x1400094cb  mov     rbp, rsp
0x1400094ce  sub     rsp, 60h
0x1400094d2  mov     rax, cs:__security_cookie
0x1400094d9  xor     rax, rsp
0x1400094dc  mov     [rbp+var_10], rax
0x1400094e0  mov     rbx, rcx
0x1400094e3  xor     edi, edi
0x1400094e5  mov     rcx, [rcx+8]; pSecurityDescriptor
0x1400094e9  test    rcx, rcx
0x1400094ec  jz      loc_1400095AB
0x1400094f2  lea     r8, [rbp+dwRevision]; lpdwRevision
0x1400094f6  mov     [rbp+pControl], di
0x1400094fa  lea     rdx, [rbp+pControl]; pControl
0x1400094fe  call    cs:__imp_GetSecurityDescriptorControl
0x140009504  test    eax, eax
0x140009506  jz      loc_14000959D
0x14000950c  mov     eax, 8000h
0x140009511  test    [rbp+pControl], ax
0x140009515  jnz     loc_14000959D
0x14000951b  mov     rcx, [rbx+8]; pSecurityDescriptor
0x14000951f  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x140009523  lea     rdx, [rbp+pOwner]; pOwner
0x140009527  call    cs:__imp_GetSecurityDescriptorOwner
0x14000952d  mov     rcx, [rbp+pOwner]; Block
0x140009531  call    cs:__imp_free
0x140009537  mov     rcx, [rbx+8]; pSecurityDescriptor
0x14000953b  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x14000953f  lea     rdx, [rbp+pGroup]; pGroup
0x140009543  call    cs:__imp_GetSecurityDescriptorGroup
0x140009549  mov     rcx, [rbp+pGroup]; Block
0x14000954d  call    cs:__imp_free
0x140009553  mov     rcx, [rbx+8]; pSecurityDescriptor
0x140009557  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x14000955b  lea     r8, [rbp+pDacl]; pDacl
0x14000955f  lea     rdx, [rbp+dwRevision]; lpbDaclPresent
0x140009563  call    cs:__imp_GetSecurityDescriptorDacl
0x140009569  cmp     [rbp+dwRevision], edi
0x14000956c  jz      short loc_140009578
0x14000956e  mov     rcx, [rbp+pDacl]; Block
0x140009572  call    cs:__imp_free
0x140009578  mov     rcx, [rbx+8]; pSecurityDescriptor
0x14000957c  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x140009580  lea     r8, [rbp+pSacl]; pSacl
0x140009584  lea     rdx, [rbp+dwRevision]; lpbSaclPresent
0x140009588  call    cs:__imp_GetSecurityDescriptorSacl
0x14000958e  cmp     [rbp+dwRevision], edi
0x140009591  jz      short loc_14000959D
0x140009593  mov     rcx, [rbp+pSacl]; Block
0x140009597  call    cs:__imp_free
0x14000959d  mov     rcx, [rbx+8]; Block
0x1400095a1  call    cs:__imp_free
0x1400095a7  mov     [rbx+8], rdi
0x1400095ab  mov     rcx, [rbp+var_10]
0x1400095af  xor     rcx, rsp; StackCookie
0x1400095b2  call    __security_check_cookie
0x1400095b7  lea     r11, [rsp+60h+var_s0]
0x1400095bc  mov     rbx, [r11+18h]
0x1400095c0  mov     rdi, [r11+20h]
0x1400095c4  mov     rsp, r11
0x1400095c7  pop     rbp
0x1400095c8  retn
```
