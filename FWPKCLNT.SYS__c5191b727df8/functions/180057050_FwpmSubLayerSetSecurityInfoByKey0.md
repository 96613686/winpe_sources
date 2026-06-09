# FwpmSubLayerSetSecurityInfoByKey0

- ea: `0x180057050`
- end: `0x18005717c`
- name: `FwpmSubLayerSetSecurityInfoByKey0`
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
- `0x1800119f4`
- `0x1800203c0`
- `0x180057050`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1800570ac`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800570ac`

## string_xrefs

- `0x1800570c2`: `FwpmSubLayerSetSecurityInfoByKey0`
- `0x18005713b`: `FwppProxySubLayerSetSecurityInfoByKey`

## pseudocode

```c
NTSTATUS __stdcall FwpmSubLayerSetSecurityInfoByKey0(
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
    v13 = WfpReportAppErrorAsNtStatus(v11, (__int64)"FwpmSubLayerSetSecurityInfoByKey0", v12);
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
      v15 = FwppProxySubLayerSetSecurityInfoByKey(
              *(_QWORD *)engineHandle,
              *((_QWORD *)engineHandle + 1),
              v9,
              securityInfo,
              (__int64)&v19);
      if ( v15 < 0 )
      {
        v13 = WfpReportSysErrorAsNtStatus(v16, (int)"FwppProxySubLayerSetSecurityInfoByKey", v15);
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
0x180057050  push    rbp
0x180057052  push    rbx
0x180057053  push    rsi
0x180057054  push    rdi
0x180057055  push    r12
0x180057057  push    r13
0x180057059  push    r14
0x18005705b  push    r15
0x18005705d  lea     rbp, [rsp-7]
0x180057062  sub     rsp, 88h
0x180057069  mov     rax, cs:__security_cookie
0x180057070  xor     rax, rsp
0x180057073  mov     [rbp+3Fh+var_50], rax
0x180057077  mov     r14, [rbp+3Fh+sidGroup]
0x18005707b  xor     eax, eax
0x18005707d  mov     r15, [rbp+3Fh+dacl]
0x180057081  xorps   xmm0, xmm0
0x180057084  mov     r12, [rbp+3Fh+sacl]
0x180057088  mov     rbx, r9
0x18005708b  mov     [rbp+3Fh+var_84], rax
0x18005708f  mov     esi, r8d
0x180057092  mov     [rbp-49h], rax
0x180057096  mov     r13, rdx
0x180057099  mov     rdi, rcx
0x18005709c  mov     [rbp+3Fh+var_58], rax
0x1800570a0  movups  [rbp+3Fh+SecurityDescriptor], xmm0
0x1800570a4  mov     [rbp+3Fh+var_90], rax
0x1800570a8  movups  [rbp+3Fh+var_68], xmm0
0x1800570ac  call    cs:__imp_KeGetCurrentIrql
0x1800570b3  nop     dword ptr [rax+rax+00h]
0x1800570b8  test    al, al
0x1800570ba  jz      short loc_1800570D0
0x1800570bc  mov     r8d, 0C00000BBh
0x1800570c2  lea     rdx, aFwpmsublayerse; "FwpmSubLayerSetSecurityInfoByKey0"
0x1800570c9  call    WfpReportAppErrorAsNtStatus
0x1800570ce  jmp     short loc_180057147
0x1800570d0  test    rdi, rdi
0x1800570d3  jnz     short loc_1800570DD
0x1800570d5  mov     r8d, 0C022001Ch
0x1800570db  jmp     short loc_1800570C2
0x1800570dd  mov     [rsp+0C0h+Sacl], r12; Sacl
0x1800570e2  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x1800570e6  mov     r9, r14
0x1800570e9  mov     [rsp+0C0h+Dacl], r15; Dacl
0x1800570ee  mov     r8, rbx
0x1800570f1  mov     edx, esi
0x1800570f3  call    FwppSecurityDescriptorSetInfo
0x1800570f8  mov     rbx, rax
0x1800570fb  test    rax, rax
0x1800570fe  jnz     short loc_18005714A
0x180057100  lea     r8, [rbp+3Fh+var_90]
0x180057104  lea     rdx, [rbp+3Fh+var_88]
0x180057108  lea     rcx, [rbp+3Fh+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x18005710c  call    BfeSecurityDescriptorEncode
0x180057111  mov     rbx, rax
0x180057114  test    rax, rax
0x180057117  jnz     short loc_18005714A
0x180057119  mov     rdx, [rdi+8]
0x18005711d  lea     rax, [rbp+3Fh+var_88]
0x180057121  mov     rcx, [rdi]
0x180057124  mov     r9d, esi
0x180057127  mov     r8, r13
0x18005712a  mov     [rsp+0C0h+Dacl], rax
0x18005712f  call    FwppProxySubLayerSetSecurityInfoByKey
0x180057134  test    eax, eax
0x180057136  jns     short loc_18005714A
0x180057138  mov     r8d, eax
0x18005713b  lea     rdx, aFwppproxysubla_2; "FwppProxySubLayerSetSecurityInfoByKey"
0x180057142  call    WfpReportSysErrorAsNtStatus
0x180057147  mov     rbx, rax
0x18005714a  lea     rcx, [rbp+3Fh+var_90]
0x18005714e  call    BfeSecurityDescriptorStorageFree
0x180057153  mov     rcx, rbx
0x180057156  call    WfpErrorToFwpErr
0x18005715b  mov     rcx, [rbp+3Fh+var_50]
0x18005715f  xor     rcx, rsp; StackCookie
0x180057162  call    __security_check_cookie
0x180057167  add     rsp, 88h
0x18005716e  pop     r15
0x180057170  pop     r14
0x180057172  pop     r13
0x180057174  pop     r12
0x180057176  pop     rdi
0x180057177  pop     rsi
0x180057178  pop     rbx
0x180057179  pop     rbp
0x18005717a  retn
```
