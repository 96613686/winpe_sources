# FwpmCalloutSetSecurityInfoByKey0

- ea: `0x180053660`
- end: `0x18005378c`
- name: `FwpmCalloutSetSecurityInfoByKey0`
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
- `0x180010f24`
- `0x1800203c0`
- `0x180053660`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800536bc`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800536bc`

## string_xrefs

- `0x1800536d2`: `FwpmCalloutSetSecurityInfoByKey0`
- `0x18005374b`: `FwppProxyCalloutSetSecurityInfoByKey`

## pseudocode

```c
NTSTATUS __stdcall FwpmCalloutSetSecurityInfoByKey0(
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
    v13 = WfpReportAppErrorAsNtStatus(v11, (__int64)"FwpmCalloutSetSecurityInfoByKey0", v12);
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
      v15 = FwppProxyCalloutSetSecurityInfoByKey(
              *(_QWORD *)engineHandle,
              *((_QWORD *)engineHandle + 1),
              v9,
              securityInfo,
              (__int64)&v19);
      if ( v15 < 0 )
      {
        v13 = WfpReportSysErrorAsNtStatus(v16, (int)"FwppProxyCalloutSetSecurityInfoByKey", v15);
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
0x180053660  push    rbp
0x180053662  push    rbx
0x180053663  push    rsi
0x180053664  push    rdi
0x180053665  push    r12
0x180053667  push    r13
0x180053669  push    r14
0x18005366b  push    r15
0x18005366d  lea     rbp, [rsp-7]
0x180053672  sub     rsp, 88h
0x180053679  mov     rax, cs:__security_cookie
0x180053680  xor     rax, rsp
0x180053683  mov     [rbp+3Fh+var_50], rax
0x180053687  mov     r14, [rbp+3Fh+sidGroup]
0x18005368b  xor     eax, eax
0x18005368d  mov     r15, [rbp+3Fh+dacl]
0x180053691  xorps   xmm0, xmm0
0x180053694  mov     r12, [rbp+3Fh+sacl]
0x180053698  mov     rbx, r9
0x18005369b  mov     [rbp+3Fh+var_84], rax
0x18005369f  mov     esi, r8d
0x1800536a2  mov     [rbp-49h], rax
0x1800536a6  mov     r13, rdx
0x1800536a9  mov     rdi, rcx
0x1800536ac  mov     [rbp+3Fh+var_58], rax
0x1800536b0  movups  [rbp+3Fh+SecurityDescriptor], xmm0
0x1800536b4  mov     [rbp+3Fh+var_90], rax
0x1800536b8  movups  [rbp+3Fh+var_68], xmm0
0x1800536bc  call    cs:__imp_KeGetCurrentIrql
0x1800536c3  nop     dword ptr [rax+rax+00h]
0x1800536c8  test    al, al
0x1800536ca  jz      short loc_1800536E0
0x1800536cc  mov     r8d, 0C00000BBh
0x1800536d2  lea     rdx, aFwpmcalloutset; "FwpmCalloutSetSecurityInfoByKey0"
0x1800536d9  call    WfpReportAppErrorAsNtStatus
0x1800536de  jmp     short loc_180053757
0x1800536e0  test    rdi, rdi
0x1800536e3  jnz     short loc_1800536ED
0x1800536e5  mov     r8d, 0C022001Ch
0x1800536eb  jmp     short loc_1800536D2
0x1800536ed  mov     [rsp+0C0h+Sacl], r12; Sacl
0x1800536f2  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x1800536f6  mov     r9, r14
0x1800536f9  mov     [rsp+0C0h+Dacl], r15; Dacl
0x1800536fe  mov     r8, rbx
0x180053701  mov     edx, esi
0x180053703  call    FwppSecurityDescriptorSetInfo
0x180053708  mov     rbx, rax
0x18005370b  test    rax, rax
0x18005370e  jnz     short loc_18005375A
0x180053710  lea     r8, [rbp+3Fh+var_90]
0x180053714  lea     rdx, [rbp+3Fh+var_88]
0x180053718  lea     rcx, [rbp+3Fh+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18005371c  call    BfeSecurityDescriptorEncode
0x180053721  mov     rbx, rax
0x180053724  test    rax, rax
0x180053727  jnz     short loc_18005375A
0x180053729  mov     rdx, [rdi+8]
0x18005372d  lea     rax, [rbp+3Fh+var_88]
0x180053731  mov     rcx, [rdi]
0x180053734  mov     r9d, esi
0x180053737  mov     r8, r13
0x18005373a  mov     [rsp+0C0h+Dacl], rax
0x18005373f  call    FwppProxyCalloutSetSecurityInfoByKey
0x180053744  test    eax, eax
0x180053746  jns     short loc_18005375A
0x180053748  mov     r8d, eax
0x18005374b  lea     rdx, aFwppproxycallo_3; "FwppProxyCalloutSetSecurityInfoByKey"
0x180053752  call    WfpReportSysErrorAsNtStatus
0x180053757  mov     rbx, rax
0x18005375a  lea     rcx, [rbp+3Fh+var_90]
0x18005375e  call    BfeSecurityDescriptorStorageFree
0x180053763  mov     rcx, rbx
0x180053766  call    WfpErrorToFwpErr
0x18005376b  mov     rcx, [rbp+3Fh+var_50]
0x18005376f  xor     rcx, rsp; StackCookie
0x180053772  call    __security_check_cookie
0x180053777  add     rsp, 88h
0x18005377e  pop     r15
0x180053780  pop     r14
0x180053782  pop     r13
0x180053784  pop     r12
0x180053786  pop     rdi
0x180053787  pop     rsi
0x180053788  pop     rbx
0x180053789  pop     rbp
0x18005378a  retn
```
