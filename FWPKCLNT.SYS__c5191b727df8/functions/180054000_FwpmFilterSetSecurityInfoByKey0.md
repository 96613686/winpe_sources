# FwpmFilterSetSecurityInfoByKey0

- ea: `0x180054000`
- end: `0x18005412c`
- name: `FwpmFilterSetSecurityInfoByKey0`
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
- `0x18001116c`
- `0x1800203c0`
- `0x180054000`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x18005405c`
- `ntoskrnl!KeGetCurrentIrql` at `0x18005405c`

## string_xrefs

- `0x180054072`: `FwpmFilterSetSecurityInfoByKey0`
- `0x1800540eb`: `FwppProxyFilterSetSecurityInfoByKey`

## pseudocode

```c
NTSTATUS __stdcall FwpmFilterSetSecurityInfoByKey0(
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
    v13 = WfpReportAppErrorAsNtStatus(v11, (__int64)"FwpmFilterSetSecurityInfoByKey0", v12);
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
      v15 = FwppProxyFilterSetSecurityInfoByKey(
              *(_QWORD *)engineHandle,
              *((_QWORD *)engineHandle + 1),
              v9,
              securityInfo,
              (__int64)&v19);
      if ( v15 < 0 )
      {
        v13 = WfpReportSysErrorAsNtStatus(v16, (int)"FwppProxyFilterSetSecurityInfoByKey", v15);
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
0x180054000  push    rbp
0x180054002  push    rbx
0x180054003  push    rsi
0x180054004  push    rdi
0x180054005  push    r12
0x180054007  push    r13
0x180054009  push    r14
0x18005400b  push    r15
0x18005400d  lea     rbp, [rsp-7]
0x180054012  sub     rsp, 88h
0x180054019  mov     rax, cs:__security_cookie
0x180054020  xor     rax, rsp
0x180054023  mov     [rbp+3Fh+var_50], rax
0x180054027  mov     r14, [rbp+3Fh+sidGroup]
0x18005402b  xor     eax, eax
0x18005402d  mov     r15, [rbp+3Fh+dacl]
0x180054031  xorps   xmm0, xmm0
0x180054034  mov     r12, [rbp+3Fh+sacl]
0x180054038  mov     rbx, r9
0x18005403b  mov     [rbp+3Fh+var_84], rax
0x18005403f  mov     esi, r8d
0x180054042  mov     [rbp-49h], rax
0x180054046  mov     r13, rdx
0x180054049  mov     rdi, rcx
0x18005404c  mov     [rbp+3Fh+var_58], rax
0x180054050  movups  [rbp+3Fh+SecurityDescriptor], xmm0
0x180054054  mov     [rbp+3Fh+var_90], rax
0x180054058  movups  [rbp+3Fh+var_68], xmm0
0x18005405c  call    cs:__imp_KeGetCurrentIrql
0x180054063  nop     dword ptr [rax+rax+00h]
0x180054068  test    al, al
0x18005406a  jz      short loc_180054080
0x18005406c  mov     r8d, 0C00000BBh
0x180054072  lea     rdx, aFwpmfiltersets; "FwpmFilterSetSecurityInfoByKey0"
0x180054079  call    WfpReportAppErrorAsNtStatus
0x18005407e  jmp     short loc_1800540F7
0x180054080  test    rdi, rdi
0x180054083  jnz     short loc_18005408D
0x180054085  mov     r8d, 0C022001Ch
0x18005408b  jmp     short loc_180054072
0x18005408d  mov     [rsp+0C0h+Sacl], r12; Sacl
0x180054092  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x180054096  mov     r9, r14
0x180054099  mov     [rsp+0C0h+Dacl], r15; Dacl
0x18005409e  mov     r8, rbx
0x1800540a1  mov     edx, esi
0x1800540a3  call    FwppSecurityDescriptorSetInfo
0x1800540a8  mov     rbx, rax
0x1800540ab  test    rax, rax
0x1800540ae  jnz     short loc_1800540FA
0x1800540b0  lea     r8, [rbp+3Fh+var_90]
0x1800540b4  lea     rdx, [rbp+3Fh+var_88]
0x1800540b8  lea     rcx, [rbp+3Fh+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1800540bc  call    BfeSecurityDescriptorEncode
0x1800540c1  mov     rbx, rax
0x1800540c4  test    rax, rax
0x1800540c7  jnz     short loc_1800540FA
0x1800540c9  mov     rdx, [rdi+8]
0x1800540cd  lea     rax, [rbp+3Fh+var_88]
0x1800540d1  mov     rcx, [rdi]
0x1800540d4  mov     r9d, esi
0x1800540d7  mov     r8, r13
0x1800540da  mov     [rsp+0C0h+Dacl], rax
0x1800540df  call    FwppProxyFilterSetSecurityInfoByKey
0x1800540e4  test    eax, eax
0x1800540e6  jns     short loc_1800540FA
0x1800540e8  mov     r8d, eax
0x1800540eb  lea     rdx, aFwppproxyfilte_5; "FwppProxyFilterSetSecurityInfoByKey"
0x1800540f2  call    WfpReportSysErrorAsNtStatus
0x1800540f7  mov     rbx, rax
0x1800540fa  lea     rcx, [rbp+3Fh+var_90]
0x1800540fe  call    BfeSecurityDescriptorStorageFree
0x180054103  mov     rcx, rbx
0x180054106  call    WfpErrorToFwpErr
0x18005410b  mov     rcx, [rbp+3Fh+var_50]
0x18005410f  xor     rcx, rsp; StackCookie
0x180054112  call    __security_check_cookie
0x180054117  add     rsp, 88h
0x18005411e  pop     r15
0x180054120  pop     r14
0x180054122  pop     r13
0x180054124  pop     r12
0x180054126  pop     rdi
0x180054127  pop     rsi
0x180054128  pop     rbx
0x180054129  pop     rbp
0x18005412a  retn
```
