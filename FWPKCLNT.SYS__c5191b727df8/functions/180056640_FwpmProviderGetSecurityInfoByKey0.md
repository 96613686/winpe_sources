# FwpmProviderGetSecurityInfoByKey0

- ea: `0x180056640`
- end: `0x180056760`
- name: `FwpmProviderGetSecurityInfoByKey0`
- size: `288`
- prototype: `NTSTATUS __stdcall(HANDLE engineHandle, const GUID *key, SECURITY_INFORMATION securityInfo, PSID *sidOwner, PSID *sidGroup, PACL *dacl, PACL *sacl, PSECURITY_DESCRIPTOR *securityDescriptor)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004904`
- `0x1800050cc`
- `0x180008440`
- `0x180008f10`
- `0x18000fccc`
- `0x180011748`
- `0x1800203c0`
- `0x180056640`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180056694`
- `ntoskrnl!KeGetCurrentIrql` at `0x180056694`

## string_xrefs

- `0x1800566aa`: `FwpmProviderGetSecurityInfoByKey0`
- `0x1800566ed`: `FwppProxyProviderGetSecurityInfoByKey`

## pseudocode

```c
NTSTATUS __stdcall FwpmProviderGetSecurityInfoByKey0(
        HANDLE engineHandle,
        const GUID *key,
        SECURITY_INFORMATION securityInfo,
        PSID *sidOwner,
        PSID *sidGroup,
        PACL *dacl,
        PACL *sacl,
        PSECURITY_DESCRIPTOR *securityDescriptor)
{
  int v10; // r13d
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rax
  int SecurityInfoByKey; // eax
  __int64 v16; // rcx
  __int64 Info; // rbx
  PSECURITY_DESCRIPTOR SecurityDescriptor[2]; // [rsp+30h] [rbp-68h] BYREF

  v10 = (int)key;
  *(_OWORD *)SecurityDescriptor = 0;
  if ( KeGetCurrentIrql() )
  {
    v13 = 3221225659LL;
LABEL_3:
    v14 = WfpReportAppErrorAsNtStatus(v12, (__int64)"FwpmProviderGetSecurityInfoByKey0", v13);
    goto LABEL_9;
  }
  if ( !engineHandle || !securityDescriptor )
  {
    v13 = 3223453724LL;
    goto LABEL_3;
  }
  SecurityInfoByKey = FwppProxyProviderGetSecurityInfoByKey(
                        *(_QWORD *)engineHandle,
                        *((_QWORD *)engineHandle + 1),
                        v10,
                        securityInfo,
                        (__int64)SecurityDescriptor);
  if ( SecurityInfoByKey >= 0 )
  {
    Info = FwppSecurityDescriptorGetInfo(SecurityDescriptor[1], securityInfo, sidOwner, sidGroup, dacl, sacl);
    if ( !Info )
    {
      *securityDescriptor = SecurityDescriptor[1];
      return WfpErrorToFwpErr(Info);
    }
    goto LABEL_10;
  }
  v14 = WfpReportSysErrorAsNtStatus(v16, (int)"FwppProxyProviderGetSecurityInfoByKey", SecurityInfoByKey);
LABEL_9:
  Info = v14;
  if ( v14 )
LABEL_10:
    FwppDeepFree_GUID(SecurityDescriptor[1]);
  return WfpErrorToFwpErr(Info);
}

```

## disassembly

```asm
0x180056640  push    rbx
0x180056642  push    rbp
0x180056643  push    rsi
0x180056644  push    rdi
0x180056645  push    r12
0x180056647  push    r13
0x180056649  push    r14
0x18005664b  push    r15
0x18005664d  sub     rsp, 58h
0x180056651  mov     rax, cs:__security_cookie
0x180056658  xor     rax, rsp
0x18005665b  mov     [rsp+98h+var_58], rax
0x180056660  mov     r14, [rsp+98h+sidGroup]
0x180056668  xorps   xmm0, xmm0
0x18005666b  mov     r15, [rsp+98h+dacl]
0x180056673  mov     rbp, r9
0x180056676  mov     r12, [rsp+98h+sacl]
0x18005667e  mov     esi, r8d
0x180056681  mov     rdi, [rsp+98h+securityDescriptor]
0x180056689  mov     r13, rdx
0x18005668c  movups  xmmword ptr [rsp+98h+SecurityDescriptor], xmm0
0x180056691  mov     rbx, rcx
0x180056694  call    cs:__imp_KeGetCurrentIrql
0x18005669b  nop     dword ptr [rax+rax+00h]
0x1800566a0  test    al, al
0x1800566a2  jz      short loc_1800566B8
0x1800566a4  mov     r8d, 0C00000BBh
0x1800566aa  lea     rdx, aFwpmproviderge_0; "FwpmProviderGetSecurityInfoByKey0"
0x1800566b1  call    WfpReportAppErrorAsNtStatus
0x1800566b6  jmp     short loc_1800566F9
0x1800566b8  test    rbx, rbx
0x1800566bb  jnz     short loc_1800566C5
0x1800566bd  mov     r8d, 0C022001Ch
0x1800566c3  jmp     short loc_1800566AA
0x1800566c5  test    rdi, rdi
0x1800566c8  jz      short loc_1800566BD
0x1800566ca  mov     rdx, [rbx+8]
0x1800566ce  lea     rax, [rsp+98h+SecurityDescriptor]
0x1800566d3  mov     rcx, [rbx]
0x1800566d6  mov     r9d, esi
0x1800566d9  mov     r8, r13
0x1800566dc  mov     [rsp+98h+Dacl], rax
0x1800566e1  call    FwppProxyProviderGetSecurityInfoByKey
0x1800566e6  test    eax, eax
0x1800566e8  jns     short loc_180056732
0x1800566ea  mov     r8d, eax
0x1800566ed  lea     rdx, aFwppproxyprovi_9; "FwppProxyProviderGetSecurityInfoByKey"
0x1800566f4  call    WfpReportSysErrorAsNtStatus
0x1800566f9  mov     rbx, rax
0x1800566fc  test    rax, rax
0x1800566ff  jz      short loc_18005670B
0x180056701  mov     rcx, [rsp+98h+SecurityDescriptor+8]
0x180056706  call    FwppDeepFree_GUID
0x18005670b  mov     rcx, rbx
0x18005670e  call    WfpErrorToFwpErr
0x180056713  mov     rcx, [rsp+98h+var_58]
0x180056718  xor     rcx, rsp; StackCookie
0x18005671b  call    __security_check_cookie
0x180056720  add     rsp, 58h
0x180056724  pop     r15
0x180056726  pop     r14
0x180056728  pop     r13
0x18005672a  pop     r12
0x18005672c  pop     rdi
0x18005672d  pop     rsi
0x18005672e  pop     rbp
0x18005672f  pop     rbx
0x180056730  retn
0x180056732  mov     rcx, [rsp+98h+SecurityDescriptor+8]; SecurityDescriptor
0x180056737  mov     r9, r14
0x18005673a  mov     [rsp+98h+Sacl], r12; Sacl
0x18005673f  mov     r8, rbp
0x180056742  mov     edx, esi
0x180056744  mov     [rsp+98h+Dacl], r15; Dacl
0x180056749  call    FwppSecurityDescriptorGetInfo
0x18005674e  mov     rbx, rax
0x180056751  test    rax, rax
0x180056754  jnz     short loc_180056701
0x180056756  mov     rax, [rsp+98h+SecurityDescriptor+8]
0x18005675b  mov     [rdi], rax
0x18005675e  jmp     short loc_18005670B
```
