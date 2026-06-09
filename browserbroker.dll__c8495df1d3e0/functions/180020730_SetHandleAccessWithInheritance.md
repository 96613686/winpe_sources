# SetHandleAccessWithInheritance

- ea: `0x180020730`
- end: `0x18002083c`
- name: `SetHandleAccessWithInheritance`
- size: `268`
- prototype: `__int64 __fastcall(HANDLE handle, SE_OBJECT_TYPE ObjectType, void *, unsigned int, bool)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180020678`
- `0x180020844`
- `0x1800208fc`

## callees

- `0x18002040c`
- `0x18002052c`
- `0x180020730`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002081b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020825`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002081b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020825`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002080b`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18002080b`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180020787`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180020787`

## pseudocode

```c
__int64 __fastcall SetHandleAccessWithInheritance(
        HANDLE handle,
        SE_OBJECT_TYPE ObjectType,
        void *a3,
        DWORD a4,
        bool a5)
{
  unsigned int SecurityInfo; // edi
  __int64 v10; // r9
  PACL v11; // rbx
  struct _ACL *pDacl; // rax
  PACL v13; // rsi
  unsigned int psidGroup; // [rsp+20h] [rbp-40h]
  PACL pAcl; // [rsp+40h] [rbp-20h] BYREF
  PACL v17; // [rsp+48h] [rbp-18h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-10h] BYREF

  hMem = 0;
  pAcl = 0;
  SecurityInfo = GetSecurityInfo(handle, ObjectType, 4u, 0, 0, &pAcl, 0, &hMem);
  if ( !SecurityInfo )
  {
    v11 = 0;
    a5 = 0;
    v17 = 0;
    if ( AclHasSIDCheckAndSetAccess(pAcl, a3, a4, v10, psidGroup, &a5) )
    {
      pDacl = pAcl;
      v13 = 0;
    }
    else
    {
      SecurityInfo = CreateSIDAcl(pAcl, &v17, a3, a4);
      if ( SecurityInfo )
      {
LABEL_8:
        LocalFree(hMem);
        return SecurityInfo;
      }
      v11 = v17;
      pDacl = v17;
      v13 = v17;
    }
    SecurityInfo = SetSecurityInfo(handle, ObjectType, 4u, 0, 0, pDacl, 0);
    if ( v13 )
      LocalFree(v11);
    goto LABEL_8;
  }
  return SecurityInfo;
}

```

## disassembly

```asm
0x180020730  mov     r11, rsp
0x180020733  push    rbp
0x180020734  push    rbx
0x180020735  push    rsi
0x180020736  push    rdi
0x180020737  push    r12
0x180020739  push    r14
0x18002073b  push    r15
0x18002073d  mov     rbp, rsp
0x180020740  sub     rsp, 60h
0x180020744  mov     esi, r9d
0x180020747  mov     [rbp+hMem], 0
0x18002074f  xor     r9d, r9d; ppsidOwner
0x180020752  mov     [rbp+pAcl], 0
0x18002075a  lea     rax, [rbp+hMem]
0x18002075e  mov     r14, r8
0x180020761  mov     [r11-60h], rax
0x180020765  mov     r15d, edx
0x180020768  mov     qword ptr [r11-68h], 0
0x180020770  lea     rax, [rbp+pAcl]
0x180020774  mov     [r11-70h], rax
0x180020778  lea     r8d, [r9+4]; SecurityInfo
0x18002077c  mov     r12, rcx
0x18002077f  mov     qword ptr [r11-78h], 0
0x180020787  call    cs:__imp_GetSecurityInfo
0x18002078d  mov     edi, eax
0x18002078f  test    eax, eax
0x180020791  jnz     loc_18002082B
0x180020797  mov     rcx, [rbp+pAcl]; pAcl
0x18002079b  xor     ebx, ebx
0x18002079d  mov     [rbp+arg_20], al
0x1800207a0  mov     r8d, esi; unsigned int
0x1800207a3  lea     rax, [rbp+arg_20]
0x1800207a7  mov     [rbp+var_18], rbx
0x1800207ab  mov     rdx, r14; pSid2
0x1800207ae  mov     [rsp+60h+pDacl], rax; bool *
0x1800207b3  call    ?AclHasSIDCheckAndSetAccess@@YA_NPEAU_ACL@@PEAXKKKPEA_N@Z; AclHasSIDCheckAndSetAccess(_ACL *,void *,ulong,ulong,ulong,bool *)
0x1800207b8  test    al, al
0x1800207ba  jnz     short loc_1800207E1
0x1800207bc  mov     rcx, [rbp+pAcl]; pAcl
0x1800207c0  lea     rdx, [rbp+var_18]; struct _ACL **
0x1800207c4  mov     r9d, esi; unsigned int
0x1800207c7  mov     r8, r14; void *
0x1800207ca  call    ?CreateSIDAcl@@YAKPEAU_ACL@@PEAPEAU1@PEAXKK@Z; CreateSIDAcl(_ACL *,_ACL * *,void *,ulong,ulong)
0x1800207cf  mov     edi, eax
0x1800207d1  test    eax, eax
0x1800207d3  jnz     short loc_180020821
0x1800207d5  mov     rbx, [rbp+var_18]
0x1800207d9  mov     rax, rbx
0x1800207dc  mov     rsi, rbx
0x1800207df  jmp     short loc_1800207E7
0x1800207e1  mov     rax, [rbp+pAcl]
0x1800207e5  xor     esi, esi
0x1800207e7  xor     r9d, r9d; psidOwner
0x1800207ea  mov     [rsp+60h+pSacl], 0; pSacl
0x1800207f3  mov     [rsp+60h+pDacl], rax; pDacl
0x1800207f8  mov     edx, r15d; ObjectType
0x1800207fb  mov     rcx, r12; handle
0x1800207fe  mov     [rsp+60h+psidGroup], 0; psidGroup
0x180020807  lea     r8d, [r9+4]; SecurityInfo
0x18002080b  call    cs:__imp_SetSecurityInfo
0x180020811  mov     edi, eax
0x180020813  test    rsi, rsi
0x180020816  jz      short loc_180020821
0x180020818  mov     rcx, rbx; hMem
0x18002081b  call    cs:__imp_LocalFree
0x180020821  mov     rcx, [rbp+hMem]; hMem
0x180020825  call    cs:__imp_LocalFree
0x18002082b  mov     eax, edi
0x18002082d  add     rsp, 60h
0x180020831  pop     r15
0x180020833  pop     r14
0x180020835  pop     r12
0x180020837  pop     rdi
0x180020838  pop     rsi
0x180020839  pop     rbx
0x18002083a  pop     rbp
0x18002083b  retn
```
