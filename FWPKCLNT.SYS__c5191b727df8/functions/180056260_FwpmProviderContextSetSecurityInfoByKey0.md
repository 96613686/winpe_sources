# FwpmProviderContextSetSecurityInfoByKey0

- ea: `0x180056260`
- end: `0x18005638c`
- name: `FwpmProviderContextSetSecurityInfoByKey0`
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
- `0x1800115fc`
- `0x1800203c0`
- `0x180056260`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800562bc`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800562bc`

## string_xrefs

- `0x1800562d2`: `FwpmProviderContextSetSecurityInfoByKey0`
- `0x18005634b`: `FwppProxyProviderContextSetSecurityInfoByKey`

## pseudocode

```c
NTSTATUS __stdcall FwpmProviderContextSetSecurityInfoByKey0(
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
    v13 = WfpReportAppErrorAsNtStatus(v11, (__int64)"FwpmProviderContextSetSecurityInfoByKey0", v12);
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
      v15 = FwppProxyProviderContextSetSecurityInfoByKey(
              *(_QWORD *)engineHandle,
              *((_QWORD *)engineHandle + 1),
              v9,
              securityInfo,
              (__int64)&v19);
      if ( v15 < 0 )
      {
        v13 = WfpReportSysErrorAsNtStatus(v16, (int)"FwppProxyProviderContextSetSecurityInfoByKey", v15);
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
0x180056260  push    rbp
0x180056262  push    rbx
0x180056263  push    rsi
0x180056264  push    rdi
0x180056265  push    r12
0x180056267  push    r13
0x180056269  push    r14
0x18005626b  push    r15
0x18005626d  lea     rbp, [rsp-7]
0x180056272  sub     rsp, 88h
0x180056279  mov     rax, cs:__security_cookie
0x180056280  xor     rax, rsp
0x180056283  mov     [rbp+3Fh+var_50], rax
0x180056287  mov     r14, [rbp+3Fh+sidGroup]
0x18005628b  xor     eax, eax
0x18005628d  mov     r15, [rbp+3Fh+dacl]
0x180056291  xorps   xmm0, xmm0
0x180056294  mov     r12, [rbp+3Fh+sacl]
0x180056298  mov     rbx, r9
0x18005629b  mov     [rbp+3Fh+var_84], rax
0x18005629f  mov     esi, r8d
0x1800562a2  mov     [rbp-49h], rax
0x1800562a6  mov     r13, rdx
0x1800562a9  mov     rdi, rcx
0x1800562ac  mov     [rbp+3Fh+var_58], rax
0x1800562b0  movups  [rbp+3Fh+SecurityDescriptor], xmm0
0x1800562b4  mov     [rbp+3Fh+var_90], rax
0x1800562b8  movups  [rbp+3Fh+var_68], xmm0
0x1800562bc  call    cs:__imp_KeGetCurrentIrql
0x1800562c3  nop     dword ptr [rax+rax+00h]
0x1800562c8  test    al, al
0x1800562ca  jz      short loc_1800562E0
0x1800562cc  mov     r8d, 0C00000BBh
0x1800562d2  lea     rdx, aFwpmproviderco; "FwpmProviderContextSetSecurityInfoByKey"...
0x1800562d9  call    WfpReportAppErrorAsNtStatus
0x1800562de  jmp     short loc_180056357
0x1800562e0  test    rdi, rdi
0x1800562e3  jnz     short loc_1800562ED
0x1800562e5  mov     r8d, 0C022001Ch
0x1800562eb  jmp     short loc_1800562D2
0x1800562ed  mov     [rsp+0C0h+Sacl], r12; Sacl
0x1800562f2  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x1800562f6  mov     r9, r14
0x1800562f9  mov     [rsp+0C0h+Dacl], r15; Dacl
0x1800562fe  mov     r8, rbx
0x180056301  mov     edx, esi
0x180056303  call    FwppSecurityDescriptorSetInfo
0x180056308  mov     rbx, rax
0x18005630b  test    rax, rax
0x18005630e  jnz     short loc_18005635A
0x180056310  lea     r8, [rbp+3Fh+var_90]
0x180056314  lea     rdx, [rbp+3Fh+var_88]
0x180056318  lea     rcx, [rbp+3Fh+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18005631c  call    BfeSecurityDescriptorEncode
0x180056321  mov     rbx, rax
0x180056324  test    rax, rax
0x180056327  jnz     short loc_18005635A
0x180056329  mov     rdx, [rdi+8]
0x18005632d  lea     rax, [rbp+3Fh+var_88]
0x180056331  mov     rcx, [rdi]
0x180056334  mov     r9d, esi
0x180056337  mov     r8, r13
0x18005633a  mov     [rsp+0C0h+Dacl], rax
0x18005633f  call    FwppProxyProviderContextSetSecurityInfoByKey
0x180056344  test    eax, eax
0x180056346  jns     short loc_18005635A
0x180056348  mov     r8d, eax
0x18005634b  lea     rdx, aFwppproxyprovi_12; "FwppProxyProviderContextSetSecurityInfo"...
0x180056352  call    WfpReportSysErrorAsNtStatus
0x180056357  mov     rbx, rax
0x18005635a  lea     rcx, [rbp+3Fh+var_90]
0x18005635e  call    BfeSecurityDescriptorStorageFree
0x180056363  mov     rcx, rbx
0x180056366  call    WfpErrorToFwpErr
0x18005636b  mov     rcx, [rbp+3Fh+var_50]
0x18005636f  xor     rcx, rsp; StackCookie
0x180056372  call    __security_check_cookie
0x180056377  add     rsp, 88h
0x18005637e  pop     r15
0x180056380  pop     r14
0x180056382  pop     r13
0x180056384  pop     r12
0x180056386  pop     rdi
0x180056387  pop     rsi
0x180056388  pop     rbx
0x180056389  pop     rbp
0x18005638a  retn
```
