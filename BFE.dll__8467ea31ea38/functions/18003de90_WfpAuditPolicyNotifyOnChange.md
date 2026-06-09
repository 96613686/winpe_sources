# WfpAuditPolicyNotifyOnChange

- ea: `0x18003de90`
- end: `0x18003dfc1`
- name: `WfpAuditPolicyNotifyOnChange`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003dc24`

## callees

- `0x18001236c`
- `0x18003de90`
- `0x180058b30`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003df7b`
- `api-ms-win-security-audit-l1-1-0!AuditFree` at `0x18003df95`
- `api-ms-win-security-audit-l1-1-0!AuditFree` at `0x18003df95`
- `api-ms-win-security-audit-l1-1-0!AuditQuerySystemPolicy` at `0x18003df5e`
- `api-ms-win-security-audit-l1-1-0!AuditQuerySystemPolicy` at `0x18003df5e`
- `api-ms-win-security-audit-l1-1-0!AuditComputeEffectivePolicyBySid` at `0x18003ded3`
- `api-ms-win-security-audit-l1-1-0!AuditComputeEffectivePolicyBySid` at `0x18003ded3`

## string_xrefs

- `0x18003df81`: `AuditComputeEffectivePolicyBySid`
- `0x18003df72`: `AuditQuerySystemPolicy`

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
0x18003de90  mov     [rsp+arg_8], rbx
0x18003de95  push    rdi
0x18003de96  sub     rsp, 30h
0x18003de9a  mov     rax, cs:__security_cookie
0x18003dea1  xor     rax, rsp
0x18003dea4  mov     [rsp+38h+var_10], rax
0x18003dea9  mov     rbx, rcx
0x18003deac  mov     [rsp+38h+ppAuditPolicy], 0
0x18003deb5  mov     rcx, [rcx]; pSid
0x18003deb8  or      edi, 0FFFFFFFFh
0x18003debb  mov     edx, [rbx+10h]; dwPolicyCount
0x18003debe  test    rcx, rcx
0x18003dec1  jz      loc_18003DF55
0x18003dec7  mov     r8d, edx; dwPolicyCount
0x18003deca  lea     r9, [rsp+38h+ppAuditPolicy]; ppAuditPolicy
0x18003decf  mov     rdx, [rbx+20h]; pSubCategoryGuids
0x18003ded3  call    cs:__imp_AuditComputeEffectivePolicyBySid
0x18003ded9  test    al, al
0x18003dedb  jz      loc_18003DF7B
0x18003dee1  cmp     dword ptr [rbx+10h], 0
0x18003dee5  mov     edi, [rbx+50h]
0x18003dee8  ja      short loc_18003DF19
0x18003deea  mov     rcx, [rsp+38h+ppAuditPolicy]; Buffer
0x18003deef  test    rcx, rcx
0x18003def2  jnz     loc_18003DF95
0x18003def8  cmp     edi, [rbx+54h]
0x18003defb  jnz     loc_18003DFAA
0x18003df01  mov     rcx, [rsp+38h+var_10]
0x18003df06  xor     rcx, rsp; StackCookie
0x18003df09  call    __security_check_cookie
0x18003df0e  mov     rbx, [rsp+38h+arg_8]
0x18003df13  add     rsp, 30h
0x18003df17  pop     rdi
0x18003df18  retn
0x18003df19  xor     r8d, r8d
0x18003df1c  xor     edx, edx
0x18003df1e  mov     rax, [rsp+38h+ppAuditPolicy]
0x18003df23  lea     rcx, [rdx+rdx*8]
0x18003df27  mov     r9d, [rax+rcx*4+10h]
0x18003df2c  mov     rcx, rdx
0x18003df2f  shl     rcx, 4
0x18003df33  test    r9b, 1
0x18003df37  jnz     short loc_18003DFA0
0x18003df39  test    r9b, 2
0x18003df3d  jz      short loc_18003DF47
0x18003df3f  mov     rax, [rbx+18h]
0x18003df43  or      edi, [rax+rcx+0Ch]
0x18003df47  inc     r8d
0x18003df4a  inc     rdx
0x18003df4d  cmp     r8d, [rbx+10h]
0x18003df51  jnb     short loc_18003DEEA
0x18003df53  jmp     short loc_18003DF1E
0x18003df55  mov     rcx, [rbx+20h]; pSubCategoryGuids
0x18003df59  lea     r8, [rsp+38h+ppAuditPolicy]; ppAuditPolicy
0x18003df5e  call    cs:__imp_AuditQuerySystemPolicy
0x18003df64  test    al, al
0x18003df66  jnz     loc_18003DEE1
0x18003df6c  call    cs:__imp_GetLastError
0x18003df72  lea     rdx, aAuditquerysyst_0; "AuditQuerySystemPolicy"
0x18003df79  jmp     short loc_18003DF88
0x18003df7b  call    cs:__imp_GetLastError
0x18003df81  lea     rdx, aAuditcomputeef_0; "AuditComputeEffectivePolicyBySid"
0x18003df88  mov     r8d, eax
0x18003df8b  call    WfpReportSysErrorAsWinError
0x18003df90  jmp     loc_18003DEEA
0x18003df95  call    cs:__imp_AuditFree
0x18003df9b  jmp     loc_18003DEF8
0x18003dfa0  mov     rax, [rbx+18h]
0x18003dfa4  or      edi, [rax+rcx+8]
0x18003dfa8  jmp     short loc_18003DF39
0x18003dfaa  mov     rcx, [rbx+30h]
0x18003dfae  mov     edx, edi
0x18003dfb0  mov     rax, [rbx+28h]
0x18003dfb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dfb9  mov     [rbx+54h], edi
0x18003dfbc  jmp     loc_18003DF01
```
