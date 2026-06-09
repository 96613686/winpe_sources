# WfpAuditPolicyNotifyOnChange

- ea: `0x1800328d0`
- end: `0x180032a23`
- name: `WfpAuditPolicyNotifyOnChange`
- size: `339`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180032628`

## callees

- `0x180012d8c`
- `0x1800328d0`
- `0x18005aa60`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800329b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800329ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800329b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800329ce`
- `api-ms-win-security-audit-l1-1-0!AuditFree` at `0x1800329ee`
- `api-ms-win-security-audit-l1-1-0!AuditFree` at `0x1800329ee`
- `api-ms-win-security-audit-l1-1-0!AuditQuerySystemPolicy` at `0x1800329a5`
- `api-ms-win-security-audit-l1-1-0!AuditQuerySystemPolicy` at `0x1800329a5`
- `api-ms-win-security-audit-l1-1-0!AuditComputeEffectivePolicyBySid` at `0x180032913`
- `api-ms-win-security-audit-l1-1-0!AuditComputeEffectivePolicyBySid` at `0x180032913`

## string_xrefs

- `0x1800329da`: `AuditComputeEffectivePolicyBySid`
- `0x1800329c5`: `AuditQuerySystemPolicy`

## pseudocode

```c
void __fastcall WfpAuditPolicyNotifyOnChange(__int64 a1)
{
  void *v2; // rcx
  unsigned int v3; // edi
  ULONG v4; // edx
  unsigned int v5; // r8d
  __int64 v6; // rdx
  ULONG AuditingInformation; // r9d
  __int64 v8; // rcx
  DWORD LastError; // eax
  __int64 v10; // rcx
  const char *v11; // rdx
  PAUDIT_POLICY_INFORMATION ppAuditPolicy; // [rsp+20h] [rbp-18h] BYREF

  ppAuditPolicy = 0;
  v2 = *(void **)a1;
  v3 = -1;
  v4 = *(_DWORD *)(a1 + 16);
  if ( v2 )
  {
    if ( AuditComputeEffectivePolicyBySid(v2, *(const GUID **)(a1 + 32), v4, &ppAuditPolicy) )
      goto LABEL_3;
    LastError = GetLastError();
    v11 = "AuditComputeEffectivePolicyBySid";
LABEL_18:
    WfpReportSysErrorAsWinError(v10, v11, LastError);
    goto LABEL_4;
  }
  if ( !AuditQuerySystemPolicy(*(const GUID **)(a1 + 32), v4, &ppAuditPolicy) )
  {
    LastError = GetLastError();
    v11 = "AuditQuerySystemPolicy";
    goto LABEL_18;
  }
LABEL_3:
  v3 = *(_DWORD *)(a1 + 80);
  if ( *(_DWORD *)(a1 + 16) )
  {
    v5 = 0;
    v6 = 0;
    do
    {
      AuditingInformation = ppAuditPolicy[v6].AuditingInformation;
      v8 = 16 * v6;
      if ( (AuditingInformation & 1) != 0 )
        v3 |= *(_DWORD *)(*(_QWORD *)(a1 + 24) + v8 + 8);
      if ( (AuditingInformation & 2) != 0 )
        v3 |= *(_DWORD *)(*(_QWORD *)(a1 + 24) + v8 + 12);
      ++v5;
      ++v6;
    }
    while ( v5 < *(_DWORD *)(a1 + 16) );
  }
LABEL_4:
  if ( ppAuditPolicy )
    AuditFree(ppAuditPolicy);
  if ( v3 != *(_DWORD *)(a1 + 84) )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD))(a1 + 40))(*(_QWORD *)(a1 + 48), v3);
    *(_DWORD *)(a1 + 84) = v3;
  }
}

```

## disassembly

```asm
0x1800328d0  mov     [rsp+arg_8], rbx
0x1800328d5  push    rdi
0x1800328d6  sub     rsp, 30h
0x1800328da  mov     rax, cs:__security_cookie
0x1800328e1  xor     rax, rsp
0x1800328e4  mov     [rsp+38h+var_10], rax
0x1800328e9  mov     rbx, rcx
0x1800328ec  mov     [rsp+38h+ppAuditPolicy], 0
0x1800328f5  mov     rcx, [rcx]; pSid
0x1800328f8  or      edi, 0FFFFFFFFh
0x1800328fb  mov     edx, [rbx+10h]; dwPolicyCount
0x1800328fe  test    rcx, rcx
0x180032901  jz      loc_18003299C
0x180032907  mov     r8d, edx; dwPolicyCount
0x18003290a  lea     r9, [rsp+38h+ppAuditPolicy]; ppAuditPolicy
0x18003290f  mov     rdx, [rbx+20h]; pSubCategoryGuids
0x180032913  call    cs:__imp_AuditComputeEffectivePolicyBySid
0x18003291a  nop     dword ptr [rax+rax+00h]
0x18003291f  test    al, al
0x180032921  jz      loc_1800329CE
0x180032927  cmp     dword ptr [rbx+10h], 0
0x18003292b  mov     edi, [rbx+50h]
0x18003292e  ja      short loc_180032960
0x180032930  mov     rcx, [rsp+38h+ppAuditPolicy]; Buffer
0x180032935  test    rcx, rcx
0x180032938  jnz     loc_1800329EE
0x18003293e  cmp     edi, [rbx+54h]
0x180032941  jnz     loc_180032A0C
0x180032947  mov     rcx, [rsp+38h+var_10]
0x18003294c  xor     rcx, rsp; StackCookie
0x18003294f  call    __security_check_cookie
0x180032954  mov     rbx, [rsp+38h+arg_8]
0x180032959  add     rsp, 30h
0x18003295d  pop     rdi
0x18003295e  retn
0x180032960  xor     r8d, r8d
0x180032963  xor     edx, edx
0x180032965  mov     rax, [rsp+38h+ppAuditPolicy]
0x18003296a  lea     rcx, [rdx+rdx*8]
0x18003296e  mov     r9d, [rax+rcx*4+10h]
0x180032973  mov     rcx, rdx
0x180032976  shl     rcx, 4
0x18003297a  test    r9b, 1
0x18003297e  jnz     short loc_1800329FF
0x180032980  test    r9b, 2
0x180032984  jz      short loc_18003298E
0x180032986  mov     rax, [rbx+18h]
0x18003298a  or      edi, [rax+rcx+0Ch]
0x18003298e  inc     r8d
0x180032991  inc     rdx
0x180032994  cmp     r8d, [rbx+10h]
0x180032998  jnb     short loc_180032930
0x18003299a  jmp     short loc_180032965
0x18003299c  mov     rcx, [rbx+20h]; pSubCategoryGuids
0x1800329a0  lea     r8, [rsp+38h+ppAuditPolicy]; ppAuditPolicy
0x1800329a5  call    cs:__imp_AuditQuerySystemPolicy
0x1800329ac  nop     dword ptr [rax+rax+00h]
0x1800329b1  test    al, al
0x1800329b3  jnz     loc_180032927
0x1800329b9  call    cs:__imp_GetLastError
0x1800329c0  nop     dword ptr [rax+rax+00h]
0x1800329c5  lea     rdx, aAuditquerysyst_0; "AuditQuerySystemPolicy"
0x1800329cc  jmp     short loc_1800329E1
0x1800329ce  call    cs:__imp_GetLastError
0x1800329d5  nop     dword ptr [rax+rax+00h]
0x1800329da  lea     rdx, aAuditcomputeef_0; "AuditComputeEffectivePolicyBySid"
0x1800329e1  mov     r8d, eax
0x1800329e4  call    WfpReportSysErrorAsWinError
0x1800329e9  jmp     loc_180032930
0x1800329ee  call    cs:__imp_AuditFree
0x1800329f5  nop     dword ptr [rax+rax+00h]
0x1800329fa  jmp     loc_18003293E
0x1800329ff  mov     rax, [rbx+18h]
0x180032a03  or      edi, [rax+rcx+8]
0x180032a07  jmp     loc_180032980
0x180032a0c  mov     rcx, [rbx+30h]
0x180032a10  mov     edx, edi
0x180032a12  mov     rax, [rbx+28h]
0x180032a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032a1b  mov     [rbx+54h], edi
0x180032a1e  jmp     loc_180032947
```
