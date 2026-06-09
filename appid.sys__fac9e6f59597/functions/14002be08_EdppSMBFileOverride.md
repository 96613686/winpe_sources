# EdppSMBFileOverride

- ea: `0x14002be08`
- end: `0x14002bf3c`
- name: `EdppSMBFileOverride`
- size: `308`
- prototype: `__int64 __fastcall(_QWORD *, void *, _BYTE *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14002b5e0`

## callees

- `0x140005750`
- `0x1400057d4`
- `0x14002be08`
- `0x14002d430`
- `0x140032d30`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14002bf1e`
- `ntoskrnl!ObfDereferenceObject` at `0x14002bf1e`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002be88`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14002be88`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14002bea4`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14002bea4`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14002bef4`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14002bef4`

## pseudocode

```c
__int64 __fastcall EdppSMBFileOverride(_QWORD *a1, void *a2, _BYTE *a3)
{
  BOOLEAN v3; // si
  char v4; // r14
  __int64 v5; // rdi
  _QWORD *v7; // rcx
  __int64 result; // rax
  NTSTATUS v11; // ebx
  NTSTATUS IsEnterpriseAllowed; // eax
  PEPROCESS Process; // [rsp+20h] [rbp-30h] BYREF
  __int64 v14; // [rsp+28h] [rbp-28h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+30h] [rbp-20h] BYREF
  char v16; // [rsp+90h] [rbp+40h] BYREF
  BOOLEAN v17; // [rsp+A0h] [rbp+50h] BYREF
  char v18; // [rsp+A8h] [rbp+58h] BYREF

  v3 = 0;
  Process = 0;
  v16 = 0;
  v4 = 0;
  v17 = 0;
  v5 = 0;
  v18 = 0;
  v14 = 0;
  v7 = (_QWORD *)a1[9];
  *(_OWORD *)&SubjectContext.ClientToken = 0;
  *a3 = 0;
  *(_OWORD *)&SubjectContext.PrimaryToken = 0;
  result = *v7 - qword_140019198;
  if ( *v7 == qword_140019198 )
    result = v7[1] - qword_1400191A0;
  if ( result )
  {
    EdppIsEnterpriseSMBFile(a1, &v16);
    v11 = PsLookupProcessByProcessId(a2, &Process);
    if ( v11 >= 0 )
    {
      SeCaptureSubjectContextEx(0, Process, &SubjectContext);
      if ( v16 )
      {
        IsEnterpriseAllowed = SrpIsEnterpriseAllowed(&SubjectContext, *(_QWORD *)(*a1 + 24LL), &v18);
        v4 = v18;
      }
      else
      {
        SrpIsSubjectService(&SubjectContext, &v17);
        IsEnterpriseAllowed = SrpGetPolicyFlags(&SubjectContext, &v14);
        v3 = v17;
        v5 = v14;
      }
      v11 = IsEnterpriseAllowed;
      SeReleaseSubjectContext(&SubjectContext);
      if ( v4 || !v3 && v5 == 17 )
        *a3 = 1;
    }
    if ( Process )
      ObfDereferenceObject(Process);
    return (unsigned int)v11;
  }
  return result;
}

```

## disassembly

```asm
0x14002be08  push    rbp
0x14002be0a  push    rbx
0x14002be0b  push    rsi
0x14002be0c  push    rdi
0x14002be0d  push    r12
0x14002be0f  push    r14
0x14002be11  push    r15
0x14002be13  mov     rbp, rsp
0x14002be16  sub     rsp, 50h
0x14002be1a  xor     sil, sil
0x14002be1d  mov     [rbp+Process], 0
0x14002be25  xorps   xmm0, xmm0
0x14002be28  mov     [rbp+arg_0], 0
0x14002be2c  xor     r14b, r14b
0x14002be2f  mov     [rbp+arg_10], sil
0x14002be33  xor     edi, edi
0x14002be35  mov     [rbp+arg_18], r14b
0x14002be39  mov     r15, rcx
0x14002be3c  mov     [rbp+var_28], rdi
0x14002be40  mov     rcx, [rcx+48h]
0x14002be44  mov     r12, r8
0x14002be47  movups  xmmword ptr [rbp+SubjectContext.ClientToken], xmm0
0x14002be4b  mov     rbx, rdx
0x14002be4e  mov     [r8], sil
0x14002be51  movups  xmmword ptr [rbp+SubjectContext.PrimaryToken], xmm0
0x14002be55  mov     rax, [rcx]
0x14002be58  sub     rax, cs:qword_140019198
0x14002be5f  jnz     short loc_14002BE6C
0x14002be61  mov     rax, [rcx+8]
0x14002be65  sub     rax, cs:qword_1400191A0
0x14002be6c  test    rax, rax
0x14002be6f  jz      loc_14002BF2C
0x14002be75  lea     rdx, [rbp+arg_0]
0x14002be79  mov     rcx, r15
0x14002be7c  call    EdppIsEnterpriseSMBFile
0x14002be81  lea     rdx, [rbp+Process]; Process
0x14002be85  mov     rcx, rbx; ProcessId
0x14002be88  call    cs:__imp_PsLookupProcessByProcessId
0x14002be8f  nop     dword ptr [rax+rax+00h]
0x14002be94  mov     ebx, eax
0x14002be96  test    eax, eax
0x14002be98  js      short loc_14002BF15
0x14002be9a  mov     rdx, [rbp+Process]; Process
0x14002be9e  lea     r8, [rbp+SubjectContext]; SubjectContext
0x14002bea2  xor     ecx, ecx; Thread
0x14002bea4  call    cs:__imp_SeCaptureSubjectContextEx
0x14002beab  nop     dword ptr [rax+rax+00h]
0x14002beb0  lea     rcx, [rbp+SubjectContext]; SubjectSecurityContext
0x14002beb4  cmp     [rbp+arg_0], sil
0x14002beb8  jnz     short loc_14002BEDA
0x14002beba  lea     rdx, [rbp+arg_10]
0x14002bebe  call    SrpIsSubjectService
0x14002bec3  lea     rdx, [rbp+var_28]
0x14002bec7  lea     rcx, [rbp+SubjectContext]
0x14002becb  call    SrpGetPolicyFlags
0x14002bed0  mov     sil, [rbp+arg_10]
0x14002bed4  mov     rdi, [rbp+var_28]
0x14002bed8  jmp     short loc_14002BEEE
0x14002beda  mov     rdx, [r15]
0x14002bedd  lea     r8, [rbp+arg_18]
0x14002bee1  mov     rdx, [rdx+18h]
0x14002bee5  call    SrpIsEnterpriseAllowed
0x14002beea  mov     r14b, [rbp+arg_18]
0x14002beee  lea     rcx, [rbp+SubjectContext]; SubjectContext
0x14002bef2  mov     ebx, eax
0x14002bef4  call    cs:__imp_SeReleaseSubjectContext
0x14002befb  nop     dword ptr [rax+rax+00h]
0x14002bf00  test    r14b, r14b
0x14002bf03  jnz     short loc_14002BF10
0x14002bf05  test    sil, sil
0x14002bf08  jnz     short loc_14002BF15
0x14002bf0a  cmp     rdi, 11h
0x14002bf0e  jnz     short loc_14002BF15
0x14002bf10  mov     byte ptr [r12], 1
0x14002bf15  mov     rcx, [rbp+Process]; Object
0x14002bf19  test    rcx, rcx
0x14002bf1c  jz      short loc_14002BF2A
0x14002bf1e  call    cs:__imp_ObfDereferenceObject
0x14002bf25  nop     dword ptr [rax+rax+00h]
0x14002bf2a  mov     eax, ebx
0x14002bf2c  add     rsp, 50h
0x14002bf30  pop     r15
0x14002bf32  pop     r14
0x14002bf34  pop     r12
0x14002bf36  pop     rdi
0x14002bf37  pop     rsi
0x14002bf38  pop     rbx
0x14002bf39  pop     rbp
0x14002bf3a  retn
```
