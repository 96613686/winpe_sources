# BuildAuditPolicyACL

- ea: `0x180004390`
- end: `0x180004612`
- name: `BuildAuditPolicyACL`
- size: `642`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001396c`

## callees

- `0x180004390`
- `0x1800097d0`
- `0x18000a192`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000441f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000441f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004607`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800045fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004607`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180004507`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180004507`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800045d1`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800045d1`
- `api-ms-win-security-audit-l1-1-1!AuditQueryPerUserPolicy` at `0x180004411`
- `api-ms-win-security-audit-l1-1-1!AuditQueryPerUserPolicy` at `0x180004411`
- `api-ms-win-security-audit-l1-1-0!AuditFree` at `0x1800044c8`
- `api-ms-win-security-audit-l1-1-0!AuditFree` at `0x180004539`
- `api-ms-win-security-audit-l1-1-0!AuditFree` at `0x1800044c8`
- `api-ms-win-security-audit-l1-1-0!AuditFree` at `0x180004539`
- `api-ms-win-security-audit-l1-1-0!AuditQuerySystemPolicy` at `0x1800044a5`
- `api-ms-win-security-audit-l1-1-0!AuditQuerySystemPolicy` at `0x1800044a5`

## pseudocode

```c
__int64 __fastcall BuildAuditPolicyACL(WCHAR *a1, struct _ACL *a2, HLOCAL *a3)
{
  DWORD LastError; // ebx
  WCHAR *v4; // rsi
  PACL v7; // rax
  ULONG AuditingInformation; // r12d
  int v10; // r14d
  ULONG v11; // ecx
  __int64 v12; // rdx
  PAUDIT_POLICY_INFORMATION ppAuditPolicy; // [rsp+68h] [rbp-A0h] BYREF
  PACL NewAcl; // [rsp+70h] [rbp-98h] BYREF
  PSID pSid; // [rsp+78h] [rbp-90h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries[2]; // [rsp+88h] [rbp-80h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+E8h] [rbp-20h] BYREF

  LastError = 3;
  v4 = a1;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 256;
  pSid = 0;
  ppAuditPolicy = 0;
  NewAcl = 0;
  *a3 = 0;
  if ( a1 )
  {
    if ( !AuditQueryPerUserPolicy(a1, &Audit_ObjectAccess_RemovableStorage, 1u, &ppAuditPolicy) )
    {
LABEL_3:
      LastError = GetLastError();
      goto LABEL_4;
    }
    if ( ppAuditPolicy )
    {
      AuditingInformation = ppAuditPolicy->AuditingInformation;
      v10 = AuditingInformation & 3;
      AuditFree(ppAuditPolicy);
      goto LABEL_19;
    }
  }
  else
  {
    if ( !AuditQuerySystemPolicy(&Audit_ObjectAccess_RemovableStorage, 1u, &ppAuditPolicy) )
      goto LABEL_3;
    if ( ppAuditPolicy )
    {
      AuditingInformation = ppAuditPolicy->AuditingInformation;
      AuditFree(ppAuditPolicy);
      v10 = AuditingInformation & 3;
      if ( (AuditingInformation & 3) != 0 )
      {
        if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &pSid) )
          goto LABEL_3;
        v4 = (WCHAR *)pSid;
LABEL_20:
        memset_0(pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
        NewAcl = 0;
        v11 = 0;
        if ( (AuditingInformation & 1) != 0 )
        {
          pListOfExplicitEntries[0].grfAccessMode = SET_AUDIT_SUCCESS;
          v11 = 1;
          pListOfExplicitEntries[0].grfAccessPermissions = 65543;
          pListOfExplicitEntries[0].grfInheritance = 0;
          pListOfExplicitEntries[0].Trustee.TrusteeForm = TRUSTEE_IS_SID;
          pListOfExplicitEntries[0].Trustee.TrusteeType = TRUSTEE_IS_GROUP;
          pListOfExplicitEntries[0].Trustee.ptstrName = v4;
        }
        if ( (AuditingInformation & 2) != 0 )
        {
          v12 = v11++;
          pListOfExplicitEntries[v12].grfAccessMode = SET_AUDIT_FAILURE;
          pListOfExplicitEntries[v12].grfAccessPermissions = 65543;
          pListOfExplicitEntries[v12].grfInheritance = 0;
          pListOfExplicitEntries[v12].Trustee.TrusteeForm = TRUSTEE_IS_SID;
          pListOfExplicitEntries[v12].Trustee.TrusteeType = TRUSTEE_IS_GROUP;
          pListOfExplicitEntries[v12].Trustee.ptstrName = v4;
        }
        LastError = SetEntriesInAclW(v11, pListOfExplicitEntries, a2, &NewAcl);
        if ( !LastError )
        {
          v7 = NewAcl;
          *a3 = NewAcl;
          goto LABEL_26;
        }
        goto LABEL_4;
      }
      v4 = 0;
LABEL_19:
      if ( !v10 )
        goto LABEL_4;
      goto LABEL_20;
    }
  }
LABEL_4:
  v7 = (PACL)*a3;
  if ( LastError )
  {
    if ( v7 )
      LocalFree(*a3);
    *a3 = 0;
    goto LABEL_8;
  }
LABEL_26:
  if ( !v7 )
    LastError = 3;
LABEL_8:
  if ( pSid )
    LocalFree(pSid);
  return LastError;
}

```

## disassembly

```asm
0x180004390  mov     r11, rsp
0x180004393  push    rbp
0x180004394  push    rbx
0x180004395  lea     rbp, [r11-28h]
0x180004399  sub     rsp, 118h
0x1800043a0  mov     rax, cs:__security_cookie
0x1800043a7  xor     rax, rsp
0x1800043aa  mov     [rbp+20h+var_38], rax
0x1800043ae  mov     [r11+20h], rsi
0x1800043b2  mov     ebx, 3
0x1800043b7  mov     [r11-18h], rdi
0x1800043bb  mov     rsi, rcx
0x1800043be  mov     [r11-20h], r12
0x1800043c2  mov     rdi, r8
0x1800043c5  mov     [r11-28h], r13
0x1800043c9  xor     r13d, r13d
0x1800043cc  mov     [r11-30h], r14
0x1800043d0  mov     [r11-38h], r15
0x1800043d4  mov     r15, rdx
0x1800043d7  mov     dword ptr [rbp+20h+pIdentifierAuthority.Value], 0
0x1800043de  mov     word ptr [rbp+20h+pIdentifierAuthority.Value+4], 100h
0x1800043e4  mov     [rsp+120h+pSid], r13
0x1800043e9  mov     [rsp+120h+ppAuditPolicy], r13
0x1800043ee  mov     [rsp+120h+NewAcl], r13
0x1800043f3  mov     [r8], r13
0x1800043f6  test    rcx, rcx
0x1800043f9  jz      loc_180004494
0x1800043ff  lea     r9, [rsp+120h+ppAuditPolicy]; ppAuditPolicy
0x180004404  mov     r8d, 1; dwPolicyCount
0x18000440a  lea     rdx, Audit_ObjectAccess_RemovableStorage; pSubCategoryGuids
0x180004411  call    cs:__imp_AuditQueryPerUserPolicy
0x180004417  test    al, al
0x180004419  jnz     loc_180004521
0x18000441f  call    cs:__imp_GetLastError
0x180004425  mov     ebx, eax
0x180004427  mov     rax, [rdi]
0x18000442a  test    ebx, ebx
0x18000442c  jz      loc_1800045E9
0x180004432  test    rax, rax
0x180004435  jnz     loc_1800045F9
0x18000443b  mov     [rdi], r13
0x18000443e  mov     rcx, [rsp+120h+pSid]; hMem
0x180004443  mov     r15, [rsp+120h+var_30]
0x18000444b  mov     r14, [rsp+120h+var_28]
0x180004453  mov     r13, [rsp+120h+var_20]
0x18000445b  mov     r12, [rsp+120h+var_18]
0x180004463  mov     rdi, [rsp+110h]
0x18000446b  mov     rsi, [rsp+120h+arg_18]
0x180004473  test    rcx, rcx
0x180004476  jnz     loc_180004607
0x18000447c  mov     eax, ebx
0x18000447e  mov     rcx, [rbp+20h+var_38]
0x180004482  xor     rcx, rsp; StackCookie
0x180004485  call    __security_check_cookie
0x18000448a  add     rsp, 118h
0x180004491  pop     rbx
0x180004492  pop     rbp
0x180004493  retn
0x180004494  lea     r8, [rsp+120h+ppAuditPolicy]; ppAuditPolicy
0x180004499  mov     edx, 1; dwPolicyCount
0x18000449e  lea     rcx, Audit_ObjectAccess_RemovableStorage; pSubCategoryGuids
0x1800044a5  call    cs:__imp_AuditQuerySystemPolicy
0x1800044ab  test    al, al
0x1800044ad  jz      loc_18000441F
0x1800044b3  mov     rcx, [rsp+120h+ppAuditPolicy]; Buffer
0x1800044b8  test    rcx, rcx
0x1800044bb  jz      loc_180004427
0x1800044c1  mov     r12d, [rcx+10h]
0x1800044c5  mov     r14d, r12d
0x1800044c8  call    cs:__imp_AuditFree
0x1800044ce  and     r14d, ebx
0x1800044d1  jz      short loc_18000451C
0x1800044d3  lea     rax, [rsp+120h+pSid]
0x1800044d8  xor     r9d, r9d; nSubAuthority1
0x1800044db  mov     [rsp+50h], rax; pSid
0x1800044e0  lea     rcx, [rbp+20h+pIdentifierAuthority]; pIdentifierAuthority
0x1800044e4  mov     [rsp+120h+nSubAuthority7], r13d; nSubAuthority7
0x1800044e9  xor     r8d, r8d; nSubAuthority0
0x1800044ec  mov     [rsp+120h+nSubAuthority6], r13d; nSubAuthority6
0x1800044f1  mov     dl, 1; nSubAuthorityCount
0x1800044f3  mov     [rsp+120h+nSubAuthority5], r13d; nSubAuthority5
0x1800044f8  mov     [rsp+120h+nSubAuthority4], r13d; nSubAuthority4
0x1800044fd  mov     [rsp+120h+nSubAuthority3], r13d; nSubAuthority3
0x180004502  mov     [rsp+120h+nSubAuthority2], r13d; nSubAuthority2
0x180004507  call    cs:__imp_AllocateAndInitializeSid
0x18000450d  test    eax, eax
0x18000450f  jz      loc_18000441F
0x180004515  mov     rsi, [rsp+120h+pSid]
0x18000451a  jmp     short loc_180004548
0x18000451c  mov     rsi, r13
0x18000451f  jmp     short loc_18000453F
0x180004521  mov     rcx, [rsp+120h+ppAuditPolicy]; Buffer
0x180004526  test    rcx, rcx
0x180004529  jz      loc_180004427
0x18000452f  mov     r12d, [rcx+10h]
0x180004533  mov     r14d, r12d
0x180004536  and     r14d, ebx
0x180004539  call    cs:__imp_AuditFree
0x18000453f  test    r14d, r14d
0x180004542  jz      loc_180004427
0x180004548  xor     edx, edx; Val
0x18000454a  lea     rcx, [rbp+20h+pListOfExplicitEntries]; void *
0x18000454e  mov     r8d, 60h ; '`'; Size
0x180004554  call    memset_0
0x180004559  mov     [rsp+120h+NewAcl], r13
0x18000455e  mov     ecx, r13d
0x180004561  test    r12b, 1
0x180004565  jz      short loc_18000458D
0x180004567  mov     [rbp+20h+pListOfExplicitEntries.grfAccessMode], 5
0x18000456e  mov     ecx, 1
0x180004573  mov     [rbp+20h+pListOfExplicitEntries.grfAccessPermissions], 10007h
0x18000457a  mov     [rbp+20h+pListOfExplicitEntries.grfInheritance], r13d
0x18000457e  mov     [rbp+20h+pListOfExplicitEntries.Trustee.TrusteeForm], r13d
0x180004582  mov     [rbp+20h+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x180004589  mov     [rbp+20h+pListOfExplicitEntries.Trustee.ptstrName], rsi
0x18000458d  test    r12b, 2
0x180004591  jz      short loc_1800045C5
0x180004593  mov     eax, ecx
0x180004595  lea     rdx, [rax+rax*2]
0x180004599  add     rdx, rdx
0x18000459c  inc     ecx; cCountOfExplicitEntries
0x18000459e  mov     [rbp+rdx*8+20h+pListOfExplicitEntries.grfAccessMode], 6
0x1800045a6  mov     [rbp+rdx*8+20h+pListOfExplicitEntries.grfAccessPermissions], 10007h
0x1800045ae  mov     [rbp+rdx*8+20h+pListOfExplicitEntries.grfInheritance], r13d
0x1800045b3  mov     [rbp+rdx*8+20h+pListOfExplicitEntries.Trustee.TrusteeForm], r13d
0x1800045b8  mov     [rbp+rdx*8+20h+pListOfExplicitEntries.Trustee.TrusteeType], 2
0x1800045c0  mov     [rbp+rdx*8+20h+pListOfExplicitEntries.Trustee.ptstrName], rsi
0x1800045c5  lea     r9, [rsp+120h+NewAcl]; NewAcl
0x1800045ca  mov     r8, r15; OldAcl
0x1800045cd  lea     rdx, [rbp+20h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800045d1  call    cs:__imp_SetEntriesInAclW
0x1800045d7  mov     ebx, eax
0x1800045d9  test    eax, eax
0x1800045db  jnz     loc_180004427
0x1800045e1  mov     rax, [rsp+120h+NewAcl]
0x1800045e6  mov     [rdi], rax
0x1800045e9  test    rax, rax
0x1800045ec  mov     eax, 3
0x1800045f1  cmovz   ebx, eax
0x1800045f4  jmp     loc_18000443E
0x1800045f9  mov     rcx, rax; hMem
0x1800045fc  call    cs:__imp_LocalFree
0x180004602  jmp     loc_18000443B
0x180004607  call    cs:__imp_LocalFree
0x18000460d  jmp     loc_18000447C
```
