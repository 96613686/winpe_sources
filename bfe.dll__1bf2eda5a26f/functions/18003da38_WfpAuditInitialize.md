# WfpAuditInitialize

- ea: `0x18003da38`
- end: `0x18003dc1b`
- name: `WfpAuditInitialize`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x18002fe28`

## callees

- `0x18001236c`
- `0x180012b54`
- `0x180018b74`
- `0x180022190`
- `0x1800238b4`
- `0x18002f724`
- `0x18003da38`
- `0x18003dc24`
- `0x18003dfc8`
- `0x180058b30`
- `0x180077c90`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18003da68`
- `ntdll!RtlAdjustPrivilege` at `0x18003da68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003db72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dab2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003db72`
- `AUTHZ!AuthziInitializeAuditEventType` at `0x18003db63`
- `AUTHZ!AuthziInitializeAuditEventType` at `0x18003db63`
- `AUTHZ!AuthzInitializeResourceManager` at `0x18003daa8`
- `AUTHZ!AuthzInitializeResourceManager` at `0x18003daa8`

## string_xrefs

- `0x18003da75`: `RtlAdjustPrivilege`

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
  v7 = WfpMemAllocArray(13, 8, 8, &qword_1800F2668[2]);
  if ( v7 )
    goto LABEL_19;
  LODWORD(qword_1800F2668[0]) = 13;
  while ( (unsigned __int16)v7 < 0xDu )
  {
    szResourceManagerName = LODWORD(qword_1800F2668[2]) + 8 * (unsigned __int16)v7;
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
  v7 = WfpStringTableCreate(v9, v8, &qword_1800F2668[3]);
  if ( v7
    || (v7 = WfpAuditPolicyNotifyCreate(
               qword_1800BD318,
               4u,
               (char *)&BFE_AUDIT_POLICY_INFO,
               (__int64)WfpAuditOnAuditFlagsChange,
               szResourceManagerName,
               &qword_1800F2668[5])) != 0 )
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
0x18003da38  push    rbx
0x18003da3a  push    rsi
0x18003da3b  push    rdi
0x18003da3c  push    r14
0x18003da3e  sub     rsp, 58h
0x18003da42  mov     rax, cs:__security_cookie
0x18003da49  xor     rax, rsp
0x18003da4c  mov     [rsp+78h+var_38], rax
0x18003da51  xor     r8d, r8d; ForThread
0x18003da54  mov     [rsp+78h+OldValue], 0
0x18003da59  lea     r9, [rsp+78h+OldValue]; OldValue
0x18003da5e  lea     esi, [r8+1]
0x18003da62  mov     dl, sil; NewValue
0x18003da65  lea     ecx, [rsi+14h]; Privilege
0x18003da68  call    cs:__imp_RtlAdjustPrivilege
0x18003da6e  test    eax, eax
0x18003da70  jns     short loc_18003DA86
0x18003da72  mov     r8d, eax
0x18003da75  lea     rdx, aRtladjustprivi; "RtlAdjustPrivilege"
0x18003da7c  call    WfpReportSysErrorAsNtStatus
0x18003da81  jmp     loc_18003DBE0
0x18003da86  lea     rax, gWfpAudit
0x18003da8d  xor     r9d, r9d; pfnFreeDynamicGroups
0x18003da90  mov     [rsp+78h+phAuthzResourceManager], rax; phAuthzResourceManager
0x18003da95  xor     r8d, r8d; pfnComputeDynamicGroups
0x18003da98  lea     rax, BFE_AUDIT_SUBSYTEM_NAME; "BFE"
0x18003da9f  xor     edx, edx; pfnDynamicAccessCheck
0x18003daa1  xor     ecx, ecx; Flags
0x18003daa3  mov     [rsp+78h+szResourceManagerName], rax; int
0x18003daa8  call    cs:__imp_AuthzInitializeResourceManager
0x18003daae  test    eax, eax
0x18003dab0  jnz     short loc_18003DACC
0x18003dab2  call    cs:__imp_GetLastError
0x18003dab8  lea     rdx, aAuthzinitializ; "AuthzInitializeResourceManager"
0x18003dabf  mov     r8d, eax
0x18003dac2  call    WfpReportSysErrorAsWinError
0x18003dac7  jmp     loc_18003DBE0
0x18003dacc  mov     edi, 0Dh
0x18003dad1  mov     [rsp+78h+var_40], 0
0x18003dada  lea     eax, [rdi-1]
0x18003dadd  mul     rdi
0x18003dae0  test    rdx, rdx
0x18003dae3  jnz     loc_18003DBCB
0x18003dae9  lea     r14, BFE_AUDIT_SCHEMA
0x18003daf0  mov     rdx, rax; dwBytes
0x18003daf3  mov     rcx, r14; Src
0x18003daf6  lea     r9, qword_1800F2668+8
0x18003dafd  call    WfpBufferCopy
0x18003db02  mov     rbx, rax
0x18003db05  test    rax, rax
0x18003db08  jnz     loc_18003DBE8
0x18003db0e  lea     edx, [rdi-5]
0x18003db11  mov     ecx, edi
0x18003db13  mov     r8d, edx
0x18003db16  lea     r9, qword_1800F2668+10h
0x18003db1d  call    WfpMemAllocArray
0x18003db22  mov     rbx, rax
0x18003db25  test    rax, rax
0x18003db28  jnz     loc_18003DBE8
0x18003db2e  mov     dword ptr cs:qword_1800F2668, edi
0x18003db34  cmp     bx, di
0x18003db37  jnb     short loc_18003DB84
0x18003db39  mov     rax, cs:qword_1800F2668+10h
0x18003db40  movzx   ecx, bx
0x18003db43  lea     r10, [rcx+rcx*2]
0x18003db47  movzx   r9d, word ptr [r14+r10*4+4]
0x18003db4d  lea     rdx, [rax+rcx*8]
0x18003db51  movzx   r8d, word ptr [r14+r10*4+2]
0x18003db57  xor     ecx, ecx
0x18003db59  mov     [rsp+78h+szResourceManagerName], rdx
0x18003db5e  movzx   edx, word ptr [r14+r10*4]
0x18003db63  call    cs:__imp_AuthziInitializeAuditEventType
0x18003db69  test    eax, eax
0x18003db6b  jz      short loc_18003DB72
0x18003db6d  add     bx, si
0x18003db70  jmp     short loc_18003DB34
0x18003db72  call    cs:__imp_GetLastError
0x18003db78  lea     rdx, aAuthziinitiali_1; "AuthziInitializeAuditEventType"
0x18003db7f  jmp     loc_18003DABF
0x18003db84  lea     r8, qword_1800F2668+18h
0x18003db8b  call    WfpStringTableCreate
0x18003db90  mov     rbx, rax
0x18003db93  test    rax, rax
0x18003db96  jnz     short loc_18003DBE8
0x18003db98  lea     rax, qword_1800F2668+28h
0x18003db9f  lea     r9, WfpAuditOnAuditFlagsChange
0x18003dba6  mov     [rsp+78h+phAuthzResourceManager], rax; __int64
0x18003dbab  lea     r8, BFE_AUDIT_POLICY_INFO
0x18003dbb2  lea     edx, [rbx+4]
0x18003dbb5  lea     rcx, qword_1800BD318; pSourceSid
0x18003dbbc  call    WfpAuditPolicyNotifyCreate
0x18003dbc1  mov     rbx, rax
0x18003dbc4  test    rax, rax
0x18003dbc7  jz      short loc_18003DC01
0x18003dbc9  jmp     short loc_18003DBE8
0x18003dbcb  mov     r9d, esi
0x18003dbce  lea     rdx, aUlonglongmult; "ULongLongMult"
0x18003dbd5  mov     r8d, 80070216h
0x18003dbdb  call    WfpReportSysErrorAsHResult
0x18003dbe0  mov     rbx, rax
0x18003dbe3  test    rax, rax
0x18003dbe6  jz      short loc_18003DC01
0x18003dbe8  call    WfpAuditShutdown
0x18003dbed  test    rbx, rbx
0x18003dbf0  jz      short loc_18003DC01
0x18003dbf2  lea     rdx, aWfpauditinitia; "WfpAuditInitialize"
0x18003dbf9  mov     rcx, rbx
0x18003dbfc  call    WfpReportError
0x18003dc01  mov     rax, rbx
0x18003dc04  mov     rcx, [rsp+78h+var_38]
0x18003dc09  xor     rcx, rsp; StackCookie
0x18003dc0c  call    __security_check_cookie
0x18003dc11  add     rsp, 58h
0x18003dc15  pop     r14
0x18003dc17  pop     rdi
0x18003dc18  pop     rsi
0x18003dc19  pop     rbx
0x18003dc1a  retn
```
