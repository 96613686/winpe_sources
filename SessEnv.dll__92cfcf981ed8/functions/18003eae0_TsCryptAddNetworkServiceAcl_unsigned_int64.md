# TsCryptAddNetworkServiceAcl(unsigned __int64)

- ea: `0x18003eae0`
- end: `0x18003eba5`
- name: `?TsCryptAddNetworkServiceAcl@@YAH_K@Z`
- size: `197`
- prototype: `__int64 __fastcall(NCRYPT_HANDLE hObject)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18003ea44`

## callees

- `0x18003eae0`
- `0x18003ebac`
- `0x18003ee84`
- `0x18003eec8`
- `0x18003efa8`
- `0x18003f0b0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18003eb50`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18003eb50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eb78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eb81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eb8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eb78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eb81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003eb8a`

## pseudocode

```c
__int64 __fastcall TsCryptAddNetworkServiceAcl(NCRYPT_HANDLE hObject)
{
  unsigned int v2; // ebp
  struct _SECURITY_DESCRIPTOR *SecurityDescriptor; // rax
  struct _SECURITY_DESCRIPTOR *v4; // rbx
  const unsigned __int16 *v5; // rcx
  struct _ACL *Dacl; // rsi
  void *SIDForAccount; // rax
  void *v8; // rdi
  struct _ACL *v9; // rsi
  WORD pControl; // [rsp+48h] [rbp+10h] BYREF
  DWORD dwRevision; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  SecurityDescriptor = TsCryptGetSecurityDescriptor(hObject);
  v4 = SecurityDescriptor;
  if ( SecurityDescriptor )
  {
    Dacl = TsCryptGetDacl(SecurityDescriptor);
    if ( Dacl )
    {
      SIDForAccount = TsCryptGetSIDForAccount(v5);
      v8 = SIDForAccount;
      if ( SIDForAccount )
      {
        v9 = TsCryptAddSidToAcl(Dacl, SIDForAccount);
        if ( v9 )
        {
          pControl = 0;
          dwRevision = 0;
          if ( GetSecurityDescriptorControl(v4, &pControl, &dwRevision) )
            v2 = TsCryptSetSecurityDescriptorDacl(hObject, v9, (pControl >> 12) & 1);
          LocalFree(v9);
        }
        LocalFree(v8);
      }
    }
    LocalFree(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x18003eae0  mov     [rsp+arg_0], rbx
0x18003eae5  mov     [rsp+arg_18], rbp
0x18003eaea  push    rsi
0x18003eaeb  push    rdi
0x18003eaec  push    r14
0x18003eaee  sub     rsp, 20h
0x18003eaf2  mov     r14, rcx
0x18003eaf5  xor     ebp, ebp
0x18003eaf7  call    ?TsCryptGetSecurityDescriptor@@YAPEAU_SECURITY_DESCRIPTOR@@_K@Z; TsCryptGetSecurityDescriptor(unsigned __int64)
0x18003eafc  mov     rbx, rax
0x18003eaff  test    rax, rax
0x18003eb02  jz      loc_18003EB90
0x18003eb08  mov     rcx, rax; struct _SECURITY_DESCRIPTOR *
0x18003eb0b  call    ?TsCryptGetDacl@@YAPEAU_ACL@@PEAU_SECURITY_DESCRIPTOR@@@Z; TsCryptGetDacl(_SECURITY_DESCRIPTOR *)
0x18003eb10  mov     rsi, rax
0x18003eb13  test    rax, rax
0x18003eb16  jz      short loc_18003EB87
0x18003eb18  call    ?TsCryptGetSIDForAccount@@YAPEAXPEBG@Z; TsCryptGetSIDForAccount(ushort const *)
0x18003eb1d  mov     rdi, rax
0x18003eb20  test    rax, rax
0x18003eb23  jz      short loc_18003EB87
0x18003eb25  mov     rdx, rax; void *
0x18003eb28  mov     rcx, rsi; OldAcl
0x18003eb2b  call    ?TsCryptAddSidToAcl@@YAPEAU_ACL@@PEBU1@PEAX@Z; TsCryptAddSidToAcl(_ACL const *,void *)
0x18003eb30  mov     rsi, rax
0x18003eb33  test    rax, rax
0x18003eb36  jz      short loc_18003EB7E
0x18003eb38  xor     eax, eax
0x18003eb3a  lea     r8, [rsp+38h+dwRevision]; lpdwRevision
0x18003eb3f  lea     rdx, [rsp+38h+pControl]; pControl
0x18003eb44  mov     [rsp+38h+pControl], ax
0x18003eb49  mov     rcx, rbx; pSecurityDescriptor
0x18003eb4c  mov     [rsp+38h+dwRevision], eax
0x18003eb50  call    cs:__imp_GetSecurityDescriptorControl
0x18003eb56  test    eax, eax
0x18003eb58  jz      short loc_18003EB75
0x18003eb5a  movzx   r8d, [rsp+38h+pControl]
0x18003eb60  mov     rdx, rsi; pDacl
0x18003eb63  shr     r8d, 0Ch
0x18003eb67  mov     rcx, r14; hObject
0x18003eb6a  and     r8d, 1; int
0x18003eb6e  call    ?TsCryptSetSecurityDescriptorDacl@@YAH_KPEBU_ACL@@H@Z; TsCryptSetSecurityDescriptorDacl(unsigned __int64,_ACL const *,int)
0x18003eb73  mov     ebp, eax
0x18003eb75  mov     rcx, rsi; hMem
0x18003eb78  call    cs:__imp_LocalFree
0x18003eb7e  mov     rcx, rdi; hMem
0x18003eb81  call    cs:__imp_LocalFree
0x18003eb87  mov     rcx, rbx; hMem
0x18003eb8a  call    cs:__imp_LocalFree
0x18003eb90  mov     rbx, [rsp+38h+arg_0]
0x18003eb95  mov     eax, ebp
0x18003eb97  mov     rbp, [rsp+38h+arg_18]
0x18003eb9c  add     rsp, 20h
0x18003eba0  pop     r14
0x18003eba2  pop     rdi
0x18003eba3  pop     rsi
0x18003eba4  retn
```
