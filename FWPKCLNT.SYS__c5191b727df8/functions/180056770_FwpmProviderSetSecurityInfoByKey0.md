# FwpmProviderSetSecurityInfoByKey0

- ea: `0x180056770`
- end: `0x18005689c`
- name: `FwpmProviderSetSecurityInfoByKey0`
- size: `300`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, const GUID *key, SECURITY_INFORMATION securityInfo, const SID *sidOwner, const SID *sidGroup, const ACL *dacl, const ACL *sacl)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x180004904`
- `0x1800050cc`
- `0x1800083f8`
- `0x1800086fc`
- `0x180008f10`
- `0x18000fe2c`
- `0x180011790`
- `0x1800203c0`
- `0x180056770`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800567cc`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800567cc`

## string_xrefs

- `0x1800567e2`: `FwpmProviderSetSecurityInfoByKey0`
- `0x18005685b`: `FwppProxyProviderSetSecurityInfoByKey`

## pseudocode

```c
NTSTATUS __stdcall FwpmProviderSetSecurityInfoByKey0(
        HANDLE engineHandle,
        const GUID *key,
        SECURITY_INFORMATION securityInfo,
        const SID *sidOwner,
        const SID *sidGroup,
        const ACL *dacl,
        const ACL *sacl)
{
  int v9; // r13d
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rbx
  int v15; // eax
  __int64 v16; // rcx
  PVOID v18; // [rsp+30h] [rbp-51h] BYREF
  __int64 v19; // [rsp+38h] [rbp-49h] BYREF
  int v20; // [rsp+40h] [rbp-41h]
  _OWORD SecurityDescriptor[2]; // [rsp+48h] [rbp-39h] BYREF
  __int64 v22; // [rsp+68h] [rbp-19h]

  v20 = 0;
  v19 = 0;
  v9 = (int)key;
  v22 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v18 = 0;
  if ( KeGetCurrentIrql() )
  {
    v12 = 3221225659LL;
LABEL_3:
    v13 = WfpReportAppErrorAsNtStatus(v11, (__int64)"FwpmProviderSetSecurityInfoByKey0", v12);
LABEL_10:
    v14 = v13;
    goto LABEL_11;
  }
  if ( !engineHandle )
  {
    v12 = 3223453724LL;
    goto LABEL_3;
  }
  v14 = FwppSecurityDescriptorSetInfo(
          SecurityDescriptor,
          securityInfo,
          (void *)sidOwner,
          (void *)sidGroup,
          (PACL)dacl,
          (PACL)sacl);
  if ( !v14 )
  {
    v14 = BfeSecurityDescriptorEncode(SecurityDescriptor, (__int64)&v19, &v18);
    if ( !v14 )
    {
      v15 = FwppProxyProviderSetSecurityInfoByKey(
              *(_QWORD *)engineHandle,
              *((_QWORD *)engineHandle + 1),
              v9,
              securityInfo,
              (__int64)&v19);
      if ( v15 < 0 )
      {
        v13 = WfpReportSysErrorAsNtStatus(v16, (int)"FwppProxyProviderSetSecurityInfoByKey", v15);
        goto LABEL_10;
      }
    }
  }
LABEL_11:
  BfeSecurityDescriptorStorageFree(&v18);
  return WfpErrorToFwpErr(v14);
}

```

## disassembly

```asm
0x180056770  push    rbp
0x180056772  push    rbx
0x180056773  push    rsi
0x180056774  push    rdi
0x180056775  push    r12
0x180056777  push    r13
0x180056779  push    r14
0x18005677b  push    r15
0x18005677d  lea     rbp, [rsp-7]
0x180056782  sub     rsp, 88h
0x180056789  mov     rax, cs:__security_cookie
0x180056790  xor     rax, rsp
0x180056793  mov     [rbp+3Fh+var_50], rax
0x180056797  mov     r14, [rbp+3Fh+sidGroup]
0x18005679b  xor     eax, eax
0x18005679d  mov     r15, [rbp+3Fh+dacl]
0x1800567a1  xorps   xmm0, xmm0
0x1800567a4  mov     r12, [rbp+3Fh+sacl]
0x1800567a8  mov     rbx, r9
0x1800567ab  mov     [rbp+3Fh+var_84], rax
0x1800567af  mov     esi, r8d
0x1800567b2  mov     [rbp-49h], rax
0x1800567b6  mov     r13, rdx
0x1800567b9  mov     rdi, rcx
0x1800567bc  mov     [rbp+3Fh+var_58], rax
0x1800567c0  movups  [rbp+3Fh+SecurityDescriptor], xmm0
0x1800567c4  mov     [rbp+3Fh+var_90], rax
0x1800567c8  movups  [rbp+3Fh+var_68], xmm0
0x1800567cc  call    cs:__imp_KeGetCurrentIrql
0x1800567d3  nop     dword ptr [rax+rax+00h]
0x1800567d8  test    al, al
0x1800567da  jz      short loc_1800567F0
0x1800567dc  mov     r8d, 0C00000BBh
0x1800567e2  lea     rdx, aFwpmproviderse; "FwpmProviderSetSecurityInfoByKey0"
0x1800567e9  call    WfpReportAppErrorAsNtStatus
0x1800567ee  jmp     short loc_180056867
0x1800567f0  test    rdi, rdi
0x1800567f3  jnz     short loc_1800567FD
0x1800567f5  mov     r8d, 0C022001Ch
0x1800567fb  jmp     short loc_1800567E2
0x1800567fd  mov     [rsp+0C0h+Sacl], r12; Sacl
0x180056802  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x180056806  mov     r9, r14
0x180056809  mov     [rsp+0C0h+Dacl], r15; Dacl
0x18005680e  mov     r8, rbx
0x180056811  mov     edx, esi
0x180056813  call    FwppSecurityDescriptorSetInfo
0x180056818  mov     rbx, rax
0x18005681b  test    rax, rax
0x18005681e  jnz     short loc_18005686A
0x180056820  lea     r8, [rbp+3Fh+var_90]
0x180056824  lea     rdx, [rbp+3Fh+var_88]
0x180056828  lea     rcx, [rbp+3Fh+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18005682c  call    BfeSecurityDescriptorEncode
0x180056831  mov     rbx, rax
0x180056834  test    rax, rax
0x180056837  jnz     short loc_18005686A
0x180056839  mov     rdx, [rdi+8]
0x18005683d  lea     rax, [rbp+3Fh+var_88]
0x180056841  mov     rcx, [rdi]
0x180056844  mov     r9d, esi
0x180056847  mov     r8, r13
0x18005684a  mov     [rsp+0C0h+Dacl], rax
0x18005684f  call    FwppProxyProviderSetSecurityInfoByKey
0x180056854  test    eax, eax
0x180056856  jns     short loc_18005686A
0x180056858  mov     r8d, eax
0x18005685b  lea     rdx, aFwppproxyprovi_13; "FwppProxyProviderSetSecurityInfoByKey"
0x180056862  call    WfpReportSysErrorAsNtStatus
0x180056867  mov     rbx, rax
0x18005686a  lea     rcx, [rbp+3Fh+var_90]
0x18005686e  call    BfeSecurityDescriptorStorageFree
0x180056873  mov     rcx, rbx
0x180056876  call    WfpErrorToFwpErr
0x18005687b  mov     rcx, [rbp+3Fh+var_50]
0x18005687f  xor     rcx, rsp; StackCookie
0x180056882  call    __security_check_cookie
0x180056887  add     rsp, 88h
0x18005688e  pop     r15
0x180056890  pop     r14
0x180056892  pop     r13
0x180056894  pop     r12
0x180056896  pop     rdi
0x180056897  pop     rsi
0x180056898  pop     rbx
0x180056899  pop     rbp
0x18005689a  retn
```
