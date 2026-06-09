# BfeGlobalConfigComponentSetConfig

- ea: `0x18004e3d8`
- end: `0x18004e4c8`
- name: `BfeGlobalConfigComponentSetConfig`
- size: `240`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180044f80`
- `0x180064f10`

## callees

- `0x180010d60`
- `0x1800197d0`
- `0x18001ea3c`
- `0x180034554`
- `0x18004e3d8`
- `0x18006ae10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004e455`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004e455`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e470`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004e470`

## string_xrefs

- `0x18004e4aa`: `BfeGlobalConfigComponentSetConfig`
- `0x18004e40f`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x18004e496`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`

## pseudocode

```c
__int64 __fastcall BfeGlobalConfigComponentSetConfig(int *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rcx
  int IsEnabledDeviceUsageNoInline; // eax

  v3 = BfeAccessCheck((char *)ParentDescriptor, 0x400u, 0);
  if ( v3 )
    goto LABEL_11;
  v3 = BfeRegSetDWord(
         v2,
         L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Options",
         L"EnablePacketQueue",
         *a1);
  if ( v3 )
    goto LABEL_11;
  v3 = BfeSetDriverQueuingState((unsigned int)*a1);
  if ( v3 )
  {
    v3 = BfeRegSetDWord(
           v4,
           L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Options",
           L"EnablePacketQueue",
           gBfeGlobalConfigComponent);
    if ( !v3 )
      return v3;
LABEL_11:
    WfpReportError(v3, "BfeGlobalConfigComponentSetConfig");
    return v3;
  }
  if ( (Feature_Netsec_AuditMode_Hardening__private_featureState & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = Feature_Netsec_AuditMode_Hardening__private_featureState & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_Netsec_AuditMode_Hardening__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
  {
    AcquireSRWLockExclusive(&stru_1800F5D50);
    LODWORD(gBfeGlobalConfigComponent) = *a1;
    ReleaseSRWLockExclusive(&stru_1800F5D50);
  }
  else
  {
    LODWORD(gBfeGlobalConfigComponent) = *a1;
  }
  return v3;
}

```

## disassembly

```asm
0x18004e3d8  mov     [rsp+arg_0], rbx
0x18004e3dd  push    rdi
0x18004e3de  sub     rsp, 30h
0x18004e3e2  mov     rdi, rcx
0x18004e3e5  xor     r8d, r8d
0x18004e3e8  mov     rcx, cs:ParentDescriptor; pSecurityDescriptor
0x18004e3ef  mov     edx, 400h
0x18004e3f4  call    BfeAccessCheck
0x18004e3f9  mov     rbx, rax
0x18004e3fc  test    rax, rax
0x18004e3ff  jnz     loc_18004E4AA
0x18004e405  mov     r9d, [rdi]
0x18004e408  lea     r8, aEnablepacketqu; "EnablePacketQueue"
0x18004e40f  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\BF"...
0x18004e416  call    BfeRegSetDWord
0x18004e41b  mov     rbx, rax
0x18004e41e  test    rax, rax
0x18004e421  jnz     loc_18004E4AA
0x18004e427  mov     ecx, [rdi]
0x18004e429  call    BfeSetDriverQueuingState
0x18004e42e  mov     rbx, rax
0x18004e431  test    rax, rax
0x18004e434  jnz     short loc_18004E488
0x18004e436  mov     eax, cs:Feature_Netsec_AuditMode_Hardening__private_featureState
0x18004e43c  test    al, 10h
0x18004e43e  jz      short loc_18004E445
0x18004e440  and     eax, 1
0x18004e443  jmp     short loc_18004E44A
0x18004e445  call    Feature_Netsec_AuditMode_Hardening__private_IsEnabledDeviceUsageNoInline
0x18004e44a  test    eax, eax
0x18004e44c  jz      short loc_18004E47E
0x18004e44e  lea     rcx, stru_1800F5D50; SRWLock
0x18004e455  call    cs:__imp_AcquireSRWLockExclusive
0x18004e45c  nop     dword ptr [rax+rax+00h]
0x18004e461  mov     eax, [rdi]
0x18004e463  lea     rcx, stru_1800F5D50; SRWLock
0x18004e46a  mov     dword ptr cs:gBfeGlobalConfigComponent, eax
0x18004e470  call    cs:__imp_ReleaseSRWLockExclusive
0x18004e477  nop     dword ptr [rax+rax+00h]
0x18004e47c  jmp     short loc_18004E4B9
0x18004e47e  mov     eax, [rdi]
0x18004e480  mov     dword ptr cs:gBfeGlobalConfigComponent, eax
0x18004e486  jmp     short loc_18004E4B9
0x18004e488  mov     r9d, dword ptr cs:gBfeGlobalConfigComponent
0x18004e48f  lea     r8, aEnablepacketqu; "EnablePacketQueue"
0x18004e496  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\BF"...
0x18004e49d  call    BfeRegSetDWord
0x18004e4a2  mov     rbx, rax
0x18004e4a5  test    rax, rax
0x18004e4a8  jz      short loc_18004E4B9
0x18004e4aa  lea     rdx, aBfeglobalconfi_2; "BfeGlobalConfigComponentSetConfig"
0x18004e4b1  mov     rcx, rbx
0x18004e4b4  call    WfpReportError
0x18004e4b9  mov     rax, rbx
0x18004e4bc  mov     rbx, [rsp+38h+arg_0]
0x18004e4c1  add     rsp, 30h
0x18004e4c5  pop     rdi
0x18004e4c6  retn
```
