# FwpmLayerSetSecurityInfoByKey0

- ea: `0x180054d50`
- end: `0x180054e7c`
- name: `FwpmLayerSetSecurityInfoByKey0`
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
- `0x180011374`
- `0x1800203c0`
- `0x180054d50`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180054dac`
- `ntoskrnl!KeGetCurrentIrql` at `0x180054dac`

## string_xrefs

- `0x180054dc2`: `FwpmLayerSetSecurityInfoByKey0`
- `0x180054e3b`: `FwppProxyLayerSetSecurityInfoByKey`

## pseudocode

```c
NTSTATUS __stdcall FwpmLayerSetSecurityInfoByKey0(
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
    v13 = WfpReportAppErrorAsNtStatus(v11, (__int64)"FwpmLayerSetSecurityInfoByKey0", v12);
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
      v15 = FwppProxyLayerSetSecurityInfoByKey(
              *(_QWORD *)engineHandle,
              *((_QWORD *)engineHandle + 1),
              v9,
              securityInfo,
              (__int64)&v19);
      if ( v15 < 0 )
      {
        v13 = WfpReportSysErrorAsNtStatus(v16, (int)"FwppProxyLayerSetSecurityInfoByKey", v15);
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
0x180054d50  push    rbp
0x180054d52  push    rbx
0x180054d53  push    rsi
0x180054d54  push    rdi
0x180054d55  push    r12
0x180054d57  push    r13
0x180054d59  push    r14
0x180054d5b  push    r15
0x180054d5d  lea     rbp, [rsp-7]
0x180054d62  sub     rsp, 88h
0x180054d69  mov     rax, cs:__security_cookie
0x180054d70  xor     rax, rsp
0x180054d73  mov     [rbp+3Fh+var_50], rax
0x180054d77  mov     r14, [rbp+3Fh+sidGroup]
0x180054d7b  xor     eax, eax
0x180054d7d  mov     r15, [rbp+3Fh+dacl]
0x180054d81  xorps   xmm0, xmm0
0x180054d84  mov     r12, [rbp+3Fh+sacl]
0x180054d88  mov     rbx, r9
0x180054d8b  mov     [rbp+3Fh+var_84], rax
0x180054d8f  mov     esi, r8d
0x180054d92  mov     [rbp-49h], rax
0x180054d96  mov     r13, rdx
0x180054d99  mov     rdi, rcx
0x180054d9c  mov     [rbp+3Fh+var_58], rax
0x180054da0  movups  [rbp+3Fh+SecurityDescriptor], xmm0
0x180054da4  mov     [rbp+3Fh+var_90], rax
0x180054da8  movups  [rbp+3Fh+var_68], xmm0
0x180054dac  call    cs:__imp_KeGetCurrentIrql
0x180054db3  nop     dword ptr [rax+rax+00h]
0x180054db8  test    al, al
0x180054dba  jz      short loc_180054DD0
0x180054dbc  mov     r8d, 0C00000BBh
0x180054dc2  lea     rdx, aFwpmlayersetse; "FwpmLayerSetSecurityInfoByKey0"
0x180054dc9  call    WfpReportAppErrorAsNtStatus
0x180054dce  jmp     short loc_180054E47
0x180054dd0  test    rdi, rdi
0x180054dd3  jnz     short loc_180054DDD
0x180054dd5  mov     r8d, 0C022001Ch
0x180054ddb  jmp     short loc_180054DC2
0x180054ddd  mov     [rsp+0C0h+Sacl], r12; Sacl
0x180054de2  lea     rcx, [rbp+3Fh+SecurityDescriptor]; SecurityDescriptor
0x180054de6  mov     r9, r14
0x180054de9  mov     [rsp+0C0h+Dacl], r15; Dacl
0x180054dee  mov     r8, rbx
0x180054df1  mov     edx, esi
0x180054df3  call    FwppSecurityDescriptorSetInfo
0x180054df8  mov     rbx, rax
0x180054dfb  test    rax, rax
0x180054dfe  jnz     short loc_180054E4A
0x180054e00  lea     r8, [rbp+3Fh+var_90]
0x180054e04  lea     rdx, [rbp+3Fh+var_88]
0x180054e08  lea     rcx, [rbp+3Fh+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x180054e0c  call    BfeSecurityDescriptorEncode
0x180054e11  mov     rbx, rax
0x180054e14  test    rax, rax
0x180054e17  jnz     short loc_180054E4A
0x180054e19  mov     rdx, [rdi+8]
0x180054e1d  lea     rax, [rbp+3Fh+var_88]
0x180054e21  mov     rcx, [rdi]
0x180054e24  mov     r9d, esi
0x180054e27  mov     r8, r13
0x180054e2a  mov     [rsp+0C0h+Dacl], rax
0x180054e2f  call    FwppProxyLayerSetSecurityInfoByKey
0x180054e34  test    eax, eax
0x180054e36  jns     short loc_180054E4A
0x180054e38  mov     r8d, eax
0x180054e3b  lea     rdx, aFwppproxylayer_0; "FwppProxyLayerSetSecurityInfoByKey"
0x180054e42  call    WfpReportSysErrorAsNtStatus
0x180054e47  mov     rbx, rax
0x180054e4a  lea     rcx, [rbp+3Fh+var_90]
0x180054e4e  call    BfeSecurityDescriptorStorageFree
0x180054e53  mov     rcx, rbx
0x180054e56  call    WfpErrorToFwpErr
0x180054e5b  mov     rcx, [rbp+3Fh+var_50]
0x180054e5f  xor     rcx, rsp; StackCookie
0x180054e62  call    __security_check_cookie
0x180054e67  add     rsp, 88h
0x180054e6e  pop     r15
0x180054e70  pop     r14
0x180054e72  pop     r13
0x180054e74  pop     r12
0x180054e76  pop     rdi
0x180054e77  pop     rsi
0x180054e78  pop     rbx
0x180054e79  pop     rbp
0x180054e7a  retn
```
