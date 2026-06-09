# IkeSaDbSetSecurityInfoAndSave

- ea: `0x1800ec9a0`
- end: `0x1800eca86`
- name: `IkeSaDbSetSecurityInfoAndSave`
- size: `230`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR *ObjectDescriptor, RPC_BINDING_HANDLE BindingHandle, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR ModificationDescriptor)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006f340`

## callees

- `0x180008388`
- `0x18004aa3c`
- `0x180050850`
- `0x1800ec7c4`
- `0x1800ec9a0`
- `0x1801122f0`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x1800eca0a`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800eca0a`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800eca37`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800eca4c`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800eca37`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x1800eca4c`

## string_xrefs

- `0x1800eca1d`: `IkeSaveRpcSdRegConfig`
- `0x1800ec9cd`: `IkeSaDbSetSecurityInfoAndSave`
- `0x1800eca54`: `IkeSaDbSetSecurityInfoAndSave`
- `0x1800eca60`: `IkeSaDbSetSecurityInfoAndSave`

## pseudocode

```c
__int64 __fastcall IkeSaDbSetSecurityInfoAndSave(
        PSECURITY_DESCRIPTOR *ObjectDescriptor,
        RPC_BINDING_HANDLE BindingHandle,
        SECURITY_INFORMATION SecurityInformation,
        PSECURITY_DESCRIPTOR ModificationDescriptor)
{
  __int64 v8; // rbx
  BYTE *v9; // rbx
  ULONG v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  __int64 v14; // rax
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-38h] BYREF

  SecurityDescriptor = 0;
  TraceLogHelper("IkeSaDbSetSecurityInfoAndSave", 1);
  v8 = IkeSaDbSetSecurityInfo(
         *ObjectDescriptor,
         BindingHandle,
         SecurityInformation,
         ModificationDescriptor,
         (__int64)&SecurityDescriptor);
  if ( v8
    || (v9 = (BYTE *)SecurityDescriptor,
        v10 = RtlLengthSecurityDescriptor(SecurityDescriptor),
        v14 = WfpRegSetBinary(v12, v11, v13, v10, v9),
        (v8 = IkeReturnError(v14, "IkeSaveRpcSdRegConfig")) != 0) )
  {
    DestroyPrivateObjectSecurity(&SecurityDescriptor);
  }
  else
  {
    DestroyPrivateObjectSecurity(ObjectDescriptor);
    *ObjectDescriptor = SecurityDescriptor;
  }
  TraceLogHelper("IkeSaDbSetSecurityInfoAndSave", 0);
  return IkeReturnError(v8, "IkeSaDbSetSecurityInfoAndSave");
}

```

## disassembly

```asm
0x1800ec9a0  push    rbx
0x1800ec9a2  push    rsi
0x1800ec9a3  push    rdi
0x1800ec9a4  push    r14
0x1800ec9a6  sub     rsp, 48h
0x1800ec9aa  mov     rax, cs:__security_cookie
0x1800ec9b1  xor     rax, rsp
0x1800ec9b4  mov     [rsp+68h+var_30], rax
0x1800ec9b9  mov     rbx, rdx
0x1800ec9bc  mov     [rsp+68h+SecurityDescriptor], 0
0x1800ec9c5  mov     r14, rcx
0x1800ec9c8  mov     edx, 1
0x1800ec9cd  lea     rcx, aIkesadbsetsecu; "IkeSaDbSetSecurityInfoAndSave"
0x1800ec9d4  mov     rsi, r9
0x1800ec9d7  mov     edi, r8d
0x1800ec9da  call    TraceLogHelper
0x1800ec9df  mov     rcx, [r14]; pSecurityDescriptor
0x1800ec9e2  lea     rax, [rsp+68h+SecurityDescriptor]
0x1800ec9e7  mov     r9, rsi; ModificationDescriptor
0x1800ec9ea  mov     [rsp+68h+var_48], rax; __int64
0x1800ec9ef  mov     r8d, edi; SecurityInformation
0x1800ec9f2  mov     rdx, rbx; BindingHandle
0x1800ec9f5  call    IkeSaDbSetSecurityInfo
0x1800ec9fa  mov     rbx, rax
0x1800ec9fd  test    rax, rax
0x1800eca00  jnz     short loc_1800ECA47
0x1800eca02  mov     rbx, [rsp+68h+SecurityDescriptor]
0x1800eca07  mov     rcx, rbx; SecurityDescriptor
0x1800eca0a  call    cs:__imp_RtlLengthSecurityDescriptor
0x1800eca10  mov     r9d, eax
0x1800eca13  mov     [rsp+68h+var_48], rbx
0x1800eca18  call    WfpRegSetBinary
0x1800eca1d  lea     rdx, aIkesaverpcsdre; "IkeSaveRpcSdRegConfig"
0x1800eca24  mov     rcx, rax
0x1800eca27  call    IkeReturnError
0x1800eca2c  mov     rbx, rax
0x1800eca2f  test    rax, rax
0x1800eca32  jnz     short loc_1800ECA47
0x1800eca34  mov     rcx, r14; ObjectDescriptor
0x1800eca37  call    cs:__imp_DestroyPrivateObjectSecurity
0x1800eca3d  mov     rax, [rsp+68h+SecurityDescriptor]
0x1800eca42  mov     [r14], rax
0x1800eca45  jmp     short loc_1800ECA52
0x1800eca47  lea     rcx, [rsp+68h+SecurityDescriptor]; ObjectDescriptor
0x1800eca4c  call    cs:__imp_DestroyPrivateObjectSecurity
0x1800eca52  xor     edx, edx
0x1800eca54  lea     rcx, aIkesadbsetsecu; "IkeSaDbSetSecurityInfoAndSave"
0x1800eca5b  call    TraceLogHelper
0x1800eca60  lea     rdx, aIkesadbsetsecu; "IkeSaDbSetSecurityInfoAndSave"
0x1800eca67  mov     rcx, rbx
0x1800eca6a  call    IkeReturnError
0x1800eca6f  mov     rcx, [rsp+68h+var_30]
0x1800eca74  xor     rcx, rsp; StackCookie
0x1800eca77  call    __security_check_cookie
0x1800eca7c  add     rsp, 48h
0x1800eca80  pop     r14
0x1800eca82  pop     rdi
0x1800eca83  pop     rsi
0x1800eca84  pop     rbx
0x1800eca85  retn
```
