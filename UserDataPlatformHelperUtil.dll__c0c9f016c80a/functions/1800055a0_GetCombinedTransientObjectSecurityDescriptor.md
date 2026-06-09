# GetCombinedTransientObjectSecurityDescriptor

- ea: `0x1800055a0`
- end: `0x1800057ba`
- name: `GetCombinedTransientObjectSecurityDescriptor`
- size: `538`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x18000520c`
- `0x1800055a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005678`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000566e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800056a7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18000566e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800056a7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800056f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005732`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000577a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005789`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800056f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005732`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000577a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005789`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1800055c8`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1800055ff`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1800055c8`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1800055ff`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800055e1`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180005640`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180005762`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180005798`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800057a7`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800055e1`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180005640`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180005762`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180005798`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800057a7`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180005712`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180005712`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x1800056cc`
- `api-ms-win-security-provider-l1-1-0!GetExplicitEntriesFromAclW` at `0x1800056cc`

## pseudocode

```c
__int64 __fastcall GetCombinedTransientObjectSecurityDescriptor(__int64 a1, __int64 a2, unsigned int a3, void **a4)
{
  int v7; // ebx
  int UpdatedSecurityDescriptor; // ebx
  int v10; // ebx
  PSECURITY_DESCRIPTOR v11; // rax
  PSECURITY_DESCRIPTOR v12; // rcx
  signed int LastError; // eax
  signed int ExplicitEntriesFromAclW; // eax
  signed int v15; // eax
  PACL v16; // rcx
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+20h] [rbp-50h] BYREF
  PSECURITY_DESCRIPTOR v18; // [rsp+28h] [rbp-48h] BYREF
  PEXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+30h] [rbp-40h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+38h] [rbp-38h] BYREF
  WINBOOL bDaclPresent; // [rsp+3Ch] [rbp-34h] BYREF
  ULONG pcCountOfExplicitEntries; // [rsp+40h] [rbp-30h] BYREF
  PACL NewAcl; // [rsp+48h] [rbp-28h] BYREF
  void *v24; // [rsp+50h] [rbp-20h] BYREF
  PACL pacl; // [rsp+58h] [rbp-18h] BYREF
  PACL pDacl; // [rsp+60h] [rbp-10h] BYREF

  pSecurityDescriptor = 0;
  v7 = QueryTransientObjectSecurityDescriptor(a3, a1, &pSecurityDescriptor);
  if ( v7 >= 0 )
  {
    v18 = 0;
    v10 = QueryTransientObjectSecurityDescriptor(a3, a2, &v18);
    if ( v10 == -1073741772 )
    {
      v11 = pSecurityDescriptor;
      v12 = v18;
      pSecurityDescriptor = 0;
      *a4 = v11;
      if ( !v12 )
        return 0;
LABEL_35:
      FreeTransientObjectSecurityDescriptor();
LABEL_36:
      if ( pSecurityDescriptor )
        FreeTransientObjectSecurityDescriptor();
      return 0;
    }
    if ( v10 >= 0 )
    {
      pDacl = 0;
      bDaclPresent = 0;
      bDaclDefaulted = 0;
      if ( GetSecurityDescriptorDacl(pSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted)
        && (pacl = 0, GetSecurityDescriptorDacl(v18, &bDaclPresent, &pacl, &bDaclDefaulted)) )
      {
        pcCountOfExplicitEntries = 0;
        pListOfExplicitEntries = 0;
        ExplicitEntriesFromAclW = GetExplicitEntriesFromAclW(pacl, &pcCountOfExplicitEntries, &pListOfExplicitEntries);
        UpdatedSecurityDescriptor = ExplicitEntriesFromAclW;
        if ( ExplicitEntriesFromAclW )
        {
          if ( ExplicitEntriesFromAclW > 0 )
            UpdatedSecurityDescriptor = (unsigned __int16)ExplicitEntriesFromAclW | 0x80070000;
        }
        else
        {
          NewAcl = 0;
          v15 = SetEntriesInAclW(pcCountOfExplicitEntries, pListOfExplicitEntries, pDacl, &NewAcl);
          UpdatedSecurityDescriptor = v15;
          if ( v15 )
          {
            if ( v15 > 0 )
              UpdatedSecurityDescriptor = (unsigned __int16)v15 | 0x80070000;
          }
          else
          {
            v24 = 0;
            UpdatedSecurityDescriptor = GetUpdatedSecurityDescriptor(pSecurityDescriptor, NewAcl, &v24);
            if ( UpdatedSecurityDescriptor >= 0 )
            {
              v16 = NewAcl;
              *a4 = v24;
              if ( v16 )
                LocalFree(v16);
              if ( pListOfExplicitEntries )
                LocalFree(pListOfExplicitEntries);
              if ( !v18 )
                goto LABEL_36;
              goto LABEL_35;
            }
            if ( v24 )
              FreeTransientObjectSecurityDescriptor();
          }
          if ( NewAcl )
            LocalFree(NewAcl);
        }
        if ( pListOfExplicitEntries )
          LocalFree(pListOfExplicitEntries);
      }
      else
      {
        LastError = GetLastError();
        UpdatedSecurityDescriptor = LastError;
        if ( LastError > 0 )
          UpdatedSecurityDescriptor = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      UpdatedSecurityDescriptor = v10 | 0x10000000;
    }
    if ( v18 )
      FreeTransientObjectSecurityDescriptor();
    goto LABEL_3;
  }
  UpdatedSecurityDescriptor = v7 | 0x10000000;
LABEL_3:
  if ( pSecurityDescriptor )
    FreeTransientObjectSecurityDescriptor();
  return (unsigned int)UpdatedSecurityDescriptor;
}

```

## disassembly

```asm
0x1800055a0  push    rbp
0x1800055a2  push    rbx
0x1800055a3  push    rsi
0x1800055a4  push    rdi
0x1800055a5  push    r14
0x1800055a7  mov     rbp, rsp
0x1800055aa  sub     rsp, 70h
0x1800055ae  mov     esi, r8d
0x1800055b1  mov     [rbp+pSecurityDescriptor], 0
0x1800055b9  mov     r14, rdx
0x1800055bc  lea     r8, [rbp+pSecurityDescriptor]
0x1800055c0  mov     rdx, rcx
0x1800055c3  mov     rdi, r9
0x1800055c6  mov     ecx, esi
0x1800055c8  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x1800055ce  mov     ebx, eax
0x1800055d0  test    eax, eax
0x1800055d2  jns     short loc_1800055EE
0x1800055d4  bts     ebx, 1Ch
0x1800055d8  mov     rcx, [rbp+pSecurityDescriptor]
0x1800055dc  test    rcx, rcx
0x1800055df  jz      short loc_1800055E7
0x1800055e1  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800055e7  mov     eax, ebx
0x1800055e9  jmp     loc_1800057AF
0x1800055ee  lea     r8, [rbp+var_48]
0x1800055f2  mov     [rbp+var_48], 0
0x1800055fa  mov     rdx, r14
0x1800055fd  mov     ecx, esi
0x1800055ff  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180005605  mov     ebx, eax
0x180005607  cmp     eax, 0C0000034h
0x18000560c  jnz     short loc_18000562F
0x18000560e  mov     rax, [rbp+pSecurityDescriptor]
0x180005612  mov     rcx, [rbp+var_48]
0x180005616  mov     [rbp+pSecurityDescriptor], 0
0x18000561e  mov     [rdi], rax
0x180005621  test    rcx, rcx
0x180005624  jz      loc_1800057AD
0x18000562a  jmp     loc_180005798
0x18000562f  test    ebx, ebx
0x180005631  jns     short loc_180005648
0x180005633  bts     ebx, 1Ch
0x180005637  mov     rcx, [rbp+var_48]
0x18000563b  test    rcx, rcx
0x18000563e  jz      short loc_1800055D8
0x180005640  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180005646  jmp     short loc_1800055D8
0x180005648  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x18000564c  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180005650  lea     r8, [rbp+pDacl]; pDacl
0x180005654  mov     [rbp+pDacl], 0
0x18000565c  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180005660  mov     [rbp+bDaclPresent], 0
0x180005667  mov     [rbp+bDaclDefaulted], 0
0x18000566e  call    cs:__imp_GetSecurityDescriptorDacl
0x180005674  test    eax, eax
0x180005676  jnz     short loc_18000568F
0x180005678  call    cs:__imp_GetLastError
0x18000567e  mov     ebx, eax
0x180005680  test    eax, eax
0x180005682  jle     short loc_180005637
0x180005684  movzx   ebx, ax
0x180005687  or      ebx, 80070000h
0x18000568d  jmp     short loc_180005637
0x18000568f  mov     rcx, [rbp+var_48]; pSecurityDescriptor
0x180005693  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180005697  lea     r8, [rbp+pacl]; pDacl
0x18000569b  mov     [rbp+pacl], 0
0x1800056a3  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800056a7  call    cs:__imp_GetSecurityDescriptorDacl
0x1800056ad  test    eax, eax
0x1800056af  jz      short loc_180005678
0x1800056b1  mov     rcx, [rbp+pacl]; pacl
0x1800056b5  lea     r8, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800056b9  lea     rdx, [rbp+pcCountOfExplicitEntries]; pcCountOfExplicitEntries
0x1800056bd  mov     [rbp+pcCountOfExplicitEntries], 0
0x1800056c4  mov     [rbp+pListOfExplicitEntries], 0
0x1800056cc  call    cs:__imp_GetExplicitEntriesFromAclW
0x1800056d2  mov     ebx, eax
0x1800056d4  test    eax, eax
0x1800056d6  jz      short loc_1800056FB
0x1800056d8  jle     short loc_1800056E3
0x1800056da  movzx   ebx, ax
0x1800056dd  or      ebx, 80070000h
0x1800056e3  mov     rcx, [rbp+pListOfExplicitEntries]; hMem
0x1800056e7  test    rcx, rcx
0x1800056ea  jz      loc_180005637
0x1800056f0  call    cs:__imp_LocalFree
0x1800056f6  jmp     loc_180005637
0x1800056fb  mov     r8, [rbp+pDacl]; OldAcl
0x1800056ff  lea     r9, [rbp+NewAcl]; NewAcl
0x180005703  mov     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x180005707  mov     ecx, [rbp+pcCountOfExplicitEntries]; cCountOfExplicitEntries
0x18000570a  mov     [rbp+NewAcl], 0
0x180005712  call    cs:__imp_SetEntriesInAclW
0x180005718  mov     ebx, eax
0x18000571a  test    eax, eax
0x18000571c  jz      short loc_18000573A
0x18000571e  jle     short loc_180005729
0x180005720  movzx   ebx, ax
0x180005723  or      ebx, 80070000h
0x180005729  mov     rcx, [rbp+NewAcl]; hMem
0x18000572d  test    rcx, rcx
0x180005730  jz      short loc_1800056E3
0x180005732  call    cs:__imp_LocalFree
0x180005738  jmp     short loc_1800056E3
0x18000573a  mov     rdx, [rbp+NewAcl]; pDacl
0x18000573e  lea     r8, [rbp+var_20]; void **
0x180005742  mov     rcx, [rbp+pSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x180005746  mov     [rbp+var_20], 0
0x18000574e  call    ?GetUpdatedSecurityDescriptor@@YAJPEAXPEAU_ACL@@PEAPEAX@Z; GetUpdatedSecurityDescriptor(void *,_ACL *,void * *)
0x180005753  mov     ebx, eax
0x180005755  test    eax, eax
0x180005757  jns     short loc_18000576A
0x180005759  mov     rcx, [rbp+var_20]
0x18000575d  test    rcx, rcx
0x180005760  jz      short loc_180005729
0x180005762  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180005768  jmp     short loc_180005729
0x18000576a  mov     rcx, [rbp+NewAcl]; hMem
0x18000576e  mov     rax, [rbp+var_20]
0x180005772  mov     [rdi], rax
0x180005775  test    rcx, rcx
0x180005778  jz      short loc_180005780
0x18000577a  call    cs:__imp_LocalFree
0x180005780  mov     rcx, [rbp+pListOfExplicitEntries]; hMem
0x180005784  test    rcx, rcx
0x180005787  jz      short loc_18000578F
0x180005789  call    cs:__imp_LocalFree
0x18000578f  mov     rcx, [rbp+var_48]
0x180005793  test    rcx, rcx
0x180005796  jz      short loc_18000579E
0x180005798  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18000579e  mov     rcx, [rbp+pSecurityDescriptor]
0x1800057a2  test    rcx, rcx
0x1800057a5  jz      short loc_1800057AD
0x1800057a7  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800057ad  xor     eax, eax
0x1800057af  add     rsp, 70h
0x1800057b3  pop     r14
0x1800057b5  pop     rdi
0x1800057b6  pop     rsi
0x1800057b7  pop     rbx
0x1800057b8  pop     rbp
0x1800057b9  retn
```
