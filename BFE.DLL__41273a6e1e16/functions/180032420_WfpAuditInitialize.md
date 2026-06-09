# WfpAuditInitialize

- ea: `0x180032420`
- end: `0x180032622`
- name: `WfpAuditInitialize`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180031740`

## callees

- `0x180012d8c`
- `0x1800135ac`
- `0x1800197d0`
- `0x180024880`
- `0x180025fe4`
- `0x180031210`
- `0x180032420`
- `0x180032628`
- `0x180032a2c`
- `0x18005aa60`
- `0x18007a81c`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x180032450`
- `ntdll!RtlAdjustPrivilege` at `0x180032450`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800324a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032572`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800324a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032572`
- `AUTHZ!AuthziInitializeAuditEventType` at `0x18003255d`
- `AUTHZ!AuthziInitializeAuditEventType` at `0x18003255d`
- `AUTHZ!AuthzInitializeResourceManager` at `0x180032496`
- `AUTHZ!AuthzInitializeResourceManager` at `0x180032496`

## string_xrefs

- `0x180032463`: `RtlAdjustPrivilege`

## pseudocode

```c
__int64 WfpAuditInitialize()
{
  NTSTATUS v0; // eax
  __int64 v1; // rcx
  __int64 v2; // rax
  __int64 v3; // rcx
  DWORD LastError; // eax
  __int64 v5; // rcx
  const char *v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int szResourceManagerName; // [rsp+20h] [rbp-58h]
  unsigned __int8 OldValue[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v13; // [rsp+38h] [rbp-40h]

  OldValue[0] = 0;
  v0 = RtlAdjustPrivilege(0x15u, 1u, 0, OldValue);
  if ( v0 < 0 )
  {
    v2 = WfpReportSysErrorAsNtStatus(v1, "RtlAdjustPrivilege", (unsigned int)v0);
    goto LABEL_18;
  }
  if ( !AuthzInitializeResourceManager(0, 0, 0, 0, L"BFE", &gWfpAudit) )
  {
    LastError = GetLastError();
    v6 = "AuthzInitializeResourceManager";
LABEL_5:
    v2 = WfpReportSysErrorAsWinError(v5, v6, LastError);
LABEL_18:
    v7 = v2;
    if ( !v2 )
      return v7;
    goto LABEL_19;
  }
  v13 = 0;
  if ( !is_mul_ok(0xDu, 0xCu) )
  {
    v2 = WfpReportSysErrorAsHResult(v3, "ULongLongMult", 2147942934LL, 1);
    goto LABEL_18;
  }
  v7 = WfpBufferCopy(BFE_AUDIT_SCHEMA, 0x9Cu);
  if ( v7 )
    goto LABEL_19;
  v7 = WfpMemAllocArray(13, 8, 8, &qword_1800F5698);
  if ( v7 )
    goto LABEL_19;
  dword_1800F5688 = 13;
  while ( (unsigned __int16)v7 < 0xDu )
  {
    szResourceManagerName = qword_1800F5698 + 8 * (unsigned __int16)v7;
    if ( !(unsigned int)AuthziInitializeAuditEventType(
                          0,
                          *((unsigned __int16 *)BFE_AUDIT_SCHEMA + 6 * (unsigned __int16)v7),
                          *((unsigned __int16 *)BFE_AUDIT_SCHEMA + 6 * (unsigned __int16)v7 + 1),
                          *((unsigned __int16 *)BFE_AUDIT_SCHEMA + 6 * (unsigned __int16)v7 + 2)) )
    {
      LastError = GetLastError();
      v6 = "AuthziInitializeAuditEventType";
      goto LABEL_5;
    }
    LOWORD(v7) = v7 + 1;
  }
  v7 = WfpStringTableCreate(v9, v8, &qword_1800F56A0);
  if ( v7
    || (v7 = WfpAuditPolicyNotifyCreate(
               qword_1800B7CC8,
               4u,
               (char *)&BFE_AUDIT_POLICY_INFO,
               (__int64)WfpAuditOnAuditFlagsChange,
               szResourceManagerName,
               &qword_1800F56B0)) != 0 )
  {
LABEL_19:
    WfpAuditShutdown();
    if ( v7 )
      WfpReportError(v7, "WfpAuditInitialize");
  }
  return v7;
}

```

## disassembly

```asm
0x180032420  push    rbx
0x180032422  push    rsi
0x180032423  push    rdi
0x180032424  push    r14
0x180032426  sub     rsp, 58h
0x18003242a  mov     rax, cs:__security_cookie
0x180032431  xor     rax, rsp
0x180032434  mov     [rsp+78h+var_38], rax
0x180032439  xor     r8d, r8d; ForThread
0x18003243c  mov     [rsp+78h+OldValue], 0
0x180032441  lea     r9, [rsp+78h+OldValue]; OldValue
0x180032446  lea     esi, [r8+1]
0x18003244a  mov     dl, sil; NewValue
0x18003244d  lea     ecx, [rsi+14h]; Privilege
0x180032450  call    cs:__imp_RtlAdjustPrivilege
0x180032457  nop     dword ptr [rax+rax+00h]
0x18003245c  test    eax, eax
0x18003245e  jns     short loc_180032474
0x180032460  mov     r8d, eax
0x180032463  lea     rdx, aRtladjustprivi; "RtlAdjustPrivilege"
0x18003246a  call    WfpReportSysErrorAsNtStatus
0x18003246f  jmp     loc_1800325E6
0x180032474  lea     rax, gWfpAudit
0x18003247b  xor     r9d, r9d; pfnFreeDynamicGroups
0x18003247e  mov     [rsp+78h+phAuthzResourceManager], rax; phAuthzResourceManager
0x180032483  xor     r8d, r8d; pfnComputeDynamicGroups
0x180032486  lea     rax, BFE_AUDIT_SUBSYTEM_NAME; "BFE"
0x18003248d  xor     edx, edx; pfnDynamicAccessCheck
0x18003248f  xor     ecx, ecx; Flags
0x180032491  mov     [rsp+78h+szResourceManagerName], rax; int
0x180032496  call    cs:__imp_AuthzInitializeResourceManager
0x18003249d  nop     dword ptr [rax+rax+00h]
0x1800324a2  test    eax, eax
0x1800324a4  jnz     short loc_1800324C6
0x1800324a6  call    cs:__imp_GetLastError
0x1800324ad  nop     dword ptr [rax+rax+00h]
0x1800324b2  lea     rdx, aAuthzinitializ; "AuthzInitializeResourceManager"
0x1800324b9  mov     r8d, eax
0x1800324bc  call    WfpReportSysErrorAsWinError
0x1800324c1  jmp     loc_1800325E6
0x1800324c6  mov     edi, 0Dh
0x1800324cb  mov     [rsp+78h+var_40], 0
0x1800324d4  lea     eax, [rdi-1]
0x1800324d7  mul     rdi
0x1800324da  test    rdx, rdx
0x1800324dd  jnz     loc_1800325D1
0x1800324e3  lea     r14, BFE_AUDIT_SCHEMA
0x1800324ea  mov     rdx, rax; dwBytes
0x1800324ed  mov     rcx, r14; Src
0x1800324f0  lea     r9, qword_1800F5690
0x1800324f7  call    WfpBufferCopy
0x1800324fc  mov     rbx, rax
0x1800324ff  test    rax, rax
0x180032502  jnz     loc_1800325EE
0x180032508  lea     edx, [rdi-5]
0x18003250b  mov     ecx, edi
0x18003250d  mov     r8d, edx
0x180032510  lea     r9, qword_1800F5698
0x180032517  call    WfpMemAllocArray
0x18003251c  mov     rbx, rax
0x18003251f  test    rax, rax
0x180032522  jnz     loc_1800325EE
0x180032528  mov     cs:dword_1800F5688, edi
0x18003252e  cmp     bx, di
0x180032531  jnb     short loc_18003258A
0x180032533  mov     rax, cs:qword_1800F5698
0x18003253a  movzx   ecx, bx
0x18003253d  lea     r10, [rcx+rcx*2]
0x180032541  movzx   r9d, word ptr [r14+r10*4+4]
0x180032547  lea     rdx, [rax+rcx*8]
0x18003254b  movzx   r8d, word ptr [r14+r10*4+2]
0x180032551  xor     ecx, ecx
0x180032553  mov     [rsp+78h+szResourceManagerName], rdx
0x180032558  movzx   edx, word ptr [r14+r10*4]
0x18003255d  call    cs:__imp_AuthziInitializeAuditEventType
0x180032564  nop     dword ptr [rax+rax+00h]
0x180032569  test    eax, eax
0x18003256b  jz      short loc_180032572
0x18003256d  add     bx, si
0x180032570  jmp     short loc_18003252E
0x180032572  call    cs:__imp_GetLastError
0x180032579  nop     dword ptr [rax+rax+00h]
0x18003257e  lea     rdx, aAuthziinitiali_1; "AuthziInitializeAuditEventType"
0x180032585  jmp     loc_1800324B9
0x18003258a  lea     r8, qword_1800F56A0
0x180032591  call    WfpStringTableCreate
0x180032596  mov     rbx, rax
0x180032599  test    rax, rax
0x18003259c  jnz     short loc_1800325EE
0x18003259e  lea     rax, qword_1800F56B0
0x1800325a5  lea     r9, WfpAuditOnAuditFlagsChange
0x1800325ac  mov     [rsp+78h+phAuthzResourceManager], rax; __int64
0x1800325b1  lea     r8, BFE_AUDIT_POLICY_INFO
0x1800325b8  lea     edx, [rbx+4]
0x1800325bb  lea     rcx, qword_1800B7CC8; pSourceSid
0x1800325c2  call    WfpAuditPolicyNotifyCreate
0x1800325c7  mov     rbx, rax
0x1800325ca  test    rax, rax
0x1800325cd  jz      short loc_180032607
0x1800325cf  jmp     short loc_1800325EE
0x1800325d1  mov     r9d, esi
0x1800325d4  lea     rdx, aUlonglongmult; "ULongLongMult"
0x1800325db  mov     r8d, 80070216h
0x1800325e1  call    WfpReportSysErrorAsHResult
0x1800325e6  mov     rbx, rax
0x1800325e9  test    rax, rax
0x1800325ec  jz      short loc_180032607
0x1800325ee  call    WfpAuditShutdown
0x1800325f3  test    rbx, rbx
0x1800325f6  jz      short loc_180032607
0x1800325f8  lea     rdx, aWfpauditinitia; "WfpAuditInitialize"
0x1800325ff  mov     rcx, rbx
0x180032602  call    WfpReportError
0x180032607  mov     rax, rbx
0x18003260a  mov     rcx, [rsp+78h+var_38]
0x18003260f  xor     rcx, rsp; StackCookie
0x180032612  call    __security_check_cookie
0x180032617  add     rsp, 58h
0x18003261b  pop     r14
0x18003261d  pop     rdi
0x18003261e  pop     rsi
0x18003261f  pop     rbx
0x180032620  retn
```
