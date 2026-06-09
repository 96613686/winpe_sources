# BfeGlobalConfigComponentSetConfig

- ea: `0x18004c910`
- end: `0x18004c9ef`
- name: `BfeGlobalConfigComponentSetConfig`
- size: `223`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180043320`
- `0x180062bc0`

## callees

- `0x180010360`
- `0x180018b74`
- `0x180034650`
- `0x180045774`
- `0x18004c910`
- `0x180068800`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c989`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004c989`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c99e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c99e`

## string_xrefs

- `0x18004c9d2`: `BfeGlobalConfigComponentSetConfig`
- `0x18004c947`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x18004c9be`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`

## pseudocode

```c
__int64 __fastcall BfeGlobalConfigComponentSetConfig(int *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  __int64 v4; // rcx
  int IsEnabledDeviceUsageNoInline; // eax

  v3 = BfeAccessCheck((char *)qword_1800F2668[173], 0x400u, 0);
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
           qword_1800F2668[215]);
    if ( !v3 )
      return v3;
LABEL_11:
    WfpReportError(v3, "BfeGlobalConfigComponentSetConfig");
    return v3;
  }
  if ( (qword_1800F2668[369] & 0x10) != 0 )
    IsEnabledDeviceUsageNoInline = qword_1800F2668[369] & 1;
  else
    IsEnabledDeviceUsageNoInline = Feature_Netsec_AuditMode_Hardening__private_IsEnabledDeviceUsageNoInline();
  if ( IsEnabledDeviceUsageNoInline )
  {
    AcquireSRWLockExclusive((PSRWLOCK)&qword_1800F2668[217]);
    LODWORD(qword_1800F2668[215]) = *a1;
    ReleaseSRWLockExclusive((PSRWLOCK)&qword_1800F2668[217]);
  }
  else
  {
    LODWORD(qword_1800F2668[215]) = *a1;
  }
  return v3;
}

```

## disassembly

```asm
0x18004c910  mov     [rsp+arg_0], rbx
0x18004c915  push    rdi
0x18004c916  sub     rsp, 30h
0x18004c91a  mov     rdi, rcx
0x18004c91d  xor     r8d, r8d
0x18004c920  mov     rcx, cs:qword_1800F2668+568h; pSecurityDescriptor
0x18004c927  mov     edx, 400h
0x18004c92c  call    BfeAccessCheck
0x18004c931  mov     rbx, rax
0x18004c934  test    rax, rax
0x18004c937  jnz     loc_18004C9D2
0x18004c93d  mov     r9d, [rdi]
0x18004c940  lea     r8, aEnablepacketqu; "EnablePacketQueue"
0x18004c947  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\BF"...
0x18004c94e  call    BfeRegSetDWord
0x18004c953  mov     rbx, rax
0x18004c956  test    rax, rax
0x18004c959  jnz     short loc_18004C9D2
0x18004c95b  mov     ecx, [rdi]
0x18004c95d  call    BfeSetDriverQueuingState
0x18004c962  mov     rbx, rax
0x18004c965  test    rax, rax
0x18004c968  jnz     short loc_18004C9B0
0x18004c96a  mov     eax, dword ptr cs:qword_1800F2668+0B88h
0x18004c970  test    al, 10h
0x18004c972  jz      short loc_18004C979
0x18004c974  and     eax, 1
0x18004c977  jmp     short loc_18004C97E
0x18004c979  call    Feature_Netsec_AuditMode_Hardening__private_IsEnabledDeviceUsageNoInline
0x18004c97e  test    eax, eax
0x18004c980  jz      short loc_18004C9A6
0x18004c982  lea     rcx, qword_1800F2668+6C8h; SRWLock
0x18004c989  call    cs:__imp_AcquireSRWLockExclusive
0x18004c98f  mov     eax, [rdi]
0x18004c991  lea     rcx, qword_1800F2668+6C8h; SRWLock
0x18004c998  mov     dword ptr cs:qword_1800F2668+6B8h, eax
0x18004c99e  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c9a4  jmp     short loc_18004C9E1
0x18004c9a6  mov     eax, [rdi]
0x18004c9a8  mov     dword ptr cs:qword_1800F2668+6B8h, eax
0x18004c9ae  jmp     short loc_18004C9E1
0x18004c9b0  mov     r9d, dword ptr cs:qword_1800F2668+6B8h
0x18004c9b7  lea     r8, aEnablepacketqu; "EnablePacketQueue"
0x18004c9be  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\BF"...
0x18004c9c5  call    BfeRegSetDWord
0x18004c9ca  mov     rbx, rax
0x18004c9cd  test    rax, rax
0x18004c9d0  jz      short loc_18004C9E1
0x18004c9d2  lea     rdx, aBfeglobalconfi_2; "BfeGlobalConfigComponentSetConfig"
0x18004c9d9  mov     rcx, rbx
0x18004c9dc  call    WfpReportError
0x18004c9e1  mov     rax, rbx
0x18004c9e4  mov     rbx, [rsp+38h+arg_0]
0x18004c9e9  add     rsp, 30h
0x18004c9ed  pop     rdi
0x18004c9ee  retn
```
